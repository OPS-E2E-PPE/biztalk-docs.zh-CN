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
ms.openlocfilehash: 01290e6bec1157baed8bbb89d73b10a904dc1250
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332536"
---
# <a name="identifying-lost-tracking-data"></a>确定丢失的跟踪数据
在 BizTalk Server 管理控制台可用于帮助标识哪些跟踪数据已因硬件故障而丢失。 在 BizTalk Server 管理控制台可用于实时或存档的数据。  
  
 在 BizTalk Server 管理控制台可用于确定哪些服务处于活动状态恢复 MessageBox 时的时间。 因为该数据库恢复的时间和发生硬件故障的时间之间间隙，可能无法确定某些事务的状态。  
  
 跟踪数据可用于标识服务实例后完成和启动的恢复点，如下所示：  
  
- 查找哪些实例完成或启动自上次备份数据库。  
  
- 如果 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据指示消息已启动但未完成，并且该消息不在数据库中，该消息已在上次备份后进行发送。  
  
  跟踪可以报告任何服务都已完成，并且可以指示服务已启动。 跟踪数据首先临时保存到 MessageBox，然后移至 BizTalk 跟踪数据库。 已暂存的数据可能已丢失到 BAM 事件总线服务积压工作。  
  
  所有数据库都需要还原到相同的标记的操作的原因，而可以在存档模式下使用的 BizTalk 跟踪数据库 （未丢失） 以查看标记后发生了什么。  
  
  如果跟踪显示服务实例已完成，则可以终止该实例。 它可以显示在恢复点之后启动的实例。 如果这样，您将需要补偿这些实例所执行的任何操作，然后重新提交其初始激活消息。  
  
  可以使用业务流程调试器查看最后的执行，以及如何将消息流以查看哪些消息应已发送或接收形状。  
  
  如果 BizTalk 跟踪数据库丢失，需要通过使用外部系统报告机制完成所有发现的恢复点之后发生了什么情况。  
  
## <a name="see-also"></a>请参阅  
 [解决数据丢失问题](../core/resolving-data-loss.md)