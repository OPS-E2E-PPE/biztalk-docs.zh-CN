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
ms.openlocfilehash: c3d971f805ab546bd758166429bdca47e5073a72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356494"
---
# <a name="condition-evaluation-and-action-execution"></a>条件评估和操作执行
业务规则框架提供了高效的推理引擎，能够将规则链接到.NET 对象、 XML 文档或数据库表。  
  
 业务规则引擎策略执行的使用三阶段算法。 这些阶段如下所示：  
  
- **匹配**。 在匹配阶段中，针对使用的事实类型 （规则引擎工作内存中维护的对象引用） 的谓词匹配事实使用规则条件中定义的谓词。 为了实现效率，会在策略中的所有规则进行模式匹配和在规则之间共享的条件匹配仅一次。 部分条件匹配可能存储在工作内存，以加快后续模式匹配操作。 模式匹配阶段的输出包含到规则引擎议程更新。  
  
- **冲突解决**。 在冲突解决阶段，检查作为执行候选的规则来确定规则操作执行下一组基于预设的解决方案。 在匹配阶段找到的所有候选规则都添加到规则引擎议程中。  
  
   默认冲突解决架构根据策略中的规则优先级。 优先级是规则的业务规则编辑器中的可配置属性。 数字越大，优先级越高;因此如果触发了多个规则，优先级较高的操作首先执行。  
  
- **操作**。 在操作阶段中，执行了解析规则中的操作。 请注意，规则操作可以添加到规则引擎，这将导致循环继续的新的事实。 这是也称为正向链接。 请务必注意，算法永远不会抢先于当前正在执行的规则。 在重复匹配阶段之前，将执行当前触发的规则的所有操作。 但是，再次开始匹配阶段之前也不会触发议程的其他规则。 匹配阶段可能导致议程要触发议程之前从议程中删除这些规则。  
  
  下面的示例显示了匹配-冲突解决-操作的三阶段算法。  
  
  **规则 1:评估收入**  
  
- 声明性表示形式：  
  
   仅当申请人的收入与贷款比率小于 0.2，应获取申请人的信用等级。  
  
- 如果 — 然后使用业务对象的表示形式：  
  
  ```  
  IF Application.Income / Property.Price < 0.2    
  THEN Assert new CreditRating( Application)   
  ```  
  
  **规则 2:评估信用等级**  
  
- 声明性表示形式：  
  
   仅当申请人的信用等级超过 725 应批准申请人。  
  
- 如果 — 然后使用业务对象的表示形式：  
  
  ```  
  IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
  THEN SendApprovalLetter(Application)    
  ```  
  
  下表总结了事实数据。  
  
|事实|字段|  
|----------|------------|  
|应用程序 – XML 文档，表示房屋贷款申请|-收入 = $65000<br />-   SSN = XXX-XX-XXXX|  
|属性 – XML 文档，表示购买的房产|-Price = $225,000|  
|信用等级 – XML 文档包含贷款申请人的信用等级|的值 = 0-800<br />-   SSN = XXX-XX-XXXX|  
  
 规则引擎工作内存和议程最初是空的。 应用程序添加的应用程序和属性的事实数据后，规则引擎工作内存和议程更新，如下所示。  
  
|工作内存|议程|  
|--------------------|------------|  
|-   Application<br />-属性|规则 1|  
  
 规则 1 添加到议程，因为其条件 (Application.Income / Property.Price < 0.2) 的计算结果为 **，则返回 true**在匹配阶段。 有工作内存中是没有信用等级事实，因此不计算规则 2 的条件。 由于议程中的唯一规则是规则 1，此规则执行，并从议程中然后消失。 为规则 1 会导致新的事实 （申请人的信用等级文档） 定义的单个操作添加到工作内存中。 规则 1 在执行完成后，控件返回到匹配阶段。 要匹配的唯一新对象是信用等级这一事实，因为在匹配阶段的结果如下所示。  
  
|工作内存|议程|  
|--------------------|------------|  
|-   Application<br />-属性<br />的信用等级|规则 2|  
  
 此时将执行规则 2，从而导致调用向申请人发送批准信件的函数。 完成规则 2 之后，执行正向链接算法将返回到匹配阶段。 由于不再有新的事实要匹配并且议程为空，则终止正向链接，策略执行已完成。  
  
## <a name="see-also"></a>请参阅  
 [规则引擎](../core/rule-engine.md)