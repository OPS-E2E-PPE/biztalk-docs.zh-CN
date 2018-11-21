---
title: 使用 Unity 容器创建自定义冲突解决程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6f95f5e-64dd-4cc6-802f-0c5fd6a01c91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5280108bddeeacd78b9e8f6df0fa908329af8dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012670"
---
# <a name="creating-a-custom-resolver-with-a-unity-container"></a>使用 Unity 容器创建自定义冲突解决程序
您可以创建自定义冲突解决程序使用[Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) 进行的解析逻辑和元数据源的运行时依赖关系注入。
  
 **这一事实提供程序**  
  
 这一事实提供程序是实现的类的实例**IFactProvider**接口。 此接口公开一个名为方法的三个不同的重载**RegisterFact**。 此方法采用在消息中，冲突解决程序配置，以及在某些情况下，管道上下文中，并返回一个对象。 此对象可能以某种方式输入中提取的信息，可能是某种形式的计算，它或者它可能会看到从某些外部源。 这一事实提供程序返回的每个对象可以作为事实引用和更高版本的事实转换器用于解析容器通常添加到列表。  
  
 Unity 冲突解决程序可能有零个或多个事实提供程序，可以添加或删除任何时间通过单一配置更改。  
  
 下面的代码示范了这一事实提供程序中所包含的逻辑。 此外可以在 ESB ItineraryStaticFactProvider.cs 文件中找到此代码。Resolver.Itinerary.Facts 项目。 它是路线的在收集从解析程序的连接字符串的名称和版本的旅行计划静态冲突解决程序组件。  
  
```csharp  
public object RegisterFact(IBaseMessage message, IPipelineContext pipelineContext, Dictionary\<string, string\> resolverContents)  
{  
    return GetItineraryFactFromResolver(resolverContents);  
}  
  
private static object GetItineraryFactFromResolver(Dictionary\<string, string\> resolverContents)  
{              
    if (resolverContents == null)  
        throw new ArgumentNullException("resolverContents");  
  
    ItineraryFact itineraryFact = new ItineraryFact();  
    itineraryFact.Name = ResolverMgr.GetConfigValue(resolverContents, true, "name");  
    string version = ResolverMgr.GetConfigValue(resolverContents, false, "version");  
    if (!string.IsNullOrEmpty(version))  
    {  
        EventLogger.Write(string.Format("Version set with value {0}.", version));  
        itineraryFact.SetVersion(version);  
    }  
    return itineraryFact;  
}  
```  
  
 **这一事实转换器**  
  
 这一事实转换器是实现的类的实例**IFactTranslator**接口。 此接口公开一个名为的单个方法**TranslateFact**。 此方法采用一个对象数组，其中包含一系列事实和更高版本将返回的冲突解决程序，使用这一事实转换器的冲突解决程序字典中。 这一事实转换器负责处理事实提供程序中有意义的方式提供的事实数据，然后填充冲突解决程序字典。  
  
 Unity 冲突解决程序可能有零个或多个事实翻译人员，可以添加或删除任何时间通过单一配置更改。  
  
 下面的代码示范了这一事实转换器所包含的逻辑。 此外可以在 ESB ItineraryStaticFactTranslator.cs 文件中找到此代码。Resolver.Itinerary.Facts 项目。 它是在执行数据库查询，以按名称和 （可选） 版本收集路线的旅行计划 XML 路线静态冲突解决程序组件。  
  
```csharp  
public void TranslateFact(object[] facts, Dictionary\<string, string\> factDictionary)  
{  
    #region Argument Check  
    if (null == facts) throw new ArgumentNullException("fact");  
    if (null == factDictionary) throw new ArgumentNullException("factDictionary");  
    #endregion  
  
    #region Local Variables  
    Version version = new Version(1, 0);                         
    #endregion  
    try  
    {  
        foreach (object fact in facts)  
        {  
            if (fact is ItineraryFact)  
            {  
                ItineraryFact targetFact = (ItineraryFact)fact;  
                factDictionary.Add(_FactKeyItineraryName, targetFact.Name ?? string.Empty);  
                if (null != targetFact.Version)  
                {  
                    factDictionary.Add(_FactKeyItineraryVersion, targetFact.Version.ToString(2) ?? string.Empty);  
                    version = targetFact.Version;  
                }  
  
                string xml = null;  
  
                if (targetFact.Version != null)  
                {  
                    xml = _repositoryProvider.GetItinerary(targetFact.Name, version.Major, version.Minor);  
                }  
                else  
                {  
                    xml = _repositoryProvider.GetItinerary(targetFact.Name);  
                }  
                if (!string.IsNullOrEmpty(xml))  
                {  
                    factDictionary.Add(_FactKeyItinerary, xml);  
                }  
  
                break;  
            }  
        }  
    }  
    #region Exception Handling  
    catch (System.Exception)  
    {  
        throw;  
    }              
    #endregion  
}  
#endregion  
```  
  
 **解决容器**  
  
 解析容器是一个类，实现**IResolveContainer**接口。 通常情况下，它还实现**IResolveProvider**接口。 **IResolveContainer**接口公开一个名为的单个方法**初始化**以**IUnityContainer**。 容器传递给此方法将包含所有依赖项 (即，类的实例**IFactProvider**和**IFactTranslator**，以及所需的任何其他类型) 的必要条件若要完成其处理的解析程序。  
  
 下面的代码是实现的示例**IResolveContainer**接口。 此外可以在 ESB StaticItineraryResolveContainer.cs 文件中找到此代码。Resolver.Itinerary 项目。  
  
