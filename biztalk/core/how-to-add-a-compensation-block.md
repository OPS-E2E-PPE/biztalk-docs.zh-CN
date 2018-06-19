---
title: 如何添加补偿块 |Microsoft 文档
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
ms.openlocfilehash: a2dec4f4dd01c2bbf522dfff44ec8aaf0c2f5e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246533"
---
# <a name="how-to-add-a-compensation-block"></a>如何添加补偿模块
如果您没有添加您自己的补偿，则运行时引擎将执行默认补偿，该默认补偿调用当前事务内任何嵌套事务的补偿。 它首先调用最近完成的事务的补偿，并直到所有嵌套的事务都已得到补偿前一直有效。  
  
 甚至当你补偿内发生循环形状这保持为 true: 补偿将按相反的顺序运行。 首先，将调用循环中最后一个迭代的补偿，然后调用前一个迭代的补偿，依此类推。  
  
> [!CAUTION]
>  由于为使补偿有效，数据将保存到物理内存中，因此，在循环内使用补偿可能会影响性能，在有大量迭代存在的情况下，可能导致问题。  
  
 如果默认顺序无法满足您的要求，您可以编写自己的补偿处理程序，以便按您指定的顺序显式调用嵌套作用域的补偿处理程序。  
  
### <a name="to-add-a-compensation-block"></a>添加补偿模块  
  
1.  右键单击**作用域**你想要添加的事务的形状**补偿块**，然后单击**新补偿块**。  
  
    > [!NOTE]
    >  若要添加**补偿块**到**作用域**形状，**事务类型**属性**作用域**形状必须设置为**原子**或**长时间运行的**。  
  
     A**补偿块**添加到紧跟在关联的业务流程**作用域**形状。  
  
2.  内部**补偿块**形状，添加形状创建撤消已提交的事务的过程。