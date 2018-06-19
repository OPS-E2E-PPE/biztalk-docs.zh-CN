---
title: BizTalk Framework 汇编程序管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777e3d98ade5b4e0c54744cea6d37b1e43717e66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231101"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a>BizTalk Framework 汇编程序管道组件
BizTalk 框架是用于在使用网络传输协议(例如 HTTP 或 SMTP)时保证一次性传送即可送达的一种方法。 此框架自 1998 年起就已存在，并且可被视为基于 Web services（尤其是 WSReliable）的挂起标准计划的先驱。 通常，保证一次性传送即可送达数据的问题已属于诸如消息队列（也称为 MSMQ）之类的技术领域。 不过，此类技术通常需要在数据流的两个终结点具有通用软件，并且不适用于使用基于公共网络的开放传输协议，例如使用 Internet 在企业边界间传输的数据。  
  
 BizTalk 框架将实施某些在早期尝试中所使用的相同机制，以解决保证一次性传送即可送达数据的问题，这一点并不奇怪。 对于该问题的其他解决方案的一个很好示例是电子数据交换 (EDI)，其中 ANSI X12 控制编号和标准 997 功能确认文档形成了保证只接收一次数据并将有关接收端的任何问题通知发件人的基础。  
  
 BizTalk 框架假定无论系统交换数据的方式如何不同，这些系统都了解 BizTalk 框架协议的以下要求：  
  
-   使用换行传输的可预测信封格式。  
  
-   使用全局唯一标识符标记每个出站传输。  
  
-   即使对于已接收、已确认和已处理的数据，也始终向发件人返回包括全局唯一标识符的回执确认。  
  
-   在收到收件人的回执或达到传输变为无效前持续的时间段之前，发件人可通过某些方式重复传输。  
  
 BizTalk 框架组装器管道组件负责在传输前将 BizTalk 框架信封和内容序列化为消息，并在分配的时段内回执未送达的情况下进行重新发送。 该组件还负责接收和处理回执，以及删除消息实例。 （在 BizTalk 收到来自目标的确认回执之前，已发送消息的消息实例副本将保存在 MessageBox 数据库中。 收到确认回执后，消息引擎将删除该消息实例。）  
  
## <a name="see-also"></a>另请参阅  
 [如何将 BizTalk Framework 汇编程序管道组件配置](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)   
 [管道组件](../core/pipeline-components.md)