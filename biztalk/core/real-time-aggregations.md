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
ms.openlocfilehash: d76a61fef1f25933e4ac35071e5890ab16606768
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398277"
---
# <a name="real-time-aggregations"></a><span data-ttu-id="ab123-102">实时聚合</span><span class="sxs-lookup"><span data-stu-id="ab123-102">Real-Time Aggregations</span></span>
<span data-ttu-id="ab123-103">在某些情况下，多维聚合的特定切片是时间非常敏感，希望它们在真实时间中不可用。</span><span class="sxs-lookup"><span data-stu-id="ab123-103">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="ab123-104">例如，你的业务销售腐烂的产品和所需的产品数量传递要在真实时间中可用的不同阶段中的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="ab123-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="ab123-105">同时，您希望其他聚合，如年龄的典型客户，但只会在商业智能分析的月结束。</span><span class="sxs-lookup"><span data-stu-id="ab123-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
 <span data-ttu-id="ab123-106">BAM 为活动存储表中由触发器维护的表实现实时聚合 (RTA)。</span><span class="sxs-lookup"><span data-stu-id="ab123-106">BAM implements real-time aggregation (RTA) as a table maintained by triggers from the activity storage tables.</span></span> <span data-ttu-id="ab123-107">在这种情况时你的业务处理采购订单 (PO) 时，RTA 视图可能类似下图中的示例。</span><span class="sxs-lookup"><span data-stu-id="ab123-107">In the case when your business deals with purchase orders (PO), the RTA view may look like the example in the following figure.</span></span>  
  
 <span data-ttu-id="ab123-108">![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")</span><span class="sxs-lookup"><span data-stu-id="ab123-108">![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")</span></span>  
<span data-ttu-id="ab123-109">BAM 实时聚合</span><span class="sxs-lookup"><span data-stu-id="ab123-109">BAM Real-time Aggregations</span></span>  
  
 <span data-ttu-id="ab123-110">在此图中，如果收到来自 Redmond 的新采购订单，则 BAM 将对应行中单元格的供稿 {redmond，InProcess} 执行等操作`Count=Count+1`和`Amount=Amount+$100`。</span><span class="sxs-lookup"><span data-stu-id="ab123-110">In this figure, if a new PO of $100 from Redmond is received, BAM adds a contribution to the cells in the corresponding row for {Redmond, InProcess} by performing an operation like `Count=Count+1` and `Amount=Amount+$100`.</span></span>  
  
 <span data-ttu-id="ab123-111">更高版本，如果订单，然后 BAM 从行 {Redmond，InProcess} 中删除此发布内容并将其添加到行 {Redmond，Shipped}。</span><span class="sxs-lookup"><span data-stu-id="ab123-111">Later, if the same order ships, then BAM removes this contribution from the row {Redmond, InProcess} and adds it to the row {Redmond, Shipped}.</span></span>  
  
 <span data-ttu-id="ab123-112">BAM 在给定的联机时段内 RTA 数据维护，然后删除它。</span><span class="sxs-lookup"><span data-stu-id="ab123-112">BAM maintains the data inside RTA for a given online window, and then deletes it.</span></span> <span data-ttu-id="ab123-113">可以通过更改相应的行的表的配置的联机时段**bam_Metadata_RealTimeAggregations**。</span><span class="sxs-lookup"><span data-stu-id="ab123-113">You can configure the online window by changing the corresponding row of the table **bam_Metadata_RealTimeAggregations**.</span></span>  
  
 <span data-ttu-id="ab123-114">以下语句也适用于实时聚合：</span><span class="sxs-lookup"><span data-stu-id="ab123-114">The following statements also apply to real-time aggregations:</span></span>  
  
- <span data-ttu-id="ab123-115">实时聚合会显著影响 BAM 写入数据的速度。</span><span class="sxs-lookup"><span data-stu-id="ab123-115">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="ab123-116">因此，只应定义为 RTA 的最重要的聚合结构切片。</span><span class="sxs-lookup"><span data-stu-id="ab123-116">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
- <span data-ttu-id="ab123-117">实时聚合的维度级别限制为 14。</span><span class="sxs-lookup"><span data-stu-id="ab123-117">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="ab123-118">例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。</span><span class="sxs-lookup"><span data-stu-id="ab123-118">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="ab123-119">对于进度维度的级别数是树的深度，最好为时间维度的所有子单位计数。</span><span class="sxs-lookup"><span data-stu-id="ab123-119">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="ab123-120">例如，时间维度为年、 月、 日和小时，则计为四个级别。</span><span class="sxs-lookup"><span data-stu-id="ab123-120">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
- <span data-ttu-id="ab123-121">BAM 不支持类型的实时聚合**最小**并**最大**。</span><span class="sxs-lookup"><span data-stu-id="ab123-121">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="ab123-122">BAM 支持聚合**计数**， **Sum**，并**平均**。</span><span class="sxs-lookup"><span data-stu-id="ab123-122">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
- <span data-ttu-id="ab123-123">必须始终为 RTA 创建时间维度，并始终使用其所有数据切片，因为 RTA 中的数据过期的基于服务器时间戳，而不依赖任何特定的业务里程碑。</span><span class="sxs-lookup"><span data-stu-id="ab123-123">You must always create a time dimension for RTA and always use it in all data slices, because the data in RTA is aged based on the server time stamp, and not on any specific business milestone.</span></span>  
  
- <span data-ttu-id="ab123-124">未定义使用同一个 BAM 活动的多个 Rta。</span><span class="sxs-lookup"><span data-stu-id="ab123-124">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="ab123-125">如果这样做，RTA 数据将不正确，当您存档 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="ab123-125">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
  <span data-ttu-id="ab123-126">实时聚合会显著影响 BAM 写入数据的速度。</span><span class="sxs-lookup"><span data-stu-id="ab123-126">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="ab123-127">因此，只应定义为 RTA 的最重要的聚合结构切片。</span><span class="sxs-lookup"><span data-stu-id="ab123-127">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
  <span data-ttu-id="ab123-128">实时聚合的维度级别限制为 14。</span><span class="sxs-lookup"><span data-stu-id="ab123-128">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="ab123-129">例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。</span><span class="sxs-lookup"><span data-stu-id="ab123-129">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="ab123-130">对于进度维度的级别数是树的深度，最好为时间维度的所有子单位计数。</span><span class="sxs-lookup"><span data-stu-id="ab123-130">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="ab123-131">例如，时间维度为年、 月、 日和小时，则计为四个级别。</span><span class="sxs-lookup"><span data-stu-id="ab123-131">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
  <span data-ttu-id="ab123-132">BAM 不支持类型的实时聚合**最小**并**最大**。</span><span class="sxs-lookup"><span data-stu-id="ab123-132">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="ab123-133">BAM 支持聚合**计数**， **Sum**，并**平均**。</span><span class="sxs-lookup"><span data-stu-id="ab123-133">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
  <span data-ttu-id="ab123-134">未定义使用同一个 BAM 活动的多个 Rta。</span><span class="sxs-lookup"><span data-stu-id="ab123-134">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="ab123-135">如果这样做，RTA 数据将不正确，当您存档 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="ab123-135">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab123-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab123-136">See Also</span></span>  
 [<span data-ttu-id="ab123-137">聚合概述</span><span class="sxs-lookup"><span data-stu-id="ab123-137">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)