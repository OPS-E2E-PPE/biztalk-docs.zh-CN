---
title: Update1 |Microsoft 文档
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
ms.openlocfilehash: 3a4ea10e72be2a39eedaafa0e00c8f8ac630393b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288397"
---
# <a name="update"></a><span data-ttu-id="e3505-102">Update</span><span class="sxs-lookup"><span data-stu-id="e3505-102">Update</span></span>
<span data-ttu-id="e3505-103">当**更新**调用函数对象，该对象 reasserted 引擎重新评估，基于新数据和状态。</span><span class="sxs-lookup"><span data-stu-id="e3505-103">When **Update** function is invoked an object, the object is reasserted into the engine to be re-evaluated, based on the new data and state.</span></span> <span data-ttu-id="e3505-104">对象可以是类型**TypedXmlDocument**或.NET 类或**该组**或**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="e3505-104">The object can be of type **TypedXmlDocument** or .NET class or **DataConnection** or **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="e3505-105">你还可以使用**更新**函数以提高引擎性能并防止无限循环方案，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="e3505-105">You can also use **Update** function to improve engine performance and prevent endless loop scenarios as described in this topic.</span></span>  
  
 <span data-ttu-id="e3505-106">通常情况下，使用**断言**规则引擎中，工作内存中将新的对象并使用**更新**更新工作内存中的现有对象。</span><span class="sxs-lookup"><span data-stu-id="e3505-106">Typically, you use **Assert** to place a new object in the working memory of the rule engine, and use **Update** to update an already existing object in the working memory.</span></span> <span data-ttu-id="e3505-107">当您添加新的对象时，会评估所有规则的条件。</span><span class="sxs-lookup"><span data-stu-id="e3505-107">When you assert a new object, conditions in all the rules are evaluated.</span></span> <span data-ttu-id="e3505-108">当您更新现有对象时，仅重新评估使用已更新事实的条件，并且如果这些条件评估结果为真，则会将操作添加到议程中。</span><span class="sxs-lookup"><span data-stu-id="e3505-108">When you update an existing object, only conditions that use the updated fact are reevaluated, and actions are added to the agenda if these conditions are evaluated to true.</span></span>  
  
