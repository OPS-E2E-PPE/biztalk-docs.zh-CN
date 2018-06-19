---
title: 发送传出 MDN |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dce7620-d354-4b76-bcbc-f97dc93c3fc3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d947751e06e0dc9892ab63e109b417047ad91b59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271421"
---
# <a name="sending-an-outgoing-mdn"></a>发送传出 MDN
传出的 MDN 由 AS2EDIReceive 或 AS2Receive 接收管道生成，由 AS2Send 管道发送。 本主题介绍如何发送 MDN。 有关如何生成 MDN 的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。  
  
> [!NOTE]
>  AS2EDISend 发送管道不用于发送传出的 MDN，原因是在处理 MDN 的过程中不使用该管道中的 EDI 组装器。  
  
## <a name="agreement-resolution-for-an-mdn"></a>MDN 的协议解析  
 MDN 是自路由的。 它包含路由到目标协议所需的信息。 发送管道使用 AS2 协议属性来处理传出的 MDN。 但是，MDN 不必等到解析某个协议之后才能路由到参与方。  
  
 当 AS2Send 管道处理某个传出的 MDN 时，它使用消息上下文中的 AS2-To 值来获得用于处理此 MDN 的协议属性。 它会通过匹配 AS2-到通过 AS2 的上下文属性-到中的协议属性**标识符**的单向 AS2 协议选项卡中的页**协议属性**对话框。 如果没有为此协议设置 AS2-To 值，则此 MDN 的协议解析可能会失败。 如果无法确定此协议，则使用默认协议来生成 MDN。  
  
 在传出的 MDN 的默认协议中，会执行证书解析列表验证。 如果您不希望执行此验证，请确认设置了正确的 AS2-To 协议属性，以便能够解析接收方并且能够确定协议属性。 这样的话，将不使用提示验证证书解析列表的默认协议。 你还需要禁用**检查证书吊销列表**属性**验证**页中的单向 AS2 协议选项卡**协议属性**对话框。  
  
## <a name="synchronous-and-asynchronous-transmission"></a>同步和异步传输  
 在默认的 AS2 处理过程中，MDN 是同步发送的。 MDN 是通过与双向接收端口关联的发送端口发送的。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为 HTTP 响应为 HTTP POST 或消息正文，在相同的 TCP/IP 连接到 HTTPS 响应发送 MDN。 MDN 包含在 HTTP 响应命令的消息正文中。  
  
 如果 MDN 是异步发送的，则 MDN 必须通过另外的发送端口发送，此发送端口从 MessageBox 提取 MDN。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为一个单独的 HTTP Post 提供唯一的 TCP/IP 连接不同于用于提供原始 AS2 消息发送 MDN。 即使此 MDN 设置为单独的 HTTP POST，此 POST 仍需要 HTTP 响应命令。  
  
 异步 MDN 通常会发送到原始 AS2 消息的回执送达选项标头中的 URL。 但是，如果**使用验证和 MDN 的协议设置，而不是消息标头**上设置属性上**验证**页中的单向 AS2 协议选项卡**协议属性**对话框中，将 MDN 将发送到的 URL，**回执送达选项 (URL)** 协议属性设置为。  
  
## <a name="how-the-send-pipeline-processes-an-outgoing-mdn"></a>发送管道如何处理传出的 MDN  
 AS2Send 管道按如下方式处理传出的 MDN：  
  
-   执行 MIME 处理，其中包括应用数字签名（如果在 AS2 单向协议属性中启用了相应选项）。  
  
-   在不可否认数据库（BizTalkDTADb 数据库的 EdiMessageContent 表）中创建关联条目。  
  
-   （在连网格式） 将 MDN 的副本，并将其存储在不可否认性数据库中，如果在中启用**为出站的 MDN 启用 NRR**协议属性。  
  
-   将 MDN 传递到 HTTP 适配器。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 发送组件](../core/as2-send-components.md)