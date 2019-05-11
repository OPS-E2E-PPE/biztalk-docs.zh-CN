---
title: Update1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update function [Business Rules Engine]
- Update function [Business Rules Engine], TypedXMLDocument
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], .NET objects
- .NET objects
- Update function [Business Rules Engine], DataConnection
ms.assetid: 939e45dc-6433-42f3-a336-8f3c247417ac
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fcb8b79b93dc2f7eeb742579afd7852dc7467a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398623"
---
# <a name="update"></a><span data-ttu-id="e2d98-102">Update</span><span class="sxs-lookup"><span data-stu-id="e2d98-102">Update</span></span>
<span data-ttu-id="e2d98-103">当**更新**调用函数对象，该对象会重新添加到引擎会重新评估，基于新数据和状态。</span><span class="sxs-lookup"><span data-stu-id="e2d98-103">When **Update** function is invoked an object, the object is reasserted into the engine to be re-evaluated, based on the new data and state.</span></span> <span data-ttu-id="e2d98-104">该对象可以是类型**TypedXmlDocument**或.NET 类或**DataConnection**或**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="e2d98-104">The object can be of type **TypedXmlDocument** or .NET class or **DataConnection** or **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="e2d98-105">此外可以使用**更新**函数来提高引擎性能并防止无限循环方案，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="e2d98-105">You can also use **Update** function to improve engine performance and prevent endless loop scenarios as described in this topic.</span></span>  
  
 <span data-ttu-id="e2d98-106">通常情况下，使用**Assert**规则引擎工作内存中放置一个新的对象并使用**更新**更新工作内存中已经存在的对象。</span><span class="sxs-lookup"><span data-stu-id="e2d98-106">Typically, you use **Assert** to place a new object in the working memory of the rule engine, and use **Update** to update an already existing object in the working memory.</span></span> <span data-ttu-id="e2d98-107">当添加新的对象时，将评估中的所有规则的条件。</span><span class="sxs-lookup"><span data-stu-id="e2d98-107">When you assert a new object, conditions in all the rules are evaluated.</span></span> <span data-ttu-id="e2d98-108">更新现有对象，请重新评估使用已更新的事实的条件，并操作添加到议程中，如果这些条件进行计算时为 true。</span><span class="sxs-lookup"><span data-stu-id="e2d98-108">When you update an existing object, only conditions that use the updated fact are reevaluated, and actions are added to the agenda if these conditions are evaluated to true.</span></span>  
  
