---
title: 进程管理器逻辑 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9894c2201ab9a96559188fd102ec585fafd5afd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396674"
---
# <a name="process-manager-logic"></a><span data-ttu-id="438e8-102">进程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="438e8-102">Process Manager Logic</span></span>
<span data-ttu-id="438e8-103">本部分介绍了如何流程管理器**OrderManager**业务流程、 进程订单。</span><span class="sxs-lookup"><span data-stu-id="438e8-103">This section describes how the process manager, the **OrderManager** orchestration, processes orders.</span></span> <span data-ttu-id="438e8-104">它描述了各个订单消息中的键字段，并遵循新的和更新订单通过业务流程。</span><span class="sxs-lookup"><span data-stu-id="438e8-104">It describes key fields in the various order messages and follows new and updated orders through the orchestration.</span></span>  
  
 <span data-ttu-id="438e8-105">**OrderManager**业务流程协调从属业务流程以处理订单。</span><span class="sxs-lookup"><span data-stu-id="438e8-105">The **OrderManager** orchestration coordinates subordinate orchestrations to process the order.</span></span> <span data-ttu-id="438e8-106">可以添加、 删除或修改这些阶段，而无需更改**OrderManager**。</span><span class="sxs-lookup"><span data-stu-id="438e8-106">You can add, delete, or modify these stages without having to change the **OrderManager**.</span></span> <span data-ttu-id="438e8-107">**OrderManager**进行许多协调处理由.NET 类定义的自定义消息。</span><span class="sxs-lookup"><span data-stu-id="438e8-107">The **OrderManager** does much of the coordination through custom messages defined by .NET classes.</span></span> <span data-ttu-id="438e8-108">在解决方案中的所有消息的列表，请参阅[业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="438e8-108">For a list of all messages in the solution, see [Message Reference for the Business Process Management Solution](../core/message-reference-for-the-business-process-management-solution.md).</span></span> <span data-ttu-id="438e8-109">有关定义消息类型使用.NET 类的信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="438e8-109">For information about defining message types with .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="438e8-110">由于大小和范围**OrderManager**，可能需要阅读这些部分中，尤其是第二个，与在 Microsoft Visual Studio 中打开业务流程。</span><span class="sxs-lookup"><span data-stu-id="438e8-110">Because of the size and scope of **OrderManager**, you may want to read these sections, especially the second, with the orchestration open in Microsoft Visual Studio.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="438e8-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="438e8-111">In This Section</span></span>  
  
-   [<span data-ttu-id="438e8-112">主要消息和字段</span><span class="sxs-lookup"><span data-stu-id="438e8-112">Key Messages and Fields</span></span>](../core/key-messages-and-fields.md)  
  
-   [<span data-ttu-id="438e8-113">通过进程管理器的订单流</span><span class="sxs-lookup"><span data-stu-id="438e8-113">Order Flow through the Process Manager</span></span>](../core/order-flow-through-the-process-manager.md)