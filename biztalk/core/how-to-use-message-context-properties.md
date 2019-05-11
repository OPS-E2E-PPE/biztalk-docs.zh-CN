---
title: 如何使用消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, building
- building, insufficient configuration
ms.assetid: 6ca95017-74e0-42d7-befa-93e0c1e1ecd1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49787a244abd24738e589f444a0d3cb047c2dc47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383334"
---
# <a name="how-to-use-message-context-properties"></a>如何使用消息上下文属性
系统属性主要由 BizTalk 消息引擎和其组件在内部使用。 一般情况下，引擎为那些属性设置的值不是建议更改，因为它可能会影响引擎的执行逻辑。 但是，有大量的可以更改的属性。  
  
 下表列出了消息引擎可以升级的消息上下文属性。 可将这些属性用于创建发送端口和 Microsoft 中的业务流程的筛选器表达式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 例如，  
  
```  
PortName = MyMessage(BTS.ReceivePortName);  
MyFileName = MyMessage(BTS.ReceivedFileName);  
MySubject= MyMessage(POP3.Subject);  
```  
  
 一个单独的表列出了可能的不能升级某些 BizTalk 应用程序中使用的其他属性。  
  
|属性|时间和位置提升|类型|Description|  
|--------------|-----------------------------------|----------|-----------------|  
|BTS.AckFailureCategory|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:int|标识**ErrorCategory**，它可使位置和挂起的原因。|  
|BTS.AckFailureCode|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识**ErrorCode**，它可使位置和挂起的原因。|  
|BTS.AckID|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识**MessageID**的原始消息。|  
|BTS.AckInboundTransportLocation|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识**InboundTransportLocation**原始消息中。|  
|BTS.AckOutboundTransportLocation|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识**OutboundTransportLocation**原始消息中。|  
|BTS.AckOwnerID|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识原始消息中的实例 ID。|  
|BTS.AckReceivePortID|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识**ReceivePortID**原始消息中。|  
|BTS.AckReceivePortName|由消息引擎为确认消息升级。|xs:string|标识**ReceivePortName**原始消息中。|  
|BTS.AckSendPortID|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识**SendPortID**原始消息中。|  
|BTS.AckSendPortName|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|标识**SendPortName**原始消息中。|  
|BTS.AckType|确认消息发布到 MessageBox 数据库之前由消息引擎升级。|xs:string|允许由业务流程监视确认和非确认等功能。 值将是 ACK 确认和 NACK 对于否定确认。|  
|BTS.ActionOnFailure|若要提交到 BizTalk 消息，可以由适配器调用 IBTTTransportBatch::SubmitMessage() API 前设置此属性。|xs:int|在接收管道故障时控制消息引擎的行为。 通常，消息引擎挂起失败的消息;但是，某些适配器 （如 HTTP) 会将故障报告到客户端而不是接收管道失败时挂起消息。<br /><br /> 有效的值：<br /><br /> -默认值。 如果该属性不存在，消息引擎将自动尝试挂起消息。<br />-   0. 指示消息引擎应自动挂起引擎。<br /><br /> 其他值保留供将来使用。|  
|BTS.CorrelationToken|如果在消息上下文上设置此属性，它是由消息引擎升级。 此属性隐式设置的上下文时请求-响应适配器或业务流程将请求消息提交到 MessageBox 数据库。|xs:string|启用路由到请求-响应端口的响应。|  
|BTS.EpmRRCorrelationToken|由消息引擎在请求-响应消息执行升级。 消息提交到 MessageBox 数据库之前，则升级该属性。|xs:int|由消息引擎在内部使用。 指定服务器名称、 进程 ID 和消息的请求响应流的唯一 GUID。|  
|BTS.InboundTransportLocation|由消息引擎升级后从接收适配器和之前将其发布到 MessageBox 数据库接收消息。|xs:string|指定在其收到消息的处理程序的位置 (URI)。|  
|BTS.InboundTransportType|由消息引擎升级后从接收适配器和之前将其发布到 MessageBox 数据库接收消息。|xs:string|指定接收此消息并提交到服务器的适配器类型：文件、 HTTP 等。|  
|BTS.InterchangeSequenceNumber|通过从接收适配器和之前将其发布到 MessageBox 数据库接收消息之后，消息引擎升级。|xs:int|指示交换中文档的序列号。 如果文档不是拆装到各个文档的交换的一部分，此值将为 1。 该属性可以在业务流程，发送管道中读取和发送适配器。|  
|BTS.IsDynamicSend|在消息上下文上设置此属性。 它将不升级，并仅应用于发送操作。|xs:boolean|动态发送端口上发送操作时，它是由消息引擎，值为 true 写入消息上下文。 如果你想要在发送管道中动态设置属性的静态发送端口，您需要将此值设置为 true。|  
|BTS.MessageDestination|此属性可以设置在接收管道中拆装器管道组件从 getnext （） 返回一条消息时。|xs:string|主要用于支持可恢复交换处理中的拆装器，此属性控制是否发布到消息框或到挂起队列中挂起消息。 如果管道遇到错误的消息交换中，并且想要挂起该消息并继续进行处理，则可采用通过设置 MessageDestination = SuspendQueue 并在该引擎对拆装器调用 getnext （） 返回该消息。<br /><br /> 有效的值：<br /><br /> -默认值。 如果属性不存在，消息则假定为很好，且被发布到消息框。<br />-SuspendQueue。 指示消息引擎挂起消息。 **注意：** 对挂起的消息将是后管道/映射消息和未提交的适配器 （即网络消息） 的消息。|  
|BTS.MessageType|在消息解析期间升级拆装器管道组件。|xs:string|指定消息类型。 消息类型指文档架构命名空间和文档根节点的串联： http://<*MyNamespace*>#<*MyRoot*>。|  
|BTS.OutboundTransportLocation|如果在消息上下文上设置此属性，它是由消息引擎升级。 此属性隐式设置消息上下文时业务流程向发送端口发送一条消息。 此属性是还可以设置显式在业务流程或管道中。|xs:string|指定发送消息的目标位置 URI。 URI 可能包含适配器前缀，如 **http://** 。 适配器前缀由消息引擎使用，以确定发送消息时使用的适配器类型。 如果这两个适配器前缀和**BTS。OutboundTransportType**设置属性，从适配器类型**BTS。OutboundTransportType**始终优先于由前缀的适配器类型。<br /><br /> 有效的值：<br /><br /> BizTalk 消息队列：**DIRECT =**，**专用 =**，和**公共 =**<br /><br /> 文件： **file://**<br /><br /> FTP:**FTP://**<br /><br /> HTTP: **http://** 和**https://**<br /><br /> SMTP: **mailto:**<br /><br /> SOAP:**SOAP://**<br /><br /> SQL:**SQL://**|  
|BTS.OutboundTransportType|如果在消息上下文上设置此属性，它是由消息引擎升级。 此属性隐式设置的上下文时业务流程向发送端口发送一条消息。 此属性在业务流程或管道中还可以显式设置。|xs:string|指定用于发送消息的适配器的类型。 可用适配器类型为**文件**， **FTP**， **HTTP**， **SMTP**， **SOAP**，和**SQL**。<br /><br /> 此属性上设置的值以及地址中指定的适配器前缀不区分大小写。|  
|BTS.PropertiesToUpdate|适配器可设置此属性时需要保留的某些属性值的失败消息，它是正在重新提交或已挂起。<br /><br /> 这意味着当消息重新提交或恢复，它将具有对上下文设置的指定的属性。|xs:string|包含其元素表示属性名称、 命名空间和值的 XML 字符串。|  
|BTS.ReceivePortID|由消息引擎升级后从接收适配器和之前将其发布到 MessageBox 数据库接收消息。|xs:int|标识接收消息的接收端口。|  
|BTS.ReceivePortName|由消息引擎升级后从接收适配器和之前将其发布到 MessageBox 数据库接收消息。|xs:string|接收消息的接收端口的用户友好名称。|  
|BTS.RouteDirectToTP|由消息引擎在消息循环后或请求-响应执行升级。 消息提交到 MessageBox 数据库之前，则升级该属性。|xs:boolean|在内部由消息引擎用于启用循环上一页和请求-响应方案。|  
|BTS.SPGroupID|从业务流程向发送端口发送消息时由消息引擎升级。|xs:string|指定发送端口组的 ID。|  
|BTS.SPID|从业务流程将消息发送到发送端口，由消息引擎升级。|xs:string|指定发送端口的 ID。|  
|BTS.SPName|发布来自要求-响应的响应消息发送端口时由消息引擎升级。|xs:string|用于订阅来自要求-响应发送端口的响应消息。 值为发送端口的名称。|  
|BTS.SPTransportBackupID|从业务流程将消息发送到发送端口，由消息引擎升级。|xs:string|指定发送端口中备份适配器的 ID。|  
|BTS.SPTransportID|从业务流程将消息发送到发送端口，由消息引擎升级。|xs:string|指定发送端口中主适配器的 ID。|  
|BTS.SuspendAsNonResumable|在调用 submitmessage （） 之前或在业务流程向发送端口发送消息之前，可以由适配器设置此属性。 **注意：** Submitrequestmessage （） 将忽略此属性;双向消息始终挂起且不可恢复。|xs:boolean|控制消息引擎是否应在消息失败时挂起且不可恢复的消息。 通常作为恢复挂起消息，但有时这样做不合适-例如，恢复为有序的消息发送或接收端口的情况下会打乱消息顺序。<br /><br /> 有效的值：<br /><br /> -如果为 false。 作为可恢复挂起消息 （这是默认值）。<br />-为 true。 消息被挂起且不可恢复。|  
|BTS.SuspendMessageOnRoutingFailure|由消息引擎升级后从接收适配器和之前将其发布到 MessageBox 数据库接收消息。|xs:boolean|指定传入消息出现路由故障时的行为。<br /><br /> 有效的值：<br /><br /> -Default / False。 如果属性不存在或设置为 False，引擎时出现路由故障通知的错误的适配器。<br />-为 true。 路由故障发生时，路由引擎将自动挂起该消息。 **注意：** 对挂起的消息将是后管道/映射消息和未提交的适配器 （即网络消息） 的消息。|  
  
 有多种此命名空间中包含对于某些 BizTalk 应用程序可能很有用的信息的其他属性。  
  
