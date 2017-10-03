---
title: "在表达式中使用运算符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 155aad11ecddd021b8e16892b5a5294087fedd4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-operators-in-expressions"></a>在表达式中使用运算符
以下 XLANG/s 运算符可用于业务流程表达式。 这些运算符与 C# 中相应运算符的功能基本一致。  
  
|运算符|Description|示例|  
|--------------|-----------------|-------------|  
|checked()|在算术溢出时引发错误|检查 (x = y * 1000年)|  
|unchecked()|忽略算术溢出|未选中状态 (x = y * 1000年)|  
|新|创建类的实例|myObject = 新 MyClass;|  
|typeof|类型检索|myMapType = typeof(myMap)|  
|succeeded()|测试事务作用域或业务流程是否已经成功完成|成功 (\<子事务的当前作用域或服务的事务 ID >)|  
|存在|测试是否存在某个消息上下文属性|BTS。RetryCount 存在 Message_In|  
|+|一元加|+(int x)|  
|-|一元减|-(int x)|  
|!|逻辑求反|！ myBool|  
|~|按位求补|x = ~ y|  
|()|强制转换|(bool) myInt|  
|*|times|权重 = MyMsg.numOrders * 20|  
|/|除以|x / y|  
|+|加|x + y|  
|-|减号|x-y|  
|<<|左移|x <\< 2|  
|>>|右移|x >> 2|  
|<|小于|如果 (MyMsg.numOrders \< 10)...|  
|>|大于|如果 (MyMsg.numOrders > 10)...|  
|<=|小于或等于|如果 (MyMsg.numOrders \<= 10)...|  
|>=|大于或等于|如果 (MyMsg.numOrders > = 10)...|  
|==|等于|如果 (MyMsg.numOrders = = 10)...|  
|!=|不等于|如果 (MyMsg.numOrders ！ = 10)...|  
|&|和|如果 (myByte 和 255)...|  
|^|异或|If (myByte ^ 1)...|  
|&#124;|或|如果 (myByte &#124; 1)...|  
|&&|条件与|如果 (MyMsg.numOrders > 10) （& a) （& a) (MyMsg.numOrders < 100)|  
|&#124;&#124;|条件或|如果 (MyMsg.numOrders \< 10) &#124; &#124;(MyMsg.numOrders > 100)|  
|//|注释|//This is the comment|  
  
> [!NOTE]
>  常规表达式和一起使用的筛选器表达式之间有所不同，规则**接收**形状。  
  
## <a name="see-also"></a>另请参阅  
 [使用接收消息形状使用筛选器](../core/using-filters-with-the-receive-message-shape.md)