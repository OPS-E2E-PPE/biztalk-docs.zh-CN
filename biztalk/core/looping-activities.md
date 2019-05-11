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
ms.openlocfilehash: 58668a901f9bb5a4aba3ae2ee25917c9227daac6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330139"
---
# <a name="looping-activities"></a><span data-ttu-id="4b864-102">循环活动</span><span class="sxs-lookup"><span data-stu-id="4b864-102">Looping Activities</span></span>
<span data-ttu-id="4b864-103">循环活动是指在业务流程内循环的操作。</span><span class="sxs-lookup"><span data-stu-id="4b864-103">Looping activities refers to actions that loop within an orchestration.</span></span> <span data-ttu-id="4b864-104">就可以捕获来自业务流程内循环的操作的事件。</span><span class="sxs-lookup"><span data-stu-id="4b864-104">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="4b864-105">若要执行此操作，创建另一个活动并将映射的所有新活动里程碑和在循环内的数据。</span><span class="sxs-lookup"><span data-stu-id="4b864-105">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="4b864-106">这是必需的因为在循环中的数据处理将会发生多个计划的执行每一次。</span><span class="sxs-lookup"><span data-stu-id="4b864-106">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span> <span data-ttu-id="4b864-107">下图显示了这种情况的示例。</span><span class="sxs-lookup"><span data-stu-id="4b864-107">The following figure shows an example of this situation.</span></span>  
  
 <span data-ttu-id="4b864-108">![](../core/media/handlingloops2.gif "handlingloops2")</span><span class="sxs-lookup"><span data-stu-id="4b864-108">![](../core/media/handlingloops2.gif "handlingloops2")</span></span>  
  
 <span data-ttu-id="4b864-109">如图所示，如果您有包含在循环中处理的多个行项的采购订单，等问题"哪些采购订单的货物价格为 $100？"</span><span class="sxs-lookup"><span data-stu-id="4b864-109">As shown in the figure, if you have a Purchase Order with multiple Line Items that process in a loop, questions like "Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="4b864-110">是不明确。</span><span class="sxs-lookup"><span data-stu-id="4b864-110">are ambiguous.</span></span> <span data-ttu-id="4b864-111">问题则含义明确：</span><span class="sxs-lookup"><span data-stu-id="4b864-111">Unambiguous questions are:</span></span>  
  
- <span data-ttu-id="4b864-112">哪些采购订单的价格为 $100 的货物行？</span><span class="sxs-lookup"><span data-stu-id="4b864-112">Which purchase orders have line items with a price of $100?</span></span>  
  
- <span data-ttu-id="4b864-113">哪些采购订单的总计/最小/最大货物价格为 $100？</span><span class="sxs-lookup"><span data-stu-id="4b864-113">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
  <span data-ttu-id="4b864-114">内容使用独立的从采购订单创建明确问题需要考虑的行项。</span><span class="sxs-lookup"><span data-stu-id="4b864-114">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="4b864-115">在跟踪配置文件编辑器中，根活动 （例如，采购订单） 映射到在循环外的所有操作。</span><span class="sxs-lookup"><span data-stu-id="4b864-115">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="4b864-116">子活动 （例如，行项） 映射到此循环操作。</span><span class="sxs-lookup"><span data-stu-id="4b864-116">The child activity (for example, line item) maps to the actions inside the loop.</span></span>  
  
  <span data-ttu-id="4b864-117">需要一个负载项用作根活动的 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="4b864-117">You need to use a payload item as ActivityID for the root activity.</span></span> <span data-ttu-id="4b864-118">有一些在循环内的消息中提供此负载项。</span><span class="sxs-lookup"><span data-stu-id="4b864-118">Have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="4b864-119">该活动映射到关系节点下的子活动，并将其命名为根活动。</span><span class="sxs-lookup"><span data-stu-id="4b864-119">Map the activity to the Relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b864-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b864-120">See Also</span></span>  
 [<span data-ttu-id="4b864-121">与事件流实现 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="4b864-121">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)