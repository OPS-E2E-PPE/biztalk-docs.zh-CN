---
title: 使用 MATH_NUMERIC Type2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exponents, JD Edwards OneWorld adapters
- currency, JD Edwards OneWorld adapters
- MATH_NUMERIC type
- adapters [JD Edwards OneWorld adapters], currency
ms.assetid: 14d04576-0028-4af4-84bd-92c4ca492126
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13de687f158bc18f4fa6a036ab239a25774d02ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998902"
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="6171f-102">使用 MATH_NUMERIC 类型</span><span class="sxs-lookup"><span data-stu-id="6171f-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="6171f-103">本主题介绍了 MATH_NUMERIC 类型并详细说明了指数的处理方式、数字的最大位数以及小数的最大位数。</span><span class="sxs-lookup"><span data-stu-id="6171f-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="6171f-104">它还包括有关以下内容的讨论：</span><span class="sxs-lookup"><span data-stu-id="6171f-104">It also includes a discussion on the following:</span></span>  
  
- <span data-ttu-id="6171f-105">指数的后面</span><span class="sxs-lookup"><span data-stu-id="6171f-105">Exponents</span></span>  
  
- <span data-ttu-id="6171f-106">无效值</span><span class="sxs-lookup"><span data-stu-id="6171f-106">Invalid Values</span></span>  
  
- <span data-ttu-id="6171f-107">操作精度</span><span class="sxs-lookup"><span data-stu-id="6171f-107">Precision for Operations</span></span>  
  
- <span data-ttu-id="6171f-108">货币</span><span class="sxs-lookup"><span data-stu-id="6171f-108">Currency</span></span>  
  
  <span data-ttu-id="6171f-109">MATH_NUMERIC 类型为数值字符串类型。</span><span class="sxs-lookup"><span data-stu-id="6171f-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="6171f-110">若要使用此类型，请输入以下格式的参数值：</span><span class="sxs-lookup"><span data-stu-id="6171f-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
