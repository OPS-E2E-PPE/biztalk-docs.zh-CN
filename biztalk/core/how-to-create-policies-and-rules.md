---
title: "如何创建策略和规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, business rules
- policies, rules
- policies, predicates
- business rules, creating
- creating, policies
- policies, logical operators
- policies, examples
- policies, default actions
- policies
- policies, arguments
- policies, creating
ms.assetid: 59f06a67-edde-443b-9fbb-55ec4429837a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52fb3d835b39a4059fc7a4a1644d7653257ea3dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-policies-and-rules"></a>如何创建策略和规则
你可以使用是逻辑运算符的逻辑分组的条件创建规则 (**AND**， **OR**，和**不**) 应用于谓词 （内置或用户定义函数或运算符），采用自变量 （内置或用户定义的事实引用）。 你还可以右键单击**条件**或逻辑运算符，然后从上下文菜单中选择的逻辑运算符或内置的谓词。  
  
 你可以定义操作 （内置或用户定义函数） 时的规则条件的计算结果为要执行**true**。  
  
> [!NOTE]
>  如果规则中包括多个谓词，所有谓词必须都显示为一个逻辑运算符的自变量。 （顶层可以为单个 .NET 成员、db 列或布尔类型的 XML 字段/属性。）  
  
### <a name="to-create-a-policy"></a>创建策略  
  
1.  在策略资源管理器窗格中，右键单击**策略**，然后单击**添加新策略**。  
  
     一个新文件夹中，**策略 1**下, 创建**策略**。 默认情况下，为你创建新策略的版本 1。  
  
2.  单击**策略 1**。  
  
3.  在名称属性窗格中，键入的名称。  
  
### <a name="to-add-a-rule-to-a-policy-version"></a>若要将规则添加到策略版本  
  
-   在策略资源管理器窗格中，展开 [**你的策略**]，右键单击**（不保存） 1.0 版**，然后选择**添加新规则**。  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a>若要将一个逻辑运算符添加到规则条件  
  
-   在规则定义窗口中，右键单击**条件**，然后单击其中一个**添加逻辑和**，**添加逻辑或**，或**添加逻辑不**.  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a>若要将内置谓词添加到规则条件或逻辑运算符  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡上，并依次**谓词**文件夹。  
  
2.  展开发布的版本的谓词的词汇，并单击所需的谓词。  
  
3.  将该谓词，拖到逻辑运算符，或**条件**如果你的规则将包含只有一个谓词。  
  
    > [!NOTE]
    >  你还可以添加谓词直接从数据源，前提是数据元素充当一个谓词 (计算结果为**true**或**false**)。  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a>将内置操作添加到规则  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡上，并依次**函数**文件夹。  
  
2.  展开的函数词汇，发布的版本并单击所需的函数。  
  
3.  将函数拖放到**操作**。 你还可以右键单击**操作**，然后从上下文菜单中选择内置操作。  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a>若要将参数添加到条件或操作  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡上，并依次词汇文件夹。  
  
2.  展开词汇的已发布版本，并单击所需的术语。 该术语必须属于谓词或功能所要求的类型。  
  
3.  将该术语拖至条件中的谓词参数上，或拖至操作中的函数参数上。  
  
    > [!NOTE]
    >  还可以直接从数据源中添加参数，或者，如果要添加 XML 参数，也可以在选择字段时在属性中指定字段类型；当然，如果数据元素属于谓词或操作所要求的类型，则该元素必须与数据本身兼容。 若要直接从数据源添加参数，单击事实浏览器窗口中相应的选项卡，导航到所需的项并将其拖到谓词自变量或函数参数。  
  
    > [!NOTE]
    >  通过单击参数并输入所需的常数值，可以直接向参数添加常数值。