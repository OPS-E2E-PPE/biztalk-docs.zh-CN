---
title: "原子事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- atomic transactions
- scopes, examples
- transactions, orchestrations
- orchestrations, transactions
- transactions, isolation levels
- transactions, ACID concept
- transactions, examples
- transactions, atomic
- scopes, transactions
- scopes
ms.assetid: 5030e1fd-943f-42bc-9296-4f315bd5f733
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc07f379c1f7aa1c846b2c20c19cbfb3393e8174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="atomic-transactions"></a><span data-ttu-id="67152-102">原子事务</span><span class="sxs-lookup"><span data-stu-id="67152-102">Atomic Transactions</span></span>
<span data-ttu-id="67152-103">BizTalk 业务流程可设计为按照事务的传统“ACID”概念，执行不同部分的工作。</span><span class="sxs-lookup"><span data-stu-id="67152-103">BizTalk orchestrations can be designed to run discrete pieces of work, following the classic 'ACID' concept of a transaction.</span></span> <span data-ttu-id="67152-104">在执行时，这些离散的或原子的工作单位会将业务流程从一个一致的状态转移到独立于其他工作单位的一致且持久的新状态。</span><span class="sxs-lookup"><span data-stu-id="67152-104">These discrete or atomic units of work, when performed, move the business process from one consistent state to a new, consistent and durable state that is isolated from other units of work.</span></span> <span data-ttu-id="67152-105">这通常是通过使用**作用域**构造，用于封装的与事务的语义的工作单元。</span><span class="sxs-lookup"><span data-stu-id="67152-105">This is typically done by using the **Scope** construct that encapsulates the units of work with the transactional semantics.</span></span> <span data-ttu-id="67152-106">也可以将整个业务流程定义为一个原子事务，而不使用作用域。</span><span class="sxs-lookup"><span data-stu-id="67152-106">The entire orchestration can also be defined as an atomic transaction without the use of scopes.</span></span> <span data-ttu-id="67152-107">但是，这些作用域不能标记为事务性的，除非业务流程本身标记为长期或原子事务类型。</span><span class="sxs-lookup"><span data-stu-id="67152-107">The scopes, however, cannot be marked as transactional unless the orchestration itself is marked as a long running or atomic transaction type.</span></span> <span data-ttu-id="67152-108">原子事务保证在事务性更新期间发生故障时可自动回滚任何部分更新，并且消除事务的影响（事务中进行的任何 .NET 调用的影响除外）。</span><span class="sxs-lookup"><span data-stu-id="67152-108">Atomic transactions guarantee that any partial updates are rolled back automatically in the event of a failure during the transactional update, and that the effects of the transaction are erased (except for the effects of any .NET calls that are made in the transaction).</span></span> <span data-ttu-id="67152-109">BizTalk 业务流程中的原子事务与分布式事务处理协调器 (DTC) 事务大体相似，只是前者通常存活时间较短并且具有四个“ACID”属性（原子性、一致性、隔离性和持久性）：</span><span class="sxs-lookup"><span data-stu-id="67152-109">Atomic transactions in BizTalk orchestrations are similar to distributed transaction coordinator (DTC) transactions in that they are generally short-lived and have the four "ACID" attributes (atomicity, consistency, isolation, and durability):</span></span>  
  
-   <span data-ttu-id="67152-110">**原子性**</span><span class="sxs-lookup"><span data-stu-id="67152-110">**Atomicity**</span></span>  
  
     <span data-ttu-id="67152-111">一个事务就表示一个原子的工作单位。</span><span class="sxs-lookup"><span data-stu-id="67152-111">A transaction represents an atomic unit of work.</span></span> <span data-ttu-id="67152-112">要么在事务内执行所有修改，要么不执行任何修改。</span><span class="sxs-lookup"><span data-stu-id="67152-112">Either all modifications within a transaction are performed, or none of the modifications are performed.</span></span>  
  
