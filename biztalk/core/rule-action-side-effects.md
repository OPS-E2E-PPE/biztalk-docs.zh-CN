---
title: 规则操作副作用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, side effects
ms.assetid: 1ef65014-9c0a-40d3-b941-2a67c20b54d3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cfcff7fed8a559c725d0180f89cdd0d385b1e0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254614"
---
# <a name="rule-action-side-effects"></a>规则操作副作用
如果执行某个操作影响的一个或多个条件中所使用的术语的状态，该操作被视为对象上具有负面影响。  
  
 假设我们有以下规则。  
  
## <a name="rule-1"></a>规则 1  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a>规则 2  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 在这种情况下， **OrderForm.UpdateStatus**称为具有副作用**OrderForm.Status**。 这并不意味着**OrderForm.UpdateStatus**具有副作用，而是， **OrderForm.Status**可能受到一个或多个操作。  
  
 默认情况下**SideEffects**属性为.NET 类成员**true**，这样可以防止规则引擎缓存具有副作用的成员。 在本示例中，规则引擎不会缓存**OrderForm.Status**中的工作内存中; 而是它获取最新的值**OrderForm.Status**每次计算规则 1。 如果**SideEffects**属性设置为**false**，规则引擎缓存的值计算结果的第一次**OrderForm.Status**，但对于更高版本的评估 （在正向链接方案），它使用缓存的值。  
  
 当前业务规则编辑器不提供使用户能够修改地**SideEffects**，但是，您可以只设置**SideEffects**通过业务规则框架以编程方式的属性. 您设置执行在此操作使用的绑定[ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx)类，以指定对象的方法、 属性和字段规则条件和操作中使用。 **ClassMemberBinding**有一个属性， [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects)，其中包含一个布尔值，该值指示是否将访问该成员更改其值。  
  
## <a name="see-also"></a>请参阅  
 [规则引擎](../core/rule-engine.md)