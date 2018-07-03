---
title: 使用 MATH_NUMERIC 类型 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards EnterpriseOne adapters], currency
- JD Edwards EnterpriseOne adapters, exponents
- adapters [JD Edwards EnterpriseOne adapters], exponents
- MATH_NUMERIC type
- currency, values [JD Edwards EnterpriseOne adapters]
- JD Edwards EnterpriseOne adapters, currency
- exponents, values [JD Edwards EnterpriseOne adapters]
ms.assetid: 2a302216-f0a6-4afb-8f7d-bb1475ea1c57
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dba376c1bbbb6e5219969b97393f72380c75d9fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007526"
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="69403-102">使用 MATH_NUMERIC 类型</span><span class="sxs-lookup"><span data-stu-id="69403-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="69403-103">本主题介绍了 MATH_NUMERIC 类型并详细说明了指数的处理方式、数字的最大位数以及小数的最大位数。</span><span class="sxs-lookup"><span data-stu-id="69403-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="69403-104">本主题还讨论下列内容：</span><span class="sxs-lookup"><span data-stu-id="69403-104">It also includes a discussion on:</span></span>  
  
- <span data-ttu-id="69403-105">指数的后面</span><span class="sxs-lookup"><span data-stu-id="69403-105">Exponents</span></span>  
  
- <span data-ttu-id="69403-106">无效值</span><span class="sxs-lookup"><span data-stu-id="69403-106">Invalid Values</span></span>  
  
- <span data-ttu-id="69403-107">操作精度</span><span class="sxs-lookup"><span data-stu-id="69403-107">Precision for Operations</span></span>  
  
- <span data-ttu-id="69403-108">货币</span><span class="sxs-lookup"><span data-stu-id="69403-108">Currency</span></span>  
  
  <span data-ttu-id="69403-109">MATH_NUMERIC 类型为数值字符串类型。</span><span class="sxs-lookup"><span data-stu-id="69403-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="69403-110">若要使用此类型，请输入以下格式的参数值：</span><span class="sxs-lookup"><span data-stu-id="69403-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 <span data-ttu-id="69403-111">位置</span><span class="sxs-lookup"><span data-stu-id="69403-111">Where</span></span>  
  
 <span data-ttu-id="69403-112">`<OptionalSign>` 可以是`+`或`-`。</span><span class="sxs-lookup"><span data-stu-id="69403-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="69403-113">`+` 默认值。</span><span class="sxs-lookup"><span data-stu-id="69403-113">`+` is the default.</span></span>  
  
 <span data-ttu-id="69403-114">`<IntegerAndFractionalPart>` 是最大数值的 32 有效数字，不包括小数点符号。</span><span class="sxs-lookup"><span data-stu-id="69403-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="69403-115">小数点符号是特定于区域设置到 JD Edwards EnterpriseOne 安装-通常一个句点 （.） 或逗号 （，）。</span><span class="sxs-lookup"><span data-stu-id="69403-115">The decimal symbol is locale-specific to the JD Edwards EnterpriseOne installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="69403-116">数字可能是所有整数、 所有分数，或一部分整数和部分分数，但它们不能超过 32。</span><span class="sxs-lookup"><span data-stu-id="69403-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
 <span data-ttu-id="69403-117">`<OptionalExponentPart>` 等于：</span><span class="sxs-lookup"><span data-stu-id="69403-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 <span data-ttu-id="69403-118">位置</span><span class="sxs-lookup"><span data-stu-id="69403-118">Where</span></span>  
  
 <span data-ttu-id="69403-119">`<OptionalSign>` 可以是`+`或`-`。</span><span class="sxs-lookup"><span data-stu-id="69403-119">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="69403-120">`+` 默认值。</span><span class="sxs-lookup"><span data-stu-id="69403-120">`+` is the default.</span></span>  
  
 <span data-ttu-id="69403-121">`<ExponentDigits>` 最多是两位数字。</span><span class="sxs-lookup"><span data-stu-id="69403-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="69403-122">允许使用 63 之间，不包括零值。</span><span class="sxs-lookup"><span data-stu-id="69403-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="69403-123">有效值</span><span class="sxs-lookup"><span data-stu-id="69403-123">Valid Values</span></span>  
 <span data-ttu-id="69403-124">示例**有效**MATH_NUMERIC 值：</span><span class="sxs-lookup"><span data-stu-id="69403-124">Examples of **valid** MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="69403-125">123.045</span><span class="sxs-lookup"><span data-stu-id="69403-125">123.045</span></span>  
  
-   <span data-ttu-id="69403-126">4089 （请注意数千个没有逗号）</span><span class="sxs-lookup"><span data-stu-id="69403-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="69403-127">-9084</span><span class="sxs-lookup"><span data-stu-id="69403-127">-9084</span></span>  
  
-   <span data-ttu-id="69403-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="69403-128">-230.75</span></span>  
  
-   <span data-ttu-id="69403-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="69403-129">0.010503</span></span>  
  
