---
title: 如何创建策略和规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57fa00774f1c27b6a3de323369c3d260851ecade
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385467"
---
# <a name="how-to-create-policies-and-rules"></a>如何创建策略和规则
使用逻辑运算符的逻辑分组的条件创建规则 (**AND**， **OR**，并**不**) 应用于谓词 （内置或用户定义函数或运算符） 的采用自变量 （内置或用户定义的事实引用）。 此外可以右键单击**条件**或逻辑运算符，然后从上下文菜单中选择逻辑运算符或内置谓词。  
  
 可以定义规则条件计算结果为时要执行的操作 （内置或用户定义函数） **，则返回 true**。  
  
> [!NOTE]
>  如果在规则中包括多个谓词，所有谓词必须都显示为一个逻辑运算符的参数。 （最高级别可以是单个.NET 成员、 db 列或 XML 字段/属性的布尔值类型。）  
  
### <a name="to-create-a-policy"></a>创建策略  
  
1.  在策略浏览器窗格中，右键单击**策略**，然后单击**添加新策略**。  
  
     一个新文件夹**Policy1**，创建下**策略**。 默认情况下，为你创建新策略的版本 1。  
  
2.  单击**Policy1**。  
  
3.  在名称属性窗格中键入的名称。  
  
### <a name="to-add-a-rule-to-a-policy-version"></a>若要将规则添加到策略版本  
  
-   在策略浏览器窗格中，展开 [**策略**]，用鼠标右键单击**版本 1.0 （未保存）**，然后选择**添加新规则**。  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a>若要将一个逻辑运算符添加到规则条件  
  
-   在规则定义窗口中，右键单击**条件**，然后单击其中一个**添加逻辑并**，**添加逻辑或**，或**添加逻辑非**.  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a>若要将内置谓词添加到规则条件或逻辑运算符  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡，然后依次**谓词**文件夹。  
  
2.  展开的谓词的词汇，发布的版本，然后单击所需的谓词。  
  
3.  将谓词，拖到该逻辑运算符，或**条件**如果你的规则将只包含一个谓词。  
  
    > [!NOTE]
    >  您还可以添加一个谓词，直接从数据源，前提是数据元素充当谓词 (计算结果为 **，则返回 true**或**false**)。  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a>若要向规则添加内置操作  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡，然后依次**函数**文件夹。  
  
2.  展开函数词汇的已发布的版本，然后单击所需的函数。  
  
3.  将函数拖放到拖动**操作**。 此外可以右键单击**操作**，然后从上下文菜单中选择内置操作。  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a>若要将参数添加到条件或操作  
  
1.  在事实浏览器窗口中，单击**词汇**卡，并单击词汇文件夹。  
  
2.  展开词汇的已发布的版本，然后单击所需的术语。 术语必须是谓词或函数所要求的类型。  
  
3.  将术语拖至条件中的谓词参数或操作中的函数参数。  
  
    > [!NOTE]
    >  你还可以直接从数据源添加参数或在 XML 的情况下您可以将字段类型属性中指定选择字段; 时这当然必须符合数据本身，前提是数据元素属于谓词或操作所要求的类型。 若要直接从数据源中添加参数，请单击相应的选项卡在事实浏览器窗口中，导航到所需的项将其拖至谓词参数或函数参数。  
  
    > [!NOTE]
    >  直接通过单击参数并输入所需的常量值，可以向参数添加常数值。