## <a name="using-update-function-on-net-facts"></a><span data-ttu-id="e3505-109">对 .NET 事实使用更新功能</span><span class="sxs-lookup"><span data-stu-id="e3505-109">Using Update function on .NET facts</span></span>  
 <span data-ttu-id="e3505-110">现以下面两个规则举例说明。</span><span class="sxs-lookup"><span data-stu-id="e3505-110">Take the two rules that follow as an example.</span></span> <span data-ttu-id="e3505-111">假设对象**ItemA**和**ItemB**工作内存中已存在。</span><span class="sxs-lookup"><span data-stu-id="e3505-111">Suppose that objects **ItemA** and **ItemB** already exist in working memory.</span></span> <span data-ttu-id="e3505-112">规则 1 的计算结果**Id**属性**ItemA**，设置**Id**属性**ItemB**，然后 reasserts **ItemB**更改后。</span><span class="sxs-lookup"><span data-stu-id="e3505-112">Rule 1 evaluates the **Id** property on **ItemA**, sets the **Id** property on **ItemB**, and then reasserts **ItemB** after the change.</span></span> <span data-ttu-id="e3505-113">当**ItemB** reasserted，它将被视为新的对象和引擎重新评估使用对象的所有规则**ItemB**中的谓词或操作。</span><span class="sxs-lookup"><span data-stu-id="e3505-113">When **ItemB** is reasserted, it is treated as a new object and the engine re-evaluates all rules that use object **ItemB** in the predicates or actions.</span></span> <span data-ttu-id="e3505-114">这可确保规则 2 会针对的新值重新评估**ItemB.Id**，在规则 1 中进行设置。</span><span class="sxs-lookup"><span data-stu-id="e3505-114">This ensures that Rule 2 is re-evaluated against the new value of **ItemB.Id**, as set in Rule 1.</span></span> <span data-ttu-id="e3505-115">规则 2 可能已失败第一次它已计算，但计算结果为**true**计算第二次。</span><span class="sxs-lookup"><span data-stu-id="e3505-115">Rule 2 may have failed the first time it was evaluated, but evaluates to **true** the second time it is evaluated.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e3505-116">规则 1</span><span class="sxs-lookup"><span data-stu-id="e3505-116">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Assert(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="e3505-117">规则 2</span><span class="sxs-lookup"><span data-stu-id="e3505-117">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="e3505-118">通过将对象重新添加到工作内存的功能，用户可以显式控制正向链接方案中的行为。</span><span class="sxs-lookup"><span data-stu-id="e3505-118">This ability to reassert objects into working memory allows the user explicit control over the behavior in forward-chaining scenarios.</span></span> <span data-ttu-id="e3505-119">而此示例中重新添加对象的副作用是还需要重新评估规则 1。</span><span class="sxs-lookup"><span data-stu-id="e3505-119">A side effect of the reassertion in this example, however, is that Rule 1 is also re-evaluated.</span></span> <span data-ttu-id="e3505-120">因为**ItemA.Id**未更改，规则 1 再次计算结果为**true**和**Assert(ItemB)** 操作，将再次引发。</span><span class="sxs-lookup"><span data-stu-id="e3505-120">Because **ItemA.Id** was not changed, Rule 1 again evaluates to **true** and the **Assert(ItemB)** action fires again.</span></span> <span data-ttu-id="e3505-121">而这会导致规则产生无穷循环。</span><span class="sxs-lookup"><span data-stu-id="e3505-121">As a result, the rule creates an endless loop situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3505-122">重新计算规则的默认最大循环计数为 2 ^32。</span><span class="sxs-lookup"><span data-stu-id="e3505-122">The default maximum loop count of re-evaluation of rules is 2^32.</span></span> <span data-ttu-id="e3505-123">对于某些规则，策略执行无法持续很长时间。</span><span class="sxs-lookup"><span data-stu-id="e3505-123">For certain rules, the policy execution could last for a long time.</span></span> <span data-ttu-id="e3505-124">你可以通过调整减少计数**执行循环的最大深度**策略版本的属性。</span><span class="sxs-lookup"><span data-stu-id="e3505-124">You can reduce the count by adjusting the **Maximum Execution Loop Depth** property of the policy version.</span></span>  
  
 <span data-ttu-id="e3505-125">若要能够重新对象声明而无需创建无限循环，你需要与**更新**函数提供了此功能。</span><span class="sxs-lookup"><span data-stu-id="e3505-125">You need to be able to reassert objects without creating endless loops, and the **Update** function provides this capability.</span></span> <span data-ttu-id="e3505-126">如重新声明，**更新**函数执行**收回**和**断言**关联的对象实例，其中已更改了规则操作，但有两个主要差异：</span><span class="sxs-lookup"><span data-stu-id="e3505-126">Like a reassert, the **Update** function performs **Retract** and **Assert** of the associated object instances, which have been changed from rule actions, but there are two key differences:</span></span>  
  
-   <span data-ttu-id="e3505-127">对于只在操作中（而不在谓词中）使用实例类型的规则，其议程的操作将保留在议程中。</span><span class="sxs-lookup"><span data-stu-id="e3505-127">Actions on the agenda for rules where the instance type is only used in the actions (not the predicates) will remain on the agenda.</span></span>  
  
