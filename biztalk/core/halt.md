---
title: Halt | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc7006581b3ccbf856d48d365cf6b003d97ec93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344790"
---
# <a name="halt"></a>暂停
可以使用**暂停**函数停止当前规则引擎执行。 **暂停**函数采用一个参数类型的`Boolean`。 如果指定为参数的值为`true`，规则引擎还会清除包含挂起的候选规则的议程。  
  
 **Policy.Execute**方法基本上是周围的包装**RuleEngine.Execute**方法。 它具有类似于下面的代码的代码：  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 如果您使用**Policy.Execute**方法以执行策略，规则引擎将控制权返回给**Policy.Execute**方法时**暂停**执行函数。 **Policy.Execute**方法取消事实并将控制权返回给调用方。 因此，不能在这种情况下恢复已停止的策略执行。 当你使用时，会发生相同的操作**调用规则**形状来调用该策略。  
  
 但是，如果您使用**RuleEngine.Execute**方法以执行策略，可以继续下一个挂起的规则触发已停止的策略执行只需调用直接**RuleEngine.Execute**再次 （只要没有取消两个调用之间所需的任何对象）。 恢复已停止的策略执行的示例代码如下所示：  
  
```  
//assert facts into working memory of the rule engine instance  
RuleEngine.Assert(facts);   
//execute the policy  
RuleEngine.Execute();   
//policy invokes the Halt method when executing actions.   
//control is returned to here when the Halt method is invoked  
  
//when engine is halted do the following  
//Add your code here  
  
//To resume the halted rule engine execution  
RuleEngine.Execute();  
//retract or remove facts frm the working memory of the rule engine  
RuleEngine.Retract(facts);  
```  
  
 请注意， **Policy.Execute**方法将缓存规则引擎实例，以更好的性能。 当你使用**RuleEngine.Execute**直接方法时，规则引擎实例不会被缓存。  
  
## <a name="see-also"></a>请参阅  
 [引擎控制函数](../core/engine-control-functions.md)