```  
  
 <span data-ttu-id="6171f-111">位置</span><span class="sxs-lookup"><span data-stu-id="6171f-111">Where</span></span>  
  
- <span data-ttu-id="6171f-112">`<OptionalSign>` 可以是`+`或`-`。</span><span class="sxs-lookup"><span data-stu-id="6171f-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="6171f-113">`+` 默认值。</span><span class="sxs-lookup"><span data-stu-id="6171f-113">`+` is the default.</span></span>  
  
- <span data-ttu-id="6171f-114">`<IntegerAndFractionalPart>` 是最大数值的 32 有效数字，不包括小数点符号。</span><span class="sxs-lookup"><span data-stu-id="6171f-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="6171f-115">小数点符号对于 JD Edwards OneWorld 安装来说是特定于区域设置的 - 通常为句点 (.) 或逗号 (,)。</span><span class="sxs-lookup"><span data-stu-id="6171f-115">The decimal symbol is locale-specific to the JD Edwards OneWorld installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="6171f-116">数字可能是所有整数、 所有分数，或一部分整数和部分分数，但它们不能超过 32。</span><span class="sxs-lookup"><span data-stu-id="6171f-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
- <span data-ttu-id="6171f-117">`<OptionalExponentPart>` 等于：</span><span class="sxs-lookup"><span data-stu-id="6171f-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
  ```  
  'e' <OptionalSign><ExponentDigits>  
  ```  
  
  <span data-ttu-id="6171f-118">位置</span><span class="sxs-lookup"><span data-stu-id="6171f-118">Where</span></span>  
  
- <span data-ttu-id="6171f-119">`<OptionalSign>` 可以是`+`或-。</span><span class="sxs-lookup"><span data-stu-id="6171f-119">`<OptionalSign>` can be `+` or -.</span></span> <span data-ttu-id="6171f-120">`+` 默认值。</span><span class="sxs-lookup"><span data-stu-id="6171f-120">`+` is the default.</span></span>  
  
- <span data-ttu-id="6171f-121">`<ExponentDigits>` 最多是两位数字。</span><span class="sxs-lookup"><span data-stu-id="6171f-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="6171f-122">允许使用 63 之间，不包括零值。</span><span class="sxs-lookup"><span data-stu-id="6171f-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="6171f-123">有效值</span><span class="sxs-lookup"><span data-stu-id="6171f-123">Valid Values</span></span>  
 <span data-ttu-id="6171f-124">有效 MATH_NUMERIC 值的示例：</span><span class="sxs-lookup"><span data-stu-id="6171f-124">Examples of valid MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="6171f-125">123.045</span><span class="sxs-lookup"><span data-stu-id="6171f-125">123.045</span></span>  
  
-   <span data-ttu-id="6171f-126">4089 （请注意数千个没有逗号）</span><span class="sxs-lookup"><span data-stu-id="6171f-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="6171f-127">-9084</span><span class="sxs-lookup"><span data-stu-id="6171f-127">-9084</span></span>  
  
-   <span data-ttu-id="6171f-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="6171f-128">-230.75</span></span>  
  
-   <span data-ttu-id="6171f-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="6171f-129">0.010503</span></span>  
  
-   <span data-ttu-id="6171f-130">1.023e-10，其等同于 0.0000000001023</span><span class="sxs-lookup"><span data-stu-id="6171f-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="6171f-131">0.097e5 或 0.097e + 5，等效于 9700</span><span class="sxs-lookup"><span data-stu-id="6171f-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="6171f-132">1.0e-32，等于 0.00000000000000000000000000000001</span><span class="sxs-lookup"><span data-stu-id="6171f-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001</span></span>  
  
     <span data-ttu-id="6171f-133">（此值有效，因为在这种情况下，整数“0”将被忽略，所以有效小数位为 32。）</span><span class="sxs-lookup"><span data-stu-id="6171f-133">(This is valid because in this case the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="6171f-134">无效值</span><span class="sxs-lookup"><span data-stu-id="6171f-134">Invalid Values</span></span>  
 <span data-ttu-id="6171f-135">无效的值取决于值的种类。</span><span class="sxs-lookup"><span data-stu-id="6171f-135">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="6171f-136">太小，为小数部分被解释为零 （全部有效数字都将丢失）。</span><span class="sxs-lookup"><span data-stu-id="6171f-136">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="6171f-137">一个整数，过多的有效数字会导致意外的结果。</span><span class="sxs-lookup"><span data-stu-id="6171f-137">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="6171f-138">在这种情况下，JD Edwards OneWorld 不会始终导致错误。</span><span class="sxs-lookup"><span data-stu-id="6171f-138">JD Edwards OneWorld does not always raise an error condition in this case.</span></span>  
  
 <span data-ttu-id="6171f-139">太大或太小的指数会返回无效值。</span><span class="sxs-lookup"><span data-stu-id="6171f-139">An exponent that is too large or small returns as an invalid value.</span></span>  
  
 <span data-ttu-id="6171f-140">无效 MATH_NUMERIC 值的示例：</span><span class="sxs-lookup"><span data-stu-id="6171f-140">Examples of invalid MATH_NUMERIC values:</span></span>  
  
- <span data-ttu-id="6171f-141">1034.00000000000000000000000000001023-太多的有效数字</span><span class="sxs-lookup"><span data-stu-id="6171f-141">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
- <span data-ttu-id="6171f-142">1.023e-64-指数太小</span><span class="sxs-lookup"><span data-stu-id="6171f-142">1.023e-64 - exponent too small</span></span>  
  
- <span data-ttu-id="6171f-143">0.00317e64-指数太大</span><span class="sxs-lookup"><span data-stu-id="6171f-143">0.00317e64 - exponent too large</span></span>  
  
  <span data-ttu-id="6171f-144">适用于符号和十进制符号以外的任何非数字字符会导致无效的值。</span><span class="sxs-lookup"><span data-stu-id="6171f-144">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="6171f-145">指数的后面</span><span class="sxs-lookup"><span data-stu-id="6171f-145">Exponents</span></span>  
 <span data-ttu-id="6171f-146">指数由 JD Edwards OneWorld MATH_NUMERIC 提供以便于输入值。</span><span class="sxs-lookup"><span data-stu-id="6171f-146">Exponents are provided by the JD Edwards OneWorld MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="6171f-147">但是，大多数值返回不带指数的后面 （与所有 32 有效数字可见）。</span><span class="sxs-lookup"><span data-stu-id="6171f-147">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="6171f-148">操作精度</span><span class="sxs-lookup"><span data-stu-id="6171f-148">Precision for Operations</span></span>  
 <span data-ttu-id="6171f-149">如果操作导致丢失精度，舍入将会发生。</span><span class="sxs-lookup"><span data-stu-id="6171f-149">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="6171f-150">例如：</span><span class="sxs-lookup"><span data-stu-id="6171f-150">For example:</span></span>  
  
 <span data-ttu-id="6171f-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span><span class="sxs-lookup"><span data-stu-id="6171f-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span></span>  
  
 <span data-ttu-id="6171f-152">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="6171f-152">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="6171f-153">在其他情况下，不可预知的结果发生，因为当非常大的正数值乘以另一个。</span><span class="sxs-lookup"><span data-stu-id="6171f-153">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span>  
  
 <span data-ttu-id="6171f-154">1.01e32 \* 2.053e32 不生成可靠的结果并不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="6171f-154">1.01e32 \* 2.053e32 does not yield reliable results and does not raise an error.</span></span>  
  
 <span data-ttu-id="6171f-155">大多数业务情况下，未超过这些范围。</span><span class="sxs-lookup"><span data-stu-id="6171f-155">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="6171f-156">货币</span><span class="sxs-lookup"><span data-stu-id="6171f-156">Currency</span></span>  
 <span data-ttu-id="6171f-157">当 JD Edwards OneWorld 业务功能需要货币值时，业务功能会始终对四个字符的货币代码拥有单独的参数。</span><span class="sxs-lookup"><span data-stu-id="6171f-157">When a JD Edwards OneWorld business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="6171f-158">不必传递此代码，除非您使用的货币不是为 JD Edwards OneWorld 系统配置的默认货币。</span><span class="sxs-lookup"><span data-stu-id="6171f-158">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards OneWorld system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6171f-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="6171f-159">See Also</span></span>  
 [<span data-ttu-id="6171f-160">附录 A：数据类型</span><span class="sxs-lookup"><span data-stu-id="6171f-160">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)