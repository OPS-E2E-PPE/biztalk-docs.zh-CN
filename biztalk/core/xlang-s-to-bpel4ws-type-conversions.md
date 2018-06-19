---
title: 类型转换，到 BPEL4WS XLANG-s |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XLANG/s
- XLANG/s, warning
- XLANG/s, BPEL4WS
- XLANG/s, converting
ms.assetid: a35d4dba-9344-43c8-86e6-a373a4452579
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02412b86b8649b73cadb4715793f085682a1de74
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973739"
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a><span data-ttu-id="e2f6c-102">XLANG-s 的 BPEL4WS 类型转换</span><span class="sxs-lookup"><span data-stu-id="e2f6c-102">XLANG-s to BPEL4WS Type Conversions</span></span>
<span data-ttu-id="e2f6c-103">下表详细说明了各种 XLANG/s 构造和 BPEL4WS 构造之间的转换。</span><span class="sxs-lookup"><span data-stu-id="e2f6c-103">The following tables detail the conversions between various XLANG/s constructs and BPEL4WS constructs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e2f6c-104">XPath 1.1 不支持以指数记数法表示的数字或双精度格式。</span><span class="sxs-lookup"><span data-stu-id="e2f6c-104">XPath 1.1 does not support numbers in exponential or double formats.</span></span> <span data-ttu-id="e2f6c-105">XLANG/s 业务流程中使用这些格式的文本值使用 %f 格式导出到 BPEL4WS，因此可能会影响精度。</span><span class="sxs-lookup"><span data-stu-id="e2f6c-105">Literal values in these formats in XLANG/s orchestrations are exported to BPEL4WS using the %f format, and a loss of precision might result.</span></span>  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a><span data-ttu-id="e2f6c-106">文本（如果文本是表达式的一部分）</span><span class="sxs-lookup"><span data-stu-id="e2f6c-106">Literals (if the literal is part of an expression)</span></span>  
  
|<span data-ttu-id="e2f6c-107">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="e2f6c-107">XLANG/s</span></span>|<span data-ttu-id="e2f6c-108">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="e2f6c-108">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="e2f6c-109">字符串、字符</span><span class="sxs-lookup"><span data-stu-id="e2f6c-109">String, character</span></span>|<span data-ttu-id="e2f6c-110">XPath 字符串</span><span class="sxs-lookup"><span data-stu-id="e2f6c-110">XPath string</span></span>|  
|<span data-ttu-id="e2f6c-111">整数、实型</span><span class="sxs-lookup"><span data-stu-id="e2f6c-111">Integer, real</span></span>|<span data-ttu-id="e2f6c-112">XPath 数字</span><span class="sxs-lookup"><span data-stu-id="e2f6c-112">XPath number</span></span>|  
|<span data-ttu-id="e2f6c-113">布尔值“true”、“false”</span><span class="sxs-lookup"><span data-stu-id="e2f6c-113">Boolean "true", "false"</span></span>|<span data-ttu-id="e2f6c-114">XPath true()、false() 函数</span><span class="sxs-lookup"><span data-stu-id="e2f6c-114">XPath true(), false() functions</span></span>|  
  
## <a name="literals-standalone-assignment"></a><span data-ttu-id="e2f6c-115">文本（单独赋值）</span><span class="sxs-lookup"><span data-stu-id="e2f6c-115">Literals (standalone assignment)</span></span>  
  
|<span data-ttu-id="e2f6c-116">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="e2f6c-116">XLANG/s</span></span>|<span data-ttu-id="e2f6c-117">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="e2f6c-117">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="e2f6c-118">文本常数</span><span class="sxs-lookup"><span data-stu-id="e2f6c-118">Literal constant</span></span>|<span data-ttu-id="e2f6c-119">XSD 等价</span><span class="sxs-lookup"><span data-stu-id="e2f6c-119">XSD equivalent</span></span>|  
  
