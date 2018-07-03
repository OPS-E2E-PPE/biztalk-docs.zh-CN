---
title: 业务规则的策略测试跟踪输出信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, business rules
- testing, policies
- business rules, testing
- policies, testing
ms.assetid: 26ff584e-97a1-4d76-a8a9-a55b4c99231f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8795e926d496f586d032bb85fe4a1fddb473ec5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005134"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a><span data-ttu-id="11d14-102">业务规则的策略测试跟踪输出信息</span><span class="sxs-lookup"><span data-stu-id="11d14-102">Policy Test Trace Output Information for Business Rules</span></span>
<span data-ttu-id="11d14-103">本部分介绍了在业务规则编辑器中测试策略时显示的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="11d14-103">This section provides information on the tracking information that is displayed when testing a policy in the Business Rule Composer.</span></span> <span data-ttu-id="11d14-104">使用“组中心”页上的消息事件和服务实例跟踪查询查看策略执行的跟踪结果时，会看到非常相似的信息。</span><span class="sxs-lookup"><span data-stu-id="11d14-104">Very similar information is seen when viewing tracking results for policy execution using the message event and service instance tracking queries on the Group Hub page.</span></span>  
  
 <span data-ttu-id="11d14-105">跟踪输出中显示有四种语句类型：</span><span class="sxs-lookup"><span data-stu-id="11d14-105">There are four statement types that are displayed in the tracking output:</span></span>  
  
- <span data-ttu-id="11d14-106">事实活动</span><span class="sxs-lookup"><span data-stu-id="11d14-106">Fact Activity</span></span>  
  
- <span data-ttu-id="11d14-107">条件评估</span><span class="sxs-lookup"><span data-stu-id="11d14-107">Condition Evaluation</span></span>  
  
- <span data-ttu-id="11d14-108">议程更新</span><span class="sxs-lookup"><span data-stu-id="11d14-108">Agenda Update</span></span>  
  
- <span data-ttu-id="11d14-109">触发的规则</span><span class="sxs-lookup"><span data-stu-id="11d14-109">Rule Fired</span></span>  
  
  <span data-ttu-id="11d14-110">下面介绍了每种语句类型。</span><span class="sxs-lookup"><span data-stu-id="11d14-110">Each statement type is described below.</span></span>  
  
## <a name="fact-activity"></a><span data-ttu-id="11d14-111">事实活动</span><span class="sxs-lookup"><span data-stu-id="11d14-111">Fact Activity</span></span>  
 <span data-ttu-id="11d14-112">此语句指示对引擎工作内存中存在的事实的更改。</span><span class="sxs-lookup"><span data-stu-id="11d14-112">This statement indicates changes to the facts present in the working memory of the engine.</span></span> <span data-ttu-id="11d14-113">下面列出了一个事实活动条目示例：</span><span class="sxs-lookup"><span data-stu-id="11d14-113">The following is an example of a fact activity entry:</span></span>  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a><span data-ttu-id="11d14-114">规则引擎实例标识符</span><span class="sxs-lookup"><span data-stu-id="11d14-114">Rule Engine Instance Identifier</span></span>  
 <span data-ttu-id="11d14-115">唯一标识符**RuleEngine**提供规则触发的执行环境的实例。</span><span class="sxs-lookup"><span data-stu-id="11d14-115">Unique identifier for the **RuleEngine** instance that provides the execution environment for the rule firing.</span></span>  
  
### <a name="ruleset-name"></a><span data-ttu-id="11d14-116">规则集名称</span><span class="sxs-lookup"><span data-stu-id="11d14-116">Ruleset Name</span></span>  
 <span data-ttu-id="11d14-117">规则集（策略）的名称。</span><span class="sxs-lookup"><span data-stu-id="11d14-117">The name of the rule set (policy).</span></span>  
  
