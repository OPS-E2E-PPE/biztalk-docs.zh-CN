---
title: 如何添加补偿块 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef3cce71a85b41ccfc4291f82c5736d77f15162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343852"
---
# <a name="how-to-add-a-compensation-block"></a>如何添加补偿块
如果不添加您自己的补偿，则运行时引擎将执行默认补偿调用当前事务中任何嵌套事务的补偿。 首先调用最近完成的事务，补偿，并向后工作，直到所有嵌套的事务有补偿。  
  
 这为 true 甚至当您的补偿内发生循环形状： 补偿将以反向顺序运行。 首先，将调用循环的最后一个迭代的补偿，然后补偿的上一次迭代，依次类推。  
  
> [!CAUTION]
>  由于数据将保存到补偿有效的物理内存，使用补偿在循环内，可能会影响性能，这可能会提供大量迭代出现问题。  
  
 如果默认顺序无法满足您的要求，可以编写您自己的补偿处理程序，以显式调用中所指定的顺序的嵌套作用域的补偿处理程序。  
  
### <a name="to-add-a-compensation-block"></a>若要添加补偿模块  
  
1.  右键单击**作用域**交易记录你想要添加的形状**补偿模块**，然后单击**新建补偿模块**。  
  
    > [!NOTE]
    >  若要添加**补偿模块**到**作用域**形状，**事务类型**属性的**范围**形状必须设置为**原子**或**长时间运行的**。  
  
     一个**补偿模块**添加到紧跟相关业务流程**作用域**形状。  
  
2.  内部**补偿模块**形状中，添加形状以创建用于撤消已提交的事务的进程。