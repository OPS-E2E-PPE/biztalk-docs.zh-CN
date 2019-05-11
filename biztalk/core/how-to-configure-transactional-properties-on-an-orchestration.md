---
title: 如何在业务流程配置事务属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c999ca7c487cdcf59fd29e76b3d466194aa8ee21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385780"
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a>如何在业务流程配置事务属性
业务流程可将其视为原子事务、 长时间运行的事务，还是两者皆未。  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a>若要使某一原子事务的业务流程  
  
1.  在业务流程视图窗口中，选择**业务流程属性**。  
  
2.  在属性窗口中，选择**原子**的下拉列表中**事务类型**属性。  
  
     **批处理**，**补偿**，**隔离级别**，**重试**，**超时**，和**事务标识符**作为属性出现在属性窗口中，就像针对任何作用域。 有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a>若要使一个长时间运行的事务的业务流程  
  
1.  在业务流程视图窗口中，选择**业务流程属性**。  
  
2.  在属性窗口中，选择**长期**的下拉列表中**事务类型**属性。  
  
     **补偿**，**超时**，和**事务标识符**作为属性出现在属性窗口。 有关详细信息属性，就像针对任何作用域。 有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。  
  
## <a name="see-also"></a>请参阅  
 [使业务流程成为事务性业务流程](../core/making-orchestrations-transactional.md)