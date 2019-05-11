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
# <a name="processing-in-the-business-process-management-solution"></a><span data-ttu-id="57a7d-102">在业务流程管理解决方案中处理</span><span class="sxs-lookup"><span data-stu-id="57a7d-102">Processing in the Business Process Management Solution</span></span>
<span data-ttu-id="57a7d-103">本部分介绍业务流程管理解决方案的工作原理： 如何处理订单，如何使该操作使用的中断，以及如何处理异常以便可以重试。</span><span class="sxs-lookup"><span data-stu-id="57a7d-103">This section describes how the Business Process Management Solution works: how it processes orders, how it makes use of interrupts, and how it handles exceptions so that actions can be retried.</span></span>  
  
 <span data-ttu-id="57a7d-104">订单处理依赖于两个主要业务流程**OrderBroker**并**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="57a7d-104">Order processing relies on two main orchestrations, **OrderBroker** and **OrderManager**.</span></span> <span data-ttu-id="57a7d-105">**OrderBroker**业务流程，以便可以有多个订单管理器业务流程，一个用于每种类型的顺序写入。</span><span class="sxs-lookup"><span data-stu-id="57a7d-105">The **OrderBroker** orchestration is written so that there can be multiple order manager orchestrations, one for each kind of order.</span></span> <span data-ttu-id="57a7d-106">该解决方案包含一个**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="57a7d-106">The solution includes only one **OrderManager**.</span></span> <span data-ttu-id="57a7d-107">它，也是相对通用以便可适用于其他类型的订单。</span><span class="sxs-lookup"><span data-stu-id="57a7d-107">It, too, is relatively generic so that it can be adapted to other types of orders.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57a7d-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="57a7d-108">In This Section</span></span>  
  
-   [<span data-ttu-id="57a7d-109">OrderBroker 业务流程中处理</span><span class="sxs-lookup"><span data-stu-id="57a7d-109">Processing in the OrderBroker Orchestration</span></span>](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [<span data-ttu-id="57a7d-110">进程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="57a7d-110">Process Manager Logic</span></span>](../core/process-manager-logic.md)  
  
-   [<span data-ttu-id="57a7d-111">在订单处理阶段中处理</span><span class="sxs-lookup"><span data-stu-id="57a7d-111">Processing in the Order Processing Stages</span></span>](../core/processing-in-the-order-processing-stages.md)  
  
-   [<span data-ttu-id="57a7d-112">业务流程管理解决方案中的中断处理</span><span class="sxs-lookup"><span data-stu-id="57a7d-112">Interrupt Handling in the Business Process Management Solution</span></span>](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="57a7d-113">业务流程管理解决方案中的异常处理</span><span class="sxs-lookup"><span data-stu-id="57a7d-113">Exception Handling in the Business Process Management Solution</span></span>](../core/exception-handling-in-the-business-process-management-solution.md)