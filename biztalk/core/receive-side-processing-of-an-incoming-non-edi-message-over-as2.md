---
title: 接收方处理通过 AS2 传入的非 EDI 消息的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee10cba-8b1a-4d2c-b9d9-efbb74c3f461
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9d37479d66001eb073cb29a47b1fb8f56b0af8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398194"
---
# <a name="receive-side-processing-of-an-incoming-non-edi-message-over-as2"></a>通过 AS2 传入的非 EDI 消息的接收方处理
AS2 管道附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用于处理通过 AS2 传输发送的 EDI 消息或非 EDI 消息。 不同的管道用于两个不同类型的有效负载。 使用 AS2EdiReceive 管道处理通过 AS2 传入的 EDI 消息和 AS2Send 管道返回关联的 MDN （如果已启用）。 使用 AS2Receive 管道处理通过 AS2 传入的非 EDI 消息和 AS2Send 管道返回关联的 MDN （如果已启用）。 非 EDI 消息可以是任何二进制负载。  
  
 AS2Receive 接收管道对 AS2 消息进行解码，然后对 AS2 消息执行拆装。 AS2Send 发送管道对 MDN 进行编码。 可以包括 AS2Receive 和 AS2Send 管道在一个 HTTP 双向要求响应发送端口 （如果 MDN 是同步的），或在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口 （如果 MDN 是异步的）。 如果需要执行的非 EDI 负载的反汇编，您将必须执行该操作在另一个接收管道中，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在接收管道中仅允许一个拆装器。 这将需要环回发送端口和接收位置 (请参阅[处理接收非 EDI 负载](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI)下面一节)。  
  
 若要通过 AS2 接收非 EDI 交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行以下步骤：  
  
-   处理所接收的 AS2 消息  
  
-   发送一个 MDN  
  
-   处理收到的非 EDI 负载  
  
## <a name="processing-the-received-as2-message"></a>处理收到的 AS2 消息  
 AS2 解码器在 AS2Receive 接收管道处理传入的 AS2 消息。 它是通过使用`InboundHTTPHeaders`HTTP 适配器创建 AS2 消息中的 HTTP 标头上下文属性。 这些标头包括下列 AS2 标头：  
  
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
  
- 使用 AS2 发送方进行身份验证-从和 AS2 的属性。  
  
  > [!NOTE]
  >  AS2 接收管道处理的详细信息执行对传入的 AS2 消息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  
  
## <a name="sending-an-mdn"></a>发送一个 MDN  
 如果已启用 MDN，则 AS2Receive 管道生成 MDN 并将其放入 MessageBox。 MDN 返回到原始消息的发件人的方式取决于 AS2 传输是同步还是异步。  
  
> [!NOTE]
>  对传出 Mdn 执行有关 AS2 接收管道处理的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。  
  
 **同步模式**  
  
 如果在同步模式下，通过 AS2 发送非 EDI 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将通过该同步连接返回 MDN，然后关闭该连接。 MDN 将由 AS2Receive 管道生成的、 由该管道路由到 MessageBox，然后自动提取请求的一部分的 AS2Send 管道响应接收端口。  
  
 **异步模式**  
  
 如果非 EDI 消息通过 HTTP/HTTPS 传输以异步模式发送的您必须创建发送端口以单独返回 MDN。 如果它是一个动态发送端口，它将使用消息标头中的回执送达通知行中的地址将消息路由到贸易合作伙伴。 如果它是一个静态发送端口，它将使用在端口属性中定义的地址。 此发送端口使用订阅异步 MDN`EdiIntAS.IsAS2AsynchronousMDN==True`筛选表达式。 在异步处理中，AS2Receive 管道将生成在 MDN 之外还 HTTP 响应。 接收端口接收端口和发送方，这会关闭该连接之间通过 HTTP 连接返回到原始发送方的 HTTP 响应。 这是必需的因为 MDN 不会关闭同步连接。  
  
##  <a name="BKMK_NonEDI"></a> 处理收到的非 EDI 负载  
 当未以 EDI 编码的消息接收通过 AS2，并且需要对负载执行拆装时，必须在 AS2Receive 管道以外的其他接收管道在执行该操作。 这是必需的因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在接收管道中仅允许一个拆装器。 这种情况下将需要环回机制使用的发送端口和接收位置。 在第一个阶段中，EDIReceive 管道处理 AS2 消息，并将消息以其本机格式发送到 MessageBox。 在第二个阶段中，接收管道生成的 XML 消息的本机格式。  
  
 BizTalk Server 将执行以下接收端处理通过 AS2 BizTalk Server 上的非 EDI 消息：  
  
-   AS2Receive 接收管道关联与双向请求响应接收位置分析从非 EDI 消息的 AS2 标头，然后将非 EDI 消息路由到 BizTalk MessageBox。  
  
-   环回发送端口 （FILE 或 MSMQ） 中提取该非 EDI 消息从 MessageBox，因为它依据 BizTalk 属性筛选`IsAS2PayloadMessage == True`。 与此发送端口关联的 PassThruTransmit 发送管道以非 EDI 格式，该消息路由到一个文件夹或一个 MSMQ 队列将消息传递。  
  
-   环回接收位置从其中提取消息。 与环回接收位置关联的接收管道生成的 XML 消息从非 EDI 消息，并将其路由到 MessageBox。  
  
-   如果该消息将路由到后端应用程序，发送端口提取 XML 消息，并将其路由到该应用程序。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)   
 [通过 AS2 传出的 EDI 消息的发送方处理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)