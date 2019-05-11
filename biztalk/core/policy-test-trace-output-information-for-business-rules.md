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
ms.openlocfilehash: 427eb9f1a7cae3cd6a1c9a6fe9a5ecac82e60c80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394939"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a><span data-ttu-id="c1c3e-102">业务规则的策略测试跟踪输出信息</span><span class="sxs-lookup"><span data-stu-id="c1c3e-102">Policy Test Trace Output Information for Business Rules</span></span>
<span data-ttu-id="c1c3e-103">本部分提供在业务规则编辑器测试策略时显示的跟踪信息的信息。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-103">This section provides information on the tracking information that is displayed when testing a policy in the Business Rule Composer.</span></span> <span data-ttu-id="c1c3e-104">查看跟踪结果的策略执行，使用组中心页上跟踪查询的消息事件和服务实例时，会看到非常相似的信息。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-104">Very similar information is seen when viewing tracking results for policy execution using the message event and service instance tracking queries on the Group Hub page.</span></span>  
  
 <span data-ttu-id="c1c3e-105">有四种跟踪输出中显示的语句类型：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-105">There are four statement types that are displayed in the tracking output:</span></span>  
  
- <span data-ttu-id="c1c3e-106">事实活动</span><span class="sxs-lookup"><span data-stu-id="c1c3e-106">Fact Activity</span></span>  
  
- <span data-ttu-id="c1c3e-107">条件评估</span><span class="sxs-lookup"><span data-stu-id="c1c3e-107">Condition Evaluation</span></span>  
  
- <span data-ttu-id="c1c3e-108">议程更新</span><span class="sxs-lookup"><span data-stu-id="c1c3e-108">Agenda Update</span></span>  
  
- <span data-ttu-id="c1c3e-109">触发的规则</span><span class="sxs-lookup"><span data-stu-id="c1c3e-109">Rule Fired</span></span>  
  
  <span data-ttu-id="c1c3e-110">下面描述了每个语句类型。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-110">Each statement type is described below.</span></span>  
  
## <a name="fact-activity"></a><span data-ttu-id="c1c3e-111">事实活动</span><span class="sxs-lookup"><span data-stu-id="c1c3e-111">Fact Activity</span></span>  
 <span data-ttu-id="c1c3e-112">此语句指示对引擎工作内存中存在的事实的更改。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-112">This statement indicates changes to the facts present in the working memory of the engine.</span></span> <span data-ttu-id="c1c3e-113">下面是一个事实活动条目示例：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-113">The following is an example of a fact activity entry:</span></span>  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a><span data-ttu-id="c1c3e-114">规则引擎实例标识符</span><span class="sxs-lookup"><span data-stu-id="c1c3e-114">Rule Engine Instance Identifier</span></span>  
 <span data-ttu-id="c1c3e-115">唯一标识符**RuleEngine**提供规则触发的执行环境的实例。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-115">Unique identifier for the **RuleEngine** instance that provides the execution environment for the rule firing.</span></span>  
  
### <a name="ruleset-name"></a><span data-ttu-id="c1c3e-116">规则集名称</span><span class="sxs-lookup"><span data-stu-id="c1c3e-116">Ruleset Name</span></span>  
 <span data-ttu-id="c1c3e-117">规则集 （策略） 的名称。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-117">The name of the rule set (policy).</span></span>  
  
### <a name="operation"></a><span data-ttu-id="c1c3e-118">操作</span><span class="sxs-lookup"><span data-stu-id="c1c3e-118">Operation</span></span>  
 <span data-ttu-id="c1c3e-119">有三种类型的事实活动中可能会发生的操作：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-119">There are three types of operation that can occur in a fact activity:</span></span>  
  
 <span data-ttu-id="c1c3e-120">ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="c1c3e-120">Assert</span></span>  
  
 <span data-ttu-id="c1c3e-121">事实将添加到工作内存。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-121">The fact is being added to the working memory.</span></span>  
  
 <span data-ttu-id="c1c3e-122">Update</span><span class="sxs-lookup"><span data-stu-id="c1c3e-122">Update</span></span>  
  
 <span data-ttu-id="c1c3e-123">这一事实由规则正在更新，然后需要重新添加到要重新计算，基于新数据和状态的引擎。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-123">The fact is being updated by a rule and then needs to be reasserted into the engine to be re-evaluated, based on the new data and state.</span></span>  
  
 <span data-ttu-id="c1c3e-124">收回</span><span class="sxs-lookup"><span data-stu-id="c1c3e-124">Retract</span></span>  
  
 <span data-ttu-id="c1c3e-125">正在从工作内存中删除这一事实。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-125">The fact is being removed from the working memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1c3e-126">如果所添加事实，其类型不匹配任何策略中使用的类型，则添加操作将显示"添加-事实无法识别"。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-126">If a fact is asserted whose type does not match any of the types used in the policy, the Assert operation will display "Assert – Fact Unrecognized".</span></span>  
  
### <a name="object-type"></a><span data-ttu-id="c1c3e-127">对象类型</span><span class="sxs-lookup"><span data-stu-id="c1c3e-127">Object Type</span></span>  
 <span data-ttu-id="c1c3e-128">特定活动的事实类型：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-128">The type of fact for a particular activity:</span></span>  
  
-   <span data-ttu-id="c1c3e-129">DataConnection</span><span class="sxs-lookup"><span data-stu-id="c1c3e-129">DataConnection</span></span>  
  
-   <span data-ttu-id="c1c3e-130">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="c1c3e-130">TypedDataTable</span></span>  
  
