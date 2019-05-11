---
title: EDI 上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6a408af-daf5-4e9e-afb3-9fd1795e8c16
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afd9724b8728878e358392c28689f6778229d9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350551"
---
# <a name="edi-context-properties"></a>EDI 上下文属性
EDI 全局属性架构中的消息上下文属性被公开以便消息路由等操作中使用它们。 这些上下文属性在 Microsoft.BizTalk.Edi.BaseArtifacts 程序集中 PropertySchema.xsd 中定义。 属性的命名空间是`http://schemas.microsoft.com/ Edi/PropertySchema`。 如果对它们进行升级，这些消息上下文属性都可用作 Edi。\<*属性名称*\>中**筛选器**页**发送端口属性对话框** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。


## <a name="context-properties-list"></a>上下文属性列表  
 只要对 Microsoft.BizTalk.Edi.BaseArtifacts 程序集的引用已添加到业务流程项目，则还可在业务流程中 EDI 上下文属性。
  
|“属性”|类型|Description|  
|----------|----------|-----------------|  
|AK901|string|指示是否接受或拒绝确认的 AK1 段中标识的功能组 (X12 997 的确认）。|  
|AttachmentId|String|邮件附件的 ID。|  
|AgreementID|smallint|写入由 EDI 接收管道。 指定入站的消息解析的协议的 ID。 对于备用协议此值为 0。|  
|AgreementName|String|写入由 EDI 接收管道。 指定入站的消息解析的协议的名称。 此值是对于备用协议**BTSGuestParty**。|  
|AgreementNameForSend|String|由 EDI 发送管道的出站文档的协议解析。|  
|AgreementPartIDForSend|smallint|由 EDI 发送管道的出站文档的协议解析。 此值由批处理业务流程写入。|  
|AgreementPartIDOnReceive|smallint|写入由 EDI 接收管道。 指定入站的消息解析的协议的单项协议 ID。 对于备用协议此值为 0。|  
|BatchElementValidationFailure|boolean|指示当批元素验证失败时错误时升级批处理系统。|  
|BatchEncodingType|string|编码该 BizTalk 服务器的类型必须使用传出的批处理的交换进行编码。|  
|BatchId|smallint|处理时要使用本文档中，如果文档只与一个批处理筛选器相匹配的批处理配置批处理 ID。|  
|BatchIds|String|将集的批处理 Id 匹配批处理筛选器列表，如果文档与多个批处理筛选器相匹配。|  
|BatchingError|string|挂起批元素时，批处理系统提示发生错误的说明。|  
|BatchName|String|要处理此文档时使用的批处理配置的名称。|  
|CodePage|string|要用于验证交换的代码页。|  
|CONTRL_UCI4|string|CONTRL 确认，，该值指示是否已接受交换 （值为"8"） 的操作代码字段或由于 UNA 或 UNB 段 （值为"4"） 中出错而被拒绝 （仅 EDIFACT CONTRL 确认）。|  
|DestinationPartyID （BizTalk Server 中不推荐使用）|ssNoversion|应将消息发送到的目标参与方 ID。|  
|DestinationPartyName （BizTalk Server 中不推荐使用）|string|应将消息发送到的目标参与方名称。|  
|DestinationPartyReceiver<br />Identifier|string|应将消息发送到的目标参与方的标识符。 可以在自定义组件，以便在发送管道中的参与方解析中升级此属性。|  
|DestinationPartyReceiver<br />Qualifier|string|应将消息发送到的目标参与方的限定符。 可以在自定义组件，以便在发送管道中的参与方解析中升级此属性。|  
|DestinationPartySender<br />Identifier|string|将消息发送到目标参与方的参与方的标识符。 可以在自定义组件，以便在发送管道中的参与方解析中升级此属性。|  
|DestinationPartySender<br />Qualifier|string|将消息发送到目标参与方的参与方的限定符。 可以在自定义组件，以便在发送管道中的参与方解析中升级此属性。|  
|EncodingType|short|编码该 BizTalk 服务器的类型必须使用传出消息进行编码。|  
|ErrorDescription|string|对挂起的消息，包含错误消息 （类似于事件查看器中的消息） 的副本。|  
|GS_Segment|string|完整 GS （功能组） 段 (X12)。<br /><br /> 当交换拆分为事务集，则不在保留交换时，EDI 接收管道写入此属性设置为上下文。|  
|GS01|string|功能标识符代码 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|GS02|string|应用程序发送方代码 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|GS03|string|应用程序接收方代码 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|GS07|string|负责机构 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|GS08|string|版本/发行版/行业标识符代码 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|ISA_Segment|string|完整 ISA （交换控制标头） 段 (X12)。<br /><br /> 当交换拆分为事务集，则不在保留交换时，BizTalk Server 会将此属性写入到上下文。<br /><br /> 此属性包含安全/授权信息 （ISA2、 授权信息和 ISA4，安全信息），这可能导致信息泄漏。 您可以使用屏蔽安全/授权/密码信息属性 (在**验证和确认生成**页) 以将 ISA2 和 ISA4 字段中的每个字符替换为"#"字符。 这是一个单向过程： 不能将"#"字符转换为实际的字符。<br /><br /> 当交换拆分为事务集，则不在保留交换时，EDI 接收管道写入此属性设置为上下文。|  
|ISA05|string|交换发送方限定符 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|ISA06|string|交换发送方 ID (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|ISA07|string|交换接收方限定符 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|ISA08|string|交换接收方 ID (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|ISA15|string|用法指示符 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 (如果交换不是批处理保留)。|  
|IsResendControlMessage|ssNoversion|AS2 引擎用于指示，AS2 消息发送应该重新传输，因为未配置的时间内收到 MDN 响应。|  
|IsSystemGeneratedACK|boolean|指示该消息是由系统生成的确认 (X 12 TA1 或 997 或 EDIFACT CONTRL）。 可以设置为 True 或 False。<br /><br /> 这是可用作 EDI 消息上下文属性。在 IsSystemGeneratedACK**筛选器**页**发送端口属性**对话框。|  
|ReceiverPartyName|String|写入由 EDI 接收管道。 指定在解析消息的协议中提供的目标合作伙伴的名称。 此值是对于备用协议**RECEIVE-PARTNER**。|  
|ReceiverPartyNameForSend|String|由 EDI 发送管道的出站文档的协议解析。|  
|ReuseEnvelope|boolean|指示是否保留或拆分交换。 如果保留交换，BizTalk Server 将重用信封处理交换以便发送时。|  
|SenderPartyName|String|写入由 EDI 接收管道。 指定入站的消息解析协议中提供的源合作伙伴的名称。 此值将为对于备用协议**BTS-SENDER**。|  
|SenderPartyNameForSend|String|由 EDI 发送管道的出站文档的协议解析。|  
|ST01|string|事务集标识符代码 (X12)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|ST03|string|版本/发行版/行业标识符代码 (X12)<br /><br /> 可以编写和提升此属性设置为上下文并将其用于消息路由。|  
|TA1_TA104|string|引擎行为 TA104 确认字段，，该值指示是否已接受交换 （值为"A"），但出现错误 （"E"的值），接受或拒绝/已挂起 （值为"R"） (X12 TA1 确认仅)。|  
|ToBeBatched|boolean|指示是否应进行消息与其他消息批处理由批处理业务流程。<br /><br /> 之后对交换的批处理，批处理业务流程设置此属性设置为"False"。|  
|ToBeRouted|boolean|表示应路由业务流程，创建多个批元素副本以及对该元素的订阅，提取消息，然后将这些副本路由到 MessageBox。|  
|UNA_Segment|string|完整 UNA （服务字符串建议） 段 (EDIFACT)<br /><br /> 当交换拆分为事务集，则不在保留交换时，EDI 接收管道写入此属性设置为上下文。|  
|UNB_Segment|string|完整 UNB （交换控制标头） 段 (EDIFACT)<br /><br /> 当交换拆分为事务集，则不在保留交换时，EDI 接收管道写入此属性设置为上下文。<br /><br /> 此属性包含安全/授权信息 （UNB6.1 和 UNB6.2），这可能导致信息泄漏。 屏蔽安全/授权/密码信息属性可用于 UNB6.1 和 UNB6.2 字段中的值替换为"#"字符。 请注意"#"字符，不能转换为实际的字符。|  
|UNB11|string|用法指示符 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNB2_1|string|交换发送方 ID (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNB2_2|string|交换发送方代码限定符 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNB2_3|string|反向路由 (EDIFACT) 地址<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNB3_1|string|交换接收方 ID (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNB3_2|string|交换接收方代码限定符 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNG_Segment|string|完整 UNG （功能组） 段 (X12)<br /><br /> 当交换拆分为事务集，则不在保留交换时，EDI 接收管道写入此属性设置为上下文。|  
|UNG1|string|功能组标识 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNG2_1|string|应用程序发送方的标识 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNG3_1|string|应用程序接收方的标识 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNH2_1|string|消息类型 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNH2_2|string|消息版本号 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
|UNH2_3|string|消息发行版号 (EDIFACT)<br /><br /> EDI 接收管道会升级此属性设置为上下文 （如果交换没有保留批处理的交换）。|  
  
## <a name="extracting-individual-fields-from-the-segment-context-properties"></a>从段上下文属性中提取各个字段  
 某些属性不是写入或升级到消息上下文由 EDI 接收管道作为单独的属性，但仅作为段字符串的一部分。 这样做是出于性能原因，因为属性升级会对性能的影响。 例如，ISA 段 ISA5、 ISA6、 ISA7、 ISA8 和 ISA15 字段作为单独的属性，接收管道进行升级，但其余 ISA 字段仅作为 ISA_Segment 属性的一部分写入到消息上下文。 这些属性会写入或升级时，才**ReuseEnvelope**未设置为 True，指示未保留收到的批的交换。  
  
 如果需要将单个字段的一个段 （ISA、 GS、 UNB、 UNG 或 UNA） 写入到消息上下文，但此单独字段不会默认写入到消息上下文，您需要编写自定义组件以将其写入到消息上下文。 此自定义组件需要解析段字段并将单独的字段写入到消息上下文。  
  
 消息收集示例演示如何使用分析程序从段中提取各个字段并将其写入到上下文。 此示例包含在\<驱动器\>: \Program Files\Microsoft BizTalk Server\SDK\Samples\EDI\MessageEnrichment。 有关详细信息，请参阅[消息充实示例 （BizTalk Server 示例）](../core/message-enrichment-sample-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)