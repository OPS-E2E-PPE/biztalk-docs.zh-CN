---
title: 接收方处理通过 AS2 传入的 EDI 消息的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 118451ab-d847-4f87-80ab-3cf812d71ac3
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b4d582dd2a40efd08015b6039d97a7e1bfda3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398179"
---
# <a name="receive-side-processing-of-an-incoming-edi-message-over-as2"></a>通过 AS2 传入的 EDI 消息的接收方处理
通过 AS2 的 EDI 消息的接收方处理包括接收 AS2 消息、 发送一个 MDN、 处理 EDI 负载和发送 EDI 确认 （如果已启用）。  
  
 AS2EdiReceive 接收管道接收 AS2 消息和拆装 EDI 负载的 AS2 消息中。 AS2EDISend 发送管道发送一个 MDN 以响应 AS2 消息，并在响应 EDI 消息中返回 EDI 确认。 可以包含这些管道在一个 HTTP 双向要求响应发送端口 （如果 MDN 是同步的），或在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口 （如果 MDN 是异步的）。  
  
 若要通过 AS2 接收 EDI 交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行以下步骤：  
  
-   处理所接收的 AS2 消息  
  
-   发送一个 MDN  
  
-   处理收到的 EDI 负载  
  
-   发送 EDI 确认  
  
## <a name="processing-the-received-as2-message"></a>处理收到的 AS2 消息  
 AS2 解码器在 AS2EdiReceive 接收管道处理传入的 AS2 消息。 它是通过使用`InboundHTTPHeaders`HTTP 适配器创建 AS2 消息中的 HTTP 标头上下文属性。 这些标头包括下列 AS2 标头：  
  
- AS2-To  
  
- AS2-从  
  
- AS2 版本  
  
- MessageID  
  
- OriginalMessageID (仅限 Mdn)  
  
- 处理设置-通知-向 （如果请求一个 MDN）  
  
- 回执送达选项 （如果请求一个 MDN）  
  
- 签名的回执-MICalg （如果请求一个 MDN）  
  
  AS2 解码器将升级到消息上下文的这些标头。 它然后执行以下操作：  
  
- 执行协议解析，以确定要用来处理传入的消息的属性。 有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)。  
  
- 对使用发件人进行身份验证**AS2-从**属性。  
  
  > [!NOTE]
  >  AS2 接收管道处理的详细信息执行对传入的 AS2 消息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  
  
## <a name="sending-an-mdn"></a>发送一个 MDN  
 如果已启用 MDN，则 AS2EdiReceive 管道生成 MDN 并将其放入 MessageBox。  
  
> [!NOTE]
>  对传出 Mdn 执行有关 AS2 接收管道处理的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。  
  
 **同步模式**  
  
 如果在同步模式下，通过 AS2 发送 EDI 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将通过该同步连接返回 MDN，然后关闭该连接。 因为连接已关闭，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法通过该连接返回 EDI 确认 (997、 TA1 或 CONTRL)。 EDI 确认始终通过 AS2 异步发送。  
  
 MDN 将由 AS2EDIReceive 管道生成的、 由该管道路由到 MessageBox，然后自动提取请求的一部分的 AS2Send 管道响应接收端口。  
  
 **异步模式**  
  
 如果 EDIINT/AS2 编码的消息通过 HTTP/HTTPS 传输以异步模式发送的您必须创建发送端口以单独返回 MDN。 可以配置此发送端口返回异步 Mdn 和 EDI 确认。 如果它是一个动态发送端口，它将使用消息标头中的回执送达通知行中的地址将消息路由到贸易合作伙伴。 如果它是一个静态发送端口，它将使用在端口属性中配置的地址。 此发送端口使用订阅异步 MDN`EdiIntAS.IsAS2AsynchronousMDN==True`筛选表达式。  
  
 在异步处理过程，则 AS2EdiReceive 管道将生成在 MDN 之外还 HTTP 响应。 接收端口接收端口和发送方，这会关闭该连接之间通过 HTTP 连接返回到原始发送方的 HTTP 响应。 这是必需的因为 MDN 不会关闭同步连接。  
  
 如果 BizTalk 通过 HTTP/HTTPS 传输 EDIINT/AS2 编码的消息，但 EDI 编码的负载的处理失败，原始消息的发件人会收到表示成功处理了 AS2 和 EDI 确认，它指示这两个的 MDN在 EDI 处理中失败。 EDI 编码的负载将被挂起，并会发出错误。  
  
## <a name="processing-the-received-edi-payload"></a>处理收到的 EDI 负载  
 如果**入站批处理选项**对于 EDI 协议设置为**将交换拆分**，AS2EdiReceive 接收管道关联与双向请求响应接收位置分析设置 EDI 消息转换为每个 EDI 事务单独的 XML 消息。 如果**入站批处理选项**设置为**保留交换**，接收管道将不解析 EDI 消息。  
  
 接收管道将 XML 事务集或保留的 EDI 交换路由到 BizTalk MessageBox 中。  
  
 如果该消息将路由到后端应用程序，发送端口提取 XML 消息，并将其路由到该应用程序。  
  
> [!NOTE]
>  此发送端口可以是任何类型。  
  
## <a name="sending-the-edi-acknowledgment"></a>发送 EDI 确认  
 如果已启用 EDI 确认，EDI 拆装器在 AS2EdiReceive 接收管道将生成 EDI 确认 （如果启用）。 必须在单独的单向发送端口中的 AS2EdiSend 发送管道发送 EDI 确认。  
  
 如果设置了一个双向请求-响应接收端口返回同步 MDN 或 HTTP 响应 （对于异步 MDN)，将 EDI/AS2 消息**将确认路由到发送管道请求-响应接收端口**属性 (在中设置**本地主机设置**单向 EDI 协议中的页**协议属性**对话框) 将被忽略。 即使选中此属性，发送管道将返回同步 MDN 或 HTTP 响应，不是 EDI 确认。  
  
 有关详细信息，请参阅[发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)