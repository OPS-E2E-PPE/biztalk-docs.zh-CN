---
title: 事务性业务流程 |Microsoft Docs
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
ms.openlocfilehash: 2607c6619391481870baa19b5cda07d7419f9dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313294"
---
# <a name="transacted-orchestrations"></a>事务处理业务流程
业务流程可以是事务性的作用域类似。 实际上，业务流程本身可以视为作用域。 一般情况下，同一规则对进行事务处理业务流程与事务处理的作用域。  
  
> [!NOTE]
>  业务流程和其他作用域之间的一个区别是，业务流程没有异常处理程序。  
  
## <a name="orchestration-compensation"></a>业务流程补偿  
 如果**事务类型**业务流程的属性设置为长时间运行或原子的您还可以选择的值**补偿**属性，它可以是默认或自定义。  
  
 如果选择**自定义**补偿**补偿**选项卡将显示与业务流程设计图面。 它看起来相同作为业务流程设计图面上，并且可以添加形状和端口到该相同的方式。  
  
 补偿只会在由其他业务流程调用的业务流程上发生。 可以通过使用补偿特定业务流程实例**标识符**上的属性**调用业务流程**形状。  
  
> [!IMPORTANT]
>  如果补偿存在于顶级业务流程，运行时引擎将忽略它。  
  
## <a name="see-also"></a>请参阅  
 [使业务流程成为事务性](../core/making-orchestrations-transactional.md)   
 [使用事务和处理异常](../core/using-transactions-and-handling-exceptions.md)