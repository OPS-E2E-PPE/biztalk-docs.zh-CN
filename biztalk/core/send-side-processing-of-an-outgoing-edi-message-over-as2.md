---
title: 发送方的传出 EDI 消息处理通过 AS2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfb63b22-6e2e-4d4f-b028-301c8d4d53b0
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b893f7a5732bf204764bf7377ee39a8e628f3747
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271869"
---
# <a name="send-side-processing-of-an-outgoing-edi-message-over-as2"></a>通过 AS2 传出的 EDI 消息的发送端处理
发送方在处理通过 AS2 EDI 消息包括发送 EDI 负载的 AS2 消息和接收 MDN 和 EDI 确认 （如果启用）。  
  
 AS2EDISend 发送管道通过 HTTP/HTTPS 将装配的 EDI/AS2 消息发送到接收的贸易合作伙伴。 AS2EDIReceive 接收管道接收到的 AS2 消息和 EDI 确认 EDI 消息的响应中返回的响应中返回 MDN。 每个这些管道处理 AS2 消息并处理 AS2 消息中的 EDI 负载。 你可以包括这些管道中双向 HTTP 请求作出响应发送端口，或在单向 HTTP 发送端口和单向 HTTP 接收端口。  
  
 若要通过 AS2 发送 EDI 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将执行以下步骤：  
  
-   处理发送的 EDI 负载  
  
-   发送 AS2 消息  
  
-   接收返回的 MDN  
  
-   接收返回的 EDI 确认  
  
## <a name="processing-the-edi-payload-for-sending"></a>处理发送的 EDI 负载  
 在创建 AS2 消息之前, AS2EdiSend 管道必须处理 EDI 交换。 如果启用出站批处理时，在中所述，将进行批处理事务集[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。 EDI 汇编器将创建 EDI 交换中所述[EDI 汇编程序的工作原理](../core/how-the-edi-assembler-works.md)。  
  
## <a name="sending-the-as2-message"></a>发送 AS2 消息  
 AS2 发送管道中的 AS2 编码器首先执行协议解析，以确定将要用于处理传出消息的协议属性。 有关详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
 AS2 编码器可生成发送 AS2 消息所需的 HTTP 标头集。 它将这些标头添加到 `HTTP.UserHttpHeaders` 上下文属性中，该属性是标头值的单个字符串。 AS2 编码器生成以下 AS2 标头`HTTP.UserHttpHeaders`。 这些标头必须包含在 AS2 消息中。  
  
-   AS2-To  
  
-   AS2-From  
  
-   AS2-Version  
  
-   MessageID  
  
-   OriginalMessageID（仅限 MDN）  
  
 如果**请求 MDN**属性已选中，则管道将中的相应属性; 和它的值将邮件中设置处置-到通知、 回执送达选项和已签名回执 MICalg AS2 标头如果将设置为"pcks7 签名"的已签名回执协议 AS2 标头**请求经过签名的 MDN**检查属性。  
  
 如果 `HTTP.UserHttpHeaders` 上下文属性不存在，则 AS2 编码器将创建该属性。 如果 `HTTP.UserHttpHeaders` 已存在，则 AS2 编码器将使用它，而不是创建它。 如果创建 `HTTP.UserHttpHeaders` 并将标头写入该属性，然后将该属性写入消息的上下文，AS2 编码器将使用这些标头，并且这些标头的优先级将高于其他源中的标头。 但 AS2-From 标头是一个例外，它始终来自协议属性。  
  
 如果 AS2 标头不在 `HTTP.UserHttpHeaders` 中，则 AS2 编码器会从单个上下文属性添加该标头。 也就是说，您可以通过将属性升级或写入消息的上下文来添加 AS2 标头（如果这些标头尚不在 `HTTP.UserHttpHeaders` 中）。 如果 AS2 标头既不在 `HTTP.UserHttpHeaders` 中，也没有作为属性存在于上下文中，则 AS2 编码器会从协议属性将该标头添加到 `HTTP.UserHttpHeaders` 中。  
  
 AS2 编码器在 `HTTP.UserHttpHeaders` 属性中生成标头后，它会将该属性写入消息的上下文。 HTTP 适配器提取 `HTTP.UserHttpHeaders`，并将 `HTTP.UserHttpHeaders` 中的标头值预置到消息中。  
  
> [!NOTE]
>  AS2 传输仅用于 HTTP 适配器。 然而，如果您手动设置了相应的上下文属性，则可以使用 FILE 适配器传输 AS2 消息。 有关详细信息，请参阅[通过文件发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。  
  
## <a name="processing-the-returned-mdn"></a>处理返回的 MDN  
 如果 MDN 已启用，则与双向发送端口相关联的接收管道将从接收 AS2 消息的参与方接收 MDN。  
  
> [!NOTE]
>  有关对传入 Mdn 执行 AS2 发送管道处理的详细信息，请参阅[发送传出 MDN](../core/sending-an-outgoing-mdn.md)。  
  
## <a name="processing-the-returned-edi-acknowledgment"></a>处理返回的 EDI 确认  
 如果启用了 EDI 确认时，接收管道与双向发送端口相关联还 EDI 确认从接收 EDI 消息的接收方 （因为它在 BizTalk EDI ACK 消息类型上进行筛选）。 有关详细信息，请参阅[处理收到的确认](../core/processing-a-received-acknowledgment.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md)