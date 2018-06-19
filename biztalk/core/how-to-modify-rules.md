---
title: 如何修改规则 |Microsoft 文档
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
ms.openlocfilehash: fce3fb78ce67b6c82f2301dfcb4cb2175aee0dde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254229"
---
# <a name="how-to-modify-rules"></a>如何修改规则
若要更改规则的功能是业务规则范例的一个重要部分。 你可以修改中两种方式的策略规则： 通过创建新版本的策略，或通过直接修改取消发布的版本的策略。  
  
 你可以单独修改规则、 添加新规则，或删除现有规则。 可以删除从规则条件的谓词和逻辑运算符，删除操作，在显示中，向上和向下移动操作或移动谓词和在一个条件中的逻辑运算符。 请记住，但是，谓词和逻辑运算符的显示顺序不确定的计算顺序。  
  
 你可以设置为非活动状态，以便执行策略，或可以重新激活已停用的规则时，不执行规则的规则。  
  
 可以对规则设置优先级，以便之前或之后的任何规则不同的优先级的操作，将执行其操作。  
  
> [!CAUTION]
>  如果你需要停止 SQL Server 计算机，请务必保存任何未保存的词汇版本或词汇定义，并关闭业务规则编辑器，以便任何更改都将丢失。  
  
 本主题包含以下任务的过程：  
  
-   若要更改中的条件或操作的自变量  
  
-   将在一个条件中的谓词  
  
-   将在一个条件中的一个逻辑运算符  
  
-   若要更改规则的操作顺序  
  
-   若要删除的谓词，逻辑运算符或操作  
  
-   若要激活或停用一条规则  
  
-   规则上设置优先级  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a>若要更改中的条件或操作的自变量  
  
1.  在事实和定义窗口中，单击相应的选项卡，并导航到想要作为自变量使用的术语。 该术语必须属于谓词或功能所要求的类型。  
  
2.  单击术语，并将其拖到条件中的谓词自变量或操作中的函数自变量。  
  
### <a name="to-move-a-predicate-within-a-condition"></a>将在一个条件中的谓词  
  
-   单击该谓词，并将其拖到另一个逻辑运算符。  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a>将在一个条件中的一个逻辑运算符  
  
-   单击逻辑运算符，并将其拖到另一个逻辑运算符或**条件**。  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a>若要更改规则的操作顺序  
  
-   单击操作，然后单击**移操作**或**向下移动操作**。  
  
    > [!NOTE]
    >  除了引擎控制功能以及执行其他操作后指定的顺序，将执行一个规则的操作。  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a>若要删除的谓词，逻辑运算符或操作  
  
-   单击谓词，逻辑运算符或操作，，然后单击**删除**。  
  
### <a name="to-activate-or-deactivate-a-rule"></a>若要激活或停用一条规则  
  
-   单击该规则，然后在属性窗口中，设置**Active**为**True**或**False**。  
  
### <a name="to-set-a-priority-on-a-rule"></a>规则上设置优先级  
  
-   单击该规则，然后在属性窗口中，设置**优先级**为整数值。  
  
    > [!NOTE]
    >  优先级是相对的并且所有给定优先级的规则的操作将在任何具有较低的值的规则的操作前优先级的顺序执行。 优先级值默认为零，但它可以是正数或负数。