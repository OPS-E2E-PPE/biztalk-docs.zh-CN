---
title: 原子事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79512ead7a9ec91fe1558643fa66747e6674eee6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530696"
---
# <a name="atomic-transactions"></a><span data-ttu-id="926b5-102">原子事务</span><span class="sxs-lookup"><span data-stu-id="926b5-102">Atomic Transactions</span></span>
<span data-ttu-id="926b5-103">BizTalk 业务流程可以用于运行不同部分的工作，按照事务的传统 ACID 概念。</span><span class="sxs-lookup"><span data-stu-id="926b5-103">BizTalk orchestrations can be designed to run discrete pieces of work, following the classic 'ACID' concept of a transaction.</span></span> <span data-ttu-id="926b5-104">工作，在执行时，这些离散的或原子单元将业务流程从一个一致的状态移到新的、 一致和持久的状态独立于其他工作单位。</span><span class="sxs-lookup"><span data-stu-id="926b5-104">These discrete or atomic units of work, when performed, move the business process from one consistent state to a new, consistent and durable state that is isolated from other units of work.</span></span> <span data-ttu-id="926b5-105">这通常是通过使用**作用域**构造，它封装的使用事务性语义的工作单元。</span><span class="sxs-lookup"><span data-stu-id="926b5-105">This is typically done by using the **Scope** construct that encapsulates the units of work with the transactional semantics.</span></span> <span data-ttu-id="926b5-106">此外可以为无需使用一个原子事务的作用域定义整个业务流程。</span><span class="sxs-lookup"><span data-stu-id="926b5-106">The entire orchestration can also be defined as an atomic transaction without the use of scopes.</span></span> <span data-ttu-id="926b5-107">作用域，但是，不能标记为事务性的除非业务流程本身标记为长期或原子事务类型。</span><span class="sxs-lookup"><span data-stu-id="926b5-107">The scopes, however, cannot be marked as transactional unless the orchestration itself is marked as a long running or atomic transaction type.</span></span> <span data-ttu-id="926b5-108">原子事务保证，任何部分更新自动发生故障时在过程中回滚事务的更新，并将删除事务的影响 (除外的任何.NET 调用中所做的效果事务）。</span><span class="sxs-lookup"><span data-stu-id="926b5-108">Atomic transactions guarantee that any partial updates are rolled back automatically in the event of a failure during the transactional update, and that the effects of the transaction are erased (except for the effects of any .NET calls that are made in the transaction).</span></span> <span data-ttu-id="926b5-109">BizTalk 业务流程中的原子事务是类似于分布式的事务处理协调器 (DTC) 事务，因为它们生存期通常较短并且具有四个"ACID"属性 （原子性、 一致性、 隔离和持续性）：</span><span class="sxs-lookup"><span data-stu-id="926b5-109">Atomic transactions in BizTalk orchestrations are similar to distributed transaction coordinator (DTC) transactions in that they are generally short-lived and have the four "ACID" attributes (atomicity, consistency, isolation, and durability):</span></span>  
  
- <span data-ttu-id="926b5-110">**原子性**</span><span class="sxs-lookup"><span data-stu-id="926b5-110">**Atomicity**</span></span>  
  
   <span data-ttu-id="926b5-111">一个事务就表示原子工作单元。</span><span class="sxs-lookup"><span data-stu-id="926b5-111">A transaction represents an atomic unit of work.</span></span> <span data-ttu-id="926b5-112">要么执行事务内的所有修改，要么不都执行任何所做的修改。</span><span class="sxs-lookup"><span data-stu-id="926b5-112">Either all modifications within a transaction are performed, or none of the modifications are performed.</span></span>  
  
- <span data-ttu-id="926b5-113">**一致性**</span><span class="sxs-lookup"><span data-stu-id="926b5-113">**Consistency**</span></span>  
  
   <span data-ttu-id="926b5-114">在提交时，事务必须保留在系统中的数据的完整性。</span><span class="sxs-lookup"><span data-stu-id="926b5-114">When committed, a transaction must preserve the integrity of the data within the system.</span></span> <span data-ttu-id="926b5-115">如果事务是该事务开始前内部一致的数据库上执行数据修改，数据库仍必须在内部一致提交事务时。</span><span class="sxs-lookup"><span data-stu-id="926b5-115">If a transaction performs a data modification on a database that was internally consistent before the transaction started, the database must still be internally consistent when the transaction is committed.</span></span> <span data-ttu-id="926b5-116">确保此属性是很大程度上应用程序开发人员的责任。</span><span class="sxs-lookup"><span data-stu-id="926b5-116">Ensuring this property is largely the responsibility of the application developer.</span></span>  
  
- <span data-ttu-id="926b5-117">**隔离**</span><span class="sxs-lookup"><span data-stu-id="926b5-117">**Isolation**</span></span>  
  
   <span data-ttu-id="926b5-118">由并发事务所做的修改必须与其他并发事务所做的修改隔离。</span><span class="sxs-lookup"><span data-stu-id="926b5-118">Modifications made by concurrent transactions must be isolated from the modifications made by other concurrent transactions.</span></span> <span data-ttu-id="926b5-119">并发运行的隔离级别事务执行的修改将保持内部数据库一致性，如果按顺序运行事务的样子。</span><span class="sxs-lookup"><span data-stu-id="926b5-119">Isolated transactions that run concurrently perform modifications that preserve internal database consistency exactly as they would if the transactions were run serially.</span></span>  
  
- <span data-ttu-id="926b5-120">**持续性**</span><span class="sxs-lookup"><span data-stu-id="926b5-120">**Durability**</span></span>  
  
   <span data-ttu-id="926b5-121">提交事务后，所有修改都都永久就地默认情况下在系统中。</span><span class="sxs-lookup"><span data-stu-id="926b5-121">After a transaction is committed, all modifications are permanently in place in the system by default.</span></span> <span data-ttu-id="926b5-122">即使系统发生故障，持久保存所做的修改。</span><span class="sxs-lookup"><span data-stu-id="926b5-122">The modifications persist even if a system failure occurs.</span></span>  
  
  <span data-ttu-id="926b5-123">使用 BizTalk 业务流程中的原子事务支持以下隔离级别：</span><span class="sxs-lookup"><span data-stu-id="926b5-123">The following isolation levels are supported by the atomic transactions used in BizTalk Orchestrations:</span></span>  
  
- <span data-ttu-id="926b5-124">**已提交读**</span><span class="sxs-lookup"><span data-stu-id="926b5-124">**Read Committed**</span></span>  
  
   <span data-ttu-id="926b5-125">正在读取数据以避免脏读，但可以结束该事务，从而导致不可重复读取或幻像数据之前更改数据时保持共享的锁。</span><span class="sxs-lookup"><span data-stu-id="926b5-125">Shared locks are held while the data is being read to avoid dirty reads, but the data can be changed before the end of the transaction, resulting in non-repeatable reads or phantom data.</span></span>  
  
- <span data-ttu-id="926b5-126">**可重复读**</span><span class="sxs-lookup"><span data-stu-id="926b5-126">**Repeatable Read**</span></span>  
  
   <span data-ttu-id="926b5-127">在查询中，从而阻止其他用户更新的数据所使用的所有数据上放置锁。</span><span class="sxs-lookup"><span data-stu-id="926b5-127">Locks are placed on all data that is used in a query, preventing other users from updating the data.</span></span> <span data-ttu-id="926b5-128">这防止了不可重复读取，但有仍有可能产生幻像行。</span><span class="sxs-lookup"><span data-stu-id="926b5-128">This prevents non-repeatable reads, but phantom rows are still possible.</span></span>  
  
- <span data-ttu-id="926b5-129">**可序列化**</span><span class="sxs-lookup"><span data-stu-id="926b5-129">**Serializable**</span></span>  
  
   <span data-ttu-id="926b5-130">防止其他用户更新或将行插入到数据库，在事务完成之前放置范围锁。</span><span class="sxs-lookup"><span data-stu-id="926b5-130">A range lock is placed preventing other users from updating or inserting rows into the database until the transaction is complete.</span></span>  
  
  <span data-ttu-id="926b5-131">BizTalk Server 确保原子事务内的状态变化 — 例如对变量、 消息和对象的修改 — 仅在事务提交后在原子事务的作用域外可见。</span><span class="sxs-lookup"><span data-stu-id="926b5-131">BizTalk Server ensures that state changes within an atomic transaction—such as modifications to variables, messages, and objects—are visible outside the scope of the atomic transaction only upon commitment of the transaction.</span></span> <span data-ttu-id="926b5-132">中间状态的变化是独立于业务流程的其他部分。</span><span class="sxs-lookup"><span data-stu-id="926b5-132">The intermediate state changes are isolated from other parts of an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="926b5-133">如果某一原子事务包含**接收**形状**发送**形状，或**启动业务流程**形状，则相应操作不会发生之前事务已提交。</span><span class="sxs-lookup"><span data-stu-id="926b5-133">If an atomic transaction contains a **Receive** shape, a **Send** shape, or a **Start Orchestration** shape, the corresponding actions will not take place until the transaction has committed.</span></span>  
  
 <span data-ttu-id="926b5-134">如果需要完整的 ACID 属性的数据 — 例如，当数据必须是独立于其他事务，必须以独占方式使用原子事务。</span><span class="sxs-lookup"><span data-stu-id="926b5-134">If you require full ACID properties on the data—for example, when the data must be isolated from other transactions—you must use atomic transactions exclusively.</span></span>  
  
 <span data-ttu-id="926b5-135">当某一原子事务失败时，所有状态将重都置，如同业务流程实例永远不会进入该作用域。</span><span class="sxs-lookup"><span data-stu-id="926b5-135">When an atomic transaction fails, all states are reset as if the orchestration instance never entered the scope.</span></span> <span data-ttu-id="926b5-136">该规则 BizTalk 具有原子事务是所有变量 （而不仅仅是本地的范围） 都参与该事务。</span><span class="sxs-lookup"><span data-stu-id="926b5-136">The rule BizTalk has for atomic transactions is that all variables (not just local to the scope) participate in the transaction.</span></span> <span data-ttu-id="926b5-137">所有不可序列化的变量和使用原子事务中的消息应声明为作用域; 的本地否则，编译器将产生"变量...未标记为可序列化"错误。</span><span class="sxs-lookup"><span data-stu-id="926b5-137">All non-serializable variables and messages used in an atomic transaction should be declared local to the scope; otherwise, the compiler will give the "variable….is not marked as serializable" error.</span></span> <span data-ttu-id="926b5-138">所有原子作用域被认为"同步"和业务流程编译器将提供对冗余的使用，一条警告，如果确实同步的关键字用于原子作用域。</span><span class="sxs-lookup"><span data-stu-id="926b5-138">All atomic scopes are assumed to be "synchronized" and the orchestration compiler will provide a warning for redundant usage, if indeed the synchronized keyword is used for atomic scopes.</span></span> <span data-ttu-id="926b5-139">共享数据的同步扩展从直到成功完成 （包括范围的结束时的状态持久化） 的作用域范围的开始或完成的异常处理程序 （如果出错）。</span><span class="sxs-lookup"><span data-stu-id="926b5-139">The synchronization for the shared data extends from the beginning of the scope until the successful completion of the scope (including the state persistence at the end of the scope) or to the completion of the exception handler (in case of errors).</span></span> <span data-ttu-id="926b5-140">同步域不会扩展到补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="926b5-140">The synchronization domain does not extend to the compensation handler.</span></span>  
  
 <span data-ttu-id="926b5-141">原子事务可以与该业务流程将停止事务并且实例的点就将挂起超时值相关联。</span><span class="sxs-lookup"><span data-stu-id="926b5-141">Atomic transactions can be associated with timeout values at which point the orchestration will stop the transaction and the instance will be suspended.</span></span> <span data-ttu-id="926b5-142">如果原子事务包含接收形状、 发送形状或启动业务流程形状，则相应操作之前不会发生提交该事务。</span><span class="sxs-lookup"><span data-stu-id="926b5-142">If an atomic transaction contains a Receive shape, a Send shape, or a Start Orchestration shape, the corresponding actions will not take place until the transaction has committed.</span></span>  
  
 <span data-ttu-id="926b5-143">原子事务重试时用户故意引发**RetryTransactionException**或者如果**PersistenceException**在原子事务尝试提交时引发。</span><span class="sxs-lookup"><span data-stu-id="926b5-143">An atomic transaction retries when the user deliberately throws a **RetryTransactionException** or if a **PersistenceException** is raised at the time that the atomic transaction tries to commit.</span></span> <span data-ttu-id="926b5-144">例如，在原子事务是分布式的 DTC 事务和一些其他参与者的一部分，停止该事务的事务时，可能发生后一种。</span><span class="sxs-lookup"><span data-stu-id="926b5-144">The latter could happen if for instance, the atomic transaction was part of a distributed DTC transaction and some other participant in that transaction stopped the transaction.</span></span> <span data-ttu-id="926b5-145">同样，如果在事务正尝试提交的时存在数据库连接问题，则也可能**PersistenceException**引发。</span><span class="sxs-lookup"><span data-stu-id="926b5-145">Likewise, if there were database connectivity problems at the time when the transaction was trying to commit, there would also be a **PersistenceException** raised.</span></span> <span data-ttu-id="926b5-146">如果发生这种情况有的原子作用域**重试 = True**，则它将重试最多 21 次。</span><span class="sxs-lookup"><span data-stu-id="926b5-146">If this happens for an atomic scope that has **Retry=True**, then it will retry up to 21 times.</span></span> <span data-ttu-id="926b5-147">每次重试之间的延迟为 2 秒默认情况下 （但这是可修改）。</span><span class="sxs-lookup"><span data-stu-id="926b5-147">The delay between each retry is two seconds by default (but that is modifiable).</span></span> <span data-ttu-id="926b5-148">21 次重试已经耗尽，如果仍无法提交事务后，则挂起整个业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="926b5-148">After 21 retries are exhausted, if the transaction is still unable to commit, the whole orchestration instance is suspended.</span></span> <span data-ttu-id="926b5-149">可以手动恢复，并且它将重新开始，使用新的计数器，从冲突原子作用域的开头。</span><span class="sxs-lookup"><span data-stu-id="926b5-149">It can be manually resumed and it will start over again, with a fresh counter, from the beginning of the offending atomic scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="926b5-150">仅**RetryTransactionException**并**PersistenceException**可能会导致原子作用域以重试。</span><span class="sxs-lookup"><span data-stu-id="926b5-150">Only the **RetryTransactionException** and **PersistenceException** can cause an atomic scope to retry.</span></span> <span data-ttu-id="926b5-151">在原子作用域中引发的任何其他异常不会导致它重试，即使**重试**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="926b5-151">Any other exception raised in an atomic scope cannot cause it to retry, even if the **Retry** property is set to **True**.</span></span> <span data-ttu-id="926b5-152">每个两个连续重试之间的两个 2 秒的默认延迟可以通过使用公共属性上重写**RetryTransactionException** （如果这是用于导致重试的异常）。</span><span class="sxs-lookup"><span data-stu-id="926b5-152">The two-second default delay between each two consecutive retries can be overridden by using a public property on **RetryTransactionException** (if that is the exception that is being used to cause the retries).</span></span>  
  
 <span data-ttu-id="926b5-153">原子作用域具有对嵌套其他事务不能嵌套其他事务或包括的限制**捕获的异常**块。</span><span class="sxs-lookup"><span data-stu-id="926b5-153">The atomic scopes have restrictions on nesting other transactions that cannot nest other transactions or include **Catch - Exception** blocks.</span></span>  
  
## <a name="dtc-transactions"></a><span data-ttu-id="926b5-154">DTC 事务</span><span class="sxs-lookup"><span data-stu-id="926b5-154">DTC transactions</span></span>  
 <span data-ttu-id="926b5-155">尽管原子事务在行为上类似 DTC 事务，它们不是显式默认的 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="926b5-155">While atomic transactions behave like DTC transactions, they are not explicitly DTC transactions by default.</span></span> <span data-ttu-id="926b5-156">您可以显式使它们 DTC 事务，前提是用在事务中任何对象是 COM + 对象是从 System.EnterpriseServices.ServicedComponents，派生和隔离级别事务组件之间达成一致。</span><span class="sxs-lookup"><span data-stu-id="926b5-156">You can explicitly make them DTC transactions, provided that any objects being used in the transaction are COM+ objects derived from System.EnterpriseServices.ServicedComponents, and that isolation levels agree between transaction components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="926b5-157">原子事务不能包含任何其他事务，也不能包含异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="926b5-157">An atomic transaction cannot contain any other transactions within it, nor can it contain exception handlers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="926b5-158">原子事务不能包含匹配的发送和接收操作 — 的是，请求-响应对或发送和接收的使用同一相关集。</span><span class="sxs-lookup"><span data-stu-id="926b5-158">An atomic transaction cannot contain matching send and receive actions—that is, a request-response pair or a send and receive that use the same correlation set.</span></span>  
  
## <a name="non-serializable-objects"></a><span data-ttu-id="926b5-159">非可序列化对象</span><span class="sxs-lookup"><span data-stu-id="926b5-159">Non-serializable objects</span></span>  
 <span data-ttu-id="926b5-160">如果你想要使用业务流程中的非可序列化对象，则必须使用它仅在原子事务内。</span><span class="sxs-lookup"><span data-stu-id="926b5-160">If you want to use a non-serializable object within an orchestration, you must use it only within an atomic transaction.</span></span> <span data-ttu-id="926b5-161">使用此类原子事务外的对象数据丢失的风险时由引擎保持在业务流程。</span><span class="sxs-lookup"><span data-stu-id="926b5-161">Any use of such an object outside of an atomic transaction risks data loss whenever the orchestration is persisted by the engine.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="926b5-162">每个原子作用域表示持久化点，这意味着业务流程的状态保存到每个持久化点上的数据库。</span><span class="sxs-lookup"><span data-stu-id="926b5-162">Each Atomic scope represents a persistence point and what that means is the state of the orchestration is saved to the database at each persistence point.</span></span> <span data-ttu-id="926b5-163">广泛使用原子作用域将增加业务流程中的延迟。</span><span class="sxs-lookup"><span data-stu-id="926b5-163">Extensive use of Atomic scope will increase the latency in the orchestration.</span></span> <span data-ttu-id="926b5-164">而不是使用以创建非可序列化对象的原子作用域，则可以使用静态方法调用不要求原子作用域，因此无需持久化点。</span><span class="sxs-lookup"><span data-stu-id="926b5-164">Instead of using Atomic scope for the purpose of creating non-serializable objects, you can use Static method calls which they don not require Atomic scopes, thus eliminating the need for the persistence points.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="926b5-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="926b5-165">See Also</span></span>  
 <span data-ttu-id="926b5-166">[使用原子事务的方案](../core/scenarios-using-atomic-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="926b5-166">[Scenarios Using Atomic Transactions](../core/scenarios-using-atomic-transactions.md) </span></span>  
 [<span data-ttu-id="926b5-167">长时间运行的事务</span><span class="sxs-lookup"><span data-stu-id="926b5-167">Long-Running Transactions</span></span>](../core/long-running-transactions.md)