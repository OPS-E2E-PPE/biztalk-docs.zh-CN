---
title: "循环活动 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f66382a27ed564da0c41257e8abe95accba5e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="looping-activities"></a><span data-ttu-id="0522d-102">循环的活动</span><span class="sxs-lookup"><span data-stu-id="0522d-102">Looping Activities</span></span>
<span data-ttu-id="0522d-103">循环活动是指在某个业务流程内循环的操作。</span><span class="sxs-lookup"><span data-stu-id="0522d-103">Looping activities refers to actions that loop within an orchestration.</span></span> <span data-ttu-id="0522d-104">可以从在业务流程内循环的操作中捕获事件。</span><span class="sxs-lookup"><span data-stu-id="0522d-104">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="0522d-105">为此，需要创建另一个活动，并映射该循环内的所有新活动里程碑和数据。</span><span class="sxs-lookup"><span data-stu-id="0522d-105">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="0522d-106">这样做是有必要的，因为在循环中数据处理在每次计划的执行中将发生多次。</span><span class="sxs-lookup"><span data-stu-id="0522d-106">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span> <span data-ttu-id="0522d-107">下图显示的就是这种情况的一个示例。</span><span class="sxs-lookup"><span data-stu-id="0522d-107">The following figure shows an example of this situation.</span></span>  
  
 ![](../core/media/handlingloops2.gif "handlingloops2")  
  
 <span data-ttu-id="0522d-108">如图所示，如果你有具有在循环中处理的多个行项的购买订单，此类问题:"的采购订单有 100 美元的项价格？"</span><span class="sxs-lookup"><span data-stu-id="0522d-108">As shown in the figure, if you have a Purchase Order with multiple Line Items that process in a loop, questions like "Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="0522d-109">不明确。</span><span class="sxs-lookup"><span data-stu-id="0522d-109">are ambiguous.</span></span> <span data-ttu-id="0522d-110">下面的问题则含义明确：</span><span class="sxs-lookup"><span data-stu-id="0522d-110">Unambiguous questions are:</span></span>  
  
-   <span data-ttu-id="0522d-111">哪些采购订单包含价格为 $100 的货物行？</span><span class="sxs-lookup"><span data-stu-id="0522d-111">Which purchase orders have line items with a price of $100?</span></span>  
  
-   <span data-ttu-id="0522d-112">哪些采购订单的货物的总计/最小/最大价格为 $100？</span><span class="sxs-lookup"><span data-stu-id="0522d-112">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
 <span data-ttu-id="0522d-113">要提出含义明确的问题，则需要将货物行同采购订单分开考虑。</span><span class="sxs-lookup"><span data-stu-id="0522d-113">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="0522d-114">在跟踪配置文件编辑器中，根活动（例如，采购订单）映射到循环外的所有操作。</span><span class="sxs-lookup"><span data-stu-id="0522d-114">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="0522d-115">子活动 （例如，行项） 将映射到循环内的操作。</span><span class="sxs-lookup"><span data-stu-id="0522d-115">The child activity (for example, line item) maps to the actions inside the loop.</span></span>  
  
 <span data-ttu-id="0522d-116">您需要将负载项目用作根活动的 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="0522d-116">You need to use a payload item as ActivityID for the root activity.</span></span> <span data-ttu-id="0522d-117">使此负载项目可供循环内的某些消息使用。</span><span class="sxs-lookup"><span data-stu-id="0522d-117">Have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="0522d-118">映射到的子活动下显示的关系节点的活动并将它作为根活动。</span><span class="sxs-lookup"><span data-stu-id="0522d-118">Map the activity to the Relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0522d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0522d-119">See Also</span></span>  
 [<span data-ttu-id="0522d-120">实现事件流 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="0522d-120">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)