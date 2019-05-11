---
title: 如何修改规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, activating
- deactivating business rules
- business rules, priorities
- activating business rules
- business rules, deactivating
- modifying, business rules
- business rules, modifying
ms.assetid: 661b2637-b5d6-4bde-9c42-24cd9e9d241c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2badd7947e439fe3ba80d86607a1a271d52b5eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336009"
---
# <a name="how-to-modify-rules"></a>如何修改规则
若要更改规则的功能是业务规则范例的一个重要部分。 您可以修改策略中通过两种方式的规则： 通过创建新版本的策略，或通过直接修改策略的未发布的版本。  
  
 可以单独修改规则、 添加新规则，或删除现有规则。 可以从规则条件中删除谓词和逻辑运算符、 删除操作，在显示中，向上和向下移动操作或移动谓词和某一条件内的逻辑运算符。 但是请记住，、 谓词和逻辑运算符的显示的顺序不确定的计算顺序。  
  
 可以设置为非活动状态，以便执行策略，或可以重新激活已停用的规则时不执行规则的规则。  
  
 可以对规则设置优先级，从而使之前或之后的任何其他优先级的规则的操作，将执行其操作。  
  
> [!CAUTION]
>  如果你需要停止 SQL Server 计算机，请务必保存任何未保存的词汇版本或词汇定义，并关闭业务规则编辑器，以便不不丢失任何更改。  
  
 本主题包含以下任务的过程：  
  
-   若要更改条件或操作中的自变量  
  
-   若要移动某一条件内的谓词  
  
-   若要移动某一条件内的逻辑运算符  
  
-   若要更改规则中的操作顺序  
  
-   若要删除谓词、 逻辑运算符或操作  
  
-   若要激活或停用某个规则  
  
-   若要设置规则优先级  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a>若要更改条件或操作中的自变量  
  
1.  在事实和定义窗口中，单击相应的选项卡，并导航到想要作为参数使用的术语。 术语必须是谓词或函数所要求的类型。  
  
2.  单击术语并将其拖至条件中的谓词参数或操作中的函数参数。  
  
### <a name="to-move-a-predicate-within-a-condition"></a>若要移动某一条件内的谓词  
  
-   单击该谓词中，并将其拖到另一个逻辑运算符。  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a>若要移动某一条件内的逻辑运算符  
  
-   单击该逻辑运算符，并将其拖到另一个逻辑运算符或上**条件**。  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a>若要更改规则中的操作顺序  
  
-   单击操作，然后单击**操作上移**或**向下移动操作**。  
  
    > [!NOTE]
    >  将指定除了引擎控制功能的其他操作之后执行的顺序执行规则的操作。  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a>若要删除谓词、 逻辑运算符或操作  
  
-   单击谓词、 逻辑运算符或操作，然后依次**删除**。  
  
### <a name="to-activate-or-deactivate-a-rule"></a>若要激活或停用某个规则  
  
-   单击该规则，然后在属性窗口中设置**Active**至任一**True**或**False**。  
  
### <a name="to-set-a-priority-on-a-rule"></a>若要设置规则优先级  
  
-   单击该规则，然后在属性窗口中设置**优先级**为整数值。  
  
    > [!NOTE]
    >  优先级是相对的并将之前的任何具有较低的值的规则操作的优先级的顺序执行的所有给定优先级的规则的操作。 默认优先级值为零，但它可以是正数或负数。