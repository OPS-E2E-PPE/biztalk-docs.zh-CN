---
title: 活动和 ActivityID 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ActivityID nodes [Tracking Profile Editor]
- Activity nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- activities [BAM], definitions
ms.assetid: 94d4130a-53c5-4cd5-916a-4a6bd9acbf23
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ad89c82f7eac4aca14ca3d424a5bda6056f95f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361821"
---
# <a name="activity-and-activityid-nodes"></a><span data-ttu-id="d9eee-102">活动和 ActivityID 节点</span><span class="sxs-lookup"><span data-stu-id="d9eee-102">Activity and ActivityID Nodes</span></span>
<span data-ttu-id="d9eee-103">活动和 ActivityID 节点用于包含和标识活动定义。</span><span class="sxs-lookup"><span data-stu-id="d9eee-103">Activity and ActivityID nodes are used to contain and identify an activity definition.</span></span> <span data-ttu-id="d9eee-104">活动节点是活动定义中的项的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="d9eee-104">The Activity node is the parent folder for the items in the activity definition.</span></span> <span data-ttu-id="d9eee-105">所有数据项和业务事件节点都都属于或包含在相关的活动节点。</span><span class="sxs-lookup"><span data-stu-id="d9eee-105">All data items and business event nodes are subordinate to and contained within the associated activity node.</span></span> <span data-ttu-id="d9eee-106">活动节点的名称应反映活动本身的名称。</span><span class="sxs-lookup"><span data-stu-id="d9eee-106">The name of the Activity node should reflect the name of the activity itself.</span></span>  
  
 <span data-ttu-id="d9eee-107">ActivityID 节点是活动定义中自动生成的项，旨在用于保存活动的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d9eee-107">The ActivityID node is an automatically generated item in the activity definition and is intended to hold a unique identifier for the activity.</span></span> <span data-ttu-id="d9eee-108">ActivityID 节点可用于跟踪用户提供的标识符或系统生成的标识符。</span><span class="sxs-lookup"><span data-stu-id="d9eee-108">The ActivityID node can be used to track user supplied identifiers or identifiers that are system generated.</span></span> <span data-ttu-id="d9eee-109">例如，在其中有采购订单号的唯一标识符作为所有采购订单的系统中的情况下，您可以使用它作为 ActivityID，在这种情况下将映射从某些事件源，例如采购订单编号字段中的 ActivityID 的值 采购订单架构。</span><span class="sxs-lookup"><span data-stu-id="d9eee-109">For example, in a scenario in which you have purchase order number as a unique identifier across all purchase orders in the system, you can use it as the ActivityID, in which case you will map the value of the ActivityID from some event source, such as the PO number field in the purchase order schema.</span></span> <span data-ttu-id="d9eee-110">但是，如果采购订单值不是唯一的则可以将映射节点，并且 BAM 将自动生成在运行时的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d9eee-110">On the other hand, if the purchase order value is not unique, then you can leave the node unmapped, and BAM will automatically generate unique identifiers at run-time.</span></span>  
  
 <span data-ttu-id="d9eee-111">可以与其他活动相关的活动。</span><span class="sxs-lookup"><span data-stu-id="d9eee-111">Activities can be related to other activities.</span></span> <span data-ttu-id="d9eee-112">在某些情况下这些关系是显式的观察模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9eee-112">In some scenarios these relationships are explicitly part of the observation model.</span></span>  <span data-ttu-id="d9eee-113">具体而言，当用户视图中包含两个或多个活动，自动产生关系之间没有这些活动。</span><span class="sxs-lookup"><span data-stu-id="d9eee-113">Specifically, when any user view includes two or more activities, there is an automatic relationship between those activities.</span></span>  <span data-ttu-id="d9eee-114">存在此类关系时，将自动在活动树中，每个已知的同级活动的活动节点下创建关系节点。</span><span class="sxs-lookup"><span data-stu-id="d9eee-114">When such a relationship exists, a relationship node is automatically created in the activity tree, under the Activity node, for each known peer activity.</span></span> <span data-ttu-id="d9eee-115">在方案中，为数据关系，不存在延伸视图，可以手动添加关系节点到活动树。</span><span class="sxs-lookup"><span data-stu-id="d9eee-115">In scenarios where there  is a data relationship and no spanning view exists, you can manually add a relationship node to  the activity tree.</span></span>  
  
 <span data-ttu-id="d9eee-116">在任一情况下，关系节点的目的是为相关的活动提供标识符。</span><span class="sxs-lookup"><span data-stu-id="d9eee-116">In either case, the purpose of the relationship node is to provide an identifier for the related activity.</span></span> <span data-ttu-id="d9eee-117">例如，采购订单和发货可以有多对多关系 （一个 PO 需要多次发货情况; 一次发货可以满足许多 POs 产品）。</span><span class="sxs-lookup"><span data-stu-id="d9eee-117">For example, purchase orders and shipments can have a many-to-many relationship (one PO is fulfilled by multiple shipments; one shipment can carry a product satisfying many POs).</span></span>  <span data-ttu-id="d9eee-118">每个采购订单的活动记录可以有多个指向相关发货和每个发货活动记录可以指向一个或多个采购订单。</span><span class="sxs-lookup"><span data-stu-id="d9eee-118">The activity record for each purchase order can have multiple pointers to related shipments, and each shipment activity record could point to one or more Purchase Orders.</span></span>  <span data-ttu-id="d9eee-119">在数据库术语中，关系节点的值是其他活动到表的外键。</span><span class="sxs-lookup"><span data-stu-id="d9eee-119">In database terms, the value of the relationship node is the foreign key into the table for the other activity.</span></span>  
  