-   <span data-ttu-id="e3505-128">只在操作中使用实例类型的规则将不会重新进行评估。</span><span class="sxs-lookup"><span data-stu-id="e3505-128">Rules that only use the instance type in the actions will not be re-evaluated.</span></span>  
  
 <span data-ttu-id="e3505-129">因此，只在谓词中或者既在谓词中也在操作中使用实例类型的规则将会重新进行评估，并且它们的操作也将根据需要添加到议程中。</span><span class="sxs-lookup"><span data-stu-id="e3505-129">Therefore, rules that use the instance types in either the predicates only or both the predicates and actions will be re-evaluated and their actions added to the agenda as appropriate.</span></span>  
  
 <span data-ttu-id="e3505-130">更改该前面的示例，以使用**更新**函数会确保仅规则 2 会重新评估，因为**ItemB**用于规则 2 的条件。</span><span class="sxs-lookup"><span data-stu-id="e3505-130">Changing the preceding example to use the **Update** function ensures that only Rule 2 is re-evaluated because **ItemB** is used in the condition of Rule 2.</span></span> <span data-ttu-id="e3505-131">不重新计算规则 1，因为**ItemB**仅用在规则 1，消除循环方案的操作。</span><span class="sxs-lookup"><span data-stu-id="e3505-131">Rule 1 is not reevaluated because **ItemB** is only used in the actions of Rule 1, eliminating the looping scenario.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e3505-132">规则 1</span><span class="sxs-lookup"><span data-stu-id="e3505-132">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Update(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="e3505-133">规则 2</span><span class="sxs-lookup"><span data-stu-id="e3505-133">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="e3505-134">但是，它仍然可能会创建循环。</span><span class="sxs-lookup"><span data-stu-id="e3505-134">However, it is still possible to create looping scenarios.</span></span> <span data-ttu-id="e3505-135">例如，考虑以下规则：</span><span class="sxs-lookup"><span data-stu-id="e3505-135">For example, consider the following rule.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e3505-136">规则 1</span><span class="sxs-lookup"><span data-stu-id="e3505-136">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="e3505-137">因为**ItemA**使用在谓词中，它会重新评估时**更新**上调用**ItemA**。</span><span class="sxs-lookup"><span data-stu-id="e3505-137">Because **ItemA** is used in the predicate, it is re-evaluated when **Update** is called on **ItemA**.</span></span> <span data-ttu-id="e3505-138">如果值**ItemA.Id**不会更改到其他位置，规则 1 继续的计算结果为**true**，从而导致**更新**再一次调用上 a。规则设计器必须确保不会创建此类循环情况。</span><span class="sxs-lookup"><span data-stu-id="e3505-138">If the value of **ItemA.Id** is not changed elsewhere, Rule 1 continues to evaluate to **true**, causing **Update** to once again be called on A. The rule designer must ensure that looping scenarios such as this are not created.</span></span>  
  
 <span data-ttu-id="e3505-139">根据规则性质的不同，实现方法也会不同。</span><span class="sxs-lookup"><span data-stu-id="e3505-139">The appropriate approach for this will differ based on the nature of the rules.</span></span> <span data-ttu-id="e3505-140">下面是解决上述示例中的问题的简单机制。</span><span class="sxs-lookup"><span data-stu-id="e3505-140">The following is a simple mechanism to solve the problem in the preceding example.</span></span>  
  
 <span data-ttu-id="e3505-141">**更新**函数可能在类中，引用业务规则编辑器中使用与**断言**，**收回**，或**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="e3505-141">The **Update** function may be used in the Business Rule Composer with a reference to the class, as with the **Assert**, **Retract**, or **RetractByType** functions.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e3505-142">规则 1</span><span class="sxs-lookup"><span data-stu-id="e3505-142">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="e3505-143">上添加检查**ItemA.Value**防止规则 1 评估结果为**true**再次规则 1 的操作在首次执行后。</span><span class="sxs-lookup"><span data-stu-id="e3505-143">Adding the check on **ItemA.Value** prevents Rule 1 from evaluating to **true** again after the actions of Rule 1 are executed the first time.</span></span>  
  
## <a name="using-update-function-on-xml-facts"></a><span data-ttu-id="e3505-144">对 XML 事实使用更新功能</span><span class="sxs-lookup"><span data-stu-id="e3505-144">Using Update function on XML facts</span></span>  
 <span data-ttu-id="e3505-145">现以下面两个规则举例说明。</span><span class="sxs-lookup"><span data-stu-id="e3505-145">Take the two rules that follow as an example.</span></span> <span data-ttu-id="e3505-146">假定</span><span class="sxs-lookup"><span data-stu-id="e3505-146">Suppose that.</span></span> <span data-ttu-id="e3505-147">规则 1 评估采购订单消息中项目的总数，如果总数大于或等于 10，规则 2 便将状态设置为“需要批准”。</span><span class="sxs-lookup"><span data-stu-id="e3505-147">Rule 1 evaluates the total count of the items in a purchase order message, and rule2 sets the status to "Needs approval" if the total count is greater than or equal to 10.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e3505-148">规则 1</span><span class="sxs-lookup"><span data-stu-id="e3505-148">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="e3505-149">规则 2</span><span class="sxs-lookup"><span data-stu-id="e3505-149">Rule 2</span></span>  
  
