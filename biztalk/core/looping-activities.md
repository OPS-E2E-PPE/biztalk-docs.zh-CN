---
title: 循环活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cf2b768deca72b281bc189431b01f5e63a4887
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005062"
---
# <a name="looping-activities"></a><span data-ttu-id="531d1-102">循环活动</span><span class="sxs-lookup"><span data-stu-id="531d1-102">Looping Activities</span></span>
<span data-ttu-id="531d1-103">循环活动是指在某个业务流程内循环的操作。</span><span class="sxs-lookup"><span data-stu-id="531d1-103">Looping activities refers to actions that loop within an orchestration.</span></span> <span data-ttu-id="531d1-104">可以从在业务流程内循环的操作中捕获事件。</span><span class="sxs-lookup"><span data-stu-id="531d1-104">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="531d1-105">为此，需要创建另一个活动，并映射该循环内的所有新活动里程碑和数据。</span><span class="sxs-lookup"><span data-stu-id="531d1-105">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="531d1-106">这样做是有必要的，因为在循环中数据处理在每次计划的执行中将发生多次。</span><span class="sxs-lookup"><span data-stu-id="531d1-106">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span> <span data-ttu-id="531d1-107">下图显示的就是这种情况的一个示例。</span><span class="sxs-lookup"><span data-stu-id="531d1-107">The following figure shows an example of this situation.</span></span>  
  
 <span data-ttu-id="531d1-108">![](../core/media/handlingloops2.gif "handlingloops2")</span><span class="sxs-lookup"><span data-stu-id="531d1-108">![](../core/media/handlingloops2.gif "handlingloops2")</span></span>  
  
 <span data-ttu-id="531d1-109">如图所示，如果您有包含在循环中处理的多个行项的采购订单，等问题"哪些采购订单的货物价格为 $100？"</span><span class="sxs-lookup"><span data-stu-id="531d1-109">As shown in the figure, if you have a Purchase Order with multiple Line Items that process in a loop, questions like "Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="531d1-110">是不明确。</span><span class="sxs-lookup"><span data-stu-id="531d1-110">are ambiguous.</span></span> <span data-ttu-id="531d1-111">下面的问题则含义明确：</span><span class="sxs-lookup"><span data-stu-id="531d1-111">Unambiguous questions are:</span></span>  
  
- <span data-ttu-id="531d1-112">哪些采购订单包含价格为 $100 的货物行？</span><span class="sxs-lookup"><span data-stu-id="531d1-112">Which purchase orders have line items with a price of $100?</span></span>  
  
- <span data-ttu-id="531d1-113">哪些采购订单的货物的总计/最小/最大价格为 $100？</span><span class="sxs-lookup"><span data-stu-id="531d1-113">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
  <span data-ttu-id="531d1-114">要提出含义明确的问题，则需要将货物行同采购订单分开考虑。</span><span class="sxs-lookup"><span data-stu-id="531d1-114">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="531d1-115">在跟踪配置文件编辑器中，根活动（例如，采购订单）映射到循环外的所有操作。</span><span class="sxs-lookup"><span data-stu-id="531d1-115">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="531d1-116">子活动 （例如，行项） 映射到此循环操作。</span><span class="sxs-lookup"><span data-stu-id="531d1-116">The child activity (for example, line item) maps to the actions inside the loop.</span></span>  
  
  <span data-ttu-id="531d1-117">您需要将负载项目用作根活动的 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="531d1-117">You need to use a payload item as ActivityID for the root activity.</span></span> <span data-ttu-id="531d1-118">使此负载项目可供循环内的某些消息使用。</span><span class="sxs-lookup"><span data-stu-id="531d1-118">Have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="531d1-119">该活动映射到关系节点下的子活动，并将其命名为根活动。</span><span class="sxs-lookup"><span data-stu-id="531d1-119">Map the activity to the Relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531d1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="531d1-120">See Also</span></span>  
 [<span data-ttu-id="531d1-121">与事件流实现 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="531d1-121">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)