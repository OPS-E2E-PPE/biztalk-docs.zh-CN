---
title: 对传出 AS2 消息的协议解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 578d7565-534c-4c13-b473-975f347f3a9b
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8329b2b80ca3b9bfd6b34379d936d6be1df3ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975854"
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a>对传出 AS2 消息的协议解析
当 AS2 发送管道处理通过 HTTP/HTTPS 传输传出的 EDIINT/AS2 编码的消息时，它会确定此消息将解析到的协议。 然后，它将使用这些协议属性来处理此传出消息。 发送管道将使用以下条件来确定协议（按优先顺序）：  
  
1. 发送管道将尝试将 AS2From 和 AS2To 上下文属性与指定为协议属性的一部分的 AS2From 和 AS2To 的值匹配。  
  
2. 如果在上一步失败，发送管道将尝试匹配出站消息的 AS2To 上下文属性设置为中的其他协议解析程序的 AS2To 属性的值与**标识符**协议选项卡属性。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不会将 AS2To 属性写入上下文。 如果要对 AS2To 上下文属性执行协议解析，您必须并入一个自定义业务流程或自定义管道组件来执行此解析。 有关详细信息，请参阅[写入 AS2 上下文属性进行出站参与方解析](../core/writing-as2-context-properties-for-outbound-party-resolution.md)。  
   > 
   > [!NOTE]
   >  当您使用动态发送端口时，必须将 AS2To 属性写入上下文以进行协议解析。  
  
3. 如果上一步失败，则发送管道将尝试将与协议关联的发送端口与订阅消息的发送端口匹配。 发送端口是与中的协议相关联**发送端口**页的单向 AS2 协议**协议属性**对话框。  
  
   > [!NOTE]
   >  与 EDI 处理过程不同，如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，则它没有任何可以使用的后备 AS2 属性。 但存在用于发送 MDN 的默认协议。 此外，发送端口和 Http.UserHttpHeaders 上下文属性都不用于解析 MDN 的协议。 有关详细信息，请参阅的"协议解析 MDN 的"部分[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。  
   > 
   > [!NOTE]
   >  如果 AS2-To 协议属性中**标识符**页的单向 AS2 协议的**协议属性**对话框中设置默认情况下为英文参与方名称，而值中 AS2-To 标头as2 消息设置为非英文名称，然后将找不到匹配项。  
  
> [!NOTE]
>  当通过 AS2 发送 EDI 时，您需要为 EDI 和 AS2 使用单独的协议。  
  
 有关发送过程的更多详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)