-   <span data-ttu-id="69403-130">1.023e-10，其等同于 0.0000000001023</span><span class="sxs-lookup"><span data-stu-id="69403-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="69403-131">0.097e5 或 0.097e + 5，等效于 9700</span><span class="sxs-lookup"><span data-stu-id="69403-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="69403-132">1.0e-32 等于 0.00000000000000000000000000000001（这是 32 有效的分数数字，因为忽略了整数“0”。）</span><span class="sxs-lookup"><span data-stu-id="69403-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001 (This is valid because in this case, the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="69403-133">无效值</span><span class="sxs-lookup"><span data-stu-id="69403-133">Invalid Values</span></span>  
 <span data-ttu-id="69403-134">无效的值取决于值的种类。</span><span class="sxs-lookup"><span data-stu-id="69403-134">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="69403-135">太小，为小数部分被解释为零 （全部有效数字都将丢失）。</span><span class="sxs-lookup"><span data-stu-id="69403-135">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="69403-136">一个整数，过多的有效数字会导致意外的结果。</span><span class="sxs-lookup"><span data-stu-id="69403-136">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="69403-137">JD Edwards EnterpriseOne 不会始终引发的错误条件在此情况下。</span><span class="sxs-lookup"><span data-stu-id="69403-137">JD Edwards EnterpriseOne does not always raise an error condition in this case.</span></span> <span data-ttu-id="69403-138">太大或太小的指数也会返回作为无效值。</span><span class="sxs-lookup"><span data-stu-id="69403-138">An exponent that is too large or too small also returns as an invalid value.</span></span>  
  
 <span data-ttu-id="69403-139">示例**无效**MATH_NUMERIC 值：</span><span class="sxs-lookup"><span data-stu-id="69403-139">Examples of **invalid** MATH_NUMERIC values:</span></span>  
  
- <span data-ttu-id="69403-140">1034.00000000000000000000000000001023-太多的有效数字</span><span class="sxs-lookup"><span data-stu-id="69403-140">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
- <span data-ttu-id="69403-141">1.023e-64-指数太小</span><span class="sxs-lookup"><span data-stu-id="69403-141">1.023e-64 - exponent too small</span></span>  
  
- <span data-ttu-id="69403-142">0.00317e64-指数太大</span><span class="sxs-lookup"><span data-stu-id="69403-142">0.00317e64 - exponent too large</span></span>  
  
  <span data-ttu-id="69403-143">适用于符号和十进制符号以外的任何非数字字符会导致无效的值。</span><span class="sxs-lookup"><span data-stu-id="69403-143">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="69403-144">指数的后面</span><span class="sxs-lookup"><span data-stu-id="69403-144">Exponents</span></span>  
 <span data-ttu-id="69403-145">为了便于输入值，JD Edwards EnterpriseOne MATH_NUMERIC 提供了指数。</span><span class="sxs-lookup"><span data-stu-id="69403-145">Exponents are provided by the JD Edwards EnterpriseOne MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="69403-146">但是，大多数值返回不带指数的后面 （与所有 32 有效数字可见）。</span><span class="sxs-lookup"><span data-stu-id="69403-146">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="69403-147">操作精度</span><span class="sxs-lookup"><span data-stu-id="69403-147">Precision for Operations</span></span>  
 <span data-ttu-id="69403-148">如果操作导致丢失精度，舍入将会发生。</span><span class="sxs-lookup"><span data-stu-id="69403-148">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="69403-149">例如：</span><span class="sxs-lookup"><span data-stu-id="69403-149">For example:</span></span>  
  
 <span data-ttu-id="69403-150">1.9e-31 / 10.0 = 0.00000000000000000000000000000002。</span><span class="sxs-lookup"><span data-stu-id="69403-150">1.9e-31 / 10.0 = 0.00000000000000000000000000000002.</span></span>  
  
 <span data-ttu-id="69403-151">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="69403-151">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="69403-152">在其他情况下，不可预知的结果发生，因为当非常大的正数值乘以另一个。</span><span class="sxs-lookup"><span data-stu-id="69403-152">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span> <span data-ttu-id="69403-153">1.01e32 \* 2.053e32 不生成可靠的结果并不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="69403-153">1.01e32 \* 2.053e32 does not yield reliable results and does not raise an error.</span></span> <span data-ttu-id="69403-154">大多数业务情况下，未超过这些范围。</span><span class="sxs-lookup"><span data-stu-id="69403-154">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="69403-155">货币</span><span class="sxs-lookup"><span data-stu-id="69403-155">Currency</span></span>  
 <span data-ttu-id="69403-156">当 JD Edwards EnterpriseOne 业务功能需要货币值时，业务函数始终具有四个字符的货币代码单独的参数。</span><span class="sxs-lookup"><span data-stu-id="69403-156">When a JD Edwards EnterpriseOne business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="69403-157">不需要传递此代码，除非您使用的一种货币而不是默认为 JD Edwards EnterpriseOne 系统配置。</span><span class="sxs-lookup"><span data-stu-id="69403-157">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards EnterpriseOne system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69403-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="69403-158">See Also</span></span>  
 [<span data-ttu-id="69403-159">附录 B：数据类型</span><span class="sxs-lookup"><span data-stu-id="69403-159">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)