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
ms.openlocfilehash: ba2390cb20b053fa20c460f670975702772d0ab3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396022"
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="ee1ab-102">使用 MATH_NUMERIC 类型</span><span class="sxs-lookup"><span data-stu-id="ee1ab-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="ee1ab-103">本主题介绍了 MATH_NUMERIC 类型和指数的处理方式的详细信息、 数字、 最大数目和十进制数字的最大数目。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="ee1ab-104">它还包括以下的讨论：</span><span class="sxs-lookup"><span data-stu-id="ee1ab-104">It also includes a discussion on the following:</span></span>  
  
- <span data-ttu-id="ee1ab-105">指数的后面</span><span class="sxs-lookup"><span data-stu-id="ee1ab-105">Exponents</span></span>  
  
- <span data-ttu-id="ee1ab-106">无效值</span><span class="sxs-lookup"><span data-stu-id="ee1ab-106">Invalid Values</span></span>  
  
- <span data-ttu-id="ee1ab-107">操作精度</span><span class="sxs-lookup"><span data-stu-id="ee1ab-107">Precision for Operations</span></span>  
  
- <span data-ttu-id="ee1ab-108">货币</span><span class="sxs-lookup"><span data-stu-id="ee1ab-108">Currency</span></span>  
  
  <span data-ttu-id="ee1ab-109">MATH_NUMERIC 类型为数值字符串类型。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="ee1ab-110">若要使用它，输入以下格式的参数值：</span><span class="sxs-lookup"><span data-stu-id="ee1ab-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
