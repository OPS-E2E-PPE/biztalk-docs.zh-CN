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
ms.openlocfilehash: c2ac015986c78f97082321171ca2fcd01a4854e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380014"
---
# <a name="mdn-messages"></a>MDN 消息
消息处置通知 (MDN) 用于确认已发送 AS2 消息的响应中。 如果启用了 MDN，直到接收并验证 MDN 才完成 AS2 传输。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将始终尝试返回一个 MDN 以指示消息处理的状态，即使在处理 AS2 消息时出错。  
  
 MDN 用于确认以下：  
  
-   **原始消息已成功接收到接收方**。 原始消息的发件人来验证这一点比较包含在 MDN 中接收方的原始消息 id 字段的原始发送消息的 MessageID。  
  
-   **接收方已验证交换的数据的完整性**。 原始消息的发件人来验证这一点将原始发送的消息有效负载，接收方收到的消息有效负载计算以及 （如果 MDN 的接收时间内容 MIC 字段中包含的 mic 计算的 MIC 进行比较有符号）。  
  
-   **是否存在的不可否认的回执**。 发件人执行此方法是使用接收方的公钥，验证已签名的 MDN，并通过验证返回的 MIC 值在 MDN 中的原始消息负载的 MIC 相同存储在不可否认数据库中。  
  
    > [!NOTE]
    >  同步 MDN 可用作 HTTP 响应，例如，200 OK。  
  
    > [!NOTE]
    >  有关 Mdn 的接收方处理的详细信息，请参阅[处理传入 MDN](../core/processing-an-incoming-mdn.md)。 有关 Mdn 的发送端处理的详细信息，请参阅[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。  
  
## <a name="properties-used-to-generate-the-mdn"></a>用于生成 MDN 的属性  
 AS2Receive 接收管道将生成 MDN 使用参与方的 AS2 协议属性，如果**使用的验证和 MDN 的协议设置而非消息标头**中的单向协议选项卡上选择属性**协议属性**对话框。 在此情况下，AS2-从消息中的属性标头将用于生成 MDN，但其他属性将被从参与方的 AS2 协议设置。  
  
 如果未选择的选项来覆盖 AS2 属性，或者参与方的 AS2 协议可用，则接收管道将生成 MDN 的 AS2 标头标记使用传入消息中。  
  
 可以对 MDN 进行签名，但不能加密或压缩。  
  
## <a name="mdn-context-properties"></a>MDN 上下文属性  
 使用在处理 MDN 消息上下文属性包括可以升级的属性，以及未公开，但可以在已挂起和跟踪消息中查看的属性。 有关这些上下文属性的列表，请参阅[AS2 上下文属性](../core/as2-context-properties.md)。  
  
 若要生成 MDN，必须升级 DispositionMode 和 DispositionType 上下文属性。 如果在 AS2 或 EDI 负载中出错，则 DispositionType 属性将指示该错误。 可以看到在此属性**消息的详细信息**中的挂起服务实例 （通过服务详细信息对话框中） 显示的对话框**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 如果在标题中，出现错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将指示错误在 DispositionType 属性中，并将尝试发送该 MDN，但根据具体的错误，可能无法再执行此操作。  
  
## <a name="mdn-headers"></a>MDN 标头  
 MDN 包含以下标头：  
  
- **HTTP/AS2 标头**。 有关详细信息，请参阅[AS2 消息](../core/as2-messages.md)。  
  
- **传输层**。 这包括用于 MIC、 签名格式化协议和最外面的多部分边界子标头包括已签名的多部分消息，该算法的内容类型标头。  
  
- **第一部分**。 多部分签名消息的第一部分是嵌入式的 MDN。 它是人工可读。  
  
- **第 2 个部分**。 多部分签名消息的第二部分包含的数字签名、 原始消息、 处置类型和状态和 MIC 值的引用。 它是计算机可读。  
  
  AS2-From 标头、 AS2-标头和 MessageID 上下文属性用于将 MDN 所响应的 AS2 消息相关联。 MDN 中的原始消息 ID 标头来自 MDN 所响应的 AS2 消息的消息 ID 标头。  
  
## <a name="mic"></a>MIC  
 消息完整性检查 (MIC) 用于验证 MDN 关联到原始发送的消息有效负载。 MIC 摘要包括在多部分签名 MDN 消息的第二部分中的已接收内容 MIC 扩展字段。  
  
 如果启用了 MDN，当 AS2 发送管道处理出站消息时，它将计算出一个 MICHashValue 从消息负载。 发送管道在 BizTalkMsgBoxDb 数据库的 EdiInt_Mic 表中保存的哈希值。 在此表中，由 AS2From 和 AS2To，MessageID 值，并伴随的 MICHashValue 列唯一标识跟踪 AS2 消息。 消息的接收方处理消息负载，和它返回的 MDN 中包括的哈希值时计算 MIC 哈希值。 原始消息的发件人将比较接收 MDN 中的 MIC 哈希值与将其保存的哈希值。 如果它们匹配，则处置 MDN、 删除 EdiInt_Mic 表中，以及传输中的项是完成。  
  
 MIC 是 base64 编码。 要将应用于的 MIC 的算法可以是 SHA1 或 MD5。 它由**签名算法**下拉列表 (才启用**请求经过签名的 MDN**属性为选中状态) 中**发送方 MDN 设置**单向协议的页在选项卡**协议属性**对话框。 它还取决于从原始消息的 Signed-receipt-micalg 即用的 AS2 标头。  
  
## <a name="see-also"></a>请参阅  
 [AS2 消息](../core/as2-messages.md)   
 [处理传入 MDN](../core/processing-an-incoming-mdn.md)   
 [发送传出 MDN](../core/sending-an-outgoing-mdn.md)