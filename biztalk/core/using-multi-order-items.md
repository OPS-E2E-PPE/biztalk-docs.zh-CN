---
title: "使用多订单项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, multiple calls
- JD Edwards OneWorld adapters, multi-order numbers
- multiple edit line calls [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multi-order numbers
- multi-order numbers [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multiple calls
ms.assetid: 207ea92c-03f7-4117-8414-eb174e659d26
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389e73ede2d1062c9907bd8640f38ce74ad6f316
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-multi-order-items"></a><span data-ttu-id="f814f-102">使用多订单项</span><span class="sxs-lookup"><span data-stu-id="f814f-102">Using Multi-Order Items</span></span>
<span data-ttu-id="f814f-103">由于 JD Edwards OneWorld API 的结构，如果想要在 BizTalk Server 上使用 multi-order 成员，必须在业务流程中创建多个编辑行调用，以将这些行项目添加到业务流程中。</span><span class="sxs-lookup"><span data-stu-id="f814f-103">Due to the structure of the JD Edwards OneWorld API, if you want to use multi-order numbers with BizTalk Server, you must make multiple edit line calls in your orchestration to add those line items in an orchestration.</span></span> <span data-ttu-id="f814f-104">例如，一个 multi-order 项目可能包含带有单个订单编号的标头，以及包括多个项目订单（如 Toy 1EA、Gloves 2EA）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f814f-104">For example, a multi-order item might contain a header with a single order number, and detail that includes several items orders (like Toy 1EA, Gloves 2EA).</span></span>  
  
 <span data-ttu-id="f814f-105">若要使用多个编辑行调用，则由 BizTalk Server 开发人员负责开发这些调用的结构。</span><span class="sxs-lookup"><span data-stu-id="f814f-105">To use multiple edit line calls, it is the responsibility of the BizTalk Server developer to structure them.</span></span> <span data-ttu-id="f814f-106">开发人员应该在业务流程中创建一个内部循环来实现这些调用。</span><span class="sxs-lookup"><span data-stu-id="f814f-106">The developer should create an internal loop in the orchestration to make those calls.</span></span>  
  
 <span data-ttu-id="f814f-107">JD Edwards OneWorld 系统支持多个编辑行调用，但该 API 不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="f814f-107">The JD Edwards OneWorld system supports multiple edit line calls, but the API does not.</span></span> <span data-ttu-id="f814f-108">如果您正在查看编辑行方法的结构，它是一个平滑的结构而不是一个序列。</span><span class="sxs-lookup"><span data-stu-id="f814f-108">If you look at the structure of the Edit Line method, it is a flat structure and not a sequence.</span></span> <span data-ttu-id="f814f-109">因此，您必须在每次想要插入行项目时调用此函数。</span><span class="sxs-lookup"><span data-stu-id="f814f-109">Therefore, you must call the function every time you want to insert a line item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f814f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f814f-110">See Also</span></span>  
 [<span data-ttu-id="f814f-111">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="f814f-111">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)