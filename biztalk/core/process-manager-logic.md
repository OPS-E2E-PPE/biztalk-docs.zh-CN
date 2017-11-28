---
title: "过程管理器逻辑 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e562362fec8e13589f1860e74024ffe70dad1c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="process-manager-logic"></a><span data-ttu-id="4df18-102">过程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="4df18-102">Process Manager Logic</span></span>
<span data-ttu-id="4df18-103">本部分介绍如何进程管理器中， **OrderManager**业务流程、 进程订单。</span><span class="sxs-lookup"><span data-stu-id="4df18-103">This section describes how the process manager, the **OrderManager** orchestration, processes orders.</span></span> <span data-ttu-id="4df18-104">此外，还介绍了各个订单消息中的关键字段，以及新订单和更新的订单通过该业务流程的过程。</span><span class="sxs-lookup"><span data-stu-id="4df18-104">It describes key fields in the various order messages and follows new and updated orders through the orchestration.</span></span>  
  
 <span data-ttu-id="4df18-105">**OrderManager** orchestration 协调从属业务流程来处理订单。</span><span class="sxs-lookup"><span data-stu-id="4df18-105">The **OrderManager** orchestration coordinates subordinate orchestrations to process the order.</span></span> <span data-ttu-id="4df18-106">你可以添加、 删除或修改这些阶段，而无需更改**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="4df18-106">You can add, delete, or modify these stages without having to change the **OrderManager**.</span></span> <span data-ttu-id="4df18-107">**OrderManager**由.NET 类定义的自定义消息都可通过协调大部分。</span><span class="sxs-lookup"><span data-stu-id="4df18-107">The **OrderManager** does much of the coordination through custom messages defined by .NET classes.</span></span> <span data-ttu-id="4df18-108">在解决方案中的所有消息的列表，请参阅[业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="4df18-108">For a list of all messages in the solution, see [Message Reference for the Business Process Management Solution](../core/message-reference-for-the-business-process-management-solution.md).</span></span> <span data-ttu-id="4df18-109">有关定义使用.NET 类的消息类型的信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="4df18-109">For information about defining message types with .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4df18-110">由于的大小和作用域**OrderManager**，你可能想要阅读这些部分中，特别是第二个，与 Microsoft Visual Studio 中打开业务流程。</span><span class="sxs-lookup"><span data-stu-id="4df18-110">Because of the size and scope of **OrderManager**, you may want to read these sections, especially the second, with the orchestration open in Microsoft Visual Studio.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4df18-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="4df18-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4df18-112">关键信息和字段</span><span class="sxs-lookup"><span data-stu-id="4df18-112">Key Messages and Fields</span></span>](../core/key-messages-and-fields.md)  
  
-   [<span data-ttu-id="4df18-113">顺序流通过进程管理器</span><span class="sxs-lookup"><span data-stu-id="4df18-113">Order Flow through the Process Manager</span></span>](../core/order-flow-through-the-process-manager.md)