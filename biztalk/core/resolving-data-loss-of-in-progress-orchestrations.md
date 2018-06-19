---
title: 解决数据丢失的正在进行中业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, MessageBox database
- data recovery
- data loss, recovery
- data loss, orchestrations
- data recovery, MessageBox database
- data recovery, orchestrations
- data loss, data recovery
- orchestrations, data recovery
- orchestrations, data loss
ms.assetid: dc6f1fd2-1976-40f2-ab57-41c7db40705e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eca757b80e31ee5db829d2d2079bf657d01079b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268997"
---
# <a name="resolving-data-loss-of-in-progress-orchestrations"></a>解决正在进行的业务流程的数据丢失问题
MessageBox 数据库包含当前正在进行的业务流程的状态。 尽管没有没有方法来判断完全哪些数据已从 MessageBox 数据库丢失，但有一些可用于收集有关数据丢失的信息的步骤：  
  
-   确定哪些消息具有已发送和接收当前业务流程，以及哪些外部系统均已使用的恢复点之后。 例如，如果你的系统维护的消息和事件的外部日志，你可以检查该日志。 你可能还需要手动查看外部的系统，以查看发生了哪些活动。  
  
-   确定数据丢失的原因后，你可以开始更正系统还原，决定哪些进程可以继续，必须终止的进程，并将其重新启动 （通过在重新提交丢失的激活消息），以及哪些进程完成已成功，可以被终止。 此过程很大程度上取决于你的系统的体系结构，并且必须作为系统恢复规划的一部分加以考虑。  
  
## <a name="see-also"></a>另请参阅  
 [解决数据丢失](../core/resolving-data-loss.md)