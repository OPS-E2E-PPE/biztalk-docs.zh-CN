---
title: 确定丢失的跟踪数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, HAT
- reporting tools
- Orchestration Debugger
- Tracking database, data loss
- HAT, data loss
- HAT, Operation View tool
- HAT, reporting tools
- Operation View tool, MessageBox database
- MessageBox database, Operation View tool
- Operation View tool, data loss
ms.assetid: 1ac13e2c-cd5e-437e-b924-d4547931874e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17116d3a560e968e8dd9da0e42f5af221c23f5d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982854"
---
# <a name="identifying-lost-tracking-data"></a>确定丢失的跟踪数据
您可以使用 BizTalk Server 管理控制台来帮助标识哪些跟踪数据已因硬件失败而丢失。 您可以将 BizTalk Server 管理控制台用于实时数据或存档数据。  
  
 在 BizTalk Server 管理控制台可用于确定哪些服务处于活动状态恢复 MessageBox 时的时间。 由于在恢复该数据库和发生硬件故障之间有时间差，因此可能无法确定某些事务的状态。  
  
 您可以使用跟踪数据来标识在恢复点后完成和启动的服务实例，如下所示：  
  
- 寻找自上次备份数据库以后完成或启动的实例。  
  
- 如果 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据指示消息已启动但未完成并且该消息不在数据库中，则该消息是在上一次备份之后发送的。  
  
  跟踪可以报告任何已完成的服务，并且可以指示服务已启动。 跟踪数据首先临时保存在 MessageBox 中，然后被移到 BizTalk 跟踪数据库中。 临时保存的数据可能会由于 BAM 事件总线服务积压而丢失。  
  
  尽管出于操作原因，所有数据库都需要还原到同一标记，但是您可以使用存档模式下的 BizTalk 跟踪数据库（未丢失）查看在该标记之后执行的操作。  
  
  如果跟踪显示某个服务实例已完成，则可以终止该实例。 它可以显示在恢复点之后启动的实例。 如果这样，您将需要补偿这些实例所执行的任何操作，然后重新提交它们的初始激活消息。  
  
  您可以使用业务流程调试器查看最后执行的形状，然后使用“消息流”查看本应发送或接收的消息。  
  
  如果 BizTalk 跟踪数据库丢失，则需要使用外部系统报告机制来查找恢复点之后执行的所有操作。  
  
## <a name="see-also"></a>请参阅  
 [解决数据丢失问题](../core/resolving-data-loss.md)