---
title: "使用长时间运行事务的方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions, long-running
- long-running transactions, timeouts
- transactions, examples
- long-running transactions, examples
- long-running compensations
- examples, long-running transactions
- examples, custom compensations
ms.assetid: 76b3e0f8-44dc-419e-a73a-c2908b1d8795
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ac14bc6e333f963dda7cb9b33d1ebf371c0546
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenarios-using-long-running-transactions"></a><span data-ttu-id="7639c-102">使用长期事务的方案</span><span class="sxs-lookup"><span data-stu-id="7639c-102">Scenarios Using Long-Running Transactions</span></span>
<span data-ttu-id="7639c-103">下面的方案介绍如何使用长期事务。</span><span class="sxs-lookup"><span data-stu-id="7639c-103">The following scenarios describe the use of long running transactions.</span></span>  
  
## <a name="scenario-1-using-long-running-transactions-with-timeouts"></a><span data-ttu-id="7639c-104">方案 1： 使用与超时长时间运行事务</span><span class="sxs-lookup"><span data-stu-id="7639c-104">Scenario 1: Using Long Running Transactions with Timeouts</span></span>  
 <span data-ttu-id="7639c-105">长期作用域可与某一超时关联，超时是长期工作必须在此时间范围内完成的逻辑时间。</span><span class="sxs-lookup"><span data-stu-id="7639c-105">Long running scopes can be associated with a timeout, which is a logical time within which the long-running work must complete.</span></span> <span data-ttu-id="7639c-106">如果未指定的时间，预定义的系统异常内完成，作用域**TimeoutException**引发。</span><span class="sxs-lookup"><span data-stu-id="7639c-106">If the scope does not complete within the specified time, a pre-defined system exception **TimeoutException** is raised.</span></span>  
  
 <span data-ttu-id="7639c-107">您可以通过将整个业务流程标记为长期的，或者通过让外部长期作用域嵌套任何其他作用域，创建长期进程。</span><span class="sxs-lookup"><span data-stu-id="7639c-107">You can create long running processes by either marking the entire orchestration as long running or having an outer long running scope nest any other scopes.</span></span> <span data-ttu-id="7639c-108">在前一个方案中，系统提供的异常处理程序将运行，而后一个方案则允许特定的异常处理程序与外部作用域相关联。</span><span class="sxs-lookup"><span data-stu-id="7639c-108">In the former scenario, a system-provided exception handler runs, whereas the latter allows associating specific exception handlers to the outer scope.</span></span> <span data-ttu-id="7639c-109">默认的系统提供的异常处理程序将为每个成功完成的嵌套事务性作用域（如果有）运行补偿处理程序，运行顺序与其完成顺序相反。</span><span class="sxs-lookup"><span data-stu-id="7639c-109">The default system-provided exception handler will run the compensation handler for each of the successfully completed nested transactional scopes, if any, in reverse order of their completion.</span></span> <span data-ttu-id="7639c-110">您可以通过在异常处理程序中将补偿形状用于长期事务，通过自补偿实现同一任务。</span><span class="sxs-lookup"><span data-stu-id="7639c-110">You can achieve the same through self compensating by using the Compensate shape in the exception handler for a long running transaction.</span></span>  
  
 <span data-ttu-id="7639c-111">下面的业务流程介绍如何将超时与长期事务相关联。</span><span class="sxs-lookup"><span data-stu-id="7639c-111">The following orchestration is a representation of how to associate timeouts with long running transactions.</span></span>  
  
 <span data-ttu-id="7639c-112">**使用超时值的长时间运行事务**</span><span class="sxs-lookup"><span data-stu-id="7639c-112">**Long running transactions with timeouts**</span></span>  
  
 <span data-ttu-id="7639c-113">![使用超时长时间运行事务](../core/media/bts-trans-orch-fig7.gif "BTS_Trans_Orch_Fig7")</span><span class="sxs-lookup"><span data-stu-id="7639c-113">![Long running transactions with timeouts](../core/media/bts-trans-orch-fig7.gif "BTS_Trans_Orch_Fig7")</span></span>  
  
 <span data-ttu-id="7639c-114">有时候，您可能需要连接以批处理形式操作的旧式系统。</span><span class="sxs-lookup"><span data-stu-id="7639c-114">Sometimes you may need to interface with legacy systems that operate in a batch fashion.</span></span> <span data-ttu-id="7639c-115">此方案显示了一个要接收并发送到旧式系统的采购订单。</span><span class="sxs-lookup"><span data-stu-id="7639c-115">This scenario shows a purchase order being received and sent to the legacy system.</span></span> <span data-ttu-id="7639c-116">此旧式系统处理该采购订单，并且发送回采购订单确认。</span><span class="sxs-lookup"><span data-stu-id="7639c-116">The legacy system processes the purchase order and sends back a purchase order acknowledgement.</span></span> <span data-ttu-id="7639c-117">该发送操作采用采购订单号初始化某一相关集，并且接收操作将遵循该相关集。</span><span class="sxs-lookup"><span data-stu-id="7639c-117">The send operation initializes a correlation set using the purchase order number and the receive operation follows that correlation set.</span></span> <span data-ttu-id="7639c-118">该接收操作还处于具有超时值的长期作用域中。</span><span class="sxs-lookup"><span data-stu-id="7639c-118">The receive operation is also in a long running scope with a timeout value.</span></span>  
  
 <span data-ttu-id="7639c-119">业务流程引擎将冻结正等待接收的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="7639c-119">The orchestration engine will dehydrate the orchestration instance waiting for the receive.</span></span> <span data-ttu-id="7639c-120">相关将确保在接收消息后调用同一业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="7639c-120">The correlation will ensure that the same orchestration instance is invoked after the message is received.</span></span> <span data-ttu-id="7639c-121">如果购买订单确认没有超时值，通过指定的时间间隔内到达**TimeoutException**将引发。</span><span class="sxs-lookup"><span data-stu-id="7639c-121">If the purchase order acknowledgement does not arrive within the time interval specified by the timeout values, a **TimeoutException** will be thrown.</span></span>  
  
