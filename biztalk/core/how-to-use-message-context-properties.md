---
title: 如何使用消息上下文属性 |Microsoft 文档
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
ms.openlocfilehash: 084eae49777b62b190e8e090c0b1045d301d420b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975315"
---
# <a name="how-to-use-message-context-properties"></a>如何使用消息上下文属性
系统属性主要由 BizTalk 消息引擎及其组件在内部使用。 通常，不建议更改引擎为那些属性设置的值，因为这样可能会影响引擎的执行逻辑。 然而，还有很多可以修改的属性。  
  
 下表包含了消息引擎可以升级的消息上下文属性的列表。 可以使用这些属性在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中对发送端口和业务流程创建筛选器表达式。 例如：  
  
```  
PortName = MyMessage(BTS.ReceivePortName);  
MyFileName = MyMessage(BTS.ReceivedFileName);  
MySubject= MyMessage(POP3.Subject);  
```  
  
 一个单独的表列出了可能在某些无法升级的 BizTalk 应用程序中使用的其他属性。  
  
|属性|升级的时间和位置|类型|Description|  
|--------------|-----------------------------------|----------|-----------------|  
|BTS.AckFailureCategory|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:int|标识**ErrorCategory**，后者提供的位置和将其挂起的原因。|  
|BTS.AckFailureCode|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识**ErrorCode**，后者提供的位置和将其挂起的原因。|  
|BTS.AckID|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识**MessageID**的原始消息。|  
|BTS.AckInboundTransportLocation|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识**InboundTransportLocation**原始消息中。|  
|BTS.AckOutboundTransportLocation|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识**OutboundTransportLocation**原始消息中。|  
|BTS.AckOwnerID|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识从原始消息的实例 ID。|  
|BTS.AckReceivePortID|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识**ReceivePortID**原始消息中。|  
|BTS.AckReceivePortName|由消息引擎为确认消息升级。|xs:string|标识**ReceivePortName**原始消息中。|  
|BTS.AckSendPortID|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识**SendPortID**原始消息中。|  
|BTS.AckSendPortName|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|标识**SendPortName**原始消息中。|  
|BTS.AckType|将确认消息发布到 MessageBox 数据库之前，由消息引擎升级。|xs:string|允许由业务流程监视确认和非确认。 值将 ACK 有关确认，以及 NACK 否定确认。|  
|BTS.ActionOnFailure|在调用 IBTTTransportBatch::SubmitMessage() API 以便将消息提交到 BizTalk 之前，此属性可由适配器设置。|xs:int|接收管道中出现故障时，控制消息引擎的行为。 通常，消息引擎挂起失败的消息；不过，某些适配器（如 HTTP）会将故障报告到客户端，而不是在出现接收管道故障时挂起消息。<br /><br /> 有效值：<br /><br /> 的默认值。 如果该属性不存在，消息引擎将自动尝试挂起消息。<br />-   0. 指示消息引擎不应自动挂起引擎。<br /><br /> 保留其他值以供将来使用。|  
|BTS.CorrelationToken|如果对消息上下文设置了此属性，消息引擎将对其升级。 当请求-响应适配器或业务流程将请求消息提交到 MessageBox 数据库中时，则对上下文隐式设置此属性。|xs:string|对请求-响应端口启用响应路由。|  
|BTS.EpmRRCorrelationToken|由消息引擎在执行请求-响应消息时升级。 在消息提交到 MessageBox 数据库之前升级该属性。|xs:int|由消息引擎内部使用。 为消息的请求响应流指定服务器名称、进程 ID 和唯一 GUID。|  
|BTS.InboundTransportLocation|从接收适配器和之前将其发布到 MessageBox 数据库收到一条消息后提升由消息传送引擎。|xs:string|指定处理程序接收消息的位置 (URI)。|  
|BTS.InboundTransportType|从接收适配器和之前将其发布到 MessageBox 数据库收到一条消息后提升由消息传送引擎。|xs:string|指定接收此消息并提交到该服务器适配器的类型： 文件、 HTTP，等等。|  
|BTS.InterchangeSequenceNumber|从接收适配器接收消息之后并且在将其发布到 MessageBox 数据库之前，由消息引擎升级。|xs:int|指示文档在交换中的顺序号。 如果该文档不是交换的已分解到单个文档的一部分，此值将是交换的 1。 属性可以按业务流程，发送管道读取，并发送适配器。|  
|BTS.IsDynamicSend|可以对消息上下文设置此属性。 此属性将不升级，并且只应用于发送操作。|xs:boolean|在发送操作在动态发送端口上进行时，如果该值为 true 值，则消息引擎会将其写入消息上下文。 如果您想要为发送管道中的静态发送端口动态设置属性，则需要将此值设置为 true。|  
|BTS.MessageDestination|当拆装器管道组件从 GetNext() 返回消息时，此属性可由该组件在接收管道中设置。|xs:string|此属性主要用于支持拆装器中的可恢复交换处理，控制消息是发布到 MessageBox 还是在挂起队列中挂起。 如果管道在交换中遇到错误消息，需要挂起该消息然后继续处理，则可通过设置 MessageDestination = SuspendQueue 来实现，并在引擎对拆装器调用 GetNext() 时返回该消息。<br /><br /> 有效值：<br /><br /> 的默认值。 如果属性不存在，则假定消息正常，并发布到 MessageBox。<br />-SuspendQueue。 指示消息引擎挂起消息。 **注意：** 挂起的消息将 pipeline 后/映射消息和未提交的适配器 （即网络消息） 的消息。|  
|BTS.MessageType|由拆装器管道组件在消息解析期间升级。|xs:string|指定消息类型。 消息类型指文档架构命名空间和文档根节点的串联： http://&lt*MyNamespace*>#<*MyRoot*>。|  
|BTS.OutboundTransportLocation|如果对消息上下文设置了此属性，消息引擎将对其升级。 当业务流程向发送端口发送消息时，对消息上下文隐式设置此属性。 也可在业务流程或管道中显式设置此属性。|xs:string|指定发送消息的目标位置 URI。 URI 可能包含适配器前缀，如**http://**。 适配器前缀由消息引擎使用，以确定发送消息时使用的适配器类型。 如果这两个适配器前缀和**BTS。OutboundTransportType**设置属性，从适配器类型**BTS。OutboundTransportType**始终优先于从前缀确定的适配器类型。<br /><br /> 有效值：<br /><br /> BizTalk 消息队列：**直接 =**，**私有 =**，和**公共 =**<br /><br /> 文件： **file://**<br /><br /> FTP: **FTP: / /**<br /><br /> HTTP: **http://** 和**https://**<br /><br /> SMTP: **mailto:**<br /><br /> SOAP: **SOAP: / /**<br /><br /> SQL: **SQL: / /**|  
|BTS.OutboundTransportType|如果对消息上下文设置了此属性，消息引擎将对其升级。 当业务流程向发送端口发送消息时，对上下文隐式设置此属性。 此属性在业务流程中或在管道中还可以显式设置。|xs:string|指定用于发送消息的适配器类型。 可用的适配器类型**文件**， **FTP**， **HTTP**， **SMTP**， **SOAP**，和**SQL**。<br /><br /> 对此属性设置的值以及地址中指定的适配器前缀不区分大小写。|  
|BTS.PropertiesToUpdate|当适配器需要保留某些正在重新提交或挂起的失败消息的属性值时，将设置此属性。<br /><br /> 这意味着，当消息重新提交或恢复后，将具有对上下文设置的指定属性。|xs:string|包含具有表示属性名称、命名空间和值的元素的 XML 字符串。|  
|BTS.ReceivePortID|从接收适配器和之前将其发布到 MessageBox 数据库收到一条消息后提升由消息传送引擎。|xs:int|标识接收消息的接收端口。|  
|BTS.ReceivePortName|从接收适配器和之前将其发布到 MessageBox 数据库收到一条消息后提升由消息传送引擎。|xs:string|接收消息的接收端口的用户友好名称。|  
|BTS.RouteDirectToTP|在执行环回或请求-响应消息时由消息引擎升级。 在消息提交到 MessageBox 数据库之前升级该属性。|xs:boolean|由消息引擎内部使用，以启用环回或请求-响应方案。|  
|BTS.SPGroupID|由消息传送引擎后将消息发送到发送端口业务流程从提升。|xs:string|指定发送端口组的 ID。|  
|BTS.SPID|当消息从业务流程发送到发送端口时由消息引擎升级。|xs:string|指定发送端口的 ID。|  
|BTS.SPName|从要求-响应发送端口发布响应消息时由消息引擎升级。|xs:string|用于订阅来自要求-响应发送端口的响应消息。 值为发送端口的名称。|  
|BTS.SPTransportBackupID|后一条消息发送到发送端口业务流程从按消息引擎提升。|xs:string|指定发送端口中备份适配器的 ID。|  
|BTS.SPTransportID|后一条消息发送到发送端口业务流程从按消息引擎提升。|xs:string|指定发送端口中主适配器的 ID。|  
|BTS.SuspendAsNonResumable|在调用 SubmitMessage() 之前或在业务流程中向发送端口发送消息之前，可由适配器设置此属性。 **注意：** SubmitRequestMessage() 将忽略此属性; 双向消息都将被挂起始终为非可恢复。|xs:boolean|控制消息引擎是否应该在发生消息故障时将消息作为不可恢复的消息挂起。 通常消息作为可恢复的消息挂起，但在有些情况下，这样做不合适。例如，为有序的发送或接收端口恢复消息会打乱消息顺序。<br /><br /> 有效值：<br /><br /> -如果为 false。 消息作为可恢复消息挂起（这是默认设置）。<br />-为 true。 消息作为不可恢复消息挂起。|  
|BTS.SuspendMessageOnRoutingFailure|从接收适配器和之前将其发布到 MessageBox 数据库收到一条消息后提升由消息传送引擎。|xs:boolean|指定传入消息出现路由故障时的行为。<br /><br /> 有效值：<br /><br /> 的默认 / False。 如果该属性不存在或设置为 False，则引擎将在出现路由故障时向适配器通知错误。<br />-为 true。 出现路由故障时，路由引擎将自动挂起消息。 **注意：** 挂起的消息将 pipeline 后/映射消息和未提交的适配器 （即网络消息） 的消息。|  
  
 此命名空间中有许多其他属性，它们包含了对某些 BizTalk 应用程序可能很有用的信息。  
  