-   <span data-ttu-id="c1c3e-131">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="c1c3e-131">TypedDataRow</span></span>  
  
     <span data-ttu-id="c1c3e-132">作为 Typeddatarow 添加 TypedDataTable 时添加的所有包含的行。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-132">When a TypedDataTable is asserted all of the contained rows are asserted as TypedDataRows.</span></span>  <span data-ttu-id="c1c3e-133">才计算条件并执行生成的查询，则会添加与 DataConnection 关联的 TypedDataRows。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-133">TypedDataRows associated with a DataConnection are not asserted until a condition is evaluated and the resulting query is executed.</span></span>  
  
-   <span data-ttu-id="c1c3e-134">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="c1c3e-134">TypedXmlDocument</span></span>  
  
     <span data-ttu-id="c1c3e-135">父级和子级 TypedXmlDocument 实例都可以看到断言。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-135">Assertions will be seen for both parent and child TypedXmlDocument instances.</span></span>  
  
### <a name="object-instance-identifier"></a><span data-ttu-id="c1c3e-136">对象实例标识符</span><span class="sxs-lookup"><span data-stu-id="c1c3e-136">Object Instance Identifier</span></span>  
 <span data-ttu-id="c1c3e-137">事实引用的唯一实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-137">Unique instance ID of the fact reference.</span></span>  
  
## <a name="condition-evaluation"></a><span data-ttu-id="c1c3e-138">条件评估</span><span class="sxs-lookup"><span data-stu-id="c1c3e-138">Condition Evaluation</span></span>  
 <span data-ttu-id="c1c3e-139">此活动指示评估各个谓词的结果。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-139">This activity indicates the result of evaluating individual predicates.</span></span> <span data-ttu-id="c1c3e-140">下面是一个条件评估条目示例：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-140">The following is an example of a condition evaluation entry:</span></span>  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 <span data-ttu-id="c1c3e-141">对于某些中前面的示例中的条款的说明如下所示：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-141">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="c1c3e-142">**测试表达式。**</span><span class="sxs-lookup"><span data-stu-id="c1c3e-142">**Test Expression.**</span></span> <span data-ttu-id="c1c3e-143">在规则中的简单 （一元或二元） 表达式。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-143">A simple (unary or binary) expression within a rule.</span></span>  
  
-   <span data-ttu-id="c1c3e-144">**左的操作数的值。**</span><span class="sxs-lookup"><span data-stu-id="c1c3e-144">**Left Operand Value.**</span></span> <span data-ttu-id="c1c3e-145">在左侧和右侧的表达式术语的值。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-145">The value of the term on the left side of an expression.</span></span>  
  
-   <span data-ttu-id="c1c3e-146">**右操作数的值。**</span><span class="sxs-lookup"><span data-stu-id="c1c3e-146">**Right Operand Value.**</span></span> <span data-ttu-id="c1c3e-147">在表达式右侧术语的值。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-147">The value of the term on the right side of an expression.</span></span>  
  
-   <span data-ttu-id="c1c3e-148">**测试结果。**</span><span class="sxs-lookup"><span data-stu-id="c1c3e-148">**Test Result.**</span></span> <span data-ttu-id="c1c3e-149">结果计算，这为 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-149">The result of the evaluation, which is either True or False.</span></span>  
  
## <a name="agenda-update"></a><span data-ttu-id="c1c3e-150">议程更新</span><span class="sxs-lookup"><span data-stu-id="c1c3e-150">Agenda Update</span></span>  
 <span data-ttu-id="c1c3e-151">此活动指示添加到规则引擎议程中以便后续执行的规则。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-151">This activity indicates rules that are added to the rule engine agenda for subsequent execution.</span></span> <span data-ttu-id="c1c3e-152">下面是一个议程更新条目示例：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-152">The following is an example of an agenda update entry:</span></span>  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 <span data-ttu-id="c1c3e-153">对于某些中前面的示例中的条款的说明如下所示：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-153">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="c1c3e-154">**操作。**</span><span class="sxs-lookup"><span data-stu-id="c1c3e-154">**Operation.**</span></span> <span data-ttu-id="c1c3e-155">可以添加或从议程中删除规则。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-155">Rules can be added or removed from the agenda.</span></span>  
  
-   <span data-ttu-id="c1c3e-156">**规则名称。**</span><span class="sxs-lookup"><span data-stu-id="c1c3e-156">**Rule Name.**</span></span> <span data-ttu-id="c1c3e-157">要添加到议程的规则的名称。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-157">The name of the rule that is being added to the agenda.</span></span>  
  
-   <span data-ttu-id="c1c3e-158">**冲突解决标准。**</span><span class="sxs-lookup"><span data-stu-id="c1c3e-158">**Conflict Resolution Criteria.**</span></span> <span data-ttu-id="c1c3e-159">规则的优先级，用于确定执行操作的相对顺序 （首先执行优先级较高的操作）。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-159">The priority of a rule, which determines the relative order in which actions are executed (higher-priority actions are executed first).</span></span>  
  
## <a name="rule-fired"></a><span data-ttu-id="c1c3e-160">触发的规则</span><span class="sxs-lookup"><span data-stu-id="c1c3e-160">Rule Fired</span></span>  
 <span data-ttu-id="c1c3e-161">此活动指示规则的操作的执行。</span><span class="sxs-lookup"><span data-stu-id="c1c3e-161">This activity indicates the execution of a rule's actions.</span></span> <span data-ttu-id="c1c3e-162">下面是一个规则触发条目示例：</span><span class="sxs-lookup"><span data-stu-id="c1c3e-162">The following is an example of a rule fired entry:</span></span>  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```