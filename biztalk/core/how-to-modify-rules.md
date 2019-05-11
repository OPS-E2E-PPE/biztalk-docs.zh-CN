---
title: 如何修改规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2badd7947e439fe3ba80d86607a1a271d52b5eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336009"
---
# <a name="how-to-modify-rules"></a><span data-ttu-id="8cc50-102">如何修改规则</span><span class="sxs-lookup"><span data-stu-id="8cc50-102">How to Modify Rules</span></span>
<span data-ttu-id="8cc50-103">若要更改规则的功能是业务规则范例的一个重要部分。</span><span class="sxs-lookup"><span data-stu-id="8cc50-103">The ability to change rules is an important part of the business rules paradigm.</span></span> <span data-ttu-id="8cc50-104">您可以修改策略中通过两种方式的规则： 通过创建新版本的策略，或通过直接修改策略的未发布的版本。</span><span class="sxs-lookup"><span data-stu-id="8cc50-104">You can modify rules within a policy in two ways: either by creating a new version of the policy, or by directly modifying an unpublished version of the policy.</span></span>  
  
 <span data-ttu-id="8cc50-105">可以单独修改规则、 添加新规则，或删除现有规则。</span><span class="sxs-lookup"><span data-stu-id="8cc50-105">You can modify rules individually, add new rules, or delete existing rules.</span></span> <span data-ttu-id="8cc50-106">可以从规则条件中删除谓词和逻辑运算符、 删除操作，在显示中，向上和向下移动操作或移动谓词和某一条件内的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="8cc50-106">You can delete predicates and logical operators from a rule condition, delete actions, move actions up and down in the display, or move predicates and logical operators within a condition.</span></span> <span data-ttu-id="8cc50-107">但是请记住，、 谓词和逻辑运算符的显示的顺序不确定的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="8cc50-107">Keep in mind, however, the order in which the predicates and logical operators are displayed does not determine the order of evaluation.</span></span>  
  
 <span data-ttu-id="8cc50-108">可以设置为非活动状态，以便执行策略，或可以重新激活已停用的规则时不执行规则的规则。</span><span class="sxs-lookup"><span data-stu-id="8cc50-108">You can set a rule to be inactive, so that the rule is not executed when the policy is executed, or you can reactivate a rule that has been deactivated.</span></span>  
  
 <span data-ttu-id="8cc50-109">可以对规则设置优先级，从而使之前或之后的任何其他优先级的规则的操作，将执行其操作。</span><span class="sxs-lookup"><span data-stu-id="8cc50-109">You can set the priority on a rule so that its actions will be executed before or after the actions of any rule of different priority.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8cc50-110">如果你需要停止 SQL Server 计算机，请务必保存任何未保存的词汇版本或词汇定义，并关闭业务规则编辑器，以便不不丢失任何更改。</span><span class="sxs-lookup"><span data-stu-id="8cc50-110">If you need to stop your SQL Server computer, be sure to save any unsaved vocabulary versions or vocabulary definitions, and close the Business Rule Composer so that no changes are lost.</span></span>  
  
 <span data-ttu-id="8cc50-111">本主题包含以下任务的过程：</span><span class="sxs-lookup"><span data-stu-id="8cc50-111">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="8cc50-112">若要更改条件或操作中的自变量</span><span class="sxs-lookup"><span data-stu-id="8cc50-112">To change an argument in a condition or action</span></span>  
  
-   <span data-ttu-id="8cc50-113">若要移动某一条件内的谓词</span><span class="sxs-lookup"><span data-stu-id="8cc50-113">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="8cc50-114">若要移动某一条件内的逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="8cc50-114">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="8cc50-115">若要更改规则中的操作顺序</span><span class="sxs-lookup"><span data-stu-id="8cc50-115">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="8cc50-116">若要删除谓词、 逻辑运算符或操作</span><span class="sxs-lookup"><span data-stu-id="8cc50-116">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="8cc50-117">若要激活或停用某个规则</span><span class="sxs-lookup"><span data-stu-id="8cc50-117">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="8cc50-118">若要设置规则优先级</span><span class="sxs-lookup"><span data-stu-id="8cc50-118">To set a priority on a rule</span></span>  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a><span data-ttu-id="8cc50-119">若要更改条件或操作中的自变量</span><span class="sxs-lookup"><span data-stu-id="8cc50-119">To change an argument in a condition or action</span></span>  
  