## <a name="using-update-function-on-net-facts"></a><span data-ttu-id="e2d98-109">对.NET 事实使用更新功能</span><span class="sxs-lookup"><span data-stu-id="e2d98-109">Using Update function on .NET facts</span></span>  
 <span data-ttu-id="e2d98-110">需要按照作为示例的两个规则。</span><span class="sxs-lookup"><span data-stu-id="e2d98-110">Take the two rules that follow as an example.</span></span> <span data-ttu-id="e2d98-111">假设的对象**ItemA**并**ItemB**工作内存中已存在。</span><span class="sxs-lookup"><span data-stu-id="e2d98-111">Suppose that objects **ItemA** and **ItemB** already exist in working memory.</span></span> <span data-ttu-id="e2d98-112">规则 1 评估**Id**上的属性**ItemA**，设置**Id**属性**ItemB**，然后重新添加和**ItemB**在更改后。</span><span class="sxs-lookup"><span data-stu-id="e2d98-112">Rule 1 evaluates the **Id** property on **ItemA**, sets the **Id** property on **ItemB**, and then reasserts **ItemB** after the change.</span></span> <span data-ttu-id="e2d98-113">当**ItemB**重新添加，它被视为新对象和引擎将重新评估使用对象的所有规则**ItemB**谓词或操作中。</span><span class="sxs-lookup"><span data-stu-id="e2d98-113">When **ItemB** is reasserted, it is treated as a new object and the engine re-evaluates all rules that use object **ItemB** in the predicates or actions.</span></span> <span data-ttu-id="e2d98-114">这可确保，是对的新值重新计算规则 2 **ItemB.Id**，按照中的规则 1。</span><span class="sxs-lookup"><span data-stu-id="e2d98-114">This ensures that Rule 2 is re-evaluated against the new value of **ItemB.Id**, as set in Rule 1.</span></span> <span data-ttu-id="e2d98-115">规则 2 可能已失败它已计算，但计算结果为第一次 **，则返回 true**第二次计算。</span><span class="sxs-lookup"><span data-stu-id="e2d98-115">Rule 2 may have failed the first time it was evaluated, but evaluates to **true** the second time it is evaluated.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e2d98-116">规则 1</span><span class="sxs-lookup"><span data-stu-id="e2d98-116">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Assert(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="e2d98-117">规则 2</span><span class="sxs-lookup"><span data-stu-id="e2d98-117">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="e2d98-118">将对象重新添加到工作内存中此功能可在正向链接情况下让用户显式控制行为。</span><span class="sxs-lookup"><span data-stu-id="e2d98-118">This ability to reassert objects into working memory allows the user explicit control over the behavior in forward-chaining scenarios.</span></span> <span data-ttu-id="e2d98-119">在此示例中，副作用的副作用，但还重新计算规则 1。</span><span class="sxs-lookup"><span data-stu-id="e2d98-119">A side effect of the reassertion in this example, however, is that Rule 1 is also re-evaluated.</span></span> <span data-ttu-id="e2d98-120">因为**ItemA.Id**未更改，规则 1 评估结果仍为**true**并**assert （itemb)** 操作会重新触发。</span><span class="sxs-lookup"><span data-stu-id="e2d98-120">Because **ItemA.Id** was not changed, Rule 1 again evaluates to **true** and the **Assert(ItemB)** action fires again.</span></span> <span data-ttu-id="e2d98-121">因此，规则就会创建无限循环情况。</span><span class="sxs-lookup"><span data-stu-id="e2d98-121">As a result, the rule creates an endless loop situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2d98-122">重新计算规则的默认最大循环计数为 2 ^32。</span><span class="sxs-lookup"><span data-stu-id="e2d98-122">The default maximum loop count of re-evaluation of rules is 2^32.</span></span> <span data-ttu-id="e2d98-123">对于某些规则，策略执行可能会持续很长时间。</span><span class="sxs-lookup"><span data-stu-id="e2d98-123">For certain rules, the policy execution could last for a long time.</span></span> <span data-ttu-id="e2d98-124">可以通过调整减少计数**最大执行循环深度**属性的策略版本。</span><span class="sxs-lookup"><span data-stu-id="e2d98-124">You can reduce the count by adjusting the **Maximum Execution Loop Depth** property of the policy version.</span></span>  
  
 <span data-ttu-id="e2d98-125">您需要能够将对象重新添加而无需创建无限循环，并**更新**函数提供了此功能。</span><span class="sxs-lookup"><span data-stu-id="e2d98-125">You need to be able to reassert objects without creating endless loops, and the **Update** function provides this capability.</span></span> <span data-ttu-id="e2d98-126">喜欢 reassert**更新**函数执行**Retract**并**Assert**的关联的对象实例中，这都已更改规则操作，但有两个主要区别：</span><span class="sxs-lookup"><span data-stu-id="e2d98-126">Like a reassert, the **Update** function performs **Retract** and **Assert** of the associated object instances, which have been changed from rule actions, but there are two key differences:</span></span>  
  
- <span data-ttu-id="e2d98-127">在操作 （不在谓词中），才使用实例类型的规则议程中的上的操作将保留在议程中。</span><span class="sxs-lookup"><span data-stu-id="e2d98-127">Actions on the agenda for rules where the instance type is only used in the actions (not the predicates) will remain on the agenda.</span></span>  
  
