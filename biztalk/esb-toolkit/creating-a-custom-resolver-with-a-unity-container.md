---
title: "使用 Unity 容器中创建自定义解析程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6f95f5e-64dd-4cc6-802f-0c5fd6a01c91
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15952ef3cc8f19eaa5de1a4155d0dc7f6e03c5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-resolver-with-a-unity-container"></a><span data-ttu-id="793f9-102">使用 Unity 容器中创建自定义冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="793f9-102">Creating a Custom Resolver with a Unity Container</span></span>
<span data-ttu-id="793f9-103">你可以创建使用自定义解析程序[Unity 应用程序块](http://go.microsoft.com/fwlink/?LinkId=188286)(Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) 的解析逻辑和元数据源的运行时依赖关系注入。</span><span class="sxs-lookup"><span data-stu-id="793f9-103">You can create a custom resolver using the [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) for run-time dependency injection of resolution logic and metadata sources.</span></span>
  
 <span data-ttu-id="793f9-104">**事实提供程序**</span><span class="sxs-lookup"><span data-stu-id="793f9-104">**Fact Providers**</span></span>  
  
 <span data-ttu-id="793f9-105">事实提供程序是实现的类的实例**IFactProvider**接口。</span><span class="sxs-lookup"><span data-stu-id="793f9-105">Fact providers are instances of classes that implement the **IFactProvider** interface.</span></span> <span data-ttu-id="793f9-106">此接口公开一个名为方法的三个不同的重载**RegisterFact**。</span><span class="sxs-lookup"><span data-stu-id="793f9-106">This interface exposes three different overloads of a method named **RegisterFact**.</span></span> <span data-ttu-id="793f9-107">此方法采用在消息中，解析程序配置，以及在某些情况下，管道上下文中，并返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="793f9-107">This method takes in the message, the resolver configuration, and, in some cases, the pipeline context, and returns an object.</span></span> <span data-ttu-id="793f9-108">此对象可能从以某种方式输入中提取信息，它可能是某种形式的一项计算或者它可能查找从某些外部源。</span><span class="sxs-lookup"><span data-stu-id="793f9-108">This object may be information extracted from the inputs in some way, it may be a calculation of some form, or it may be looked up from some external source.</span></span> <span data-ttu-id="793f9-109">事实提供程序返回的每个对象可以与的事实数据引用和更高版本使用事实转换器解析容器通常添加到列表。</span><span class="sxs-lookup"><span data-stu-id="793f9-109">Each object returned by a fact provider can be referred to as a fact and is typically added to a list by the resolve container for later use by a fact translator.</span></span>  
  
 <span data-ttu-id="793f9-110">Unity 冲突解决程序可能有零个或多个事实提供程序可以添加或删除随时与单个配置更改。</span><span class="sxs-lookup"><span data-stu-id="793f9-110">A Unity resolver may have zero or more fact providers that can be added or removed at any time with a single configuration change.</span></span>  
  
 <span data-ttu-id="793f9-111">下面的代码演示了包含事实提供程序中的逻辑。</span><span class="sxs-lookup"><span data-stu-id="793f9-111">The following code is an example of the logic contained in a fact provider.</span></span> <span data-ttu-id="793f9-112">此代码还可以在 ESB ItineraryStaticFactProvider.cs 文件中找到。Resolver.Itinerary.Facts 项目。</span><span class="sxs-lookup"><span data-stu-id="793f9-112">This code can also be found in the ItineraryStaticFactProvider.cs file of the ESB.Resolver.Itinerary.Facts project.</span></span> <span data-ttu-id="793f9-113">它是在从解析程序连接字符串中收集的名称和版本的一条路线路线静态冲突解决程序组件。</span><span class="sxs-lookup"><span data-stu-id="793f9-113">It is a component in the ITINERARY-STATIC resolver that gathers the name and version of an itinerary from the resolver connection string.</span></span>  
  
```csharp  
public object RegisterFact(IBaseMessage message, IPipelineContext pipelineContext, Dictionary\<string, string> resolverContents)  
{  
    return GetItineraryFactFromResolver(resolverContents);  
}  
  
private static object GetItineraryFactFromResolver(Dictionary\<string, string> resolverContents)  
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
  
 <span data-ttu-id="793f9-114">**事实转换器**</span><span class="sxs-lookup"><span data-stu-id="793f9-114">**Fact Translators**</span></span>  
  
 <span data-ttu-id="793f9-115">事实转换器是实现的类的实例**IFactTranslator**接口。</span><span class="sxs-lookup"><span data-stu-id="793f9-115">Fact translators are instances of classes that implement the **IFactTranslator** interface.</span></span> <span data-ttu-id="793f9-116">此接口公开一个名为的单个方法**TranslateFact**。</span><span class="sxs-lookup"><span data-stu-id="793f9-116">This interface exposes a single method named **TranslateFact**.</span></span> <span data-ttu-id="793f9-117">此方法采用一个对象数组，包含事实和更高版本将返回由解析程序使用事实转换器的冲突解决程序字典的列表中。</span><span class="sxs-lookup"><span data-stu-id="793f9-117">This method takes in an object array that contains a list of facts and the resolver dictionary that will later be returned by the resolver using the fact translator.</span></span> <span data-ttu-id="793f9-118">事实转换器负责处理事实提供程序中有意义的方式提供的事实数据，然后填充冲突解决程序字典。</span><span class="sxs-lookup"><span data-stu-id="793f9-118">A fact translator is responsible for processing the facts provided by the fact providers in a meaningful way and then populating the resolver dictionary.</span></span>  
  
 <span data-ttu-id="793f9-119">Unity 冲突解决程序可能有零个或多个事实转换器可以添加或删除随时与单个配置更改。</span><span class="sxs-lookup"><span data-stu-id="793f9-119">A Unity resolver may have zero or more fact translators that can be added or removed at any time with a single configuration change.</span></span>  
  
 <span data-ttu-id="793f9-120">下面的代码演示了一个事实转换器中包含的逻辑。</span><span class="sxs-lookup"><span data-stu-id="793f9-120">The following code is an example of the logic contained in a fact translator.</span></span> <span data-ttu-id="793f9-121">此代码还可以在 ESB ItineraryStaticFactTranslator.cs 文件中找到。Resolver.Itinerary.Facts 项目。</span><span class="sxs-lookup"><span data-stu-id="793f9-121">This code can also be found in the ItineraryStaticFactTranslator.cs file of the ESB.Resolver.Itinerary.Facts project.</span></span> <span data-ttu-id="793f9-122">它是在执行数据库查询，就可以按名称和 （可选） 版本收集的一条路线路线 XML 路线静态冲突解决程序组件。</span><span class="sxs-lookup"><span data-stu-id="793f9-122">It is a component in the ITINERARY-STATIC resolver that performs a database query to gather the itinerary XML for an itinerary by name and, optionally, by version.</span></span>  
  
```csharp  
public void TranslateFact(object[] facts, Dictionary\<string, string> factDictionary)  
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
  
 <span data-ttu-id="793f9-123">**解决容器**</span><span class="sxs-lookup"><span data-stu-id="793f9-123">**Resolve Containers**</span></span>  
  
 <span data-ttu-id="793f9-124">解析容器是一个类以实现**IResolveContainer**接口。</span><span class="sxs-lookup"><span data-stu-id="793f9-124">A resolve container is a class that implements the **IResolveContainer** interface.</span></span> <span data-ttu-id="793f9-125">通常情况下，它还实现**IResolveProvider**接口。</span><span class="sxs-lookup"><span data-stu-id="793f9-125">Typically, it also implements the **IResolveProvider** interface.</span></span> <span data-ttu-id="793f9-126">**IResolveContainer**接口公开一个名为的单个方法**初始化**采用**IUnityContainer**。</span><span class="sxs-lookup"><span data-stu-id="793f9-126">The **IResolveContainer** interface exposes a single method named **Initialize** that takes in an **IUnityContainer**.</span></span> <span data-ttu-id="793f9-127">传递给此方法的容器将包含所有依赖项 (即，这些类的实例**IFactProvider**和**IFactTranslator**，和所需的任何其他类型) 的必要条件若要完成其处理的解析程序。</span><span class="sxs-lookup"><span data-stu-id="793f9-127">The container passed to this method will contain all of the dependencies (that is, instances of the classes **IFactProvider** and **IFactTranslator**, and any other types required) necessary for the resolver to complete its processing.</span></span>  
  
 <span data-ttu-id="793f9-128">下面的代码是实现的一个示例**IResolveContainer**接口。</span><span class="sxs-lookup"><span data-stu-id="793f9-128">The following code is an example of an implementation of the **IResolveContainer** interface.</span></span> <span data-ttu-id="793f9-129">此代码还可以在 ESB StaticItineraryResolveContainer.cs 文件中找到。Resolver.Itinerary 项目。</span><span class="sxs-lookup"><span data-stu-id="793f9-129">This code can also be found in the StaticItineraryResolveContainer.cs file of the ESB.Resolver.Itinerary project.</span></span>  
  
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
  
 <span data-ttu-id="793f9-130">中的实现中的解决容器**解决**方法从**IResolveProvider**接口，它是需循环访问所有事实供应商和 Unity 中的事实翻译要允许其中执行它们的处理每个容器。</span><span class="sxs-lookup"><span data-stu-id="793f9-130">In a resolve container, in the implementations of the **Resolve** methods from the **IResolveProvider** interface, it is necessary to iterate through all the fact providers and fact translators in the Unity container to allow each of them to perform their processing.</span></span>  
  
 <span data-ttu-id="793f9-131">下面的代码演示了解决容器中包含的逻辑。</span><span class="sxs-lookup"><span data-stu-id="793f9-131">The following code is an example of the logic contained in a Resolve container.</span></span> <span data-ttu-id="793f9-132">此代码还可以在 ESB StaticItineraryResolveContainer.cs 文件中找到。Resolver.Itinerary 项目。</span><span class="sxs-lookup"><span data-stu-id="793f9-132">This code can also be found in the StaticItineraryResolveContainer.cs file of the ESB.Resolver.Itinerary project.</span></span>  
  
```csharp  
public Dictionary\<string, string> Resolve(ResolverInfo resolverInfo,  
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
  
private Dictionary\<string, string> ResolveStatic(string config, string resolver,   
    Func<IFactProvider, Dictionary\<string, string>, object> RegisterFact)  
{  
    try  
    {  
        EventLogger.Write(string.Format("Received {0} value in ITINERARY STATIC resolver.", config));  
  
        Dictionary\<string, string> queryParams =  
                ResolverMgr.GetFacts(config, resolver);  
  
        List<object> facts = new List<object>();  
  
        foreach (IFactProvider factProvider in Container.ResolveAll<IFactProvider>())  
        {  
            facts.Add(RegisterFact(factProvider, queryParams));  
        }  
  
        Dictionary\<string, string> resolverDictionary = new Dictionary\<string, string>();  
  
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
  
 <span data-ttu-id="793f9-133">**配置自定义 Unity 冲突解决程序**</span><span class="sxs-lookup"><span data-stu-id="793f9-133">**Configuring a Custom Unity Resolver**</span></span>  
  
 <span data-ttu-id="793f9-134">若要配置自定义 Unity 解析程序，相同的配置步骤将应用于时创建自定义解析程序;但是，没有其他一些必须包含在内，以正确注册构成冲突解决程序组件的配置。</span><span class="sxs-lookup"><span data-stu-id="793f9-134">To configure a custom Unity resolver, the same configuration steps apply as when creating a custom resolver; however, there is some additional configuration that must be included to properly register the components that make up the resolver.</span></span>  
  
 <span data-ttu-id="793f9-135">首先，在 Esb.config 文件中，冲突解决程序声明下**resolverConfig**节点必须添加具有以下两个属性：</span><span class="sxs-lookup"><span data-stu-id="793f9-135">First, in the Esb.config file, under the resolver declaration, a **resolverConfig** node must be added with the following two properties:</span></span>  
  
-   <span data-ttu-id="793f9-136">**unitySectionName**。</span><span class="sxs-lookup"><span data-stu-id="793f9-136">**unitySectionName**.</span></span> <span data-ttu-id="793f9-137">此属性包含配置文件包含配置的 Unity 应用程序块; 中的配置节的名称默认情况下，此属性的值是**esb.resolver**。</span><span class="sxs-lookup"><span data-stu-id="793f9-137">This property contains the name of the configuration section in the configuration file that contains the configuration for the Unity Application Block; by default, the value for this property is **esb.resolver**.</span></span>  
  
-   <span data-ttu-id="793f9-138">**unityContainerName**。</span><span class="sxs-lookup"><span data-stu-id="793f9-138">**unityContainerName**.</span></span> <span data-ttu-id="793f9-139">此属性包含在 Unity 配置特定于你的自定义冲突解决程序中定义的 Unity 容器的名称。</span><span class="sxs-lookup"><span data-stu-id="793f9-139">This property contains the name of the Unity container defined in the Unity configuration specific to your custom resolver.</span></span>  
  
 <span data-ttu-id="793f9-140">以下 XML 是必要的配置示例**冲突解决程序**节点。</span><span class="sxs-lookup"><span data-stu-id="793f9-140">The following XML is an example of the configuration necessary in the **resolvers** node.</span></span>  
  
```xml  
<resolver name="ITINERARY-STATIC" type="Microsoft.Practices.ESB.Resolver.Unity.ResolveProvider, Microsoft.Practices.ESB.Resolver.Unity, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
     <resolverConfig>  
          <add name="unitySectionName" value="esb.resolver" />  
          <add name="unityContainerName" value="ITINERARY" />  
     </resolverConfig>  
</resolver>  
```  
  
 <span data-ttu-id="793f9-141">以下 XML 是有必要在下配置的一个示例**esb.resolver**节点。</span><span class="sxs-lookup"><span data-stu-id="793f9-141">The following XML is an example of the configuration necessary under the **esb.resolver** node.</span></span>  
  
```xml  
<typeAliases>  
     \<!-- Lifetime manager types -->  
     <typeAlias alias="singleton" type="Microsoft.Practices.Unity.ContainerControlledLifetimeManager, Microsoft.Practices.Unity, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     \<!-- std type providers -->  
     <typeAlias alias="string" type="System.String, mscorlib"/>  
     <typeAlias alias="int" type="System.Int32, mscorlib"/>  
     \<!-- repository providers -->  
     <typeAlias alias="IRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.Repository.IRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="SqlRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess.SqlRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     \<!-- fact providers -->  
     <typeAlias alias="IFactProvider" type="Microsoft.Practices.ESB.Resolver.Facts.IFactProvider, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="IFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.IFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryStaticFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryStaticFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryHeaderFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryHeaderFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ResolutionFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ResolutionFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="DefaultFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.DefaultFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactTranslator" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactTranslator, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     \<!-- resolve providers -->  
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
  
 <span data-ttu-id="793f9-142">有关在中是必需的配置详细信息**esb.resolvers**节点，请参阅[Unity 应用程序块的源架构](http://go.microsoft.com/fwlink/?LinkId=188288)([http://go.microsoft.com/fwlink/?LinkId = 188288](http://go.microsoft.com/fwlink/?LinkId=188288)) MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="793f9-142">For detailed information about the configuration that is necessary in the **esb.resolvers** node, see [Source Schema for the Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188288) ([http://go.microsoft.com/fwlink/?LinkId=188288](http://go.microsoft.com/fwlink/?LinkId=188288)) on MSDN.</span></span>  
  
 <span data-ttu-id="793f9-143">**创建自定义 Unity 解析程序**</span><span class="sxs-lookup"><span data-stu-id="793f9-143">**Creating a Custom Unity Resolver**</span></span>  
  
 <span data-ttu-id="793f9-144">**若要创建自定义 Unity 解析程序**</span><span class="sxs-lookup"><span data-stu-id="793f9-144">**To create a custom Unity resolver**</span></span>  
  
1.  <span data-ttu-id="793f9-145">（可选）使用实现的类创建程序集或程序集**IFactProvider**接口并包含**RegisterFact**方法，提供所需的可发生的解决方法信息。</span><span class="sxs-lookup"><span data-stu-id="793f9-145">(Optional) Create an assembly or assemblies with a class that implements the **IFactProvider** interface and contains a **RegisterFact** method that provides information necessary for resolution to occur.</span></span>  
  
2.  <span data-ttu-id="793f9-146">（可选）使用实现的类创建程序集或程序集**IFactTranslator**接口并包含**TranslateFact**转换以键/值对中的提供事实数据的方法冲突解决程序字典。</span><span class="sxs-lookup"><span data-stu-id="793f9-146">(Optional) Create an assembly or assemblies with a class that implements the **IFactTranslator** interface and contains a **TranslateFact** method that translates the provided facts to key/value pairs within the resolver dictionary.</span></span>  
  
3.  <span data-ttu-id="793f9-147">与实现的类创建一个程序集**IResolveContainer**和**IResolveProvider**接口并包含**解决**验证的方法解析程序配置，从事实提供程序收集的所有事实数据、 执行任何特殊的处理，会将它们使用的事实转换器，转换和实例的形式返回的已翻译的事实数据**字典**类。</span><span class="sxs-lookup"><span data-stu-id="793f9-147">Create an assembly with a class that implements the **IResolveContainer** and **IResolveProvider** interface and that contains a **Resolve** method that validates the resolver configuration, gathers all the facts from the fact providers, performs any specialized processing, translates them using the fact translators, and returns the translated facts as an instance of the **Dictionary** class.</span></span>  
  
4.  <span data-ttu-id="793f9-148">通过将它添加到 Esb.config 配置文件使用注册冲突解决程序**\<冲突解决程序 >**包含根名字对象作为元素**名称**属性和完全限定程序集名称作为**类型**属性。</span><span class="sxs-lookup"><span data-stu-id="793f9-148">Register the resolver by adding it to the Esb.config configuration file using a **\<resolver>** element that contains the root moniker as the **name** attribute and the fully qualified assembly name as the **type** attribute.</span></span>  
  
5.  <span data-ttu-id="793f9-149">此解析程序将添加到 Esb.config 文件特定于 Unity 的配置。</span><span class="sxs-lookup"><span data-stu-id="793f9-149">Add the Unity-specific configuration to the Esb.config file for this resolver.</span></span>  
  
6.  <span data-ttu-id="793f9-150">（可选）创建架构，用于定义根名字对象和查询参数，然后将其保存在 ESB。Schemas.Resolvers 文件夹。</span><span class="sxs-lookup"><span data-stu-id="793f9-150">(Optional) Create a schema that defines the root moniker and the query parameters, and then save it in the ESB.Schemas.Resolvers folder.</span></span> <span data-ttu-id="793f9-151">该名称应遵循现有 ESB 命名约定;这意味着它应使用的名称后追加"_Resolution.xsd"的根名字对象。</span><span class="sxs-lookup"><span data-stu-id="793f9-151">The name should follow existing ESB naming conventions; this means it should use the name of the root moniker appended with "_Resolution.xsd".</span></span>  
  
7.  <span data-ttu-id="793f9-152">（可选）从新的架构生成的类并将它保存在自定义解析程序程序集。</span><span class="sxs-lookup"><span data-stu-id="793f9-152">(Optional) Generate a class from the new schema and save it in the custom resolver assembly.</span></span> <span data-ttu-id="793f9-153">这将公开自定义冲突解决程序中的类型化的参数。</span><span class="sxs-lookup"><span data-stu-id="793f9-153">This will expose typed parameters in the custom resolver.</span></span>  
  
8.  <span data-ttu-id="793f9-154">在全局程序集缓存中注册所有程序集。</span><span class="sxs-lookup"><span data-stu-id="793f9-154">Register all the assemblies in the global assembly cache.</span></span>