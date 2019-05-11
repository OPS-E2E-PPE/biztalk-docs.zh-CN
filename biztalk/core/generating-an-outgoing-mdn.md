---
title: 生成传出 MDN |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12d7da1c-0d3c-42d4-9388-29f499353d13
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a002383265b0b8d4001c89f61131c6749668cdd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345221"
---
# <a name="generating-an-outgoing-mdn"></a>生成传出 MDN
AS2 接收管道生成的传入消息的 MDN （消息处置通知） 响应。 执行此操作由 EDI 拆装器管道组件在 AS2EDIReceive 接收管道 （响应 EDI 编码消息） 或 AS2 拆装器管道组件在 AS2Receive 接收管道 （为了响应非 EDI 编码的消息）。  
  
## <a name="when-and-how-an-mdn-is-generated"></a>何时以及如何生成 MDN  
 MDN 是通常情况下生成基于原始 AS2 消息中的 AS2 标头，如下所示：  
  
- 如果 AS2 消息中存在的处置通知的标题，将发送一个 MDN。  
  
- 如果消息中存在的处置通知-标题和回执送达选项标头时，将以异步方式发送 MDN。 通过不同于原始消息的连接，将向回执送达选项标头中的 URL 发送它。  
  
- 如果的处置通知的标题在消息中，存在但回执送达选项标头不存在消息中，MDN 将通过原始消息的同一连接同步发送。  
  
  拆装器创建 AS2-From 标头中的 AS2 MDN 中-中收到的 AS2 消息，和它的标头创建 AS2-到 MDN 中的标头中的 AS2-从标头中所接收 AS2 消息。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以重写这些设置，指定是否将生成一个 MDN 以及生成方式基于参与方的 AS2 协议属性。 重写在消息中使用的 AS2 标头设置**使用的验证和 MDN 的协议设置而非消息标头**属性中的单向 AS2 协议选项卡**协议属性**对话框。 此属性可以发送一个 MDN，即使在 AS2 标头不会调用其中一个，或 AS2 标头指定同步连接时以异步方式发送 MDN。  
  
  如果您设置**使用的验证和 MDN 的协议设置而非消息标头**属性中中的值**请求 MDN**一部分**发送方 MDN 设置**页中的单向 AS2 协议选项卡**协议属性**对话框将用于该 MDN，按如下所示：  
  
- 如果将发送一个 MDN**请求 MDN**选择属性。  
  
- 如果**请求 MDN**选择属性，并**请求异步 MDN**选择属性，将以异步方式发送 MDN。 MDN 将发送到的 URL，**回执送达选项 (URL)** 属性设置为，通过不同于原始消息的连接。  
  
- 如果**请求 MDN**选择属性，但**请求异步 MDN**未选择属性，将通过原始消息的同一连接同步发送 MDN。  
  
  如果**使用的验证和 MDN 的协议设置而非消息标头**设置属性，将 AS2-从消息中的属性标头将用来生成 MDN，但 AS2-到来自协议属性中，和管道将对根据 MDN**请求经过签名的 MDN**属性。 AS2 标头与相对应的协议属性，如下所示：  
  
|协议属性|消息中的 AS2 标头|  
|------------------------|-------------------------------|  
|生成 MDN|处置-到通知|  
|对 MDN 签名|Signed-Receipt-Protocol|  
|Receipt-Delivery-Option|Receipt-Delivery-Option|  
  
 如果启用了 MDN，接收管道将升级下列上下文属性：  
  
- `EdiIntAS.DispositionMode`  
  
- `EdiIntAS.DispositionType`  
  
  为了使若要生成 MDN，必须升级两个上下文属性。 有关这些上下文属性的详细信息，请参阅[AS2 上下文属性](../core/as2-context-properties.md)。  
  
  如果配置设置和传入消息中的标头不一致，则管道将生成一个负值 MDN。  
  
  如果在协议属性中请求 MDN，接收管道将尝试发送一个 MDN，即使在 AS2 处理中发生错误。  
  
## <a name="how-the-receive-pipeline-processes-a-generated-mdn"></a>接收管道如何处理生成的 MDN  
 如果 MDN 生成根据上述规则，则 AS2EDIReceive 或 AS2Receive 接收管道将按如下所示处理 MDN:  
  
-   创建 MDN 的副本 （以传输格式），并将其存储在不可否认数据库中，如果在单向 AS2 协议属性中启用。  
  
-   执行 MIME 处理，其中包括应用数字签名，如果在单向 AS2 协议属性中启用。  
  
-   计算的 AS2 消息负载的 MIC （消息完整性检查），并将其追加到 MDN 的接收时间内容 MIC 扩展字段。 要应用的传入消息的签名回执 micalg 标头决定 MIC 的算法或**签名算法**上的属性**发送方 MDN 设置**页的单向协议选项卡**协议属性**（当替代入站的消息属性） 对话框。 它可以是 SHA1 或 MD5。 算法的值也包括在 MDN。  
  
-   不可否认数据库中创建相关条目。  
  
-   生成 MDN 消息的副本。  
  
-   如果 MDN 是同步传输，管道设置`EdiIntAS.IsAS2AsynchronousMDN`属性设置为 False; 如果以异步方式，它将属性设置为 True。  
  
-   如果 MDN 是同步传输，AS2Send 发送管道关联与双向接收端口将提取 MDN 基于`EdiIntAS.IsAS2AsynchronousMDN`属性 （设置为 False） 和相关标记。  
  
    > [!NOTE]
    >  此外可以设置用于订阅传出同步 mdn 的发送端口。 若要执行此操作，设置发送端口筛选器为`EdiIntAS.IsAS2MdnResponseMessage==True`。  
  
-   如果异步传输 MDN，接收管道会将 MDN 路由到 MessageBox 中。 必须设置发送端口以订阅 mdn，发送端口筛选器设置为`IsAS2AsynchronousMdn==True`。 AS2Send 发送管道将基于该属性和相关标记该消息。 如果发送端口是动态的它将基于为消息标头中的回执送达通知行中的地址将 MDN 路由。 如果发送端口是静态的它会根据发送端口的传输 URI 属性将消息路由。  
  
## <a name="mdn-generation-rules"></a>MDN 生成规则  
 以下规则适用于生成 MDN:  
  
-   当消息发送方特别请求签名的回执，但在处理消息的内容存在错误时，消息接收方仍必须返回签名的回执，即使事务自身可能无效。 必须在"处理的字段"设置中处理消息的内容的错误的原因。  
  
-   如果 MDN 回执请求显式指定的回执进行签名，但原始消息的接收方无法支持请求的协议格式或请求的 MIC 算法，则是已签名或未签名回执应为返回。  
  
-   如果未显式请求签名，或如果接收方的协议无法识别签名的回执请求参数，然后接收方可能会返回未签名的回执、 签名的回执或无回执。  
  
## <a name="mic-generation"></a>MIC 生成  
 需要 MDN 时，原始消息的接收方将生成一个 MIC （消息完整性检查），并将其添加到该 MDN。 多部分 MIME 内容类型的一部分的 EDI 交换时，必须在整个多部分内容，包括 EDI 交换和 MIME 标头计算 MIC。 对于加密，未签名的消息，要返回的 MIC 计算的解密 MIME 标头和内容。 对于未签名的、 未加密的消息，必须不带 MIME 标头的消息内容计算 MIC。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)