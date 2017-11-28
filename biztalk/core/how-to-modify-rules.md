---
title: "如何修改规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, activating
- deactivating business rules
- business rules, priorities
- activating business rules
- business rules, deactivating
- modifying, business rules
- business rules, modifying
ms.assetid: 661b2637-b5d6-4bde-9c42-24cd9e9d241c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fce3fb78ce67b6c82f2301dfcb4cb2175aee0dde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-rules"></a><span data-ttu-id="73732-102">如何修改规则</span><span class="sxs-lookup"><span data-stu-id="73732-102">How to Modify Rules</span></span>
<span data-ttu-id="73732-103">若要更改规则的功能是业务规则范例的一个重要部分。</span><span class="sxs-lookup"><span data-stu-id="73732-103">The ability to change rules is an important part of the business rules paradigm.</span></span> <span data-ttu-id="73732-104">你可以修改中两种方式的策略规则： 通过创建新版本的策略，或通过直接修改取消发布的版本的策略。</span><span class="sxs-lookup"><span data-stu-id="73732-104">You can modify rules within a policy in two ways: either by creating a new version of the policy, or by directly modifying an unpublished version of the policy.</span></span>  
  
 <span data-ttu-id="73732-105">你可以单独修改规则、 添加新规则，或删除现有规则。</span><span class="sxs-lookup"><span data-stu-id="73732-105">You can modify rules individually, add new rules, or delete existing rules.</span></span> <span data-ttu-id="73732-106">可以删除从规则条件的谓词和逻辑运算符，删除操作，在显示中，向上和向下移动操作或移动谓词和在一个条件中的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="73732-106">You can delete predicates and logical operators from a rule condition, delete actions, move actions up and down in the display, or move predicates and logical operators within a condition.</span></span> <span data-ttu-id="73732-107">请记住，但是，谓词和逻辑运算符的显示顺序不确定的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="73732-107">Keep in mind, however, the order in which the predicates and logical operators are displayed does not determine the order of evaluation.</span></span>  
  
 <span data-ttu-id="73732-108">你可以设置为非活动状态，以便执行策略，或可以重新激活已停用的规则时，不执行规则的规则。</span><span class="sxs-lookup"><span data-stu-id="73732-108">You can set a rule to be inactive, so that the rule is not executed when the policy is executed, or you can reactivate a rule that has been deactivated.</span></span>  
  
 <span data-ttu-id="73732-109">可以对规则设置优先级，以便之前或之后的任何规则不同的优先级的操作，将执行其操作。</span><span class="sxs-lookup"><span data-stu-id="73732-109">You can set the priority on a rule so that its actions will be executed before or after the actions of any rule of different priority.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="73732-110">如果你需要停止 SQL Server 计算机，请务必保存任何未保存的词汇版本或词汇定义，并关闭业务规则编辑器，以便任何更改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="73732-110">If you need to stop your SQL Server computer, be sure to save any unsaved vocabulary versions or vocabulary definitions, and close the Business Rule Composer so that no changes are lost.</span></span>  
  
 <span data-ttu-id="73732-111">本主题包含以下任务的过程：</span><span class="sxs-lookup"><span data-stu-id="73732-111">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="73732-112">若要更改中的条件或操作的自变量</span><span class="sxs-lookup"><span data-stu-id="73732-112">To change an argument in a condition or action</span></span>  
  
-   <span data-ttu-id="73732-113">将在一个条件中的谓词</span><span class="sxs-lookup"><span data-stu-id="73732-113">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="73732-114">将在一个条件中的一个逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="73732-114">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="73732-115">若要更改规则的操作顺序</span><span class="sxs-lookup"><span data-stu-id="73732-115">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="73732-116">若要删除的谓词，逻辑运算符或操作</span><span class="sxs-lookup"><span data-stu-id="73732-116">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="73732-117">若要激活或停用一条规则</span><span class="sxs-lookup"><span data-stu-id="73732-117">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="73732-118">规则上设置优先级</span><span class="sxs-lookup"><span data-stu-id="73732-118">To set a priority on a rule</span></span>  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a><span data-ttu-id="73732-119">若要更改中的条件或操作的自变量</span><span class="sxs-lookup"><span data-stu-id="73732-119">To change an argument in a condition or action</span></span>  
  
