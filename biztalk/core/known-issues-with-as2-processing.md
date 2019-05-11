---
title: 有关 AS2 处理的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 389184d177fe1b192db22660bdf382a6e64f37bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329372"
---
# <a name="known-issues-with-as2-processing"></a>AS2 处理的已知的问题
本部分包含介绍了 BizTalk Server AS2 解决方案的已知的问题的主题。  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a>不支持在 64 位计算机上的 AS2 处理  
 64 位计算机上不支持 BizTalk Server AS2 解决方案。 AS2 处理只能在 32 位计算机上或在 64 位计算机上在 WOW64 仿真器下运行。  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a>AS2 接收管道要求，BizTalk 独立主机实例进程正在运行的是一部分 BizTalk Application Users 组的帐户  
 如果使用 AS2EdiReceive 或 AS2Receive 管道，则必须添加到 BizTalk Application Users 组运行 BizTalk 独立主机实例进程的用户帐户。 AS2EdiReceive 和 AS2Receive 管道在 BizTalk 独立主机实例进程中执行。  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a>回执送达选项标头为空将导致同步发送 MDN  
 如果 AS2Receive 管道接收的消息回执送达选项标头为空，并且请求异步 MDN，则该管道将忽略异步 MDN 请求。 它将发送回一个同步 MDN，并发布错误，事件日志和 AS2 状态报告 （如果已启用）。 如果未选中"替代入站的消息属性"属性，将发生这种情况。 如果已选择该属性，它将会替代的消息的参与方中的回执送达选项属性的值的回执送达选项标头作为 AS2 消息发送方的 AS2 属性对话框的页。  
  
 在此情况下，由于回执送达选项标头为空，因此 AS2Receive 管道没有要发送的 MDN 响应通过异步连接的地址。 但是，该管道仍然具有打开的同步连接，因此它将返回通过该连接发送 MDN。 如果它是一个单向接收端口，BizTalk Server 将关闭在发送 HTTP 200OK 消息之后连接。  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a>使用展开和折叠 HTTP 行标头  
 最大互操作性，应为 AS2 消息使用的 HTTP 行标的头。 信息服务 (IIS) 7.0 支持仅展开的 HTTP 标头。 IIS 6.0 支持折叠和展开的标头。 但是，不是所有系统可以都支持标头与每行，超过 80 个字符，因此对于此类系统，应使用折叠的行。  
  
 在 BizTalk Server 中 as2 默认值为 HTTP 行标的头。  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a>参与方解析可能会受到本地化名称  
 当 BizTalk Server 上的出站 AS2 消息执行参与方解析时，参与方解析可能受到消息标头中本地化的值。 如果 AS2-To 参与方的参与方中的属性，因为 AS2 消息接收方的 AS2 属性对话框的页设置为英文参与方名称，而 AS2 中的值默认情况下-To 标头的 as2 消息设置为非英文名称，则将找不到匹配项。  
  
## <a name="as2-message-size-limitation"></a>AS2 消息大小限制  
 加密的 AS2 消息应小于 96 兆字节为单位，才能进行处理。 此限制规定 AS2 解码器，它是 AS2Receive 和 AS2EdiReceive 管道的一部分。  
  
 若要解决此大小限制的一种方法是使用压缩，因为 AS2 消息进行压缩，再对其进行加密。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>不得修改 BizTalk EDI 应用程序  
 不得修改或删除 BizTalk EDI 应用程序中的项目。 如果修改此应用程序，则没有办法可以恢复到原始应用程序通过取消配置和重新配置 EDI 和 AS2 功能。  
  
## <a name="partner-may-reject-multipart-messages"></a>合作伙伴可能会拒绝多部分消息  
 **症状**  
  
 在发送多部分消息使用 AS2 发送管道时，你的合作伙伴可能会拒绝消息，因为缺少内容类型 MIME 标头。  
  
 **可能的原因**  
  
 内容类型是一个可为每个正文部分出现在多部分消息的可选标头。 一些合作伙伴要求此标头存在每个正文部分，并将设置为特定的内容类型。  
  
> [!NOTE]
>  消息的正文将拥有通过 AS2 发送管道中，设置内容类型的属性，但任何附件都不会将内容类型属性设置。  
  
 **解决方法**  
  
 如果您的合作伙伴要求各正文部分内容类型标头值，必须创建一个自定义管道组件设置此属性，并在发送管道中使用该组件。  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a>当接收多部分消息，第一部分视为正文  
 **症状**  
  
 当接收多部分 AS2 消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能错误地将其中一个附件标识为消息正文。  
  
 **可能的原因**  
  
 多部分/相关消息的 MIME 标头可能包含一个可选 start 参数，用于指示该部分应视为通过指定部件的内容 ID 的消息的正文。 如果不存在 start 参数，第一部分应被视为消息正文。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如果它存在，并且始终会将第一部分视为消息正文，则不会遵循 start 参数。  
  
 **解决方法**  
  
 如果你的合作伙伴不能发送正文作为多部分/相关消息的第一部分，则必须创建正确标识消息的正文的管道组件。  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [AS2 解决方案体系结构](../core/as2-solution-architecture.md)   
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)