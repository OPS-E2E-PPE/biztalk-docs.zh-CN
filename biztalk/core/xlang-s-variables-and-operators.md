---
title: Xlang-s 变量和运算符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eace5d4a30f8cac80403143a5dc3cfb887c0bc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246438"
---
# <a name="xlang-s-variables-and-operators"></a>Xlang-s 变量和运算符
本部分讨论的变量和运算符在 XLANG/s 语言中使用。  
  
## <a name="xlangs-variables"></a>XLANG/s 变量  
 变量表示存储位置。 每个变量具有类型，用于确定值可以是存储在该变量中。 XLANG/s 是类型安全和相应的编译器可确保存储在变量中的值始终是适当的类型。 XLANG/s 支持以下变量类型：  
  
- 消息  
  
- 相关集  
  
- 服务链接  
  
- 端口  
  
- 可分辨内置值类型：**布尔**，**字节**， **Char**，**十进制**， **Double**， **Int16**， **Int32**， **Int64**， **SByte**，**单个**，**字符串**， **UInt16**， **UInt32**，并**UInt64**  
  
- 对象  
  
- 枚举类型  
  
  XLANG/s 为上述类型的每个提供初始化语义。 此类初始化可以查看为该类型的向变量赋值。 在 XLANG/s，必须明确赋值变量之前可以获取或使用它的值。  
  
## <a name="xlangs-operators"></a>XLANG/s 运算符  
 XLANG/s 支持以下运算符。 它们紧密遵循 C# 中的相应运算符的功能。  
  
|运算符|Description|示例|  
|--------------|-----------------|-------------|  
|已选中|在算术溢出将引发错误|checked(x = y * 1000)|  
|unchecked|忽略算术溢出|unchecked(x = y * 1000)|  
|新|创建一个类的实例|匹配大小写 = 新 MyClass;|  
|typeof|检索的类型|myMapType = typeof(myMap)|  
|succeeded|测试成功完成的事务作用域或业务流程|已成功 (\<的子事务的当前作用域或服务的事务 ID\>)|  
|存在|测试存在的消息上下文属性|BTS。RetryCount 存在 Message_In|  
|+|一元加|+(int x)|  
|-|一元负|-(int x)|  
|!|逻辑求反|!myBool|  
|~|按位求补|x = ~y|  
|()|强制转换|(bool) myInt|  
|*|时间|Weight = MyMsg.numOrders * 20|  
|/|除以|x / y|  
|+|Plus|x + y|  
|-|减号|x - y|  
|<<|左移|x << 2|  
|>>|右移|x >> 2|  
|<|小于|如果 (MyMsg.numOrders < 10)...|  
|>|大于|如果 (MyMsg.numOrders > 10)...|  
|<=|小于或等于|如果 (MyMsg.numOrders < = 10)...|  
|>=|大于或等于|If (MyMsg.numOrders >= 10)...|  
|==|等于|If (MyMsg.numOrders == 10)...|  
|!=|不等于|If (MyMsg.numOrders != 10)...|  
  
## <a name="see-also"></a>请参阅  
 [Xlang-s 数据类型](../core/xlang-s-data-types.md)   
 [Xlang-s 语句](../core/xlang-s-statements.md)   
 [Xlang-s 表达式](../core/xlang-s-expressions.md)   
 [Xlang-s 保留字](../core/xlang-s-reserved-words.md)   
 [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)