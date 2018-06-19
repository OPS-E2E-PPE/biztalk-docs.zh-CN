---
title: 采用表达式的形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, shapes
- Decide shape [Orchestration Designer], expressions
- Message Assignment shape [Orchestration Designer], expressions
- Filter Expression property
- Listen shape [Orchestration Designer], expressions
- Delay shape [Orchestration Designer], expressions
- shapes, expressions
- Receive shape [Orchestration Designer], expressions
- Loop shape [Orchestration Designer], expressions
- Rule shape [Orchestration Designer]
ms.assetid: 0d27f711-ff7c-422b-b231-aa3c9a42ed0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e78ada2c69205a0201c4bae9f3c7fa5b0656fa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270781"
---
# <a name="shapes-that-take-expressions"></a><span data-ttu-id="8a5a1-102">采用表达式的形状</span><span class="sxs-lookup"><span data-stu-id="8a5a1-102">Shapes that Take Expressions</span></span>
<span data-ttu-id="8a5a1-103">多个形状中业务流程设计器中，包括**确定**和**循环**，使用控制分支的窗体规则的布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-103">Several shapes in Orchestration Designer, including **Decide** and **Loop**, use Boolean expressions to form rules that control branching.</span></span> <span data-ttu-id="8a5a1-104">其他形状将表达式用于其他用途。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-104">Other shapes use expressions for other purposes.</span></span> <span data-ttu-id="8a5a1-105">通过使用 BizTalk 表达式编辑器，您可以为这些形状创建或编辑表达式。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-105">You can create or edit an expression for these shapes by using BizTalk Expression Editor.</span></span>  
  
 <span data-ttu-id="8a5a1-106">下表概括列出了可在业务流程设计器中使用表达式的形状，并列出了对这些表达式有效的数据类型：</span><span class="sxs-lookup"><span data-stu-id="8a5a1-106">The following table summarizes the shapes that use expressions in Orchestration Designer and lists the data types that are valid for those expressions.</span></span>  
  
