---
title: 规则操作副作用 |Microsoft 文档
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
ms.openlocfilehash: d2ed890ca8efca6fdd1403c4ec89f4c0c5d32eaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268837"
---
# <a name="rule-action-side-effects"></a><span data-ttu-id="f1377-102">规则操作副作用</span><span class="sxs-lookup"><span data-stu-id="f1377-102">Rule Action Side Effects</span></span>
<span data-ttu-id="f1377-103">如果执行某个操作会影响条件中所使用的对象或术语的状态，则将该操作视为对该对象具有副作用。</span><span class="sxs-lookup"><span data-stu-id="f1377-103">If the execution of an action affects the state of an object or a term used in conditions, that action is considered to have a side effect on the object.</span></span>  
  
 <span data-ttu-id="f1377-104">假设具有以下规则：</span><span class="sxs-lookup"><span data-stu-id="f1377-104">Assume we have the following rules.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="f1377-105">规则 1</span><span class="sxs-lookup"><span data-stu-id="f1377-105">Rule 1</span></span>  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a><span data-ttu-id="f1377-106">规则 2</span><span class="sxs-lookup"><span data-stu-id="f1377-106">Rule 2</span></span>  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 <span data-ttu-id="f1377-107">在这种情况下， **OrderForm.UpdateStatus**称具有副作用**OrderForm.Status**。</span><span class="sxs-lookup"><span data-stu-id="f1377-107">In this case, **OrderForm.UpdateStatus** is said to have a side effect on **OrderForm.Status**.</span></span> <span data-ttu-id="f1377-108">这并不意味着**OrderForm.UpdateStatus**具有副作用; 相反， **OrderForm.Status**由一个或多个操作可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="f1377-108">This does not mean that **OrderForm.UpdateStatus** has side effects; instead, **OrderForm.Status** is potentially affected by one or more actions.</span></span>  
  
 <span data-ttu-id="f1377-109">默认情况下， **SideEffects** .NET 类成员的属性是**true**，从而防止规则引擎缓存具有副作用的成员。</span><span class="sxs-lookup"><span data-stu-id="f1377-109">By default, the **SideEffects** property for .NET class members is **true**, which prevents the rule engine from caching the member with side effects.</span></span> <span data-ttu-id="f1377-110">在本示例中，规则引擎不会缓存**OrderForm.Status**工作内存中; 中改为其获取最新的值**OrderForm.Status**每次计算时规则 1。</span><span class="sxs-lookup"><span data-stu-id="f1377-110">In our example, the rule engine does not cache **OrderForm.Status** in the working memory; instead it gets the most up-to-date value of **OrderForm.Status** every time Rule 1 is evaluated.</span></span> <span data-ttu-id="f1377-111">如果**SideEffects**属性设置为**false**，规则引擎将缓存值计算结果的第一次**OrderForm.Status**，但对于更高版本 （在评估正向链接方案），它使用缓存的值。</span><span class="sxs-lookup"><span data-stu-id="f1377-111">If the **SideEffects** property is set to **false**, the rule engine caches the value first time it evaluates **OrderForm.Status**, but for later evaluations (in forward-chaining scenarios), it uses the cached value.</span></span>  
  
 <span data-ttu-id="f1377-112">当前业务规则编辑器不提供一种方法，使用户可以修改**SideEffects**，但是，仅可以设置**SideEffects**通过业务规则框架以编程方式的属性.</span><span class="sxs-lookup"><span data-stu-id="f1377-112">Currently the Business Rule Composer does not provide a way for users to modify **SideEffects**, however, you can only set the **SideEffects** property programmatically through the Business Rules Framework.</span></span> <span data-ttu-id="f1377-113">你集中执行这一切所需绑定，使用[ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx)类指定对象的方法、 属性和规则条件和操作中使用的字段。</span><span class="sxs-lookup"><span data-stu-id="f1377-113">You set do this at binding, using the [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx) class to specify object methods, properties, and fields used in rule conditions and actions.</span></span> <span data-ttu-id="f1377-114">**ClassMemberBinding**拥有一个属性， [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects)，其中包含一个布尔值，该值指示是否将访问该成员更改其值。</span><span class="sxs-lookup"><span data-stu-id="f1377-114">**ClassMemberBinding** has a property, [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects), which contains a Boolean value indicating whether accessing the member changes its value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1377-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1377-115">See Also</span></span>  
 [<span data-ttu-id="f1377-116">规则引擎</span><span class="sxs-lookup"><span data-stu-id="f1377-116">Rule Engine</span></span>](../core/rule-engine.md)