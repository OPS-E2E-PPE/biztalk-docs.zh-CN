---
title: 安排和优先级 |Microsoft 文档
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
ms.openlocfilehash: 4529753251c2bf7934616b91662bde836c8339e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230205"
---
# <a name="agenda-and-priority"></a><span data-ttu-id="c2724-102">议程和优先级</span><span class="sxs-lookup"><span data-stu-id="c2724-102">Agenda and Priority</span></span>
<span data-ttu-id="c2724-103">若要了解业务规则引擎如何计算规则并执行操作，你需要了解的概念*安排*和*优先级*。</span><span class="sxs-lookup"><span data-stu-id="c2724-103">To understand how the Business Rule engine evaluates rules and executes actions, you need to understand the concepts of *agenda* and *priority*.</span></span>  
  
## <a name="agenda"></a><span data-ttu-id="c2724-104">议程</span><span class="sxs-lookup"><span data-stu-id="c2724-104">Agenda</span></span>  
 <span data-ttu-id="c2724-105">议程是引擎对要执行的规则进行排队时使用的计划。</span><span class="sxs-lookup"><span data-stu-id="c2724-105">The agenda is a schedule used by the engine to queue rules for execution.</span></span> <span data-ttu-id="c2724-106">议程用于引擎实例，它对单个策略而不是一系列策略起作用。</span><span class="sxs-lookup"><span data-stu-id="c2724-106">The agenda exists for an engine instance, and acts on a single policy, not on a series of policies.</span></span> <span data-ttu-id="c2724-107">将事实添加到工作内存中并且满足给定规则的条件时，该规则将被放置在议程上并根据优先级执行。</span><span class="sxs-lookup"><span data-stu-id="c2724-107">When a fact is asserted into working memory and the conditions of a given rule are satisfied, the rule is placed on the agenda and executed according to priority.</span></span> <span data-ttu-id="c2724-108">从上至下按顺序执行规则的操作，然后执行议程中下一个规则的操作。</span><span class="sxs-lookup"><span data-stu-id="c2724-108">A rule's actions are executed in order from top to bottom, and then the actions of the next rule on the agenda are executed.</span></span>  
  
 <span data-ttu-id="c2724-109">属于某一规则的操作被视为一个模块，这样，在继续到下一个规则之前将执行该规则的所有操作。</span><span class="sxs-lookup"><span data-stu-id="c2724-109">The actions belonging to a rule are treated as a block, so that all actions are executed before moving on to the next rule.</span></span> <span data-ttu-id="c2724-110">将执行规则模块中的所有操作，而不管模块中的其他操作。</span><span class="sxs-lookup"><span data-stu-id="c2724-110">All actions in a rule block will execute regardless of other actions in the block.</span></span> <span data-ttu-id="c2724-111">有关断言的详细信息，请参阅[引擎控制功能](../core/engine-control-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="c2724-111">For more information about assertion, see [Engine Control Functions](../core/engine-control-functions.md).</span></span>  
  
 <span data-ttu-id="c2724-112">以下示例说明议程是如何工作的：</span><span class="sxs-lookup"><span data-stu-id="c2724-112">The following example demonstrates how the agenda works.</span></span>  
  
 <span data-ttu-id="c2724-113">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="c2724-113">**Rule1**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 <span data-ttu-id="c2724-114">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="c2724-114">**Rule2**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 <span data-ttu-id="c2724-115">我们将值为 1 的事实 Fact1 添加到引擎中。</span><span class="sxs-lookup"><span data-stu-id="c2724-115">We assert the fact Fact1, which has a value of 1, into the engine.</span></span> <span data-ttu-id="c2724-116">由于 Rule1 和 Rule2 的条件都得到了满足，因此两个规则都移至议程，以便执行它们的操作。</span><span class="sxs-lookup"><span data-stu-id="c2724-116">Because the conditions of both Rule 1 and Rule 2 are satisfied, both rules are moved to the agenda for execution of their actions.</span></span>  
  
|<span data-ttu-id="c2724-117">工作内存</span><span class="sxs-lookup"><span data-stu-id="c2724-117">Working memory</span></span>|<span data-ttu-id="c2724-118">议程</span><span class="sxs-lookup"><span data-stu-id="c2724-118">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="c2724-119">Fact1（值=1）</span><span class="sxs-lookup"><span data-stu-id="c2724-119">Fact1 (value=1)</span></span>|<span data-ttu-id="c2724-120">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="c2724-120">**Rule1**</span></span><br /><br /> <span data-ttu-id="c2724-121">-Action1</span><span class="sxs-lookup"><span data-stu-id="c2724-121">-   Action1</span></span><br /><span data-ttu-id="c2724-122">-Action2</span><span class="sxs-lookup"><span data-stu-id="c2724-122">-   Action2</span></span><br /><br /> <span data-ttu-id="c2724-123">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="c2724-123">**Rule2**</span></span><br /><br /> <span data-ttu-id="c2724-124">-Action3</span><span class="sxs-lookup"><span data-stu-id="c2724-124">-   Action3</span></span><br /><span data-ttu-id="c2724-125">-Action4</span><span class="sxs-lookup"><span data-stu-id="c2724-125">-   Action4</span></span>|  
  
## <a name="priority"></a><span data-ttu-id="c2724-126">Priority</span><span class="sxs-lookup"><span data-stu-id="c2724-126">Priority</span></span>  
 <span data-ttu-id="c2724-127">每个规则都设置了执行优先级，所有规则的默认优先级为 0。</span><span class="sxs-lookup"><span data-stu-id="c2724-127">Priority for execution is set on each individual rule, with a default priority of 0 for all rules.</span></span> <span data-ttu-id="c2724-128">优先级可以大于、等于或小于 0，数字越大优先级越高。</span><span class="sxs-lookup"><span data-stu-id="c2724-128">The priority can range on either side of 0, with larger numbers having higher priority.</span></span> <span data-ttu-id="c2724-129">操作按照从最高优先级到最低优先级的顺序执行。</span><span class="sxs-lookup"><span data-stu-id="c2724-129">Actions are executed in order from highest priority to lowest priority.</span></span>  
  
 <span data-ttu-id="c2724-130">以下示例说明优先级如何影响规则的执行顺序：</span><span class="sxs-lookup"><span data-stu-id="c2724-130">The following example shows how priority affects the order of execution for the rules.</span></span>  
  
 <span data-ttu-id="c2724-131">**规则 1 (优先级 = 0)**</span><span class="sxs-lookup"><span data-stu-id="c2724-131">**Rule1 (priority = 0)**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 <span data-ttu-id="c2724-132">**Rule2 (优先级 = 10)**</span><span class="sxs-lookup"><span data-stu-id="c2724-132">**Rule2 (priority = 10)**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 <span data-ttu-id="c2724-133">两条规则的条件都已得到满足，但首先执行 Rule2，因为它具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="c2724-133">The conditions for both rules have been met, but Rule2 is executed first because it has higher priority.</span></span> <span data-ttu-id="c2724-134">最终折扣为 10%，因为它是对 Rule1 执行操作的结果，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="c2724-134">The final discount is 10 percent, because it is the result of the action executed for Rule1, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c2724-135">工作内存</span><span class="sxs-lookup"><span data-stu-id="c2724-135">Working memory</span></span>|<span data-ttu-id="c2724-136">议程</span><span class="sxs-lookup"><span data-stu-id="c2724-136">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="c2724-137">Fact1（值=1）</span><span class="sxs-lookup"><span data-stu-id="c2724-137">Fact1 (value=1)</span></span>|<span data-ttu-id="c2724-138">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="c2724-138">**Rule2**</span></span><br /><br /> <span data-ttu-id="c2724-139">折扣 = 15%</span><span class="sxs-lookup"><span data-stu-id="c2724-139">Discount = 15%</span></span><br /><br /> <span data-ttu-id="c2724-140">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="c2724-140">**Rule1**</span></span><br /><br /> <span data-ttu-id="c2724-141">折扣 = 10%</span><span class="sxs-lookup"><span data-stu-id="c2724-141">Discount = 10%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2724-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2724-142">See Also</span></span>  
 [<span data-ttu-id="c2724-143">规则引擎</span><span class="sxs-lookup"><span data-stu-id="c2724-143">Rule Engine</span></span>](../core/rule-engine.md)