---
title: ESB 解析程序和适配器提供程序框架 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95134a1f806398f14a5596149eb605e2de20cac2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002798"
---
# <a name="the-resolver-and-adapter-provider-framework"></a>冲突解决程序和适配器提供程序框架
冲突解决程序和适配器提供程序框架支持路线、 转换和终结点解析和路由。 框架可以动态地解析终结点，并设置出站适配器属性。 之后冲突解决程序组件解决了终结点 （例如，使用通用描述、 发现和集成 [UDDI] 若要查找出站 Web 服务终结点），适配器提供程序组件设置已注册的 BizTalk Server 的特定属性适配器。 例如，Wcf-basichttp 适配器提供程序负责设置特定于 BizTalk 消息上下文属性为终结点 URI，将使用特定的 BizTalk 适配器;FTP 适配器提供程序负责特定的属性设置为 FTP 适配器。  
  
 冲突解决程序和适配器提供程序框架的一个目标是支持解析和路由在任一消息传送级别，而无需使用 BizTalk 业务流程，或在业务流程级别。 在这两种情况下，可插入的框架提供了更轻松的开发、 部署和注册的新解析程序和适配器提供程序。 所有冲突解决程序和适配器提供程序实现定义完善的接口，并在运行时通过注册配置文件中是按需加载。  
  
 ESB 调度程序和 ESB 调度程序拆装管道组件使用的冲突解决程序和适配器提供程序框架并传递连接字符串从路线 SOAP 标头或管道配置为冲突解决程序管理器。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]配置包含所有已注册冲突解决程序和适配器提供程序的详细信息。 在运行的时、 冲突解决程序经理和适配器管理器配置文件中读取的已注册冲突解决程序和适配器提供程序的详细信息，加载相应的程序集，并将其存储在 BizTalk 主机级缓存中。 此缓存方法中删除重复的配置文件的读取和加载的程序集的每个提交的消息的要求。  
  
 有关详细信息冲突解决程序和适配器提供程序框架的工作原理和如何通过创建自定义冲突解决程序和适配器提供程序扩展它的请参阅有关[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。  
  
## <a name="supported-resolution-mechanisms-resolvers"></a>支持的分辨率机制 （冲突解决程序）  
 BizTalk ESB 工具包包括以下冲突解决程序：**静态、 UDDI、 UDDI3、 XPATH、 BRE、 BRI 的路线，路线静态**并**LDAP**。  
  
 冲突解决程序的连接字符串始终组成**名字对象**(如**BRE**) 后跟":\\\\"和连接或处理的详细信息。 名字对象与关联的冲突解决程序在配置文件定义相匹配。 与每个连接字符串关联的属性是唯一的并不是所有属性都是必需。 可在 ESB 解析程序的每个架构。Resolvers.Schemas 项目。  
  
 连接字符串的示例如下：  
  
- **静态**  
  
   STATIC:\\\TransportType=;  
  
   TransportLocation =<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>;  
  
   Action=;  
  
   EndPointConfig=;  
  
   JaxRpcResponse=false;  
  
   MessageExchangePattern=;  
  
   TargetNamespace=<http://globalbank.esb.dynamicresolution.com/canadianservices/>;  
  
   TransformType=;  
  
- **UDDI**  
  
   UDDI:\\\serverUrl=<http://localhost:9901/rmengine>;  
  
   serviceName=OrderPurchaseWebService;  
  
   serviceProvider=Microsoft Practices ESB  
  
- **XPATH**  
  
   XPATH:\\\TransportType=;  
  
   `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   Action=;  
  
   EndPointConfig=;  
  
   JaxRpcResponse=;  
  
   MessageExchangePattern=;  
  
   `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   TransformType=;  

- **BRE**  
  
   BRE:\\\policy=GetCanadaEndPoint;  
  
   version=;  
  
   useMsg=;  
  
- **BRI**  
  
   BRI:\\\policy=ResolveItinerary;  
  
   version=;  
  
   useMsg=;  
  
- **路线**  
  
   ITINERARY:\\\name=TwoWayTestItinerary;  
  
   version=;  
  
- **路线静态**  
  
   路线静态：\\\name=TwoWayTestItinerary;  
  
   version=;  
  
- **LDAP**  
  
   LDAP:\\\TransportType=SMTP;  
  
   TransportLocation={mail}  
  
   筛选器 = (&(objectClass=User) (| (userPrincipalName =yourname@domain.com)));  
  
   SearchRoot=;  
  
   SearchScope=Subtree;  
  
   EndpointConfig = Subject = {邮件} 路线测试消息 （& a) 
  
   SMTPAuthenticate = 0 （& a)
  
   SMTPHost = 127.0.0.1 （& a)
  
   从 =test@globalbank.com（& a)
  
   DeliveryReceipt = false （& a)
  
   MessagePartsAttachments = 0 （& a)
  
   ReadReceipt=false;  
  
   ThrowErrorIfNotFound=false;  
  
   Action=;  
  
   JaxRpcResponse=false;  
  
   MessageExchangePattern=;  
  
   TargetNamespace=;  
  
   TransformType=;  
  
  并非所有连接字符串中的属性都是必需的。 此外， **EndPointConfig**是一个特殊属性，可以填充并返回任何冲突解决程序。 （可选） 冲突解决程序可以存储对应于特定的 BizTalk 适配器上下文属性，又可以写入 BizTalk 消息上下文的名称/值对。  
  
  在这种情况下， **ResolverDictionary**实例，它包含所有已解决的属性返回从解决过程，然后传递到适配器管理器。 适配器管理器将传递到特定的适配器提供程序将设置所有特定于适配器的和特定于终结点的 BizTalk 上下文消息属性的字典。 冲突解决程序寻找**EndPointConfig**属性，提取到它们各自的适配器的属性相对应的名称/值对，然后在消息上设置这些值。  
  
## <a name="supported-adapter-providers"></a>支持的适配器提供程序  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下内置适配器提供程序：**文件、 FTP、 SMTP、 MQSeries、 Wcf-basichttp、 Wcf-wshttp**并**WCF 自定义**。 每个适配器提供程序的名称与 BizTalk Server 中的关联适配器 （传输类型） 的名称完全相同。  
  
 冲突解决程序和适配器提供程序框架的主要优势是，您可以通过创建和注册自己的自定义解析程序来解决终结点信息和要设置的已注册的 BizTalk 适配器的特定属性的自定义适配器提供程序来扩展它。 有关详细信息，请参阅[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。
