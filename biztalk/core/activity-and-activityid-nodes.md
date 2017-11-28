---
title: "活动和 ActivityID 节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ActivityID nodes [Tracking Profile Editor]
- Activity nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- activities [BAM], definitions
ms.assetid: 94d4130a-53c5-4cd5-916a-4a6bd9acbf23
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d100c88eec5f5a05db2bb651968aa987e3ec4e33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="activity-and-activityid-nodes"></a><span data-ttu-id="3231a-102">活动和 ActivityID 节点</span><span class="sxs-lookup"><span data-stu-id="3231a-102">Activity and ActivityID Nodes</span></span>
<span data-ttu-id="3231a-103">活动节点 和 ActivityID 节点用于包含和标识活动定义。</span><span class="sxs-lookup"><span data-stu-id="3231a-103">Activity and ActivityID nodes are used to contain and identify an activity definition.</span></span> <span data-ttu-id="3231a-104">活动节点是活动定义中项的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="3231a-104">The Activity node is the parent folder for the items in the activity definition.</span></span> <span data-ttu-id="3231a-105">所有数据项和业务事件节点都属于或包含于相关的活动节点中。</span><span class="sxs-lookup"><span data-stu-id="3231a-105">All data items and business event nodes are subordinate to and contained within the associated activity node.</span></span> <span data-ttu-id="3231a-106">活动节点的名称应该反映活动本身的名称。</span><span class="sxs-lookup"><span data-stu-id="3231a-106">The name of the Activity node should reflect the name of the activity itself.</span></span>  
  
 <span data-ttu-id="3231a-107">ActivityID 节点是活动定义中自动生成的项，用于保存活动的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3231a-107">The ActivityID node is an automatically generated item in the activity definition and is intended to hold a unique identifier for the activity.</span></span> <span data-ttu-id="3231a-108">ActivityID 节点可用于跟踪用户提供的标识符或系统生成的标识符。</span><span class="sxs-lookup"><span data-stu-id="3231a-108">The ActivityID node can be used to track user supplied identifiers or identifiers that are system generated.</span></span> <span data-ttu-id="3231a-109">例如，如果将采购订单的编号作为系统中所有采购订单的唯一标识符，则可以将此标识符用作 ActivityID，此时将从某些事件源（如采购订单架构中的采购订单编号字段）映射 ActivityID 的值。</span><span class="sxs-lookup"><span data-stu-id="3231a-109">For example, in a scenario in which you have purchase order number as a unique identifier across all purchase orders in the system, you can use it as the ActivityID, in which case you will map the value of the ActivityID from some event source, such as the PO number field in the purchase order schema.</span></span> <span data-ttu-id="3231a-110">反之，如果采购订单值不是唯一的，则可以不映射节点，BAM 将在运行时将自动生成唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3231a-110">On the other hand, if the purchase order value is not unique, then you can leave the node unmapped, and BAM will automatically generate unique identifiers at run-time.</span></span>  
  
 <span data-ttu-id="3231a-111">活动可关联至其他活动。</span><span class="sxs-lookup"><span data-stu-id="3231a-111">Activities can be related to other activities.</span></span> <span data-ttu-id="3231a-112">在某些方案中，这些关系明确地作为观察模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="3231a-112">In some scenarios these relationships are explicitly part of the observation model.</span></span>  <span data-ttu-id="3231a-113">具体而言，当用户视图中包含两个或多个活动时，这些活动之间将自动产生关系。</span><span class="sxs-lookup"><span data-stu-id="3231a-113">Specifically, when any user view includes two or more activities, there is an automatic relationship between those activities.</span></span>  <span data-ttu-id="3231a-114">存在这种关系后，在活动树的活动节点下将自动为每个已知的同级活动创建关系节点。</span><span class="sxs-lookup"><span data-stu-id="3231a-114">When such a relationship exists, a relationship node is automatically created in the activity tree, under the Activity node, for each known peer activity.</span></span> <span data-ttu-id="3231a-115">如果存在数据关系而不存在延伸视图，则您可以手动向活动树中添加关系节点。</span><span class="sxs-lookup"><span data-stu-id="3231a-115">In scenarios where there  is a data relationship and no spanning view exists, you can manually add a relationship node to  the activity tree.</span></span>  
  
 <span data-ttu-id="3231a-116">无论哪种情况，关系节点的用途都是为相关的活动提供标识符。</span><span class="sxs-lookup"><span data-stu-id="3231a-116">In either case, the purpose of the relationship node is to provide an identifier for the related activity.</span></span> <span data-ttu-id="3231a-117">例如，采购订单和发货可以有多对多关系（一个 PO 需要多次发货，一次发货可以运送多个 PO 的产品)。</span><span class="sxs-lookup"><span data-stu-id="3231a-117">For example, purchase orders and shipments can have a many-to-many relationship (one PO is fulfilled by multiple shipments; one shipment can carry a product satisfying many POs).</span></span>  <span data-ttu-id="3231a-118">每个采购订单的活动记录可以有多个指向相关发货的指针，而每个发货活动记录可以指向一个或多个采购订单。</span><span class="sxs-lookup"><span data-stu-id="3231a-118">The activity record for each purchase order can have multiple pointers to related shipments, and each shipment activity record could point to one or more Purchase Orders.</span></span>  <span data-ttu-id="3231a-119">如果用数据库术语来描述，关系节点的值就是指向其他活动的表的外键。</span><span class="sxs-lookup"><span data-stu-id="3231a-119">In database terms, the value of the relationship node is the foreign key into the table for the other activity.</span></span>  
  
