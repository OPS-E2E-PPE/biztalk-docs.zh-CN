---
title: 使用原子事务的方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d959fdb9135a804346a869811072f826906b5876
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308161"
---
# <a name="scenarios-using-atomic-transactions"></a><span data-ttu-id="65662-102">使用原子事务的方案</span><span class="sxs-lookup"><span data-stu-id="65662-102">Scenarios Using Atomic Transactions</span></span>
<span data-ttu-id="65662-103">以下方案说明原子事务的使用。</span><span class="sxs-lookup"><span data-stu-id="65662-103">The following scenarios describe the use of atomic transactions.</span></span>  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a><span data-ttu-id="65662-104">应用场景 1：具有 COM + ServicedComponent 的原子事务</span><span class="sxs-lookup"><span data-stu-id="65662-104">Scenario 1: An Atomic Transaction with COM+ ServicedComponent</span></span>  
 <span data-ttu-id="65662-105">下面的业务流程演示如何使用**RetryTransactionException**具有原子事务。</span><span class="sxs-lookup"><span data-stu-id="65662-105">The following orchestration shows how to use the **RetryTransactionException** with atomic transactions.</span></span> <span data-ttu-id="65662-106">尽管异常处理程序不能直接包含的原子作用域中，作用域可以包括可以具有异常处理程序的非事务性作用域。</span><span class="sxs-lookup"><span data-stu-id="65662-106">Although exception handlers cannot be directly included for an atomic scope, the scope can include a non-transactional scope that can have an exception handler.</span></span> <span data-ttu-id="65662-107">**ServicedComponent**在同一 DTC 事务中登记和捕获组件引发的任何异常并将其作为重新引发**RetryTransactionException**。</span><span class="sxs-lookup"><span data-stu-id="65662-107">The **ServicedComponent** enlists in the same DTC transaction and any exception raised by the component is caught and re-thrown as **RetryTransactionException**.</span></span> <span data-ttu-id="65662-108">(这假定**重试**属性设置为**True**原子作用域)。</span><span class="sxs-lookup"><span data-stu-id="65662-108">(This assumes that the **Retry** property is set to **True** for the atomic scope).</span></span>  
  
 <span data-ttu-id="65662-109">请注意，已挂起业务流程和 MessageAssignment 形状中的操作将都已回退即使**RetryTransactionException**不会引发。</span><span class="sxs-lookup"><span data-stu-id="65662-109">Note that the orchestration would have been suspended and the action in the MessageAssignment shape would have been rolled back even if the **RetryTransactionException** is not thrown.</span></span> <span data-ttu-id="65662-110">此模式，但是，可构建应用程序中的恢复能力重试会自动执行。</span><span class="sxs-lookup"><span data-stu-id="65662-110">This pattern, however, allows building resilience in the application where the retries occur automatically.</span></span>  
  
 <span data-ttu-id="65662-111">**具有 COM + ServicedComponent 的原子事务**</span><span class="sxs-lookup"><span data-stu-id="65662-111">**An atomic transaction with COM+ ServicedComponent**</span></span>  
  
 <span data-ttu-id="65662-112">![原子事务与 COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span><span class="sxs-lookup"><span data-stu-id="65662-112">![An atomic transaction with COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span></span>  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a><span data-ttu-id="65662-113">应用场景 2：使用事务性的适配器与原子事务</span><span class="sxs-lookup"><span data-stu-id="65662-113">Scenario 2: Using Transacted Adapters with Atomic Transactions</span></span>  
 <span data-ttu-id="65662-114">下面的业务流程演示如何使用 SQL 适配器与原子事务。</span><span class="sxs-lookup"><span data-stu-id="65662-114">The following orchestration shows how to use the atomic transactions with the SQL adapter.</span></span> <span data-ttu-id="65662-115">长时间运行的两个逻辑工作部分的单独原子事务与标记将整个业务流程：客户插入新客户和插入订单详细信息。</span><span class="sxs-lookup"><span data-stu-id="65662-115">The whole orchestration is marked as long running with individual atomic transactions for the two logical pieces of work: Inserting a new Customer and Insert Order details for the customer.</span></span>  
  
 <span data-ttu-id="65662-116">如果由于任何原因而将订单插入失败，客户插入应回滚。</span><span class="sxs-lookup"><span data-stu-id="65662-116">If, for whatever reason, the Order Insert fails, the Customer Insert should be rolled back.</span></span> <span data-ttu-id="65662-117">此示例使用 SQL 适配器执行数据库工作。</span><span class="sxs-lookup"><span data-stu-id="65662-117">The sample uses the SQL adapter to do the database work.</span></span> <span data-ttu-id="65662-118">如前文所述，原子事务与关联的范围完成时将消息发送到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="65662-118">As mentioned earlier, the scope associated with an atomic transaction completes when the message is sent to the MessageBox database.</span></span> <span data-ttu-id="65662-119">这意味着，该引擎在 Scope_InsertCustomer 和 Scope_InsertOrder 作用域中发送该消息成功后，作用域的每个提交。</span><span class="sxs-lookup"><span data-stu-id="65662-119">This implies that after the engine is successful in sending the message in the Scope_InsertCustomer and Scope_InsertOrder scopes, each one of the scopes commits.</span></span> <span data-ttu-id="65662-120">SQL 适配器为客户或订单的实际插入创建了新事务。</span><span class="sxs-lookup"><span data-stu-id="65662-120">The SQL adapter creates a new transaction for the actual Insert of the Customer or the order.</span></span>  
  
 <span data-ttu-id="65662-121">端口具有一个属性，"送达通知"用于验证它已成功通过发送端口发送消息。</span><span class="sxs-lookup"><span data-stu-id="65662-121">The Ports have a property “Delivery Notification” for validating that the message has been successfully sent via the Sent Port.</span></span> <span data-ttu-id="65662-122">当送达通知属性设置为"已传输"时，在发送操作的事务性提交点之前放置一个接收订阅。</span><span class="sxs-lookup"><span data-stu-id="65662-122">When the Delivery Notification property is set to “Transmitted”, a receive subscription is placed before the Transactional commit point of the Send Operation.</span></span> <span data-ttu-id="65662-123">但是，在原子作用域，则封闭的父作用域中放置接收订阅。</span><span class="sxs-lookup"><span data-stu-id="65662-123">However, in case of Atomic Scopes, the receive subscription is placed in the enclosing Parent scope.</span></span>  
  
 <span data-ttu-id="65662-124">在 InsertOrder SQL 事务失败的方案中，将发送"Nack"后退和提交"Scope_InsertOrder"。</span><span class="sxs-lookup"><span data-stu-id="65662-124">In the scenario where the InsertOrder SQL transaction fails, a "Nack" will be sent back and the "Scope_InsertOrder" commits.</span></span> <span data-ttu-id="65662-125">在发送端口用尽配置重试次数后，将引发 DeliveryFailureException。</span><span class="sxs-lookup"><span data-stu-id="65662-125">After the Sent Port exhausts the configured retries, a DeliveryFailureException will be raised.</span></span> <span data-ttu-id="65662-126">将运行默认补偿过程的默认异常处理程序将捕获此异常。</span><span class="sxs-lookup"><span data-stu-id="65662-126">This exception will be caught by the default exception handler, which will run the default compensation process.</span></span> <span data-ttu-id="65662-127">这将调用与 Scope_InsertCustomer 和 Scope_InsertOrder，从而导致撤销插入客户信息的操作相关联的补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="65662-127">This will invoke the compensation handlers associated with the Scope_InsertCustomer and Scope_InsertOrder, causing the undo operation of inserting the customer information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65662-128">如上文所述，嵌套的长期作用域中的两个作用域和从长期作用域的异常处理程序中调用补偿形状 （面向长时间运行的事务） 将导致相同的行为。</span><span class="sxs-lookup"><span data-stu-id="65662-128">Nesting the two scopes in a long running scope and invoking the Compensate shape (targeting the long running transaction) from the exception handler for the long running scope will result in the same behavior as described above.</span></span> <span data-ttu-id="65662-129">将整个业务流程可能不会标记原子如原子事务不允许嵌套的事务。</span><span class="sxs-lookup"><span data-stu-id="65662-129">The whole orchestration could not be marked atomic as atomic transactions do not allow nested transactions.</span></span>  
  
 <span data-ttu-id="65662-130">**具有原子事务的事务性的适配器**</span><span class="sxs-lookup"><span data-stu-id="65662-130">**Transacted adapters with atomic transactions**</span></span>  
  
 <span data-ttu-id="65662-131">![事务性适配器与原子事务一起](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span><span class="sxs-lookup"><span data-stu-id="65662-131">![Transacted adapters with atomic transactions](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span></span>