|属性|时间和位置提升|类型|Description|  
|--------------|-----------------------------------|----------|-----------------|  
|BTS.AckDescription|在确认消息发布到 MessageBox 数据库之前设置由消息引擎。|xs:string|标识**ErrorDescription**，它可使位置和挂起的原因。|  
|BTS.EncryptionCert|不可升级。|xs:int|标识相对应的加密证书的指纹。 在业务流程或自定义管道组件放置在一个管道以接收已签名和加密消息的请求响应端口执行响应加密的 MIME/SMIME 编码器管道组件之前设置此属性。|  
|BTS.InterchangeID|由消息引擎为到达服务器上的每个消息设置。|xs:string|定义用于分组从同一交换消息生成的文档的唯一 ID。|  
|BTS.Loopback|提交为环回执行的请求消息时由适配器设置。|xs:boolean|定义消息是否应提交到服务器以进行环回执行。 在循环中执行中，请求消息发布到 MessageBox 数据库中，它直接路由到接收适配器作为响应。|  
|BTS.SignatureCertificate|当消息提交到服务器时由某些适配器设置。 参与方解析管道组件使用此属性。|xs:string|标识用于对 BizTalk Server 接收的消息进行签名的签名证书的指纹。|  
|BTS.SourcePartyID|后已为传入消息标识的参与方设置参与方解析管道组件。|xs:string|BizTalk 参与方的 ID。|  
|BTS.SSOTicket|如果接收适配器支持此属性，设置时将消息发布到服务器。|xs:string|票证包含加密的域和用户名的当前用户，以及票证到期时间。 启用 SSO 的适配器使用票证以获取用户的凭据进行身份验证向目标终结点时。|  
|BTS.WindowsUser|当消息提交到服务器时由某些适配器设置。 参与方解析管道组件使用此属性。|xs:string|指定代表消息提交到服务器的用户的帐户。|  
  
 有关属性和属性架构与管道组件和适配器关联的其他信息，请参阅：  
  
-   [文件适配器属性架构和属性](../core/file-adapter-property-schema-and-properties.md)
  
-   [FTP 适配器属性架构和属性](../core/ftp-adapter-property-schema-and-properties.md)  
  
-   [HTTP 适配器属性架构和属性](../core/http-adapter-property-schema-and-properties.md)  
  
-   [MSMQ 适配器属性架构和属性](../core/msmq-adapter-property-schema-and-properties.md)  
  
-   [SMTP 适配器属性架构和属性](../core/smtp-adapter-property-schema-and-properties.md)  
  
-   [SOAP 适配器属性架构和属性](../core/soap-adapter-property-schema-and-properties.md)  
  
-   [BizTalk 框架架构和属性](../core/biztalk-framework-schema-and-properties.md)  
  
-   [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)  
  
-   [POP3 适配器属性架构和属性](../core/pop3-adapter-property-schema-and-properties.md)  
  
-   [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)  
  
-   [MIME/SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)  
  
-   [XML 和平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
## <a name="see-also"></a>请参阅  
 [关于 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)   
 [如何使用表达式向动态端口赋值](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)