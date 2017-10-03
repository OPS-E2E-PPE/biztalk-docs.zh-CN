---
title: "创建自定义解析程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2775460-8e04-40be-9557-8278336b031c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1d583389189e09a0b9e0e5157ce5466004c03a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-resolver"></a>创建自定义冲突解决程序
中的冲突解决程序和适配器提供程序框架实现[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用一个名为调度程序的管道组件和名为 ItineraryReceive 和 ItinerarySend 的管道。  
  
 调度程序管道组件具有四个属性：**验证、 已启用、 终结点，**和**映射名称**。 **终结点**属性可以包含冲突解决程序用类似于下面的值的连接字符串其中**UDDI:\\ \\** 表示要使用 （根的解决方法类型名字对象）。  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 其他受支持的名字对象包括**XPATH:\\\\、 静态：\\\\，**和**BRE:\\\\**。 每个标记类型使用一个特定的类以实现**IResolveProvider**接口。 你可以创建其他名字对象类型为你自己自定义冲突解决程序和注册它们以供使用的动态解析系统。  
  
 标记相当于冲突解决程序连接字符串。 具体的架构定义的参数，其根名字对象。 解析程序采用冲突解决程序连接字符串，验证它，并使用结果来查询并填充**字典**对象可以用于路由、 转换、 路线选择或其他目的特定于你服务。  
  
## <a name="resolver-configuration"></a>解析程序配置  
 你必须在 Esb.config 配置文件中注册所有冲突解决程序。 以下 XML 显示了配置文件内容的示例。  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
     <configSections>  
          <section name="esb" type="Microsoft.Practices.ESB.Configuration.ESBConfigurationSection, Microsoft.Practices.ESB.Configuration, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
          <!-- Other Section Definitions Here -->  
     </configSections>  
  
     <esb>  
          <resolvers cacheManager= "Resolver Providers Cache Manager"  absoluteExpiration="3600">  
               <resolver name="UDDI" type="Microsoft.Practices.ESB.Resolver.UDDI.ResolveProvider, Microsoft.Practices.ESB.Resolver.UDDI, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
                    <resolverConfig>  
                         <add name="cacheTimeoutValue" value="120" />  
                         <add name="cacheName" value="UDDI Cache Manager" />  
                    </resolverConfig>  
               </resolver>  
               <resolver name="XPATH" type="Microsoft.Practices.ESB.Resolver.XPATH.ResolveProvider, Microsoft.Practices.ESB.Resolver.XPATH, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
               <!-- Other Resolver Definitions Here -->  
          </resolvers>  
          <!-- Other ESB Configuration Settings Here -->  
     </esb>  
     <!-- Other Configuration Sections Here -->  
</configuration>  
```  
  
 **ResolverConfig**每个冲突解决程序节点下的部分允许您配置你的冲突解决程序可能需要在特定环境中运行的其他属性。 如果希望对配置的访问，请你解析程序必须公开的构造函数中类型的参数的**Microsoft.Practices.ESB.Configuration.Resolver**。 在解析程序实现中，配置属性可以然后使用访问**ReadResolverConfigByKey**方法**ResolverConfigHelper**类; 为此，传递的参数中最初传递到构造函数中，然后传入名称值问题。 如果中不指定的任何名称-值对**resolverConfig**节点，将使用默认的无参数构造函数来实例化你的冲突解决程序。  
  
 两个通用、 描述、 发现和集成 (UDDI) 3 已在配置中定义的解析程序： UDDI 3 和 UDDI 3 SOASOFTWARE。 这些冲突解决程序都使用相同的基础程序集，但它们提供的支持与不同的统一资源标识符 (URI) 格式和安全要求的不同 UDDI 3.0 – 符合注册表不同配置。 如果你需要配置 UDDI 3.0 – 符合注册表，除了那些已支持其他标记，可以使用下面的配置属性：  
  
-   **cacheTimeoutValue**  
  
-   **cacheName**  
  
-   **publisherKey**  
  
-   **useUddiAuth**  
  
-   **baseUri**  
  
-   **inquireUriSuffix**  
  
-   **securityUriSuffix**  
  
-   **securityMode**。 有关有效值，请参阅枚举[System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409))。 默认值是**TransportCredentialOnly**。  
  
-   **credentialType**。 有关有效值，请参阅枚举[System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285))。 默认值是**Windows**。  
  
-   **用户名**  
  
-   **密码**  
  
 如果你想要创建依赖于 Unity 应用程序块的依赖关系注入功能对解析程序，不需要附加配置。 有关详细信息，请参阅[使用 Unity 容器创建一个自定义冲突解决程序](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)。  
  
## <a name="the-iresolveprovider-interface"></a>IResolveProvider 接口  
 所有的解析程序必须实现**IResolveProvider**接口。 **IResolveProvider**接口，在 Microsoft.Practices.ESB.Resolver 项目中，位于包含的三个重载**解决**返回的实例的方法**字典**类，该类包含具体的解析程序类的实例提供的解析事实。 下面的代码示例演示了这些方法重载的签名。  
  
```csharp  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from a Microsoft BizTalk   
// Server pipeline component.  
// </summary>  
// <param name="config">Configuration string entered into   
// pipeline component as argument</param>  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">IBaseMessage passed from pipeline</param>.  
// <param name="pipelineContext">IPipelineContext passed from   
// pipeline</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(string config, string resolver,  
              IBaseMessage message, IPipelineContext pipelineContext);  
  
