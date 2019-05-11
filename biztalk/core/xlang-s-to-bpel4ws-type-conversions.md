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
# <a name="xlang-s-to-bpel4ws-type-conversions"></a>Xlang-s 到 BPEL4WS 的类型转换
下表详细说明各种 XLANG/s 构造和 BPEL4WS 构造之间的转换。  
  
> [!CAUTION]
>  XPath 1.1 不支持以指数或双精度格式的数字。 XLANG/s 业务流程中使用这些格式中的文本值导出到 BPEL4WS 使用 %f 格式和精度降低可能会导致。  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a>文本 （如果文本表达式的一部分）  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|字符串、 字符|XPath 字符串|  
|整数、 实型|XPath 数字|  
|布尔值"true"、"false"|XPath true （)、 false （） 函数|  
  
## <a name="literals-standalone-assignment"></a>文本 （单独赋值）  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|文本常量|XSD 等价|  
  
## <a name="variables"></a>变量  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|变量引用|bpws:getContainerData(%varName%, part, %locationPath%)|  
|消息参考 （.NET 类型）|bpws:getContainerData(%msgName%, part, %locationPath%)|  
|消息部分引用|bpws:getContainerData(%msgName%, %locationPath%)|  
|可分辨字段引用|bpws:getContainerData(%msgName%, %partName%, %locationPath%)|  
|消息数据属性引用|bpws:getContainerProperty(%msgName%, %propertyQName%)|  
  
## <a name="operators"></a>运算符  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|一元 +|忽略|  
|一元-|XPath 一元-|  
|一元 ！|XPath not （） 函数|  
|二进制 & &、&#124;&#124;|XPath 'and'、 'or' 运算符|  
|二进制 = =、 ！ =、 < =、 <>、 =、 >|XPath =、 ！ =，< ='，' <'，' > =，> 运算符|  
|二进制 +、-、 *、 %使用这两个整数操作数|XPath '+'、 '-'，' *'，'mod' 运算符|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a>BPEL4WS 中不允许的 XLANG/s 构造  
  
-   消息上下文属性引用  
  
-   服务属性引用  
  
-   端口属性引用  
  
-   服务链接属性引用  
  
-   一元 – 非整数类型  
  
-   一元 ~  
  
-   强制转换运算符  
  
-   二进制使用整数操作数  
  
-   二进制 +、-、 *、 %、 使用非整数操作数  
  
-   二进制 < =、 <>、 =、 > 使用非字符串操作数  
  
-   按位运算符 &，^，&#124;  
  
-   移位运算符 <<>>、  
  
-   已检查的表达式  
  
-   内部函数的表达式  
  
-   预处理脚本和后续递增和递减 + +、-  
  
-   对象调用 (与我们无需扩展和/或 ref 参数)  
  
-   'new' 运算符