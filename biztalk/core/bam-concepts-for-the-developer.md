---
title: 开发人员的 BAM 概念 |Microsoft Docs
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
ms.openlocfilehash: ec027ef80ebaa9f1c8954e09722156a48c843a70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358607"
---
# <a name="bam-concepts-for-the-developer"></a><span data-ttu-id="5d191-102">开发人员的 BAM 概念</span><span class="sxs-lookup"><span data-stu-id="5d191-102">BAM Concepts for the Developer</span></span>
<span data-ttu-id="5d191-103">作为 BAM 开发人员，您需要熟悉重要的 BAM 概念，如活动、 继续符和引用。</span><span class="sxs-lookup"><span data-stu-id="5d191-103">As a BAM developer, you need to be familiar with important BAM concepts, such as activities, continuations, and references.</span></span> <span data-ttu-id="5d191-104">您还应该了解跟踪和事务性处理之间的差异。</span><span class="sxs-lookup"><span data-stu-id="5d191-104">You should also understand the differences between tracking and transactional processing.</span></span>  
  
## <a name="what-is-a-bam-activity"></a><span data-ttu-id="5d191-105">什么是 BAM 活动？</span><span class="sxs-lookup"><span data-stu-id="5d191-105">What Is a BAM Activity?</span></span>  
 <span data-ttu-id="5d191-106">BAM 活动是哪些数据是业务流程 （如单个 PO) 中的项有趣的定义。</span><span class="sxs-lookup"><span data-stu-id="5d191-106">A BAM activity is the definition of what data is interesting for an item in the business process (such as a single PO).</span></span> <span data-ttu-id="5d191-107">它定义了 BAM 数据库中包括的列。</span><span class="sxs-lookup"><span data-stu-id="5d191-107">It defines what columns are in the BAM database.</span></span>  
  
 <span data-ttu-id="5d191-108">活动的实例表示在企业中，例如采购订单或贷款申请的工作单元。</span><span class="sxs-lookup"><span data-stu-id="5d191-108">An instance of an activity represents a unit of work in the business, such as a purchase order or a loan application.</span></span> <span data-ttu-id="5d191-109">活动指定了里程碑 （活动的历史记录） 和感兴趣的数据的列表。</span><span class="sxs-lookup"><span data-stu-id="5d191-109">An activity specifies a list of milestones (the history of the activity) and data of interest.</span></span> <span data-ttu-id="5d191-110">活动实例表现为 BAM 主导入数据库中的单个行。</span><span class="sxs-lookup"><span data-stu-id="5d191-110">An instance of an activity is manifested as a single row in the BAM Primary Import database.</span></span> <span data-ttu-id="5d191-111">没有为该实例的活动的任何数据项的一个且只有一个值。</span><span class="sxs-lookup"><span data-stu-id="5d191-111">There is one and only one value for any data item for that instance of the activity.</span></span>  
  
 <span data-ttu-id="5d191-112">活动用于向业务最终用户或信息工作者显示里程碑和有关此工作单位的数据。</span><span class="sxs-lookup"><span data-stu-id="5d191-112">An activity is used to show the milestones and data about this unit of work to the business end user, or information worker.</span></span> <span data-ttu-id="5d191-113">例如，BAM SDK 示例中定义的活动以及如"Total Amount"。 所需的数据作为包含"已支付"和"发送"等里程碑</span><span class="sxs-lookup"><span data-stu-id="5d191-113">For example, the activity defined in the BAM SDK sample contains milestones such as “Paid” and "Send," as well data of interest such as “Total Amount.”</span></span>  
  
 <span data-ttu-id="5d191-114">BAM 活动常常直接映射到业务流程，尽管作为高级抽象活动是独立于你的 IT 基础结构的实际实现。</span><span class="sxs-lookup"><span data-stu-id="5d191-114">BAM activities often map directly to a business process, although as a high-level abstraction an activity is independent of the actual implementation of your IT infrastructure.</span></span>  
  
 <span data-ttu-id="5d191-115">您作为开发人员的工作是通过公开的相关里程碑和上下文中的特定活动的实现中的数据来保持这种抽象。</span><span class="sxs-lookup"><span data-stu-id="5d191-115">Your job as a developer is to maintain this abstraction by exposing only the relevant milestones and data from the implementation in the context of a specific activity.</span></span>  
  
## <a name="what-is-a-continuation"></a><span data-ttu-id="5d191-116">延续是什么？</span><span class="sxs-lookup"><span data-stu-id="5d191-116">What Is a Continuation?</span></span>  
 <span data-ttu-id="5d191-117">延续任务提供指导到 BAM 基础结构有关的以下信息：</span><span class="sxs-lookup"><span data-stu-id="5d191-117">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
- <span data-ttu-id="5d191-118">事件预期发生的顺序</span><span class="sxs-lookup"><span data-stu-id="5d191-118">The order in which events are expected to occur</span></span>  
  
