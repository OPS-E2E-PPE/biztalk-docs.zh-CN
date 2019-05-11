---
title: 发送传出的 MDN |Microsoft Docs
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
ms.openlocfilehash: 4dbe1365681fe40ef81b1634307d1535c325ad5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399054"
---
# <a name="sending-an-outgoing-mdn"></a>发送传出的 MDN
传出的 MDN 由 AS2EDIReceive 或 AS2Receive 接收管道，并由 AS2Send 管道发送。 本主题介绍如何发送 MDN。 有关如何生成 MDN 的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。  
  
> [!NOTE]
>  AS2EDISend 发送管道不用于发送传出的 MDN，因为在处理 MDN 时不使用该管道中的 EDI 组装器。  
  
## <a name="agreement-resolution-for-an-mdn"></a>MDN 的协议解析  
 MDN 是自路由。 它包含路由到目标协议所需的信息。 发送管道使用 AS2 协议属性来处理传出的 MDN。 但是，MDN 不必签订了协议，为其路由到参与方解析。  
  
 当 AS2Send 管道处理传出的 MDN 时，它使用 AS2-到消息上下文来获得用于处理此 MDN 的协议属性中的值。 这是通过匹配 AS2-To 上下文属性与 AS2-To 协议属性中**标识符**页中的单向 AS2 协议选项卡**协议属性**对话框。 如果此 mdn 的协议解析可能会失败的 AS2-到协议未设置值。 如果无法确定协议，则使用默认协议来生成 MDN。  
  
 传出的 MDN 的默认协议，在执行证书解析列表验证。 如果不希望执行此验证，确认正确的 AS2-协议属性设置为，以便能够解析接收方并且可以确定协议属性。 如果是这样，将不使用提示验证证书解析列表的默认协议。 您还需要禁用**检查证书吊销列表**上的属性**验证**中的单向 AS2 协议选项卡页**协议属性**对话框。  
  
## <a name="synchronous-and-asynchronous-transmission"></a>同步和异步传输  
 在默认 AS2 处理中，以同步方式发送 MDN。 发送 MDN 的发送端口关联与双向接收端口。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将此 MDN 作为对 HTTP POST 的 HTTP 响应或作为对 HTTPS POST，相同的 TCP/IP 连接的 HTTPS 响应。 MDN 包含在消息正文的 HTTP 响应命令。  
  
 如果以异步方式发送 MDN，MDN 必须通过单独的发送端口，从 MessageBox 提取 MDN 发送。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将此 MDN 作为单独 HTTP Post 发送唯一的 TCP/IP 连接不同于用来传递原始 AS2 消息。 即使此 MDN 设置为一个单独的 HTTP Post，一个 HTTP 响应命令，仍需要 post。  
  
 通常情况下将向原始 AS2 消息的回执送达选项标头中的 URL 发送异步 MDN。 但是，如果**使用的验证和 MDN 的协议设置而非消息标头**上设置属性上**验证**中的单向 AS2 协议选项卡页**协议属性**对话框中，MDN 将发送到的 URL，**回执送达选项 (URL)** 协议属性设置为。  
  
## <a name="how-the-send-pipeline-processes-an-outgoing-mdn"></a>发送管道如何处理传出的 MDN  
 AS2Send 管道处理传出的 MDN 如下所示：  
  
-   执行 MIME 处理，其中包括应用数字签名，如果在 AS2 单向协议属性中启用。  
  
-   不可否认数据库 （BizTalkDTADb 数据库的 EdiMessageContent 表） 中创建相关条目。  
  
-   创建 MDN 的副本 （以传输格式） 并将其存储在不可否认数据库中，如果在中启用**对出站 MDN 启用 NRR**协议属性。  
  
-   将 MDN 传递到 HTTP 适配器。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 发送组件](../core/as2-send-components.md)