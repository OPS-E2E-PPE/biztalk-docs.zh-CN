---
title: 议程和优先级 |Microsoft Docs
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
ms.openlocfilehash: 85274b0cbd59cd9272bb63030296d3f527e096a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360419"
---
# <a name="agenda-and-priority"></a>议程和优先级
若要了解如何在业务规则引擎计算规则，并执行操作，您需要了解的概念*议程*并*优先级*。  
  
## <a name="agenda"></a>议程  
 议程是引擎对队列规则执行时使用的计划。 议程用于引擎实例，存在且作用于单个策略而不是上一系列的策略。 如果事实添加到工作内存中时，满足给定规则的条件规则放置在议程，并根据优先级执行。 从上到下的顺序执行规则的操作，然后执行议程的下一个规则的操作。  
  
 属于某一规则的操作被视为一个块，以便在前进到下一规则之前执行所有操作。 无论在块中的其他操作将执行规则模块中的所有操作。 有关断言的详细信息，请参阅[引擎控制功能](../core/engine-control-functions.md)。  
  
 下面的示例演示了议程的工作原理。  
  
 **Rule1**  
  
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
  
 我们断言事实 Fact1，具有值为 1，到引擎中。 因为满足规则 1 和规则 2 的条件时，这两个规则都执行其操作移至议程。  
  
|工作内存|议程|  
|--------------------|------------|  
|Fact1 (value=1)|**Rule1**<br /><br /> -   Action1<br />-   Action2<br /><br /> **Rule2**<br /><br /> -   Action3<br />-   Action4|  
  
## <a name="priority"></a>Priority  
 执行优先级设置每个规则的默认优先级为 0 表示所有规则。 优先级为 0，或小于范围更大的数字越大优先级越高。 从最高优先级到最低优先级的顺序执行操作。  
  
 下面的示例显示了优先级如何影响规则的执行顺序。  
  
 **Rule1 (优先级 = 0)**  
  
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
  
 这两个规则的条件均已满足，但首先执行 Rule2，因为它具有更高的优先级。 最终折扣为 10%，因为它是对 Rule1 执行操作的结果下, 表中所示。  
  
|工作内存|议程|  
|--------------------|------------|  
|Fact1 (value=1)|**Rule2**<br /><br /> 折扣 = 15%<br /><br /> **Rule1**<br /><br /> 折扣 = 10%|  
  
## <a name="see-also"></a>请参阅  
 [规则引擎](../core/rule-engine.md)