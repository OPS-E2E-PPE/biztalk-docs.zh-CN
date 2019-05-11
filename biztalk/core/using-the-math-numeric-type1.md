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
ms.openlocfilehash: 519605c89cc808c91e1045c191dc01ec46739ae8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396008"
---
# <a name="using-the-mathnumeric-type"></a>使用 MATH_NUMERIC 类型
本主题介绍了 MATH_NUMERIC 类型和指数的处理方式的详细信息、 数字、 最大数目和十进制数字的最大数目。 它还包括上的讨论：  
  
- 指数的后面  
  
- 无效值  
  
- 操作精度  
  
- 货币  
  
  MATH_NUMERIC 类型为数值字符串类型。 若要使用它，输入以下格式的参数值：  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 位置  
  
 `<OptionalSign>` 可以是 `+` 或 `-`。 `+` 默认值。  
  
 `<IntegerAndFractionalPart>` 最多为 32 有效数字，不包括小数点符号。 小数点符号是特定于区域设置到 JD Edwards EnterpriseOne 安装-通常一个句点 （.） 或逗号 （，）。 数字可能是所有整数、 所有分数，或一部分整数和部分分数，但它们不能超过 32。  
  
 `<OptionalExponentPart>` 等效于：  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 位置  
  
 `<OptionalSign>` 可以是 `+` 或 `-`。 `+` 默认值。  
  
 `<ExponentDigits>` 最多是两位数字。 允许使用 63 之间，不包括零值。  
  
## <a name="valid-values"></a>有效值  
 示例**有效**MATH_NUMERIC 值：  
  
-   123.045  
  
-   4089 （请注意数千个没有逗号）  
  
-   -9084  
  
-   -230.75  
  
-   0.010503  
  
-   1.023e-10，其等同于 0.0000000001023  
  
-   0.097e5 或 0.097e + 5，等效于 9700  
  
-   1.0e-32 等于 0.00000000000000000000000000000001 (这是有效的在这种情况下，整数"0"将被忽略，因为 32 有效小数位。)  
  
## <a name="invalid-values"></a>无效值  
 无效的值取决于值的种类。 太小，为小数部分被解释为零 （全部有效数字都将丢失）。 一个整数，过多的有效数字会导致意外的结果。 JD Edwards EnterpriseOne 不会始终引发的错误条件在此情况下。 太大或太小的指数也会返回作为无效值。  
  
 示例**无效**MATH_NUMERIC 值：  
  
- 1034.00000000000000000000000000001023-太多的有效数字  
  
- 1.023e-64-指数太小  
  
- 0.00317e64-指数太大  
  
  适用于符号和十进制符号以外的任何非数字字符会导致无效的值。  
  
## <a name="exponents"></a>指数的后面  
 指数的后面是由 JD Edwards EnterpriseOne MATH_NUMERIC 中为方便起见提供用于在输入值。 但是，大多数值返回不带指数的后面 （与所有 32 有效数字可见）。  
  
## <a name="precision-for-operations"></a>操作精度  
 如果操作导致丢失精度，舍入将会发生。 例如：  
  
 1.9e-31 / 10.0 = 0.00000000000000000000000000000002.  
  
 1.9e-31 / 100.0 = 0.00000000000000000000000000000000  
  
 在其他情况下，不可预知的结果发生，因为当非常大的正数值乘以另一个。 1.01e32 * 2.053e32 不生成可靠的结果并不会引发错误。 大多数业务情况下，未超过这些范围。  
  
## <a name="currency"></a>货币  
 当 JD Edwards EnterpriseOne 业务功能需要货币值时，业务函数始终具有四个字符的货币代码单独的参数。 不需要传递此代码，除非您使用的一种货币而不是默认为 JD Edwards EnterpriseOne 系统配置。  
  
## <a name="see-also"></a>请参阅  
 [附录 b:数据类型](../core/appendix-b-data-types.md)