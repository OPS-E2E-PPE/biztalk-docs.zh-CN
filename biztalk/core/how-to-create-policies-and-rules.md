---
title: "如何创建策略和规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, business rules
- policies, rules
- policies, predicates
- business rules, creating
- creating, policies
- policies, logical operators
- policies, examples
- policies, default actions
- policies
- policies, arguments
- policies, creating
ms.assetid: 59f06a67-edde-443b-9fbb-55ec4429837a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52fb3d835b39a4059fc7a4a1644d7653257ea3dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-policies-and-rules"></a><span data-ttu-id="6efb9-102">如何创建策略和规则</span><span class="sxs-lookup"><span data-stu-id="6efb9-102">How to Create Policies and Rules</span></span>
<span data-ttu-id="6efb9-103">你可以使用是逻辑运算符的逻辑分组的条件创建规则 (**AND**， **OR**，和**不**) 应用于谓词 （内置或用户定义函数或运算符），采用自变量 （内置或用户定义的事实引用）。</span><span class="sxs-lookup"><span data-stu-id="6efb9-103">You can create rules with conditions that are logical groupings of logical operators (**AND**, **OR**, and **NOT**) applied to predicates (built-in or user-defined functions or operators) that take arguments (built-in or user-defined fact references).</span></span> <span data-ttu-id="6efb9-104">你还可以右键单击**条件**或逻辑运算符，然后从上下文菜单中选择的逻辑运算符或内置的谓词。</span><span class="sxs-lookup"><span data-stu-id="6efb9-104">You can also right-click **Conditions** or logical operators and select a logical operator or built-in predicate from the context menu.</span></span>  
  
 <span data-ttu-id="6efb9-105">你可以定义操作 （内置或用户定义函数） 时的规则条件的计算结果为要执行**true**。</span><span class="sxs-lookup"><span data-stu-id="6efb9-105">You can define actions (built-in or user-defined functions) to be executed if the rule condition evaluates to **true**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6efb9-106">如果规则中包括多个谓词，所有谓词必须都显示为一个逻辑运算符的自变量。</span><span class="sxs-lookup"><span data-stu-id="6efb9-106">If you include more than one predicate in a rule, all predicates must appear as arguments to a logical operator.</span></span> <span data-ttu-id="6efb9-107">（顶层可以为单个 .NET 成员、db 列或布尔类型的 XML 字段/属性。）</span><span class="sxs-lookup"><span data-stu-id="6efb9-107">(The top level can be a single .NET member, db column, or XML field/attribute that is of boolean type.)</span></span>  
  
### <a name="to-create-a-policy"></a><span data-ttu-id="6efb9-108">创建策略</span><span class="sxs-lookup"><span data-stu-id="6efb9-108">To create a policy</span></span>  
  
1.  <span data-ttu-id="6efb9-109">在策略资源管理器窗格中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="6efb9-109">In the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
     <span data-ttu-id="6efb9-110">一个新文件夹中，**策略 1**下, 创建**策略**。</span><span class="sxs-lookup"><span data-stu-id="6efb9-110">A new folder, **Policy1**, is created under **Policies**.</span></span> <span data-ttu-id="6efb9-111">默认情况下，为你创建新策略的版本 1。</span><span class="sxs-lookup"><span data-stu-id="6efb9-111">By default, version 1 of a new policy is created for you.</span></span>  
  
2.  <span data-ttu-id="6efb9-112">单击**策略 1**。</span><span class="sxs-lookup"><span data-stu-id="6efb9-112">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="6efb9-113">在名称属性窗格中，键入的名称。</span><span class="sxs-lookup"><span data-stu-id="6efb9-113">In the Name property pane, type a name.</span></span>  
  
### <a name="to-add-a-rule-to-a-policy-version"></a><span data-ttu-id="6efb9-114">若要将规则添加到策略版本</span><span class="sxs-lookup"><span data-stu-id="6efb9-114">To add a rule to a policy version</span></span>  
  
-   <span data-ttu-id="6efb9-115">在策略资源管理器窗格中，展开 [**你的策略**]，右键单击**（不保存） 1.0 版**，然后选择**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="6efb9-115">In the Policy Explorer pane, expand [**your policy**], right-click **Version 1.0 (not saved)**, and then select **Add New Rule**.</span></span>  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a><span data-ttu-id="6efb9-116">若要将一个逻辑运算符添加到规则条件</span><span class="sxs-lookup"><span data-stu-id="6efb9-116">To add a logical operator to a rule condition</span></span>  
  
-   <span data-ttu-id="6efb9-117">在规则定义窗口中，右键单击**条件**，然后单击其中一个**添加逻辑和**，**添加逻辑或**，或**添加逻辑不**.</span><span class="sxs-lookup"><span data-stu-id="6efb9-117">In the Rule Definition window, right-click **Conditions**, and then click one of **Add Logical AND**, **Add Logical OR**, or **Add Logical NOT**.</span></span>  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a><span data-ttu-id="6efb9-118">若要将内置谓词添加到规则条件或逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="6efb9-118">To add a built-in predicate to a rule condition or logical operator</span></span>  
  
