---
title: "使用原子事务的方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e73cfea7a99e2fafbf115a367dbf0840de3369c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenarios-using-atomic-transactions"></a><span data-ttu-id="90ad7-102">使用原子事务的方案</span><span class="sxs-lookup"><span data-stu-id="90ad7-102">Scenarios Using Atomic Transactions</span></span>
<span data-ttu-id="90ad7-103">下面的方案描述了原子事务的使用。</span><span class="sxs-lookup"><span data-stu-id="90ad7-103">The following scenarios describe the use of atomic transactions.</span></span>  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a><span data-ttu-id="90ad7-104">方案 1： 原子事务与 COM + ServicedComponent</span><span class="sxs-lookup"><span data-stu-id="90ad7-104">Scenario 1: An Atomic Transaction with COM+ ServicedComponent</span></span>  
 <span data-ttu-id="90ad7-105">以下业务流程演示如何使用**RetryTransactionException**与原子事务。</span><span class="sxs-lookup"><span data-stu-id="90ad7-105">The following orchestration shows how to use the **RetryTransactionException** with atomic transactions.</span></span> <span data-ttu-id="90ad7-106">尽管无法为原子作用域直接包括异常处理程序，但该作用域可以包括可具有异常处理程序的非事务性作用域。</span><span class="sxs-lookup"><span data-stu-id="90ad7-106">Although exception handlers cannot be directly included for an atomic scope, the scope can include a non-transactional scope that can have an exception handler.</span></span> <span data-ttu-id="90ad7-107">**ServicedComponent**在同一个 DTC 事务中登记和由组件引发任何异常捕获和重新引发作为**RetryTransactionException**。</span><span class="sxs-lookup"><span data-stu-id="90ad7-107">The **ServicedComponent** enlists in the same DTC transaction and any exception raised by the component is caught and re-thrown as **RetryTransactionException**.</span></span> <span data-ttu-id="90ad7-108">(此操作假定**重试**属性设置为**True**原子作用域)。</span><span class="sxs-lookup"><span data-stu-id="90ad7-108">(This assumes that the **Retry** property is set to **True** for the atomic scope).</span></span>  
  
 <span data-ttu-id="90ad7-109">请注意，已挂起业务流程和 MessageAssignment 形状中的操作将已回滚即使**RetryTransactionException**不会引发。</span><span class="sxs-lookup"><span data-stu-id="90ad7-109">Note that the orchestration would have been suspended and the action in the MessageAssignment shape would have been rolled back even if the **RetryTransactionException** is not thrown.</span></span> <span data-ttu-id="90ad7-110">但是，这种模式能够在自动进行重试的应用程序中提供一定的弹性。</span><span class="sxs-lookup"><span data-stu-id="90ad7-110">This pattern, however, allows building resilience in the application where the retries occur automatically.</span></span>  
  
 <span data-ttu-id="90ad7-111">**与 COM + ServicedComponent 原子事务**</span><span class="sxs-lookup"><span data-stu-id="90ad7-111">**An atomic transaction with COM+ ServicedComponent**</span></span>  
  
 <span data-ttu-id="90ad7-112">![使用 COM &#43; 原子事务ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span><span class="sxs-lookup"><span data-stu-id="90ad7-112">![An atomic transaction with COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span></span>  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a><span data-ttu-id="90ad7-113">方案 2： 原子事务中使用事务处理的适配器</span><span class="sxs-lookup"><span data-stu-id="90ad7-113">Scenario 2: Using Transacted Adapters with Atomic Transactions</span></span>  
 <span data-ttu-id="90ad7-114">下面的业务流程显示如何将原子事务与 SQL 适配器一起使用。</span><span class="sxs-lookup"><span data-stu-id="90ad7-114">The following orchestration shows how to use the atomic transactions with the SQL adapter.</span></span> <span data-ttu-id="90ad7-115">整个业务流程被标记为长时间运行的两个逻辑部分的工作的单个原子事务： 插入新的客户和插入顺序客户有关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="90ad7-115">The whole orchestration is marked as long running with individual atomic transactions for the two logical pieces of work: Inserting a new Customer and Insert Order details for the customer.</span></span>  
  
 <span data-ttu-id="90ad7-116">如果由于某种原因导致插入订单的操作失败，则应回滚插入客户的操作。</span><span class="sxs-lookup"><span data-stu-id="90ad7-116">If, for whatever reason, the Order Insert fails, the Customer Insert should be rolled back.</span></span> <span data-ttu-id="90ad7-117">该示例使用 SQL 适配器执行数据库工作。</span><span class="sxs-lookup"><span data-stu-id="90ad7-117">The sample uses the SQL adapter to do the database work.</span></span> <span data-ttu-id="90ad7-118">如前所述，消息发送到 MessageBox 数据库时将完成与原子事务相关联的作用域。</span><span class="sxs-lookup"><span data-stu-id="90ad7-118">As mentioned earlier, the scope associated with an atomic transaction completes when the message is sent to the MessageBox database.</span></span> <span data-ttu-id="90ad7-119">这表示引擎在 Scope_InsertCustomer 和 Scope_InsertOrder 作用域中成功发送消息后，将提交每一作用域。</span><span class="sxs-lookup"><span data-stu-id="90ad7-119">This implies that after the engine is successful in sending the message in the Scope_InsertCustomer and Scope_InsertOrder scopes, each one of the scopes commits.</span></span> <span data-ttu-id="90ad7-120">SQL 适配器将为客户或订单的实际插入创建一个新事务。</span><span class="sxs-lookup"><span data-stu-id="90ad7-120">The SQL adapter creates a new transaction for the actual Insert of the Customer or the order.</span></span>  
  
 <span data-ttu-id="90ad7-121">这些端口具有“送达通知”属性，用来验证是否通过发送端口成功发送了消息。</span><span class="sxs-lookup"><span data-stu-id="90ad7-121">The Ports have a property “Delivery Notification” for validating that the message has been successfully sent via the Sent Port.</span></span> <span data-ttu-id="90ad7-122">将“送达通知”属性设置为“已传输”时，会在发送操作的事务性提交点之前放置一个接收订阅。</span><span class="sxs-lookup"><span data-stu-id="90ad7-122">When the Delivery Notification property is set to “Transmitted”, a receive subscription is placed before the Transactional commit point of the Send Operation.</span></span> <span data-ttu-id="90ad7-123">但是在原子作用域的情况下，会将接收订阅放在封闭的父作用域中。</span><span class="sxs-lookup"><span data-stu-id="90ad7-123">However, in case of Atomic Scopes, the receive subscription is placed in the enclosing Parent scope.</span></span>  
  
 <span data-ttu-id="90ad7-124">在 InsertOrder SQL 事务失败的情况下，将发送回“Nack”并提交“Scope_InsertOrder”。</span><span class="sxs-lookup"><span data-stu-id="90ad7-124">In the scenario where the InsertOrder SQL transaction fails, a "Nack" will be sent back and the "Scope_InsertOrder" commits.</span></span> <span data-ttu-id="90ad7-125">发送端口用尽所配置的重试次数后，将引发 DeliveryFailureException。</span><span class="sxs-lookup"><span data-stu-id="90ad7-125">After the Sent Port exhausts the configured retries, a DeliveryFailureException will be raised.</span></span> <span data-ttu-id="90ad7-126">将运行默认补偿过程的默认异常处理程序会捕获此异常。</span><span class="sxs-lookup"><span data-stu-id="90ad7-126">This exception will be caught by the default exception handler, which will run the default compensation process.</span></span> <span data-ttu-id="90ad7-127">这将调用与 Scope_InsertCustomer 和 Scope_InsertOrder 相关联的补偿处理程序，从而导致撤销插入客户信息的操作。</span><span class="sxs-lookup"><span data-stu-id="90ad7-127">This will invoke the compensation handlers associated with the Scope_InsertCustomer and Scope_InsertOrder, causing the undo operation of inserting the customer information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90ad7-128">将两个作用域嵌套在长期作用域中并从长期作用域的异常处理程序中调用补偿形状（以长期事务为目标），可产生与上述做法相同的行为。</span><span class="sxs-lookup"><span data-stu-id="90ad7-128">Nesting the two scopes in a long running scope and invoking the Compensate shape (targeting the long running transaction) from the exception handler for the long running scope will result in the same behavior as described above.</span></span> <span data-ttu-id="90ad7-129">不能将整个业务流程标记为原子的，这是因为原子事务不允许嵌套的事务。</span><span class="sxs-lookup"><span data-stu-id="90ad7-129">The whole orchestration could not be marked atomic as atomic transactions do not allow nested transactions.</span></span>  
  
 <span data-ttu-id="90ad7-130">**与原子事务的事务处理的适配器**</span><span class="sxs-lookup"><span data-stu-id="90ad7-130">**Transacted adapters with atomic transactions**</span></span>  
  
 <span data-ttu-id="90ad7-131">![事务处理具有原子事务适配器](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span><span class="sxs-lookup"><span data-stu-id="90ad7-131">![Transacted adapters with atomic transactions](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span></span>