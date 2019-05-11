---
title: 如何向业务流程添加自定义补偿 |Microsoft Docs
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
ms.openlocfilehash: 09c8d6bfa6f935c6d34de093fc066eee420705b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343304"
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a>如何向业务流程添加自定义补偿
配置为长时间运行的业务流程事务可以具有自定义补偿代码来撤销事务的影响。 如果业务流程已成功完成并已由另一个业务流程调用，调用业务流程可以调用其补偿块使用**补偿**形状。  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a>若要指定业务流程将使用自定义补偿  
  
1.  在业务流程视图窗口中，选择**业务流程属性**。  
  
2.  在属性窗口中，选择**自定义**的下拉列表中**补偿**属性。  
  
     **补偿**选项卡旁边将显示**业务流程**设计图面底部的选项卡。  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a>若要设计为业务流程的自定义补偿  
  
1.  单击**补偿**设计图面底部的选项卡。  
  
     **补偿设计图面**出现。  
  
2.  添加到形状**补偿设计图面**就像在**业务流程设计图面**。  
  
     有关详细信息，请参阅[向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md)。  
  
## <a name="see-also"></a>请参阅  
 [使业务流程成为事务性业务流程](../core/making-orchestrations-transactional.md)