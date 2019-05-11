---
title: 规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d51492beb69b2789100f7328e84323cfff7ae2c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254621"
---
# <a name="rules"></a><span data-ttu-id="3d5ba-102">规则</span><span class="sxs-lookup"><span data-stu-id="3d5ba-102">Rules</span></span>
<span data-ttu-id="3d5ba-103">业务规则是控制业务流程的行为准则的声明性语句。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-103">Business rules are declarative statements that govern the conduct of business processes.</span></span> <span data-ttu-id="3d5ba-104">规则由条件和操作组成。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-104">A rule consists of a condition and actions.</span></span> <span data-ttu-id="3d5ba-105">计算条件时，如果其计算结果为 **，则返回 true**，规则引擎将启动一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-105">The condition is evaluated, and if it evaluates to **true**, the rule engine initiates one or more actions.</span></span>  
  
 <span data-ttu-id="3d5ba-106">通过使用以下格式定义业务规则框架中的规则：</span><span class="sxs-lookup"><span data-stu-id="3d5ba-106">Rules in the Business Rules Framework are defined by using the following format:</span></span>  
  
 <span data-ttu-id="3d5ba-107">如果`condition`然后`action`</span><span class="sxs-lookup"><span data-stu-id="3d5ba-107">IF`condition` THEN`action`</span></span>  
  
 <span data-ttu-id="3d5ba-108">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="3d5ba-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="3d5ba-109">IF 金额小于或等于可用资金</span><span class="sxs-lookup"><span data-stu-id="3d5ba-109">IF amount is less than or equal to available funds</span></span>  
  
 <span data-ttu-id="3d5ba-110">THEN 执行交易并打印收据</span><span class="sxs-lookup"><span data-stu-id="3d5ba-110">THEN conduct transaction and print receipt</span></span>  
  
 <span data-ttu-id="3d5ba-111">此规则确定是否将通过对数据或事务量和可用资金的窗体中事实数据应用业务逻辑，比较的两个货币值，窗体中执行事务。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-111">This rule determines whether a transaction will be conducted by applying business logic, in the form of a comparison of two monetary values, to data or facts, in the form of a transaction amount and available funds.</span></span>  
  
 <span data-ttu-id="3d5ba-112">您可以使用业务规则编辑器来创建、 修改版本，并部署业务规则。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-112">You can use the Business Rule Composer to create, modify, version, and deploy business rules.</span></span> <span data-ttu-id="3d5ba-113">或者，可以以编程方式执行上述任务。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-113">Alternatively, you can perform the preceding tasks programmatically.</span></span>  
  
## <a name="conditions"></a><span data-ttu-id="3d5ba-114">条件</span><span class="sxs-lookup"><span data-stu-id="3d5ba-114">Conditions</span></span>  
 <span data-ttu-id="3d5ba-115">条件是一个 true/false （布尔） 表达式，由应用于事实的一个或多个谓词组成。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-115">A condition is a true/false (Boolean) expression that consists of one or more predicates that are applied to facts.</span></span>  
  
 <span data-ttu-id="3d5ba-116">在本示例中，谓词**小于或等于**应用于事实**量**并**可用资金**。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-116">In our example, the predicate **less than or equal to** is applied to the facts **amount** and **available funds**.</span></span> <span data-ttu-id="3d5ba-117">此条件将计算结果始终为任一 **，则返回 true**或**false**。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-117">This condition will always evaluate to either **true** or **false**.</span></span>  
  
 <span data-ttu-id="3d5ba-118">可以使用逻辑运算符组合谓词**AND**，**或者**，并**不**到逻辑表达式，表示可能很复杂，但将计算结果始终为窗体任一 **，则返回 true**或**false**。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-118">Predicates can be combined with the logical operators **AND**, **OR**, and **NOT** to form a logical expression that is potentially quite large, but will always evaluate to either **true** or **false**.</span></span>  
  
## <a name="actions"></a><span data-ttu-id="3d5ba-119">操作</span><span class="sxs-lookup"><span data-stu-id="3d5ba-119">Actions</span></span>  
 <span data-ttu-id="3d5ba-120">操作是条件计算的功能性结果。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-120">Actions are the functional consequences of condition evaluation.</span></span> <span data-ttu-id="3d5ba-121">如果满足规则条件，则启动相应的操作。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-121">If a rule condition is met, a corresponding action or actions are initiated.</span></span>  
  
 <span data-ttu-id="3d5ba-122">在本示例中，"行为准则 transaction"和"打印收据"是，当且仅当条件 （在这种情况下，"金额小于或等于可用资金"） 为 true 时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-122">In our example, "conduct transaction" and "print receipt" are actions that are carried out when, and only when, the condition (in this case, "IF amount is less than or equal to available funds") is true.</span></span>  
  
 <span data-ttu-id="3d5ba-123">操作表示业务规则框架中调用方法或设置属性的对象，或通过执行 XML 文档或数据库表的 set 操作。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-123">Actions are represented in the Business Rules Framework by invoking methods or setting properties on objects, or by performing set operations on XML documents or database tables.</span></span>  
  
## <a name="facts"></a><span data-ttu-id="3d5ba-124">事实</span><span class="sxs-lookup"><span data-stu-id="3d5ba-124">Facts</span></span>  
 <span data-ttu-id="3d5ba-125">事实是在其规则所操作的数据。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-125">Facts are the data upon which rules operate.</span></span> <span data-ttu-id="3d5ba-126">在本例中为"金额"和"可用资金"是事实。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-126">In our example, "amount" and "available funds" are facts.</span></span> <span data-ttu-id="3d5ba-127">有关详细信息，请参阅[事实](../core/facts.md)。</span><span class="sxs-lookup"><span data-stu-id="3d5ba-127">For more information, see [Facts](../core/facts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5ba-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d5ba-128">See Also</span></span>  
 [<span data-ttu-id="3d5ba-129">如何创建策略和规则</span><span class="sxs-lookup"><span data-stu-id="3d5ba-129">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)