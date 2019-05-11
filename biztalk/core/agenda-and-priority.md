---
title: 议程和优先级 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, executing
- Business Rules Engine, agendas
- Business Rules Engine, priorities
- business rules, priorities
- business rules, examples
- Business Rules Engine, examples
- examples, Business Rules Engine
- Business Rules Engine, rules
ms.assetid: ca54f750-4f2d-4734-8e6e-7af1b4967e6a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85274b0cbd59cd9272bb63030296d3f527e096a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360419"
---
# <a name="agenda-and-priority"></a><span data-ttu-id="b9366-102">议程和优先级</span><span class="sxs-lookup"><span data-stu-id="b9366-102">Agenda and Priority</span></span>
<span data-ttu-id="b9366-103">若要了解如何在业务规则引擎计算规则，并执行操作，您需要了解的概念*议程*并*优先级*。</span><span class="sxs-lookup"><span data-stu-id="b9366-103">To understand how the Business Rule engine evaluates rules and executes actions, you need to understand the concepts of *agenda* and *priority*.</span></span>  
  
## <a name="agenda"></a><span data-ttu-id="b9366-104">议程</span><span class="sxs-lookup"><span data-stu-id="b9366-104">Agenda</span></span>  
 <span data-ttu-id="b9366-105">议程是引擎对队列规则执行时使用的计划。</span><span class="sxs-lookup"><span data-stu-id="b9366-105">The agenda is a schedule used by the engine to queue rules for execution.</span></span> <span data-ttu-id="b9366-106">议程用于引擎实例，存在且作用于单个策略而不是上一系列的策略。</span><span class="sxs-lookup"><span data-stu-id="b9366-106">The agenda exists for an engine instance, and acts on a single policy, not on a series of policies.</span></span> <span data-ttu-id="b9366-107">如果事实添加到工作内存中时，满足给定规则的条件规则放置在议程，并根据优先级执行。</span><span class="sxs-lookup"><span data-stu-id="b9366-107">When a fact is asserted into working memory and the conditions of a given rule are satisfied, the rule is placed on the agenda and executed according to priority.</span></span> <span data-ttu-id="b9366-108">从上到下的顺序执行规则的操作，然后执行议程的下一个规则的操作。</span><span class="sxs-lookup"><span data-stu-id="b9366-108">A rule's actions are executed in order from top to bottom, and then the actions of the next rule on the agenda are executed.</span></span>  
  
 <span data-ttu-id="b9366-109">属于某一规则的操作被视为一个块，以便在前进到下一规则之前执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="b9366-109">The actions belonging to a rule are treated as a block, so that all actions are executed before moving on to the next rule.</span></span> <span data-ttu-id="b9366-110">无论在块中的其他操作将执行规则模块中的所有操作。</span><span class="sxs-lookup"><span data-stu-id="b9366-110">All actions in a rule block will execute regardless of other actions in the block.</span></span> <span data-ttu-id="b9366-111">有关断言的详细信息，请参阅[引擎控制功能](../core/engine-control-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="b9366-111">For more information about assertion, see [Engine Control Functions](../core/engine-control-functions.md).</span></span>  
  
 <span data-ttu-id="b9366-112">下面的示例演示了议程的工作原理。</span><span class="sxs-lookup"><span data-stu-id="b9366-112">The following example demonstrates how the agenda works.</span></span>  
  
 <span data-ttu-id="b9366-113">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="b9366-113">**Rule1**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 <span data-ttu-id="b9366-114">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="b9366-114">**Rule2**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 <span data-ttu-id="b9366-115">我们断言事实 Fact1，具有值为 1，到引擎中。</span><span class="sxs-lookup"><span data-stu-id="b9366-115">We assert the fact Fact1, which has a value of 1, into the engine.</span></span> <span data-ttu-id="b9366-116">因为满足规则 1 和规则 2 的条件时，这两个规则都执行其操作移至议程。</span><span class="sxs-lookup"><span data-stu-id="b9366-116">Because the conditions of both Rule 1 and Rule 2 are satisfied, both rules are moved to the agenda for execution of their actions.</span></span>  
  
|<span data-ttu-id="b9366-117">工作内存</span><span class="sxs-lookup"><span data-stu-id="b9366-117">Working memory</span></span>|<span data-ttu-id="b9366-118">议程</span><span class="sxs-lookup"><span data-stu-id="b9366-118">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="b9366-119">Fact1 (value=1)</span><span class="sxs-lookup"><span data-stu-id="b9366-119">Fact1 (value=1)</span></span>|<span data-ttu-id="b9366-120">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="b9366-120">**Rule1**</span></span><br /><br /> <span data-ttu-id="b9366-121">-   Action1</span><span class="sxs-lookup"><span data-stu-id="b9366-121">-   Action1</span></span><br /><span data-ttu-id="b9366-122">-   Action2</span><span class="sxs-lookup"><span data-stu-id="b9366-122">-   Action2</span></span><br /><br /> <span data-ttu-id="b9366-123">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="b9366-123">**Rule2**</span></span><br /><br /> <span data-ttu-id="b9366-124">-   Action3</span><span class="sxs-lookup"><span data-stu-id="b9366-124">-   Action3</span></span><br /><span data-ttu-id="b9366-125">-   Action4</span><span class="sxs-lookup"><span data-stu-id="b9366-125">-   Action4</span></span>|  
  
## <a name="priority"></a><span data-ttu-id="b9366-126">Priority</span><span class="sxs-lookup"><span data-stu-id="b9366-126">Priority</span></span>  
 <span data-ttu-id="b9366-127">执行优先级设置每个规则的默认优先级为 0 表示所有规则。</span><span class="sxs-lookup"><span data-stu-id="b9366-127">Priority for execution is set on each individual rule, with a default priority of 0 for all rules.</span></span> <span data-ttu-id="b9366-128">优先级为 0，或小于范围更大的数字越大优先级越高。</span><span class="sxs-lookup"><span data-stu-id="b9366-128">The priority can range on either side of 0, with larger numbers having higher priority.</span></span> <span data-ttu-id="b9366-129">从最高优先级到最低优先级的顺序执行操作。</span><span class="sxs-lookup"><span data-stu-id="b9366-129">Actions are executed in order from highest priority to lowest priority.</span></span>  
  
 <span data-ttu-id="b9366-130">下面的示例显示了优先级如何影响规则的执行顺序。</span><span class="sxs-lookup"><span data-stu-id="b9366-130">The following example shows how priority affects the order of execution for the rules.</span></span>  
  
 <span data-ttu-id="b9366-131">**Rule1 (优先级 = 0)**</span><span class="sxs-lookup"><span data-stu-id="b9366-131">**Rule1 (priority = 0)**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 <span data-ttu-id="b9366-132">**Rule2 (优先级 = 10)**</span><span class="sxs-lookup"><span data-stu-id="b9366-132">**Rule2 (priority = 10)**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 <span data-ttu-id="b9366-133">这两个规则的条件均已满足，但首先执行 Rule2，因为它具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="b9366-133">The conditions for both rules have been met, but Rule2 is executed first because it has higher priority.</span></span> <span data-ttu-id="b9366-134">最终折扣为 10%，因为它是对 Rule1 执行操作的结果下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="b9366-134">The final discount is 10 percent, because it is the result of the action executed for Rule1, as shown in the following table.</span></span>  
  
|<span data-ttu-id="b9366-135">工作内存</span><span class="sxs-lookup"><span data-stu-id="b9366-135">Working memory</span></span>|<span data-ttu-id="b9366-136">议程</span><span class="sxs-lookup"><span data-stu-id="b9366-136">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="b9366-137">Fact1 (value=1)</span><span class="sxs-lookup"><span data-stu-id="b9366-137">Fact1 (value=1)</span></span>|<span data-ttu-id="b9366-138">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="b9366-138">**Rule2**</span></span><br /><br /> <span data-ttu-id="b9366-139">折扣 = 15%</span><span class="sxs-lookup"><span data-stu-id="b9366-139">Discount = 15%</span></span><br /><br /> <span data-ttu-id="b9366-140">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="b9366-140">**Rule1**</span></span><br /><br /> <span data-ttu-id="b9366-141">折扣 = 10%</span><span class="sxs-lookup"><span data-stu-id="b9366-141">Discount = 10%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9366-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9366-142">See Also</span></span>  
 [<span data-ttu-id="b9366-143">规则引擎</span><span class="sxs-lookup"><span data-stu-id="b9366-143">Rule Engine</span></span>](../core/rule-engine.md)