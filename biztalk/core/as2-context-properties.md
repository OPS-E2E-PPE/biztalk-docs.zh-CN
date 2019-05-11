---
title: AS2 上下文属性 |Microsoft Docs
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
ms.openlocfilehash: 9a2685a9547d71d3e6fad4b2f81c0c9d2d7d35b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358947"
---
# <a name="as2-context-properties"></a>AS2 上下文属性
五种类型的上下文属性适用于 BizTalk Server 中的 AS2 消息：  

-   EdiIntProperties.xsd 架构中的上下文属性  

-   内部的 BizTalk Server 上下文属性  

-   BizTalk MIME 内部的上下文属性  

-   内部的 AS2 上下文属性  

-   AS2 状态报告的内部的上下文属性  

## <a name="context-properties-in-the-ediintpropertiesxsd-schema"></a>EdiIntProperties.xsd 架构中的上下文属性  
 EDI/INT 全局属性架构中的消息上下文属性被公开以便消息路由等操作中使用它们。 集中的 ediintproperties.xsd 中定义了这些上下文属性`Microsoft.BizTalk.Edi.BaseArtifacts`程序集。 属性的命名空间是`http://schemas.microsoft.com/BizTalk/2006/as2-properties`。 如果对它们进行升级，这些消息上下文属性都可用作`EdiIntAS.<Property Name>`中**筛选器**页**发送端口属性**对话框。  

|“属性”|类型|Description|  
|----------|----------|-----------------|  
|AS2From|string|包含 AS2-From AS2 标头值，该值表示发件人的名称。|  
|AS2PayloadContentType|string|包含负载消息的内容类型。|  
|AS2To|string|包含 AS2-To AS2 标头值，该值表示接收方的名称。|  
|DispositionMode|string|包含 MDN 处置模式值。<br /><br /> 为了使若要生成 MDN，必须升级此上下文属性和 DispositionType 上下文属性。|  
|DispositionType|string|包含 MDN 处置类型值。<br /><br /> 为了使若要生成 MDN，必须升级此上下文属性和 DispositionMode 上下文属性。|  
|IsAS2AsynchronousMdn|boolean|指示该消息是一个异步 MDN。|  
|IsAS2FailedMessage|boolean|指示传入 AS2 消息已失败处理在 AS2 中，导致负载消息挂起。|  
|IsAS2Http200OKResponse|boolean|设置将作为 HTTP 200 OK 响应消息生成的消息。 为 AS2 消息或以异步方式发送 MDN 时，将不会生成一个 MDN 时使用它。|  
|IsAS2MdnResponseMessage|boolean|指示该消息是一个 MDN 响应消息。|  
|IsAS2MessageDuplicate|boolean|指示传入 AS2 消息以前已收到。|  
|IsAS2MessageCompressed|boolean|指示传入的 AS2 消息已压缩。|  
|IsAS2MessageEncrypted|boolean|指示传入的 AS2 消息已加密。|  
|IsAS2MessageSigned|boolean|指示传入 AS2 消息的签名。|  
|IsAS2PayloadMessage|boolean|指示此消息包含解码的 AS2 消息内容，并应作为负载处理。|  
|MDNAsyncURI|string|包含**回执送达选项**用于发送异步 MDN 响应消息的值。|  
|MessageId|string|包含在 AS2 消息的标头中包含的 AS2 消息 ID。|  
|OriginalMessageId|string|包含原始 AS2 消息的消息 ID。 此上下文属性是 MDN 消息的一部分，用于将 AS2 消息和与其 MDN 响应相关联。|  
|PreservedFileName|string|包含消息的原始文件名称。 如果传入消息包含文件名信息作为 Content-disposition MIME 标头的一部分，才会填充此上下文属性。|  
|SendMDN|boolean|如果，设置为 true 应生成一个 MDN 消息。|  

