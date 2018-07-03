---
title: 实时聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- aggregations [BAM], real-time data
ms.assetid: 0ef44641-e067-4108-b318-f4373ca8fa8f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cfb7d2c50b011743f652fd261eed68e810db10f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981038"
---
# <a name="real-time-aggregations"></a><span data-ttu-id="c2cd9-102">实时聚合</span><span class="sxs-lookup"><span data-stu-id="c2cd9-102">Real-Time Aggregations</span></span>
<span data-ttu-id="c2cd9-103">在某些情况下，多维聚合的特定切片对时间非常敏感，需要它们实时可用。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-103">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="c2cd9-104">例如，您的企业出售的是容易腐烂的产品，因而您希望各个交货阶段的产品数量的聚合实时可用。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="c2cd9-105">同时，您还需要在月底获得其他聚合，如典型客户的年龄，以便进行商业智能分析。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
 <span data-ttu-id="c2cd9-106">BAM 将实时聚合 (RTA) 实现为活动存储表中由触发器维护的表。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-106">BAM implements real-time aggregation (RTA) as a table maintained by triggers from the activity storage tables.</span></span> <span data-ttu-id="c2cd9-107">当您的企业处理采购订单 (PO) 时，RTA 视图可能类似下图中的示例。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-107">In the case when your business deals with purchase orders (PO), the RTA view may look like the example in the following figure.</span></span>  
  
 <span data-ttu-id="c2cd9-108">![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")</span><span class="sxs-lookup"><span data-stu-id="c2cd9-108">![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")</span></span>  
<span data-ttu-id="c2cd9-109">BAM 实时聚合</span><span class="sxs-lookup"><span data-stu-id="c2cd9-109">BAM Real-time Aggregations</span></span>  
  
 <span data-ttu-id="c2cd9-110">在此图中，如果接收到来自 Redmond 的 $100 新采购订单，则 BAM 将执行 `Count=Count+1` 和 `Amount=Amount+$100` 操作，在相应行 {Redmond, InProcess} 的单元格中加入新项的值。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-110">In this figure, if a new PO of $100 from Redmond is received, BAM adds a contribution to the cells in the corresponding row for {Redmond, InProcess} by performing an operation like `Count=Count+1` and `Amount=Amount+$100`.</span></span>  
  
 <span data-ttu-id="c2cd9-111">随后，如果该订单已发货，则 BAM 将从行 {Redmond, InProgress} 中减去此项的值，并将它添加到行 {Redmond, Shipped} 中。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-111">Later, if the same order ships, then BAM removes this contribution from the row {Redmond, InProcess} and adds it to the row {Redmond, Shipped}.</span></span>  
  
 <span data-ttu-id="c2cd9-112">BAM 在给定联机时段内维护 RTA 的数据，过后则删除这些数据。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-112">BAM maintains the data inside RTA for a given online window, and then deletes it.</span></span> <span data-ttu-id="c2cd9-113">可以通过更改相应的行的表的配置的联机时段**bam_Metadata_RealTimeAggregations**。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-113">You can configure the online window by changing the corresponding row of the table **bam_Metadata_RealTimeAggregations**.</span></span>  
  
 <span data-ttu-id="c2cd9-114">使用实时聚合还应注意以下问题：</span><span class="sxs-lookup"><span data-stu-id="c2cd9-114">The following statements also apply to real-time aggregations:</span></span>  
  
- <span data-ttu-id="c2cd9-115">实时聚合会显著影响 BAM 写入数据的速度。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-115">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="c2cd9-116">因而，应该只将最重要的聚合结构切片定义为 RTA。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-116">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
- <span data-ttu-id="c2cd9-117">实时聚合的维度级别限制为 14。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-117">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="c2cd9-118">例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-118">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="c2cd9-119">对于进度维度，级别数为树的深度，而对于时间维度，级别数是所有子单位的数目。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-119">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="c2cd9-120">例如，如果时间维度为年、月、日和小时，则计为四个级别。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-120">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
- <span data-ttu-id="c2cd9-121">BAM 不支持类型的实时聚合**最小**并**最大**。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-121">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="c2cd9-122">BAM 支持聚合**计数**， **Sum**，并**平均**。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-122">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
- <span data-ttu-id="c2cd9-123">必须始终为 RTA 创建时间维度，并且始终将它用于所有数据切片，这是因为 RTA 中的数据是基于服务器时间戳（而不是任何特定的业务里程碑）老化的。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-123">You must always create a time dimension for RTA and always use it in all data slices, because the data in RTA is aged based on the server time stamp, and not on any specific business milestone.</span></span>  
  
- <span data-ttu-id="c2cd9-124">不要定义使用同一个 BAM 活动的多个 RTA。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-124">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="c2cd9-125">否则，当您存档 BAM 数据时，RTA 数据将不正确。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-125">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
  <span data-ttu-id="c2cd9-126">实时聚合会显著影响 BAM 写入数据的速度。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-126">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="c2cd9-127">因而，应该只将最重要的聚合结构切片定义为 RTA。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-127">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
  <span data-ttu-id="c2cd9-128">实时聚合的维度级别限制为 14。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-128">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="c2cd9-129">例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-129">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="c2cd9-130">对于进度维度，级别数为树的深度，而对于时间维度，级别数是所有子单位的数目。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-130">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="c2cd9-131">例如，如果时间维度为年、月、日和小时，则计为四个级别。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-131">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
  <span data-ttu-id="c2cd9-132">BAM 不支持类型的实时聚合**最小**并**最大**。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-132">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="c2cd9-133">BAM 支持聚合**计数**， **Sum**，并**平均**。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-133">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
  <span data-ttu-id="c2cd9-134">不要定义使用同一个 BAM 活动的多个 RTA。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-134">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="c2cd9-135">否则，当您存档 BAM 数据时，RTA 数据将不正确。</span><span class="sxs-lookup"><span data-stu-id="c2cd9-135">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cd9-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2cd9-136">See Also</span></span>  
 [<span data-ttu-id="c2cd9-137">聚合概述</span><span class="sxs-lookup"><span data-stu-id="c2cd9-137">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)