---
title: "类型转换，到 BPEL4WS XLANG-s |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XLANG/s
- XLANG/s, warning
- XLANG/s, BPEL4WS
- XLANG/s, converting
ms.assetid: a35d4dba-9344-43c8-86e6-a373a4452579
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02412b86b8649b73cadb4715793f085682a1de74
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a><span data-ttu-id="b1fb5-102">XLANG-s 的 BPEL4WS 类型转换</span><span class="sxs-lookup"><span data-stu-id="b1fb5-102">XLANG-s to BPEL4WS Type Conversions</span></span>
<span data-ttu-id="b1fb5-103">下表详细说明了各种 XLANG/s 构造和 BPEL4WS 构造之间的转换。</span><span class="sxs-lookup"><span data-stu-id="b1fb5-103">The following tables detail the conversions between various XLANG/s constructs and BPEL4WS constructs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b1fb5-104">XPath 1.1 不支持以指数记数法表示的数字或双精度格式。</span><span class="sxs-lookup"><span data-stu-id="b1fb5-104">XPath 1.1 does not support numbers in exponential or double formats.</span></span> <span data-ttu-id="b1fb5-105">XLANG/s 业务流程中使用这些格式的文本值使用 %f 格式导出到 BPEL4WS，因此可能会影响精度。</span><span class="sxs-lookup"><span data-stu-id="b1fb5-105">Literal values in these formats in XLANG/s orchestrations are exported to BPEL4WS using the %f format, and a loss of precision might result.</span></span>  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a><span data-ttu-id="b1fb5-106">文本（如果文本是表达式的一部分）</span><span class="sxs-lookup"><span data-stu-id="b1fb5-106">Literals (if the literal is part of an expression)</span></span>  
  
|<span data-ttu-id="b1fb5-107">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="b1fb5-107">XLANG/s</span></span>|<span data-ttu-id="b1fb5-108">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="b1fb5-108">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="b1fb5-109">字符串、字符</span><span class="sxs-lookup"><span data-stu-id="b1fb5-109">String, character</span></span>|<span data-ttu-id="b1fb5-110">XPath 字符串</span><span class="sxs-lookup"><span data-stu-id="b1fb5-110">XPath string</span></span>|  
|<span data-ttu-id="b1fb5-111">整数、实型</span><span class="sxs-lookup"><span data-stu-id="b1fb5-111">Integer, real</span></span>|<span data-ttu-id="b1fb5-112">XPath 数字</span><span class="sxs-lookup"><span data-stu-id="b1fb5-112">XPath number</span></span>|  
|<span data-ttu-id="b1fb5-113">布尔值“true”、“false”</span><span class="sxs-lookup"><span data-stu-id="b1fb5-113">Boolean "true", "false"</span></span>|<span data-ttu-id="b1fb5-114">XPath true()、false() 函数</span><span class="sxs-lookup"><span data-stu-id="b1fb5-114">XPath true(), false() functions</span></span>|  
  
## <a name="literals-standalone-assignment"></a><span data-ttu-id="b1fb5-115">文本（单独赋值）</span><span class="sxs-lookup"><span data-stu-id="b1fb5-115">Literals (standalone assignment)</span></span>  
  
|<span data-ttu-id="b1fb5-116">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="b1fb5-116">XLANG/s</span></span>|<span data-ttu-id="b1fb5-117">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="b1fb5-117">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="b1fb5-118">文本常数</span><span class="sxs-lookup"><span data-stu-id="b1fb5-118">Literal constant</span></span>|<span data-ttu-id="b1fb5-119">XSD 等价</span><span class="sxs-lookup"><span data-stu-id="b1fb5-119">XSD equivalent</span></span>|  
  
## <a name="variables"></a><span data-ttu-id="b1fb5-120">变量</span><span class="sxs-lookup"><span data-stu-id="b1fb5-120">Variables</span></span>  
  
