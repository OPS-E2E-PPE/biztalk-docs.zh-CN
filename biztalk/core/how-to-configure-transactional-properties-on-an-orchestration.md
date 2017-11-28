---
title: "如何在业务流程上配置事务属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9164a9f5670a996a62450a19d802c97b89d8e242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a><span data-ttu-id="b574e-102">如何在业务流程上配置事务属性</span><span class="sxs-lookup"><span data-stu-id="b574e-102">How to Configure Transactional Properties on an Orchestration</span></span>
<span data-ttu-id="b574e-103">业务流程可被视为原子事务、长期事务或既非原子事务也非长期事务。</span><span class="sxs-lookup"><span data-stu-id="b574e-103">An orchestration can be treated as an atomic transaction, a long-running transaction, or neither.</span></span>  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a><span data-ttu-id="b574e-104">使业务流程成为原子事务</span><span class="sxs-lookup"><span data-stu-id="b574e-104">To make your orchestration an atomic transaction</span></span>  
  
1.  <span data-ttu-id="b574e-105">在业务流程视图窗口中，选择**业务流程属性**。</span><span class="sxs-lookup"><span data-stu-id="b574e-105">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="b574e-106">在属性窗口中，选择**原子**下拉列表中**事务类型**属性。</span><span class="sxs-lookup"><span data-stu-id="b574e-106">In the Properties window, select **Atomic** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="b574e-107">**批处理**，**补偿**，**隔离级别**，**重试**，**超时**，和**事务标识符**显示为属性窗口中的属性，就像它们针对任何范围内采取的操作。</span><span class="sxs-lookup"><span data-stu-id="b574e-107">**Batch**, **Compensation**, **Isolation Level**, **Retry**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window, just as they do for any scope.</span></span> <span data-ttu-id="b574e-108">有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="b574e-108">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a><span data-ttu-id="b574e-109">使业务流程成为长期事务</span><span class="sxs-lookup"><span data-stu-id="b574e-109">To make your orchestration a long-running transaction</span></span>  
  
1.  <span data-ttu-id="b574e-110">在业务流程视图窗口中，选择**业务流程属性**。</span><span class="sxs-lookup"><span data-stu-id="b574e-110">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="b574e-111">在属性窗口中，选择**运行长时间**下拉列表中**事务类型**属性。</span><span class="sxs-lookup"><span data-stu-id="b574e-111">In the Properties window, select **Long Running** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="b574e-112">**补偿**，**超时**，和**事务标识符**显示为属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="b574e-112">**Compensation**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window.</span></span> <span data-ttu-id="b574e-113">有关这些属性的详细信息，与它们针对任何作用域显示一样。</span><span class="sxs-lookup"><span data-stu-id="b574e-113">For more information on these properties, just as they do for any scope.</span></span> <span data-ttu-id="b574e-114">有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="b574e-114">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b574e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b574e-115">See Also</span></span>  
 [<span data-ttu-id="b574e-116">使业务流程事务</span><span class="sxs-lookup"><span data-stu-id="b574e-116">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)