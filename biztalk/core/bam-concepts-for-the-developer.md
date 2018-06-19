---
title: 开发人员的 BAM 概念 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c26d0aed-821c-4e1f-9cc9-9375a2ba28de
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e407121e9f71707b45f95e77a8520ed30df3b33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230805"
---
# <a name="bam-concepts-for-the-developer"></a><span data-ttu-id="cd79b-102">适用于开发人员的 BAM 概念</span><span class="sxs-lookup"><span data-stu-id="cd79b-102">BAM Concepts for the Developer</span></span>
<span data-ttu-id="cd79b-103">作为 BAM 开发人员，您需要熟悉重要的 BAM 概念，如活动、继续符和引用，</span><span class="sxs-lookup"><span data-stu-id="cd79b-103">As a BAM developer, you need to be familiar with important BAM concepts, such as activities, continuations, and references.</span></span> <span data-ttu-id="cd79b-104">还应该了解跟踪和事务性处理之间的区别。</span><span class="sxs-lookup"><span data-stu-id="cd79b-104">You should also understand the differences between tracking and transactional processing.</span></span>  
  
## <a name="what-is-a-bam-activity"></a><span data-ttu-id="cd79b-105">什么是 BAM 活动？</span><span class="sxs-lookup"><span data-stu-id="cd79b-105">What Is a BAM Activity?</span></span>  
 <span data-ttu-id="cd79b-106">BAM 活动定义了哪些数据对于业务流程中的项是目标数据（如单个 PO）。</span><span class="sxs-lookup"><span data-stu-id="cd79b-106">A BAM activity is the definition of what data is interesting for an item in the business process (such as a single PO).</span></span> <span data-ttu-id="cd79b-107">它定义了 BAM 数据库中包括的列。</span><span class="sxs-lookup"><span data-stu-id="cd79b-107">It defines what columns are in the BAM database.</span></span>  
  
 <span data-ttu-id="cd79b-108">活动实例代表业务中的工作单位，例如采购订单或贷款申请。</span><span class="sxs-lookup"><span data-stu-id="cd79b-108">An instance of an activity represents a unit of work in the business, such as a purchase order or a loan application.</span></span> <span data-ttu-id="cd79b-109">活动指定了里程碑（活动的历史记录）列表和目标数据。</span><span class="sxs-lookup"><span data-stu-id="cd79b-109">An activity specifies a list of milestones (the history of the activity) and data of interest.</span></span> <span data-ttu-id="cd79b-110">活动实例表现为 BAM 主导入数据库中的单个行。</span><span class="sxs-lookup"><span data-stu-id="cd79b-110">An instance of an activity is manifested as a single row in the BAM Primary Import database.</span></span> <span data-ttu-id="cd79b-111">对于活动实例的任何数据项，有一个且只有一个值。</span><span class="sxs-lookup"><span data-stu-id="cd79b-111">There is one and only one value for any data item for that instance of the activity.</span></span>  
  
 <span data-ttu-id="cd79b-112">活动用于向业务最终用户或信息工作者显示有关此工作单位的里程碑和数据。</span><span class="sxs-lookup"><span data-stu-id="cd79b-112">An activity is used to show the milestones and data about this unit of work to the business end user, or information worker.</span></span> <span data-ttu-id="cd79b-113">例如，在 BAM SDK 示例中定义的活动包含诸如“已支付”和“发送”这样的里程碑以及诸如“总额”这样的目标数据。</span><span class="sxs-lookup"><span data-stu-id="cd79b-113">For example, the activity defined in the BAM SDK sample contains milestones such as “Paid” and "Send," as well data of interest such as “Total Amount.”</span></span>  
  
 <span data-ttu-id="cd79b-114">BAM 活动常常直接映射到业务流程，尽管作为高级抽象概念，活动独立于 IT 基础结构的实际实现。</span><span class="sxs-lookup"><span data-stu-id="cd79b-114">BAM activities often map directly to a business process, although as a high-level abstraction an activity is independent of the actual implementation of your IT infrastructure.</span></span>  
  
 <span data-ttu-id="cd79b-115">开发人员可以只在特定活动的上下文公开实现的相关里程碑和数据，以此来维护这种抽象概念。</span><span class="sxs-lookup"><span data-stu-id="cd79b-115">Your job as a developer is to maintain this abstraction by exposing only the relevant milestones and data from the implementation in the context of a specific activity.</span></span>  
  
## <a name="what-is-a-continuation"></a><span data-ttu-id="cd79b-116">什么是继续符？</span><span class="sxs-lookup"><span data-stu-id="cd79b-116">What Is a Continuation?</span></span>  
 <span data-ttu-id="cd79b-117">继续符为 BAM 基础结构提供有关以下信息的指导：</span><span class="sxs-lookup"><span data-stu-id="cd79b-117">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
-   <span data-ttu-id="cd79b-118">事件应按何种顺序发生</span><span class="sxs-lookup"><span data-stu-id="cd79b-118">The order in which events are expected to occur</span></span>  
  
