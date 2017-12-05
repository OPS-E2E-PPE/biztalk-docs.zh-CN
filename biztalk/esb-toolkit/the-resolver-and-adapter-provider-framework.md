---
title: "冲突解决程序和适配器提供程序框架 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b97eec38f868a6d1aa00684d92166bb2759a51d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="the-resolver-and-adapter-provider-framework"></a>冲突解决程序和适配器提供程序框架
冲突解决程序和适配器提供程序框架支持路线、 转换和终结点解析和路由。 框架可以动态解析终结点，并设置出站适配器属性。 后一个冲突解决程序组件解析终结点 （例如，使用通用、 描述、 发现和集成 [UDDI] 看起来出站 Web 服务终结点），适配器提供程序组件设置的已注册 BizTalk Server 特定属性适配器。 例如，WCF BasicHttp 适配器提供程序负责设置 BizTalk 特定消息终结点将使用特定的 BizTalk adapter; 的 URI 的上下文属性FTP 适配器提供程序负责属性特定于设置 FTP 适配器。  
  
 冲突解决程序和适配器提供程序框架的目标之一是支持解析和路由在任一消息级别，而无需使用 BizTalk 业务流程或业务流程级别。 在这两种情况下，可插入 framework 会提供更轻松的开发、 部署和新解析程序和适配器提供程序的注册。 所有冲突解决程序和适配器提供程序实现定义完善的接口，且需加载在运行时通过在配置文件中的注册。  
  
 ESB 调度程序和 ESB 调度程序反汇编管道组件使用的解析程序和适配器提供程序框架从路线 SOAP 标头或管道配置到的冲突解决程序管理器传递连接字符串。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]配置包含所有已注册的解析程序和适配器提供程序的详细信息。 在运行的时，冲突解决程序管理器和适配器管理器从配置文件中读取的已注册的解析程序和适配器提供程序的详细信息，加载相应的程序集，并将它们存储在 BizTalk 主机级缓存。 此缓存的方法中删除重复的配置文件的读取和加载的程序集的每个已提交的邮件的要求。  
  
 有关详细信息冲突解决程序和适配器提供程序框架的工作原理以及如何通过创建自定义解析程序和适配器提供程序，扩展它的请参阅有关[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。  
  
## <a name="supported-resolution-mechanisms-resolvers"></a>支持的解析机制 （解析程序）  
 BizTalk ESB 工具包包括以下冲突解决程序：**静态、 UDDI、 UDDI3、 XPATH、 BRE、 BRI、 路线，路线静态**和**LDAP**。  
  
 冲突解决程序的连接字符串始终组成**标记**(如**BRE**) 后跟":\\\\"和连接或处理的详细信息。 标记与配置文件中关联的冲突解决程序的定义相匹配。 与每个连接字符串关联的属性是唯一的而不是所有属性都是必需。 ESB 中找不到解析程序的每个架构。Resolvers.Schemas 项目。  
  
 连接字符串的示例如下：  
  
-   **静态**  
  
     静态：\\\TransportType=;  
  
     TransportLocation = http://localhost/ESB.CanadianServices/SubmitPOService.asmx;  
  
     操作 =;  
  
     EndPointConfig =;  
  
     JaxRpcResponse = false;  
  
     MessageExchangePattern =;  
  
     TargetNamespace = http://globalbank.esb.dynamicresolution.com/canadianservices/;  
  
     TransformType =;  
  
-   **UDDI**  
  
     UDDI:\\\serverUrl= http://localhost: 9901/rmengine;  
  
     serviceName = OrderPurchaseWebService;  
  
     服务提供商处 = Microsoft 做法 ESB  
  
-   **XPATH**  
  
     \\\TransportType=;  
  
     TransportLocation=/*[本地名称()=OrderDoc 和 namespace-uri()=http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[本地名称()='ID'和namespace-uri()=http://globalbank.esb.dynamicresolution.com/northamericanservices/];  
  
     操作 =;  
  
     EndPointConfig =;  
  
     JaxRpcResponse =;  
  
     MessageExchangePattern =;  
  
     TargetNamespace=/*[本地名称()=OrderDoc和namespace-uri()=http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[本地名称()=customerName和命名空间uri()=http://globalbank.esb.dynamicresolution.com/northamericanservices/];  
  
     TransformType =;  
  
-   **BRE**  
  
     BRE:\\\policy=GetCanadaEndPoint;  
  
     版本 =;  
  
     useMsg =;  
  
-   **BRI**  
  
     BRI:\\\policy=ResolveItinerary;  
  
     版本 =;  
  
     useMsg =;  
  
-   **路线**  
  
     路线：\\\name=TwoWayTestItinerary;  
  
     版本 =;  
  
-   **路线静态**  
  
     路线静态：\\\name=TwoWayTestItinerary;  
  
     版本 =;  
  
-   **LDAP**  
  
     LDAP:\\\TransportType=SMTP;  
  
     TransportLocation = {邮件}  
  
     筛选器 = (&amp;(objectClass = User) (&#124; (userPrincipalName =yourname@domain.com)));  
  
     SearchRoot =;  
  
     SearchScope = 子树;  
  
     EndpointConfig = Subject = 路线测试消息到 {邮件}&amp;  
  
     SMTPAuthenticate = 0&amp;  
  
     SMTPHost = 127.0.0.1&amp;  
  
     从 =test@globalbank.com&amp;  
  
     DeliveryReceipt = false&amp;  
  
     MessagePartsAttachments = 0&amp;  
  
     ReadReceipt = false;  
  
     ThrowErrorIfNotFound = false;  
  
     操作 =;  
  
     JaxRpcResponse = false;  
  
     MessageExchangePattern =;  
  
     TargetNamespace =;  
  
     TransformType =;  
  
 并非所有连接字符串中的属性都是必需的。 此外， **EndPointConfig**是一个特殊属性，任何冲突解决程序可以填充并返回。 （可选） 冲突解决程序可以存储特定的 BizTalk 适配器上下文属性，它可以反过来，写入 BizTalk 消息的上下文所对应的名称/值对。  
  
 在这种情况下， **ResolverDictionary**实例，其中包含所有已解决的属性返回的解析进程然后传递到适配器管理器。 适配器管理器将传递到的特定的适配器提供程序将设置所有适配器特定和特定终结点的 BizTalk 上下文消息属性的字典。 冲突解决程序查找**EndPointConfig**属性，对应于它们各自的适配器的属性的名称/值对中提取，然后在消息上设置这些值。  
  
## <a name="supported-adapter-providers"></a>受支持的适配器提供程序  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下内置适配器提供程序：**文件、 FTP、 SMTP、 MQSeries、 WCF BasicHttp、 WCF WSHttp，**和**WCF 自定义**。 每个适配器提供程序的名称等同于 BizTalk Server 中关联的适配器 （传输类型） 的名称。  
  
 冲突解决程序和适配器提供程序框架的主要优点是，你可以通过创建并注册你自己的自定义解析程序来解析终结点信息和自定义适配器提供商能够设置的已注册 BizTalk 适配器的特定属性来扩展它。 有关详细信息，请参阅[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。