1.  <span data-ttu-id="73732-120">在事实和定义窗口中，单击相应的选项卡，并导航到想要作为自变量使用的术语。</span><span class="sxs-lookup"><span data-stu-id="73732-120">In the Facts and Definitions window, click the appropriate tab, and navigate to the term you want to use as an argument.</span></span> <span data-ttu-id="73732-121">该术语必须属于谓词或功能所要求的类型。</span><span class="sxs-lookup"><span data-stu-id="73732-121">The term must be of a type expected by the predicate or function.</span></span>  
  
2.  <span data-ttu-id="73732-122">单击术语，并将其拖到条件中的谓词自变量或操作中的函数自变量。</span><span class="sxs-lookup"><span data-stu-id="73732-122">Click the term and drag it onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
### <a name="to-move-a-predicate-within-a-condition"></a><span data-ttu-id="73732-123">将在一个条件中的谓词</span><span class="sxs-lookup"><span data-stu-id="73732-123">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="73732-124">单击该谓词，并将其拖到另一个逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="73732-124">Click the predicate, and drag it to another logical operator.</span></span>  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a><span data-ttu-id="73732-125">将在一个条件中的一个逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="73732-125">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="73732-126">单击逻辑运算符，并将其拖到另一个逻辑运算符或**条件**。</span><span class="sxs-lookup"><span data-stu-id="73732-126">Click the logical operator, and drag it onto another logical operator or onto **Conditions**.</span></span>  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a><span data-ttu-id="73732-127">若要更改规则的操作顺序</span><span class="sxs-lookup"><span data-stu-id="73732-127">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="73732-128">单击操作，然后单击**移操作**或**向下移动操作**。</span><span class="sxs-lookup"><span data-stu-id="73732-128">Click the action and then click **Move action up** or **Move action down**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73732-129">除了引擎控制功能以及执行其他操作后指定的顺序，将执行一个规则的操作。</span><span class="sxs-lookup"><span data-stu-id="73732-129">The actions of a rule will be executed in the order specified with the exception of engine control functions which are executed after the other actions.</span></span>  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a><span data-ttu-id="73732-130">若要删除的谓词，逻辑运算符或操作</span><span class="sxs-lookup"><span data-stu-id="73732-130">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="73732-131">单击谓词，逻辑运算符或操作，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="73732-131">Click the predicate, logical operator, or action, and then click **Delete**.</span></span>  
  
### <a name="to-activate-or-deactivate-a-rule"></a><span data-ttu-id="73732-132">若要激活或停用一条规则</span><span class="sxs-lookup"><span data-stu-id="73732-132">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="73732-133">单击该规则，然后在属性窗口中，设置**Active**为**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="73732-133">Click the rule, and then in the Properties window, set **Active** to either **True** or **False**.</span></span>  
  
### <a name="to-set-a-priority-on-a-rule"></a><span data-ttu-id="73732-134">规则上设置优先级</span><span class="sxs-lookup"><span data-stu-id="73732-134">To set a priority on a rule</span></span>  
  
-   <span data-ttu-id="73732-135">单击该规则，然后在属性窗口中，设置**优先级**为整数值。</span><span class="sxs-lookup"><span data-stu-id="73732-135">Click the rule, and then in the Properties window, set **Priority** to an integer value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73732-136">优先级是相对的并且所有给定优先级的规则的操作将在任何具有较低的值的规则的操作前优先级的顺序执行。</span><span class="sxs-lookup"><span data-stu-id="73732-136">Priorities are relative, and all of the actions of a rule of a given priority will be executed in order before any of the actions of a rule with a lower value for priority.</span></span> <span data-ttu-id="73732-137">优先级值默认为零，但它可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="73732-137">The priority value defaults to zero, but it can be positive or negative.</span></span>