### <a name="operation"></a><span data-ttu-id="11d14-118">运算</span><span class="sxs-lookup"><span data-stu-id="11d14-118">Operation</span></span>  
 <span data-ttu-id="11d14-119">可以在事实活动中执行三种类型的操作：</span><span class="sxs-lookup"><span data-stu-id="11d14-119">There are three types of operation that can occur in a fact activity:</span></span>  
  
 <span data-ttu-id="11d14-120">ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="11d14-120">Assert</span></span>  
  
 <span data-ttu-id="11d14-121">事实将添加到工作内存中。</span><span class="sxs-lookup"><span data-stu-id="11d14-121">The fact is being added to the working memory.</span></span>  
  
 <span data-ttu-id="11d14-122">Update</span><span class="sxs-lookup"><span data-stu-id="11d14-122">Update</span></span>  
  
 <span data-ttu-id="11d14-123">事实将按规则进行更新，然后需要重新添加到引擎中，才能根据新的数据和状态重新进行评估。</span><span class="sxs-lookup"><span data-stu-id="11d14-123">The fact is being updated by a rule and then needs to be reasserted into the engine to be re-evaluated, based on the new data and state.</span></span>  
  
 <span data-ttu-id="11d14-124">收回</span><span class="sxs-lookup"><span data-stu-id="11d14-124">Retract</span></span>  
  
 <span data-ttu-id="11d14-125">事实将从工作内存中删除。</span><span class="sxs-lookup"><span data-stu-id="11d14-125">The fact is being removed from the working memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11d14-126">如果所添加事实，其类型不匹配任何策略中使用的类型，则添加操作将显示"添加-事实无法识别"。</span><span class="sxs-lookup"><span data-stu-id="11d14-126">If a fact is asserted whose type does not match any of the types used in the policy, the Assert operation will display "Assert – Fact Unrecognized".</span></span>  
  
### <a name="object-type"></a><span data-ttu-id="11d14-127">对象类型</span><span class="sxs-lookup"><span data-stu-id="11d14-127">Object Type</span></span>  
 <span data-ttu-id="11d14-128">特定活动的事实类型：</span><span class="sxs-lookup"><span data-stu-id="11d14-128">The type of fact for a particular activity:</span></span>  
  
-   <span data-ttu-id="11d14-129">DataConnection</span><span class="sxs-lookup"><span data-stu-id="11d14-129">DataConnection</span></span>  
  
-   <span data-ttu-id="11d14-130">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="11d14-130">TypedDataTable</span></span>  
  
-   <span data-ttu-id="11d14-131">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="11d14-131">TypedDataRow</span></span>  
  
     <span data-ttu-id="11d14-132">添加 TypedDataTable 时，包含的所有行都将作为 TypedDataRows 添加。</span><span class="sxs-lookup"><span data-stu-id="11d14-132">When a TypedDataTable is asserted all of the contained rows are asserted as TypedDataRows.</span></span>  <span data-ttu-id="11d14-133">在评估条件并执行结果查询后，才会添加与 DataConnection 关联的 TypedDataRows。</span><span class="sxs-lookup"><span data-stu-id="11d14-133">TypedDataRows associated with a DataConnection are not asserted until a condition is evaluated and the resulting query is executed.</span></span>  
  
-   <span data-ttu-id="11d14-134">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="11d14-134">TypedXmlDocument</span></span>  
  
     <span data-ttu-id="11d14-135">父 TypedXmlDocument 实例和子 TypedXmlDocument 实例的断言都可以看到。</span><span class="sxs-lookup"><span data-stu-id="11d14-135">Assertions will be seen for both parent and child TypedXmlDocument instances.</span></span>  
  
### <a name="object-instance-identifier"></a><span data-ttu-id="11d14-136">对象实例标识符</span><span class="sxs-lookup"><span data-stu-id="11d14-136">Object Instance Identifier</span></span>  
 <span data-ttu-id="11d14-137">事实引用的唯一实例 ID。</span><span class="sxs-lookup"><span data-stu-id="11d14-137">Unique instance ID of the fact reference.</span></span>  
  
## <a name="condition-evaluation"></a><span data-ttu-id="11d14-138">条件评估</span><span class="sxs-lookup"><span data-stu-id="11d14-138">Condition Evaluation</span></span>  
 <span data-ttu-id="11d14-139">此活动指示评估各个谓词的结果。</span><span class="sxs-lookup"><span data-stu-id="11d14-139">This activity indicates the result of evaluating individual predicates.</span></span> <span data-ttu-id="11d14-140">下面列出了一个条件评估条目示例：</span><span class="sxs-lookup"><span data-stu-id="11d14-140">The following is an example of a condition evaluation entry:</span></span>  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 <span data-ttu-id="11d14-141">下面对上例中的某些术语进行了说明：</span><span class="sxs-lookup"><span data-stu-id="11d14-141">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="11d14-142">**测试表达式。**</span><span class="sxs-lookup"><span data-stu-id="11d14-142">**Test Expression.**</span></span> <span data-ttu-id="11d14-143">规则中的简单（一元或二元）表达式。</span><span class="sxs-lookup"><span data-stu-id="11d14-143">A simple (unary or binary) expression within a rule.</span></span>  
  
