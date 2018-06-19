---
title: 事务处理业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- orchestrations, transactional
- Transaction Type property
ms.assetid: c4f0b6ca-d939-4d3a-b7ef-53c6aafdea9c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c6fb466e0c3cc5cae4a076237d1dbc970b5794
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278733"
---
# <a name="transacted-orchestrations"></a>事务处理的业务流程
业务流程可以是事务性的，与作用域类似。 实际上，业务流程本身可以视为作用域。 通常，同一规则对进行事务处理的业务流程的适用性与对进行事务处理的作用域的适用性是一样的。  
  
> [!NOTE]
>  业务流程和其他作用域之间的一个区别是，业务流程没有异常处理程序。  
  
## <a name="orchestration-compensation"></a>业务流程补偿  
 如果**事务类型**适用于你的业务流程的属性设置为长时间运行或原子性的你还可以选择的值**补偿**属性，它可以是默认或自定义。  
  
 如果你选择**自定义**的补偿，**补偿**选项卡将显示与业务流程设计图面。 其外观与业务流程设计图面一样，您可以用同样的方式向其中添加形状和端口。  
  
 补偿只针对被其他业务流程调用的业务流程进行。 你可以通过使用补偿的特定业务流程实例**标识符**属性**调用 Orchestration**形状。  
  
> [!IMPORTANT]
>  如果补偿存在于顶级业务流程，将被运行时引擎忽略。  
  
## <a name="see-also"></a>另请参阅  
 [使业务流程事务](../core/making-orchestrations-transactional.md)   
 [使用事务和处理异常](../core/using-transactions-and-handling-exceptions.md)