|<span data-ttu-id="8a5a1-107">形状</span><span class="sxs-lookup"><span data-stu-id="8a5a1-107">Shape</span></span>|<span data-ttu-id="8a5a1-108">表达式用法说明</span><span class="sxs-lookup"><span data-stu-id="8a5a1-108">Description of expression use</span></span>|<span data-ttu-id="8a5a1-109">有效的表达式数据类型</span><span class="sxs-lookup"><span data-stu-id="8a5a1-109">Valid expression data types</span></span>|  
|-----------|-----------------------------------|---------------------------------|  
|<span data-ttu-id="8a5a1-110">**决定**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-110">**Decide**</span></span>|<span data-ttu-id="8a5a1-111">**决定**形状包含**规则**形状，使用布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-111">**Decide** shapes contain **Rule** shapes, which use Boolean expressions.</span></span>|<span data-ttu-id="8a5a1-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="8a5a1-112">Boolean</span></span>|  
|<span data-ttu-id="8a5a1-113">**接收**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-113">**Receive**</span></span>|<span data-ttu-id="8a5a1-114">**接收**激活属性设置为 True 的使用的形状**筛选器表达式**属性筛选传入消息。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-114">**Receive** shapes that have the Activate property set to True use the **Filter Expression** property to filter incoming messages.</span></span> <span data-ttu-id="8a5a1-115">此属性中的表达式的计算结果必须是布尔类型，该计算结果值将确定是否接受传入消息。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-115">The expression in this property must evaluate to a Boolean, whose value determines whether or not to accept an incoming message.</span></span><br /><br /> <span data-ttu-id="8a5a1-116">**筛选器表达式**对话框用于创建筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-116">The **Filter Expression** dialog box is used to create filter expressions.</span></span>|<span data-ttu-id="8a5a1-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="8a5a1-117">Boolean</span></span>|  
|<span data-ttu-id="8a5a1-118">**循环**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-118">**Loop**</span></span>|<span data-ttu-id="8a5a1-119">A**循环**形状需要**规则**形状，这反过来必须包含布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-119">A **Loop** shape requires a **Rule** shape, which in turn must contain a Boolean expression.</span></span>|<span data-ttu-id="8a5a1-120">Boolean</span><span class="sxs-lookup"><span data-stu-id="8a5a1-120">Boolean</span></span>|  
|<span data-ttu-id="8a5a1-121">**规则**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-121">**Rule**</span></span>|<span data-ttu-id="8a5a1-122">**规则**形状 （作为"分支"形状显示过程区域上） 是简单形状，包含布尔表达式，用于在其他 （复杂） 形状内控制分支。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-122">**Rule** shapes (displayed on the Process Area as "branch" shapes) are simple shapes that contain Boolean expressions and are used within other (complex) shapes to govern branching.</span></span>|<span data-ttu-id="8a5a1-123">Boolean</span><span class="sxs-lookup"><span data-stu-id="8a5a1-123">Boolean</span></span>|  
|<span data-ttu-id="8a5a1-124">**侦听**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-124">**Listen**</span></span>|<span data-ttu-id="8a5a1-125">每个分支**侦听**形状，至少包含，或者**接收**形状，只对筛选器表达式中使用布尔表达式 (请参阅的条目**接收**)或**延迟**调整，它使用**System.DateTime**对象或**System.TimeSpan**对象。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-125">Each branch of a **Listen** shape contains, at a minimum, either a **Receive** shape, which uses a Boolean expression only for filter expressions (see the entry for **Receive**), or a **Delay** shape, which uses a **System.DateTime** object or **System.TimeSpan** object.</span></span>|<span data-ttu-id="8a5a1-126">Boolean、System.DateTime、System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8a5a1-126">Boolean, System.DateTime, System.TimeSpan</span></span>|  
|<span data-ttu-id="8a5a1-127">**延迟**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-127">**Delay**</span></span>|<span data-ttu-id="8a5a1-128">中所用的表达式**延迟**形状的计算结果必须为**System.DateTime**对象，表示截止时间，或**System.TimeSpan**对象，表示持续时间。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-128">The expression used in a **Delay** shape must evaluate to a **System.DateTime** object, to express a deadline, or a **System.TimeSpan** object, to express duration.</span></span>|<span data-ttu-id="8a5a1-129">System.DateTime、System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8a5a1-129">System.DateTime, System.TimeSpan</span></span>|  
|<span data-ttu-id="8a5a1-130">**消息赋值**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-130">**Message Assignment**</span></span>|<span data-ttu-id="8a5a1-131">中的表达式**消息分配**形状将值分配给一条消息。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-131">The expression in a **Message Assignment** shape assigns a value to a message.</span></span> <span data-ttu-id="8a5a1-132">尽管赋值的对象通常是消息，但所赋的值可以为任何类型。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-132">The value assigned can be of any type, though typically a message is assigned.</span></span>|<span data-ttu-id="8a5a1-133">Any</span><span class="sxs-lookup"><span data-stu-id="8a5a1-133">Any</span></span>|  
|<span data-ttu-id="8a5a1-134">**表达式**</span><span class="sxs-lookup"><span data-stu-id="8a5a1-134">**Expression**</span></span>|<span data-ttu-id="8a5a1-135">**表达式**形状使您能够输入您的业务流程中选择任何表达式。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-135">The **Expression** shape enables you to enter any expression you choose in your orchestration.</span></span> <span data-ttu-id="8a5a1-136">例如，您可以借助 .NET 调用来运行外部程序，或仅处理业务流程变量的值。</span><span class="sxs-lookup"><span data-stu-id="8a5a1-136">For example, you can make a .NET call to run an external program, or simply manipulate the values of your orchestration variables.</span></span>|<span data-ttu-id="8a5a1-137">Any</span><span class="sxs-lookup"><span data-stu-id="8a5a1-137">Any</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="8a5a1-138">本节内容</span><span class="sxs-lookup"><span data-stu-id="8a5a1-138">In This Section</span></span>  
 [<span data-ttu-id="8a5a1-139">如何使用表达式形状</span><span class="sxs-lookup"><span data-stu-id="8a5a1-139">How to Use Expression Shape</span></span>](../core/how-to-use-expression-shape.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a5a1-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a5a1-140">See Also</span></span>  
 <span data-ttu-id="8a5a1-141">[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="8a5a1-141">[Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md) </span></span>  
 <span data-ttu-id="8a5a1-142">[构造消息](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8a5a1-142">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 [<span data-ttu-id="8a5a1-143">配置流控制形状</span><span class="sxs-lookup"><span data-stu-id="8a5a1-143">Configuring Flow Control Shapes</span></span>](../core/configuring-flow-control-shapes.md)