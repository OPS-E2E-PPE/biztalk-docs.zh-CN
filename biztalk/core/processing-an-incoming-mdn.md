---
title: "处理传入 MDN |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e599e9ebbc7a05a466cc047d891699222c2dabac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-an-incoming-mdn"></a>处理传入 MDN
AS2 接收传入 MDN 基于为作为 AS2 消息接收方方的协议属性的管道 （AS2EDIReceive 和 AS2Receive） 过程。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动关联到传出的 AS2 消息 MDN。  
  
 每个管道执行的步骤如下所示：  
  
-   通过匹配 AS2 确定发送方-中消息的 AS2 标头值与 AS2 的值从-从列表中**标识符**的单向 AS2 协议选项卡页**协议属性**对话框。 如果未找到匹配项，则管道将中止处理并引发异常。  
  
-   将下列 AS2 属性升级到上下文中：  
  
    -   IsAS2FailedMessage  
  
    -   DispositionType  
  
    -   GenerateAsynchronous200OKOnly  
  
    -   IsAS2MdnResponseMessage  
  
    -   IsAS2MessageSigned  
  
    -   OriginalMessageId  
  
    -   ReceivedContentMic  
  
    -   DispositionMode  
  
    -   MessageId  
  
-   将 InboundHttpHeaders 属性设置为消息的所有 HTTP 标头，并将其升级到消息的上下文中。  
  
-   创建 MDN 的副本（以传输格式）并将该副本存储在不可否认数据库（BizTalkDTADb 数据库的 EdiMessageContent 表）中（如果在单向 AS2 协议属性中启用了相应选项）。  
  
-   执行 MIME 处理，其中包括验证签名（如果对 MDN 进行了签名）。  
  
-   将 MDN 中的 MIC（消息完整性检查）与 AS2Send 管道在发送原始消息时所计算的数据存储区中的 MIC 进行比较（如果适用）。 有关详细信息，请参阅[MDN 消息](../core/mdn-messages.md)。  
  
-   在不可否认数据库中创建相关条目。  
  
-   除非删除 MDN，**路由/传递到 MessageBox 处理入站的 MDN**属性在中设置**发件人 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框。  
  
-   如果**路由/传递到 MessageBox 处理入站的 MDN**属性在中设置**发件人 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框中，接收管道将 MDN 路由中通过 AS2 解码器作为传递消息的连网格式，并将它放置到 MessageBox。 传输格式的 MDN 包含所有 HTTP 标头。  
  
    > [!NOTE]
    >  可以设置发送端口以订阅已放入 MessageBox 中的收到的 MDN。 若要订阅收到的 MDN，请将发送端口筛选器设置为 `IsAS2MdnResponseMessage==True`。  
  
    > [!NOTE]
    >  如果你使用 AS2EdiReceive 管道处理收到的 MDN，不能通过设置，到 MessageBox 路由 MDN**路由/传递到 MessageBox 处理入站的 MDN**中的属性**发件人 MDN设置**的单向 AS2 协议选项卡页**协议属性**对话框。 如果尝试进行此操作，将会导致一个 EDI 错误，因为 MDN 将传递至 EDI 解码器，而 EDI 解码器无法对 MDN 进行处理。 如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此不会将其传递到 EDI 解码器。  
  
## <a name="message-integrity-check"></a>消息完整性检查  
 消息完整性检查 (MIC) 用于验证 MDN 与已发送的原始消息相关联。 AS2Send 发送管道在生成原始 AS2 消息时将计算来自消息负载的 MIC，并将该 MIC 存储在数据存储区中。 需要 MDN 时，原始消息的接收方将生成一个 MIC 并将其添加到该 MDN。 当 AS2MdnReceive 接收管道接收 MDN 时，如果需要一个经过签名的 MDN，则它会将 MDN 中的 MIC 与数据存储区中的 MIC 进行比较。  
  
 MDN 中的 MIC 与数据存储区中的 MIC 不匹配表明接收方在传输或接收消息期间发生了错误。 发生此类错误时将报告如下值：  
  
-   AS2DispositionType：失败  
  
-   AS2DispositionModifierExtensionType：错误  
  
-   AS2DispositionModifierExtensionDescription：完整性检查失败  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 接收 AS2 消息的方式](../core/how-biztalk-server-receives-as2-messages.md)   
 [MDN 消息](../core/mdn-messages.md)