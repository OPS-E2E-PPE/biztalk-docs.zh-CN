---
title: 处理传入 AS2 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 998ff334-71e2-4686-b2b7-44940a0ebed1
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03ac0dc787733461b36abcba3438a22a167b0547
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003190"
---
# <a name="processing-an-incoming-as2-message"></a>处理传入 AS2 消息
AS2 接收管道可处理通过 AS2 传入的消息。 AS2EdiReceive 接收管道使用 EDI 拆装器处理 EDI 编码的消息。 AS2Receive 接收管道使用 AS2 拆装器处理非 EDI 编码的消息。 这两个管道采用不同的方式来处理 AS2 消息负载和生成 MDN；不过，两个接收管道都使用 AS2 解码器来处理 AS2 消息。  
  
 在 AS2EdiReceive 管道处理带有 EDI 负载的传入 AS2 消息时，该管道会先完成对已接收消息的 AS2 处理，然后执行 EDI 处理。 如果该管道为 AS2 消息的 EDI 负载生成一个 EDI 确认，则它必须异步返回该 EDI 确认，因为连接已由 AS2 响应关闭。  
  
## <a name="the-receive-port"></a>接收端口  
 HTTP 接收端口用于接收带有 EDI 或非 EDI 负载的 AS2 消息。 如果必须同步返回 MDN，则接收端口必须是请求-响应端口。  
  
 可同步或异步返回 MDN。 这由 AS2 消息处理设置-通知-to 标头，除非**使用的验证和 MDN 的协议设置而非消息标头**的单向AS2协议选项卡中选择属性**协议属性**对话框。 如果选择属性，则 MDN 返回的方式由**请求异步 MDN**属性中的**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框。 有关详细信息，请参阅[AS2 消息](../core/as2-messages.md)并[MDN 消息](../core/mdn-messages.md)。  
  
 如果将同步返回 MDN，则 MDN 将通过双向接收位置的发送端口返回。 此 MDN 将用作 HTTP 响应，例如，200OK 指示成功接收消息。  
  
 如果将以异步方式返回 MDN，则 MDN 必须通过一个单独的发送端口返回。 如果使用一个动态发送端口，则 MDN 将发送到 Disposition-notification-To 标头中所包含的地址。  
  
> [!NOTE]
>  用于接收 AS2 消息的双向接收端口不得用于接收 MDN 消息， 而应使用静态单向接收端口来接收 MDN 消息。 对异步返回的 MDN 使用请求/响应接收端口将会阻止返回 200OK 消息来响应传入 MDN，从而导致不必要的 MDN 重新传输。  
  
## <a name="how-the-as2-receive-pipelines-work"></a>AS2 接收管道的工作原理  
 AS2 接收管道处理传入 AS2 消息的步骤如下：  
  
- 进行匹配 AS2 来确定发送参与方的消息的 AS2 头部中 AS2 的值的值从-从列表中**标识符**的单向 AS2 协议选项卡页**协议属性**对话框。 如果通过上述方式无法确定，则通过将为传入消息设置的 AS2-From 上下文属性与参与方的名称进行匹配来尝试确定发送参与方。 如果找到匹配项，并**使用的验证和 MDN 的协议设置而非消息标头**的单向 AS2 协议选项卡中选择属性**协议属性**对话框中， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用与参与方的协议来处理 AS2 消息相关联的 AS2 属性。 如果没有选择该属性，则接收管道将使用传入消息中的 AS2 标头标记。 如果未找到协议，则接收管道将中止处理，挂起消息并引发异常。  
  
  > [!NOTE]
  >  **使用的验证和 MDN 的协议设置而非消息标头**属性允许你验证传入消息具有签名、 加密和压缩属性 (如果在指定了这些属性中的协议**验证**的单向协议选项卡)，如果不能，挂起消息并发布错误。 必须与发送参与方的协议协商这些更改。 有关详细信息请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
- 如果发送参与方的协议已确定，但在接收管道尝试处理 AS2 消息时出现错误，则该管道会将 AS2 消息的上下文属性 MessageDestination 设置为 SuspendQueue。 然后，接收管道将挂起 MessageBox 中的消息。 接收管道还会将 `EdiIntAS.IsAS2FailedMessage` 上下文属性设置为 True。 如果通过设置启用了 MDN**请求 MDN**中**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框中，管道将然后将相应的 MDN 返回给发件人。 如果已请求 MDN，则该管道将始终尝试返回 MDN。  
  
- 确定消息是否有重复，如果**检查重复消息**中选择选项**验证**的单向 AS2 协议选项卡页**协议属性**对话框。 通过将入站消息上的 AS2-From、AS2-To 和 Message-ID 值与以前收到的消息上的值相匹配，可实现重复消息的检测。 如果所有三个值都匹配，则接收管道会将 `EdiIntAs.IsAS2MessageDuplicate` 上下文属性的值设置为 True。 如果**挂起重复消息**上的选项也**验证**页上，将会挂起该消息并记录一个错误。  
  
- 检索每个附件的文件名（如果有），并将其升级为上下文属性。  
  
- 以传输格式创建消息的副本，并将该副本存储在不可否认接收数据库中（如果在单向 AS2 协议属性中启用了相应选项）。  
  
- 执行 MIME 处理，其中包括验证签名并对消息进行解密（基于标头标记）。  
  
- 如果已接收消息是经过压缩的消息，则对其进行解压缩。  
  
- 生成 HTTP 响应，该响应将以同步请求-响应模式追加到 MDN 中，或以异步模式作为独立响应发送。  
  
- 如果需要，则生成 MDN 响应。 如果，则管道将生成基于协议属性 MDN**使用的验证和 MDN 的协议设置而非消息标头**设置属性，或从上下文属性，如果未设置该属性。 如果传入消息中的配置设置和标头不一致，则管道将生成一个负值 MDN。  
  
- 如果是 EDI 编码的消息并且已启用确认，则 AS2EdiReceive 接收管道中的 EDI 拆装器会生成 EDI 确认。 该管道会将 EDI 确认路由到 MessageBox，而动态发送端口将从 MessageBox 中提取并异步发送 EDI 确认。 EDI 确认会始终通过 AS2 传输类型异步发送，因为 MDN 或 HTTP 响应是同步发送的。  
  
- 创建 MDN 的副本，并将其存储在不可否认接收数据库中（如果在单向 AS2 协议属性中启用了相应选项）。  
  
- 创建解码后的消息的副本，并将该副本存储在不可否认接收数据库中（如果在单向 AS2 协议属性中启用了相应选项）。  
  
  如果出现 AS2 错误，则不会对接收的消息进行进一步的处理。 然而，接收管道仍将生成 MDN 响应。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)   
 [AS2 消息](../core/as2-messages.md)   
 [MDN 消息](../core/mdn-messages.md)