## <a name="context-properties-internal-to-biztalk-server"></a>BizTalk Server 内部的上下文属性  
 下面的消息上下文属性不是公开，因此不能用于消息路由等操作。 但是，它们可以挂起和跟踪的消息中查看。 这些上下文属性的命名空间是`http://schemas.microsoft.com/BizTalk/2006/system-properties`。  


|                  “属性”                  |  类型   |                                                                                            Description                                                                                             |
|----------------------------------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IgnoreSslCertificateNameMismatchErrors | boolean |                  指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 处理在处理期间忽略 SSL 名称不匹配错误。                  |
|               KeepAlive                | Boolean |                                                                    控制 HTTP Keep Alive 功能的行为。                                                                     |
|        TreatEPMSuspendAsSuccess        | boolean | 指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要被视为一条成功消息将挂起的消息在处理双向 HTTP 入站连接时。 |
|           IsSolicitResponse            | boolean |                      通过设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和指示该消息是一个要求-响应消息。                       |

## <a name="context-properties-internal-to-biztalk-mime"></a>到 BizTalk MIME 内部的上下文属性  
 下面的消息上下文属性不是公开，因此不能用于消息路由等操作。 但是，它们可以挂起和跟踪的消息中查看。 这些上下文属性的命名空间是`http://schemas.microsoft.com/BizTalk/2006/system-properties`。  


|                  “属性”                   |  类型   |                                                                                     Description                                                                                     |
|-----------------------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            IsMultipartReport            | boolean |                 导致[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MIME 编码器生成多部分/报告消息。                  |
| SuppressMimeVersionFromMultiPartMessage | boolean | 导致[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MIME 编码器取消多部分消息的每个部分中的 MIME Version 标头。 |

## <a name="context-properties-internal-to-as2"></a>内部的 AS2 上下文属性  
 下面的消息上下文属性不是公开，因此不能用于消息路由等操作。 但是，它们可以挂起和跟踪的消息中查看。 这些上下文属性的命名空间是`http://schemas.microsoft.com/BizTalk/2006/as2-properties`。  

|“属性”|类型|Description|  
|----------|----------|-----------------|  
|MicHashAlgorithm|string|包含计算 MIC 哈希值时使用的哈希算法。|  
|ReceivedContentMic|string|包含计算的 MIC 哈希值。|  

## <a name="context-properties-internal-to-as2-status-reporting"></a>内部的 AS2 上下文属性状态报告  
 下面的消息上下文属性不是公开，因此不能用于消息路由等操作。 但是，它们可以挂起和跟踪的消息中查看。 这些上下文属性的命名空间是`http://schemas.microsoft.com/BizTalk/2006/edi-properties`。  

|“属性”|类型|Description|  
|----------|----------|-----------------|  
|InterchangeControlNo|string|来自 EDI 交换的交换控制编号。 此属性在 AS2 编码期间从消息中读取，用于报告 AS2 交换活动。|  
|InterchangeDate|string|来自 EDI 交换的交换日期。 此属性在 AS2 编码期间从消息中读取，用于报告 AS2 交换活动。|  
|InterchangeTime|string|来自 EDI 交换的交换时间。 此消息上下文属性在 AS2 编码期间从消息中读取，用于报告 AS2 交换活动。|  
|ReceiverID|string|来自 EDI 交换的交换接收方 ID。 此属性在 AS2 编码期间从消息中读取，用于报告 AS2 交换活动。|  
|ReceiverQualifier|string|来自 EDI 交换的交换接收方限定符。 此属性在 AS2 编码期间从消息中读取，用于报告 AS2 交换活动。|  
|SenderID|string|来自 EDI 交换的交换发送方 ID。 此属性在 AS2 编码期间从消息中读取，用于报告 AS2 交换活动。|  
|SenderQualifier|string|来自 EDI 交换的交换发送方限定符。 此属性在 AS2 编码期间从消息中读取，用于报告 AS2 交换活动。|  

## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)