- <span data-ttu-id="e2d98-128">仅在操作中使用的实例类型的规则不会重新计算。</span><span class="sxs-lookup"><span data-stu-id="e2d98-128">Rules that only use the instance type in the actions will not be re-evaluated.</span></span>  
  
  <span data-ttu-id="e2d98-129">因此，任一谓词仅中的实例类型或同时使用谓词和操作的规则将会重新进行评估，并且其操作添加到根据议程。</span><span class="sxs-lookup"><span data-stu-id="e2d98-129">Therefore, rules that use the instance types in either the predicates only or both the predicates and actions will be re-evaluated and their actions added to the agenda as appropriate.</span></span>  
  
  <span data-ttu-id="e2d98-130">更改上面的示例使用**更新**函数还可确保只有规则 2 会重新评估，因为**ItemB**规则 2 的条件中使用。</span><span class="sxs-lookup"><span data-stu-id="e2d98-130">Changing the preceding example to use the **Update** function ensures that only Rule 2 is re-evaluated because **ItemB** is used in the condition of Rule 2.</span></span> <span data-ttu-id="e2d98-131">不重新计算规则 1，因为**ItemB**仅用在规则 1，消除了循环情况的操作。</span><span class="sxs-lookup"><span data-stu-id="e2d98-131">Rule 1 is not reevaluated because **ItemB** is only used in the actions of Rule 1, eliminating the looping scenario.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e2d98-132">规则 1</span><span class="sxs-lookup"><span data-stu-id="e2d98-132">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Update(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="e2d98-133">规则 2</span><span class="sxs-lookup"><span data-stu-id="e2d98-133">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="e2d98-134">但是，就仍然可以创建循环。</span><span class="sxs-lookup"><span data-stu-id="e2d98-134">However, it is still possible to create looping scenarios.</span></span> <span data-ttu-id="e2d98-135">例如，考虑以下规则。</span><span class="sxs-lookup"><span data-stu-id="e2d98-135">For example, consider the following rule.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e2d98-136">规则 1</span><span class="sxs-lookup"><span data-stu-id="e2d98-136">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="e2d98-137">因为**ItemA**用于在谓词中，它会重新评估时**更新**上调用**ItemA**。</span><span class="sxs-lookup"><span data-stu-id="e2d98-137">Because **ItemA** is used in the predicate, it is re-evaluated when **Update** is called on **ItemA**.</span></span> <span data-ttu-id="e2d98-138">如果的值**ItemA.Id**不会更改到其他位置，规则 1 仍将评估为**true**，从而导致**更新**再一次调用 a规则设计器必须确保不会创建此类循环情况。</span><span class="sxs-lookup"><span data-stu-id="e2d98-138">If the value of **ItemA.Id** is not changed elsewhere, Rule 1 continues to evaluate to **true**, causing **Update** to once again be called on A. The rule designer must ensure that looping scenarios such as this are not created.</span></span>  
  
 <span data-ttu-id="e2d98-139">实现此方法将因规则性质而异。</span><span class="sxs-lookup"><span data-stu-id="e2d98-139">The appropriate approach for this will differ based on the nature of the rules.</span></span> <span data-ttu-id="e2d98-140">下面是一个简单的机制来解决上述示例中的问题。</span><span class="sxs-lookup"><span data-stu-id="e2d98-140">The following is a simple mechanism to solve the problem in the preceding example.</span></span>  
  
 <span data-ttu-id="e2d98-141">**更新**可能会在类中，引用业务规则编辑器中使用函数与一样**Assert**， **Retract**，或**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="e2d98-141">The **Update** function may be used in the Business Rule Composer with a reference to the class, as with the **Assert**, **Retract**, or **RetractByType** functions.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e2d98-142">规则 1</span><span class="sxs-lookup"><span data-stu-id="e2d98-142">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="e2d98-143">在添加复选**ItemA.Value**阻止规则 1 评估结果为**true**再次规则 1 的操作第一次执行后。</span><span class="sxs-lookup"><span data-stu-id="e2d98-143">Adding the check on **ItemA.Value** prevents Rule 1 from evaluating to **true** again after the actions of Rule 1 are executed the first time.</span></span>  
  
## <a name="using-update-function-on-xml-facts"></a><span data-ttu-id="e2d98-144">对 XML 事实使用更新功能</span><span class="sxs-lookup"><span data-stu-id="e2d98-144">Using Update function on XML facts</span></span>  
 <span data-ttu-id="e2d98-145">需要按照作为示例的两个规则。</span><span class="sxs-lookup"><span data-stu-id="e2d98-145">Take the two rules that follow as an example.</span></span> <span data-ttu-id="e2d98-146">假设的。</span><span class="sxs-lookup"><span data-stu-id="e2d98-146">Suppose that.</span></span> <span data-ttu-id="e2d98-147">规则 1 评估采购订单消息中的项的总计数和规则 2 设置为"需要批准"状态的总计数是否大于或等于 10。</span><span class="sxs-lookup"><span data-stu-id="e2d98-147">Rule 1 evaluates the total count of the items in a purchase order message, and rule2 sets the status to "Needs approval" if the total count is greater than or equal to 10.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e2d98-148">规则 1</span><span class="sxs-lookup"><span data-stu-id="e2d98-148">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="e2d98-149">规则 2</span><span class="sxs-lookup"><span data-stu-id="e2d98-149">Rule 2</span></span>  
  
