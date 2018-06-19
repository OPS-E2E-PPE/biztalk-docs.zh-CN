---
title: 接收方处理的传入非 EDI 消息通过 AS2 |Microsoft 文档
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
ms.openlocfilehash: 7a313c7351f40ba3dbdaf33d15008598dac2ad73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269445"
---
# <a name="receive-side-processing-of-an-incoming-non-edi-message-over-as2"></a>通过 AS2 传入的非 EDI 消息的接收方处理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 随附的 AS2 管道可用于处理通过 AS2 传输发送的 EDI 消息或非 EDI 消息。 不同的管道可用于两种不同类型的负载。 使用 AS2EdiReceive 管道处理通过 AS2 传入的 EDI 消息，使用 AS2Send 管道返回关联的 MDN（如果已启用）。 使用 AS2Receive 管道处理通过 AS2 传入的非 EDI 消息，使用 AS2Send 管道返回关联的 MDN（如果已启用）。 非 EDI 消息可以是任何二进制负载。  
  
 AS2Receive 接收管道对 AS2 消息进行解码，然后对 AS2 消息执行拆装。 AS2Send 发送管道对 MDN 进行编码。 可以将 AS2Receive 和 AS2Send 管道包含在一个 HTTP 双向要求响应发送端口中（如果 MDN 是同步的），或者包含在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口中（如果 MDN 是异步的）。 如果需要对非 EDI 负载执行拆卸，则必须在其他接收管道中执行此操作，因为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在接收管道中仅允许使用一个拆装器。 这将需要环回发送端口和接收位置 (请参阅[处理接收非 EDI 负载](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI)下面一节)。  
  
 若要通过 AS2 接收非 EDI 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将执行以下步骤：  
  
-   处理收到的 AS2 消息  
  
-   发送一个 MDN  
  
-   处理收到的非 EDI 负载  
  
## <a name="processing-the-received-as2-message"></a>处理接收 AS2 消息  
 AS2Receive 接收管道中的 AS2 解码器处理传入的 AS2 消息。 它都使用`InboundHTTPHeaders`HTTP 适配器创建为 AS2 消息中的 HTTP 标头的上下文属性。 这些标头包括下列 AS2 标头：  
  
-   AS2-To  
  
-   AS2-From  
  
-   AS2-Version  
  
-   MessageID  
  
-   OriginalMessageID（仅限 MDN）  
  
-   Disposition-Notification-To（如果请求一个 MDN）  
  
-   Receipt-Delivery-Option（如果请求一个 MDN）  
  
-   Signed-Receipt-MICalg（如果请求一个 MDN）  
  
 AS2 解码器将把这些标头升级到消息的上下文。 随后将执行以下操作：  
  
-   执行协议解析，以确定要用于处理传入消息的属性。 有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)。  
  
-   使用 AS2-From 和 AS2-To 属性验证发送方。  
  
    > [!NOTE]
    >  有关处理的详细信息的 AS2 接收管道执行对传入的 AS2 消息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  
  
## <a name="sending-an-mdn"></a>发送一个 MDN  
 如果已启用 MDN，则 AS2Receive 管道将生成一个 MDN 并将其放入 MessageBox 中。 MDN 返回给原始消息的发送方的方式取决于 AS2 传输是同步传输还是异步传输。  
  
> [!NOTE]
>  有关处理的详细信息的 AS2 接收管道中在传出 Mdn 上各项中执行，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。  
  
 **同步模式**  
  
 如果非 EDI 消息是通过 AS2 以同步模式发送的，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将通过该同步连接返回 MDN，然后关闭该连接。 MDN 将由 AS2Receive 管道生成，并由该管道路由到 MessageBox，然后由作为请求响应接收端口一部分的 AS2Send 管道自动提取。  
  
 **异步模式**  
  
 如果非 EDI 消息是通过 HTTP/HTTPS 传输以异步模式发送的，则必须创建一个发送端口以单独返回 MDN。 如果它是一个动态发送端口，则将使用消息标头中 Receipt-Delivery-Notification 行中的地址将该消息路由到贸易合作伙伴。 如果它是一个静态发送端口，则它将使用在端口属性中定义的地址。 此发送端口使用 `EdiIntAS.IsAS2AsynchronousMDN==True` 筛选器表达式订阅异步 MDN。 在异步处理过程中，AS2Receive 除生成 MDN 之外，还将生成一个 HTTP 响应。 接收端口通过接收端口和发送方之间的 HTTP 连接对原始发送方返回 HTTP 响应，这将关闭该连接。 这是必要的，因为 MDN 不会关闭同步连接。  
  
##  <a name="BKMK_NonEDI"></a>处理接收非 EDI 负载  
 通过 AS2 接收非 EDI 编码的消息时，您需要对该负载执行拆装，并且必须在 AS2Receive 管道以外的其他接收管道中执行拆装。 这是必需的，因为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在接收管道中仅允许一个拆装器。 此方案将需要一个使用发送端口和接收位置的环回机制。 在第一次传递中，EDIReceive 管道处理 AS2 消息并以其本机格式将消息发送至 MessageBox。 在第二次传递中，接收管道采用消息的本机格式生成 XML。  
  
 BizTalk Server 将通过 AS2 BizTalk Server 对非 EDI 消息执行以下接收方处理：  
  
-   与双向请求响应接收位置关联的 AS2Receive 接收管道解析非 EDI 消息中的 AS2 标头，然后将该非 EDI 消息路由至 BizTalk MessageBox。  
  
-   环回发送端口（FILE 或 MSMQ）从 MessageBox 中提取该非 EDI 消息，因为它依据 BizTalk 属性 `IsAS2PayloadMessage == True` 执行筛选。 与此发送端口关联的 PassThruTransmit 发送管道以非 EDI 格式传递该消息，从而将该消息路由至一个文件夹或一个 MSMQ 队列。  
  
-   环回接收位置提取该消息。 与环回接收位置关联的接收管道根据该非 EDI 消息生成一个 XML 消息，并将其路由至 MessageBox。  
  
-   如果该消息将被路由到后端应用程序，则发送端口将提取该 XML 消息并将其路由到应用程序。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 接收 AS2 消息的方式](../core/how-biztalk-server-receives-as2-messages.md)   
 [通过 AS2 传出 EDI 消息的发送端处理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)