```  
  
 <span data-ttu-id="ee1ab-111">位置</span><span class="sxs-lookup"><span data-stu-id="ee1ab-111">Where</span></span>  
  
- <span data-ttu-id="ee1ab-112">`<OptionalSign>` 可以是 `+` 或 `-`。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="ee1ab-113">`+` 默认值。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-113">`+` is the default.</span></span>  
  
- <span data-ttu-id="ee1ab-114">`<IntegerAndFractionalPart>` 最多为 32 有效数字，不包括小数点符号。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="ee1ab-115">小数点符号是特定于区域设置到 JD Edwards OneWorld 安装-通常一个句点 （.） 或逗号 （，）。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-115">The decimal symbol is locale-specific to the JD Edwards OneWorld installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="ee1ab-116">数字可能是所有整数、 所有分数，或一部分整数和部分分数，但它们不能超过 32。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
- <span data-ttu-id="ee1ab-117">`<OptionalExponentPart>` 等效于：</span><span class="sxs-lookup"><span data-stu-id="ee1ab-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
  ```  
  'e' <OptionalSign><ExponentDigits>  
  ```  
  
  <span data-ttu-id="ee1ab-118">位置</span><span class="sxs-lookup"><span data-stu-id="ee1ab-118">Where</span></span>  
  
- <span data-ttu-id="ee1ab-119">`<OptionalSign>` 可以是`+`或-。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-119">`<OptionalSign>` can be `+` or -.</span></span> <span data-ttu-id="ee1ab-120">`+` 默认值。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-120">`+` is the default.</span></span>  
  
- <span data-ttu-id="ee1ab-121">`<ExponentDigits>` 最多是两位数字。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="ee1ab-122">允许使用 63 之间，不包括零值。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="ee1ab-123">有效值</span><span class="sxs-lookup"><span data-stu-id="ee1ab-123">Valid Values</span></span>  
 <span data-ttu-id="ee1ab-124">有效 MATH_NUMERIC 值的示例：</span><span class="sxs-lookup"><span data-stu-id="ee1ab-124">Examples of valid MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="ee1ab-125">123.045</span><span class="sxs-lookup"><span data-stu-id="ee1ab-125">123.045</span></span>  
  
-   <span data-ttu-id="ee1ab-126">4089 （请注意数千个没有逗号）</span><span class="sxs-lookup"><span data-stu-id="ee1ab-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="ee1ab-127">-9084</span><span class="sxs-lookup"><span data-stu-id="ee1ab-127">-9084</span></span>  
  
-   <span data-ttu-id="ee1ab-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="ee1ab-128">-230.75</span></span>  
  
-   <span data-ttu-id="ee1ab-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="ee1ab-129">0.010503</span></span>  
  
-   <span data-ttu-id="ee1ab-130">1.023e-10，其等同于 0.0000000001023</span><span class="sxs-lookup"><span data-stu-id="ee1ab-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="ee1ab-131">0.097e5 或 0.097e + 5，等效于 9700</span><span class="sxs-lookup"><span data-stu-id="ee1ab-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="ee1ab-132">1.0e-32 等于 0.00000000000000000000000000000001</span><span class="sxs-lookup"><span data-stu-id="ee1ab-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001</span></span>  
  
     <span data-ttu-id="ee1ab-133">(这是有效的因为在这种情况下，整数"0"将被忽略，32 有效小数位。)</span><span class="sxs-lookup"><span data-stu-id="ee1ab-133">(This is valid because in this case the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="ee1ab-134">无效值</span><span class="sxs-lookup"><span data-stu-id="ee1ab-134">Invalid Values</span></span>  
 <span data-ttu-id="ee1ab-135">无效的值取决于值的种类。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-135">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="ee1ab-136">太小，为小数部分被解释为零 （全部有效数字都将丢失）。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-136">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="ee1ab-137">一个整数，过多的有效数字会导致意外的结果。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-137">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="ee1ab-138">JD Edwards OneWorld 不会始终引发的错误条件在此情况下。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-138">JD Edwards OneWorld does not always raise an error condition in this case.</span></span>  
  
 <span data-ttu-id="ee1ab-139">太大或小的指数返回作为无效值。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-139">An exponent that is too large or small returns as an invalid value.</span></span>  
  
 <span data-ttu-id="ee1ab-140">无效 MATH_NUMERIC 值的示例：</span><span class="sxs-lookup"><span data-stu-id="ee1ab-140">Examples of invalid MATH_NUMERIC values:</span></span>  
  
- <span data-ttu-id="ee1ab-141">1034.00000000000000000000000000001023-太多的有效数字</span><span class="sxs-lookup"><span data-stu-id="ee1ab-141">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
- <span data-ttu-id="ee1ab-142">1.023e-64-指数太小</span><span class="sxs-lookup"><span data-stu-id="ee1ab-142">1.023e-64 - exponent too small</span></span>  
  
- <span data-ttu-id="ee1ab-143">0.00317e64-指数太大</span><span class="sxs-lookup"><span data-stu-id="ee1ab-143">0.00317e64 - exponent too large</span></span>  
  
  <span data-ttu-id="ee1ab-144">适用于符号和十进制符号以外的任何非数字字符会导致无效的值。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-144">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="ee1ab-145">指数的后面</span><span class="sxs-lookup"><span data-stu-id="ee1ab-145">Exponents</span></span>  
 <span data-ttu-id="ee1ab-146">指数的后面是由 JD Edwards OneWorld MATH_NUMERIC 中为方便起见提供用于在输入值。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-146">Exponents are provided by the JD Edwards OneWorld MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="ee1ab-147">但是，大多数值返回不带指数的后面 （与所有 32 有效数字可见）。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-147">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="ee1ab-148">操作精度</span><span class="sxs-lookup"><span data-stu-id="ee1ab-148">Precision for Operations</span></span>  
 <span data-ttu-id="ee1ab-149">如果操作导致丢失精度，舍入将会发生。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-149">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="ee1ab-150">例如：</span><span class="sxs-lookup"><span data-stu-id="ee1ab-150">For example:</span></span>  
  
 <span data-ttu-id="ee1ab-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span><span class="sxs-lookup"><span data-stu-id="ee1ab-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span></span>  
  
 <span data-ttu-id="ee1ab-152">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="ee1ab-152">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="ee1ab-153">在其他情况下，不可预知的结果发生，因为当非常大的正数值乘以另一个。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-153">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span>  
  
 <span data-ttu-id="ee1ab-154">1.01e32 \* 2.053e32 不生成可靠的结果并不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-154">1.01e32 \* 2.053e32 does not yield reliable results and does not raise an error.</span></span>  
  
 <span data-ttu-id="ee1ab-155">大多数业务情况下，未超过这些范围。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-155">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="ee1ab-156">货币</span><span class="sxs-lookup"><span data-stu-id="ee1ab-156">Currency</span></span>  
 <span data-ttu-id="ee1ab-157">当 JD Edwards OneWorld 业务功能需要货币值时，业务函数始终具有四个字符的货币代码单独的参数。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-157">When a JD Edwards OneWorld business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="ee1ab-158">不需要传递此代码，除非您使用的一种货币而不是默认为 JD Edwards OneWorld 系统配置。</span><span class="sxs-lookup"><span data-stu-id="ee1ab-158">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards OneWorld system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1ab-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee1ab-159">See Also</span></span>  
 [<span data-ttu-id="ee1ab-160">附录 a:数据类型</span><span class="sxs-lookup"><span data-stu-id="ee1ab-160">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)