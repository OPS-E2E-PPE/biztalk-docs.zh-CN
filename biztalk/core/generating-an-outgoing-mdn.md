---
title: 生成传出 MDN |Microsoft 文档
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
ms.openlocfilehash: a903cc72a41362f6843449a4d635878706f2ea1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247949"
---
# <a name="generating-an-outgoing-mdn"></a>生成传出 MDN
AS2 接收管道会对传入消息生成一个 MDN（消息处置通知）响应。 这是由 AS2EDIReceive 接收管道（响应 EDI 编码的消息）中的 EDI 拆装器管道组件或 AS2Receive 接收管道中的 AS2 拆装器管道组件（响应非 EDI 编码的消息）执行的。  
  
## <a name="when-and-how-an-mdn-is-generated"></a>何时以及如何生成 MDN  
 MDN 一般基于原始 AS2 消息中的 AS2 标头生成，如下所述：  
  
-   如果 AS2 消息中具有 Disposition-Notification-To 标头，则将发送 MDN。  
  
-   如果消息中具有 Disposition-Notification-To 和 Receipt-Delivery-Option 标头，则将异步发送 MDN。 通过不同于原始消息所用连接的其他连接将它发送到 Receipt-Delivery-Option 标头中的 URL。  
  
-   如果消息中具有 Disposition-Notification-To 标头，但不存在 Receipt-Delivery-Option 标头，则将通过原始消息所用同一连接同步发送 MDN。  
  
 拆装器将从接收到的 AS2 消息中的 AS2-To 标头创建 MDN 中的 AS2-From 标头，并从接收到的 AS2 消息中的 AS2-From 标头创建 MDN 中的 AS2-To 标头。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使你可以覆盖这些设置，指定是否将生成 MDN 并将如何生成基于参与方的 AS2 协议属性。 重写在消息中使用的 AS2 标头设置**使用验证和 MDN 的协议设置，而不是消息标头**的单向 AS2 协议选项卡中的属性**协议属性**对话框。 通过“替代入站消息属性”，您甚至可在 AS2 标头没有要求 MDN 时也发送 MDN；或者在 AS2 标头指定同步连接时通过异步方式发送 MDN。  
  
 如果你设置**使用验证和 MDN 的协议设置，而不是消息标头**属性、 中的值**请求 MDN**部分**发件人 MDN 设置**页在单向 AS2 协议选项卡中的**协议属性**对话框中将用于将 MDN，如下所示：  
  
-   如果，则会发送 MDN**请求 MDN**选择属性。  
  
-   如果**请求 MDN**选定属性，则与**请求异步 MDN**选择属性，则会以异步方式发送 MDN。 MDN 将发送到的 URL，**回执送达选项 (URL)** 属性设置为中，通过不同连接比原始消息。  
  
-   如果**请求 MDN**选择属性，但**请求异步 MDN**不选择属性后，将通过作为原始消息的相同连接以同步方式发送 MDN。  
  
 如果**使用验证和 MDN 的协议设置，而不是消息标头**设置属性，AS2-从消息中的属性标头将用来生成 MDN，但 AS2-到将被从协议属性和管道会对签名根据 MDN**请求签名的 MDN**属性。 AS2 标头对应于协议属性，如下所示：  
  
|协议属性|消息中的 AS2 标头|  
|------------------------|-------------------------------|  
|生成 MDN|Disposition-Notification-To|  
|对 MDN 签名|Signed-Receipt-Protocol|  
|Receipt-Delivery-Option|Receipt-Delivery-Option|  
  
 如果已启用 MDN，接收管道将升级下列上下文属性：  
  
-   `EdiIntAS.DispositionMode`  
  
-   `EdiIntAS.DispositionType`  
  
 若要生成 MDN，必须同时升级这两个上下文属性。 有关这些上下文属性的详细信息，请参阅[AS2 上下文属性](../core/as2-context-properties.md)。  
  
 如果传入消息中的配置设置和标头不一致，则管道将生成一个负值 MDN。  
  
 如果在协议属性中请求 MDN，则即使在 AS2 处理过程中出现错误，接收管道也会尝试发送一个 MDN。  
  
