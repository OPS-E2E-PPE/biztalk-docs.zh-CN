---
title: MDN 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16ac6253-0be5-4636-b102-bf5af8956261
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c716d1f756f078095c19ac3d3e151c84b0e2a4be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970110"
---
# <a name="mdn-messages"></a>MDN 消息
消息处置通知 (MDN) 用于确认已发送 AS2 消息。 如果启用了 MDN，则 AS2 传输直到接收并验证 MDN 后才完成。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将始终尝试返回一个 MDN 以指示消息处理的状态，即使在处理 AS2 消息时出错。  
  
 MDN 用于确认以下过程：  
  
-   **原始消息已成功接收到接收方**。 原始消息的发送方通过比较已发送原始消息的 MessageID 与接收方包括在 MDN 中的 original-message-id 字段来验证这一点。  
  
-   **接收方已验证交换的数据的完整性**。 原始消息的发件人来验证这一点将原始发送的消息有效负载，接收方收到的消息有效负载计算以及 （如果 MDN 的接收时间内容 MIC 字段中包含的 mic 计算的 MIC 进行比较有符号）。  
  
-   **是否存在的不可否认的回执**。 发件人执行此方法是使用接收方的公钥，验证已签名的 MDN，并通过验证返回的 MIC 值在 MDN 中的原始消息负载的 MIC 相同存储在不可否认数据库中。  
  
    > [!NOTE]
    >  同步 MDN 可用作 HTTP 响应，例如：200 OK。  
  
    > [!NOTE]
    >  有关 Mdn 的接收方处理的详细信息，请参阅[处理传入 MDN](../core/processing-an-incoming-mdn.md)。 有关 Mdn 的发送端处理的详细信息，请参阅[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。  
  
## <a name="properties-used-to-generate-the-mdn"></a>用于生成 MDN 的属性  
 AS2Receive 接收管道将生成 MDN 使用参与方的 AS2 协议属性，如果**使用的验证和 MDN 的协议设置而非消息标头**中的单向协议选项卡上选择属性**协议属性**对话框。 在此情况下，AS2-从消息中的属性标头将用于生成 MDN，但其他属性将被从参与方的 AS2 协议设置。  
  
 如果未选择的选项来覆盖 AS2 属性，或者参与方的 AS2 协议可用，则接收管道将生成 MDN 的 AS2 标头标记使用传入消息中。  
  
 MDN 可进行签名，但不能加密或压缩。  
  
## <a name="mdn-context-properties"></a>MDN 上下文属性  
 处理 MDN 消息时使用的上下文属性包括可以升级的属性以及未公开但可以在已挂起和跟踪的消息中查看的属性。 有关这些上下文属性的列表，请参阅[AS2 上下文属性](../core/as2-context-properties.md)。  
  
 若要生成 MDN，必须同时升级 DispositionMode 和 DispositionType 上下文属性。 如果在 AS2 或 EDI 负载中出现错误，则 DispositionType 属性将指示出该错误。 可以看到在此属性**消息的详细信息**中的挂起服务实例 （通过服务详细信息对话框中） 显示的对话框**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 如果在标题中，出现错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将指示错误在 DispositionType 属性中，并将尝试发送该 MDN，但根据具体的错误，可能无法再执行此操作。  
  
## <a name="mdn-headers"></a>MDN 标头  
 MDN 包含下列标头：  
  
- **HTTP/AS2 标头**。 有关详细信息，请参阅[AS2 消息](../core/as2-messages.md)。  
  
- **传输层**。 这包括内容类型标头，其中包括签名的多部分消息、MIC 的算法、签名格式化协议以及最外面的多部分边界子标头。  
  
- **第一部分**。 多部分签名消息的第一部分是嵌入式 MDN。 它是人工可读取的。  
  
- **第 2 个部分**。 多部分签名消息的第二部分包含数字签名、原始消息的引用、处置类型和状态、MIC 值。 它是机器可读取的。  
  
  AS2-From 标头、AS2-To 标头和 MessageID 上下文属性用于将 MDN 与其要做出响应的 AS2 消息相关联。 MDN 中的 Original-Message-ID 标头来自 MDN 所响应的 AS2 消息的 Message-ID 标头。  
  
## <a name="mic"></a>MIC  
 消息完整性检查 (MIC) 用于验证 MDN 关联到原始发送的消息有效负载。 MIC 摘要包括在多部分签名 MDN 消息的第二部分中的 Received-Content-MIC 扩展字段中。  
  
 如果已启用 MDN，则当 AS2 发送管道处理出站消息时，它将通过相应的消息负载计算 MICHashValue。 该发送管道在 BizTalkMsgBoxDb 数据库的 EdiInt_Mic 表中保存哈希值。 系统在此表中跟踪 AS2 消息，并使用 AS2From、AS2To 和 MessageID 值和伴随的 MICHashValue 列唯一标识这些消息。 消息的接收方在处理消息负载时计算 MIC 哈希值，并在它返回的 MDN 中包括该哈希值。 原始消息的发送方将把它接收的 MDN 中的 MIC 哈希值与它所保存的哈希值相比较。 如果这两个值相匹配，则处置 MDN、删除 EdiInt_Mic 表中的条目，传输将完成。  
  
 MIC 是 base64 编码的。 对 MIC 可使用 SHA1 或 MD5 算法。 它由**签名算法**下拉列表 (才启用**请求经过签名的 MDN**属性为选中状态) 中**发送方 MDN 设置**单向协议的页在选项卡**协议属性**对话框。 也可通过原始消息的 Signed-Receipt-MICalg AS2 标头来确定。  
  
## <a name="see-also"></a>请参阅  
 [AS2 消息](../core/as2-messages.md)   
 [处理传入 MDN](../core/processing-an-incoming-mdn.md)   
 [发送传出 MDN](../core/sending-an-outgoing-mdn.md)