-   <span data-ttu-id="11d14-144">**左的操作数的值。**</span><span class="sxs-lookup"><span data-stu-id="11d14-144">**Left Operand Value.**</span></span> <span data-ttu-id="11d14-145">表达式左侧项的值。</span><span class="sxs-lookup"><span data-stu-id="11d14-145">The value of the term on the left side of an expression.</span></span>  
  
-   <span data-ttu-id="11d14-146">**右操作数的值。**</span><span class="sxs-lookup"><span data-stu-id="11d14-146">**Right Operand Value.**</span></span> <span data-ttu-id="11d14-147">表达式右侧项的值。</span><span class="sxs-lookup"><span data-stu-id="11d14-147">The value of the term on the right side of an expression.</span></span>  
  
-   <span data-ttu-id="11d14-148">**测试结果。**</span><span class="sxs-lookup"><span data-stu-id="11d14-148">**Test Result.**</span></span> <span data-ttu-id="11d14-149">评估的结果，即 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="11d14-149">The result of the evaluation, which is either True or False.</span></span>  
  
## <a name="agenda-update"></a><span data-ttu-id="11d14-150">议程更新</span><span class="sxs-lookup"><span data-stu-id="11d14-150">Agenda Update</span></span>  
 <span data-ttu-id="11d14-151">此活动指示添加到规则引擎议程中以便随后执行的规则。</span><span class="sxs-lookup"><span data-stu-id="11d14-151">This activity indicates rules that are added to the rule engine agenda for subsequent execution.</span></span> <span data-ttu-id="11d14-152">下面列出了一个议程更新条目示例：</span><span class="sxs-lookup"><span data-stu-id="11d14-152">The following is an example of an agenda update entry:</span></span>  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 <span data-ttu-id="11d14-153">下面对上例中的某些术语进行了说明：</span><span class="sxs-lookup"><span data-stu-id="11d14-153">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="11d14-154">**操作。**</span><span class="sxs-lookup"><span data-stu-id="11d14-154">**Operation.**</span></span> <span data-ttu-id="11d14-155">可以在议程中添加或删除规则。</span><span class="sxs-lookup"><span data-stu-id="11d14-155">Rules can be added or removed from the agenda.</span></span>  
  
-   <span data-ttu-id="11d14-156">**规则名称。**</span><span class="sxs-lookup"><span data-stu-id="11d14-156">**Rule Name.**</span></span> <span data-ttu-id="11d14-157">向议程添加的规则的名称。</span><span class="sxs-lookup"><span data-stu-id="11d14-157">The name of the rule that is being added to the agenda.</span></span>  
  
-   <span data-ttu-id="11d14-158">**冲突解决标准。**</span><span class="sxs-lookup"><span data-stu-id="11d14-158">**Conflict Resolution Criteria.**</span></span> <span data-ttu-id="11d14-159">规则的优先级，用于确定执行操作的相对顺序（首先执行优先级较高的操作）。</span><span class="sxs-lookup"><span data-stu-id="11d14-159">The priority of a rule, which determines the relative order in which actions are executed (higher-priority actions are executed first).</span></span>  
  
## <a name="rule-fired"></a><span data-ttu-id="11d14-160">触发的规则</span><span class="sxs-lookup"><span data-stu-id="11d14-160">Rule Fired</span></span>  
 <span data-ttu-id="11d14-161">此活动指示规则操作的执行情况。</span><span class="sxs-lookup"><span data-stu-id="11d14-161">This activity indicates the execution of a rule's actions.</span></span> <span data-ttu-id="11d14-162">下面列出了一个规则触发条目示例：</span><span class="sxs-lookup"><span data-stu-id="11d14-162">The following is an example of a rule fired entry:</span></span>  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```