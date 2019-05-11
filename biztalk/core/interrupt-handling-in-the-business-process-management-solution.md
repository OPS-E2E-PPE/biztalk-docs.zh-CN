---
title: 业务流程管理解决方案中的中断处理 |Microsoft Docs
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
ms.openlocfilehash: 9e064c86c5546bac55eb564db12ec43d3f1c16d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331390"
---
# <a name="interrupt-handling-in-the-business-process-management-solution"></a>业务流程管理解决方案中的中断处理
本部分介绍的中断处理机制在业务流程管理解决方案中使用。 使用该中断机制，可更新或取消订单时停止订单处理。  
  
## <a name="interrupt-handling"></a>中断处理  
 实施处理阶段业务流程调用业务流程**CheckInterrupt**，用于测试的过程的一些其他部分的中断请求。 **CheckInterrupt**业务流程组成**侦听**形状。 一个分支**侦听**形状检查其消息具有与当前订单相同的相关 ID。 如果没有此类消息**CheckInterrupt**业务流程将发送确认消息，执行**引发**形状。 因为中的分支**侦听**形状执行从左到右，右侧分支中会出现延迟。 请注意，延迟是零 (0)。  
  
 组合**侦听**形状、 接收分支和延迟分支允许业务流程，以检查是否有消息。 如果没有中断消息，则将执行左侧的分支。 如果没有消息，右分支执行，并返回到调用业务流程。 可以随时发送中断消息。 因为**CheckInterrupt**仅有时，可能有等待它的中断消息运行业务流程。  
  
 **OrderManager**通过调用来设置中断**Interrupter**业务流程。 **Interrupter**业务流程将发送到的中断消息**InterruptPort**并等待回复。 该业务流程使用**超时**封闭的属性**作用域**形状以重新启动循环，如果没有收到回复。 业务流程仍会继续发送中断消息，只要收到回复之前超时的作用域。 超时表示请求匹配的订阅，但没有时间进行答复。 如果回复，或者没有为订阅循环将结束**InterruptPort**。  
  
 请求-响应-完成模式**OrderManager**对处理阶段使用是中断处理的关键部分。 因为**OrderManager**等待响应，确认 — 从该阶段，它知道该阶段已开始运行，然后才能继续操作。 这可确保在开始之前，一个阶段不能接收中断。 这还可让**OrderManager**知道，是否没有中断的订阅，该阶段已完成。  
  
## <a name="see-also"></a>请参阅  
 [在业务流程管理解决方案中处理](../core/processing-in-the-business-process-management-solution.md)   
 [进程管理器逻辑](../core/process-manager-logic.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)