## <a name="variables"></a><span data-ttu-id="e2f6c-120">变量</span><span class="sxs-lookup"><span data-stu-id="e2f6c-120">Variables</span></span>  
  
|<span data-ttu-id="e2f6c-121">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="e2f6c-121">XLANG/s</span></span>|<span data-ttu-id="e2f6c-122">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="e2f6c-122">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="e2f6c-123">变量引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-123">Variable reference</span></span>|<span data-ttu-id="e2f6c-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="e2f6c-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span></span>|  
|<span data-ttu-id="e2f6c-125">消息引用（.NET 类型）</span><span class="sxs-lookup"><span data-stu-id="e2f6c-125">Message reference (.NET type)</span></span>|<span data-ttu-id="e2f6c-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="e2f6c-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span></span>|  
|<span data-ttu-id="e2f6c-127">消息部分引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-127">Message-part reference</span></span>|<span data-ttu-id="e2f6c-128">bpws:getContainerData(%msgName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="e2f6c-128">bpws:getContainerData(%msgName%, %locationPath%)</span></span>|  
|<span data-ttu-id="e2f6c-129">可分辨字段引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-129">Distinguished-field reference</span></span>|<span data-ttu-id="e2f6c-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="e2f6c-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span></span>|  
|<span data-ttu-id="e2f6c-131">消息数据属性引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-131">Message data-property reference</span></span>|<span data-ttu-id="e2f6c-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span><span class="sxs-lookup"><span data-stu-id="e2f6c-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span></span>|  
  
## <a name="operators"></a><span data-ttu-id="e2f6c-133">运算符</span><span class="sxs-lookup"><span data-stu-id="e2f6c-133">Operators</span></span>  
  
|<span data-ttu-id="e2f6c-134">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="e2f6c-134">XLANG/s</span></span>|<span data-ttu-id="e2f6c-135">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="e2f6c-135">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="e2f6c-136">Unary +</span><span class="sxs-lookup"><span data-stu-id="e2f6c-136">Unary +</span></span>|<span data-ttu-id="e2f6c-137">忽略</span><span class="sxs-lookup"><span data-stu-id="e2f6c-137">Ignored</span></span>|  
|<span data-ttu-id="e2f6c-138">一元：-</span><span class="sxs-lookup"><span data-stu-id="e2f6c-138">Unary -</span></span>|<span data-ttu-id="e2f6c-139">XPath unary -</span><span class="sxs-lookup"><span data-stu-id="e2f6c-139">XPath unary -</span></span>|  
|<span data-ttu-id="e2f6c-140">Unary !</span><span class="sxs-lookup"><span data-stu-id="e2f6c-140">Unary !</span></span>|<span data-ttu-id="e2f6c-141">XPath not() 函数</span><span class="sxs-lookup"><span data-stu-id="e2f6c-141">XPath not() function</span></span>|  
|<span data-ttu-id="e2f6c-142">二进制 & &、 &#124; &#124;</span><span class="sxs-lookup"><span data-stu-id="e2f6c-142">Binary &&, &#124;&#124;</span></span>|<span data-ttu-id="e2f6c-143">XPath 'and'、'or' 运算符</span><span class="sxs-lookup"><span data-stu-id="e2f6c-143">XPath 'and', 'or' operators</span></span>|  
|<span data-ttu-id="e2f6c-144">二进制 = =、 ！ =、 < =、 <>、 =、 ></span><span class="sxs-lookup"><span data-stu-id="e2f6c-144">Binary ==, !=, <=, <, >=, ></span></span>|<span data-ttu-id="e2f6c-145">XPath '='、'!</span><span class="sxs-lookup"><span data-stu-id="e2f6c-145">XPath '=', '!</span></span> <span data-ttu-id="e2f6c-146">=，< ='，' <'，' > =，> 运算符</span><span class="sxs-lookup"><span data-stu-id="e2f6c-146">=', '<=', '<', '>=', '>' operators</span></span>|  
|<span data-ttu-id="e2f6c-147">使用两个整数操作数的 Binary +、-、\*、%</span><span class="sxs-lookup"><span data-stu-id="e2f6c-147">Binary +, -, \*, % with both integral operands</span></span>|<span data-ttu-id="e2f6c-148">XPath '+'、'-'、'\*'、'mod' 运算符</span><span class="sxs-lookup"><span data-stu-id="e2f6c-148">XPath '+', '-', '\*', 'mod' operators</span></span>|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a><span data-ttu-id="e2f6c-149">BPEL4WS 中不允许的 XLANG/s 构造</span><span class="sxs-lookup"><span data-stu-id="e2f6c-149">XLANG/s constructs that are disallowed in BPEL4WS</span></span>  
  
