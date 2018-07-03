---
title: 传入 AS2 消息的协议解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 746d01af-de6a-4d5d-9433-b0e1a2b41861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25a464025377eae7fd70992359d3be1582fa748a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016725"
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a>传入 AS2 消息的协议解析
当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过 HTTP/HTTPS 传输接收 EDIINT/AS2 编码消息时，它会尝试确定发送该消息的贸易合作伙伴的业务配置文件。 它通过尝试执行以下操作（按照所示顺序）来实现此目的：  
  
1. 使匹配 AS2-From 的值与传入消息中的标头**AS2-从**中**标识符**中的单向 AS2 协议页**协议属性**对话框。  
  
2. 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，则它会尝试将为传入的消息设置的 AS2-From 上下文属性与贸易合作伙伴的名称进行匹配。  
  
> [!NOTE]
>  由于 AS2-From 标头只能包含 ASCII 字符，因此必须确保贸易合作伙伴名称和 AS2-From 别名也只包含 ASCII 字符。 如果不是完全匹配，BizTalk 将无法基于传入消息标头确定协议。  
  
 只有在确定了协议的情况下，AS2 接收管道才会处理该消息。 与 EDI 处理过程不同，如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，则它没有任何可以使用的后备 AS2 属性。  
  
 一旦管道确定了协议，它将检查的设置**使用协议设置用于验证和 MDN 而非消息标头**属性中的**验证**页的单向 AS2中的协议**协议设置**对话框。 如果该属性处于选中状态，接收管道将使用协议属性处理消息。 如果未选中该属性，接收管道将使用消息的 AS2 标头中的值处理消息。  
  
> [!NOTE]
>  在协议解析过程中确定的 AS2 协议可能不是 EDI 负载的形式相同的协议。 没有要求，AS2 和 EDI 必须共享相同的协议，因为 AS2 协议可能代表将路由从多个参与方的 EDI 文档交换所。  
  
 有关接收过程的更多详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)