## <a name="working-with-activity-id-nodes"></a><span data-ttu-id="d9eee-120">使用活动 ID 节点</span><span class="sxs-lookup"><span data-stu-id="d9eee-120">Working with Activity ID nodes</span></span>  
 <span data-ttu-id="d9eee-121">例如，考虑以下方案： EquityLoan 业务流程包含活动文件夹 LoanProcess。</span><span class="sxs-lookup"><span data-stu-id="d9eee-121">For example, consider the following scenario: the EquityLoan orchestration contains the activity folder LoanProcess.</span></span> <span data-ttu-id="d9eee-122">它引用了业务事件包括以下：</span><span class="sxs-lookup"><span data-stu-id="d9eee-122">It references business events including the following:</span></span>  
  
- <span data-ttu-id="d9eee-123">LoanApplicationReceived</span><span class="sxs-lookup"><span data-stu-id="d9eee-123">LoanApplicationReceived</span></span>  
  
- <span data-ttu-id="d9eee-124">CHRequest</span><span class="sxs-lookup"><span data-stu-id="d9eee-124">CHRequest</span></span>  
  
- <span data-ttu-id="d9eee-125">CHResponse</span><span class="sxs-lookup"><span data-stu-id="d9eee-125">CHResponse</span></span>  
  
- <span data-ttu-id="d9eee-126">AppraisalRequest</span><span class="sxs-lookup"><span data-stu-id="d9eee-126">AppraisalRequest</span></span>  
  
- <span data-ttu-id="d9eee-127">AppraisalResponse</span><span class="sxs-lookup"><span data-stu-id="d9eee-127">AppraisalResponse</span></span>  
  
- <span data-ttu-id="d9eee-128">已批准</span><span class="sxs-lookup"><span data-stu-id="d9eee-128">Approved</span></span>  
  
- <span data-ttu-id="d9eee-129">拒绝</span><span class="sxs-lookup"><span data-stu-id="d9eee-129">Denied</span></span>  
  
  <span data-ttu-id="d9eee-130">解决方案开发人员，以提取数据，唯一标识活动，例如采购订单编号，或者，在示例方案中，该消息的 SSN 字段的情况下使用 ActivityID 节点可以。</span><span class="sxs-lookup"><span data-stu-id="d9eee-130">The ActivityID node enables the solution developer to extract data that uniquely identifies the activity, such as a purchase order number, or, in the case of the sample scenario, the SSN field of the message.</span></span> <span data-ttu-id="d9eee-131">如果向 ActivityID 节点不拖放任何数据，自动生成的 GUID 标识的业务活动。</span><span class="sxs-lookup"><span data-stu-id="d9eee-131">If you do not drag any data to the ActivityID node, an automatically generated GUID identifies the business activities.</span></span>  
  
  <span data-ttu-id="d9eee-132">若要在不同的业务流程中定义业务事件或里程碑之间的关系，则目标业务流程必须引用 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="d9eee-132">To define the relationship between business events or milestones in different orchestrations, the target orchestration must reference the ActivityID.</span></span> <span data-ttu-id="d9eee-133">有关如何使用 TPE 实现关系的详细信息，请参阅[关系节点](../core/relationship-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="d9eee-133">For more information about how to implement relationships using TPE, see [Relationship Nodes](../core/relationship-nodes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9eee-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9eee-134">See Also</span></span>  
 [<span data-ttu-id="d9eee-135">“TPE 活动视图”节点</span><span class="sxs-lookup"><span data-stu-id="d9eee-135">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)