---
title: 在表达式中使用运算符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acb471fd12ad41776b116b1ed2f27fcfb6ea6f8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395428"
---
# <a name="using-operators-in-expressions"></a>在表达式中使用运算符
以下 XLANG/s 运算符是可在业务流程表达式中使用。 它们紧密遵循 C# 中的相应运算符的功能。  
  
|运算符|Description|示例|  
|--------------|-----------------|-------------|  
|checked()|引发在算术溢出错误|checked(x = y * 1000)|  
|unchecked()|忽略算术溢出|unchecked(x = y * 1000)|  
|新|创建一个类的实例|匹配大小写 = 新 MyClass;|  
|typeof|类型检索|myMapType = typeof(myMap)|  
|succeeded （)|测试成功完成的事务作用域或业务流程|已成功 (\<的子事务的当前作用域或服务的事务 ID\>)|  
|存在|测试存在的消息上下文属性|BTS。RetryCount 存在 Message_In|  
|+|一元加|+(int x)|  
|-|一元负|-(int x)|  
|!|逻辑求反|!myBool|  
|~|按位求补|x = ~y|  
|()|强制转换|(bool) myInt|  
|*|times|Weight = MyMsg.numOrders * 20|  
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
|&|和|如果 (myByte 和 255)...|  
|^|异或|如果 (myByte ^1)...|  
|&#124;|或|If (myByte &#124; 1)...|  
|&&|条件和|如果 (MyMsg.numOrders > 10) & & (MyMsg.numOrders < 100)|  
|&#124;&#124;|条件或|If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)|  
|//|注释|这是注释|  
  
> [!NOTE]
>  常规表达式和与一起使用的筛选器表达式的规则有所不同**接收**形状。  
  
## <a name="see-also"></a>请参阅  
 [使用带接收消息形状的筛选器](../core/using-filters-with-the-receive-message-shape.md)