---
title: "长时间运行事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- long-running transactions, about long-running transactions
- atomic transactions, long-running transactions
- long-running transactions, orchestrations
- long-running transactions, nesting
- scopes, examples
- orchestrations, transactions
- compensations, long-running transactions
- compensations, customizing
- transactions, long-running
- transactions, compensation blocks
- long-running transactions
- long-running transactions, timeouts
- compensations, examples
- fault tolerance, long-running transactions
- transactions, examples
- orchestrations, long-running transactions
- transactions, atomic
- transactions, fault tolerance
- scopes, long-running transactions
- long-running transactions, fault tolerance
- transactions, nesting
- examples, scopes
ms.assetid: 4bf4d0c8-903a-411f-963b-bd4cfdfc2958
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c419c79b9de6287a0361dfe4e2e6b9dc555153
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="long-running-transactions"></a><span data-ttu-id="888c3-102">长时间运行的事务</span><span class="sxs-lookup"><span data-stu-id="888c3-102">Long-Running Transactions</span></span>
<span data-ttu-id="888c3-103">长期事务是 BizTalk 业务流程中常用的重要构造。</span><span class="sxs-lookup"><span data-stu-id="888c3-103">Long-running transactions are important, commonly used constructs in BizTalk orchestrations.</span></span> <span data-ttu-id="888c3-104">它们提供的功能可帮助您实现自定义的基于作用域的补偿、自定义的基于作用域的异常处理以及嵌套事务，因此，您可以很灵活地设计可靠的事务结构。</span><span class="sxs-lookup"><span data-stu-id="888c3-104">They provide you with facilities for custom scope-based compensation, custom scope-based exception handling, and the ability to nest transactions, all of which give you great flexibility in designing robust transaction architecture.</span></span>  
  
 <span data-ttu-id="888c3-105">如果事务可能需要长时间运行并且不需要完整的 ACID 属性（即，不需要确保数据与其他事务隔离），则可以使用长期事务。</span><span class="sxs-lookup"><span data-stu-id="888c3-105">You use a long-running transaction when the transaction might need to run for an extended time and you do not need full ACID properties (that is, you do not need to guarantee isolation of data from other transactions).</span></span> <span data-ttu-id="888c3-106">长期事务可能具有较长的不活动时间，通常是由于等待外部消息到达造成的。</span><span class="sxs-lookup"><span data-stu-id="888c3-106">A long-running transaction might have long periods of inactivity, often due to waiting for external messages to arrive.</span></span>  
  
 <span data-ttu-id="888c3-107">长期事务拥有一致性和持久性，但不具备原子性和隔离。</span><span class="sxs-lookup"><span data-stu-id="888c3-107">Long-running transactions possess consistency, and durability, but not atomicity and isolation.</span></span> <span data-ttu-id="888c3-108">长期事务内的数据不锁定；其他进程或应用程序可以对数据进行修改。</span><span class="sxs-lookup"><span data-stu-id="888c3-108">The data within a long-running transaction is not locked; other processes or applications can modify it.</span></span> <span data-ttu-id="888c3-109">不保持状态更新的隔离属性，因为保持长期锁定不现实。</span><span class="sxs-lookup"><span data-stu-id="888c3-109">The isolation property for state updates is not maintained because holding locks for a long duration is impractical.</span></span>  
  
 <span data-ttu-id="888c3-110">长期事务的提交不同于原子事务的提交。</span><span class="sxs-lookup"><span data-stu-id="888c3-110">Commitment of a long-running transaction is different than commitment of an atomic transaction.</span></span> <span data-ttu-id="888c3-111">没有针对结果的分布式协调的隐式假定（长期事务仅存在于单个业务流程实例中）。</span><span class="sxs-lookup"><span data-stu-id="888c3-111">There is no implicit assumption of distributed coordination regarding the outcome (a long-running transaction exists only within a single orchestration instance).</span></span> <span data-ttu-id="888c3-112">而是在长期事务中的最后一个语句完成时，代表该事务已提交。</span><span class="sxs-lookup"><span data-stu-id="888c3-112">Instead, a long-running transaction is considered committed when the last statement in it has completed.</span></span> <span data-ttu-id="888c3-113">事务中止的情况下，不会“自动”回滚状态。</span><span class="sxs-lookup"><span data-stu-id="888c3-113">There is no "auto" rollback of state in case of a transaction abort.</span></span> <span data-ttu-id="888c3-114">这种回滚可以通过编写异常处理程序和补偿处理程序来实现。</span><span class="sxs-lookup"><span data-stu-id="888c3-114">You can achieve this programmatically through the exception and compensation handlers.</span></span>  
  
 <span data-ttu-id="888c3-115">作用域可通过声明变量、消息和 .NET 组件，定义自己的状态。</span><span class="sxs-lookup"><span data-stu-id="888c3-115">A scope can define its own state by declaring variables, messages, and .NET components.</span></span> <span data-ttu-id="888c3-116">长期事务能够访问自己的作用域的状态信息、封闭它的任何作用域以及在业务流程内全局定义的任何状态信息。</span><span class="sxs-lookup"><span data-stu-id="888c3-116">A long-running transaction has access to the state information of its own scope, any scope that encloses it, and any state information that is globally defined within the orchestration.</span></span> <span data-ttu-id="888c3-117">长期事务不能够访问不封闭它的任何作用域的状态信息。</span><span class="sxs-lookup"><span data-stu-id="888c3-117">It does not have access to the state information of any scopes that do not enclose it.</span></span>  
  