## <a name="scenario-2-using-long-running-transactions-with-custom-compensation"></a><span data-ttu-id="7639c-122">方案 2： 使用与自定义补偿长时间运行事务</span><span class="sxs-lookup"><span data-stu-id="7639c-122">Scenario 2: Using Long Running Transactions with Custom Compensation</span></span>  
 <span data-ttu-id="7639c-123">以下业务流程阐释如何关联自定义补偿以及调用与整个业务流程相关联的自定义补偿。</span><span class="sxs-lookup"><span data-stu-id="7639c-123">The following orchestrations demonstrate how to associate and invoke custom compensations associated with entire orchestrations.</span></span> <span data-ttu-id="7639c-124">此方案将插入一个新客户以及插入该客户的订单明细。</span><span class="sxs-lookup"><span data-stu-id="7639c-124">This scenario inserts a new customer and inserts order details for the customer.</span></span> <span data-ttu-id="7639c-125">业务流程的逻辑规定如果订单插入失败，您应该回滚该客户插入。</span><span class="sxs-lookup"><span data-stu-id="7639c-125">The logic of the orchestration dictates that if the order insert fails, you should roll back the customer insert.</span></span> <span data-ttu-id="7639c-126">该客户插入可由旧式系统执行，因此，在单独的可调用业务流程中阐释。</span><span class="sxs-lookup"><span data-stu-id="7639c-126">The customer insert could be done by a legacy system, and is therefore, demonstrated in a separate callable orchestration.</span></span> <span data-ttu-id="7639c-127">调用的业务流程已**自定义**属性设置为提供单独的工作表进行补偿过程的补偿。</span><span class="sxs-lookup"><span data-stu-id="7639c-127">The called orchestration has the **Custom** property set for compensation, which provides a separate sheet to do the compensation process.</span></span> <span data-ttu-id="7639c-128">该补偿是要删除新插入的客户。</span><span class="sxs-lookup"><span data-stu-id="7639c-128">The compensation is to delete the newly inserted customer.</span></span>  
  
 <span data-ttu-id="7639c-129">调用业务流程具有要执行订单插入的长期作用域。</span><span class="sxs-lookup"><span data-stu-id="7639c-129">The calling orchestration has a long running scope to do the order insert.</span></span> <span data-ttu-id="7639c-130">此作用域嵌套在某一外部长期作用域中。</span><span class="sxs-lookup"><span data-stu-id="7639c-130">This scope is nested within an outer long running scope.</span></span> <span data-ttu-id="7639c-131">该外部作用域具有关联的异常处理程序，以便捕获任何异常。</span><span class="sxs-lookup"><span data-stu-id="7639c-131">The outer scope has an exception handler associated to catch any exceptions.</span></span> <span data-ttu-id="7639c-132">该处理程序使用补偿形状来定义与调用的业务流程相关联的自定义异常，以便回滚在对业务流程的调用中可能发生的任何更改。</span><span class="sxs-lookup"><span data-stu-id="7639c-132">The handler uses the Compensate shape to invoke the custom exception associated with the called orchestration to roll back any changes that might have occurred in the call to the orchestration.</span></span>  
  
 <span data-ttu-id="7639c-133">**使用自定义补偿的长时间运行事务**</span><span class="sxs-lookup"><span data-stu-id="7639c-133">**Long running transactions with custom compensation**</span></span>  
  
 <span data-ttu-id="7639c-134">![长时间运行事务，使用自定义补偿](../core/media/bts-trans-orch-fig8.gif "BTS_Trans_Orch_Fig8")</span><span class="sxs-lookup"><span data-stu-id="7639c-134">![Long running transactions with custom compensation](../core/media/bts-trans-orch-fig8.gif "BTS_Trans_Orch_Fig8")</span></span>  
  
 <span data-ttu-id="7639c-135">**调用的业务流程 （主）**</span><span class="sxs-lookup"><span data-stu-id="7639c-135">**Called orchestration (main)**</span></span>  
  
 <span data-ttu-id="7639c-136">![调用 orchestration &#40; main &#41;] (../core/media/bts-trans-orch-fig9.gif "BTS_Trans_Orch_Fig9")</span><span class="sxs-lookup"><span data-stu-id="7639c-136">![Called orchestration &#40;main&#41;](../core/media/bts-trans-orch-fig9.gif "BTS_Trans_Orch_Fig9")</span></span>  
  
 <span data-ttu-id="7639c-137">**调用的业务流程 （补偿）**</span><span class="sxs-lookup"><span data-stu-id="7639c-137">**Called orchestration (compensation)**</span></span>  
  
 <span data-ttu-id="7639c-138">![调用 orchestration &#40; 补偿 &#41;] (../core/media/bts-trans-orch-fig10.gif "BTS_Trans_Orch_Fig10")</span><span class="sxs-lookup"><span data-stu-id="7639c-138">![Called orchestration &#40;compensation&#41;](../core/media/bts-trans-orch-fig10.gif "BTS_Trans_Orch_Fig10")</span></span>