-   <span data-ttu-id="67152-113">**一致性**</span><span class="sxs-lookup"><span data-stu-id="67152-113">**Consistency**</span></span>  
  
     <span data-ttu-id="67152-114">在提交时，事务必须在系统内保持数据的整体性。</span><span class="sxs-lookup"><span data-stu-id="67152-114">When committed, a transaction must preserve the integrity of the data within the system.</span></span> <span data-ttu-id="67152-115">如果某一事务在该事务开始前对已在内部保持了一致的数据库执行数据修改，则在提交该事务时，数据库仍必须在内部保持一致。</span><span class="sxs-lookup"><span data-stu-id="67152-115">If a transaction performs a data modification on a database that was internally consistent before the transaction started, the database must still be internally consistent when the transaction is committed.</span></span> <span data-ttu-id="67152-116">确保此属性的工作主要由应用程序开发人员负责。</span><span class="sxs-lookup"><span data-stu-id="67152-116">Ensuring this property is largely the responsibility of the application developer.</span></span>  
  
-   <span data-ttu-id="67152-117">**隔离**</span><span class="sxs-lookup"><span data-stu-id="67152-117">**Isolation**</span></span>  
  
     <span data-ttu-id="67152-118">并行事务进行的修改必须与其他并行事务进行的修改隔离。</span><span class="sxs-lookup"><span data-stu-id="67152-118">Modifications made by concurrent transactions must be isolated from the modifications made by other concurrent transactions.</span></span> <span data-ttu-id="67152-119">并行运行的隔离事务所执行的修改将保持内部数据库一致性，与顺序运行事务完全一样。</span><span class="sxs-lookup"><span data-stu-id="67152-119">Isolated transactions that run concurrently perform modifications that preserve internal database consistency exactly as they would if the transactions were run serially.</span></span>  
  
-   <span data-ttu-id="67152-120">**持续性**</span><span class="sxs-lookup"><span data-stu-id="67152-120">**Durability**</span></span>  
  
     <span data-ttu-id="67152-121">在提交某一事务后，默认情况下所有修改都永久存在于系统中。</span><span class="sxs-lookup"><span data-stu-id="67152-121">After a transaction is committed, all modifications are permanently in place in the system by default.</span></span> <span data-ttu-id="67152-122">即使系统发生故障，这些修改也存在。</span><span class="sxs-lookup"><span data-stu-id="67152-122">The modifications persist even if a system failure occurs.</span></span>  
  
 <span data-ttu-id="67152-123">在 BizTalk 业务流程中使用的原子事务支持以下隔离级别：</span><span class="sxs-lookup"><span data-stu-id="67152-123">The following isolation levels are supported by the atomic transactions used in BizTalk Orchestrations:</span></span>  
  
-   <span data-ttu-id="67152-124">**读提交**</span><span class="sxs-lookup"><span data-stu-id="67152-124">**Read Committed**</span></span>  
  
     <span data-ttu-id="67152-125">在正在读取数据时保持共享锁，以避免脏读，但是在事务结束之前可以更改数据，从而导致不可重复的读取或幻像数据。</span><span class="sxs-lookup"><span data-stu-id="67152-125">Shared locks are held while the data is being read to avoid dirty reads, but the data can be changed before the end of the transaction, resulting in non-repeatable reads or phantom data.</span></span>  
  
-   <span data-ttu-id="67152-126">**Repeatable Read**</span><span class="sxs-lookup"><span data-stu-id="67152-126">**Repeatable Read**</span></span>  
  
     <span data-ttu-id="67152-127">在查询中使用的所有数据上放置锁，以防止其他用户更新这些数据。</span><span class="sxs-lookup"><span data-stu-id="67152-127">Locks are placed on all data that is used in a query, preventing other users from updating the data.</span></span> <span data-ttu-id="67152-128">这防止了不可重复的读取，但仍有可能产生幻像行。</span><span class="sxs-lookup"><span data-stu-id="67152-128">This prevents non-repeatable reads, but phantom rows are still possible.</span></span>  
  
