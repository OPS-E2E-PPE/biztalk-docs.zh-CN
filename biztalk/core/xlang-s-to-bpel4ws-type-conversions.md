---
title: Xlang-s 到 BPEL4WS 的类型转换 |Microsoft Docs
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
ms.openlocfilehash: 84a184251428568305c553b63bbb164785758aca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244068"
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a><span data-ttu-id="7c942-102">Xlang-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="7c942-102">XLANG-s to BPEL4WS Type Conversions</span></span>
<span data-ttu-id="7c942-103">下表详细说明各种 XLANG/s 构造和 BPEL4WS 构造之间的转换。</span><span class="sxs-lookup"><span data-stu-id="7c942-103">The following tables detail the conversions between various XLANG/s constructs and BPEL4WS constructs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7c942-104">XPath 1.1 不支持以指数或双精度格式的数字。</span><span class="sxs-lookup"><span data-stu-id="7c942-104">XPath 1.1 does not support numbers in exponential or double formats.</span></span> <span data-ttu-id="7c942-105">XLANG/s 业务流程中使用这些格式中的文本值导出到 BPEL4WS 使用 %f 格式和精度降低可能会导致。</span><span class="sxs-lookup"><span data-stu-id="7c942-105">Literal values in these formats in XLANG/s orchestrations are exported to BPEL4WS using the %f format, and a loss of precision might result.</span></span>  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a><span data-ttu-id="7c942-106">文本 （如果文本表达式的一部分）</span><span class="sxs-lookup"><span data-stu-id="7c942-106">Literals (if the literal is part of an expression)</span></span>  
  
|<span data-ttu-id="7c942-107">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="7c942-107">XLANG/s</span></span>|<span data-ttu-id="7c942-108">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="7c942-108">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="7c942-109">字符串、 字符</span><span class="sxs-lookup"><span data-stu-id="7c942-109">String, character</span></span>|<span data-ttu-id="7c942-110">XPath 字符串</span><span class="sxs-lookup"><span data-stu-id="7c942-110">XPath string</span></span>|  
|<span data-ttu-id="7c942-111">整数、 实型</span><span class="sxs-lookup"><span data-stu-id="7c942-111">Integer, real</span></span>|<span data-ttu-id="7c942-112">XPath 数字</span><span class="sxs-lookup"><span data-stu-id="7c942-112">XPath number</span></span>|  
|<span data-ttu-id="7c942-113">布尔值"true"、"false"</span><span class="sxs-lookup"><span data-stu-id="7c942-113">Boolean "true", "false"</span></span>|<span data-ttu-id="7c942-114">XPath true （)、 false （） 函数</span><span class="sxs-lookup"><span data-stu-id="7c942-114">XPath true(), false() functions</span></span>|  
  
## <a name="literals-standalone-assignment"></a><span data-ttu-id="7c942-115">文本 （单独赋值）</span><span class="sxs-lookup"><span data-stu-id="7c942-115">Literals (standalone assignment)</span></span>  
  
|<span data-ttu-id="7c942-116">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="7c942-116">XLANG/s</span></span>|<span data-ttu-id="7c942-117">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="7c942-117">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="7c942-118">文本常量</span><span class="sxs-lookup"><span data-stu-id="7c942-118">Literal constant</span></span>|<span data-ttu-id="7c942-119">XSD 等价</span><span class="sxs-lookup"><span data-stu-id="7c942-119">XSD equivalent</span></span>|  
  
## <a name="variables"></a><span data-ttu-id="7c942-120">变量</span><span class="sxs-lookup"><span data-stu-id="7c942-120">Variables</span></span>  
  
