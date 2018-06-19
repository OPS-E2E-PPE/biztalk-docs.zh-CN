---
title: 中断处理中业务流程管理解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, pausing
- process management solution tutorial, pausing processing
ms.assetid: 23ce7617-f705-4b7d-8447-221dec9fb196
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b98eae8ee9cbb43354c1cfc48710c70969a929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257773"
---
# <a name="interrupt-handling-in-the-business-process-management-solution"></a>中断业务流程管理解决方案中的处理
本部分将介绍业务流程管理解决方案中使用的中断处理机制。 使用中断机制，可暂停顺序处理当更新或取消订单时。  
  
## <a name="interrupt-handling"></a>中断处理  
 实现处理阶段的业务流程调用业务流程， **CheckInterrupt**，中断请求的过程的某些其他部分测试。 **CheckInterrupt** orchestration 组成**侦听**形状。 一个分支**侦听**形状检查消息具有相同的相关 ID 为当前的顺序。 如果没有这样的消息， **CheckInterrupt**业务流程发送确认消息和执行**引发**形状。 因为在分支**侦听**形状执行从左到右，延迟将显示在右侧的分支。 请注意，延迟时间为零 (0)。  
  
 组合**侦听**形状、 接收分支和延迟分支允许业务流程，若要检查的消息。 如果存在中断消息，则将执行左侧分支。 如果不存在任何消息，则将执行右侧分支并返回到调用方业务流程。 可以随时发送中断消息。 因为**CheckInterrupt**有时，可能有等待它的中断消息仅运行业务流程。  
  
 **OrderManager**通过调用设置中断**Interrupter**业务流程。 **Interrupter**业务流程将发送到中断消息**InterruptPort**并等待答复。 业务流程使用**超时**封闭的属性**作用域**形状以重新启动循环，如果未收到答复。 只要作用域在收到回复之前超时，该业务流程就会继续发送中断消息。 超时表示请求与某个订阅相匹配，但没有时间进行答复。 循环结束如果没有一个答复，或者如果没有任何订阅**InterruptPort**。  
  
 完成的请求-响应模式**OrderManager**过程阶段的使用是中断处理的关键部分。 因为**OrderManager**等待响应-确认-阶段中，从它知道阶段已开始在继续之前运行。 这样确保了在阶段开始之前该阶段不能接收中断。 这还允许**OrderManager**知道，是否没有中断没有订阅，该阶段已完成。  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程管理解决方案中进行处理](../core/processing-in-the-business-process-management-solution.md)   
 [过程管理器逻辑](../core/process-manager-logic.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)