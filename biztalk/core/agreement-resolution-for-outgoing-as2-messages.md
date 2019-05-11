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
ms.openlocfilehash: c5722e128a23e5836357ec0503a24be9676e8131
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359307"
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a>对传出 AS2 消息的协议解析
当 AS2 发送管道处理通过 HTTP/HTTPS 传输传出 EDIINT/AS2 编码的消息时，它确定消息将解析为协议。 然后，它将使用这些协议属性来处理传出消息。 发送管道将使用以下条件来确定协议 （按优先顺序）：  
  
1. 发送管道将尝试匹配的 AS2From 和 AS2To 协议属性中指定的值的 AS2From 和 AS2To 上下文属性。  
  
2. 如果在上一步失败，发送管道将尝试匹配出站消息的 AS2To 上下文属性设置为中的其他协议解析程序的 AS2To 属性的值与**标识符**协议选项卡属性。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不会将 AS2To 属性写入上下文。 如果你想要对 AS2To 上下文属性执行协议解析，需要将自定义业务流程或自定义管道组件来执行此合并。 有关详细信息，请参阅[写入 AS2 上下文属性进行出站参与方解析](../core/writing-as2-context-properties-for-outbound-party-resolution.md)。  
   > 
   > [!NOTE]
   >  当使用动态发送端口时，将 AS2To 属性必须写入的协议解析的上下文。  
  
3. 如果在上一步失败，发送管道将尝试与订阅消息的发送端口与协议相关联的发送端口匹配。 发送端口是与中的协议相关联**发送端口**页的单向 AS2 协议**协议属性**对话框。  
  
   > [!NOTE]
   >  不同于在 EDI 处理中，没有回退 AS2 属性的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果它无法确定协议，可以使用。 没有，但是，用来发送 MDN 的默认协议。 此外，发送端口和 Http.UserHttpHeaders 上下文属性都不用于解析 MDN 的协议。 有关详细信息，请参阅的"协议解析 MDN 的"部分[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。  
   > 
   > [!NOTE]
   >  如果 AS2-To 协议属性中**标识符**页的单向 AS2 协议的**协议属性**对话框中设置默认情况下为英文参与方名称，而值中 AS2-To 标头as2 消息设置为非英文名称，然后将找不到匹配项。  
  
> [!NOTE]
>  通过 AS2 发送 EDI，需要为 EDI 和 AS2 使用单独的协议。  
  
 有关发送过程的更多详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)