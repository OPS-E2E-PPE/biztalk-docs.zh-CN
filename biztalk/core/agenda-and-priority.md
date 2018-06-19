---
title: 安排和优先级 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, executing
- Business Rules Engine, agendas
- Business Rules Engine, priorities
- business rules, priorities
- business rules, examples
- Business Rules Engine, examples
- examples, Business Rules Engine
- Business Rules Engine, rules
ms.assetid: ca54f750-4f2d-4734-8e6e-7af1b4967e6a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4529753251c2bf7934616b91662bde836c8339e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230205"
---
# <a name="agenda-and-priority"></a>议程和优先级
若要了解业务规则引擎如何计算规则并执行操作，你需要了解的概念*安排*和*优先级*。  
  
## <a name="agenda"></a>议程  
 议程是引擎对要执行的规则进行排队时使用的计划。 议程用于引擎实例，它对单个策略而不是一系列策略起作用。 将事实添加到工作内存中并且满足给定规则的条件时，该规则将被放置在议程上并根据优先级执行。 从上至下按顺序执行规则的操作，然后执行议程中下一个规则的操作。  
  
 属于某一规则的操作被视为一个模块，这样，在继续到下一个规则之前将执行该规则的所有操作。 将执行规则模块中的所有操作，而不管模块中的其他操作。 有关断言的详细信息，请参阅[引擎控制功能](../core/engine-control-functions.md)。  
  
 以下示例说明议程是如何工作的：  
  
 **规则 1**  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 **Rule2**  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 我们将值为 1 的事实 Fact1 添加到引擎中。 由于 Rule1 和 Rule2 的条件都得到了满足，因此两个规则都移至议程，以便执行它们的操作。  
  
|工作内存|议程|  
|--------------------|------------|  
|Fact1（值=1）|**规则 1**<br /><br /> -Action1<br />-Action2<br /><br /> **Rule2**<br /><br /> -Action3<br />-Action4|  
  
## <a name="priority"></a>Priority  
 每个规则都设置了执行优先级，所有规则的默认优先级为 0。 优先级可以大于、等于或小于 0，数字越大优先级越高。 操作按照从最高优先级到最低优先级的顺序执行。  
  
 以下示例说明优先级如何影响规则的执行顺序：  
  
 **规则 1 (优先级 = 0)**  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 **Rule2 (优先级 = 10)**  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 两条规则的条件都已得到满足，但首先执行 Rule2，因为它具有更高的优先级。 最终折扣为 10%，因为它是对 Rule1 执行操作的结果，如下表所示：  
  
|工作内存|议程|  
|--------------------|------------|  
|Fact1（值=1）|**Rule2**<br /><br /> 折扣 = 15%<br /><br /> **规则 1**<br /><br /> 折扣 = 10%|  
  
## <a name="see-also"></a>另请参阅  
 [规则引擎](../core/rule-engine.md)