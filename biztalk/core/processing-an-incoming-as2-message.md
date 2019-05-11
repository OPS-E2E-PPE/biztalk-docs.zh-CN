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
ms.openlocfilehash: 2fe8392cf09aebe3437b45b6d298a9bccfd44032
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299873"
---
# <a name="processing-an-incoming-as2-message"></a>处理传入 AS2 消息
AS2 接收通过 AS2 管道可处理传入的消息。 AS2EdiReceive 接收管道处理 EDI 编码的消息，使用 EDI 拆装器。 AS2Receive 接收管道处理非 EDI 编码的消息，使用 AS2 拆装器。 两个管道处理 AS2 消息的负载，并以不同的方式; 生成 MDN但是，这两个接收管道使用 AS2 解码器来处理 AS2 消息。  
  
 在 AS2EdiReceivePipeline 中处理带有 EDI 负载的 AS2 消息时，它将完成之前执行 EDI 处理收到的消息的 AS2 处理。 当管道生成 EDI 确认的 AS2 消息的 EDI 负载时，它必须因为由 AS2 响应关闭连接以异步方式返回 EDI 确认。  
  
## <a name="the-receive-port"></a>接收端口  
 HTTP 接收端口用于接收带有 EDI 或非 EDI 负载的 AS2 消息。 如果必须同步返回 MDN，接收端口必须是请求-响应端口。  
  
 可以同步或异步返回 MDN。 这由 AS2 消息处理设置-通知-to 标头，除非**使用的验证和 MDN 的协议设置而非消息标头**的单向AS2协议选项卡中选择属性**协议属性**对话框。 如果选择属性，则 MDN 返回的方式由**请求异步 MDN**属性中的**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框。 有关详细信息，请参阅[AS2 消息](../core/as2-messages.md)并[MDN 消息](../core/mdn-messages.md)。  
  
 如果将同步返回 MDN，MDN 通过发送端口返回双向接收位置。 此 MDN 可用作 HTTP 响应，例如，200OK 指示成功接收的消息。  
  
 如果将以异步方式返回 MDN，MDN 必须通过单独的发送端口返回。 如果使用动态发送端口，则 MDN 将发送到处理设置-通知-to 标头中包含的地址。  
  
> [!NOTE]
>  双向接收端口用于接收的 AS2 消息不应该用于接收 MDN 消息。 应接收 MDN 消息使用静态单向接收端口。 使用请求/响应接收端口以异步方式返回 MDN 将阻止 200OK 消息来响应传入 MDN，从而导致不必要的 MDN 传输返回。  
  
## <a name="how-the-as2-receive-pipelines-work"></a>AS2 接收管道的工作方式  
 AS2 接收管道的步骤执行在处理传入 AS2 消息如下所示：  
  
- 进行匹配 AS2 来确定发送参与方的消息的 AS2 头部中 AS2 的值的值从-从列表中**标识符**的单向 AS2 协议选项卡页**协议属性**对话框。 如果失败，尝试确定发送方通过匹配 AS2-From 上下文属性设置为将传入消息与参与方的名称。 如果找到匹配项，并**使用的验证和 MDN 的协议设置而非消息标头**的单向 AS2 协议选项卡中选择属性**协议属性**对话框中， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用与参与方的协议来处理 AS2 消息相关联的 AS2 属性。 如果不选择该属性，则接收管道将传入消息中使用 AS2 标头标记。 如果找不到协议，管道将中止处理，挂起消息，会引发异常。  
  
  > [!NOTE]
  >  **使用的验证和 MDN 的协议设置而非消息标头**属性允许你验证传入消息具有签名、 加密和压缩属性 (如果在指定了这些属性中的协议**验证**的单向协议选项卡)，如果不能，挂起消息并发布错误。 必须与发送参与方的协议协商这些更改。 有关详细信息请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
- 如果确定发送参与方的协议，但出现错误时接收管道尝试处理 AS2 消息，该管道将将上下文属性 MessageDestination 设置为 SuspendQueue AS2 消息。 接收管道然后将在 MessageBox 中挂起消息。 接收管道还将设置`EdiIntAS.IsAS2FailedMessage`上下文属性设为 True。 如果通过设置启用了 MDN**请求 MDN**中**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框中，管道将然后将相应的 MDN 返回给发件人。 管道将始终尝试返回 MDN，如果它请求。  
  
- 确定消息是否有重复，如果**检查重复消息**中选择选项**验证**的单向 AS2 协议选项卡页**协议属性**对话框。 重复消息检测通过匹配 AS2-From、as2-To 和以前收到的消息上的值对入站消息的消息 ID 值。 如果所有三个值匹配，接收管道将的值设置`EdiIntAs.IsAS2MessageDuplicate`上下文属性设为 true。 如果**挂起重复消息**上的选项也**验证**页上，将会挂起该消息并记录一个错误。  
  
- 如果有的话，每个附件的检索文件名，并将其升级为上下文属性。  
  
- 创建消息的副本 （以传输格式），并将该副本存储在不可否认接收数据库中，如果在单向 AS2 协议属性中启用。  
  
- 执行 MIME 处理，其中包括验证签名和解密 （基于标头标记） 的消息。  
  
- 如果它已压缩，解压缩收到的消息。  
  
- 生成 HTTP 响应，追加到 MDN 中同步请求-响应模式，或以异步模式作为独立响应发送。  
  
- 如果请求，将生成 MDN 响应。 如果，则管道将生成基于协议属性 MDN**使用的验证和 MDN 的协议设置而非消息标头**设置属性，或从上下文属性，如果未设置该属性。 如果配置设置和传入消息中的标头不一致，则管道将生成一个负值 MDN。  
  
- EDI 拆装器在 AS2EdiReceive 接收管道生成 EDI 确认，如果消息是 EDI 编码，并且已启用确认。 管道会将 EDI 确认路由到 MessageBox，动态发送端口将从其提取并以异步方式将其发送出去。 EDI 确认会始终发送以异步方式通过 AS2 传输，因为 MDN 或 HTTP 响应同步发送。  
  
- 创建 MDN 的副本并将其存储在不可否认接收数据库中，如果在单向 AS2 协议属性中启用。  
  
- 创建副本的已解码的消息，并将该副本存储在不可否认接收数据库中，如果在单向 AS2 协议属性中启用。  
  
  如果出现 AS2 错误，不进行其他处理会对收到的消息。 但是，接收管道仍将生成 MDN 响应。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)   
 [AS2 消息](../core/as2-messages.md)   
 [MDN 消息](../core/mdn-messages.md)