---
title: 条件评估和执行操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3d971f805ab546bd758166429bdca47e5073a72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356494"
---
# <a name="condition-evaluation-and-action-execution"></a><span data-ttu-id="c9289-102">条件评估和操作执行</span><span class="sxs-lookup"><span data-stu-id="c9289-102">Condition Evaluation and Action Execution</span></span>
<span data-ttu-id="c9289-103">业务规则框架提供了高效的推理引擎，能够将规则链接到.NET 对象、 XML 文档或数据库表。</span><span class="sxs-lookup"><span data-stu-id="c9289-103">The Business Rules Framework provides a highly efficient inference engine capable of linking rules to .NET objects, XML documents, or database tables.</span></span>  
  
 <span data-ttu-id="c9289-104">业务规则引擎策略执行的使用三阶段算法。</span><span class="sxs-lookup"><span data-stu-id="c9289-104">The Business Rule Engine uses a three-stage algorithm for policy execution.</span></span> <span data-ttu-id="c9289-105">这些阶段如下所示：</span><span class="sxs-lookup"><span data-stu-id="c9289-105">The stages are as follows:</span></span>  
  
- <span data-ttu-id="c9289-106">**匹配**。</span><span class="sxs-lookup"><span data-stu-id="c9289-106">**Match**.</span></span> <span data-ttu-id="c9289-107">在匹配阶段中，针对使用的事实类型 （规则引擎工作内存中维护的对象引用） 的谓词匹配事实使用规则条件中定义的谓词。</span><span class="sxs-lookup"><span data-stu-id="c9289-107">In the match stage, facts are matched against the predicates that use the fact type (object references maintained in the rule engine's working memory) using the predicates defined in the rule conditions.</span></span> <span data-ttu-id="c9289-108">为了实现效率，会在策略中的所有规则进行模式匹配和在规则之间共享的条件匹配仅一次。</span><span class="sxs-lookup"><span data-stu-id="c9289-108">For the sake of efficiency, pattern matching occurs over all the rules in the policy, and conditions that are shared across rules are matched only once.</span></span> <span data-ttu-id="c9289-109">部分条件匹配可能存储在工作内存，以加快后续模式匹配操作。</span><span class="sxs-lookup"><span data-stu-id="c9289-109">Partial condition matches may be stored in working memory to expedite subsequent pattern-matching operations.</span></span> <span data-ttu-id="c9289-110">模式匹配阶段的输出包含到规则引擎议程更新。</span><span class="sxs-lookup"><span data-stu-id="c9289-110">The output of the pattern-matching phase consists of updates to the rule engine agenda.</span></span>  
  
- <span data-ttu-id="c9289-111">**冲突解决**。</span><span class="sxs-lookup"><span data-stu-id="c9289-111">**Conflict resolution**.</span></span> <span data-ttu-id="c9289-112">在冲突解决阶段，检查作为执行候选的规则来确定规则操作执行下一组基于预设的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c9289-112">In the conflict resolution stage, the rules that are candidates for execution are examined to determine the next set of rule actions to execute based on a predetermined resolution scheme.</span></span> <span data-ttu-id="c9289-113">在匹配阶段找到的所有候选规则都添加到规则引擎议程中。</span><span class="sxs-lookup"><span data-stu-id="c9289-113">All candidate rules found during the matching stage are added to the rule engine's agenda.</span></span>  
  
   <span data-ttu-id="c9289-114">默认冲突解决架构根据策略中的规则优先级。</span><span class="sxs-lookup"><span data-stu-id="c9289-114">The default conflict resolution scheme is based on rule priorities within a policy.</span></span> <span data-ttu-id="c9289-115">优先级是规则的业务规则编辑器中的可配置属性。</span><span class="sxs-lookup"><span data-stu-id="c9289-115">The priority is a configurable property of a rule in the Business Rule Composer.</span></span> <span data-ttu-id="c9289-116">数字越大，优先级越高;因此如果触发了多个规则，优先级较高的操作首先执行。</span><span class="sxs-lookup"><span data-stu-id="c9289-116">The larger the number, the higher the priority; therefore if multiple rules are triggered, the higher-priority actions are executed first.</span></span>  
  
- <span data-ttu-id="c9289-117">**操作**。</span><span class="sxs-lookup"><span data-stu-id="c9289-117">**Action**.</span></span> <span data-ttu-id="c9289-118">在操作阶段中，执行了解析规则中的操作。</span><span class="sxs-lookup"><span data-stu-id="c9289-118">In the action stage, the actions in the resolved rule are executed.</span></span> <span data-ttu-id="c9289-119">请注意，规则操作可以添加到规则引擎，这将导致循环继续的新的事实。</span><span class="sxs-lookup"><span data-stu-id="c9289-119">Note that rule actions can assert new facts into the rule engine, which causes the cycle to continue.</span></span> <span data-ttu-id="c9289-120">这是也称为正向链接。</span><span class="sxs-lookup"><span data-stu-id="c9289-120">This is also known as forward chaining.</span></span> <span data-ttu-id="c9289-121">请务必注意，算法永远不会抢先于当前正在执行的规则。</span><span class="sxs-lookup"><span data-stu-id="c9289-121">It is important to note that the algorithm never preempts the currently executing rule.</span></span> <span data-ttu-id="c9289-122">在重复匹配阶段之前，将执行当前触发的规则的所有操作。</span><span class="sxs-lookup"><span data-stu-id="c9289-122">All actions for the rule that is currently firing will be executed before the match phase is repeated.</span></span> <span data-ttu-id="c9289-123">但是，再次开始匹配阶段之前也不会触发议程的其他规则。</span><span class="sxs-lookup"><span data-stu-id="c9289-123">However, other rules on the agenda will not be fired before the match phase begins again.</span></span> <span data-ttu-id="c9289-124">匹配阶段可能导致议程要触发议程之前从议程中删除这些规则。</span><span class="sxs-lookup"><span data-stu-id="c9289-124">The match phase may cause those rules on the agenda to be removed from the agenda before they ever fire.</span></span>  
  
  <span data-ttu-id="c9289-125">下面的示例显示了匹配-冲突解决-操作的三阶段算法。</span><span class="sxs-lookup"><span data-stu-id="c9289-125">The following example shows the three-stage algorithm of match-conflict resolution-action.</span></span>  
  
  <span data-ttu-id="c9289-126">**规则 1:评估收入**</span><span class="sxs-lookup"><span data-stu-id="c9289-126">**Rule 1: Evaluate income**</span></span>  
  
- <span data-ttu-id="c9289-127">声明性表示形式：</span><span class="sxs-lookup"><span data-stu-id="c9289-127">Declarative representation:</span></span>  
  
   <span data-ttu-id="c9289-128">仅当申请人的收入与贷款比率小于 0.2，应获取申请人的信用等级。</span><span class="sxs-lookup"><span data-stu-id="c9289-128">An applicant's credit rating should be obtained only if the applicant's income-to-loan ratio is less than 0.2.</span></span>  
  
- <span data-ttu-id="c9289-129">如果 — 然后使用业务对象的表示形式：</span><span class="sxs-lookup"><span data-stu-id="c9289-129">IF—THEN representation using business objects:</span></span>  
  
  ```  
  IF Application.Income / Property.Price < 0.2    
  THEN Assert new CreditRating( Application)   
  ```  
  
  <span data-ttu-id="c9289-130">**规则 2:评估信用等级**</span><span class="sxs-lookup"><span data-stu-id="c9289-130">**Rule 2: Evaluate credit rating**</span></span>  
  
- <span data-ttu-id="c9289-131">声明性表示形式：</span><span class="sxs-lookup"><span data-stu-id="c9289-131">Declarative representation:</span></span>  
  
   <span data-ttu-id="c9289-132">仅当申请人的信用等级超过 725 应批准申请人。</span><span class="sxs-lookup"><span data-stu-id="c9289-132">An applicant should be approved only if the applicant's credit rating is more than 725.</span></span>  
  
- <span data-ttu-id="c9289-133">如果 — 然后使用业务对象的表示形式：</span><span class="sxs-lookup"><span data-stu-id="c9289-133">IF—THEN Representation using business objects:</span></span>  
  
  ```  
  IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
  THEN SendApprovalLetter(Application)    
  ```  
  
  <span data-ttu-id="c9289-134">下表总结了事实数据。</span><span class="sxs-lookup"><span data-stu-id="c9289-134">The facts are summarized in the following table.</span></span>  
  
|<span data-ttu-id="c9289-135">事实</span><span class="sxs-lookup"><span data-stu-id="c9289-135">Fact</span></span>|<span data-ttu-id="c9289-136">字段</span><span class="sxs-lookup"><span data-stu-id="c9289-136">Fields</span></span>|  
|----------|------------|  
|<span data-ttu-id="c9289-137">应用程序 – XML 文档，表示房屋贷款申请</span><span class="sxs-lookup"><span data-stu-id="c9289-137">Application – An XML document representing a home loan application</span></span>|<span data-ttu-id="c9289-138">-收入 = $65000</span><span class="sxs-lookup"><span data-stu-id="c9289-138">-   Income = $65,000</span></span><br /><span data-ttu-id="c9289-139">-   SSN = XXX-XX-XXXX</span><span class="sxs-lookup"><span data-stu-id="c9289-139">-   SSN = XXX-XX-XXXX</span></span>|  
|<span data-ttu-id="c9289-140">属性 – XML 文档，表示购买的房产</span><span class="sxs-lookup"><span data-stu-id="c9289-140">Property – An XML document representing the property being purchased</span></span>|<span data-ttu-id="c9289-141">-Price = $225,000</span><span class="sxs-lookup"><span data-stu-id="c9289-141">-   Price = $225,000</span></span>|  
|<span data-ttu-id="c9289-142">信用等级 – XML 文档包含贷款申请人的信用等级</span><span class="sxs-lookup"><span data-stu-id="c9289-142">CreditRating – An XML document containing the loan applicant's credit rating</span></span>|<span data-ttu-id="c9289-143">的值 = 0-800</span><span class="sxs-lookup"><span data-stu-id="c9289-143">-   Value = 0 – 800</span></span><br /><span data-ttu-id="c9289-144">-   SSN = XXX-XX-XXXX</span><span class="sxs-lookup"><span data-stu-id="c9289-144">-   SSN = XXX-XX-XXXX</span></span>|  
  
 <span data-ttu-id="c9289-145">规则引擎工作内存和议程最初是空的。</span><span class="sxs-lookup"><span data-stu-id="c9289-145">Initially the rule engine working memory and agenda are empty.</span></span> <span data-ttu-id="c9289-146">应用程序添加的应用程序和属性的事实数据后，规则引擎工作内存和议程更新，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c9289-146">After the application adds the Application and Property facts, the rule engine working memory and agenda are updated as follows.</span></span>  
  
|<span data-ttu-id="c9289-147">工作内存</span><span class="sxs-lookup"><span data-stu-id="c9289-147">Working memory</span></span>|<span data-ttu-id="c9289-148">议程</span><span class="sxs-lookup"><span data-stu-id="c9289-148">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="c9289-149">-   Application</span><span class="sxs-lookup"><span data-stu-id="c9289-149">-   Application</span></span><br /><span data-ttu-id="c9289-150">-属性</span><span class="sxs-lookup"><span data-stu-id="c9289-150">-   Property</span></span>|<span data-ttu-id="c9289-151">规则 1</span><span class="sxs-lookup"><span data-stu-id="c9289-151">Rule 1</span></span>|  
  
 <span data-ttu-id="c9289-152">规则 1 添加到议程，因为其条件 (Application.Income / Property.Price < 0.2) 的计算结果为 **，则返回 true**在匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="c9289-152">Rule 1 is added to the agenda because its condition (Application.Income / Property.Price < 0.2) evaluated to **true** during the match phase.</span></span> <span data-ttu-id="c9289-153">有工作内存中是没有信用等级事实，因此不计算规则 2 的条件。</span><span class="sxs-lookup"><span data-stu-id="c9289-153">There is no CreditRating fact in working memory, so the condition for Rule 2 was not evaluated.</span></span> <span data-ttu-id="c9289-154">由于议程中的唯一规则是规则 1，此规则执行，并从议程中然后消失。</span><span class="sxs-lookup"><span data-stu-id="c9289-154">Because the only rule in the agenda is Rule 1, the rule is executed and then disappears from the agenda.</span></span> <span data-ttu-id="c9289-155">为规则 1 会导致新的事实 （申请人的信用等级文档） 定义的单个操作添加到工作内存中。</span><span class="sxs-lookup"><span data-stu-id="c9289-155">The single action defined for Rule 1 results in a new fact (CreditRating document for the applicant) being added to working memory.</span></span> <span data-ttu-id="c9289-156">规则 1 在执行完成后，控件返回到匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="c9289-156">After the execution of Rule 1 completes, control returns to the match phase.</span></span> <span data-ttu-id="c9289-157">要匹配的唯一新对象是信用等级这一事实，因为在匹配阶段的结果如下所示。</span><span class="sxs-lookup"><span data-stu-id="c9289-157">Because the only new object to match is the CreditRating fact, the results of the match phase are as follows.</span></span>  
  
|<span data-ttu-id="c9289-158">工作内存</span><span class="sxs-lookup"><span data-stu-id="c9289-158">Working memory</span></span>|<span data-ttu-id="c9289-159">议程</span><span class="sxs-lookup"><span data-stu-id="c9289-159">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="c9289-160">-   Application</span><span class="sxs-lookup"><span data-stu-id="c9289-160">-   Application</span></span><br /><span data-ttu-id="c9289-161">-属性</span><span class="sxs-lookup"><span data-stu-id="c9289-161">-   Property</span></span><br /><span data-ttu-id="c9289-162">的信用等级</span><span class="sxs-lookup"><span data-stu-id="c9289-162">-   CreditRating</span></span>|<span data-ttu-id="c9289-163">规则 2</span><span class="sxs-lookup"><span data-stu-id="c9289-163">Rule 2</span></span>|  
  
 <span data-ttu-id="c9289-164">此时将执行规则 2，从而导致调用向申请人发送批准信件的函数。</span><span class="sxs-lookup"><span data-stu-id="c9289-164">At this point Rule 2 is executed, resulting in the invocation of a function that sends an approval letter to the applicant.</span></span> <span data-ttu-id="c9289-165">完成规则 2 之后，执行正向链接算法将返回到匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="c9289-165">After Rule 2 has completed, execution of the forward-chaining algorithm returns to the match phase.</span></span> <span data-ttu-id="c9289-166">由于不再有新的事实要匹配并且议程为空，则终止正向链接，策略执行已完成。</span><span class="sxs-lookup"><span data-stu-id="c9289-166">Because there are no longer new facts to match and the agenda is empty, forward chaining terminates and policy execution is complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9289-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9289-167">See Also</span></span>  
 [<span data-ttu-id="c9289-168">规则引擎</span><span class="sxs-lookup"><span data-stu-id="c9289-168">Rule Engine</span></span>](../core/rule-engine.md)