---
title: 规则操作副作用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, side effects
ms.assetid: 1ef65014-9c0a-40d3-b941-2a67c20b54d3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cfcff7fed8a559c725d0180f89cdd0d385b1e0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254614"
---
# <a name="rule-action-side-effects"></a><span data-ttu-id="e2411-102">规则操作副作用</span><span class="sxs-lookup"><span data-stu-id="e2411-102">Rule Action Side Effects</span></span>
<span data-ttu-id="e2411-103">如果执行某个操作影响的一个或多个条件中所使用的术语的状态，该操作被视为对象上具有负面影响。</span><span class="sxs-lookup"><span data-stu-id="e2411-103">If the execution of an action affects the state of an object or a term used in conditions, that action is considered to have a side effect on the object.</span></span>  
  
 <span data-ttu-id="e2411-104">假设我们有以下规则。</span><span class="sxs-lookup"><span data-stu-id="e2411-104">Assume we have the following rules.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="e2411-105">规则 1</span><span class="sxs-lookup"><span data-stu-id="e2411-105">Rule 1</span></span>  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a><span data-ttu-id="e2411-106">规则 2</span><span class="sxs-lookup"><span data-stu-id="e2411-106">Rule 2</span></span>  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 <span data-ttu-id="e2411-107">在这种情况下， **OrderForm.UpdateStatus**称为具有副作用**OrderForm.Status**。</span><span class="sxs-lookup"><span data-stu-id="e2411-107">In this case, **OrderForm.UpdateStatus** is said to have a side effect on **OrderForm.Status**.</span></span> <span data-ttu-id="e2411-108">这并不意味着**OrderForm.UpdateStatus**具有副作用，而是， **OrderForm.Status**可能受到一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="e2411-108">This does not mean that **OrderForm.UpdateStatus** has side effects; instead, **OrderForm.Status** is potentially affected by one or more actions.</span></span>  
  
 <span data-ttu-id="e2411-109">默认情况下**SideEffects**属性为.NET 类成员**true**，这样可以防止规则引擎缓存具有副作用的成员。</span><span class="sxs-lookup"><span data-stu-id="e2411-109">By default, the **SideEffects** property for .NET class members is **true**, which prevents the rule engine from caching the member with side effects.</span></span> <span data-ttu-id="e2411-110">在本示例中，规则引擎不会缓存**OrderForm.Status**中的工作内存中; 而是它获取最新的值**OrderForm.Status**每次计算规则 1。</span><span class="sxs-lookup"><span data-stu-id="e2411-110">In our example, the rule engine does not cache **OrderForm.Status** in the working memory; instead it gets the most up-to-date value of **OrderForm.Status** every time Rule 1 is evaluated.</span></span> <span data-ttu-id="e2411-111">如果**SideEffects**属性设置为**false**，规则引擎缓存的值计算结果的第一次**OrderForm.Status**，但对于更高版本的评估 （在正向链接方案），它使用缓存的值。</span><span class="sxs-lookup"><span data-stu-id="e2411-111">If the **SideEffects** property is set to **false**, the rule engine caches the value first time it evaluates **OrderForm.Status**, but for later evaluations (in forward-chaining scenarios), it uses the cached value.</span></span>  
  
 <span data-ttu-id="e2411-112">当前业务规则编辑器不提供使用户能够修改地**SideEffects**，但是，您可以只设置**SideEffects**通过业务规则框架以编程方式的属性.</span><span class="sxs-lookup"><span data-stu-id="e2411-112">Currently the Business Rule Composer does not provide a way for users to modify **SideEffects**, however, you can only set the **SideEffects** property programmatically through the Business Rules Framework.</span></span> <span data-ttu-id="e2411-113">您设置执行在此操作使用的绑定[ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx)类，以指定对象的方法、 属性和字段规则条件和操作中使用。</span><span class="sxs-lookup"><span data-stu-id="e2411-113">You set do this at binding, using the [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx) class to specify object methods, properties, and fields used in rule conditions and actions.</span></span> <span data-ttu-id="e2411-114">**ClassMemberBinding**有一个属性， [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects)，其中包含一个布尔值，该值指示是否将访问该成员更改其值。</span><span class="sxs-lookup"><span data-stu-id="e2411-114">**ClassMemberBinding** has a property, [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects), which contains a Boolean value indicating whether accessing the member changes its value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2411-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2411-115">See Also</span></span>  
 [<span data-ttu-id="e2411-116">规则引擎</span><span class="sxs-lookup"><span data-stu-id="e2411-116">Rule Engine</span></span>](../core/rule-engine.md)