```csharp  
#region IResolveContainer Members  
  
private static IUnityContainer Container;  
  
// <summary>  
// This is used by the Unity resolver to initialize the current   
// object with the Unity container.  
// </summary>  
// <param name="container">Unity container used for dependency   
// injection.</param>  
// <remarks>  
// The container used is the ITINERARY container, although this is   
// configurable in Esb.config.  
// </remarks>  
  
public void Initialize(IUnityContainer container)  
{  
  if (container == null)  
    throw new ArgumentNullException("container");  
  
  Container = container;  
}  
#endregion  
```  
  
 中的实现中的解析容器**解决**方法从**IResolveProvider**接口后，它是需循环访问所有事实供应商和 Unity 中的事实翻译若要允许每个约束来执行其处理的容器。  
  
 以下代码是逻辑的解析容器中包含的示例。 此外可以在 ESB StaticItineraryResolveContainer.cs 文件中找到此代码。Resolver.Itinerary 项目。  
  
```csharp  
public Dictionary\<string, string\> Resolve(ResolverInfo resolverInfo,  
    XLANGMessage message)  
{  
    #region Argument Check  
    if (String.IsNullOrEmpty(resolverInfo.Config))  
        throw new ArgumentNullException("resolverInfo.Config");  
    if (String.IsNullOrEmpty(resolverInfo.Resolver))  
        throw new ArgumentNullException("resolverInfo.Resolver");  
    if (null == message)  
        throw new ArgumentNullException("message");  
    #endregion Argument Check  
  
    return ResolveStatic(resolverInfo.Config, resolverInfo.Resolver,  
        (factProvider, resolverContent) =>   
            factProvider.RegisterFact(message, resolverContent)  
     );  
}          
  
private Dictionary\<string, string\> ResolveStatic(string config, string resolver,   
    Func<IFactProvider, Dictionary\<string, string\>, object> RegisterFact)  
{  
    try  
    {  
        EventLogger.Write(string.Format("Received {0} value in ITINERARY STATIC resolver.", config));  
  
        Dictionary\<string, string\> queryParams =  
                ResolverMgr.GetFacts(config, resolver);  
  
        List<object> facts = new List<object>();  
  
        foreach (IFactProvider factProvider in Container.ResolveAll<IFactProvider>())  
        {  
            facts.Add(RegisterFact(factProvider, queryParams));  
        }  
  
        Dictionary\<string, string\> resolverDictionary = new Dictionary\<string, string\>();  
  
        object[] convertedFacts = facts.ToArray();  
  
        foreach (IFactTranslator translator in Container.ResolveAll<IFactTranslator>())  
        {  
            translator.TranslateFact(convertedFacts, resolverDictionary);  
        }  
  
        return resolverDictionary;  
    }  
    catch (System.Exception ex)  
    {  
        EventLogger.Write(MethodInfo.GetCurrentMethod(), ex);  
        throw;  
    }  
}  
```  
  
 **配置自定义 Unity 冲突解决程序**  
  
 若要配置自定义 Unity 冲突解决程序，相同的配置步骤将作为应用创建自定义冲突解决程序; 时但是，没有必须包含正确注册组件组成冲突解决程序的一些其他配置。  
  
 首先，在 Esb.config 文件，冲突解决程序声明下**resolverConfig**节点必须添加具有以下两个属性：  
  
- **unitySectionName**。 此属性包含配置文件包含配置的 Unity 应用程序块; 中的配置节的名称默认情况下，此属性的值是**esb.resolver**。  
  
- **unityContainerName**。 此属性包含特定于您的自定义解析程序在 Unity 配置中定义的 Unity 容器的名称。  
  
  以下 XML 是需要在配置的一个示例**冲突解决程序**节点。  
  
```xml  
<resolver name="ITINERARY-STATIC" type="Microsoft.Practices.ESB.Resolver.Unity.ResolveProvider, Microsoft.Practices.ESB.Resolver.Unity, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
     <resolverConfig>  
          <add name="unitySectionName" value="esb.resolver" />  
          <add name="unityContainerName" value="ITINERARY" />  
     </resolverConfig>  
</resolver>  
```  
  
 以下 XML 是下，需要配置的一个示例**esb.resolver**节点。  
  