-   <span data-ttu-id="cd79b-119">对与事件项关联的唯一 ID 中的任何更改进行处理的方法</span><span class="sxs-lookup"><span data-stu-id="cd79b-119">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
 <span data-ttu-id="cd79b-120">有关延续和如何使用它们的详细信息，请参阅[延续任务，并 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="cd79b-120">For more information about Continuations and how they are used, see [Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md).</span></span>  
  
## <a name="what-is-a-reference"></a><span data-ttu-id="cd79b-121">什么是引用？</span><span class="sxs-lookup"><span data-stu-id="cd79b-121">What Is a Reference?</span></span>  
 <span data-ttu-id="cd79b-122">引用（也称为相关活动）指定了活动和其他某个项之间的关系。</span><span class="sxs-lookup"><span data-stu-id="cd79b-122">A reference (also known as a related activity) specifies a relationship between an activity and some other item.</span></span> <span data-ttu-id="cd79b-123">可能相关的项的示例为另一个活动或文档位置。</span><span class="sxs-lookup"><span data-stu-id="cd79b-123">Examples of items that can be related are another activity or a document location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd79b-124">将活动指定为相关活动时，与继续符活动不同的是，如果相关活动尚未完成，不妨碍完成当前活动。</span><span class="sxs-lookup"><span data-stu-id="cd79b-124">When you specify an activity as a related activity, the current activity is not, unlike a continuation activity, precluded from completing if the related activity has not completed.</span></span>  
  
## <a name="tracking-and-transactional-processing"></a><span data-ttu-id="cd79b-125">跟踪和事务性处理</span><span class="sxs-lookup"><span data-stu-id="cd79b-125">Tracking and Transactional Processing</span></span>  
 <span data-ttu-id="cd79b-126">通过编写 BAM 代码，您可以控制跟踪数据的方式，也就是说，通过跟踪还是事务性处理。</span><span class="sxs-lookup"><span data-stu-id="cd79b-126">Writing code for BAM gives you control of the way data is tracked, that is, through tracking or transactional processing.</span></span> <span data-ttu-id="cd79b-127">默认情况下，BAM 为跟踪和处理分配同等的重要性。</span><span class="sxs-lookup"><span data-stu-id="cd79b-127">By default, BAM assigns equal importance to tracking and processing.</span></span> <span data-ttu-id="cd79b-128">这意味着，如果跟踪功能或事务性处理失败，都不能继续进行。</span><span class="sxs-lookup"><span data-stu-id="cd79b-128">This means that if either the tracking function or the transaction process fails, neither is allowed to proceed.</span></span> <span data-ttu-id="cd79b-129">在跟踪数据库中不记录任何数据，同时事务回滚。</span><span class="sxs-lookup"><span data-stu-id="cd79b-129">Nothing is recorded in the tracking database and the transaction is rolled back.</span></span> <span data-ttu-id="cd79b-130">对于您的解决方案而言，这可能不是首选的跟踪方法。</span><span class="sxs-lookup"><span data-stu-id="cd79b-130">This may not be the preferred method of tracking for your solution.</span></span> <span data-ttu-id="cd79b-131">通过用于 BAM 的开发，您可以确定跟踪还是事务性处理这二者哪个优先。</span><span class="sxs-lookup"><span data-stu-id="cd79b-131">By developing for BAM you can determine whether tracking or transactional processing takes precedence.</span></span>  
  
 <span data-ttu-id="cd79b-132">下表对 BAM 中跟踪数据的模式进行了说明。</span><span class="sxs-lookup"><span data-stu-id="cd79b-132">The following table describes the modes of tracking data in BAM.</span></span>  
  
|<span data-ttu-id="cd79b-133">应用场景</span><span class="sxs-lookup"><span data-stu-id="cd79b-133">Scenario</span></span>|<span data-ttu-id="cd79b-134">“说明”</span><span class="sxs-lookup"><span data-stu-id="cd79b-134">Descriptions</span></span>|  
|--------------|------------------|  
|<span data-ttu-id="cd79b-135">跟踪优于处理</span><span class="sxs-lookup"><span data-stu-id="cd79b-135">Tracking Over Processing</span></span>|<span data-ttu-id="cd79b-136">如果流程成功，则写入跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="cd79b-136">If the process succeeds, write tracking information.</span></span><br /><br /> <span data-ttu-id="cd79b-137">如果流程失败，则写入关于故障的信息。</span><span class="sxs-lookup"><span data-stu-id="cd79b-137">If the process fails, write information about the failure.</span></span>|  
|<span data-ttu-id="cd79b-138">处理等于跟踪</span><span class="sxs-lookup"><span data-stu-id="cd79b-138">Processing Equal to Tracking</span></span>|<span data-ttu-id="cd79b-139">如果跟踪或处理失败，则回滚所有内容。</span><span class="sxs-lookup"><span data-stu-id="cd79b-139">If either tracking or processing fails, roll back everything.</span></span>|  
|<span data-ttu-id="cd79b-140">处理优于跟踪</span><span class="sxs-lookup"><span data-stu-id="cd79b-140">Processing Over Tracking</span></span>|<span data-ttu-id="cd79b-141">如果流程成功而跟踪功能失败，则继续处理。</span><span class="sxs-lookup"><span data-stu-id="cd79b-141">If the process succeeds and the tracking function fails, continue processing.</span></span>|