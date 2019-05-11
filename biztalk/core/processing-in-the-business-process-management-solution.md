---
title: 在业务流程管理解决方案中处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, process management solutions
ms.assetid: 0b26447e-d8f1-4084-aa34-6e7f8ffccea5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf08892ff975348624eec4548d0895ef5f3221b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299832"
---
# <a name="processing-in-the-business-process-management-solution"></a>在业务流程管理解决方案中处理
本部分介绍业务流程管理解决方案的工作原理： 如何处理订单，如何使该操作使用的中断，以及如何处理异常以便可以重试。  
  
 订单处理依赖于两个主要业务流程**OrderBroker**并**OrderManager**。 **OrderBroker**业务流程，以便可以有多个订单管理器业务流程，一个用于每种类型的顺序写入。 该解决方案包含一个**OrderManager**。 它，也是相对通用以便可适用于其他类型的订单。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [进程管理器逻辑](../core/process-manager-logic.md)  
  
-   [在订单处理阶段中处理](../core/processing-in-the-order-processing-stages.md)  
  
-   [业务流程管理解决方案中的中断处理](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)