---
title: 如何分析的业务规则中的相同类型的多个对象 |Microsoft 文档
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
ms.openlocfilehash: 2a1e4d2fb01513b1d4d314264ab74b84d3a0223a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248429"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a>如何分析的业务规则中的相同类型的多个对象
在许多情况下，您会根据某个类型编写业务规则，希望单独分析添加到引擎的该类型的每个实例，并按规则对每个实例进行操作。 然而，在某些情况下，您可能希望使用一个规则同时分析给定类型的多个实例。  
  
 例如采用规则使用的实例的**FamilyMember**类。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 该规则标识**FamilyMember**实例，它是**父亲**和另一个实例即**子**。 如果实例相关的姓氏，**子**实例添加到父亲实例上的子级的集合。 如果每个**FamilyMember**实例已单独分析规则中，规则将在永远不会触发的因为在此方案中， **FamilyMember**只有一个角色-**父亲**或**子**。  
  
 因此，必须向引擎指示应使用该规则同时分析多个实例，并需要在规则中区分每个实例标识的方法。 **实例 ID**使用属性来提供此功能。 在事实浏览器中选择事实后，即可在“属性”窗口中使用此字段。 您应在将事实或成员拖入规则中之前更改此字段的值。  
  
 使用**实例 ID**属性，将重新生成规则。 为使用这些规则参数**子**实例**FamilyMember**、**实例 ID**字段更改默认值为 0 到 1。 当从 0 更改实例 ID，并且该事实或成员拖放到规则编辑器时，实例 ID 的值将显示在规则后类。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 现在，假定**父亲**实例和一个**子**实例断言引擎。 引擎将根据这些实例的不同组合来评估规则。 假设**父亲**和**子**实例具有相同的姓氏，**子**实例将添加到**父亲**实例作为适用。  
  
> [!NOTE]
>  **实例 ID**仅在给定的规则评估的上下文中使用。 “实例 ID”不会在执行策略时附加到对象实例，并且与对象的添加顺序无关。 每个对象实例均将使用该类型的所有规则参数进行评估。