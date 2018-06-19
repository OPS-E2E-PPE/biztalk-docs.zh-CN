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
# <a name="xlang-s-to-bpel4ws-type-conversions"></a>XLANG-s 的 BPEL4WS 类型转换
下表详细说明了各种 XLANG/s 构造和 BPEL4WS 构造之间的转换。  
  
> [!CAUTION]
>  XPath 1.1 不支持以指数记数法表示的数字或双精度格式。 XLANG/s 业务流程中使用这些格式的文本值使用 %f 格式导出到 BPEL4WS，因此可能会影响精度。  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a>文本（如果文本是表达式的一部分）  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|字符串、字符|XPath 字符串|  
|整数、实型|XPath 数字|  
|布尔值“true”、“false”|XPath true()、false() 函数|  
  
## <a name="literals-standalone-assignment"></a>文本（单独赋值）  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|文本常数|XSD 等价|  
  
## <a name="variables"></a>变量  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|变量引用|bpws:getContainerData(%varName%,  part, %locationPath%)|  
|消息引用（.NET 类型）|bpws:getContainerData(%msgName%, part, %locationPath%)|  
|消息部分引用|bpws:getContainerData(%msgName%, %locationPath%)|  
|可分辨字段引用|bpws:getContainerData(%msgName%, %partName%, %locationPath%)|  
|消息数据属性引用|bpws:getContainerProperty(%msgName%, %propertyQName%)|  
  
## <a name="operators"></a>运算符  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|Unary +|忽略|  
|一元：-|XPath unary -|  
|Unary !|XPath not() 函数|  
|二进制 & &、 &#124; &#124;|XPath 'and'、'or' 运算符|  
|二进制 = =、 ！ =、 < =、 <>、 =、 >|XPath '='、'! =，< ='，' <'，' > =，> 运算符|  
|使用两个整数操作数的 Binary +、-、*、%|XPath '+'、'-'、'*'、'mod' 运算符|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a>BPEL4WS 中不允许的 XLANG/s 构造  
  
-   消息上下文属性引用  
  
-   服务属性引用  
  
-   端口属性引用  
  
-   服务链接属性引用  
  
-   一元 – 非整数类型  
  
-   Unary ~  
  
-   强制转换运算符  
  
-   Binary，使用整数操作数  
  
-   Binary +、-、*、%，使用非整数操作数  
  
-   二进制 < =、 <>、 =、 > 与非字符串操作数  
  
-   按位运算符 &、 ^，&#124;  
  
-   移位运算符 <<>>，  
  
-   已检查表达式  
  
-   内部表达式  
  
-   前递增、后递增、前递减和后递减 ++、--  
  
-   对象调用（有 out、没有 out 和/或 ref 参数）  
  
-   'new' 运算符