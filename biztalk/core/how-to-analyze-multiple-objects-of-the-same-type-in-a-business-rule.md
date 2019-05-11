---
title: 如何分析的业务规则中的相同类型的多个对象 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1060de077a8b526db6c226786b23781da1f7421
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342941"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a><span data-ttu-id="1e2e8-102">如何分析的业务规则中的相同类型的多个对象</span><span class="sxs-lookup"><span data-stu-id="1e2e8-102">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>
<span data-ttu-id="1e2e8-103">在许多情况下，将编写针对一种类型的业务规则，并希望每个实例添加到引擎单独分析和处理规则的类型。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-103">In many scenarios, you will write a business rule against a type and expect each instance of the type that is asserted into the engine to be separately analyzed and acted upon by the rule.</span></span> <span data-ttu-id="1e2e8-104">但是，在某些情况下，会要分析的同时在规则中的给定类型的多个实例。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-104">In some scenarios, however, you will want to analyze multiple instances of a given type simultaneously in a rule.</span></span>  
  
 <span data-ttu-id="1e2e8-105">如需要使用的实例的规则**FamilyMember**类。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-105">Take for example a rule that uses instances of the **FamilyMember** class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 <span data-ttu-id="1e2e8-106">该规则标识**FamilyMember**实例的数据类型**父亲**和的另一个实例**儿子**。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-106">The rule identifies a **FamilyMember** instance that is a **Father** and another instance that is a **Son**.</span></span> <span data-ttu-id="1e2e8-107">如果按姓氏，相关实例**Son**实例添加到 Father 实例的子对象集合。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-107">If the instances are related by surname, the **Son** instance is added to a collection of children on the Father instance.</span></span> <span data-ttu-id="1e2e8-108">如果每个**FamilyMember**规则单独分析实例中，该规则永远不会触发，因为在此方案中， **FamilyMember**只有一个角色 —**父亲**或**Son**。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-108">If each **FamilyMember** instance were analyzed separately in the rule, the rule would never fire, because in this scenario, the **FamilyMember** only has one role—**Father** or **Son**.</span></span>  
  
 <span data-ttu-id="1e2e8-109">因此，在规则中，应同时分析多个实例，并需要一种方法，以区分规则中的每个实例的标识，您必须向引擎指示。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-109">Therefore, you must indicate to the engine that multiple instances should be analyzed together in the rule, and you need a way to differentiate the identity of each instance in the rule.</span></span> <span data-ttu-id="1e2e8-110">**实例 ID**属性用于提供此功能。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-110">The **Instance ID** property is used to provide this functionality.</span></span> <span data-ttu-id="1e2e8-111">此字段是可在属性窗口中时在事实浏览器中选择一个事实。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-111">This field is available in the Properties window when a fact is selected in Facts Explorer.</span></span> <span data-ttu-id="1e2e8-112">应更改之前将事实或成员拖到规则中字段的值。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-112">You should change the value of the field prior to dragging a fact or member into a rule.</span></span>  
  
 <span data-ttu-id="1e2e8-113">使用**实例 ID**属性，可重新生成规则。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-113">Using the **Instance ID** property, the rule would be rebuilt.</span></span> <span data-ttu-id="1e2e8-114">使用这些规则参数**Son**的实例**FamilyMember**，则**实例 ID**字段更改从默认值为 0 到 1。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-114">For those rule arguments that use the **Son** instance of **FamilyMember**, the **Instance ID** field is changed from the default of 0 to 1.</span></span> <span data-ttu-id="1e2e8-115">当从 0 更改实例 ID 和该事实或成员拖入规则编辑器时，实例 ID 的值将显示在规则中类进行仿造。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-115">When the Instance ID is changed from 0 and the fact or member is dragged into the rule editor, the value of Instance ID will show up in the rule after the class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 <span data-ttu-id="1e2e8-116">现在，假设**父亲**实例和一个**儿子**实例添加到引擎。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-116">Now, assume that a **Father** instance and a **Son** instance are asserted into the engine.</span></span> <span data-ttu-id="1e2e8-117">该引擎将评估规则所依据的实例的各种组合。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-117">The engine will evaluate the rule against the various combinations of the instances.</span></span> <span data-ttu-id="1e2e8-118">假设**父亲**并**儿子**实例具有相同姓氏**儿子**实例将添加到**父亲**实例作为适用。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-118">Assuming that the **Father** and **Son** instance have the same surname, the **Son** instance will be added to the **Father** instance as intended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e2e8-119">**实例 ID**只能在给定的规则评估的上下文中使用。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-119">The **Instance ID** is only used within the context of a given rule evaluation.</span></span> <span data-ttu-id="1e2e8-120">它在执行策略未附加到对象实例，并与对象的添加的顺序无关。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-120">It is not affixed to an object instance across the policy execution and is not related to the order in which objects are asserted.</span></span> <span data-ttu-id="1e2e8-121">将该类型的所有规则参数中计算每个对象实例。</span><span class="sxs-lookup"><span data-stu-id="1e2e8-121">Each object instance will be evaluated in all rule arguments for that type.</span></span>