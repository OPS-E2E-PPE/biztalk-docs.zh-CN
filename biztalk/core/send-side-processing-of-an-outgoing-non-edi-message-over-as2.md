---
title: 发送端处理通过 AS2 传出的非 EDI 消息的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f19b7df-fe6d-4105-8a44-3d6db0bba451
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47b4f553d5f16812958addab8082b5e0c79d7f0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254466"
---
# <a name="send-side-processing-of-an-outgoing-non-edi-message-over-as2"></a>通过 AS2 传出的非 EDI 消息的发送端处理
AS2 管道附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用于处理通过 AS2 传输发送的 EDI 消息或非 EDI 消息。 不同的管道用于两个不同类型的有效负载。 您使用 AS2EdiSend 管道处理通过 AS2 传出的 EDI 消息并使用 AS2Receive 管道接收关联的 MDN （如果已启用）。 您使用 AS2Send 管道处理通过 AS2 传出的非 EDI 消息并使用 AS2Receive 管道接收关联的 MDN （如果已启用）。 非 EDI 消息可以是任何二进制负载。  
  
 AS2Send 发送管道汇编的非 EDI 负载，并对 AS2 消息进行编码。 AS2Receive 接收管道将解码的 MDN 响应。 可以包含这些管道在一个 HTTP 双向要求响应发送端口 （对于同步 Mdn)，或在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口 （对于异步 Mdn)。  
  
 若要通过 AS2 发送 EDI 交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行以下步骤：  
  
-   处理用于发送非 EDI 负载  
  
-   发送 AS2 消息  
  
-   接收返回的 MDN  
  
## <a name="processing-the-non-edi-payload-for-sending"></a>处理用于发送非 EDI 负载  
 在创建之前 AS2 消息，发送端口必须提取非 EDI 负载，使用相应的筛选器表达式订阅消息。 可以使用双向发送端口或单向发送端口，取决于是否 MDN 将同步或异步。 然后，AS2Send 管道将处理成 AS2 消息的非 EDI 负载。  
  
## <a name="sending-the-as2-message"></a>发送 AS2 消息  
 AS2 发送管道中的 AS2 编码器首先执行协议解析，以确定要用来处理传出的消息的协议属性。 有关详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
 AS2 编码器生成发送 AS2 消息所需的 HTTP 标头的集合。 它将添加到这些标头`HTTP.UserHttpHeaders`上下文属性，它是单个字符串的标头值。 AS2 编码器生成以下 AS2 标头在 HTTP。UserHttpHeaders。 这些标头必须包含 AS2 消息中。  
  
- AS2-To  
  
- AS2-从  
  
- AS2 版本  
  
- MessageID  
  
- OriginalMessageID (仅限 Mdn)  
  
  如果**请求 MDN**属性后，管道会将处置-到通知、 回执送达选项和 Signed-receipt-micalg 即用的 AS2 标头中的相应属性; 和它的值将消息中设置如果将设置为"pcks7 签名"的签名回执协议 AS2 标头**请求经过签名的 MDN**属性处于选中状态。  
  
  如果`HTTP.UserHttpHeaders`上下文属性不存在，则 AS2 编码器将创建它。 如果`HTTP.UserHttpHeaders`已存在，则 AS2 编码器将使用它，而不是创建它。 如果您创建`HTTP.UserHttpHeaders`和标头写入它，然后将其写入到消息上下文，AS2 编码器将使用这些标头，并且它们将优先于标头从其他源。 是一个例外 AS2-From 标头，它始终来自协议属性。  
  
  如果 AS2 标头不在`HTTP.UserHttpHeaders`，AS2 编码器会将其添加从单个上下文属性。 这意味着，您可以通过升级或写入到消息的上下文来添加 AS2 标头 (如果它们尚不在`HTTP.UserHttpHeaders`)。 如果 AS2 标头既不在`HTTP.UserHttpHeaders`，也不作为属性存在于上下文，AS2 编码器会将其添加到的协议属性`HTTP.UserHttpHeaders`。  
  
  AS2 编码器生成标头后`HTTP.UserHttpHeaders`属性，它将其写入消息的上下文。 HTTP 适配器提取`HTTP.UserHttpHeaders`，并将前面添加的标头值`HTTP.UserHttpHeaders`到消息。  
  
> [!NOTE]
>  AS2 传输协议应仅对 HTTP 适配器。 但是，如果你手动设置相应的上下文属性，您可以使用文件适配器传输 AS2 消息。 有关详细信息，请参阅[通过 FILE 发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。  
  
## <a name="processing-the-returned-mdn"></a>处理返回的 MDN  
 如果启用了 MDN，则与双向发送端口关联的接收管道从接收 AS2 消息的参与方接收 MDN。  
  
> [!NOTE]
>  有关 AS2 发送管道对传入的 Mdn 执行处理的详细信息，请参阅[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)