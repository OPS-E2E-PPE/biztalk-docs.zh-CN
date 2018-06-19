---
title: 如何将自定义补偿添加到业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- Compensate shape [Orchestration Designer]
- Compensate shape [Orchestration Designer], orchestrations
- Compensation property
- orchestrations, transactional
- orchestrations, customizing
- customizing, orchestrations
- Compensate shape [Orchestration Designer], custom compensation
ms.assetid: d153498d-8f98-42ae-90b9-e3083d669aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eadb9cba6e5a49be516a8095b01f93ca7a490f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248117"
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a>如何将自定义补偿添加到业务流程
配置为长期的业务流程事务可以具有自定义补偿代码来撤销事务的影响。 如果业务流程已成功完成，并且已由另一个业务流程调用，调用业务流程可以调用其补偿块使用**Compensate**形状。  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a>指定业务流程将使用自定义补偿  
  
1.  在业务流程视图窗口中，选择**业务流程属性**。  
  
2.  在属性窗口中，选择**自定义**下拉列表中**补偿**属性。  
  
     **补偿**旁边显示选项卡**Orchestration**设计图面的底部的选项卡。  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a>设计业务流程的自定义补偿  
  
1.  单击**补偿**设计图面的底部的选项卡。  
  
     **补偿设计图面**显示。  
  
2.  添加到形状**补偿设计图面**就像在**业务流程设计图面**。  
  
     有关详细信息，请参阅[添加形状链接到业务流程](../core/how-to-add-shapes-to-orchestrations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使业务流程事务](../core/making-orchestrations-transactional.md)