```  
IF ProcessPO.Order:/Order/Items/TotalCount >= 10  
THEN ProcessPO.Order:/Order/Status = "Needs approval"  
```  
  
 <span data-ttu-id="e3505-150">如果您传入以下的采购订单 (PO) 消息输入到此策略，你注意到即使总项计数为 14，状态未设置为"需要审批"。</span><span class="sxs-lookup"><span data-stu-id="e3505-150">If you pass the following purchase order (PO) message as an input to this policy, you notice that the status is not set to "Needs approval" even though the total item count is 14.</span></span> <span data-ttu-id="e3505-151">这是因为，rule2 被评估为只在开始时的值**TotalCount**字段为 0，并且该规则不会评估每次更新时可用的总数。</span><span class="sxs-lookup"><span data-stu-id="e3505-151">It is because that the rule2 is evaluated only at the beginning when the value of the **TotalCount** field is 0, and the rule is not evaluated each time the total available count is updated.</span></span> <span data-ttu-id="e3505-152">具有条件重新计算每次**TotalCount**是更新，你需要调用**更新**的父节点上的函数 (**项**) 的修改后的节点 (**TotalCount**)。</span><span class="sxs-lookup"><span data-stu-id="e3505-152">To have the conditions reevaluated each time the **TotalCount** is updated, you need to call the **Update** function on the parent node (**Items**) of the modified node (**TotalCount**).</span></span> <span data-ttu-id="e3505-153">如果您按照如下所示更改规则 1，并对其进行多次测试，则您应该看到状态字段被设置成“需要批准”。</span><span class="sxs-lookup"><span data-stu-id="e3505-153">If you change the Rule1 as shown below, and test it one more time, you should see the value of the Status field set to "Needs Approval".</span></span>  
  
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
  
 <span data-ttu-id="e3505-154">已修改**规则 1**如下：</span><span class="sxs-lookup"><span data-stu-id="e3505-154">The modified **Rule 1** is as follows:</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="e3505-155">规则 1</span><span class="sxs-lookup"><span data-stu-id="e3505-155">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a><span data-ttu-id="e3505-156">对数据库事实使用更新功能</span><span class="sxs-lookup"><span data-stu-id="e3505-156">Using Update function on database facts</span></span>  
  
### <a name="typeddatatable"></a><span data-ttu-id="e3505-157">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="e3505-157">TypedDataTable</span></span>  
 <span data-ttu-id="e3505-158">如果**更新**上调用**TypedDataTable**，**更新**对所有关联引擎将调用**TypedDataRows**。</span><span class="sxs-lookup"><span data-stu-id="e3505-158">If **Update** is called on a **TypedDataTable**, **Update** is called by the engine on all associated **TypedDataRows**.</span></span> <span data-ttu-id="e3505-159">**更新**还能对单个调用**TypedDataRows**。</span><span class="sxs-lookup"><span data-stu-id="e3505-159">**Update** may also be called on individual **TypedDataRows**.</span></span>  
  
### <a name="dataconnection"></a><span data-ttu-id="e3505-160">DataConnection</span><span class="sxs-lookup"><span data-stu-id="e3505-160">DataConnection</span></span>  
 <span data-ttu-id="e3505-161">中的更新**该组**不支持。</span><span class="sxs-lookup"><span data-stu-id="e3505-161">Update of a **DataConnection** is not supported.</span></span> <span data-ttu-id="e3505-162">使用**断言**相反。</span><span class="sxs-lookup"><span data-stu-id="e3505-162">Use **Assert** instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3505-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3505-163">See Also</span></span>  
 [<span data-ttu-id="e3505-164">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="e3505-164">Engine Control Functions</span></span>](../core/engine-control-functions.md)