---
title: "中断处理中业务流程管理解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, pausing
- process management solution tutorial, pausing processing
ms.assetid: 23ce7617-f705-4b7d-8447-221dec9fb196
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b98eae8ee9cbb43354c1cfc48710c70969a929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interrupt-handling-in-the-business-process-management-solution"></a><span data-ttu-id="6ba42-102">中断业务流程管理解决方案中的处理</span><span class="sxs-lookup"><span data-stu-id="6ba42-102">Interrupt Handling in the Business Process Management Solution</span></span>
<span data-ttu-id="6ba42-103">本部分将介绍业务流程管理解决方案中使用的中断处理机制。</span><span class="sxs-lookup"><span data-stu-id="6ba42-103">This section describes the interrupt handling mechanism used in the Business Process Management Solution.</span></span> <span data-ttu-id="6ba42-104">使用中断机制，可暂停顺序处理当更新或取消订单时。</span><span class="sxs-lookup"><span data-stu-id="6ba42-104">Using the interrupt mechanism enables you to halt order processing when an order is updated or canceled.</span></span>  
  
## <a name="interrupt-handling"></a><span data-ttu-id="6ba42-105">中断处理</span><span class="sxs-lookup"><span data-stu-id="6ba42-105">Interrupt Handling</span></span>  
 <span data-ttu-id="6ba42-106">实现处理阶段的业务流程调用业务流程， **CheckInterrupt**，中断请求的过程的某些其他部分测试。</span><span class="sxs-lookup"><span data-stu-id="6ba42-106">The orchestrations that implement the processing stages call an orchestration, **CheckInterrupt**, that tests for an interrupt request from some other part of the process.</span></span> <span data-ttu-id="6ba42-107">**CheckInterrupt** orchestration 组成**侦听**形状。</span><span class="sxs-lookup"><span data-stu-id="6ba42-107">The **CheckInterrupt** orchestration consists of a **Listen** shape.</span></span> <span data-ttu-id="6ba42-108">一个分支**侦听**形状检查消息具有相同的相关 ID 为当前的顺序。</span><span class="sxs-lookup"><span data-stu-id="6ba42-108">One branch of the **Listen** shape checks for a message with the same correlation ID as the current order.</span></span> <span data-ttu-id="6ba42-109">如果没有这样的消息， **CheckInterrupt**业务流程发送确认消息和执行**引发**形状。</span><span class="sxs-lookup"><span data-stu-id="6ba42-109">If there is such a message, the **CheckInterrupt** orchestration sends an acknowledgement message and executes a **Throw** shape.</span></span> <span data-ttu-id="6ba42-110">因为在分支**侦听**形状执行从左到右，延迟将显示在右侧的分支。</span><span class="sxs-lookup"><span data-stu-id="6ba42-110">Because the branches in a **Listen** shape are executed from left to right, the delay appears in the right branch.</span></span> <span data-ttu-id="6ba42-111">请注意，延迟时间为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="6ba42-111">Notice that the delay is zero (0).</span></span>  
  
 <span data-ttu-id="6ba42-112">组合**侦听**形状、 接收分支和延迟分支允许业务流程，若要检查的消息。</span><span class="sxs-lookup"><span data-stu-id="6ba42-112">The combination of the **Listen** shape, a receive branch, and a delay branch allows the orchestration to check for messages.</span></span> <span data-ttu-id="6ba42-113">如果存在中断消息，则将执行左侧分支。</span><span class="sxs-lookup"><span data-stu-id="6ba42-113">If there is an interrupt message, the left branch executes.</span></span> <span data-ttu-id="6ba42-114">如果不存在任何消息，则将执行右侧分支并返回到调用方业务流程。</span><span class="sxs-lookup"><span data-stu-id="6ba42-114">If there is no message, the right branch executes and returns to the calling orchestration.</span></span> <span data-ttu-id="6ba42-115">可以随时发送中断消息。</span><span class="sxs-lookup"><span data-stu-id="6ba42-115">An interrupt message can be sent at any time.</span></span> <span data-ttu-id="6ba42-116">因为**CheckInterrupt**有时，可能有等待它的中断消息仅运行业务流程。</span><span class="sxs-lookup"><span data-stu-id="6ba42-116">Because the **CheckInterrupt** orchestration is run only occasionally, there may be an interrupt message waiting for it.</span></span>  
  
 <span data-ttu-id="6ba42-117">**OrderManager**通过调用设置中断**Interrupter**业务流程。</span><span class="sxs-lookup"><span data-stu-id="6ba42-117">The **OrderManager** sets interrupts by calling the **Interrupter** orchestration.</span></span> <span data-ttu-id="6ba42-118">**Interrupter**业务流程将发送到中断消息**InterruptPort**并等待答复。</span><span class="sxs-lookup"><span data-stu-id="6ba42-118">The **Interrupter** orchestration sends an interrupt message to the **InterruptPort** and waits for a reply.</span></span> <span data-ttu-id="6ba42-119">业务流程使用**超时**封闭的属性**作用域**形状以重新启动循环，如果未收到答复。</span><span class="sxs-lookup"><span data-stu-id="6ba42-119">The orchestration uses the **Timeout** property of the enclosing **Scope** shape to restart the loop if a reply isn't received.</span></span> <span data-ttu-id="6ba42-120">只要作用域在收到回复之前超时，该业务流程就会继续发送中断消息。</span><span class="sxs-lookup"><span data-stu-id="6ba42-120">The orchestration continues to send the interrupt message as long as the scope times out before receiving a reply.</span></span> <span data-ttu-id="6ba42-121">超时表示请求与某个订阅相匹配，但没有时间进行答复。</span><span class="sxs-lookup"><span data-stu-id="6ba42-121">A timeout indicates that the request matched a subscription, but there hasn't been time for a reply.</span></span> <span data-ttu-id="6ba42-122">循环结束如果没有一个答复，或者如果没有任何订阅**InterruptPort**。</span><span class="sxs-lookup"><span data-stu-id="6ba42-122">The loop ends if there is a reply, or if there is no subscription to the **InterruptPort**.</span></span>  
  
 <span data-ttu-id="6ba42-123">完成的请求-响应模式**OrderManager**过程阶段的使用是中断处理的关键部分。</span><span class="sxs-lookup"><span data-stu-id="6ba42-123">The request-response-completion pattern the **OrderManager** uses with the process stages is a critical part of the interrupt handling.</span></span> <span data-ttu-id="6ba42-124">因为**OrderManager**等待响应-确认-阶段中，从它知道阶段已开始在继续之前运行。</span><span class="sxs-lookup"><span data-stu-id="6ba42-124">Because the **OrderManager** waits for a response—an acknowledgement—from the stage, it knows that the stage has started running before continuing.</span></span> <span data-ttu-id="6ba42-125">这样确保了在阶段开始之前该阶段不能接收中断。</span><span class="sxs-lookup"><span data-stu-id="6ba42-125">This guarantees that a stage cannot receive an interrupt before it starts.</span></span> <span data-ttu-id="6ba42-126">这还允许**OrderManager**知道，是否没有中断没有订阅，该阶段已完成。</span><span class="sxs-lookup"><span data-stu-id="6ba42-126">This also lets the **OrderManager** know that, if there is no subscription to an interrupt, the stage has completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba42-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ba42-127">See Also</span></span>  
 <span data-ttu-id="6ba42-128">[在业务流程管理解决方案中进行处理](../core/processing-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6ba42-128">[Processing in the Business Process Management Solution](../core/processing-in-the-business-process-management-solution.md) </span></span>  
 <span data-ttu-id="6ba42-129">[过程管理器逻辑](../core/process-manager-logic.md) </span><span class="sxs-lookup"><span data-stu-id="6ba42-129">[Process Manager Logic](../core/process-manager-logic.md) </span></span>  
 [<span data-ttu-id="6ba42-130">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="6ba42-130">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)