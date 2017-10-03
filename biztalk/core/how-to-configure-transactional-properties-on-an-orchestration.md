---
title: "如何在业务流程上配置事务属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9164a9f5670a996a62450a19d802c97b89d8e242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a>如何在业务流程上配置事务属性
业务流程可被视为原子事务、长期事务或既非原子事务也非长期事务。  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a>使业务流程成为原子事务  
  
1.  在业务流程视图窗口中，选择**业务流程属性**。  
  
2.  在属性窗口中，选择**原子**下拉列表中**事务类型**属性。  
  
     **批处理**，**补偿**，**隔离级别**，**重试**，**超时**，和**事务标识符**显示为属性窗口中的属性，就像它们针对任何范围内采取的操作。 有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a>使业务流程成为长期事务  
  
1.  在业务流程视图窗口中，选择**业务流程属性**。  
  
2.  在属性窗口中，选择**运行长时间**下拉列表中**事务类型**属性。  
  
     **补偿**，**超时**，和**事务标识符**显示为属性窗口中的属性。 有关这些属性的详细信息，与它们针对任何作用域显示一样。 有关这些属性的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使业务流程事务](../core/making-orchestrations-transactional.md)