## <a name="working-with-activity-id-nodes"></a><span data-ttu-id="3231a-120">使用 ActivityID 节点</span><span class="sxs-lookup"><span data-stu-id="3231a-120">Working with Activity ID nodes</span></span>  
 <span data-ttu-id="3231a-121">例如，考虑以下方案： EquityLoan 业务流程包含活动文件夹 LoanProcess。</span><span class="sxs-lookup"><span data-stu-id="3231a-121">For example, consider the following scenario: the EquityLoan orchestration contains the activity folder LoanProcess.</span></span> <span data-ttu-id="3231a-122">它引用如下所示的业务事件：</span><span class="sxs-lookup"><span data-stu-id="3231a-122">It references business events including the following:</span></span>  
  
-   <span data-ttu-id="3231a-123">LoanApplicationReceived</span><span class="sxs-lookup"><span data-stu-id="3231a-123">LoanApplicationReceived</span></span>  
  
-   <span data-ttu-id="3231a-124">CHRequest</span><span class="sxs-lookup"><span data-stu-id="3231a-124">CHRequest</span></span>  
  
-   <span data-ttu-id="3231a-125">CHResponse</span><span class="sxs-lookup"><span data-stu-id="3231a-125">CHResponse</span></span>  
  
-   <span data-ttu-id="3231a-126">AppraisalRequest</span><span class="sxs-lookup"><span data-stu-id="3231a-126">AppraisalRequest</span></span>  
  
-   <span data-ttu-id="3231a-127">AppraisalResponse</span><span class="sxs-lookup"><span data-stu-id="3231a-127">AppraisalResponse</span></span>  
  
-   <span data-ttu-id="3231a-128">已同意</span><span class="sxs-lookup"><span data-stu-id="3231a-128">Approved</span></span>  
  
-   <span data-ttu-id="3231a-129">拒绝</span><span class="sxs-lookup"><span data-stu-id="3231a-129">Denied</span></span>  
  
 <span data-ttu-id="3231a-130">解决方案开发人员使用 ActivityID 节点可以提取唯一标识活动的数据，如采购订单编号；而对于实例情形而言，应该提取的是消息的 SSN 字段。</span><span class="sxs-lookup"><span data-stu-id="3231a-130">The ActivityID node enables the solution developer to extract data that uniquely identifies the activity, such as a purchase order number, or, in the case of the sample scenario, the SSN field of the message.</span></span> <span data-ttu-id="3231a-131">如果没有向 ActivityID 节点拖放任何数据，则自动生成的 GUID 将标识业务活动。</span><span class="sxs-lookup"><span data-stu-id="3231a-131">If you do not drag any data to the ActivityID node, an automatically generated GUID identifies the business activities.</span></span>  
  
 <span data-ttu-id="3231a-132">若要在不同业务流程中的业务事件或里程碑之间定义关系，则目标业务流程必须引用 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="3231a-132">To define the relationship between business events or milestones in different orchestrations, the target orchestration must reference the ActivityID.</span></span> <span data-ttu-id="3231a-133">有关如何实现使用键入的关系的详细信息，请参阅[关系节点](../core/relationship-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="3231a-133">For more information about how to implement relationships using TPE, see [Relationship Nodes](../core/relationship-nodes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3231a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3231a-134">See Also</span></span>  
 [<span data-ttu-id="3231a-135">键入活动视图节点</span><span class="sxs-lookup"><span data-stu-id="3231a-135">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)