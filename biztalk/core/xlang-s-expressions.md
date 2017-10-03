---
title: "XLANG-s 表达式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a477ee2c-7fd7-43bd-a194-0d68d79613fc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37d6099757998b0428d761f124785c363a24f2b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-expressions"></a><span data-ttu-id="14cb4-102">XLANG-s 表达式</span><span class="sxs-lookup"><span data-stu-id="14cb4-102">XLANG-s Expressions</span></span>
<span data-ttu-id="14cb4-103">表达式是运算符和操作数构成的序列。</span><span class="sxs-lookup"><span data-stu-id="14cb4-103">An expression is a sequence of operators and operands.</span></span> <span data-ttu-id="14cb4-104">本主题将说明 XLANG/s 针对各种表达式所支持的语法。</span><span class="sxs-lookup"><span data-stu-id="14cb4-104">This topic illustrates the syntax that XLANG/s supports for various expressions.</span></span>  
  
## <a name="basic-expressions"></a><span data-ttu-id="14cb4-105">基本表达式</span><span class="sxs-lookup"><span data-stu-id="14cb4-105">Basic Expressions</span></span>  
 <span data-ttu-id="14cb4-106">下面的代码显示了基本表达式的语法：</span><span class="sxs-lookup"><span data-stu-id="14cb4-106">The following code shows the syntax for basic expressions:</span></span>  
  
```  
primary-expression:  
     literal  
     enum-constant  
     variable-reference  
     invocation-expression  
     message-field-reference  
     message-property-reference  
     message-part-property-reference  
     correlation-property-reference  
     port-property-reference  
     service-property-reference  
     service-link-property-reference  
     message-part-reference  
     parenthesized-expression  
     object-reference  
     checked-expression  
     unchecked-expression  
     intrinsic-expression  
     xpath-expression  
     exists-expression  
enum-constant:  
     enum-type-name.enum-member  
enum-type-name:  
     type-name  
enum-member:  
     identifier  
parenthesized-expression:  
     (expression)  
checked-expression:  
     checked(expression)  
     checked(statement)  
unchecked-expression:  
     unchecked(expression)  
     unchecked(statement)  
unary-expression:  
     primary-expression  
     + unary-expression  
     - unary-expression  
     ! unary-expression  
     ~ unary-expression  
     cast-expression  
     property-reference exists  
cast-expression:  
     (type-name) unary-expression  
multiplicative-expression:  
     exists-expression  
     multiplicative-expression * unary-expression  
     multiplicative-expression / unary-expression  
     multiplicative-expression % unary-expression  
additive-expression:  
     multiplicative-expression  
     additive-expression + multiplicative-expression  
     additive-expression – multiplicative-expression  
shift-expression:  
     additive-expression  
     shift-expression << additive-expression  
     shift-expression >> additive-expression  
relational-expression:  
     shift-expression  
     relational-expression < shift-expression  
     relational-expression > shift-expression  
     relational-expression <= shift-expression  
     relational-expression >= shift-expression  
equality-expression:  
     relational-expression  
     equality-expression == relational-expression  
     equality-expression != relational-expression  
and-expression:  
     equality-expression  
     and-expression & equality-expression  
exclusive-or-expression:  
     and-expression  
     exclusive-or-expression ^ and-expression  
inclusive-or-expression:  
     exclusive-or-expression  
     inclusive-or-expression | exclusive-or-expression  
conditional-and-expression:  
     inclusive-or-expression  
     conditional-and-expression && inclusive-or-expression  
conditional-or-expression:  
     conditional-and-expression  
     conditional-or-expression || conditional-and-expression  
conditional-expression:  
     conditional-or-expression  
exists-expression:  
     property-reference exists  
     property-reference exists message-reference  
     property-reference exists message-part-reference  
xpath-expression:  
     xpath(message-part-reference, string-expression)  
     xpath(string-expression)  
intrinsic-expression:  
     succeeded(identifier)  
assignment-expression:  
     variable-assignment  
     object-assignment  
variable-assignment:  
     variable-reference = conditional-expression  
object-assignment:  
     object-reference = object-creation-expression  
     object-reference = conditional-expression  
     object-reference = invocation-expression  
object-creation-expression:  
     new class-name(method-argument-list) //method-argument-list is optional  
     new class-name[integer-expression]  
invocation-expression:  
     object-reference.method-name(method-argument-list) //method-argument-list is optional  
```  
  
## <a name="service-and-method-arguments"></a><span data-ttu-id="14cb4-107">服务和方法参数</span><span class="sxs-lookup"><span data-stu-id="14cb4-107">Service and Method Arguments</span></span>  
 <span data-ttu-id="14cb4-108">下面的代码显示了服务和方法参数的语法：</span><span class="sxs-lookup"><span data-stu-id="14cb4-108">The following code shows the syntax for service and method arguments:</span></span>  
  
```  
service-argument-list:  
     service-argument  
     service-argument-list, service-argument  
service-argument:  
     param-direction message-reference //param-direction is optional  
     param-direction variable-reference //param-direction is optional  
     param-direction object-name //param-direction is optional  
     correlation-reference  
     service-link-name  
     port-name  
     conditional-expression  
method-argument-list:  
     method-argument  
     method-argument-list, method-argument  
method-argument:  
     message-reference  
     param-direction variable-reference //param-direction is optional  
     param-direction object-name //param-direction is optional  
     conditional-expression  
     param-direction message-part-reference //param-direction is optional  
     param-direction message-field-reference //param-direction is optional  
```  
  
## <a name="top-level-expressions"></a><span data-ttu-id="14cb4-109">顶级表达式</span><span class="sxs-lookup"><span data-stu-id="14cb4-109">Top-Level Expressions</span></span>  
 <span data-ttu-id="14cb4-110">下面的代码显示了顶级表达式的语法：</span><span class="sxs-lookup"><span data-stu-id="14cb4-110">The following code shows the syntax for top-level expressions:</span></span>  
  
```  
expression:  
     conditional-expression  
     assignment-expression  
     invocation-expression  
constant-expression:  
     conditional-expression  
boolean-expression:  
     conditional-expression  
integer-expression:  
     conditional-expression  
date-time-expression:  
     conditional-expression  
time-span--expression:  
     conditional-expression  
string-expression:  
     conditional-expression  
```  
  
## <a name="see-also"></a><span data-ttu-id="14cb4-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14cb4-111">See Also</span></span>  
 <span data-ttu-id="14cb4-112">[XLANG-s 数据类型](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="14cb4-112">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="14cb4-113">[XLANG-s 语句](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="14cb4-113">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="14cb4-114">[XLANG-s 变量和运算符](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="14cb4-114">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="14cb4-115">[XLANG-s 保留字](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="14cb4-115">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="14cb4-116">XLANG-s 的 BPEL4WS 类型转换</span><span class="sxs-lookup"><span data-stu-id="14cb4-116">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)