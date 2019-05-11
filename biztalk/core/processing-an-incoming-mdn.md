---
title: 处理传入 MDN |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d575f78d41fdf4cb6e3902354bf218579faad7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299880"
---
# <a name="processing-an-incoming-mdn"></a>处理传入 MDN
AS2 接收管道 （AS2EDIReceive 和 AS2Receive） 处理传入 MDN 基于作为 AS2 消息接收方的参与方的协议属性。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 自动将 MDN 与传出 AS2 消息相关联。  
  
 每个管道执行的步骤如下所示：  
  
-   进行匹配 AS2 来确定发送参与方的消息的 AS2 头部中 AS2 的值的值从-从列表中**标识符**的单向 AS2 协议选项卡页**协议属性**对话框。 如果找不到匹配项，管道将中止处理并引发异常。  
  
-   升级到上下文下列 AS2 属性：  
  
    -   IsAS2FailedMessage  
  
    -   DispositionType  
  
    -   GenerateAsynchronous200OKOnly  
  
    -   IsAS2MdnResponseMessage  
  
    -   IsAS2MessageSigned  
  
    -   OriginalMessageId  
  
    -   ReceivedContentMic  
  
    -   DispositionMode  
  
    -   MessageId  
  
-   将 InboundHttpHeaders 属性设置为所有 HTTP 标头的消息，并将其升级到消息的上下文。  
  
-   创建 MDN 的副本 （以传输格式），并将该副本存储在不可否认数据库 （BizTalkDTADb 数据库的 EdiMessageContent 表），如果在单向 AS2 协议属性中启用。  
  
-   执行 MIME 处理，其中包括验证签名，如果已签名 MDN。  
  
-   AS2Send 管道发送原始消息 （如果适用） 时所计算的数据存储区中的 mic MDN 中比较的 MIC （消息完整性检查）。 有关详细信息，请参阅[MDN 消息](../core/mdn-messages.md)。  
  
-   不可否认数据库中创建相关条目。  
  
-   删除 MDN，除非**到 MessageBox 中处理入站的 MDN 以进行路由/传递**属性中设置**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框。  
  
-   如果**到 MessageBox 中处理入站的 MDN 以进行路由/传递**属性中设置**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框中，接收管道将 MDN 路由以通过 AS2 解码器作为直通消息传输格式，并将其放入 MessageBox。 以传输格式的 MDN 包含所有 HTTP 标头。  
  
    > [!NOTE]
    >  可以设置发送端口以订阅收到的 MDN 放入 MessageBox。 若要订阅收到的 MDN，请将发送端口筛选器设置为`IsAS2MdnResponseMessage==True`。  
  
    > [!NOTE]
    >  如果使用 AS2EdiReceive 管道处理收到的 MDN，则不能将 MDN 路由到 MessageBox 中通过设置**到 MessageBox 中处理入站的 MDN 以进行路由/传递**属性中的**发送方 MDN设置**页的单向 AS2 协议选项卡**协议属性**对话框。 尝试进行此操作将导致一个 EDI 错误，因为 MDN 将传递至 EDI 解码器，将无法对 MDN 进行处理。 如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此它不会传递到 EDI 解码器。  
  
## <a name="message-integrity-check"></a>消息完整性检查  
 消息完整性检查 (MIC) 用于验证 MDN 关联到原始发送的消息。 AS2Send 发送管道时将计算从消息负载的 MIC 生成原始 AS2 消息，并将该 MIC 存储在数据存储区中。 需要 MDN 时，原始消息的接收方生成一个 MIC 并将其添加到该 MDN。 当 AS2MdnReceive 接收管道接收 MDN，如果已请求经过签名的 MDN，它比较 MDN 中的 mic 数据存储区中的 MIC。  
  
 MDN 中的 MIC 数据存储区中的 MIC 不匹配指示在传输或接收到消息接收方期间出现错误。 在此类故障报告的值如下所示：  
  
-   AS2DispositionType:失败  
  
-   AS2DispositionModifierExtensionType:错误  
  
-   AS2DispositionModifierExtensionDescription:完整性检查失败  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)   
 [MDN 消息](../core/mdn-messages.md)