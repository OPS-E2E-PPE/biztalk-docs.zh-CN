---
title: "XLANG-s 变量和运算符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c1773b7af3ec029026ee884e6c1161e27a3c330
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="xlang-s-variables-and-operators"></a>XLANG-s 变量和运算符
本部分讨论的变量和 XLANG/s 语言中使用的运算符。  
  
## <a name="xlangs-variables"></a>XLANG/s 变量  
 变量表示存储位置。 每个变量具有类型，用于确定值可以是存储在该变量中。 XLANG/秒是类型安全和相应的编译器可确保存储在变量中的值始终是适当类型。 XLANG/s 支持以下变量类型：  
  
-   消息  
  
-   关联集  
  
-   服务链接  
  
-   端口  
  
-   可分辨内置值类型：**布尔**，**字节**， **Char**，**十进制**， **Double**， **Int16**， **Int32**， **Int64**， **SByte**，**单个**，**字符串**，**UInt16**， **UInt32**，和**UInt64**  
  
-   对象  
  
-   枚举类型  
  
 XLANG/s 提供了每个上述类型初始化语义。 此类初始化可以查看为该类型的向变量赋值。 在 XLANG/s，必须明确地分配变量然后可以获取或使用其值。  
  
## <a name="xlangs-operators"></a>XLANG/s 运算符  
 XLANG/s 支持以下运算符。 这些运算符与 C# 中相应运算符的功能基本一致。  
  
|运算符|Description|示例|  
|--------------|-----------------|-------------|  
|已选中|引发算术溢出错误|检查 (x = y * 1000年)|  
|unchecked|将忽略算术溢出|未选中状态 (x = y * 1000年)|  
|新|创建类的实例|myObject = 新 MyClass;|  
|typeof|检索类型|myMapType = typeof(myMap)|  
|succeeded|测试成功完成事务的作用域或业务流程|成功 (\<子事务的当前作用域或服务的事务 ID\>)|  
|存在|测试存在消息上下文属性|BTS。RetryCount 存在 Message_In|  
|+|一元加|+(int x)|  
|-|一元负|-(int x)|  
|!|逻辑求反|！ myBool|  
|~|按位求补|x = ~ y|  
|()|强制转换|(bool) myInt|  
|*|时间|权重 = MyMsg.numOrders * 20|  
|/|除以|x / y|  
|+|加号|x + y|  
|-|减号|x-y|  
|<<|右侧左移|x << 2|  
|>>|右移|x >> 2|  
|<|小于|如果 (MyMsg.numOrders < 10)...|  
|>|大于|如果 (MyMsg.numOrders > 10)...|  
|<=|小于或等于|如果 (MyMsg.numOrders < = 10)...|  
|>=|大于或等于|如果 (MyMsg.numOrders > = 10)...|  
|==|等于|如果 (MyMsg.numOrders = = 10)...|  
|!=|不等于|如果 (MyMsg.numOrders ！ = 10)...|  
  
## <a name="see-also"></a>另请参阅  
 [XLANG-s 数据类型](../core/xlang-s-data-types.md)   
 [XLANG-s 语句](../core/xlang-s-statements.md)   
 [XLANG-s 表达式](../core/xlang-s-expressions.md)   
 [XLANG-s 保留字](../core/xlang-s-reserved-words.md)   
 [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)