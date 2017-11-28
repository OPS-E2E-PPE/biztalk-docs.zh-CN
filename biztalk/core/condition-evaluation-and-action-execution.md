---
title: "计算和操作执行条件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Action stage [Business Rules Engine]
- examples, business rules
- Business Rules Engine, policies
- Match stage [Business Rules Engine]
- business rules, examples
- Business Rules Engine, algorithm
- Business Rules Engine, examples
- conflict resolution [Business Rules Engine]
- Business Rules Engine, stages
ms.assetid: dcaa32c2-3403-4f54-92e2-128686bfc193
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2814a97c1907b1bb29eee2a718d04d14cfe901a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="condition-evaluation-and-action-execution"></a><span data-ttu-id="843a3-102">条件计算和操作执行</span><span class="sxs-lookup"><span data-stu-id="843a3-102">Condition Evaluation and Action Execution</span></span>
<span data-ttu-id="843a3-103">业务规则框架提供了高效的推理引擎，可以将规则链接到 .NET 对象、XML 文档或数据库表。</span><span class="sxs-lookup"><span data-stu-id="843a3-103">The Business Rules Framework provides a highly efficient inference engine capable of linking rules to .NET objects, XML documents, or database tables.</span></span>  
  
 <span data-ttu-id="843a3-104">业务规则引擎对策略执行使用了三阶段算法。</span><span class="sxs-lookup"><span data-stu-id="843a3-104">The Business Rule Engine uses a three-stage algorithm for policy execution.</span></span> <span data-ttu-id="843a3-105">这些阶段包括：</span><span class="sxs-lookup"><span data-stu-id="843a3-105">The stages are as follows:</span></span>  
  
