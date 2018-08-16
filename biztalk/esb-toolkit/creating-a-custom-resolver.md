---
title: 创建自定义冲突解决程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2775460-8e04-40be-9557-8278336b031c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3752348a5cc9273ad203b78b77b58bde33bd141
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981710"
---
# <a name="creating-a-custom-resolver"></a>创建自定义冲突解决程序
中的冲突解决程序和适配器提供程序框架实现[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用名为调度程序的管道组件和名为 ItineraryReceive 和 ItinerarySend 的管道。  
  
 调度程序管道组件有四个属性：**验证、 已启用、 终结点，** 并**MapName**。 **终结点**属性可以包含冲突解决程序连接字符串值如下所示，其中**UDDI:\\ \\** 表示要使用 （根的解析类型名字对象）。  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 其他受支持的名字对象包括**XPATH:\\\\静态：\\\\，** 并**BRE:\\\\**。 每个名字对象类型使用特定的类实现**IResolveProvider**接口。 您可以创建自己为其他名字对象类型的自定义解析程序并注册它们以供使用的动态解析系统。  
  
 名字对象等同于冲突解决程序连接字符串。 单个架构定义的参数和其根名字对象。 冲突解决程序需要冲突解决程序连接字符串中，验证它，并使用的结果来查询和填充**字典**对象，它可用于路由、 转换、 路线选择或特定于某些其他目的在服务。  
  
## <a name="resolver-configuration"></a>解析程序配置  
 必须在 Esb.config 配置文件中注册所有冲突解决程序。 以下 XML 显示了配置文件内容的示例。  
  
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
  
 **ResolverConfig**部分中的每个冲突解决程序节点下，可配置您的解析程序可能需要的特定环境中运行的其他属性。 若要访问的配置，您的解析程序必须公开采用的类型参数的构造函数**Microsoft.Practices.ESB.Configuration.Resolver**。 在解析程序实现中，配置属性可以访问使用**ReadResolverConfigByKey**方法**ResolverConfigHelper**类; 若要执行此操作，将传递的参数中最初传递给构造函数中，然后传入名称值有问题。 如果没有名称-值对中指定**resolverConfig**节点，将使用默认的无参数构造函数来实例化您的解析程序。  
  
 两个通用描述、 发现和集成 (UDDI) 3 已在配置中定义冲突解决程序： UDDI 3 和 UDDI 3 SOASOFTWARE。 这些冲突解决程序都使用相同的基础程序集，但它们提供不同的配置，以支持不同的 UDDI 3.0 兼容注册表使用不同的统一资源标识符 (URI) 格式和安全要求。 如果你需要配置 UDDI 3.0 兼容的注册表，除了那些已支持为其他名字对象，可以使用以下配置属性：  
  
- **cacheTimeoutValue**  
  
- **cacheName**  
  
- **publisherKey**  
  
- **useUddiAuth**  
  
- **baseUri**  
  
- **inquireUriSuffix**  
  
- **securityUriSuffix**  
  
- **securityMode**。 有效的值，请参阅枚举[System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409))。 默认值是**TransportCredentialOnly**。  
  
- **credentialType**。 有效的值，请参阅枚举[System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285))。 默认值是**Windows**。  
  
- **username**  
  
- **password**  
  
  如果你想要创建的解析程序依赖于 Unity 应用程序块的依赖关系注入功能，则需要其他配置。 有关详细信息，请参阅[使用 Unity 容器创建自定义冲突解决程序](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)。  
  
## <a name="the-iresolveprovider-interface"></a>IResolveProvider 接口  
 所有冲突解决程序必须实现**IResolveProvider**接口。 **IResolveProvider**接口，位于 Microsoft.Practices.ESB.Resolver 项目包含的三个重载**解决**返回的实例方法**字典**类，该类包含提供的具体的解析程序类的实例解析事实。 下面的代码示例演示了这些方法重载的签名。  
  
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
  
 **解析**结构，位于 Microsoft.Practices.ESB.Resolver 项目还定义中存储的名称/值对**字典**实例。 **解析**结构揭示了多个属性; 下表列出了最相关的这些。 **CreateResolverDictionary**方法**ResolutionHelper**类可用于生成一个冲突解决程序字典，其中包含最常用的关键字，使用空字符串值。 **字典**实例支持的自定义冲突解决程序名称/值对的具体实现通过添加**冲突解决程序**类。  
  
|“属性”|数据类型|数据类型|数据类型|  
|--------------|---------------|---------------|---------------|  
|**TransformType**|String|**ActionField**|String|  
|**成功**|Boolean|**EpmRRCorrelationTokenField**|String|  
|**TransportNamespace**|String|**InboundTransportLocationField**|String|  
|**TransportType**|String|**InterchangeIDField**|String|  
|**TransportLocation**|String|**ReceiveLocationNameField**|String|  
|**操作**|String|**ReceivePortNameField**|String|  
|**MessageExchangePattern**|String|**InboundTransportTypeField**|String|  
|**EndpointConfig**|String|**IsRequestResponseField**|String|  
|**TargetNamespace**|String|**DocumentSpecStrongNameField**|String|  
|**FixJaxRPC**|Boolean|**DocumentSpecNameField**|String|  
|**WindowUserField**|String|**MessageType**|String|  
|**CacheTimeout**|String|**OutboundTransportCLSID**|String|  
|**MethodNameField**|String|||  
  
## <a name="creating-a-custom-resolver"></a>创建自定义冲突解决程序  
 在运行时，管道检索冲突解决程序连接字符串，并将调用冲突解决程序管理器 (的实例**ResolverMgr**类)。 冲突解决程序管理器将分析、 填充并验证冲突解决程序连接字符串。 这是通过执行以下操作：  
  
- 它将解析连接字符串以确定哪个**冲突解决程序**要加载类型。  
  
- 它可匹配此名字对象 （该密钥是根名字对象，如 UDDI） 配置文件中定义的类型。  
  
- 它将读取此名字对象的冲突解决程序的程序集名称。  
  
- 它将加载指定的程序集。  
  
  动态解析机制缓存的所有已加载的实现**IResolveProvider**接口以避免重复的读取配置信息和程序集加载时多个传入消息使用相同的冲突解决程序。  
  
  最后，冲突解决程序管理器执行**解决**方法的具体**IResolveProvider**实现，并返回填充**字典**实例。  
  
  **若要创建自定义冲突解决程序**  
  
1.  创建实现的类的程序集**IResolveProvider**接口并包含**解决**方法，它返回的实例作为冲突解决程序事实**字典**类。  
  
2.  通过将其添加到 Esb.config 配置文件使用注册冲突解决程序**\<冲突解决程序\>** 元素，其中包含作为根名字对象**名称**属性和完全限定的程序集同名**类型**属性。  
  
3.  （可选）创建架构定义的根名字对象和查询参数，并将其保存在 ESB。Schemas.Resolvers 文件夹。 该名称应采用现有 ESB 命名约定;这意味着它应使用的名称后追加"_Resolution.xsd"的根名字对象。  
  
4.  （可选）从新的架构生成类，并将其保存在自定义冲突解决程序程序集。 这会公开自定义冲突解决程序中的类型化的参数。  
  
5.  在全局程序集缓存中注册新的程序集。