## <a name="nesting"></a><span data-ttu-id="888c3-118">嵌套</span><span class="sxs-lookup"><span data-stu-id="888c3-118">Nesting</span></span>  
 <span data-ttu-id="888c3-119">长期事务可以包含原子事务或其他长期事务。</span><span class="sxs-lookup"><span data-stu-id="888c3-119">Long-running transactions can contain atomic transactions or other long-running transactions.</span></span> <span data-ttu-id="888c3-120">它们可以嵌套到任意深度。</span><span class="sxs-lookup"><span data-stu-id="888c3-120">They can be nested to arbitrary depths.</span></span> <span data-ttu-id="888c3-121">例如，您的事务可以包含两个其他的长期事务，这两个事务又可以包含原子事务。</span><span class="sxs-lookup"><span data-stu-id="888c3-121">For example, your transaction might contain two other long-running transactions, each of which might contain atomic transactions.</span></span>  
  
 <span data-ttu-id="888c3-122">如果整体事务的一个或多个组件需要是原子的，而该整体事务又需要是长期的，则嵌套将很有用。</span><span class="sxs-lookup"><span data-stu-id="888c3-122">Nesting is particularly useful when one or more components of the overall transaction need to be atomic while the overall transaction needs to be long-running.</span></span> <span data-ttu-id="888c3-123">让我们看一下一个接收和履行采购订单的例子。</span><span class="sxs-lookup"><span data-stu-id="888c3-123">Consider the example of receiving and fulfilling a purchase order.</span></span> <span data-ttu-id="888c3-124">该采购订单可能会在任何时候到达，并且履行订单的不同步骤可能需要一定时间才能完成，但您仍想要将整个过程作为一个事务处理。</span><span class="sxs-lookup"><span data-stu-id="888c3-124">The purchase order can arrive at any time, and the various steps in fulfilling the order might take time to occur, but you still want to treat the entire process as a transaction.</span></span> <span data-ttu-id="888c3-125">显然，此例子中的整体事务需要是长期事务，但对于个别步骤，例如确认付款，可能需要是原子的。</span><span class="sxs-lookup"><span data-stu-id="888c3-125">The overall transaction in this case clearly needs to be long-running, but an individual step, such as acknowledging a payment, might need to be atomic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="888c3-126">不能在并非事务性的作用域或业务流程内嵌套事务性作用域。</span><span class="sxs-lookup"><span data-stu-id="888c3-126">You cannot nest a transactional scope within a scope or orchestration that is not transactional.</span></span> <span data-ttu-id="888c3-127">并非事务性的封闭作用域或业务流程将不会管理状态，因为它必须正确处理其中任何作用域的状态管理。</span><span class="sxs-lookup"><span data-stu-id="888c3-127">An enclosing scope or orchestration that is not transactional will not manage state, as it must to properly handle the state management of any scopes within it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="888c3-128">同步的事务不能包括任何其他事务或同步的作用域。</span><span class="sxs-lookup"><span data-stu-id="888c3-128">A synchronized transaction cannot include any other transactions or synchronized scopes.</span></span>  
  
