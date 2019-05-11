---
title: 算术运算符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73e153c-aac1-4cea-92d8-af4a1bea6e6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e56d48f6c49107923541d5095fe0b1019f6afa
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528817"
---
# <a name="arithmetic-operators"></a><span data-ttu-id="84afd-102">算术运算符</span><span class="sxs-lookup"><span data-stu-id="84afd-102">Arithmetic Operators</span></span>
<span data-ttu-id="84afd-103">业务规则框架支持使用加法、 减法、 乘法、 除法和余数 （取模） 中创建业务规则的运算符。</span><span class="sxs-lookup"><span data-stu-id="84afd-103">The Business Rules Framework supports using the addition, subtraction, multiplication, division, and remainder (modulo) operators in creating business rules.</span></span> <span data-ttu-id="84afd-104">下表介绍的算术运算符。</span><span class="sxs-lookup"><span data-stu-id="84afd-104">The following table describes the arithmetic operators.</span></span>  
  
|<span data-ttu-id="84afd-105">算术运算符</span><span class="sxs-lookup"><span data-stu-id="84afd-105">Arithmetic operator</span></span>|<span data-ttu-id="84afd-106">Description</span><span class="sxs-lookup"><span data-stu-id="84afd-106">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="84afd-107">**“添加”**</span><span class="sxs-lookup"><span data-stu-id="84afd-107">**Add**</span></span>|<span data-ttu-id="84afd-108">表示加法运算符 (arg1 加上 arg2)。</span><span class="sxs-lookup"><span data-stu-id="84afd-108">Represents the addition operator (arg1 added to arg2).</span></span>|  
|<span data-ttu-id="84afd-109">**Subtract**</span><span class="sxs-lookup"><span data-stu-id="84afd-109">**Subtract**</span></span>|<span data-ttu-id="84afd-110">表示减法运算符 (arg2 减去 arg1)。</span><span class="sxs-lookup"><span data-stu-id="84afd-110">Represents the subtraction operator (arg1 subtracted from arg2).</span></span>|  
|<span data-ttu-id="84afd-111">**Multiply**</span><span class="sxs-lookup"><span data-stu-id="84afd-111">**Multiply**</span></span>|<span data-ttu-id="84afd-112">表示乘法运算符 (arg1 乘以 arg2)。</span><span class="sxs-lookup"><span data-stu-id="84afd-112">Represents the multiplication operator (arg1 multiplied by arg2).</span></span>|  
|<span data-ttu-id="84afd-113">**Divide**</span><span class="sxs-lookup"><span data-stu-id="84afd-113">**Divide**</span></span>|<span data-ttu-id="84afd-114">表示除法运算符 (arg1 除以 arg2)。</span><span class="sxs-lookup"><span data-stu-id="84afd-114">Represents the division operator (arg1 divided by arg2).</span></span>|  
|<span data-ttu-id="84afd-115">**其余部分**</span><span class="sxs-lookup"><span data-stu-id="84afd-115">**Remainder**</span></span>|<span data-ttu-id="84afd-116">表示余数运算符 (arg1 对 arg2 取模)。</span><span class="sxs-lookup"><span data-stu-id="84afd-116">Represents the remainder operator (arg1 modulo arg2).</span></span>|  
  
 <span data-ttu-id="84afd-117">不同类型的操作数时，自动进行数值升级使用较小的操作数类型转换为更大的操作数类型。</span><span class="sxs-lookup"><span data-stu-id="84afd-117">When operands are of different types, automatic numeric promotion occurs with the smaller operand type being converted to the larger operand type.</span></span> <span data-ttu-id="84afd-118">例如，如果**外**操作符的第一个操作数为**int**类型和第二个操作数**长**类型，第一个操作数的类型转换为**长**执行之前**添加**操作。</span><span class="sxs-lookup"><span data-stu-id="84afd-118">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **long** type, the type of the first operand is converted to **long** before performing the **Add** operation.</span></span> <span data-ttu-id="84afd-119">如果这两个操作数可升级为通用类型，规则引擎还支持双升级。</span><span class="sxs-lookup"><span data-stu-id="84afd-119">The rule engine also supports double promotion if both the operands can be promoted to a common type.</span></span> <span data-ttu-id="84afd-120">例如，如果**外**操作符的第一个操作数为**int**类型和第二个操作数**uint**类型，这两个操作数的类型转换为**长**执行之前**添加**操作。</span><span class="sxs-lookup"><span data-stu-id="84afd-120">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **uint** type, the types of both operands are converted to **long** before performing the **Add** operation.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="84afd-121">若要在业务规则中使用逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="84afd-121">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="84afd-122">使用以下过程在业务规则中使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="84afd-122">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="84afd-123">在事实浏览器窗口中，单击**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="84afd-123">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="84afd-124">展开**词汇**，展开**函数**，展开**版本 1.0-已发布**，然后将拖**添加/减/乘/除/余数**到条件窗格/操作窗格。</span><span class="sxs-lookup"><span data-stu-id="84afd-124">Expand **Vocabularies**, expand **Functions**, expand **Version 1.0 - Published**, and then drag the **Add/Subtract/Multiply/Divide/Remainder** to the Conditions pane/Actions pane.</span></span>  
  
3.  <span data-ttu-id="84afd-125">指定的左侧和右侧运算符的值。</span><span class="sxs-lookup"><span data-stu-id="84afd-125">Specify values for left and right operators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84afd-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="84afd-126">See Also</span></span>  
 [<span data-ttu-id="84afd-127">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="84afd-127">Logical Operators</span></span>](../core/logical-operators.md)