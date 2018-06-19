---
title: 算术运算符 |Microsoft 文档
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
ms.openlocfilehash: 4b3d66a990437929176835228efa1a74a5fa8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230517"
---
# <a name="arithmetic-operators"></a><span data-ttu-id="d719d-102">算术运算符</span><span class="sxs-lookup"><span data-stu-id="d719d-102">Arithmetic Operators</span></span>
<span data-ttu-id="d719d-103">业务规则框架支持在创建业务规则时使用加、减、乘、除和余数（模）运算符。</span><span class="sxs-lookup"><span data-stu-id="d719d-103">The Business Rules Framework supports using the addition, subtraction, multiplication, division, and remainder (modulo) operators in creating business rules.</span></span> <span data-ttu-id="d719d-104">下表对这些算术运算符进行了说明。</span><span class="sxs-lookup"><span data-stu-id="d719d-104">The following table describes the arithmetic operators.</span></span>  
  
|<span data-ttu-id="d719d-105">算术运算符</span><span class="sxs-lookup"><span data-stu-id="d719d-105">Arithmetic operator</span></span>|<span data-ttu-id="d719d-106">Description</span><span class="sxs-lookup"><span data-stu-id="d719d-106">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="d719d-107">**添加**</span><span class="sxs-lookup"><span data-stu-id="d719d-107">**Add**</span></span>|<span data-ttu-id="d719d-108">表示加法运算符（arg1 加上 arg2）。</span><span class="sxs-lookup"><span data-stu-id="d719d-108">Represents the addition operator (arg1 added to arg2).</span></span>|  
|<span data-ttu-id="d719d-109">**减去**</span><span class="sxs-lookup"><span data-stu-id="d719d-109">**Subtract**</span></span>|<span data-ttu-id="d719d-110">表示减法运算符（arg2 减去 arg1）。</span><span class="sxs-lookup"><span data-stu-id="d719d-110">Represents the subtraction operator (arg1 subtracted from arg2).</span></span>|  
|<span data-ttu-id="d719d-111">**乘**</span><span class="sxs-lookup"><span data-stu-id="d719d-111">**Multiply**</span></span>|<span data-ttu-id="d719d-112">表示乘法运算符（arg1 乘以 arg2）。</span><span class="sxs-lookup"><span data-stu-id="d719d-112">Represents the multiplication operator (arg1 multiplied by arg2).</span></span>|  
|<span data-ttu-id="d719d-113">**Divide**</span><span class="sxs-lookup"><span data-stu-id="d719d-113">**Divide**</span></span>|<span data-ttu-id="d719d-114">表示除法运算符（arg1 除以 arg2）。</span><span class="sxs-lookup"><span data-stu-id="d719d-114">Represents the division operator (arg1 divided by arg2).</span></span>|  
|<span data-ttu-id="d719d-115">**余数**</span><span class="sxs-lookup"><span data-stu-id="d719d-115">**Remainder**</span></span>|<span data-ttu-id="d719d-116">表示余数运算符（arg1 对 arg2 求模）。</span><span class="sxs-lookup"><span data-stu-id="d719d-116">Represents the remainder operator (arg1 modulo arg2).</span></span>|  
  
 <span data-ttu-id="d719d-117">如果操作数类型不同，则会自动进行数值升级，较小的操作数类型将会被转换为较大的操作数类型。</span><span class="sxs-lookup"><span data-stu-id="d719d-117">When operands are of different types, automatic numeric promotion occurs with the smaller operand type being converted to the larger operand type.</span></span> <span data-ttu-id="d719d-118">例如，如果**添加**运算符用于的第一个操作数**int**类型和第二个操作数的**长**类型，第一个操作数的类型转换为**长**之前执行**添加**操作。</span><span class="sxs-lookup"><span data-stu-id="d719d-118">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **long** type, the type of the first operand is converted to **long** before performing the **Add** operation.</span></span> <span data-ttu-id="d719d-119">如果两个操作数可升级为同一类型，则规则引擎还支持双升级。</span><span class="sxs-lookup"><span data-stu-id="d719d-119">The rule engine also supports double promotion if both the operands can be promoted to a common type.</span></span> <span data-ttu-id="d719d-120">例如，如果**添加**运算符用于的第一个操作数**int**类型和第二个操作数的**uint**类型，这两个操作数的类型转换为**长**之前执行**添加**操作。</span><span class="sxs-lookup"><span data-stu-id="d719d-120">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **uint** type, the types of both operands are converted to **long** before performing the **Add** operation.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="d719d-121">在业务规则中使用逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="d719d-121">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="d719d-122">利用以下过程可在业务规则中使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="d719d-122">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="d719d-123">在事实浏览器窗口中，单击**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d719d-123">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="d719d-124">展开**词汇**，展开**函数**，展开**版本 1.0-发布**，然后拖动**添加/减/乘/除/余数**到条件窗格/操作窗格。</span><span class="sxs-lookup"><span data-stu-id="d719d-124">Expand **Vocabularies**, expand **Functions**, expand **Version 1.0 - Published**, and then drag the **Add/Subtract/Multiply/Divide/Remainder** to the Conditions pane/Actions pane.</span></span>  
  
3.  <span data-ttu-id="d719d-125">为左操作数和右操作数指定值。</span><span class="sxs-lookup"><span data-stu-id="d719d-125">Specify values for left and right operators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d719d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d719d-126">See Also</span></span>  
 [<span data-ttu-id="d719d-127">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="d719d-127">Logical Operators</span></span>](../core/logical-operators.md)