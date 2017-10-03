---
title: "规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35f398cf98181d17833be79fbe9d282e8515e052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="rules"></a><span data-ttu-id="c8667-102">规则</span><span class="sxs-lookup"><span data-stu-id="c8667-102">Rules</span></span>
<span data-ttu-id="c8667-103">业务规则是规定的业务流程开展的声明性语句。</span><span class="sxs-lookup"><span data-stu-id="c8667-103">Business rules are declarative statements that govern the conduct of business processes.</span></span> <span data-ttu-id="c8667-104">规则由条件和操作组成。</span><span class="sxs-lookup"><span data-stu-id="c8667-104">A rule consists of a condition and actions.</span></span> <span data-ttu-id="c8667-105">对条件进行评估，如果其计算结果为**true**，规则引擎启动一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="c8667-105">The condition is evaluated, and if it evaluates to **true**, the rule engine initiates one or more actions.</span></span>  
  
 <span data-ttu-id="c8667-106">业务规则框架中的规则定义通过使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="c8667-106">Rules in the Business Rules Framework are defined by using the following format:</span></span>  
  
 <span data-ttu-id="c8667-107">如果`condition`然后`action`</span><span class="sxs-lookup"><span data-stu-id="c8667-107">IF`condition` THEN`action`</span></span>  
  
 <span data-ttu-id="c8667-108">请参考如下示例：</span><span class="sxs-lookup"><span data-stu-id="c8667-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="c8667-109">如果量小于或等于可用基金</span><span class="sxs-lookup"><span data-stu-id="c8667-109">IF amount is less than or equal to available funds</span></span>  
  
 <span data-ttu-id="c8667-110">THEN 执行交易和打印收据</span><span class="sxs-lookup"><span data-stu-id="c8667-110">THEN conduct transaction and print receipt</span></span>  
  
 <span data-ttu-id="c8667-111">此规则确定是否将通过将业务逻辑，两个的货币值的比较的形式应用于数据或在事务量和可用基金的形式事实执行事务。</span><span class="sxs-lookup"><span data-stu-id="c8667-111">This rule determines whether a transaction will be conducted by applying business logic, in the form of a comparison of two monetary values, to data or facts, in the form of a transaction amount and available funds.</span></span>  
  
 <span data-ttu-id="c8667-112">你可以使用业务规则编辑器来创建、 修改、 版本，然后部署业务规则。</span><span class="sxs-lookup"><span data-stu-id="c8667-112">You can use the Business Rule Composer to create, modify, version, and deploy business rules.</span></span> <span data-ttu-id="c8667-113">或者，你可以以编程方式执行上述任务。</span><span class="sxs-lookup"><span data-stu-id="c8667-113">Alternatively, you can perform the preceding tasks programmatically.</span></span>  
  
## <a name="conditions"></a><span data-ttu-id="c8667-114">条件</span><span class="sxs-lookup"><span data-stu-id="c8667-114">Conditions</span></span>  
 <span data-ttu-id="c8667-115">条件是 true/false （布尔） 表达式包含的适用于在事实的一个或多个谓词。</span><span class="sxs-lookup"><span data-stu-id="c8667-115">A condition is a true/false (Boolean) expression that consists of one or more predicates that are applied to facts.</span></span>  
  
 <span data-ttu-id="c8667-116">在本示例中，谓词**小于或等于**应用于这些事实**量**和**可用基金**。</span><span class="sxs-lookup"><span data-stu-id="c8667-116">In our example, the predicate **less than or equal to** is applied to the facts **amount** and **available funds**.</span></span> <span data-ttu-id="c8667-117">这种情况将始终评估为**true**或**false**。</span><span class="sxs-lookup"><span data-stu-id="c8667-117">This condition will always evaluate to either **true** or **false**.</span></span>  
  
 <span data-ttu-id="c8667-118">可以使用逻辑运算符组合谓词**AND**，**或者**，和**不**到逻辑表达式，表示可能很大，但将计算结果始终为窗体任一**true**或**false**。</span><span class="sxs-lookup"><span data-stu-id="c8667-118">Predicates can be combined with the logical operators **AND**, **OR**, and **NOT** to form a logical expression that is potentially quite large, but will always evaluate to either **true** or **false**.</span></span>  
  
## <a name="actions"></a><span data-ttu-id="c8667-119">操作</span><span class="sxs-lookup"><span data-stu-id="c8667-119">Actions</span></span>  
 <span data-ttu-id="c8667-120">操作是条件计算的功能后果。</span><span class="sxs-lookup"><span data-stu-id="c8667-120">Actions are the functional consequences of condition evaluation.</span></span> <span data-ttu-id="c8667-121">如果满足规则条件，则启动相应的操作。</span><span class="sxs-lookup"><span data-stu-id="c8667-121">If a rule condition is met, a corresponding action or actions are initiated.</span></span>  
  
 <span data-ttu-id="c8667-122">在本示例中，"准则事务"和"打印回执"都执行时，并且仅当条件 （在这种情况下，"如果数量小于或等于可用基金"） 为 true 的操作。</span><span class="sxs-lookup"><span data-stu-id="c8667-122">In our example, "conduct transaction" and "print receipt" are actions that are carried out when, and only when, the condition (in this case, "IF amount is less than or equal to available funds") is true.</span></span>  
  
 <span data-ttu-id="c8667-123">通过调用方法或在对象上设置属性或执行在 XML 文档或数据库表上的设置操作的业务规则 Framework 中表示操作。</span><span class="sxs-lookup"><span data-stu-id="c8667-123">Actions are represented in the Business Rules Framework by invoking methods or setting properties on objects, or by performing set operations on XML documents or database tables.</span></span>  
  
## <a name="facts"></a><span data-ttu-id="c8667-124">事实</span><span class="sxs-lookup"><span data-stu-id="c8667-124">Facts</span></span>  
 <span data-ttu-id="c8667-125">事实数据是在其规则进行操作的数据。</span><span class="sxs-lookup"><span data-stu-id="c8667-125">Facts are the data upon which rules operate.</span></span> <span data-ttu-id="c8667-126">在本示例中，"amount"和"可用基金"是事实。</span><span class="sxs-lookup"><span data-stu-id="c8667-126">In our example, "amount" and "available funds" are facts.</span></span> <span data-ttu-id="c8667-127">有关详细信息，请参阅[事实](../core/facts.md)。</span><span class="sxs-lookup"><span data-stu-id="c8667-127">For more information, see [Facts](../core/facts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8667-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8667-128">See Also</span></span>  
 [<span data-ttu-id="c8667-129">如何创建策略和规则</span><span class="sxs-lookup"><span data-stu-id="c8667-129">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)