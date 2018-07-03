---
title: 条件评估和执行操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Action stage [Business Rules Engine]
- examples, business rules
- Business Rules Engine, policies
- Match stage [Business Rules Engine]
- business rules, examples
- Business Rules Engine, algorithm
- Business Rules Engine, examples
- conflict resolution [Business Rules Engine]
- Business Rules Engine, stages
ms.assetid: dcaa32c2-3403-4f54-92e2-128686bfc193
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30d4f17fce34f72eed85ca49ecab09a81ce56681
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997222"
---
# <a name="condition-evaluation-and-action-execution"></a>条件评估和操作执行
业务规则框架提供了高效的推理引擎，可以将规则链接到 .NET 对象、XML 文档或数据库表。  
  
 业务规则引擎对策略执行使用了三阶段算法。 这些阶段包括：  
  
- **匹配**。 在匹配阶段，将使用在规则条件中定义的谓词，根据使用事实类型（在规则引擎的工作内存中维护的对象引用）的谓词来匹配事实。 由于效率的原因，策略中的所有规则会进行模式匹配，而规则共享的条件则只匹配一次。 部分条件匹配可能存储在工作内存中，以加快随后的模式匹配操作。 模式匹配阶段的输出由对规则引擎议程的更新组成。  
  
- **冲突解决**。 在冲突解决阶段，将检查作为执行候选的规则，以根据预设的解决方案来确定要执行的下一组规则操作。 在匹配阶段找到的所有候选规则都会添加到规则引擎的议程中。  
  
   默认冲突解决方案基于策略中的规则优先级。 优先级是业务规则编辑器中可配置的规则属性。 该数字越大，优先级越高；因此，如果触发多个规则，则首先执行优先级较高的操作。  
  
- **操作**。 在操作阶段，将执行已解析规则中的操作。 请注意，规则操作可以在规则引擎中添加新的事实，这将导致循环继续。 这也称为正向链接。 请注意，算法永远不会抢先于当前正在执行的规则。 在重复匹配阶段之前，将执行当前触发的规则的所有操作。 但是，再次开始匹配阶段之前，将不会触发议程的其他规则。 匹配阶段可能导致在触发议程的这些规则之前，从议程中删除这些规则。  
  
  以下示例显示了匹配 - 冲突解决 - 操作的三阶段算法：  
  
  **规则 1： 评估收入**  
  
- 声明性表示：  
  
   只有当申请人的收入与贷款比率小于 0.2 时，才应获取申请人的信用等级。  
  
- 使用业务对象的 IF-THEN 表示:  
  
  ```  
  IF Application.Income / Property.Price < 0.2    
  THEN Assert new CreditRating( Application)   
  ```  
  
  **规则 2： 评估信用等级**  
  
- 声明性表示：  
  
   只有当申请人的信用等级超过 725 时，才应批准申请人。  
  
- 如果 — 然后使用业务对象的表示形式：  
  
  ```  
  IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
  THEN SendApprovalLetter(Application)    
  ```  
  
  下表概括列出了事实：  
  
|事实|字段|  
|----------|------------|  
|申请 – XML 文档，表示房屋贷款申请|-收入 = $65000<br />-SSN = XXX XX XXXX|  
|房产 – XML 文档，表示购买的房产|-Price = $225,000|  
|信用等级 – XML 文档，包含贷款申请人的信用等级|的值 = 0-800<br />-SSN = XXX XX XXXX|  
  
 规则引擎工作内存和议程最初为空。 应用程序添加“申请”和“房产”事实之后，将按如下所示更新规则引擎工作内存和议程：  
  
|工作内存|议程|  
|--------------------|------------|  
|应用程序<br />-属性|规则 1|  
  
 规则 1 添加到议程，因为其条件 (Application.Income / Property.Price < 0.2) 的计算结果为 **，则返回 true**在匹配阶段。 工作内存中没有“信用等级”事实，因此不计算规则 2 的条件。 由于议程中的唯一规则是规则 1，因此该规则将被执行，然后从议程中消失。 为规则 1 定义的单个操作将导致新的事实（申请人的信用等级文档）添加到工作内存中。 执行完规则 1 之后，控制返回到匹配阶段。 由于要匹配的唯一新对象是“信用等级”事实，因此匹配阶段的结果如下所示：  
  
|工作内存|议程|  
|--------------------|------------|  
|应用程序<br />-属性<br />的信用等级|规则 2|  
  
 此时，将执行规则 2，导致调用向申请人发送批准信件的函数。 完成规则 2 之后，执行正向链接算法将返回到匹配阶段。 由于不再有新的事实要匹配并且议程为空，将终止正向链接，完成策略执行。  
  
## <a name="see-also"></a>请参阅  
 [规则引擎](../core/rule-engine.md)