-   <span data-ttu-id="67152-129">**可序列化**</span><span class="sxs-lookup"><span data-stu-id="67152-129">**Serializable**</span></span>  
  
     <span data-ttu-id="67152-130">放置一个范围锁，防止在事务完成前其他用户更新行或将行插入数据库中。</span><span class="sxs-lookup"><span data-stu-id="67152-130">A range lock is placed preventing other users from updating or inserting rows into the database until the transaction is complete.</span></span>  
  
 <span data-ttu-id="67152-131">BizTalk Server 确保原子事务内的状态变化（例如对变量、消息和对象的修改）只在事务提交后在原子事务的作用域外可见。</span><span class="sxs-lookup"><span data-stu-id="67152-131">BizTalk Server ensures that state changes within an atomic transaction—such as modifications to variables, messages, and objects—are visible outside the scope of the atomic transaction only upon commitment of the transaction.</span></span> <span data-ttu-id="67152-132">中间状态的变化将与业务流程的其他部分隔离开来。</span><span class="sxs-lookup"><span data-stu-id="67152-132">The intermediate state changes are isolated from other parts of an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67152-133">如果原子事务包含**接收**形状，**发送**形状，或**启动 Orchestration**形状，相应的操作不会发生之前事务已提交。</span><span class="sxs-lookup"><span data-stu-id="67152-133">If an atomic transaction contains a **Receive** shape, a **Send** shape, or a **Start Orchestration** shape, the corresponding actions will not take place until the transaction has committed.</span></span>  
  
 <span data-ttu-id="67152-134">如果您要求对数据具有完全的 ACID 属性（例如，数据必须独立于其他事务），则必须只使用原子事务。</span><span class="sxs-lookup"><span data-stu-id="67152-134">If you require full ACID properties on the data—for example, when the data must be isolated from other transactions—you must use atomic transactions exclusively.</span></span>  
  
 <span data-ttu-id="67152-135">在原子事务失败时，所有状态都将重置，就像业务流程实例从来没有进入该作用域。</span><span class="sxs-lookup"><span data-stu-id="67152-135">When an atomic transaction fails, all states are reset as if the orchestration instance never entered the scope.</span></span> <span data-ttu-id="67152-136">BizTalk 针对原子事务的规则是：所有变量（而不只是作用域的本地变量）都参与该事务。</span><span class="sxs-lookup"><span data-stu-id="67152-136">The rule BizTalk has for atomic transactions is that all variables (not just local to the scope) participate in the transaction.</span></span> <span data-ttu-id="67152-137">在原子事务中使用的所有非序列化变量和消息都应声明为对作用域而言是本地的；否则，编译器将显示“变量…未标记为可序列化”错误。</span><span class="sxs-lookup"><span data-stu-id="67152-137">All non-serializable variables and messages used in an atomic transaction should be declared local to the scope; otherwise, the compiler will give the "variable….is not marked as serializable" error.</span></span> <span data-ttu-id="67152-138">所有原子作用域都将认为是“同步的”，并且如果实际上将同步的关键字用于原子作用域，则业务流程编译器将对冗余的使用发出警告。</span><span class="sxs-lookup"><span data-stu-id="67152-138">All atomic scopes are assumed to be "synchronized" and the orchestration compiler will provide a warning for redundant usage, if indeed the synchronized keyword is used for atomic scopes.</span></span> <span data-ttu-id="67152-139">共享数据的同步将从作用域开始一直扩展到作用域成功完成（包括在作用域结束时的状态持久化），或者扩展到异常处理程序完成时（如果出现错误）。</span><span class="sxs-lookup"><span data-stu-id="67152-139">The synchronization for the shared data extends from the beginning of the scope until the successful completion of the scope (including the state persistence at the end of the scope) or to the completion of the exception handler (in case of errors).</span></span> <span data-ttu-id="67152-140">同步域并不扩展到补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="67152-140">The synchronization domain does not extend to the compensation handler.</span></span>  
  
 <span data-ttu-id="67152-141">原子事务可与超时值（此时，业务流程将停止事务并且实例将挂起）相关联。</span><span class="sxs-lookup"><span data-stu-id="67152-141">Atomic transactions can be associated with timeout values at which point the orchestration will stop the transaction and the instance will be suspended.</span></span> <span data-ttu-id="67152-142">如果某一原子事务包含接收形状、发送形状或启动业务流程形状，则相应操作将不会在提交该事务前发生。</span><span class="sxs-lookup"><span data-stu-id="67152-142">If an atomic transaction contains a Receive shape, a Send shape, or a Start Orchestration shape, the corresponding actions will not take place until the transaction has committed.</span></span>  
  
 <span data-ttu-id="67152-143">在用户有意引发时就会重试原子事务**RetryTransactionException**或如果**PersistenceException**原子事务尝试提交时引发。</span><span class="sxs-lookup"><span data-stu-id="67152-143">An atomic transaction retries when the user deliberately throws a **RetryTransactionException** or if a **PersistenceException** is raised at the time that the atomic transaction tries to commit.</span></span> <span data-ttu-id="67152-144">例如，如果原子事务是分布式 DTC 事务的一部分，而该事务中的其他参与者停止了该事务，则可能会引发 PersistenceException。</span><span class="sxs-lookup"><span data-stu-id="67152-144">The latter could happen if for instance, the atomic transaction was part of a distributed DTC transaction and some other participant in that transaction stopped the transaction.</span></span> <span data-ttu-id="67152-145">同样，如果事务已尝试提交时没有数据库连接问题，则还不存在**PersistenceException**引发。</span><span class="sxs-lookup"><span data-stu-id="67152-145">Likewise, if there were database connectivity problems at the time when the transaction was trying to commit, there would also be a **PersistenceException** raised.</span></span> <span data-ttu-id="67152-146">如果发生这种情况为具有一个原子作用域**重试 = True**，然后它将重试 21 次。</span><span class="sxs-lookup"><span data-stu-id="67152-146">If this happens for an atomic scope that has **Retry=True**, then it will retry up to 21 times.</span></span> <span data-ttu-id="67152-147">默认情况下，每次重试之间的延迟为 2 秒（但可以修改该默认值）。</span><span class="sxs-lookup"><span data-stu-id="67152-147">The delay between each retry is two seconds by default (but that is modifiable).</span></span> <span data-ttu-id="67152-148">在执行完全部 21 次重试后，如果该事务仍无法提交，则挂起整个业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="67152-148">After 21 retries are exhausted, if the transaction is still unable to commit, the whole orchestration instance is suspended.</span></span> <span data-ttu-id="67152-149">该实例可以手动恢复，并且将从冲突的原子作用域的开始处使用新计数器重新开始。</span><span class="sxs-lookup"><span data-stu-id="67152-149">It can be manually resumed and it will start over again, with a fresh counter, from the beginning of the offending atomic scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67152-150">仅**RetryTransactionException**和**PersistenceException**可能会导致原子作用域以重试。</span><span class="sxs-lookup"><span data-stu-id="67152-150">Only the **RetryTransactionException** and **PersistenceException** can cause an atomic scope to retry.</span></span> <span data-ttu-id="67152-151">在原子作用域中引发的任何其他异常不会导致它要重试，即使**重试**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="67152-151">Any other exception raised in an atomic scope cannot cause it to retry, even if the **Retry** property is set to **True**.</span></span> <span data-ttu-id="67152-152">可以通过上使用的公共属性重写每个两个连续重试之间的两个第二个默认延迟**RetryTransactionException** （如果这是正在使用会导致重试的异常）。</span><span class="sxs-lookup"><span data-stu-id="67152-152">The two-second default delay between each two consecutive retries can be overridden by using a public property on **RetryTransactionException** (if that is the exception that is being used to cause the retries).</span></span>  
  
 <span data-ttu-id="67152-153">原子作用域具有对嵌套其他事务不能嵌套其他事务或包括限制**捕获的异常**块。</span><span class="sxs-lookup"><span data-stu-id="67152-153">The atomic scopes have restrictions on nesting other transactions that cannot nest other transactions or include **Catch - Exception** blocks.</span></span>  
  