1.  <span data-ttu-id="8cc50-120">在事实和定义窗口中，单击相应的选项卡，并导航到想要作为参数使用的术语。</span><span class="sxs-lookup"><span data-stu-id="8cc50-120">In the Facts and Definitions window, click the appropriate tab, and navigate to the term you want to use as an argument.</span></span> <span data-ttu-id="8cc50-121">术语必须是谓词或函数所要求的类型。</span><span class="sxs-lookup"><span data-stu-id="8cc50-121">The term must be of a type expected by the predicate or function.</span></span>  
  
2.  <span data-ttu-id="8cc50-122">单击术语并将其拖至条件中的谓词参数或操作中的函数参数。</span><span class="sxs-lookup"><span data-stu-id="8cc50-122">Click the term and drag it onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
### <a name="to-move-a-predicate-within-a-condition"></a><span data-ttu-id="8cc50-123">若要移动某一条件内的谓词</span><span class="sxs-lookup"><span data-stu-id="8cc50-123">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="8cc50-124">单击该谓词中，并将其拖到另一个逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="8cc50-124">Click the predicate, and drag it to another logical operator.</span></span>  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a><span data-ttu-id="8cc50-125">若要移动某一条件内的逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="8cc50-125">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="8cc50-126">单击该逻辑运算符，并将其拖到另一个逻辑运算符或上**条件**。</span><span class="sxs-lookup"><span data-stu-id="8cc50-126">Click the logical operator, and drag it onto another logical operator or onto **Conditions**.</span></span>  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a><span data-ttu-id="8cc50-127">若要更改规则中的操作顺序</span><span class="sxs-lookup"><span data-stu-id="8cc50-127">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="8cc50-128">单击操作，然后单击**操作上移**或**向下移动操作**。</span><span class="sxs-lookup"><span data-stu-id="8cc50-128">Click the action and then click **Move action up** or **Move action down**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cc50-129">将指定除了引擎控制功能的其他操作之后执行的顺序执行规则的操作。</span><span class="sxs-lookup"><span data-stu-id="8cc50-129">The actions of a rule will be executed in the order specified with the exception of engine control functions which are executed after the other actions.</span></span>  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a><span data-ttu-id="8cc50-130">若要删除谓词、 逻辑运算符或操作</span><span class="sxs-lookup"><span data-stu-id="8cc50-130">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="8cc50-131">单击谓词、 逻辑运算符或操作，然后依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="8cc50-131">Click the predicate, logical operator, or action, and then click **Delete**.</span></span>  
  
### <a name="to-activate-or-deactivate-a-rule"></a><span data-ttu-id="8cc50-132">若要激活或停用某个规则</span><span class="sxs-lookup"><span data-stu-id="8cc50-132">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="8cc50-133">单击该规则，然后在属性窗口中设置**Active**至任一**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="8cc50-133">Click the rule, and then in the Properties window, set **Active** to either **True** or **False**.</span></span>  
  
### <a name="to-set-a-priority-on-a-rule"></a><span data-ttu-id="8cc50-134">若要设置规则优先级</span><span class="sxs-lookup"><span data-stu-id="8cc50-134">To set a priority on a rule</span></span>  
  
-   <span data-ttu-id="8cc50-135">单击该规则，然后在属性窗口中设置**优先级**为整数值。</span><span class="sxs-lookup"><span data-stu-id="8cc50-135">Click the rule, and then in the Properties window, set **Priority** to an integer value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cc50-136">优先级是相对的并将之前的任何具有较低的值的规则操作的优先级的顺序执行的所有给定优先级的规则的操作。</span><span class="sxs-lookup"><span data-stu-id="8cc50-136">Priorities are relative, and all of the actions of a rule of a given priority will be executed in order before any of the actions of a rule with a lower value for priority.</span></span> <span data-ttu-id="8cc50-137">默认优先级值为零，但它可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="8cc50-137">The priority value defaults to zero, but it can be positive or negative.</span></span>