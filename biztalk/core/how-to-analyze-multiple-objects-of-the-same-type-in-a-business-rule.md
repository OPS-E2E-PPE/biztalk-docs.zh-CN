---
title: 如何分析的业务规则中的相同类型的多个对象 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1060de077a8b526db6c226786b23781da1f7421
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342941"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a>如何分析的业务规则中的相同类型的多个对象
在许多情况下，将编写针对一种类型的业务规则，并希望每个实例添加到引擎单独分析和处理规则的类型。 但是，在某些情况下，会要分析的同时在规则中的给定类型的多个实例。  
  
 如需要使用的实例的规则**FamilyMember**类。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 该规则标识**FamilyMember**实例的数据类型**父亲**和的另一个实例**儿子**。 如果按姓氏，相关实例**Son**实例添加到 Father 实例的子对象集合。 如果每个**FamilyMember**规则单独分析实例中，该规则永远不会触发，因为在此方案中， **FamilyMember**只有一个角色 —**父亲**或**Son**。  
  
 因此，在规则中，应同时分析多个实例，并需要一种方法，以区分规则中的每个实例的标识，您必须向引擎指示。 **实例 ID**属性用于提供此功能。 此字段是可在属性窗口中时在事实浏览器中选择一个事实。 应更改之前将事实或成员拖到规则中字段的值。  
  
 使用**实例 ID**属性，可重新生成规则。 使用这些规则参数**Son**的实例**FamilyMember**，则**实例 ID**字段更改从默认值为 0 到 1。 当从 0 更改实例 ID 和该事实或成员拖入规则编辑器时，实例 ID 的值将显示在规则中类进行仿造。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 现在，假设**父亲**实例和一个**儿子**实例添加到引擎。 该引擎将评估规则所依据的实例的各种组合。 假设**父亲**并**儿子**实例具有相同姓氏**儿子**实例将添加到**父亲**实例作为适用。  
  
> [!NOTE]
>  **实例 ID**只能在给定的规则评估的上下文中使用。 它在执行策略未附加到对象实例，并与对象的添加的顺序无关。 将该类型的所有规则参数中计算每个对象实例。