## <a name="dtc-transactions"></a><span data-ttu-id="67152-154">DTC 事务</span><span class="sxs-lookup"><span data-stu-id="67152-154">DTC transactions</span></span>  
 <span data-ttu-id="67152-155">尽管原子事务在行为上类似 DTC 事务，但默认情况下，它们并不是显式的 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="67152-155">While atomic transactions behave like DTC transactions, they are not explicitly DTC transactions by default.</span></span> <span data-ttu-id="67152-156">您可以显式地使这些事务成为 DTC 事务，只要要在该事务中使用的任何对象都是从 System.EnterpriseServices.ServicedComponents 派生的 COM+ 对象，并且隔离级别在事务组件之间达成一致。</span><span class="sxs-lookup"><span data-stu-id="67152-156">You can explicitly make them DTC transactions, provided that any objects being used in the transaction are COM+ objects derived from System.EnterpriseServices.ServicedComponents, and that isolation levels agree between transaction components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67152-157">一个原子事务不能包含任何其他事务，也不能包含异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="67152-157">An atomic transaction cannot contain any other transactions within it, nor can it contain exception handlers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67152-158">一个原子事务不能包含匹配的发送和接收操作，即，请求-响应对或使用同一相关集的发送和接收。</span><span class="sxs-lookup"><span data-stu-id="67152-158">An atomic transaction cannot contain matching send and receive actions—that is, a request-response pair or a send and receive that use the same correlation set.</span></span>  
  
