---
title: AS2 上下文属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d63104-f31e-4ed2-b294-ba3ea8a39ae6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03897ce3bd74329a19d85d48b3704f551122d272
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007550"
---
# <a name="as2-context-properties"></a>AS2 上下文属性
五种类型的上下文属性适用于 BizTalk Server 中的 AS2 消息：  
  
-   EdiIntProperties.xsd 架构中的上下文属性  
  
-   BizTalk Server 的内部的上下文属性  
  
-   BizTalk MIME 内部的上下文属性  
  
-   AS2 内部的上下文属性  
  
-   AS2 状态报告内部的上下文属性  
  
## <a name="context-properties-in-the-ediintpropertiesxsd-schema"></a>EdiIntProperties.xsd 架构中的上下文属性  
 EDI/INT 全局属性架构中的消息上下文属性是公开的，因此可以在消息路由等操作中使用这些属性。 在 `Microsoft.BizTalk.Edi.BaseArtifacts` 程序集中的 EdiIntProperties.xsd 中定义了这些上下文属性。 这些属性的命名空间是 `http://schemas.microsoft.com/BizTalk/2006/as2-properties`。 如果它们已被提升，这些消息上下文属性都可用作`EdiIntAS.<Property Name>`中**筛选器**页**发送端口属性**对话框。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|AS2From|string|包含表示发送方名称的 AS2-From AS2 标头值。|  
|AS2PayloadContentType|string|包含负载消息的内容类型。|  
|AS2To|string|包含表示接收方名称的 AS2-To AS2 标头值。|  
|DispositionMode|string|包含 MDN 处置模式值。<br /><br /> 若要生成 MDN，必须同时升级此上下文属性和 DispositionType 上下文属性。|  
|DispositionType|string|包含 MDN 处置类型值。<br /><br /> 若要生成 MDN，必须同时升级此上下文属性和 DispositionMode 上下文属性。|  
|IsAS2AsynchronousMdn|boolean|指示消息是异步 MDN。|  
|IsAS2FailedMessage|boolean|指示传入 AS2 消息在 AS2 中处理失败，导致负载消息挂起。|  
|IsAS2Http200OKResponse|boolean|对将作为 HTTP 200 OK 响应消息生成的消息设置此属性。 它用于不会为 AS2 消息生成 MDN 或已异步发送 MDN 时。|  
|IsAS2MdnResponseMessage|boolean|指示消息是一个 MDN 响应消息。|  
|IsAS2MessageDuplicate|boolean|指示以前已收到传入 AS2 消息。|  
|IsAS2MessageCompressed|boolean|指示传入 AS2 消息是经过压缩的消息。|  
|IsAS2MessageEncrypted|boolean|指示传入 AS2 消息是经过加密的消息。|  
|IsAS2MessageSigned|boolean|指示传入 AS2 消息是经过签名的消息。|  
|IsAS2PayloadMessage|boolean|指示该消息包含解码的 AS2 消息内容，且应作为负载处理。|  
|MDNAsyncURI|string|包含**回执送达选项**发送异步 MDN 响应消息中使用的值。|  
|MessageId|string|包含 AS2 在 AS2 消息的头部中所包括的消息 ID。|  
|OriginalMessageId|string|包含原始 AS2 消息的消息 ID。 该上下文属性是 MDN 消息的一部分，用于将 AS2 消息与其 MDN 响应相关。|  
|PreservedFileName|string|包含消息的原始文件名。 只有传入消息包含文件名信息作为 Content-Disposition MIME 标头的一部分，才会填充此上下文属性。|  
|SendMDN|boolean|如果应当生成 MDN 消息，则设置为 True。|  
  
## <a name="context-properties-internal-to-biztalk-server"></a>BizTalk Server 内部的上下文属性  
 以下消息上下文属性未向公共公开，因此无法将其用于消息路由之类的操作。 但是，可以在被挂起和跟踪的消息中查看这些上下文属性。 这些上下文属性的命名空间是 `http://schemas.microsoft.com/BizTalk/2006/system-properties`。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|IgnoreSslCertificateNameMismatchErrors|boolean|指示 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 处理在处理期间忽略 SSL 名称不匹配错误。|  
|KeepAlive|Boolean|控制 HTTP Keep Alive 功能的行为。|  
|TreatEPMSuspendAsSuccess|boolean|指示 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理双向 HTTP 入站连接时，将挂起消息当作成功消息一样来处理。|  
|IsSolicitResponse|boolean|此属性由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置，它指示该消息是一个要求-响应消息。|  
  
## <a name="context-properties-internal-to-biztalk-mime"></a>BizTalk MIME 的内部的上下文属性  
 以下消息上下文属性未向公共公开，因此无法将其用于消息路由之类的操作。 但是，可以在被挂起和跟踪的消息中查看这些上下文属性。 这些上下文属性的命名空间是 `http://schemas.microsoft.com/BizTalk/2006/system-properties`。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|IsMultipartReport|boolean|导致 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MIME 编码器生成多部分/报告消息。|  
|SuppressMimeVersionFromMultiPartMessage|boolean|导致 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MIME 编码器取消一条多部分消息的每个部分中的 MIME Version 标头。|  
  
## <a name="context-properties-internal-to-as2"></a>AS2 的内部的上下文属性  
 以下消息上下文属性未向公共公开，因此无法将其用于消息路由之类的操作。 但是，可以在被挂起和跟踪的消息中查看这些上下文属性。 这些上下文属性的命名空间是 `http://schemas.microsoft.com/BizTalk/2006/as2-properties`。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|MicHashAlgorithm|string|包含计算 MIC 哈希值时所用的哈希算法。|  
|ReceivedContentMic|string|包含计算出的 MIC 哈希值。|  
  
## <a name="context-properties-internal-to-as2-status-reporting"></a>上下文属性 AS2 的内部状态报告  
 以下消息上下文属性未向公共公开，因此无法将其用于消息路由之类的操作。 但是，可以在被挂起和跟踪的消息中查看这些上下文属性。 这些上下文属性的命名空间是 `http://schemas.microsoft.com/BizTalk/2006/edi-properties`。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|InterchangeControlNo|string|来自 EDI 交换的交换控制编号。 该属性是在 AS2 编码期间从消息中读取的，并用于报告 AS2 交换活动。|  
|InterchangeDate|string|来自 EDI 交换的交换日期。 该属性是在 AS2 编码期间从消息中读取的，并用于报告 AS2 交换活动。|  
|InterchangeTime|string|来自 EDI 交换的交换时间。 该消息上下文属性是在 AS2 编码期间从消息中读取的，并用于报告 AS2 交换活动。|  
|ReceiverID|string|来自 EDI 交换的交换接收方 ID。 该属性是在 AS2 编码期间从消息中读取的，并用于报告 AS2 交换活动。|  
|ReceiverQualifier|string|来自 EDI 交换的交换接收方限定符。 该属性是在 AS2 编码期间从消息中读取的，并用于报告 AS2 交换活动。|  
|SenderID|string|来自 EDI 交换的交换发送方 ID。 该属性是在 AS2 编码期间从消息中读取的，并用于报告 AS2 交换活动。|  
|SenderQualifier|string|来自 EDI 交换的交换发送方限定符。 该属性是在 AS2 编码期间从消息中读取的，并用于报告 AS2 交换活动。|  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)