-   <span data-ttu-id="843a3-106">**匹配**。</span><span class="sxs-lookup"><span data-stu-id="843a3-106">**Match**.</span></span> <span data-ttu-id="843a3-107">在匹配阶段，将使用在规则条件中定义的谓词，根据使用事实类型（在规则引擎的工作内存中维护的对象引用）的谓词来匹配事实。</span><span class="sxs-lookup"><span data-stu-id="843a3-107">In the match stage, facts are matched against the predicates that use the fact type (object references maintained in the rule engine's working memory) using the predicates defined in the rule conditions.</span></span> <span data-ttu-id="843a3-108">由于效率的原因，策略中的所有规则会进行模式匹配，而规则共享的条件则只匹配一次。</span><span class="sxs-lookup"><span data-stu-id="843a3-108">For the sake of efficiency, pattern matching occurs over all the rules in the policy, and conditions that are shared across rules are matched only once.</span></span> <span data-ttu-id="843a3-109">部分条件匹配可能存储在工作内存中，以加快随后的模式匹配操作。</span><span class="sxs-lookup"><span data-stu-id="843a3-109">Partial condition matches may be stored in working memory to expedite subsequent pattern-matching operations.</span></span> <span data-ttu-id="843a3-110">模式匹配阶段的输出由对规则引擎议程的更新组成。</span><span class="sxs-lookup"><span data-stu-id="843a3-110">The output of the pattern-matching phase consists of updates to the rule engine agenda.</span></span>  
  
-   <span data-ttu-id="843a3-111">**冲突解决**。</span><span class="sxs-lookup"><span data-stu-id="843a3-111">**Conflict resolution**.</span></span> <span data-ttu-id="843a3-112">在冲突解决阶段，将检查作为执行候选的规则，以根据预设的解决方案来确定要执行的下一组规则操作。</span><span class="sxs-lookup"><span data-stu-id="843a3-112">In the conflict resolution stage, the rules that are candidates for execution are examined to determine the next set of rule actions to execute based on a predetermined resolution scheme.</span></span> <span data-ttu-id="843a3-113">在匹配阶段找到的所有候选规则都会添加到规则引擎的议程中。</span><span class="sxs-lookup"><span data-stu-id="843a3-113">All candidate rules found during the matching stage are added to the rule engine's agenda.</span></span>  
  
     <span data-ttu-id="843a3-114">默认冲突解决方案基于策略中的规则优先级。</span><span class="sxs-lookup"><span data-stu-id="843a3-114">The default conflict resolution scheme is based on rule priorities within a policy.</span></span> <span data-ttu-id="843a3-115">优先级是业务规则编辑器中可配置的规则属性。</span><span class="sxs-lookup"><span data-stu-id="843a3-115">The priority is a configurable property of a rule in the Business Rule Composer.</span></span> <span data-ttu-id="843a3-116">该数字越大，优先级越高；因此，如果触发多个规则，则首先执行优先级较高的操作。</span><span class="sxs-lookup"><span data-stu-id="843a3-116">The larger the number, the higher the priority; therefore if multiple rules are triggered, the higher-priority actions are executed first.</span></span>  
  
-   <span data-ttu-id="843a3-117">**操作**。</span><span class="sxs-lookup"><span data-stu-id="843a3-117">**Action**.</span></span> <span data-ttu-id="843a3-118">在操作阶段，将执行已解析规则中的操作。</span><span class="sxs-lookup"><span data-stu-id="843a3-118">In the action stage, the actions in the resolved rule are executed.</span></span> <span data-ttu-id="843a3-119">请注意，规则操作可以在规则引擎中添加新的事实，这将导致循环继续。</span><span class="sxs-lookup"><span data-stu-id="843a3-119">Note that rule actions can assert new facts into the rule engine, which causes the cycle to continue.</span></span> <span data-ttu-id="843a3-120">这也称为正向链接。</span><span class="sxs-lookup"><span data-stu-id="843a3-120">This is also known as forward chaining.</span></span> <span data-ttu-id="843a3-121">请注意，算法永远不会抢先于当前正在执行的规则。</span><span class="sxs-lookup"><span data-stu-id="843a3-121">It is important to note that the algorithm never preempts the currently executing rule.</span></span> <span data-ttu-id="843a3-122">在重复匹配阶段之前，将执行当前触发的规则的所有操作。</span><span class="sxs-lookup"><span data-stu-id="843a3-122">All actions for the rule that is currently firing will be executed before the match phase is repeated.</span></span> <span data-ttu-id="843a3-123">但是，再次开始匹配阶段之前，将不会触发议程的其他规则。</span><span class="sxs-lookup"><span data-stu-id="843a3-123">However, other rules on the agenda will not be fired before the match phase begins again.</span></span> <span data-ttu-id="843a3-124">匹配阶段可能导致在触发议程的这些规则之前，从议程中删除这些规则。</span><span class="sxs-lookup"><span data-stu-id="843a3-124">The match phase may cause those rules on the agenda to be removed from the agenda before they ever fire.</span></span>  
  
 <span data-ttu-id="843a3-125">以下示例显示了匹配 - 冲突解决 - 操作的三阶段算法：</span><span class="sxs-lookup"><span data-stu-id="843a3-125">The following example shows the three-stage algorithm of match-conflict resolution-action.</span></span>  
  
 <span data-ttu-id="843a3-126">**规则 1： 评估收入**</span><span class="sxs-lookup"><span data-stu-id="843a3-126">**Rule 1: Evaluate income**</span></span>  
  
-   <span data-ttu-id="843a3-127">声明性表示：</span><span class="sxs-lookup"><span data-stu-id="843a3-127">Declarative representation:</span></span>  
  
     <span data-ttu-id="843a3-128">只有当申请人的收入与贷款比率小于 0.2 时，才应获取申请人的信用等级。</span><span class="sxs-lookup"><span data-stu-id="843a3-128">An applicant's credit rating should be obtained only if the applicant's income-to-loan ratio is less than 0.2.</span></span>  
  
-   <span data-ttu-id="843a3-129">使用业务对象的 IF-THEN 表示:</span><span class="sxs-lookup"><span data-stu-id="843a3-129">IF—THEN representation using business objects:</span></span>  
  
    ```  
    IF Application.Income / Property.Price < 0.2    
    THEN Assert new CreditRating( Application)   
    ```  
  
 <span data-ttu-id="843a3-130">**规则 2： 评估信用等级**</span><span class="sxs-lookup"><span data-stu-id="843a3-130">**Rule 2: Evaluate credit rating**</span></span>  
  
-   <span data-ttu-id="843a3-131">声明性表示：</span><span class="sxs-lookup"><span data-stu-id="843a3-131">Declarative representation:</span></span>  
  
     <span data-ttu-id="843a3-132">只有当申请人的信用等级超过 725 时，才应批准申请人。</span><span class="sxs-lookup"><span data-stu-id="843a3-132">An applicant should be approved only if the applicant's credit rating is more than 725.</span></span>  
  
-   <span data-ttu-id="843a3-133">如果 — 然后使用业务对象的表示形式：</span><span class="sxs-lookup"><span data-stu-id="843a3-133">IF—THEN Representation using business objects:</span></span>  
  
    ```  
    IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
    THEN SendApprovalLetter(Application)    
    ```  
  
 <span data-ttu-id="843a3-134">下表概括列出了事实：</span><span class="sxs-lookup"><span data-stu-id="843a3-134">The facts are summarized in the following table.</span></span>  
  
|<span data-ttu-id="843a3-135">事实</span><span class="sxs-lookup"><span data-stu-id="843a3-135">Fact</span></span>|<span data-ttu-id="843a3-136">字段</span><span class="sxs-lookup"><span data-stu-id="843a3-136">Fields</span></span>|  
|----------|------------|  
|<span data-ttu-id="843a3-137">申请 – XML 文档，表示房屋贷款申请</span><span class="sxs-lookup"><span data-stu-id="843a3-137">Application – An XML document representing a home loan application</span></span>|<span data-ttu-id="843a3-138">-收入 = $65000</span><span class="sxs-lookup"><span data-stu-id="843a3-138">-   Income = $65,000</span></span><br /><span data-ttu-id="843a3-139">-SSN = XXX XX XXXX</span><span class="sxs-lookup"><span data-stu-id="843a3-139">-   SSN = XXX-XX-XXXX</span></span>|  
|<span data-ttu-id="843a3-140">房产 – XML 文档，表示购买的房产</span><span class="sxs-lookup"><span data-stu-id="843a3-140">Property – An XML document representing the property being purchased</span></span>|<span data-ttu-id="843a3-141">-Price = $225,000</span><span class="sxs-lookup"><span data-stu-id="843a3-141">-   Price = $225,000</span></span>|  
|<span data-ttu-id="843a3-142">信用等级 – XML 文档，包含贷款申请人的信用等级</span><span class="sxs-lookup"><span data-stu-id="843a3-142">CreditRating – An XML document containing the loan applicant's credit rating</span></span>|<span data-ttu-id="843a3-143">的值 = 0 – 800</span><span class="sxs-lookup"><span data-stu-id="843a3-143">-   Value = 0 – 800</span></span><br /><span data-ttu-id="843a3-144">-SSN = XXX XX XXXX</span><span class="sxs-lookup"><span data-stu-id="843a3-144">-   SSN = XXX-XX-XXXX</span></span>|  
  
 <span data-ttu-id="843a3-145">规则引擎工作内存和议程最初为空。</span><span class="sxs-lookup"><span data-stu-id="843a3-145">Initially the rule engine working memory and agenda are empty.</span></span> <span data-ttu-id="843a3-146">应用程序添加“申请”和“房产”事实之后，将按如下所示更新规则引擎工作内存和议程：</span><span class="sxs-lookup"><span data-stu-id="843a3-146">After the application adds the Application and Property facts, the rule engine working memory and agenda are updated as follows.</span></span>  
  
|<span data-ttu-id="843a3-147">工作内存</span><span class="sxs-lookup"><span data-stu-id="843a3-147">Working memory</span></span>|<span data-ttu-id="843a3-148">议程</span><span class="sxs-lookup"><span data-stu-id="843a3-148">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="843a3-149">应用程序</span><span class="sxs-lookup"><span data-stu-id="843a3-149">-   Application</span></span><br /><span data-ttu-id="843a3-150">-属性</span><span class="sxs-lookup"><span data-stu-id="843a3-150">-   Property</span></span>|<span data-ttu-id="843a3-151">规则 1</span><span class="sxs-lookup"><span data-stu-id="843a3-151">Rule 1</span></span>|  
  
 <span data-ttu-id="843a3-152">规则 1 添加到安排，因为其条件 (Application.Income / Property.Price < 0.2) 计算结果为**true**匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="843a3-152">Rule 1 is added to the agenda because its condition (Application.Income / Property.Price < 0.2) evaluated to **true** during the match phase.</span></span> <span data-ttu-id="843a3-153">工作内存中没有“信用等级”事实，因此不计算规则 2 的条件。</span><span class="sxs-lookup"><span data-stu-id="843a3-153">There is no CreditRating fact in working memory, so the condition for Rule 2 was not evaluated.</span></span> <span data-ttu-id="843a3-154">由于议程中的唯一规则是规则 1，因此该规则将被执行，然后从议程中消失。</span><span class="sxs-lookup"><span data-stu-id="843a3-154">Because the only rule in the agenda is Rule 1, the rule is executed and then disappears from the agenda.</span></span> <span data-ttu-id="843a3-155">为规则 1 定义的单个操作将导致新的事实（申请人的信用等级文档）添加到工作内存中。</span><span class="sxs-lookup"><span data-stu-id="843a3-155">The single action defined for Rule 1 results in a new fact (CreditRating document for the applicant) being added to working memory.</span></span> <span data-ttu-id="843a3-156">执行完规则 1 之后，控制返回到匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="843a3-156">After the execution of Rule 1 completes, control returns to the match phase.</span></span> <span data-ttu-id="843a3-157">由于要匹配的唯一新对象是“信用等级”事实，因此匹配阶段的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="843a3-157">Because the only new object to match is the CreditRating fact, the results of the match phase are as follows.</span></span>  
  
|<span data-ttu-id="843a3-158">工作内存</span><span class="sxs-lookup"><span data-stu-id="843a3-158">Working memory</span></span>|<span data-ttu-id="843a3-159">议程</span><span class="sxs-lookup"><span data-stu-id="843a3-159">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="843a3-160">应用程序</span><span class="sxs-lookup"><span data-stu-id="843a3-160">-   Application</span></span><br /><span data-ttu-id="843a3-161">-属性</span><span class="sxs-lookup"><span data-stu-id="843a3-161">-   Property</span></span><br /><span data-ttu-id="843a3-162">-CreditRating</span><span class="sxs-lookup"><span data-stu-id="843a3-162">-   CreditRating</span></span>|<span data-ttu-id="843a3-163">规则 2</span><span class="sxs-lookup"><span data-stu-id="843a3-163">Rule 2</span></span>|  
  
 <span data-ttu-id="843a3-164">此时，将执行规则 2，导致调用向申请人发送批准信件的函数。</span><span class="sxs-lookup"><span data-stu-id="843a3-164">At this point Rule 2 is executed, resulting in the invocation of a function that sends an approval letter to the applicant.</span></span> <span data-ttu-id="843a3-165">完成规则 2 之后，执行正向链接算法将返回到匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="843a3-165">After Rule 2 has completed, execution of the forward-chaining algorithm returns to the match phase.</span></span> <span data-ttu-id="843a3-166">由于不再有新的事实要匹配并且议程为空，将终止正向链接，完成策略执行。</span><span class="sxs-lookup"><span data-stu-id="843a3-166">Because there are no longer new facts to match and the agenda is empty, forward chaining terminates and policy execution is complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843a3-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="843a3-167">See Also</span></span>  
 [<span data-ttu-id="843a3-168">规则引擎</span><span class="sxs-lookup"><span data-stu-id="843a3-168">Rule Engine</span></span>](../core/rule-engine.md)