|<span data-ttu-id="7c942-121">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="7c942-121">XLANG/s</span></span>|<span data-ttu-id="7c942-122">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="7c942-122">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="7c942-123">变量引用</span><span class="sxs-lookup"><span data-stu-id="7c942-123">Variable reference</span></span>|<span data-ttu-id="7c942-124">bpws:getContainerData(%varName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="7c942-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span></span>|  
|<span data-ttu-id="7c942-125">消息参考 （.NET 类型）</span><span class="sxs-lookup"><span data-stu-id="7c942-125">Message reference (.NET type)</span></span>|<span data-ttu-id="7c942-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="7c942-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span></span>|  
|<span data-ttu-id="7c942-127">消息部分引用</span><span class="sxs-lookup"><span data-stu-id="7c942-127">Message-part reference</span></span>|<span data-ttu-id="7c942-128">bpws:getContainerData(%msgName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="7c942-128">bpws:getContainerData(%msgName%, %locationPath%)</span></span>|  
|<span data-ttu-id="7c942-129">可分辨字段引用</span><span class="sxs-lookup"><span data-stu-id="7c942-129">Distinguished-field reference</span></span>|<span data-ttu-id="7c942-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="7c942-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span></span>|  
|<span data-ttu-id="7c942-131">消息数据属性引用</span><span class="sxs-lookup"><span data-stu-id="7c942-131">Message data-property reference</span></span>|<span data-ttu-id="7c942-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span><span class="sxs-lookup"><span data-stu-id="7c942-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span></span>|  
  
## <a name="operators"></a><span data-ttu-id="7c942-133">运算符</span><span class="sxs-lookup"><span data-stu-id="7c942-133">Operators</span></span>  
  
|<span data-ttu-id="7c942-134">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="7c942-134">XLANG/s</span></span>|<span data-ttu-id="7c942-135">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="7c942-135">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="7c942-136">一元 +</span><span class="sxs-lookup"><span data-stu-id="7c942-136">Unary +</span></span>|<span data-ttu-id="7c942-137">忽略</span><span class="sxs-lookup"><span data-stu-id="7c942-137">Ignored</span></span>|  
|<span data-ttu-id="7c942-138">一元-</span><span class="sxs-lookup"><span data-stu-id="7c942-138">Unary -</span></span>|<span data-ttu-id="7c942-139">XPath 一元-</span><span class="sxs-lookup"><span data-stu-id="7c942-139">XPath unary -</span></span>|  
|<span data-ttu-id="7c942-140">一元 ！</span><span class="sxs-lookup"><span data-stu-id="7c942-140">Unary !</span></span>|<span data-ttu-id="7c942-141">XPath not （） 函数</span><span class="sxs-lookup"><span data-stu-id="7c942-141">XPath not() function</span></span>|  
|<span data-ttu-id="7c942-142">二进制 & &、&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="7c942-142">Binary &&, &#124;&#124;</span></span>|<span data-ttu-id="7c942-143">XPath 'and'、 'or' 运算符</span><span class="sxs-lookup"><span data-stu-id="7c942-143">XPath 'and', 'or' operators</span></span>|  
|<span data-ttu-id="7c942-144">二进制 = =、 ！ =、 < =、 <>、 =、 ></span><span class="sxs-lookup"><span data-stu-id="7c942-144">Binary ==, !=, <=, <, >=, ></span></span>|<span data-ttu-id="7c942-145">XPath =、 ！</span><span class="sxs-lookup"><span data-stu-id="7c942-145">XPath '=', '!</span></span> <span data-ttu-id="7c942-146">=，< ='，' <'，' > =，> 运算符</span><span class="sxs-lookup"><span data-stu-id="7c942-146">=', '<=', '<', '>=', '>' operators</span></span>|  
|<span data-ttu-id="7c942-147">二进制 +、-、 \*、 %使用这两个整数操作数</span><span class="sxs-lookup"><span data-stu-id="7c942-147">Binary +, -, \*, % with both integral operands</span></span>|<span data-ttu-id="7c942-148">XPath '+'、 '-'，' \*'，'mod' 运算符</span><span class="sxs-lookup"><span data-stu-id="7c942-148">XPath '+', '-', '\*', 'mod' operators</span></span>|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a><span data-ttu-id="7c942-149">BPEL4WS 中不允许的 XLANG/s 构造</span><span class="sxs-lookup"><span data-stu-id="7c942-149">XLANG/s constructs that are disallowed in BPEL4WS</span></span>  
  
-   <span data-ttu-id="7c942-150">消息上下文属性引用</span><span class="sxs-lookup"><span data-stu-id="7c942-150">Message context-property reference</span></span>  
  
-   <span data-ttu-id="7c942-151">服务属性引用</span><span class="sxs-lookup"><span data-stu-id="7c942-151">Service-property reference</span></span>  
  
-   <span data-ttu-id="7c942-152">端口属性引用</span><span class="sxs-lookup"><span data-stu-id="7c942-152">Port-property reference</span></span>  
  
-   <span data-ttu-id="7c942-153">服务链接属性引用</span><span class="sxs-lookup"><span data-stu-id="7c942-153">Service link-property reference</span></span>  
  
-   <span data-ttu-id="7c942-154">一元 – 非整数类型</span><span class="sxs-lookup"><span data-stu-id="7c942-154">Unary – with non-integral type</span></span>  
  
-   <span data-ttu-id="7c942-155">一元 ~</span><span class="sxs-lookup"><span data-stu-id="7c942-155">Unary ~</span></span>  
  
-   <span data-ttu-id="7c942-156">强制转换运算符</span><span class="sxs-lookup"><span data-stu-id="7c942-156">Cast operator</span></span>  
  
-   <span data-ttu-id="7c942-157">二进制使用整数操作数</span><span class="sxs-lookup"><span data-stu-id="7c942-157">Binary / with integral operands</span></span>  
  
-   <span data-ttu-id="7c942-158">二进制 +、-、 \*、 %、 使用非整数操作数</span><span class="sxs-lookup"><span data-stu-id="7c942-158">Binary +, -, \*, %, / with non-integral operands</span></span>  
  
-   <span data-ttu-id="7c942-159">二进制 < =、 <>、 =、 > 使用非字符串操作数</span><span class="sxs-lookup"><span data-stu-id="7c942-159">Binary <=, <, >=, > with non-string operands</span></span>  
  
-   <span data-ttu-id="7c942-160">按位运算符 &，^，&#124;</span><span class="sxs-lookup"><span data-stu-id="7c942-160">Bitwise operators &, ^, &#124;</span></span>  
  
-   <span data-ttu-id="7c942-161">移位运算符 <<>>、</span><span class="sxs-lookup"><span data-stu-id="7c942-161">Shift operators <<, >></span></span>  
  
-   <span data-ttu-id="7c942-162">已检查的表达式</span><span class="sxs-lookup"><span data-stu-id="7c942-162">Checked expression</span></span>  
  
-   <span data-ttu-id="7c942-163">内部函数的表达式</span><span class="sxs-lookup"><span data-stu-id="7c942-163">Intrinsic expression</span></span>  
  
-   <span data-ttu-id="7c942-164">预处理脚本和后续递增和递减 + +、-</span><span class="sxs-lookup"><span data-stu-id="7c942-164">Pre- and post- increment and decrement ++, --</span></span>  
  
-   <span data-ttu-id="7c942-165">对象调用 (与我们无需扩展和/或 ref 参数)</span><span class="sxs-lookup"><span data-stu-id="7c942-165">Object invocation (with our without out and/or ref params)</span></span>  
  
-   <span data-ttu-id="7c942-166">'new' 运算符</span><span class="sxs-lookup"><span data-stu-id="7c942-166">'new' operator</span></span>