|<span data-ttu-id="b1fb5-121">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="b1fb5-121">XLANG/s</span></span>|<span data-ttu-id="b1fb5-122">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="b1fb5-122">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="b1fb5-123">变量引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-123">Variable reference</span></span>|<span data-ttu-id="b1fb5-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="b1fb5-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span></span>|  
|<span data-ttu-id="b1fb5-125">消息引用（.NET 类型）</span><span class="sxs-lookup"><span data-stu-id="b1fb5-125">Message reference (.NET type)</span></span>|<span data-ttu-id="b1fb5-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="b1fb5-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span></span>|  
|<span data-ttu-id="b1fb5-127">消息部分引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-127">Message-part reference</span></span>|<span data-ttu-id="b1fb5-128">bpws:getContainerData(%msgName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="b1fb5-128">bpws:getContainerData(%msgName%, %locationPath%)</span></span>|  
|<span data-ttu-id="b1fb5-129">可分辨字段引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-129">Distinguished-field reference</span></span>|<span data-ttu-id="b1fb5-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="b1fb5-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span></span>|  
|<span data-ttu-id="b1fb5-131">消息数据属性引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-131">Message data-property reference</span></span>|<span data-ttu-id="b1fb5-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span><span class="sxs-lookup"><span data-stu-id="b1fb5-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span></span>|  
  
## <a name="operators"></a><span data-ttu-id="b1fb5-133">运算符</span><span class="sxs-lookup"><span data-stu-id="b1fb5-133">Operators</span></span>  
  
|<span data-ttu-id="b1fb5-134">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="b1fb5-134">XLANG/s</span></span>|<span data-ttu-id="b1fb5-135">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="b1fb5-135">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="b1fb5-136">Unary +</span><span class="sxs-lookup"><span data-stu-id="b1fb5-136">Unary +</span></span>|<span data-ttu-id="b1fb5-137">忽略</span><span class="sxs-lookup"><span data-stu-id="b1fb5-137">Ignored</span></span>|  
|<span data-ttu-id="b1fb5-138">一元：-</span><span class="sxs-lookup"><span data-stu-id="b1fb5-138">Unary -</span></span>|<span data-ttu-id="b1fb5-139">XPath unary -</span><span class="sxs-lookup"><span data-stu-id="b1fb5-139">XPath unary -</span></span>|  
|<span data-ttu-id="b1fb5-140">Unary !</span><span class="sxs-lookup"><span data-stu-id="b1fb5-140">Unary !</span></span>|<span data-ttu-id="b1fb5-141">XPath not() 函数</span><span class="sxs-lookup"><span data-stu-id="b1fb5-141">XPath not() function</span></span>|  
|<span data-ttu-id="b1fb5-142">二进制 & &、 &#124; &#124;</span><span class="sxs-lookup"><span data-stu-id="b1fb5-142">Binary &&, &#124;&#124;</span></span>|<span data-ttu-id="b1fb5-143">XPath 'and'、'or' 运算符</span><span class="sxs-lookup"><span data-stu-id="b1fb5-143">XPath 'and', 'or' operators</span></span>|  
|<span data-ttu-id="b1fb5-144">二进制 = =、 ！ =、 < =、 <>、 =、 ></span><span class="sxs-lookup"><span data-stu-id="b1fb5-144">Binary ==, !=, <=, <, >=, ></span></span>|<span data-ttu-id="b1fb5-145">XPath '='、'!</span><span class="sxs-lookup"><span data-stu-id="b1fb5-145">XPath '=', '!</span></span> <span data-ttu-id="b1fb5-146">=，< ='，' <'，' > =，> 运算符</span><span class="sxs-lookup"><span data-stu-id="b1fb5-146">=', '<=', '<', '>=', '>' operators</span></span>|  
|<span data-ttu-id="b1fb5-147">使用两个整数操作数的 Binary +、-、*、%</span><span class="sxs-lookup"><span data-stu-id="b1fb5-147">Binary +, -, *, % with both integral operands</span></span>|<span data-ttu-id="b1fb5-148">XPath '+'、'-'、'*'、'mod' 运算符</span><span class="sxs-lookup"><span data-stu-id="b1fb5-148">XPath '+', '-', '*', 'mod' operators</span></span>|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a><span data-ttu-id="b1fb5-149">BPEL4WS 中不允许的 XLANG/s 构造</span><span class="sxs-lookup"><span data-stu-id="b1fb5-149">XLANG/s constructs that are disallowed in BPEL4WS</span></span>  
  
