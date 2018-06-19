---
title: AS2 处理的已知问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 941111d8-b394-4648-a675-e4a8f118a84b
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61ce04c572c95a1a4e2433d6b046028468eca805
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009390"
---
# <a name="known-issues-with-as2-processing"></a>AS2 处理的已知问题
本部分包含主题描述了与 BizTalk Server AS2 解决方案的已知的问题。  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a>64 位计算机上不支持 AS2 处理。  
 BizTalk Server AS2 解决方案不支持在 64 位计算机上。 AS2 处理只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a>AS2 接收管道要求用于运行 BizTalk 独立主机实例进程的帐户应是 BizTalk Application Users 组的成员。  
 如果使用 AS2EdiReceive 或 AS2Receive 管道，则必须将运行 BizTalk 独立主机实例进程的用户帐户添加到 BizTalk Application Users 组中。 AS2EdiReceive 和 AS2Receive 管道在 BizTalk 独立主机实例进程中执行。  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a>Receipt-Delivery-Option 标头为空时将会导致同步发送 MDN  
 如果 AS2Receive 管道接收一条其 receipt-delivery-option 标头为空的消息，并请求异步 MDN，则该管道将忽略异步 MDN 请求。 相反，该管道将发送回一个同步 MDN，并且将在事件日志和 AS2 状态报告（如果已启用）中报告错误。 如果未选择“替代入站消息属性”属性，则发生此错误。 如果已选择该属性，则它将会使用“AS2 属性”对话框中“作为 AS2 消息发送方的参与方”页中的 Receipt-Delivery-Option 属性值替代消息中的 Receipt-Delivery-Option 标头。  
  
 在这种情况下，由于 receipt-delivery-option 标头为空，因此 AS2Receive 管道没有用来接收通过异步连接发送的 MDN 响应的目标地址。 然而，该管道仍然具有一个打开的同步连接，因此它会将 MDN 通过该连接发送回去。 如果它是一个单向接收端口，则 BizTalk Server 将在发送 HTTP 200OK 消息之后关闭连接。  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a>使用展开和折叠的 HTTP 行标头  
 为了实现最大的互操作性，您应当为 AS2 消息使用展开的 HTTP 行标头。 信息服务 (IIS) 7.0 仅支持展开的 HTTP 标头。 IIS 6.0 支持折叠和展开的标头。 然而，并非所有系统都支持每行超过 80 个字符的标头，因此对于此类系统，应使用折叠行。  
  
 BizTalk Server 中的 AS2 的默认值为展开的 HTTP 行标头。  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a>参与方解析可能会受到本地化名称的影响  
 在 BizTalk Server 对出站 AS2 消息执行参与方解析时，参与方解析可能会受到消息标头中本地化值的影响。 如果“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页中的 AS2-To 参与方属性默认设置为英文参与方名称，而 AS2 消息的 AS2-To 标头中的相应值设置为非英文名称，那么将找不到匹配项。  
  
## <a name="as2-message-size-limitation"></a>AS2 消息大小限制  
 加密的 AS2 消息应小于 96 MB，以便进行处理。 该限制是由 AS2 解码器规定的，AS2 解码器是 AS2Receive 和 AS2EdiReceive 管道的一部分。  
  
 解决此大小限制的一种方法是使用压缩，因为 AS2 消息会在加密之前进行压缩。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>不得修改 BizTalk EDI 应用程序  
 不得修改或删除 BizTalk EDI 应用程序中的项目。 如果修改了此应用程序，则您将无法通过取消配置和重新配置 EDI 及 AS2 功能来恢复原始应用程序。  
  
## <a name="partner-may-reject-multipart-messages"></a>合作伙伴可能会拒绝多部分消息  
 **症状**  
  
 当使用 AS2 发送管道发送多部分消息时，您的合作伙伴可能会因缺少内容类型 MIME 标头而拒绝该消息。  
  
 **可能的原因**  
  
 内容类型是一种可选的标头，在多部分消息中的各正文部分都可能存在该标头。 一些合作伙伴要求各正文部分都使用此标头，并将其设置为特定的内容类型。  
  
> [!NOTE]
>  消息的正文使用 AS2 发送管道设置内容类型的属性，但任何附件都不会设置内容类型属性。  
  
 **解决方法**  
  
 如果您的合作伙伴要求各正文部分都使用内容类型标头值，则您必须创建一个设置此属性的自定义管道组件，并在发送管道中使用该组件。  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a>当接收多部分消息时，将第一部分视为正文  
 **症状**  
  
 当接收多部分 AS2 消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可能会错误地将其中一个附件标识为消息正文。  
  
 **可能的原因**  
  
 多部分/相关消息的 MIME 标头可能包含一个可选的“start”参数，该参数通过指定某个部分的 Content-ID 指示应将该部分视为消息正文。 如果 start 参数不存在，消息的正文应考虑的第一部分。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果它存在，并且将始终被视为第一部分消息的正文，则不会遵循 start 参数。  
  
 **解决方法**  
  
 如果您的合作伙伴无法将正文作为多部分/相关消息的第一部分发送，则您必须创建一个正确标识消息正文的管道组件。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [AS2 解决方案体系结构](../core/as2-solution-architecture.md)   
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)