1.  <span data-ttu-id="6efb9-119">在事实浏览器窗口中，单击**词汇**选项卡上，并依次**谓词**文件夹。</span><span class="sxs-lookup"><span data-stu-id="6efb9-119">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Predicates** folder.</span></span>  
  
2.  <span data-ttu-id="6efb9-120">展开发布的版本的谓词的词汇，并单击所需的谓词。</span><span class="sxs-lookup"><span data-stu-id="6efb9-120">Expand a published version of a predicate vocabulary, and click the predicate you want.</span></span>  
  
3.  <span data-ttu-id="6efb9-121">将该谓词，拖到逻辑运算符，或**条件**如果你的规则将包含只有一个谓词。</span><span class="sxs-lookup"><span data-stu-id="6efb9-121">Drag the predicate onto the logical operator, or onto **Conditions** if your rule will contain only one predicate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6efb9-122">你还可以添加谓词直接从数据源，前提是数据元素充当一个谓词 (计算结果为**true**或**false**)。</span><span class="sxs-lookup"><span data-stu-id="6efb9-122">You can also add a predicate directly from a data source, provided that the data element acts as a predicate (evaluates to **true** or **false**).</span></span>  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a><span data-ttu-id="6efb9-123">将内置操作添加到规则</span><span class="sxs-lookup"><span data-stu-id="6efb9-123">To add a built-in action to a rule</span></span>  
  
1.  <span data-ttu-id="6efb9-124">在事实浏览器窗口中，单击**词汇**选项卡上，并依次**函数**文件夹。</span><span class="sxs-lookup"><span data-stu-id="6efb9-124">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Functions** folder.</span></span>  
  
2.  <span data-ttu-id="6efb9-125">展开的函数词汇，发布的版本并单击所需的函数。</span><span class="sxs-lookup"><span data-stu-id="6efb9-125">Expand a published version of the function vocabulary, and click the function you want.</span></span>  
  
3.  <span data-ttu-id="6efb9-126">将函数拖放到**操作**。</span><span class="sxs-lookup"><span data-stu-id="6efb9-126">Drag the function onto **Actions**.</span></span> <span data-ttu-id="6efb9-127">你还可以右键单击**操作**，然后从上下文菜单中选择内置操作。</span><span class="sxs-lookup"><span data-stu-id="6efb9-127">You can also right-click **Actions**, and select a built-in action from the context menu.</span></span>  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a><span data-ttu-id="6efb9-128">若要将参数添加到条件或操作</span><span class="sxs-lookup"><span data-stu-id="6efb9-128">To add an argument to a condition or action</span></span>  
  
1.  <span data-ttu-id="6efb9-129">在事实浏览器窗口中，单击**词汇**选项卡上，并依次词汇文件夹。</span><span class="sxs-lookup"><span data-stu-id="6efb9-129">In the Facts Explorer window, click the **Vocabularies** tab, and then click a vocabulary folder.</span></span>  
  
2.  <span data-ttu-id="6efb9-130">展开词汇的已发布版本，并单击所需的术语。</span><span class="sxs-lookup"><span data-stu-id="6efb9-130">Expand a published version of the vocabulary, and click the term you want.</span></span> <span data-ttu-id="6efb9-131">该术语必须属于谓词或功能所要求的类型。</span><span class="sxs-lookup"><span data-stu-id="6efb9-131">The term must be of a type expected by the predicate or function.</span></span>  
  
3.  <span data-ttu-id="6efb9-132">将该术语拖至条件中的谓词参数上，或拖至操作中的函数参数上。</span><span class="sxs-lookup"><span data-stu-id="6efb9-132">Drag the term onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6efb9-133">还可以直接从数据源中添加参数，或者，如果要添加 XML 参数，也可以在选择字段时在属性中指定字段类型；当然，如果数据元素属于谓词或操作所要求的类型，则该元素必须与数据本身兼容。</span><span class="sxs-lookup"><span data-stu-id="6efb9-133">You can also add an argument directly from a data source or in the case of XML you can specify the field type in the properties when selecting a field; this must of course be compatible with the data itself , provided that the data element is of a type expected by the predicate or action.</span></span> <span data-ttu-id="6efb9-134">若要直接从数据源添加参数，单击事实浏览器窗口中相应的选项卡，导航到所需的项并将其拖到谓词自变量或函数参数。</span><span class="sxs-lookup"><span data-stu-id="6efb9-134">To add an argument directly from a data source, click the appropriate tab in the Facts Explorer window, navigate to the item you want, and drag it onto a predicate argument or function argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6efb9-135">通过单击参数并输入所需的常数值，可以直接向参数添加常数值。</span><span class="sxs-lookup"><span data-stu-id="6efb9-135">You can add a constant value to an argument directly by clicking the argument and entering the constant value you want.</span></span>