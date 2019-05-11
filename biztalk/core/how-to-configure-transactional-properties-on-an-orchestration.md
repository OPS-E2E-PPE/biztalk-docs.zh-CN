---
title: 如何在业务流程配置事务属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c999ca7c487cdcf59fd29e76b3d466194aa8ee21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385780"
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a><span data-ttu-id="91621-102">如何在业务流程配置事务属性</span><span class="sxs-lookup"><span data-stu-id="91621-102">How to Configure Transactional Properties on an Orchestration</span></span>
<span data-ttu-id="91621-103">业务流程可将其视为原子事务、 长时间运行的事务，还是两者皆未。</span><span class="sxs-lookup"><span data-stu-id="91621-103">An orchestration can be treated as an atomic transaction, a long-running transaction, or neither.</span></span>  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a><span data-ttu-id="91621-104">若要使某一原子事务的业务流程</span><span class="sxs-lookup"><span data-stu-id="91621-104">To make your orchestration an atomic transaction</span></span>  
  
1.  <span data-ttu-id="91621-105">在业务流程视图窗口中，选择**业务流程属性**。</span><span class="sxs-lookup"><span data-stu-id="91621-105">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="91621-106">在属性窗口中，选择**原子**的下拉列表中**事务类型**属性。</span><span class="sxs-lookup"><span data-stu-id="91621-106">In the Properties window, select **Atomic** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="91621-107">**批处理**，**补偿**，**隔离级别**，**重试**，**超时**，和**事务标识符**作为属性出现在属性窗口中，就像针对任何作用域。</span><span class="sxs-lookup"><span data-stu-id="91621-107">**Batch**, **Compensation**, **Isolation Level**, **Retry**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window, just as they do for any scope.</span></span> <span data-ttu-id="91621-108">有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="91621-108">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a><span data-ttu-id="91621-109">若要使一个长时间运行的事务的业务流程</span><span class="sxs-lookup"><span data-stu-id="91621-109">To make your orchestration a long-running transaction</span></span>  
  
1.  <span data-ttu-id="91621-110">在业务流程视图窗口中，选择**业务流程属性**。</span><span class="sxs-lookup"><span data-stu-id="91621-110">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="91621-111">在属性窗口中，选择**长期**的下拉列表中**事务类型**属性。</span><span class="sxs-lookup"><span data-stu-id="91621-111">In the Properties window, select **Long Running** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="91621-112">**补偿**，**超时**，和**事务标识符**作为属性出现在属性窗口。</span><span class="sxs-lookup"><span data-stu-id="91621-112">**Compensation**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window.</span></span> <span data-ttu-id="91621-113">有关详细信息属性，就像针对任何作用域。</span><span class="sxs-lookup"><span data-stu-id="91621-113">For more information on these properties, just as they do for any scope.</span></span> <span data-ttu-id="91621-114">有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="91621-114">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91621-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="91621-115">See Also</span></span>  
 [<span data-ttu-id="91621-116">使业务流程成为事务性业务流程</span><span class="sxs-lookup"><span data-stu-id="91621-116">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)