// <summary>  
// This is the main interface that is called from the ResolverMgr   
// class.  
// This interface supports being called from a Web service interface.  
// </summary>  
// <param name="config">Configuration string entered into Web   
// service as argument</param>.  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">XML document passed from Web   
// service</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string,string> Resolve(string config, string resolver, System.Xml.XmlDocument message);  
  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from an orchestration.  
// </summary>  
// <param name="resolverInfo">Configuration string containing   
// configuration and resolver</param>.  
// <param name="message">XLANGMessage passed from   
// orchestration</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(ResolverInfo resolverInfo, XLANGs.BaseTypes.XLANGMessage message);  
```  
  
 **解析**结构，位于 Microsoft.Practices.ESB.Resolver 项目，还定义中存储的名称/值对**字典**实例。 **解析**结构揭示了几个属性; 下表列出了这些相关。 **CreateResolverDictionary**方法**ResolutionHelper**类可以用于生成一个冲突解决程序字典，其中包含的最常用的键，使用空字符串值。 **字典**实例支持的自定义冲突解决程序名称/值对的具体实现通过添加**冲突解决程序**类。  
  
|属性|数据类型|数据类型|数据类型|  
|--------------|---------------|---------------|---------------|  
|**TransformType**|字符串|**ActionField**|字符串|  
|**成功**|Boolean|**EpmRRCorrelationTokenField**|字符串|  
|**TransportNamespace**|字符串|**InboundTransportLocationField**|字符串|  
|**TransportType**|字符串|**InterchangeIDField**|字符串|  
|**TransportLocation**|字符串|**ReceiveLocationNameField**|字符串|  
|**操作**|字符串|**ReceivePortNameField**|字符串|  
|**MessageExchangePattern**|字符串|**InboundTransportTypeField**|字符串|  
|**EndpointConfig**|字符串|**IsRequestResponseField**|字符串|  
|**TargetNamespace**|字符串|**DocumentSpecStrongNameField**|字符串|  
|**FixJaxRPC**|Boolean|**DocumentSpecNameField**|字符串|  
|**WindowUserField**|字符串|**MessageType**|字符串|  
|**CacheTimeout**|字符串|**OutboundTransportCLSID**|字符串|  
|**MethodNameField**|字符串|||  
  
## <a name="creating-a-custom-resolver"></a>创建自定义冲突解决程序  
 在运行时，管道检索冲突解决程序连接字符串，并将调用冲突解决程序管理器 (实例**ResolverMgr**类)。 冲突解决程序管理器分析、 填充，并验证冲突解决程序连接字符串。 这是通过执行以下操作：  
  
-   分析连接字符串以确定哪些**冲突解决程序**要加载类型。  
  
-   它可匹配此类型设置为 （键是根标记时，如 UDDI） 配置文件中定义的名字对象。  
  
-   读取此标记的程序集名称的解析程序。  
  
-   它加载指定的程序集。  
  
 动态解决机制缓存的所有已加载的实现**IResolveProvider**接口以避免重复的读取的配置信息和程序集加载时多个传入消息使用相同冲突解决程序。  
  
 最后，冲突解决程序管理器执行**解决**方法的具体**IResolveProvider**实现，并返回已填充**字典**实例。  
  
 **若要创建自定义冲突解决程序**  
  
1.  与实现的类创建一个程序集**IResolveProvider**接口并包含**解决**实例的形式返回冲突解决程序事实的方法**字典**类。  
  
2.  通过将它添加到 Esb.config 配置文件使用注册冲突解决程序**\<冲突解决程序 >**包含根名字对象作为元素**名称**属性和完全限定程序集名称作为**类型**属性。  
  
3.  （可选）创建架构，用于定义根名字对象和查询参数，然后将其保存在 ESB。Schemas.Resolvers 文件夹。 该名称应遵循现有 ESB 命名约定;这意味着它应使用的名称后追加"_Resolution.xsd"的根名字对象。  
  
4.  （可选）从新的架构生成的类并将它保存在自定义解析程序程序集。 这会公开自定义冲突解决程序中的类型化的参数。  
  
5.  在全局程序集缓存中注册新的程序集。