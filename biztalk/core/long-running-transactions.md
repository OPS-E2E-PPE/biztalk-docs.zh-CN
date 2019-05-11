---
title: 长时间运行的事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99fb048c158b758e125d82f50ce2771bf0ede94f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330394"
---
# <a name="long-running-transactions"></a><span data-ttu-id="ccc1c-102">长时间运行的事务</span><span class="sxs-lookup"><span data-stu-id="ccc1c-102">Long-Running Transactions</span></span>
<span data-ttu-id="ccc1c-103">长时间运行的事务是 BizTalk 业务流程中的重要的是，常用构造。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-103">Long-running transactions are important, commonly used constructs in BizTalk orchestrations.</span></span> <span data-ttu-id="ccc1c-104">它们为您提供用于自定义基于作用域的补偿、 自定义基于作用域的异常处理，以及嵌套的事务，所有这些为您提供很灵活地设计可靠的事务体系结构功能的功能。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-104">They provide you with facilities for custom scope-based compensation, custom scope-based exception handling, and the ability to nest transactions, all of which give you great flexibility in designing robust transaction architecture.</span></span>  
  
 <span data-ttu-id="ccc1c-105">如果事务可能需要长时间运行并且不需要完整的 ACID 属性，可以使用一个长时间运行的事务 （即，您不需要与其他事务保证的数据隔离）。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-105">You use a long-running transaction when the transaction might need to run for an extended time and you do not need full ACID properties (that is, you do not need to guarantee isolation of data from other transactions).</span></span> <span data-ttu-id="ccc1c-106">一个长时间运行的事务可能很长一段非活动状态，通常由于等待外部消息到达。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-106">A long-running transaction might have long periods of inactivity, often due to waiting for external messages to arrive.</span></span>  
  
 <span data-ttu-id="ccc1c-107">长时间运行的事务拥有一致性和持久性，但不是原子性和隔离。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-107">Long-running transactions possess consistency, and durability, but not atomicity and isolation.</span></span> <span data-ttu-id="ccc1c-108">一个长时间运行的事务内的数据不被锁定则其他进程或应用程序可以修改它。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-108">The data within a long-running transaction is not locked; other processes or applications can modify it.</span></span> <span data-ttu-id="ccc1c-109">因为是不切实际的了很长时间持有锁不会保留状态更新的隔离属性。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-109">The isolation property for state updates is not maintained because holding locks for a long duration is impractical.</span></span>  
  
 <span data-ttu-id="ccc1c-110">原子事务的提交不同于长时间运行事务的承诺。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-110">Commitment of a long-running transaction is different than commitment of an atomic transaction.</span></span> <span data-ttu-id="ccc1c-111">没有针对结果 （仅在单个业务流程实例中存在一个长时间运行的事务） 的分布式协调的隐式假定。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-111">There is no implicit assumption of distributed coordination regarding the outcome (a long-running transaction exists only within a single orchestration instance).</span></span> <span data-ttu-id="ccc1c-112">而是一个长时间运行的事务被视为已提交的最后一个语句完成时。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-112">Instead, a long-running transaction is considered committed when the last statement in it has completed.</span></span> <span data-ttu-id="ccc1c-113">没有任何"auto"回滚事务中止的情况下的状态。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-113">There is no "auto" rollback of state in case of a transaction abort.</span></span> <span data-ttu-id="ccc1c-114">通过异常和补偿处理程序可以以编程方式实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-114">You can achieve this programmatically through the exception and compensation handlers.</span></span>  
  
 <span data-ttu-id="ccc1c-115">作用域可以通过声明变量、 消息和.NET 组件来定义其自己的状态。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-115">A scope can define its own state by declaring variables, messages, and .NET components.</span></span> <span data-ttu-id="ccc1c-116">一个长时间运行的事务有权访问自己的作用域、 封闭它的任何作用域和业务流程内全局定义的任何状态信息的状态信息。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-116">A long-running transaction has access to the state information of its own scope, any scope that encloses it, and any state information that is globally defined within the orchestration.</span></span> <span data-ttu-id="ccc1c-117">它并没有访问不封闭它的所有作用域的状态信息。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-117">It does not have access to the state information of any scopes that do not enclose it.</span></span>  
  
