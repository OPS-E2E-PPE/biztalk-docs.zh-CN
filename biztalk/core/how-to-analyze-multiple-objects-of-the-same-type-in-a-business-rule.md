---
title: "如何分析的业务规则中的相同类型的多个对象 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a1e4d2fb01513b1d4d314264ab74b84d3a0223a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a><span data-ttu-id="6d533-102">如何分析的业务规则中的相同类型的多个对象</span><span class="sxs-lookup"><span data-stu-id="6d533-102">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>
<span data-ttu-id="6d533-103">在许多情况下，您会根据某个类型编写业务规则，希望单独分析添加到引擎的该类型的每个实例，并按规则对每个实例进行操作。</span><span class="sxs-lookup"><span data-stu-id="6d533-103">In many scenarios, you will write a business rule against a type and expect each instance of the type that is asserted into the engine to be separately analyzed and acted upon by the rule.</span></span> <span data-ttu-id="6d533-104">然而，在某些情况下，您可能希望使用一个规则同时分析给定类型的多个实例。</span><span class="sxs-lookup"><span data-stu-id="6d533-104">In some scenarios, however, you will want to analyze multiple instances of a given type simultaneously in a rule.</span></span>  
  
 <span data-ttu-id="6d533-105">例如采用规则使用的实例的**FamilyMember**类。</span><span class="sxs-lookup"><span data-stu-id="6d533-105">Take for example a rule that uses instances of the **FamilyMember** class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 <span data-ttu-id="6d533-106">该规则标识**FamilyMember**实例，它是**父亲**和另一个实例即**子**。</span><span class="sxs-lookup"><span data-stu-id="6d533-106">The rule identifies a **FamilyMember** instance that is a **Father** and another instance that is a **Son**.</span></span> <span data-ttu-id="6d533-107">如果实例相关的姓氏，**子**实例添加到父亲实例上的子级的集合。</span><span class="sxs-lookup"><span data-stu-id="6d533-107">If the instances are related by surname, the **Son** instance is added to a collection of children on the Father instance.</span></span> <span data-ttu-id="6d533-108">如果每个**FamilyMember**实例已单独分析规则中，规则将在永远不会触发的因为在此方案中， **FamilyMember**只有一个角色-**父亲**或**子**。</span><span class="sxs-lookup"><span data-stu-id="6d533-108">If each **FamilyMember** instance were analyzed separately in the rule, the rule would never fire, because in this scenario, the **FamilyMember** only has one role—**Father** or **Son**.</span></span>  
  
 <span data-ttu-id="6d533-109">因此，必须向引擎指示应使用该规则同时分析多个实例，并需要在规则中区分每个实例标识的方法。</span><span class="sxs-lookup"><span data-stu-id="6d533-109">Therefore, you must indicate to the engine that multiple instances should be analyzed together in the rule, and you need a way to differentiate the identity of each instance in the rule.</span></span> <span data-ttu-id="6d533-110">**实例 ID**使用属性来提供此功能。</span><span class="sxs-lookup"><span data-stu-id="6d533-110">The **Instance ID** property is used to provide this functionality.</span></span> <span data-ttu-id="6d533-111">在事实浏览器中选择事实后，即可在“属性”窗口中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="6d533-111">This field is available in the Properties window when a fact is selected in Facts Explorer.</span></span> <span data-ttu-id="6d533-112">您应在将事实或成员拖入规则中之前更改此字段的值。</span><span class="sxs-lookup"><span data-stu-id="6d533-112">You should change the value of the field prior to dragging a fact or member into a rule.</span></span>  
  
 <span data-ttu-id="6d533-113">使用**实例 ID**属性，将重新生成规则。</span><span class="sxs-lookup"><span data-stu-id="6d533-113">Using the **Instance ID** property, the rule would be rebuilt.</span></span> <span data-ttu-id="6d533-114">为使用这些规则参数**子**实例**FamilyMember**、**实例 ID**字段更改默认值为 0 到 1。</span><span class="sxs-lookup"><span data-stu-id="6d533-114">For those rule arguments that use the **Son** instance of **FamilyMember**, the **Instance ID** field is changed from the default of 0 to 1.</span></span> <span data-ttu-id="6d533-115">当从 0 更改实例 ID，并且该事实或成员拖放到规则编辑器时，实例 ID 的值将显示在规则后类。</span><span class="sxs-lookup"><span data-stu-id="6d533-115">When the Instance ID is changed from 0 and the fact or member is dragged into the rule editor, the value of Instance ID will show up in the rule after the class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 <span data-ttu-id="6d533-116">现在，假定**父亲**实例和一个**子**实例断言引擎。</span><span class="sxs-lookup"><span data-stu-id="6d533-116">Now, assume that a **Father** instance and a **Son** instance are asserted into the engine.</span></span> <span data-ttu-id="6d533-117">引擎将根据这些实例的不同组合来评估规则。</span><span class="sxs-lookup"><span data-stu-id="6d533-117">The engine will evaluate the rule against the various combinations of the instances.</span></span> <span data-ttu-id="6d533-118">假设**父亲**和**子**实例具有相同的姓氏，**子**实例将添加到**父亲**实例作为适用。</span><span class="sxs-lookup"><span data-stu-id="6d533-118">Assuming that the **Father** and **Son** instance have the same surname, the **Son** instance will be added to the **Father** instance as intended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d533-119">**实例 ID**仅在给定的规则评估的上下文中使用。</span><span class="sxs-lookup"><span data-stu-id="6d533-119">The **Instance ID** is only used within the context of a given rule evaluation.</span></span> <span data-ttu-id="6d533-120">“实例 ID”不会在执行策略时附加到对象实例，并且与对象的添加顺序无关。</span><span class="sxs-lookup"><span data-stu-id="6d533-120">It is not affixed to an object instance across the policy execution and is not related to the order in which objects are asserted.</span></span> <span data-ttu-id="6d533-121">每个对象实例均将使用该类型的所有规则参数进行评估。</span><span class="sxs-lookup"><span data-stu-id="6d533-121">Each object instance will be evaluated in all rule arguments for that type.</span></span>