-   <span data-ttu-id="b1fb5-150">消息上下文属性引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-150">Message context-property reference</span></span>  
  
-   <span data-ttu-id="b1fb5-151">服务属性引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-151">Service-property reference</span></span>  
  
-   <span data-ttu-id="b1fb5-152">端口属性引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-152">Port-property reference</span></span>  
  
-   <span data-ttu-id="b1fb5-153">服务链接属性引用</span><span class="sxs-lookup"><span data-stu-id="b1fb5-153">Service link-property reference</span></span>  
  
-   <span data-ttu-id="b1fb5-154">一元 – 非整数类型</span><span class="sxs-lookup"><span data-stu-id="b1fb5-154">Unary – with non-integral type</span></span>  
  
-   <span data-ttu-id="b1fb5-155">Unary ~</span><span class="sxs-lookup"><span data-stu-id="b1fb5-155">Unary ~</span></span>  
  
-   <span data-ttu-id="b1fb5-156">强制转换运算符</span><span class="sxs-lookup"><span data-stu-id="b1fb5-156">Cast operator</span></span>  
  
-   <span data-ttu-id="b1fb5-157">Binary，使用整数操作数</span><span class="sxs-lookup"><span data-stu-id="b1fb5-157">Binary / with integral operands</span></span>  
  
-   <span data-ttu-id="b1fb5-158">Binary +、-、*、%，使用非整数操作数</span><span class="sxs-lookup"><span data-stu-id="b1fb5-158">Binary +, -, *, %, / with non-integral operands</span></span>  
  
-   <span data-ttu-id="b1fb5-159">二进制 < =、 <>、 =、 > 与非字符串操作数</span><span class="sxs-lookup"><span data-stu-id="b1fb5-159">Binary <=, <, >=, > with non-string operands</span></span>  
  
-   <span data-ttu-id="b1fb5-160">按位运算符 &、 ^，&#124;</span><span class="sxs-lookup"><span data-stu-id="b1fb5-160">Bitwise operators &, ^, &#124;</span></span>  
  
-   <span data-ttu-id="b1fb5-161">移位运算符 <<>>，</span><span class="sxs-lookup"><span data-stu-id="b1fb5-161">Shift operators <<, >></span></span>  
  
-   <span data-ttu-id="b1fb5-162">已检查表达式</span><span class="sxs-lookup"><span data-stu-id="b1fb5-162">Checked expression</span></span>  
  
-   <span data-ttu-id="b1fb5-163">内部表达式</span><span class="sxs-lookup"><span data-stu-id="b1fb5-163">Intrinsic expression</span></span>  
  
-   <span data-ttu-id="b1fb5-164">前递增、后递增、前递减和后递减 ++、--</span><span class="sxs-lookup"><span data-stu-id="b1fb5-164">Pre- and post- increment and decrement ++, --</span></span>  
  
-   <span data-ttu-id="b1fb5-165">对象调用（有 out、没有 out 和/或 ref 参数）</span><span class="sxs-lookup"><span data-stu-id="b1fb5-165">Object invocation (with our without out and/or ref params)</span></span>  
  
-   <span data-ttu-id="b1fb5-166">'new' 运算符</span><span class="sxs-lookup"><span data-stu-id="b1fb5-166">'new' operator</span></span>