## <a name="nesting"></a><span data-ttu-id="ccc1c-118">嵌套</span><span class="sxs-lookup"><span data-stu-id="ccc1c-118">Nesting</span></span>  
 <span data-ttu-id="ccc1c-119">长时间运行的事务可以包含原子事务或其他长时间运行的事务。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-119">Long-running transactions can contain atomic transactions or other long-running transactions.</span></span> <span data-ttu-id="ccc1c-120">它们可以嵌套到任意深度。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-120">They can be nested to arbitrary depths.</span></span> <span data-ttu-id="ccc1c-121">例如，您的事务可能包含两个其他长时间运行的事务，其中每个可以包含原子事务。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-121">For example, your transaction might contain two other long-running transactions, each of which might contain atomic transactions.</span></span>  
  
 <span data-ttu-id="ccc1c-122">嵌套将很有用，当一个或多个组件的整体事务需要是原子的而整体事务需要长时间运行。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-122">Nesting is particularly useful when one or more components of the overall transaction need to be atomic while the overall transaction needs to be long-running.</span></span> <span data-ttu-id="ccc1c-123">请考虑接收和履行采购订单的示例。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-123">Consider the example of receiving and fulfilling a purchase order.</span></span> <span data-ttu-id="ccc1c-124">采购订单可以在任何时候，到达和履行订单的不同步骤可能需要时间才能完成，但仍想要将视为一个事务的整个过程。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-124">The purchase order can arrive at any time, and the various steps in fulfilling the order might take time to occur, but you still want to treat the entire process as a transaction.</span></span> <span data-ttu-id="ccc1c-125">整体事务在这种情况下明确需要长时间运行，但个别步骤，例如确认付款，可能需要是原子性。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-125">The overall transaction in this case clearly needs to be long-running, but an individual step, such as acknowledging a payment, might need to be atomic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccc1c-126">不能嵌套事务性作用域内的作用域或不是事务性的业务流程。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-126">You cannot nest a transactional scope within a scope or orchestration that is not transactional.</span></span> <span data-ttu-id="ccc1c-127">封闭作用域或不是事务性的业务流程将不管理状态，因为它必须能够正确处理其中任何作用域的状态管理。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-127">An enclosing scope or orchestration that is not transactional will not manage state, as it must to properly handle the state management of any scopes within it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccc1c-128">同步的事务不能包括任何其他事务或同步的作用域。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-128">A synchronized transaction cannot include any other transactions or synchronized scopes.</span></span>  
  
## <a name="compensation"></a><span data-ttu-id="ccc1c-129">补偿</span><span class="sxs-lookup"><span data-stu-id="ccc1c-129">Compensation</span></span>  
 <span data-ttu-id="ccc1c-130">一个长时间运行的事务可以指定将调用以补偿该事务的活动后提交的补偿模块。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-130">A long-running transaction can specify a compensation block that will be called to compensate for the transaction's activities, after it commits.</span></span> <span data-ttu-id="ccc1c-131">它可能只需撤消事务，如果可行，或执行某些其他功能，例如通知，帮助减轻以某种方式事务的影响。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-131">It might simply undo the transaction where feasible, or perform some other function, such as notification, that helps mitigate the effects of the transaction in some way.</span></span> <span data-ttu-id="ccc1c-132">如果不添加你自己的补偿代码，运行时引擎将默认情况下调用的内部事务运行时间较长，原子的补偿模块按相反的顺序，与上次提交的事务开始和完成的第一个提交的事务。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-132">If you do not add your own compensation code, the runtime engine will by default call the compensation blocks of the inner transactions, both long-running and atomic, in reverse order, starting with the last transaction committed and finishing with the first transaction committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccc1c-133">补偿只能对已成功提交的事务。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-133">Compensation can only be done on a transaction that has committed successfully.</span></span>  
  
## <a name="fault-tolerance"></a><span data-ttu-id="ccc1c-134">容错</span><span class="sxs-lookup"><span data-stu-id="ccc1c-134">Fault tolerance</span></span>  
 <span data-ttu-id="ccc1c-135">事务支持容错，从恢复内部错误 （例如机器故障和软件故障） 以及外部错误 （例如取消消息）。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-135">Transactions support fault tolerance for recovery from both internal faults (such as machine failures and software faults) and external faults (such as cancel messages).</span></span> <span data-ttu-id="ccc1c-136">长时间运行的事务内的部分更新将不会回滚自动当发生事务失败，因为它们位于 ACID 事务。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-136">Partial updates within long-running transactions are not rolled back automatically when a transaction failure occurs, as they are in ACID transactions.</span></span>  
  
 <span data-ttu-id="ccc1c-137">在发生错误时调用长时间运行事务的异常代码块。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-137">The exception code block for the long-running transaction is called when a fault occurs.</span></span> <span data-ttu-id="ccc1c-138">异常代码块包含一组您编写的任何事务执行期间可能出现的错误处理的错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-138">The exception code block contains a set of fault handlers that you write to deal with any of the faults that can arise during the execution of the transaction.</span></span> <span data-ttu-id="ccc1c-139">您可以借助消息、 变量和对象处理错误的最后一个已知状态。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-139">You can rely on the last known state of the messages, variables, and objects in handling the fault.</span></span>  
  
 <span data-ttu-id="ccc1c-140">您通常希望异常处理程序评估在发生异常时业务流程的状态、 执行任何必要的操作，根据该状态，以及在调用任何嵌套事务的补偿。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-140">You will typically want your exception handler to evaluate the state of the orchestration at the time the exception occurs, take any necessary action based on that state, and call the compensations of any nested transactions.</span></span>  
  
 <span data-ttu-id="ccc1c-141">在发生错误时中断长时间运行事务的执行。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-141">The execution of the long-running transaction is interrupted when a fault occurs.</span></span> <span data-ttu-id="ccc1c-142">发生错误后无法恢复它。</span><span class="sxs-lookup"><span data-stu-id="ccc1c-142">It cannot be resumed after a fault occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc1c-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccc1c-143">See Also</span></span>  
 <span data-ttu-id="ccc1c-144">[使用长时间运行事务的方案](../core/scenarios-using-long-running-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="ccc1c-144">[Scenarios Using Long-Running Transactions](../core/scenarios-using-long-running-transactions.md) </span></span>  
 <span data-ttu-id="ccc1c-145">[原子事务](../core/atomic-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="ccc1c-145">[Atomic Transactions](../core/atomic-transactions.md) </span></span>  
 [<span data-ttu-id="ccc1c-146">使用事务和处理异常</span><span class="sxs-lookup"><span data-stu-id="ccc1c-146">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)