```xml  
<typeAliases>  
     <!-- Lifetime manager types -->  
     <typeAlias alias="singleton" type="Microsoft.Practices.Unity.ContainerControlledLifetimeManager, Microsoft.Practices.Unity, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     <!-- std type providers -->  
     <typeAlias alias="string" type="System.String, mscorlib"/>  
     <typeAlias alias="int" type="System.Int32, mscorlib"/>  
     <!-- repository providers -->  
     <typeAlias alias="IRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.Repository.IRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="SqlRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess.SqlRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <!-- fact providers -->  
     <typeAlias alias="IFactProvider" type="Microsoft.Practices.ESB.Resolver.Facts.IFactProvider, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="IFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.IFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryStaticFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryStaticFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryHeaderFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryHeaderFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ResolutionFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ResolutionFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="DefaultFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.DefaultFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactTranslator" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactTranslator, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <!-- resolve providers -->  
     <typeAlias alias="IResolveProvider" type="Microsoft.Practices.ESB.Resolver.IResolveProvider, Microsoft.Practices.ESB.Resolver, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryResolveProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.BREItineraryResolverContainer,Microsoft.Practices.ESB.Resolver.Itinerary, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22 "/>  
     <typeAlias alias="StaticItineraryResolveProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.StaticItineraryResolveContainer,Microsoft.Practices.ESB.Resolver.Itinerary, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22 "/>  
</typeAliases>  
<containers>  
     <container name="ITINERARY">  
          <types>  
               <type type="IResolveProvider" mapTo="StaticItineraryResolveProvider" />  
               <type type="IRepositoryProvider" mapTo="SqlRepositoryProvider" name="CurrentRepositoryProvider">  
                    <lifetime type="singleton" />  
                    <typeConfig extensionType="Microsoft.Practices.Unity.Configuration.TypeInjectionElement,Microsoft.Practices.Unity.Configuration, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
                         <constructor>  
                              <param name="connectionStringName" parameterType="string">  
                                   <value value="ItineraryDb"/>  
                              </param>  
                              <param name="cacheManagerName" parameterType="string">  
                                   <value value="Itinerary Cache Manager"/>  
                              </param>  
                              <param name="cacheTimeout" parameterType="string">  
                                   <value value="120" />  
                              </param>  
                         </constructor>  
                    </typeConfig>  
               </type>  
               <type type="IFactProvider" mapTo="ResolutionFactProvider" name="ResolutionFactProvider"  />  
               <type type="IFactProvider" mapTo="ItineraryHeaderFactProvider" name="HeaderFactProvider"  />  
               <type type="IFactProvider" mapTo="ItineraryStaticFactProvider" name="StaticFactProvider"  />  
               <type type="IFactTranslator" mapTo="DefaultFactTranslator" name="DefaultFactTranslator">  
                    <lifetime type="singleton" />  
               </type>  
               <type type="IFactTranslator" mapTo="ItineraryFactTranslator" name="ItineraryFactTranslator">  
                    <lifetime type="singleton" />  
                    <typeConfig extensionType="Microsoft.Practices.Unity.Configuration.TypeInjectionElement,Microsoft.Practices.Unity.Configuration, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
                         <constructor>  
                              <param name="repositoryProvider" parameterType="IRepositoryProvider">  
                                   <dependency name="CurrentRepositoryProvider"/>  
                              </param>  
                         </constructor>  
                    </typeConfig>  
               </type>  
          </types>  
     </container>  
</containers>  
```  
  
 有关在中是必需的配置详细信息**esb.resolvers**节点，请参阅[Unity 应用程序块的源架构](http://go.microsoft.com/fwlink/?LinkId=188288)([ http://go.microsoft.com/fwlink/?LinkId=188288 ](http://go.microsoft.com/fwlink/?LinkId=188288)) 在 MSDN 上。  
  
 **创建自定义 Unity 解析程序**  
  
 **若要创建自定义 Unity 冲突解决程序**  
  
1.  （可选）使用实现的类创建程序集或程序集**IFactProvider**接口并包含**RegisterFact**提供所需的解决方法发生信息的方法。  
  
2.  （可选）使用实现的类创建程序集或程序集**IFactTranslator**接口并包含**TranslateFact**转换提供事实数据的键/值对中的方法冲突解决程序字典。  
  
3.  创建实现的类的程序集**IResolveContainer**并**IResolveProvider**接口并包含**解决**验证的方法解析程序配置从事实提供程序收集的事实数据、 执行任何特殊的处理，会将它们使用的事实转换器，转换和实例的形式返回已翻译的事实**字典**类。  
  
4.  通过将其添加到 Esb.config 配置文件使用注册冲突解决程序 **\<冲突解决程序\>** 元素，其中包含作为根名字对象 **名称** 属性和完全限定的程序集同名 **类型** 属性。  
  
5.  对于此冲突解决程序将添加到 Esb.config 文件特定于 Unity 的配置。  
  
6.  （可选）创建架构定义的根名字对象和查询参数，并将其保存在 ESB。Schemas.Resolvers 文件夹。 该名称应采用现有 ESB 命名约定;这意味着它应使用的名称后追加"_Resolution.xsd"的根名字对象。  
  
7.  （可选）从新的架构生成类，并将其保存在自定义冲突解决程序程序集。 这将公开自定义冲突解决程序中的类型化的参数。  
  
8.  在全局程序集缓存中注册的所有程序集。