## <a name="how-the-receive-pipeline-processes-a-generated-mdn"></a>接收管道如何处理生成的 MDN  
 如果是根据上述规则生成的 MDN，则 AS2EDIReceive 或 AS2Receive 接收管道将按如下所述处理 MDN：  
  
-   创建 MDN 的副本（以传输格式）并将其存储在不可否认数据库中（如果在单向 AS2 协议属性中启用了相应选项）。  
  
-   执行 MIME 处理，其中包括应用数字签名（如果在单向 AS2 协议属性中启用了相应选项）。  
  
-   计算 MIC AS2 消息负载 （消息完整性检查），并将其追加到 MDN 的接收时间内容 MIC 扩展字段。 要应用的 MIC 由传入的消息的签名回执 micalg 标头的算法或**签名算法**属性**发件人 MDN 设置**的单向页协议选项卡**协议属性**（时的入站的消息属性被重写） 的对话框。 它可以是 SHA1 或 MD5。 该算法的值还包含在 MDN 中。  
  
-   在不可否认数据库中创建相关条目。  
  
-   创建 MDN 消息的副本。  
  
-   如果要以同步方式传输 MDN，管道将设置`EdiIntAS.IsAS2AsynchronousMDN`属性设置为 False; 如果以异步方式，它将属性设置为 True。  
  
-   与双向关联 AS2Send 发送管道 MDN 是以同步方式传输，如果接收的端口会选取基于 MDN`EdiIntAS.IsAS2AsynchronousMDN`属性 （设置为 False） 和相关令牌。  
  
    > [!NOTE]
    >  您还可设置用于订阅传出同步 MDN 的发送端口。 要执行此操作，请将发送端口筛选器设置为`EdiIntAS.IsAS2MdnResponseMessage==True`。  
  
-   如果异步传输该 MDN，则接收管道将把该 MDN 路由到 MessageBox。 你必须设置发送端口以订阅 MDN，将发送端口筛选器设置为`IsAS2AsynchronousMdn==True`。 AS2Send 发送管道将基于该属性和相关标记提取消息。 如果发送端口是动态的，它将基于消息标头的 Receipt-Delivery-Notification 行中的地址路由该 MDN。 如果发送端口是静态的它将基于发送端口的传输 URI 属性将消息进行路由。  
  
## <a name="mdn-generation-rules"></a>MDN 生成规则  
 生成 MDN 时将应用以下规则：  
  
-   当消息发送方特别请求签名回执，但处理该消息的内容过程中出现错误时，消息接收方仍必须返回签名回执，即使事务自身可能无效。 处理消息内容时的出错原因必须在“disposition-field”中进行设置。  
  
-   请求 MDN 回执时，如果显式指定应对该回执签名，但原始消息的接收方无法支持请求的协议格式或请求的 MIC 算法，则应返回签名或未签名的回执。  
  
-   如果未显式请求签名，或者，如果接收方的协议无法识别签名回执请求参数，则接收方可能会返回未签名回执、签名回执或无回执。  
  
## <a name="mic-generation"></a>MIC 生成  
 需要一个 MDN 时，原始消息的接收方将生成一个 MIC（消息完整性检查）并将其添加到该 MDN。 当 EDI 交换是多部分 MIME 内容类型的一部分时，必须在整个多部分内容（包括 EDI 交换和 MIME 标头）中计算该 MIC。 对于已加密但未签名的消息，将返回的 MIC 是根据已解密的 MIME 标头和内容计算出来的。 对于未签名且未加密的消息，必须根据无 MIME 标头的消息内容计算该 MIC。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 接收 AS2 消息的方式](../core/how-biztalk-server-receives-as2-messages.md)