```  
IF ProcessPO.Order:/Order/Items/TotalCount >= 10  
THEN ProcessPO.Order:/Order/Status = "Needs approval"  
```  
  
 <span data-ttu-id="e2d98-150">如果将以下采购订单 (PO) 消息传递作为此策略的输入，你发现即使总项计数为 14，状态未设置为"需要批准"。</span><span class="sxs-lookup"><span data-stu-id="e2d98-150">If you pass the following purchase order (PO) message as an input to this policy, you notice that the status is not set to "Needs approval" even though the total item count is 14.</span></span> <span data-ttu-id="e2d98-151">这是因为，只在开始评估 rule2 时的值**TotalCount**字段为 0，且不评估规则每次更新时可用的总数。</span><span class="sxs-lookup"><span data-stu-id="e2d98-151">It is because that the rule2 is evaluated only at the beginning when the value of the **TotalCount** field is 0, and the rule is not evaluated each time the total available count is updated.</span></span> <span data-ttu-id="e2d98-152">有条件重新计算每次**TotalCount**是更新，需要调用**更新**函数在父节点 (**项**) 的修改后的节点 (**TotalCount**)。</span><span class="sxs-lookup"><span data-stu-id="e2d98-152">To have the conditions reevaluated each time the **TotalCount** is updated, you need to call the **Update** function on the parent node (**Items**) of the modified node (**TotalCount**).</span></span> <span data-ttu-id="e2d98-153">如果更改 Rule1 如下所示，并对其进行测试一次，你应看到状态字段设置为"需要批准"的值。</span><span class="sxs-lookup"><span data-stu-id="e2d98-153">If you change the Rule1 as shown below, and test it one more time, you should see the value of the Status field set to "Needs Approval".</span></span>  
  
```  
<ns0:Order xmlns:ns0="http://ProcessPO.Order">  
    <Items>  
        <Item>  
            <Id>ITM1</Id>  
            <Count>2</Count>  
        </Item>  
        <Item>  
            <Id>ITM2</Id>  
            <Count>5</Count>  
        </Item>  
        <Item>  
            <Id>ITM3</Id>  
            <Count>7</Count>  
        </Item>  
        <TotalCount>0</TotalCount>  
    </Items>  
    <Status>No approval needed</Status>  
</ns0:Order>  
```  
  
 <span data-ttu-id="e2d98-154">已修改**规则 1**如下所示：</span><span class="sxs-lookup"><span data-stu-id="e2d98-154">The modified **Rule 1** is as follows:</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e2d98-155">规则 1</span><span class="sxs-lookup"><span data-stu-id="e2d98-155">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a><span data-ttu-id="e2d98-156">对数据库事实使用更新功能</span><span class="sxs-lookup"><span data-stu-id="e2d98-156">Using Update function on database facts</span></span>  
  
### <a name="typeddatatable"></a><span data-ttu-id="e2d98-157">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="e2d98-157">TypedDataTable</span></span>  
 <span data-ttu-id="e2d98-158">如果**更新**上调用**TypedDataTable**，**更新**上关联的所有引擎将调用**TypedDataRows**。</span><span class="sxs-lookup"><span data-stu-id="e2d98-158">If **Update** is called on a **TypedDataTable**, **Update** is called by the engine on all associated **TypedDataRows**.</span></span> <span data-ttu-id="e2d98-159">**更新**也可能在单个上称为**TypedDataRows**。</span><span class="sxs-lookup"><span data-stu-id="e2d98-159">**Update** may also be called on individual **TypedDataRows**.</span></span>  
  
### <a name="dataconnection"></a><span data-ttu-id="e2d98-160">DataConnection</span><span class="sxs-lookup"><span data-stu-id="e2d98-160">DataConnection</span></span>  
 <span data-ttu-id="e2d98-161">更新**DataConnection**不受支持。</span><span class="sxs-lookup"><span data-stu-id="e2d98-161">Update of a **DataConnection** is not supported.</span></span> <span data-ttu-id="e2d98-162">使用**Assert**相反。</span><span class="sxs-lookup"><span data-stu-id="e2d98-162">Use **Assert** instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d98-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2d98-163">See Also</span></span>  
 [<span data-ttu-id="e2d98-164">引擎控制函数</span><span class="sxs-lookup"><span data-stu-id="e2d98-164">Engine Control Functions</span></span>](../core/engine-control-functions.md)