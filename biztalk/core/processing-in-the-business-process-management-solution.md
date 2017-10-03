---
title: "在业务流程管理解决方案中处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, process management solutions
ms.assetid: 0b26447e-d8f1-4084-aa34-6e7f8ffccea5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 145dd8e616048f1caaa1a59ec41d099e93e47880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-business-process-management-solution"></a>在业务流程管理解决方案中进行处理
本部分介绍业务流程管理解决方案的工作原理： 如何处理订单，它将使用中断，以及它如何处理异常因此该操作可以重试。  
  
 订单处理依赖于两个主要业务流程， **OrderBroker**和**OrderManager**。 **OrderBroker** orchestration 编写，因此可以有多个顺序 manager 业务流程，一个用于每种类型的顺序。 此解决方案包括只有一个**OrderManager**。 但相对来说，该业务流程是通用的，这样，就可以应用于其他类型的订单。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [过程管理器逻辑](../core/process-manager-logic.md)  
  
-   [中的顺序处理阶段的处理](../core/processing-in-the-order-processing-stages.md)  
  
-   [中断业务流程管理解决方案中的处理](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)