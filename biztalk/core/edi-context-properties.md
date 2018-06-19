---
title: EDI 上下文属性 |Microsoft 文档
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
ms.openlocfilehash: 36e2f9fcc839625cc0b1ac01ec6e70b53eb2a6e2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010614"
---
# <a name="edi-context-properties"></a>EDI 上下文属性
EDI 全局属性架构中的消息上下文属性是公开的，因此可以在消息路由等操作中使用这些属性。 这些上下文属性在 Microsoft.BizTalk.Edi.BaseArtifacts 程序集的 PropertySchema.xsd 中定义。 这些属性的命名空间是 `http://schemas.microsoft.com/ Edi/PropertySchema`。 如果它们已被提升，则这些消息上下文属性都可用作 Edi。\<*属性名称*\>中**筛选器**页**发送端口属性对话框中** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。


## <a name="context-properties-list"></a>上下文属性列表  
 只要将对 Microsoft.BizTalk.Edi.BaseArtifacts 程序集的引用添加到业务流程项目中，则还可以在业务流程中使用 EDI 上下文属性。
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|AK901|string|指示接受或拒绝在确认的 AK1 段中标识的功能组（仅适用于 X12 997 确认）。|  
|AttachmentId|字符串|邮件附件的 ID。|  
|AgreementID|int|由 EDI 接收管道写入。 指定将入站消息解析到的协议 ID。 对于备用协议，此值为 0。|  
|AgreementName|字符串|由 EDI 接收管道写入。 指定将入站消息解析到的协议名称。 此值对于回退协议是**BTSGuestParty**。|  
|AgreementNameForSend|字符串|由 EDI 发送管道使用，用于出站文档的协议解析。|  
|AgreementPartIDForSend|int|由 EDI 发送管道使用，用于出站文档的协议解析。 此值由批处理业务流程写入。|  
|AgreementPartIDOnReceive|int|由 EDI 接收管道写入。 指定将入站消息解析到的协议的单项协议 ID。 对于备用协议，此值为 0。|  
|BatchElementValidationFailure|boolean|指示当批元素验证失败时批处理系统提示发生错误。|  
|BatchEncodingType|string|BizTalk Server 对传出的批处理交换进行编码时必须使用的编码类型。|  
|BatchId|int|如果此文档只与一个批处理筛选器匹配，则在处理该文档时将使用的批处理配置的批处理 ID。|  
|BatchIds|字符串|如果文档与多个批处理筛选器匹配，则为匹配批处理筛选器集的批处理 ID 列表。|  
|BatchingError|string|描述批处理系统在挂起批元素时提示发生错误。|  
|BatchName|字符串|处理此文档时使用的批处理配置的名称。|  
|CodePage|string|用于验证交换的代码页。|  
|CONTRL_UCI4|string|CONTRL 确认的“操作代码”字段，指示已接受交换（值为“8”）还是因 UNA 或 UNB 段中存在错误而拒绝交换（值为“4”）（仅适用于 EDIFACT CONTRL 确认）。|  
|DestinationPartyID （BizTalk Server 中已弃用）|int|应接收消息的目标参与方的 ID。|  
|DestinationPartyName （BizTalk Server 中已弃用）|string|应接收消息的目标参与方的名称。|  
|DestinationPartyReceiver<br />Identifier|string|应接收消息的目标参与方的标识符。 可以在自定义组件中升级该属性，以便在发送管道中启用参与方解析。|  
|DestinationPartyReceiver<br />Qualifier|string|应接收消息的目标参与方的限定符。 可以在自定义组件中升级该属性，以便在发送管道中启用参与方解析。|  
|DestinationPartySender<br />Identifier|string|将消息发送到目标参与方的参与方的标识符。 可以在自定义组件中升级该属性，以便在发送管道中启用参与方解析。|  
|DestinationPartySender<br />Qualifier|string|将消息发送到目标参与方的参与方的限定符。 可以在自定义组件中升级该属性，以便在发送管道中启用参与方解析。|  
|EncodingType|short|BizTalk Server 对传出消息进行编码所必须使用的编码类型。|  
|ErrorDescription|string|对挂起的消息包含错误消息（类似于事件查看器中的消息）的副本。|  
|GS_Segment|string|完整 GS（功能组）段 (X12)。<br /><br /> 当交换拆分为事务集（而不是保留交换）时，EDI 接收管道将此属性写入到上下文。|  
|GS01|string|功能标识符代码 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|GS02|string|应用程序发送方代码 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|GS03|string|应用程序接收方代码 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|GS07|string|负责代理 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|GS08|string|版本/发行版/行业标识符代码 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|ISA_Segment|string|完整 ISA（交换控制标头）段 (X12)。<br /><br /> 当交换拆分为事务集（而不是保留交换）时，BizTalk Server 将此属性写入到上下文。<br /><br /> 此属性包含安全/授权信息（ISA2 包含授权信息，ISA4 包含安全信息），这可能导致信息泄漏。 你可以使用安全/授权/密码信息掩码属性 (在**验证和确认生成**页) 将替换"#"字符的 ISA2 和 ISA4 字段中的每个字符。 这是一个单向过程:"#"字符不能转换为实际字符。<br /><br /> 当交换拆分为事务集（而不是保留交换）时，EDI 接收管道将此属性写入到上下文。|  
|ISA05|string|交换发送方限定符 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|ISA06|string|交换发送方 ID (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|ISA07|string|交换接收方限定符 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|ISA08|string|交换接收方 ID (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|ISA15|string|用法指示符 (X12)<br /><br /> 如果交换不是保留的批处理交换，EDI 接收管道会将此属性升级到上下文。|  
|IsResendControlMessage|int|AS2 引擎用来指示 AS2 消息发送应该重新传输，因为没有在配置时间内收到 MDN 响应。|  
|IsSystemGeneratedACK|boolean|指示消息是由系统生成的确认（X12 TA1、997 或 EDIFACT CONTRL）。 该属性可设置为 True 或 False。<br /><br /> 这是可用作 EDI 消息上下文属性。中的 IsSystemGeneratedACK**筛选器**页**发送端口属性**对话框。|  
|ReceiverPartyName|字符串|由 EDI 接收管道写入。 指定协议中提供的，并将该消息解析到的目标合作伙伴的名称。 此值对于回退协议是**接收合作伙伴**。|  
|ReceiverPartyNameForSend|字符串|用于由 EDI 发送管道协议解析的出站的文档。|  
|ReuseEnvelope|boolean|指示保留或拆分交换。 如果保留交换，当处理交换以便发送时，BizTalk Server 将重用信封。|  
|SenderPartyName|字符串|由 EDI 接收管道写入。 指定协议中提供的，并将入站消息解析到的源合作伙伴的名称。 此值将为回退协议**BTS 发件人**。|  
|SenderPartyNameForSend|字符串|用于由 EDI 发送管道协议解析的出站的文档。|  
|ST01|string|事务集标识符代码 (X12)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|ST03|string|版本/发行版/行业标识符代码 (X12)<br /><br /> 您可以将此属性写入并升级到上下文，并用于消息路由。|  
|TA1_TA104|string|TA104 确认的“引擎行为”字段，指示是接受交换（值为“A”）、接受交换但存在错误（值为“E”）还是拒绝/挂起交换（值为“R”）（仅适用于 X12 TA1 确认）。|  
|ToBeBatched|boolean|指示批处理业务流程是否应将此消息与其他消息一起进行批处理。<br /><br /> 在批处理交换后，批处理业务流程将此属性设置为“False”。|  
|ToBeRouted|boolean|指示路由业务流程应提取消息，创建尽可能多的批元素副本，使其与该元素的订阅数相等，然后将这些副本路由到 MessageBox。|  
|UNA_Segment|string|完整 UNA（服务字符串建议）段 (EDIFACT)<br /><br /> 当交换拆分为事务集（而不是保留交换）时，EDI 接收管道将此属性写入到上下文。|  
|UNB_Segment|string|完整 UNB（交换控制标头）段 (EDIFACT)。<br /><br /> 当交换拆分为事务集（而不是保留交换）时，EDI 接收管道将此属性写入到上下文。<br /><br /> 此属性包含安全/授权信息（UNB6.1 和 UNB6.2），这可能导致信息泄漏。 您可以使用屏蔽安全/授权/密码信息属性将 UNB6.1 和 UNB6.2 字段中的值替换为“#”字符。 请注意，“#”字符不能转换为实际的字符。|  
|UNB11|string|用法指示符 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNB2_1|string|交换发送方 ID (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNB2_2|string|交换发送方代码限定符 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNB2_3|string|反向路由地址 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNB3_1|string|交换接收方 ID (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNB3_2|string|交换接收方代码限定符 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNG_Segment|string|完整 UNG（功能组）段 (X12)<br /><br /> 当交换拆分为事务集（而不是保留交换）时，EDI 接收管道将此属性写入到上下文。|  
|UNG1|string|功能组标识 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNG2_1|string|应用程序发送方的标识 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNG3_1|string|应用程序接收方的标识 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNH2_1|string|消息类型 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNH2_2|string|消息版本号 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
|UNH2_3|string|消息发行版号 (EDIFACT)<br /><br /> EDI 接收管道将提升到上下文的此属性 （如果该交换不是批处理的交换保留）。|  
  
## <a name="extracting-individual-fields-from-the-segment-context-properties"></a>从段上下文属性中提取单独的字段  
 EDI 接收管道不会将某些属性作为单独属性写入或升级到消息上下文，而仅作为段字符串的一部分写入或升级。 这是出于性能方面的考虑，因为属性升级会影响性能。 例如，接收管道将 ISA 段的 ISA5、ISA6、ISA7、ISA8 和 ISA15 字段作为单独的属性进行升级，但其余 ISA 字段仅作为 ISA_Segment 属性的一部分写入到消息上下文。 这些属性编写或提升时，才**ReuseEnvelope**未设置为 True，指示不保留已收到批处理的交换。  
  
 如果需要将一个段的单独字段（ISA、GS、UNB、UNG 或 UNA）写入到消息上下文，但此单独字段不会默认写入到消息上下文，那么您需要编写一个自定义组件，以便将此字段写入到消息上下文。 该自定义组件需要解析段字段，并将单独的字段写入到消息上下文。  
  
 消息收集示例显示如何使用解析程序从段中提取单独的字段，并将其写入到上下文。 此示例包含在\<驱动器\>: files\microsoft BizTalk Server\SDK\Samples\EDI\MessageEnrichment。 有关详细信息，请参阅[消息扩充示例 （BizTalk Server 示例）](../core/message-enrichment-sample-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)