- <span data-ttu-id="5d191-119">一种方法来处理任何更改的项对与事件相关联的唯一 ID</span><span class="sxs-lookup"><span data-stu-id="5d191-119">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
  <span data-ttu-id="5d191-120">有关继续符及其使用方式的详细信息，请参阅[Continuation 和 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="5d191-120">For more information about Continuations and how they are used, see [Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md).</span></span>  
  
## <a name="what-is-a-reference"></a><span data-ttu-id="5d191-121">什么是引用？</span><span class="sxs-lookup"><span data-stu-id="5d191-121">What Is a Reference?</span></span>  
 <span data-ttu-id="5d191-122">（也称为相关活动） 的引用指定一个活动，还有一些其他项之间的关系。</span><span class="sxs-lookup"><span data-stu-id="5d191-122">A reference (also known as a related activity) specifies a relationship between an activity and some other item.</span></span> <span data-ttu-id="5d191-123">可以与相关的项的示例为另一个活动或文档位置。</span><span class="sxs-lookup"><span data-stu-id="5d191-123">Examples of items that can be related are another activity or a document location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d191-124">当活动指定为相关活动时，当前活动是不是，与继续符活动，不同妨碍完成如果相关的活动尚未完成。</span><span class="sxs-lookup"><span data-stu-id="5d191-124">When you specify an activity as a related activity, the current activity is not, unlike a continuation activity, precluded from completing if the related activity has not completed.</span></span>  
  
## <a name="tracking-and-transactional-processing"></a><span data-ttu-id="5d191-125">跟踪和事务性处理</span><span class="sxs-lookup"><span data-stu-id="5d191-125">Tracking and Transactional Processing</span></span>  
 <span data-ttu-id="5d191-126">编写 BAM 代码，您可以控制数据的方式被跟踪，即，通过跟踪还是事务性处理。</span><span class="sxs-lookup"><span data-stu-id="5d191-126">Writing code for BAM gives you control of the way data is tracked, that is, through tracking or transactional processing.</span></span> <span data-ttu-id="5d191-127">默认情况下，BAM 为跟踪和处理分配同等的重要性。</span><span class="sxs-lookup"><span data-stu-id="5d191-127">By default, BAM assigns equal importance to tracking and processing.</span></span> <span data-ttu-id="5d191-128">这意味着，如果跟踪功能或事务过程失败，既不允许继续执行。</span><span class="sxs-lookup"><span data-stu-id="5d191-128">This means that if either the tracking function or the transaction process fails, neither is allowed to proceed.</span></span> <span data-ttu-id="5d191-129">跟踪数据库中记录执行任何操作并回滚事务。</span><span class="sxs-lookup"><span data-stu-id="5d191-129">Nothing is recorded in the tracking database and the transaction is rolled back.</span></span> <span data-ttu-id="5d191-130">这可能不是跟踪的你的解决方案的首选的方法。</span><span class="sxs-lookup"><span data-stu-id="5d191-130">This may not be the preferred method of tracking for your solution.</span></span> <span data-ttu-id="5d191-131">通过用于 BAM 的开发可以确定是否跟踪或事务处理优先。</span><span class="sxs-lookup"><span data-stu-id="5d191-131">By developing for BAM you can determine whether tracking or transactional processing takes precedence.</span></span>  
  
 <span data-ttu-id="5d191-132">下表描述了 BAM 中跟踪数据的模式。</span><span class="sxs-lookup"><span data-stu-id="5d191-132">The following table describes the modes of tracking data in BAM.</span></span>  
  
|<span data-ttu-id="5d191-133">应用场景</span><span class="sxs-lookup"><span data-stu-id="5d191-133">Scenario</span></span>|<span data-ttu-id="5d191-134">“说明”</span><span class="sxs-lookup"><span data-stu-id="5d191-134">Descriptions</span></span>|  
|--------------|------------------|  
|<span data-ttu-id="5d191-135">跟踪优于处理</span><span class="sxs-lookup"><span data-stu-id="5d191-135">Tracking Over Processing</span></span>|<span data-ttu-id="5d191-136">如果该过程成功，则写入跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="5d191-136">If the process succeeds, write tracking information.</span></span><br /><br /> <span data-ttu-id="5d191-137">如果该进程将失败，写入与失败有关的信息。</span><span class="sxs-lookup"><span data-stu-id="5d191-137">If the process fails, write information about the failure.</span></span>|  
|<span data-ttu-id="5d191-138">处理等于跟踪</span><span class="sxs-lookup"><span data-stu-id="5d191-138">Processing Equal to Tracking</span></span>|<span data-ttu-id="5d191-139">如果跟踪或处理失败，则回滚所有内容。</span><span class="sxs-lookup"><span data-stu-id="5d191-139">If either tracking or processing fails, roll back everything.</span></span>|  
|<span data-ttu-id="5d191-140">处理优于跟踪</span><span class="sxs-lookup"><span data-stu-id="5d191-140">Processing Over Tracking</span></span>|<span data-ttu-id="5d191-141">如果流程成功而跟踪功能失败，继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="5d191-141">If the process succeeds and the tracking function fails, continue processing.</span></span>|