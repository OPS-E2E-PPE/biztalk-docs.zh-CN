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
ms.openlocfilehash: bf569721a2a97aeb93b8b753599c64ae0ef890ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359877"
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a>传入 AS2 消息的协议解析
当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDIINT/AS2 编码的消息通过 HTTP/HTTPS 传输，它会尝试确定发送消息的贸易合作伙伴的业务配置文件。 这是通过尝试执行以下 （按所示的顺序）：  
  
1. 使匹配 AS2-From 的值与传入消息中的标头**AS2-从**中**标识符**中的单向 AS2 协议页**协议属性**对话框。  
  
2. 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定协议，它将尝试匹配 AS2-From 上下文属性设置为将传入消息与贸易合作伙伴的名称。  
  
> [!NOTE]
>  由于 AS2-从标头只能包含 ASCII 字符，则必须确保贸易合作伙伴名称和 AS2-From 别名也只包含 ASCII 字符。 如果完全匹配项不会发生，BizTalk 将无法确定传入消息标头所基于的协议。  
  
 AS2 接收管道将处理该消息，仅当确定了协议。 不同于在 EDI 处理中，没有回退 AS2 属性的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果它无法确定协议，可以使用。  
  
 一旦管道确定了协议，它将检查的设置**使用协议设置用于验证和 MDN 而非消息标头**属性中的**验证**页的单向 AS2中的协议**协议设置**对话框。 如果该属性为选中状态，接收管道将使用协议属性来处理该消息。 如果清除该属性，则接收管道将使用值的消息的 AS2 头部中要对其进行处理。  
  
> [!NOTE]
>  在协议解析过程中确定的 AS2 协议可能不是 EDI 负载的形式相同的协议。 没有要求，AS2 和 EDI 必须共享相同的协议，因为 AS2 协议可能代表将路由从多个参与方的 EDI 文档交换所。  
  
 有关接收过程的更多详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)