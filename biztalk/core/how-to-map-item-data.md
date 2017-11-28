---
title: "如何将映射项数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data extraction
- orchestrations, data extraction
- orchestrations, tracking profiles
- tracking profiles, orchestrations
- tracking profiles, data extraction
ms.assetid: ae8b395e-152a-4e08-af31-3c9276f52711
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdfd722e1610be02c06dd6e2a9597e13c0f1e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-item-data"></a><span data-ttu-id="b7486-102">如何映射项数据</span><span class="sxs-lookup"><span data-stu-id="b7486-102">How to Map Item Data</span></span>
<span data-ttu-id="b7486-103">映射项数据可以定义如何从业务流程中提取数据。</span><span class="sxs-lookup"><span data-stu-id="b7486-103">You map item data to define the data extraction from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7486-104">在创建跟踪配置文件时，必须确保映射的数据类型值与活动项兼容。</span><span class="sxs-lookup"><span data-stu-id="b7486-104">You must be certain to map data type values that are compatible with the activity items when creating tracking profiles.</span></span> <span data-ttu-id="b7486-105">如果数据类型不兼容，将出现 BAM 运行时错误。</span><span class="sxs-lookup"><span data-stu-id="b7486-105">If the data types are not compatible you will receive a BAM runtime error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7486-106">在映射里程碑（如日期/时间戳）时，被映射的数据必须符合日期时间戳的 SQL 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="b7486-106">When mapping milestones, such as Date/Time stamps, the data being mapped must conform to the SQL string representation of a date time stamp.</span></span> <span data-ttu-id="b7486-107">XML DateTime 格式的 DateTime 数据如果采用 YYYY-MM-DDTHH:MM:SS.mmm-HH:MM 格式，则不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7486-107">DateTime data in the XML DateTime format that is formatted in the following manner, YYYY-MM-DDTHH:MM:SS.mmm-HH:MM, is not supported.</span></span>  
>   
>  <span data-ttu-id="b7486-108">例如，不支持 1999-05-31T13:20:00.000-05:00 日期字符串。</span><span class="sxs-lookup"><span data-stu-id="b7486-108">For example, the following date string, 1999-05-31T13:20:00.000-05:00, is not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b7486-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="b7486-109">Prerequisites</span></span>  
 <span data-ttu-id="b7486-110">部署要连接的 BAM 活动定义和业务流程。</span><span class="sxs-lookup"><span data-stu-id="b7486-110">Deployed BAM activity definitions and orchestrations that you will connect.</span></span>  
  
### <a name="how-to-map-item-data"></a><span data-ttu-id="b7486-111">如何将映射项数据</span><span class="sxs-lookup"><span data-stu-id="b7486-111">How to map item data</span></span>  
  
1.  <span data-ttu-id="b7486-112">打开现有的跟踪配置文件，或创建一个新跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="b7486-112">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="b7486-113">有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="b7486-113">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="b7486-114">在这种情况下，将导入一个名为 LoanProcessBamDef 的活动定义。</span><span class="sxs-lookup"><span data-stu-id="b7486-114">In the scenario, an activity definition called LoanProcessBamDef is imported.</span></span> <span data-ttu-id="b7486-115">它包含**LoanProcess**活动节点，与客户的**SSN**作为 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="b7486-115">It contains the **LoanProcess** activity node, with a customer's **SSN** as an ActivityID.</span></span> <span data-ttu-id="b7486-116">有关详细信息，请参阅[活动和 ActivityID 节点](../core/activity-and-activityid-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="b7486-116">For more information, see [Activity and ActivityID Nodes](../core/activity-and-activityid-nodes.md).</span></span>  
  
3.  <span data-ttu-id="b7486-117">确保每个活动都有一个要跟踪的 ActivityID 或 ContinuationID 数据项，如客户 SSN。</span><span class="sxs-lookup"><span data-stu-id="b7486-117">Ensure that every activity has an ActivityID or a ContinuationID data item, such as customer SSN, to track.</span></span>  
  
4.  <span data-ttu-id="b7486-118">将业务流程操作映射到相应的业务事件文件夹，以指示要跟踪的事件。例如，在贷款处理方案中的以下项，及其他将拖动下**LoanProcess**活动文件夹：</span><span class="sxs-lookup"><span data-stu-id="b7486-118">Map orchestration actions to the appropriate business events folder to indicate the event to track. For example, in a loan processing scenario the following items, among others, would be dragged under the **LoanProcess** activity folder:</span></span>  
  
    -   <span data-ttu-id="b7486-119">**LoanApplicationReceived**</span><span class="sxs-lookup"><span data-stu-id="b7486-119">**LoanApplicationReceived**</span></span>  
  
    -   <span data-ttu-id="b7486-120">**CreditHistoryRequest**</span><span class="sxs-lookup"><span data-stu-id="b7486-120">**CreditHistoryRequest**</span></span>  
  
    -   <span data-ttu-id="b7486-121">**CreditHistoryResponse**</span><span class="sxs-lookup"><span data-stu-id="b7486-121">**CreditHistoryResponse**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7486-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7486-122">See Also</span></span>  
 <span data-ttu-id="b7486-123">[数据项节点](../core/data-item-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="b7486-123">[Data Item Nodes](../core/data-item-nodes.md) </span></span>  
 [<span data-ttu-id="b7486-124">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b7486-124">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)