## <a name="compensation"></a><span data-ttu-id="888c3-129">补偿</span><span class="sxs-lookup"><span data-stu-id="888c3-129">Compensation</span></span>  
 <span data-ttu-id="888c3-130">长期事务可以指定某一补偿模块，此补偿模块将在事务提交后被调用以补偿该事务的活动。</span><span class="sxs-lookup"><span data-stu-id="888c3-130">A long-running transaction can specify a compensation block that will be called to compensate for the transaction's activities, after it commits.</span></span> <span data-ttu-id="888c3-131">它可能只是撤消事务（如果可能），或者执行以某种方式帮助减轻事务影响的某些其他功能（例如通知）。</span><span class="sxs-lookup"><span data-stu-id="888c3-131">It might simply undo the transaction where feasible, or perform some other function, such as notification, that helps mitigate the effects of the transaction in some way.</span></span> <span data-ttu-id="888c3-132">如果您没有添加自己的补偿代码，则默认情况下运行时引擎将调用内部事务的补偿模块，长期事务和原子事务都采用相反顺序，即以最后提交的事务开始、以最先提交的事务结束。</span><span class="sxs-lookup"><span data-stu-id="888c3-132">If you do not add your own compensation code, the runtime engine will by default call the compensation blocks of the inner transactions, both long-running and atomic, in reverse order, starting with the last transaction committed and finishing with the first transaction committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="888c3-133">补偿只能对已成功提交的事务进行。</span><span class="sxs-lookup"><span data-stu-id="888c3-133">Compensation can only be done on a transaction that has committed successfully.</span></span>  
  
## <a name="fault-tolerance"></a><span data-ttu-id="888c3-134">容错</span><span class="sxs-lookup"><span data-stu-id="888c3-134">Fault tolerance</span></span>  
 <span data-ttu-id="888c3-135">事务支持容错，以便从内部错误（例如机器故障和软件错误）和外部错误（例如取消消息）恢复。</span><span class="sxs-lookup"><span data-stu-id="888c3-135">Transactions support fault tolerance for recovery from both internal faults (such as machine failures and software faults) and external faults (such as cancel messages).</span></span> <span data-ttu-id="888c3-136">在发生事务错误时，并不自动回滚长期事务内的部分更新，因为它们位于 ACID 事务中。</span><span class="sxs-lookup"><span data-stu-id="888c3-136">Partial updates within long-running transactions are not rolled back automatically when a transaction failure occurs, as they are in ACID transactions.</span></span>  
  
 <span data-ttu-id="888c3-137">在发生错误时将调用长期事务的异常代码块。</span><span class="sxs-lookup"><span data-stu-id="888c3-137">The exception code block for the long-running transaction is called when a fault occurs.</span></span> <span data-ttu-id="888c3-138">异常代码块包含一组您编写的错误处理程序，用于处理在事务执行期间可能导致的任何错误。</span><span class="sxs-lookup"><span data-stu-id="888c3-138">The exception code block contains a set of fault handlers that you write to deal with any of the faults that can arise during the execution of the transaction.</span></span> <span data-ttu-id="888c3-139">您可以借助消息、变量和对象的最后已知状态来处理错误。</span><span class="sxs-lookup"><span data-stu-id="888c3-139">You can rely on the last known state of the messages, variables, and objects in handling the fault.</span></span>  
  
 <span data-ttu-id="888c3-140">通常，您将希望异常处理程序评估在发生异常时业务流程的状态，基于该状态采取任何必要措施，并且调用任何嵌套事务的补偿。</span><span class="sxs-lookup"><span data-stu-id="888c3-140">You will typically want your exception handler to evaluate the state of the orchestration at the time the exception occurs, take any necessary action based on that state, and call the compensations of any nested transactions.</span></span>  
  
 <span data-ttu-id="888c3-141">在发生错误时，将中断长期事务的执行。</span><span class="sxs-lookup"><span data-stu-id="888c3-141">The execution of the long-running transaction is interrupted when a fault occurs.</span></span> <span data-ttu-id="888c3-142">长期事务不能在发生错误后恢复。</span><span class="sxs-lookup"><span data-stu-id="888c3-142">It cannot be resumed after a fault occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888c3-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="888c3-143">See Also</span></span>  
 <span data-ttu-id="888c3-144">[使用长时间运行事务的方案](../core/scenarios-using-long-running-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="888c3-144">[Scenarios Using Long-Running Transactions](../core/scenarios-using-long-running-transactions.md) </span></span>  
 <span data-ttu-id="888c3-145">[原子事务](../core/atomic-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="888c3-145">[Atomic Transactions](../core/atomic-transactions.md) </span></span>  
 [<span data-ttu-id="888c3-146">使用事务和处理异常</span><span class="sxs-lookup"><span data-stu-id="888c3-146">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)