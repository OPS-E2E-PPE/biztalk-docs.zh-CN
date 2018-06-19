---
title: 使用 MATH_NUMERIC Type1 |Microsoft 文档
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
ms.openlocfilehash: ec4a5df2d15f489d52c8e3d6dfc575f9e644c646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288509"
---
# <a name="using-the-mathnumeric-type"></a>使用 MATH_NUMERIC 类型
本主题介绍了 MATH_NUMERIC 类型并详细说明了指数的处理方式、数字的最大位数以及小数的最大位数。 本主题还讨论下列内容：  
  
-   指数  
  
-   无效值  
  
-   操作精度  
  
-   货币  
  
 MATH_NUMERIC 类型为数值字符串类型。 若要使用此类型，请输入以下格式的参数值：  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 位置  
  
 `<OptionalSign>`可以是`+`或`-`。 `+`默认值。  
  
 `<IntegerAndFractionalPart>` 是最大数值的 32 有效数字，不包括小数点符号。 小数点符号是特定于区域设置到博士 Edwards EnterpriseOne 安装-通常一个句点 （.） 或逗号 （，）。 每个数字可能会所有整数、 所有分数，或一部分整数和一部分分数，但它们不能超过 32。  
  
 `<OptionalExponentPart>` 等于：  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 位置  
  
 `<OptionalSign>`可以是`+`或`-`。 `+`默认值。  
  
 `<ExponentDigits>` 最多是两位数字。 允许使用之间 63 个和-63 不包括零值。  
  
## <a name="valid-values"></a>有效值  
 示例**有效**MATH_NUMERIC 值：  
  
-   123.045  
  
-   4089 （请注意数千没有逗号）  
  
-   -9084  
  
-   -230.75  
  
-   0.010503  
  
-   1.023e-10，等效于 0.0000000001023  
  
-   0.097e5 或 0.097e + 5，等效于 9700  
  
-   1.0e-32 等于 0.00000000000000000000000000000001（这是 32 有效的分数数字，因为忽略了整数“0”。）  
  
## <a name="invalid-values"></a>无效值  
 无效的值取决于类型的值。 太小的小数被解释为零 （全部有效数字都将丢失）。 一个整数，过多的有效数字会导致意外的结果。 博士 Edwards EnterpriseOne 不会始终引发的错误条件在此情况下。 指数太大或太小，也会返回作为无效值。  
  
 示例**无效**MATH_NUMERIC 值：  
  
-   1034.00000000000000000000000000001023-太很多重要数字  
  
-   1.023e-64-指数太小  
  
-   0.00317e64-指数太大  
  
 适用于符号和十进制符号之外的任何非数字字符导致无效的值。  
  
## <a name="exponents"></a>指数  
 为了便于输入值，JD Edwards EnterpriseOne MATH_NUMERIC 提供了指数。 但是，大多数值返回不带指数 （与所有 32 位数可见）。  
  
## <a name="precision-for-operations"></a>操作精度  
 如果操作导致丢失精度，舍入会发生。 例如：  
  
 1.9e-31 / 10.0 = 0.00000000000000000000000000000002。  
  
 1.9e-31 / 100.0 = 0.00000000000000000000000000000000  
  
 在其他情况下，不可预知的结果发生，因为时是非常大的正数值的另一乘数。 1.01e32 * 2.053e32 不会生成可靠的结果并不会引发错误。 对于大多数的业务方案，这些范围不超过。  
  
## <a name="currency"></a>货币  
 当博士 Edwards EnterpriseOne 业务功能需要的货币值时，业务函数始终具有单独参数的四个字符货币代码。 不需要在此代码中传递，除非你使用非默认为博士 Edwards EnterpriseOne 系统配置了一种货币。  
  
## <a name="see-also"></a>另请参阅  
 [附录 b： 数据类型](../core/appendix-b-data-types.md)