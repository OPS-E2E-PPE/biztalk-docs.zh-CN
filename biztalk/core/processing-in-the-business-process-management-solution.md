---
title: 在业务流程管理解决方案中处理 |Microsoft 文档
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
ms.openlocfilehash: 145dd8e616048f1caaa1a59ec41d099e93e47880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264597"
---
# <a name="processing-in-the-business-process-management-solution"></a><span data-ttu-id="fcda0-102">在业务流程管理解决方案中进行处理</span><span class="sxs-lookup"><span data-stu-id="fcda0-102">Processing in the Business Process Management Solution</span></span>
<span data-ttu-id="fcda0-103">本部分介绍业务流程管理解决方案的工作原理： 如何处理订单，它将使用中断，以及它如何处理异常因此该操作可以重试。</span><span class="sxs-lookup"><span data-stu-id="fcda0-103">This section describes how the Business Process Management Solution works: how it processes orders, how it makes use of interrupts, and how it handles exceptions so that actions can be retried.</span></span>  
  
 <span data-ttu-id="fcda0-104">订单处理依赖于两个主要业务流程， **OrderBroker**和**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="fcda0-104">Order processing relies on two main orchestrations, **OrderBroker** and **OrderManager**.</span></span> <span data-ttu-id="fcda0-105">**OrderBroker** orchestration 编写，因此可以有多个顺序 manager 业务流程，一个用于每种类型的顺序。</span><span class="sxs-lookup"><span data-stu-id="fcda0-105">The **OrderBroker** orchestration is written so that there can be multiple order manager orchestrations, one for each kind of order.</span></span> <span data-ttu-id="fcda0-106">此解决方案包括只有一个**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="fcda0-106">The solution includes only one **OrderManager**.</span></span> <span data-ttu-id="fcda0-107">但相对来说，该业务流程是通用的，这样，就可以应用于其他类型的订单。</span><span class="sxs-lookup"><span data-stu-id="fcda0-107">It, too, is relatively generic so that it can be adapted to other types of orders.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcda0-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="fcda0-108">In This Section</span></span>  
  
-   [<span data-ttu-id="fcda0-109">OrderBroker 业务流程中的处理</span><span class="sxs-lookup"><span data-stu-id="fcda0-109">Processing in the OrderBroker Orchestration</span></span>](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [<span data-ttu-id="fcda0-110">过程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="fcda0-110">Process Manager Logic</span></span>](../core/process-manager-logic.md)  
  
-   [<span data-ttu-id="fcda0-111">中的顺序处理阶段的处理</span><span class="sxs-lookup"><span data-stu-id="fcda0-111">Processing in the Order Processing Stages</span></span>](../core/processing-in-the-order-processing-stages.md)  
  
-   [<span data-ttu-id="fcda0-112">中断业务流程管理解决方案中的处理</span><span class="sxs-lookup"><span data-stu-id="fcda0-112">Interrupt Handling in the Business Process Management Solution</span></span>](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="fcda0-113">业务流程管理解决方案中的异常处理</span><span class="sxs-lookup"><span data-stu-id="fcda0-113">Exception Handling in the Business Process Management Solution</span></span>](../core/exception-handling-in-the-business-process-management-solution.md)