-   <span data-ttu-id="e2f6c-150">消息上下文属性引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-150">Message context-property reference</span></span>  
  
-   <span data-ttu-id="e2f6c-151">服务属性引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-151">Service-property reference</span></span>  
  
-   <span data-ttu-id="e2f6c-152">端口属性引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-152">Port-property reference</span></span>  
  
-   <span data-ttu-id="e2f6c-153">服务链接属性引用</span><span class="sxs-lookup"><span data-stu-id="e2f6c-153">Service link-property reference</span></span>  
  
-   <span data-ttu-id="e2f6c-154">一元 – 非整数类型</span><span class="sxs-lookup"><span data-stu-id="e2f6c-154">Unary – with non-integral type</span></span>  
  
-   <span data-ttu-id="e2f6c-155">Unary ~</span><span class="sxs-lookup"><span data-stu-id="e2f6c-155">Unary ~</span></span>  
  
-   <span data-ttu-id="e2f6c-156">强制转换运算符</span><span class="sxs-lookup"><span data-stu-id="e2f6c-156">Cast operator</span></span>  
  
-   <span data-ttu-id="e2f6c-157">Binary，使用整数操作数</span><span class="sxs-lookup"><span data-stu-id="e2f6c-157">Binary / with integral operands</span></span>  
  
-   <span data-ttu-id="e2f6c-158">Binary +、-、\*、%，使用非整数操作数</span><span class="sxs-lookup"><span data-stu-id="e2f6c-158">Binary +, -, \*, %, / with non-integral operands</span></span>  
  
-   <span data-ttu-id="e2f6c-159">二进制 < =、 <>、 =、 > 与非字符串操作数</span><span class="sxs-lookup"><span data-stu-id="e2f6c-159">Binary <=, <, >=, > with non-string operands</span></span>  
  
-   <span data-ttu-id="e2f6c-160">按位运算符 &、 ^，&#124;</span><span class="sxs-lookup"><span data-stu-id="e2f6c-160">Bitwise operators &, ^, &#124;</span></span>  
  
-   <span data-ttu-id="e2f6c-161">移位运算符 <<>>，</span><span class="sxs-lookup"><span data-stu-id="e2f6c-161">Shift operators <<, >></span></span>  
  
-   <span data-ttu-id="e2f6c-162">已检查表达式</span><span class="sxs-lookup"><span data-stu-id="e2f6c-162">Checked expression</span></span>  
  
-   <span data-ttu-id="e2f6c-163">内部表达式</span><span class="sxs-lookup"><span data-stu-id="e2f6c-163">Intrinsic expression</span></span>  
  
-   <span data-ttu-id="e2f6c-164">前递增、后递增、前递减和后递减 ++、--</span><span class="sxs-lookup"><span data-stu-id="e2f6c-164">Pre- and post- increment and decrement ++, --</span></span>  
  
-   <span data-ttu-id="e2f6c-165">对象调用（有 out、没有 out 和/或 ref 参数）</span><span class="sxs-lookup"><span data-stu-id="e2f6c-165">Object invocation (with our without out and/or ref params)</span></span>  
  
-   <span data-ttu-id="e2f6c-166">'new' 运算符</span><span class="sxs-lookup"><span data-stu-id="e2f6c-166">'new' operator</span></span>