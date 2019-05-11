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
# <a name="interrupt-handling-in-the-business-process-management-solution"></a><span data-ttu-id="313e4-102">业务流程管理解决方案中的中断处理</span><span class="sxs-lookup"><span data-stu-id="313e4-102">Interrupt Handling in the Business Process Management Solution</span></span>
<span data-ttu-id="313e4-103">本部分介绍的中断处理机制在业务流程管理解决方案中使用。</span><span class="sxs-lookup"><span data-stu-id="313e4-103">This section describes the interrupt handling mechanism used in the Business Process Management Solution.</span></span> <span data-ttu-id="313e4-104">使用该中断机制，可更新或取消订单时停止订单处理。</span><span class="sxs-lookup"><span data-stu-id="313e4-104">Using the interrupt mechanism enables you to halt order processing when an order is updated or canceled.</span></span>  
  
## <a name="interrupt-handling"></a><span data-ttu-id="313e4-105">中断处理</span><span class="sxs-lookup"><span data-stu-id="313e4-105">Interrupt Handling</span></span>  
 <span data-ttu-id="313e4-106">实施处理阶段业务流程调用业务流程**CheckInterrupt**，用于测试的过程的一些其他部分的中断请求。</span><span class="sxs-lookup"><span data-stu-id="313e4-106">The orchestrations that implement the processing stages call an orchestration, **CheckInterrupt**, that tests for an interrupt request from some other part of the process.</span></span> <span data-ttu-id="313e4-107">**CheckInterrupt**业务流程组成**侦听**形状。</span><span class="sxs-lookup"><span data-stu-id="313e4-107">The **CheckInterrupt** orchestration consists of a **Listen** shape.</span></span> <span data-ttu-id="313e4-108">一个分支**侦听**形状检查其消息具有与当前订单相同的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="313e4-108">One branch of the **Listen** shape checks for a message with the same correlation ID as the current order.</span></span> <span data-ttu-id="313e4-109">如果没有此类消息**CheckInterrupt**业务流程将发送确认消息，执行**引发**形状。</span><span class="sxs-lookup"><span data-stu-id="313e4-109">If there is such a message, the **CheckInterrupt** orchestration sends an acknowledgement message and executes a **Throw** shape.</span></span> <span data-ttu-id="313e4-110">因为中的分支**侦听**形状执行从左到右，右侧分支中会出现延迟。</span><span class="sxs-lookup"><span data-stu-id="313e4-110">Because the branches in a **Listen** shape are executed from left to right, the delay appears in the right branch.</span></span> <span data-ttu-id="313e4-111">请注意，延迟是零 (0)。</span><span class="sxs-lookup"><span data-stu-id="313e4-111">Notice that the delay is zero (0).</span></span>  
  
 <span data-ttu-id="313e4-112">组合**侦听**形状、 接收分支和延迟分支允许业务流程，以检查是否有消息。</span><span class="sxs-lookup"><span data-stu-id="313e4-112">The combination of the **Listen** shape, a receive branch, and a delay branch allows the orchestration to check for messages.</span></span> <span data-ttu-id="313e4-113">如果没有中断消息，则将执行左侧的分支。</span><span class="sxs-lookup"><span data-stu-id="313e4-113">If there is an interrupt message, the left branch executes.</span></span> <span data-ttu-id="313e4-114">如果没有消息，右分支执行，并返回到调用业务流程。</span><span class="sxs-lookup"><span data-stu-id="313e4-114">If there is no message, the right branch executes and returns to the calling orchestration.</span></span> <span data-ttu-id="313e4-115">可以随时发送中断消息。</span><span class="sxs-lookup"><span data-stu-id="313e4-115">An interrupt message can be sent at any time.</span></span> <span data-ttu-id="313e4-116">因为**CheckInterrupt**仅有时，可能有等待它的中断消息运行业务流程。</span><span class="sxs-lookup"><span data-stu-id="313e4-116">Because the **CheckInterrupt** orchestration is run only occasionally, there may be an interrupt message waiting for it.</span></span>  
  
 <span data-ttu-id="313e4-117">**OrderManager**通过调用来设置中断**Interrupter**业务流程。</span><span class="sxs-lookup"><span data-stu-id="313e4-117">The **OrderManager** sets interrupts by calling the **Interrupter** orchestration.</span></span> <span data-ttu-id="313e4-118">**Interrupter**业务流程将发送到的中断消息**InterruptPort**并等待回复。</span><span class="sxs-lookup"><span data-stu-id="313e4-118">The **Interrupter** orchestration sends an interrupt message to the **InterruptPort** and waits for a reply.</span></span> <span data-ttu-id="313e4-119">该业务流程使用**超时**封闭的属性**作用域**形状以重新启动循环，如果没有收到回复。</span><span class="sxs-lookup"><span data-stu-id="313e4-119">The orchestration uses the **Timeout** property of the enclosing **Scope** shape to restart the loop if a reply isn't received.</span></span> <span data-ttu-id="313e4-120">业务流程仍会继续发送中断消息，只要收到回复之前超时的作用域。</span><span class="sxs-lookup"><span data-stu-id="313e4-120">The orchestration continues to send the interrupt message as long as the scope times out before receiving a reply.</span></span> <span data-ttu-id="313e4-121">超时表示请求匹配的订阅，但没有时间进行答复。</span><span class="sxs-lookup"><span data-stu-id="313e4-121">A timeout indicates that the request matched a subscription, but there hasn't been time for a reply.</span></span> <span data-ttu-id="313e4-122">如果回复，或者没有为订阅循环将结束**InterruptPort**。</span><span class="sxs-lookup"><span data-stu-id="313e4-122">The loop ends if there is a reply, or if there is no subscription to the **InterruptPort**.</span></span>  
  
 <span data-ttu-id="313e4-123">请求-响应-完成模式**OrderManager**对处理阶段使用是中断处理的关键部分。</span><span class="sxs-lookup"><span data-stu-id="313e4-123">The request-response-completion pattern the **OrderManager** uses with the process stages is a critical part of the interrupt handling.</span></span> <span data-ttu-id="313e4-124">因为**OrderManager**等待响应，确认 — 从该阶段，它知道该阶段已开始运行，然后才能继续操作。</span><span class="sxs-lookup"><span data-stu-id="313e4-124">Because the **OrderManager** waits for a response—an acknowledgement—from the stage, it knows that the stage has started running before continuing.</span></span> <span data-ttu-id="313e4-125">这可确保在开始之前，一个阶段不能接收中断。</span><span class="sxs-lookup"><span data-stu-id="313e4-125">This guarantees that a stage cannot receive an interrupt before it starts.</span></span> <span data-ttu-id="313e4-126">这还可让**OrderManager**知道，是否没有中断的订阅，该阶段已完成。</span><span class="sxs-lookup"><span data-stu-id="313e4-126">This also lets the **OrderManager** know that, if there is no subscription to an interrupt, the stage has completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313e4-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="313e4-127">See Also</span></span>  
 <span data-ttu-id="313e4-128">[在业务流程管理解决方案中处理](../core/processing-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="313e4-128">[Processing in the Business Process Management Solution](../core/processing-in-the-business-process-management-solution.md) </span></span>  
 <span data-ttu-id="313e4-129">[进程管理器逻辑](../core/process-manager-logic.md) </span><span class="sxs-lookup"><span data-stu-id="313e4-129">[Process Manager Logic](../core/process-manager-logic.md) </span></span>  
 [<span data-ttu-id="313e4-130">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="313e4-130">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)