|属性|升级的时间和位置|类型|Description|  
|--------------|-----------------------------------|----------|-----------------|  
|BTS.AckDescription|将确认消息发布到 MessageBox 数据库之前，由消息引擎设置。|xs:string|标识**ErrorDescription**，后者提供的位置和将其挂起的原因。|  
|BTS.EncryptionCert|不可升级。|xs:int|标识与加密证书相对应的指纹。 在业务流程中或在管道中的 MIME/SMIME 编码器管道组件前放置的自定义管道组件中设置此属性，以便对接收已签名且加密的消息的请求-响应端口执行响应加密。|  
|BTS.InterchangeID|由消息引擎为到达服务器的每个消息设置。|xs:string|定义用于对从同一交换消息生成的文档进行分组的唯一 ID。|  
|BTS.Loopback|为环回执行提交请求消息时由适配器设置。|xs:boolean|定义消息是否应提交到服务器以进行环回执行。 在环回执行中，请求消息发布到 MessageBox 数据库，在那里作为响应直接路由到接收适配器。|  
|BTS.SignatureCertificate|将消息提交到服务器时由某些适配器设置。 此属性由参与方解析管道组件使用。|xs:string|标识用于给 BizTalk Server 接收的消息签名的签名证书的指纹。|  
|BTS.SourcePartyID|已为传入消息标识参与方后，由参与方解析管道组件设置。|xs:string|BizTalk 参与方的 ID。|  
|BTS.SSOTicket|如果接收适配器支持此属性，则将消息发布到服务器时设置该属性。|xs:string|票证包含当前用户的加密域和用户名以及票证到期时间。 此票证由启用 SSO 的适配器使用，以便在向目标终结点进行身份验证时获取用户的凭据。|  
|BTS.WindowsUser|将消息提交到服务器时由某些适配器设置。 此属性由参与方解析管道组件使用。|xs:string|指定以其名义将消息提交到服务器时的用户帐户。|  
  
 有关与管道组件和适配器关联的属性和属性架构的其他信息，请参阅以下主题：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [有关 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)   
 [如何使用表达式将值分配到动态端口](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)