## <a name="non-serializable-objects"></a><span data-ttu-id="67152-159">非可序列化对象</span><span class="sxs-lookup"><span data-stu-id="67152-159">Non-serializable objects</span></span>  
 <span data-ttu-id="67152-160">如果您想要在某一业务流程内使用非序列化对象，则必须只在原子事务内使用它。</span><span class="sxs-lookup"><span data-stu-id="67152-160">If you want to use a non-serializable object within an orchestration, you must use it only within an atomic transaction.</span></span> <span data-ttu-id="67152-161">只要业务流程由引擎保存，在原子事务外使用此类对象都可能会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="67152-161">Any use of such an object outside of an atomic transaction risks data loss whenever the orchestration is persisted by the engine.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="67152-162">每个原子作用域都表示一个持久化点，这意味着业务流程的状态将在每个持久化点保存到数据库。</span><span class="sxs-lookup"><span data-stu-id="67152-162">Each Atomic scope represents a persistence point and what that means is the state of the orchestration is saved to the database at each persistence point.</span></span> <span data-ttu-id="67152-163">广泛使用原子作用域将增加业务流程中的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="67152-163">Extensive use of Atomic scope will increase the latency in the orchestration.</span></span> <span data-ttu-id="67152-164">代替出于创建非序列化对象目的而使用原子作用域，您可以使用不要求原子作用域的静态方法调用，从而无需持久化点。</span><span class="sxs-lookup"><span data-stu-id="67152-164">Instead of using Atomic scope for the purpose of creating non-serializable objects, you can use Static method calls which they don not require Atomic scopes, thus eliminating the need for the persistence points.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67152-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67152-165">See Also</span></span>  
 <span data-ttu-id="67152-166">[使用原子事务的方案](../core/scenarios-using-atomic-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="67152-166">[Scenarios Using Atomic Transactions](../core/scenarios-using-atomic-transactions.md) </span></span>  
 [<span data-ttu-id="67152-167">长时间运行的事务</span><span class="sxs-lookup"><span data-stu-id="67152-167">Long-Running Transactions</span></span>](../core/long-running-transactions.md)