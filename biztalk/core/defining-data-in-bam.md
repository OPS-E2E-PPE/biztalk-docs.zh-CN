---
title: 定义 BAM 中的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- monitoring business activities [BAM], BAM Activity Wizard
- monitoring business activities [BAM], time intervals
- aggregations [BAM], measurements
- monitoring business activities [BAM], views
- monitoring business activities [BAM], aggregations
- Excel add-in [BAM], collecting data
- aggregations [BAM], scheduling
- monitoring business activities [BAM], milestone groups
- aggregations [BAM], real-time data
ms.assetid: 501a1c08-3979-4a99-94d9-0d1b5ec4266b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b40c37f0f0f71a119dcb55465e1c22f30e6267
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390280"
---
# <a name="defining-data-in-bam"></a><span data-ttu-id="593ed-102">定义 BAM 中的</span><span class="sxs-lookup"><span data-stu-id="593ed-102">Defining Data in BAM</span></span>
<span data-ttu-id="593ed-103">使用 BAM Excel 外接程序来定义您希望 BAM 收集的数据和定义共享的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="593ed-103">You use the BAM Excel Add-in to define the data you want BAM to collect, and define the way in which the data will be shared.</span></span> <span data-ttu-id="593ed-104">使用 BAM 活动定义的数据，并使用 BAM 视图来定义其他用户可以看到的数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-104">You use BAM activities to define the data, and you use BAM views to define the data that other users can see.</span></span>  
  
## <a name="activities"></a><span data-ttu-id="593ed-105">活动</span><span class="sxs-lookup"><span data-stu-id="593ed-105">Activities</span></span>  
 <span data-ttu-id="593ed-106">创建 BAM 活动定义有关你想要使用 BAM 监视业务流程的信息。</span><span class="sxs-lookup"><span data-stu-id="593ed-106">You create a BAM activity to define information about a business process that you want to monitor with BAM.</span></span> <span data-ttu-id="593ed-107">BAM 活动代表业务中的特定业务流程，例如处理采购订单或发运产品。</span><span class="sxs-lookup"><span data-stu-id="593ed-107">A BAM activity represents a specific business process in the business, such as handling purchase orders or shipping a product.</span></span> <span data-ttu-id="593ed-108">业务流程具有一组定义的里程碑和业务数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-108">A business process has a defined set of milestones and business data.</span></span> <span data-ttu-id="593ed-109">例如，采购订单流程可能 Approved、 Denied 和 Delivered 等里程碑以及客户姓名和产品等业务数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-109">For example, a purchase order process might have milestones such as Approved, Denied, and Delivered along with business data like Customer Name and Product.</span></span>  
  
 <span data-ttu-id="593ed-110">BAM 活动的目的是向信息工作者显示历史记录 （里程碑） 和有关进程的数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-110">The intention of a BAM activity is to show the history (milestones) and data about a process to information workers.</span></span> <span data-ttu-id="593ed-111">BAM 活动都是独立于 BizTalk Server 的实际实现的高级抽象。</span><span class="sxs-lookup"><span data-stu-id="593ed-111">BAM activities are high-level abstractions that are independent of the actual implementation of BizTalk Server.</span></span> <span data-ttu-id="593ed-112">BAM 的概念性概述，请参阅主题"业务活动监视"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="593ed-112">For a conceptual overview of BAM, see the topic "Business Activity Monitoring" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="593ed-113">使用 BAM 活动向导可以定义包含至少一个活动项的 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="593ed-113">You use the BAM Activity Wizard to define BAM activities that contain at least one activity item.</span></span> <span data-ttu-id="593ed-114">在活动中的相关的活动项进行分组并使用活动项来描述您想要在业务流程中提供的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="593ed-114">You group related activity items in an activity, and you use activity items to describe the type of data you want to make available from a business process.</span></span>  
  
 <span data-ttu-id="593ed-115">下表描述类型 BAM 提供的活动项。</span><span class="sxs-lookup"><span data-stu-id="593ed-115">The following table describes the types of activity items BAM provides.</span></span>  
  
|<span data-ttu-id="593ed-116">项类型</span><span class="sxs-lookup"><span data-stu-id="593ed-116">Item type</span></span>|<span data-ttu-id="593ed-117">Description</span><span class="sxs-lookup"><span data-stu-id="593ed-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="593ed-118">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="593ed-118">Business Milestone</span></span>|<span data-ttu-id="593ed-119">日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="593ed-119">A date/time value.</span></span> <span data-ttu-id="593ed-120">例如，采购订单的批准日期。</span><span class="sxs-lookup"><span data-stu-id="593ed-120">For example, an approval date for a purchase order.</span></span>|  
|<span data-ttu-id="593ed-121">业务数据-Text</span><span class="sxs-lookup"><span data-stu-id="593ed-121">Business Data - Text</span></span>|<span data-ttu-id="593ed-122">包含任何字母数字字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="593ed-122">A string containing any alphanumeric characters.</span></span> <span data-ttu-id="593ed-123">例如，发运到：城市、 省/市/自治区和邮政编码的代码。</span><span class="sxs-lookup"><span data-stu-id="593ed-123">For example, Ship to: City, State/Province and Zip/Postal code.</span></span>|  
|<span data-ttu-id="593ed-124">业务数据 – Integer</span><span class="sxs-lookup"><span data-stu-id="593ed-124">Business Data - Integer</span></span>|<span data-ttu-id="593ed-125">一个整数值。</span><span class="sxs-lookup"><span data-stu-id="593ed-125">A whole number value.</span></span> <span data-ttu-id="593ed-126">例如，购买的总数。</span><span class="sxs-lookup"><span data-stu-id="593ed-126">For example, the total number of purchases.</span></span>|  
|<span data-ttu-id="593ed-127">业务数据-Float</span><span class="sxs-lookup"><span data-stu-id="593ed-127">Business Data - Float</span></span>|<span data-ttu-id="593ed-128">一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="593ed-128">A decimal value.</span></span> <span data-ttu-id="593ed-129">有关示例的美元总金额的采购订单。</span><span class="sxs-lookup"><span data-stu-id="593ed-129">For example the total dollar amount of the PO.</span></span>|  
  
 <span data-ttu-id="593ed-130">例如，在采购订单活动中，可能会创建以下表中的活动项。</span><span class="sxs-lookup"><span data-stu-id="593ed-130">For example, in a purchase order activity, you might create the activity items in the following table.</span></span>  
  
|<span data-ttu-id="593ed-131">活动项</span><span class="sxs-lookup"><span data-stu-id="593ed-131">Activity item</span></span>|<span data-ttu-id="593ed-132">项类型</span><span class="sxs-lookup"><span data-stu-id="593ed-132">Item type</span></span>|  
|-------------------|---------------|  
|<span data-ttu-id="593ed-133">产品</span><span class="sxs-lookup"><span data-stu-id="593ed-133">Product</span></span>|<span data-ttu-id="593ed-134">业务数据 — Text</span><span class="sxs-lookup"><span data-stu-id="593ed-134">Business Data — Text</span></span>|  
|<span data-ttu-id="593ed-135">City</span><span class="sxs-lookup"><span data-stu-id="593ed-135">City</span></span>|<span data-ttu-id="593ed-136">业务数据 — Text</span><span class="sxs-lookup"><span data-stu-id="593ed-136">Business Data — Text</span></span>|  
|<span data-ttu-id="593ed-137">State</span><span class="sxs-lookup"><span data-stu-id="593ed-137">State</span></span>|<span data-ttu-id="593ed-138">业务数据 — Text</span><span class="sxs-lookup"><span data-stu-id="593ed-138">Business Data — Text</span></span>|  
|<span data-ttu-id="593ed-139">Amount</span><span class="sxs-lookup"><span data-stu-id="593ed-139">Amount</span></span>|<span data-ttu-id="593ed-140">业务数据 — Float</span><span class="sxs-lookup"><span data-stu-id="593ed-140">Business Data — Float</span></span>|  
|<span data-ttu-id="593ed-141">Quantity</span><span class="sxs-lookup"><span data-stu-id="593ed-141">Quantity</span></span>|<span data-ttu-id="593ed-142">业务数据 — Integer</span><span class="sxs-lookup"><span data-stu-id="593ed-142">Business Data — Integer</span></span>|  
|<span data-ttu-id="593ed-143">已批准</span><span class="sxs-lookup"><span data-stu-id="593ed-143">Approved</span></span>|<span data-ttu-id="593ed-144">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="593ed-144">Business Milestone</span></span>|  
|<span data-ttu-id="593ed-145">传递</span><span class="sxs-lookup"><span data-stu-id="593ed-145">Delivered</span></span>|<span data-ttu-id="593ed-146">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="593ed-146">Business Milestone</span></span>|  
|<span data-ttu-id="593ed-147">拒绝</span><span class="sxs-lookup"><span data-stu-id="593ed-147">Denied</span></span>|<span data-ttu-id="593ed-148">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="593ed-148">Business Milestone</span></span>|  
|<span data-ttu-id="593ed-149">收到</span><span class="sxs-lookup"><span data-stu-id="593ed-149">Received</span></span>|<span data-ttu-id="593ed-150">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="593ed-150">Business Milestone</span></span>|  
  
 <span data-ttu-id="593ed-151">请注意量是浮点数，因为它可能是一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="593ed-151">Note that Amount is a float because it may be a decimal value.</span></span> <span data-ttu-id="593ed-152">数量是一个整数，因为它将始终保持在此示例中的整数。</span><span class="sxs-lookup"><span data-stu-id="593ed-152">Quantity is an integer because it will always be a whole number in this example.</span></span> <span data-ttu-id="593ed-153">获得批准，Delivered、 Denied 和 Received 都是采购订单流程中的里程碑。</span><span class="sxs-lookup"><span data-stu-id="593ed-153">Approved, Delivered, Denied, and Received are all milestones in the purchase order process.</span></span>  
  
## <a name="views"></a><span data-ttu-id="593ed-154">Views</span><span class="sxs-lookup"><span data-stu-id="593ed-154">Views</span></span>  
 <span data-ttu-id="593ed-155">创建视图以公开对用户活动的数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-155">You create views to expose data from an activity to users.</span></span> <span data-ttu-id="593ed-156">当你创建基于采购订单活动的视图时，您定义活动项背后的数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-156">When you create a view based on the purchase order activity, you define the data behind the activity items.</span></span> <span data-ttu-id="593ed-157">查看数据在 BAM 中定义为维度、 度量值、 持续时间、 里程碑组和进度维度中。</span><span class="sxs-lookup"><span data-stu-id="593ed-157">You define view data in BAM as dimensions, measures, durations, milestone groups, and progress dimensions.</span></span>  
  
 <span data-ttu-id="593ed-158">视图包含一个或多个视图项。</span><span class="sxs-lookup"><span data-stu-id="593ed-158">A view contains one or more view items.</span></span> <span data-ttu-id="593ed-159">可以创建以下类型的视图项：</span><span class="sxs-lookup"><span data-stu-id="593ed-159">You can create the following types of view items:</span></span>  
  
-   <span data-ttu-id="593ed-160">持续时间</span><span class="sxs-lookup"><span data-stu-id="593ed-160">Durations</span></span>  
  
-   <span data-ttu-id="593ed-161">里程碑组</span><span class="sxs-lookup"><span data-stu-id="593ed-161">Milestone groups</span></span>  
  
-   <span data-ttu-id="593ed-162">Aggregations</span><span class="sxs-lookup"><span data-stu-id="593ed-162">Aggregations</span></span>  
  
### <a name="durations"></a><span data-ttu-id="593ed-163">持续时间</span><span class="sxs-lookup"><span data-stu-id="593ed-163">Durations</span></span>  
 <span data-ttu-id="593ed-164">持续时间为时间间隔。</span><span class="sxs-lookup"><span data-stu-id="593ed-164">Durations are time intervals.</span></span> <span data-ttu-id="593ed-165">持续时间的里程碑来定义的开始和结束时间间隔的描述。</span><span class="sxs-lookup"><span data-stu-id="593ed-165">Durations are described in terms of the milestones that define the start and end of time intervals.</span></span> <span data-ttu-id="593ed-166">下表显示了您可从上表中列出的里程碑的持续时间。</span><span class="sxs-lookup"><span data-stu-id="593ed-166">The following table shows the durations you can make from the milestones listed in the previous table.</span></span>  
  
|<span data-ttu-id="593ed-167">Duration</span><span class="sxs-lookup"><span data-stu-id="593ed-167">Duration</span></span>|<span data-ttu-id="593ed-168">开始里程碑</span><span class="sxs-lookup"><span data-stu-id="593ed-168">Start milestone</span></span>|<span data-ttu-id="593ed-169">结束里程碑</span><span class="sxs-lookup"><span data-stu-id="593ed-169">End milestone</span></span>|  
|--------------|---------------------|-------------------|  
|<span data-ttu-id="593ed-170">1</span><span class="sxs-lookup"><span data-stu-id="593ed-170">1</span></span>|<span data-ttu-id="593ed-171">收到</span><span class="sxs-lookup"><span data-stu-id="593ed-171">Received</span></span>|<span data-ttu-id="593ed-172">已批准</span><span class="sxs-lookup"><span data-stu-id="593ed-172">Approved</span></span>|  
|<span data-ttu-id="593ed-173">2</span><span class="sxs-lookup"><span data-stu-id="593ed-173">2</span></span>|<span data-ttu-id="593ed-174">收到</span><span class="sxs-lookup"><span data-stu-id="593ed-174">Received</span></span>|<span data-ttu-id="593ed-175">传递</span><span class="sxs-lookup"><span data-stu-id="593ed-175">Delivered</span></span>|  
|<span data-ttu-id="593ed-176">3</span><span class="sxs-lookup"><span data-stu-id="593ed-176">3</span></span>|<span data-ttu-id="593ed-177">收到</span><span class="sxs-lookup"><span data-stu-id="593ed-177">Received</span></span>|<span data-ttu-id="593ed-178">拒绝</span><span class="sxs-lookup"><span data-stu-id="593ed-178">Denied</span></span>|  
|<span data-ttu-id="593ed-179">4</span><span class="sxs-lookup"><span data-stu-id="593ed-179">4</span></span>|<span data-ttu-id="593ed-180">已批准</span><span class="sxs-lookup"><span data-stu-id="593ed-180">Approved</span></span>|<span data-ttu-id="593ed-181">传递</span><span class="sxs-lookup"><span data-stu-id="593ed-181">Delivered</span></span>|  
  
 <span data-ttu-id="593ed-182">在此表中，可以看到第一个持续时间 (持续时间 1) 是启动采购订单由 BizTalk Server 收到并批准采购订单时结束时的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="593ed-182">In this table, you can see that the first duration (Duration 1) is the time interval that starts when a purchase order is received by BizTalk Server, and ends when the purchase order is approved.</span></span>  
  
### <a name="milestone-groups"></a><span data-ttu-id="593ed-183">里程碑组</span><span class="sxs-lookup"><span data-stu-id="593ed-183">Milestone groups</span></span>  
 <span data-ttu-id="593ed-184">您创建里程碑组，例如作为单个实体，将一组里程碑、 开始和结束里程碑的过程中，将创建一个里程碑来表示该过程的整个长度。</span><span class="sxs-lookup"><span data-stu-id="593ed-184">You create milestone groups to treat a set of milestones as a single entity, for example, the beginning and ending milestones for a process, which creates a single milestone to represent the entire length of the process.</span></span>  
  
### <a name="aggregations"></a><span data-ttu-id="593ed-185">Aggregations</span><span class="sxs-lookup"><span data-stu-id="593ed-185">Aggregations</span></span>  
 <span data-ttu-id="593ed-186">使用聚合可以缩短刷新数据库中的数据的响应时间。</span><span class="sxs-lookup"><span data-stu-id="593ed-186">You use aggregations to improve the response time for refreshing data from the database.</span></span> <span data-ttu-id="593ed-187">Excel 将聚合定义为预先计算的数据汇总，通过在提问之前准备好答案的方式来提高查询响应时间。</span><span class="sxs-lookup"><span data-stu-id="593ed-187">Excel defines aggregations as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="593ed-188">例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。</span><span class="sxs-lookup"><span data-stu-id="593ed-188">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="593ed-189">然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。</span><span class="sxs-lookup"><span data-stu-id="593ed-189">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="593ed-190">下图显示的是预先计算的聚合数据的示例。</span><span class="sxs-lookup"><span data-stu-id="593ed-190">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 <span data-ttu-id="593ed-191">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="593ed-191">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
  
 <span data-ttu-id="593ed-192">该图汇总了两个月时间段内发送到特定地点的每个产品的数量。</span><span class="sxs-lookup"><span data-stu-id="593ed-192">The figure summarizes the numbers of each product shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="593ed-193">通常，Excel 将此数据定义为度量值。</span><span class="sxs-lookup"><span data-stu-id="593ed-193">Excel typically defines this data as measure.</span></span> <span data-ttu-id="593ed-194">Excel 将用于筛选和分类的数据定义为维度。</span><span class="sxs-lookup"><span data-stu-id="593ed-194">The data used for filtering and categorization, Excel defines as dimension.</span></span>  
  
 <span data-ttu-id="593ed-195">BAM 工作簿中，可以定义两种类型的聚合：</span><span class="sxs-lookup"><span data-stu-id="593ed-195">You can define two types of aggregations in the BAM workbook:</span></span>  
  
-   <span data-ttu-id="593ed-196">实时聚合</span><span class="sxs-lookup"><span data-stu-id="593ed-196">Real-time aggregations</span></span>  
  
-   <span data-ttu-id="593ed-197">计划的聚合</span><span class="sxs-lookup"><span data-stu-id="593ed-197">Scheduled aggregations</span></span>  
  
### <a name="real-time-aggregations"></a><span data-ttu-id="593ed-198">实时聚合</span><span class="sxs-lookup"><span data-stu-id="593ed-198">Real-time aggregations</span></span>  
 <span data-ttu-id="593ed-199">实时聚合 (RTA) 允许您可以看到业务流程的当前状态，并能够轻松地确定流程瓶颈。</span><span class="sxs-lookup"><span data-stu-id="593ed-199">Real-time aggregations (RTA) allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="593ed-200">BAM 数据显示在数据透视表。</span><span class="sxs-lookup"><span data-stu-id="593ed-200">BAM data is displayed in a pivot table.</span></span> <span data-ttu-id="593ed-201">您可以将 BAM 透视表定义为 RTA 或计划的聚合。</span><span class="sxs-lookup"><span data-stu-id="593ed-201">You can define a BAM pivot table as an RTA or a scheduled aggregation.</span></span> <span data-ttu-id="593ed-202">RTA 可为您提供最新的数据视图，例如，特定 PO 在发货流程中所处的位置。</span><span class="sxs-lookup"><span data-stu-id="593ed-202">An RTA gives you an up-to-the-minute view of your data, for example, where a particular PO is in the shipping process.</span></span> <span data-ttu-id="593ed-203">您可以随时刷新屏幕以更新数据视图。</span><span class="sxs-lookup"><span data-stu-id="593ed-203">You can refresh your screen to update the view of the data throughout the day.</span></span>  
  
 <span data-ttu-id="593ed-204">在某些情况下，多维聚合的特定切片是时间非常敏感，希望它们在真实时间中不可用。</span><span class="sxs-lookup"><span data-stu-id="593ed-204">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="593ed-205">例如，你的业务销售腐烂的产品和所需的产品数量传递要在真实时间中可用的不同阶段中的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="593ed-205">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="593ed-206">同时，您希望其他聚合，如年龄的典型客户，但只会在商业智能分析的月结束。</span><span class="sxs-lookup"><span data-stu-id="593ed-206">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="593ed-207">未定义使用同一个 BAM 活动的多个 Rta。</span><span class="sxs-lookup"><span data-stu-id="593ed-207">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="593ed-208">如果这样做，RTA 数据将不正确，当您存档 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-208">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="593ed-209">有关浏览多维数据的信息，请参阅 Excel 帮助中的数据透视表主题。</span><span class="sxs-lookup"><span data-stu-id="593ed-209">For information about browsing multidimensional data, see the PivotTable topic in Excel Help.</span></span>  
  
### <a name="scheduled-aggregations"></a><span data-ttu-id="593ed-210">计划的聚合</span><span class="sxs-lookup"><span data-stu-id="593ed-210">Scheduled aggregations</span></span>  
 <span data-ttu-id="593ed-211">所有 BAM 聚合都是默认情况下计划的聚合。</span><span class="sxs-lookup"><span data-stu-id="593ed-211">All BAM aggregations are scheduled aggregations by default.</span></span> <span data-ttu-id="593ed-212">计划聚合表示特定时间的业务快照，例如，今天上午发货活动的摘要。</span><span class="sxs-lookup"><span data-stu-id="593ed-212">A scheduled aggregation represents a snapshot of the business at a specific time, for example, a summary of this morning's shipments.</span></span> <span data-ttu-id="593ed-213">请询问数据库管理员何时处理聚合，然后您可以查看历史数据。</span><span class="sxs-lookup"><span data-stu-id="593ed-213">Ask your database administrator when your aggregations are processed, and then you can look at the historical data.</span></span>  
  
### <a name="dimensions-and-measures"></a><span data-ttu-id="593ed-214">维度和度量值</span><span class="sxs-lookup"><span data-stu-id="593ed-214">Dimensions and Measures</span></span>  
 <span data-ttu-id="593ed-215">使用维度和度量值可以创建数据聚合：</span><span class="sxs-lookup"><span data-stu-id="593ed-215">You use dimensions and measures to create data aggregations:</span></span>  
  
- <span data-ttu-id="593ed-216">维度描述事实。</span><span class="sxs-lookup"><span data-stu-id="593ed-216">Dimensions describe a fact.</span></span>  
  
- <span data-ttu-id="593ed-217">度量值是事实的值。</span><span class="sxs-lookup"><span data-stu-id="593ed-217">Measures are fact values.</span></span>  
  
  <span data-ttu-id="593ed-218">例如，事实可以是"3 辆红色轿车"清单中。</span><span class="sxs-lookup"><span data-stu-id="593ed-218">For example, a fact could be “3 red cars” in inventory.</span></span> <span data-ttu-id="593ed-219">产品的说明:"car"和"红色"是维度。</span><span class="sxs-lookup"><span data-stu-id="593ed-219">The description of the product: "car" and "red" are dimensions.</span></span> <span data-ttu-id="593ed-220">事实"3"的值是度量值。</span><span class="sxs-lookup"><span data-stu-id="593ed-220">The value of the fact "3" is a measure.</span></span> <span data-ttu-id="593ed-221">如果每辆轿车的价格包含在这一事实，则轿车价格是维度，但库存中轿车的平均价格是度量值。</span><span class="sxs-lookup"><span data-stu-id="593ed-221">If the price of each car is included in the fact, the car price is a dimension, but the average price of cars in inventory is a measure.</span></span> <span data-ttu-id="593ed-222">Microsoft SQL Server 联机丛书将度量值描述为"的中心值进行聚合和分析。"</span><span class="sxs-lookup"><span data-stu-id="593ed-222">Microsoft SQL Server Books Online describes a measure as "the central values that are aggregated and analyzed."</span></span> <span data-ttu-id="593ed-223">换而言之，如果可以对其进行计数、 求平均数，或者执行数学函数以获取它，它是一个度量值。</span><span class="sxs-lookup"><span data-stu-id="593ed-223">In other words, if you can count it, average it, or otherwise perform mathematical functions to get it, it is a measure.</span></span>  
  
  <span data-ttu-id="593ed-224">可以创建以下类型的维度：</span><span class="sxs-lookup"><span data-stu-id="593ed-224">You can create the following types of dimensions:</span></span>  
  
- <span data-ttu-id="593ed-225">进度维度</span><span class="sxs-lookup"><span data-stu-id="593ed-225">Progress dimension</span></span>  
  
- <span data-ttu-id="593ed-226">数据维度</span><span class="sxs-lookup"><span data-stu-id="593ed-226">Data dimension</span></span>  
  
- <span data-ttu-id="593ed-227">时间维度</span><span class="sxs-lookup"><span data-stu-id="593ed-227">Time dimension</span></span>  
  
- <span data-ttu-id="593ed-228">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="593ed-228">Numeric range dimension</span></span>  
  
## <a name="progress-dimensions"></a><span data-ttu-id="593ed-229">进度维度</span><span class="sxs-lookup"><span data-stu-id="593ed-229">Progress dimensions</span></span>  
 <span data-ttu-id="593ed-230">BAM 引入了新类型的维度： 进度维度。</span><span class="sxs-lookup"><span data-stu-id="593ed-230">BAM introduces a new type of dimension: the progress dimension.</span></span> <span data-ttu-id="593ed-231">创建进度维度可以创建与正在进行的活动的进度相关的聚合。</span><span class="sxs-lookup"><span data-stu-id="593ed-231">You create progress dimensions to create aggregations that relate to the progress of activities still in process.</span></span>  
  
 <span data-ttu-id="593ed-232">例如，考虑你在其中接收 1,000 个采购订单的采购业务流程。</span><span class="sxs-lookup"><span data-stu-id="593ed-232">For example, consider a purchasing business process where you receive 1,000 purchase orders.</span></span> <span data-ttu-id="593ed-233">可以在行上使用进度维度来创建下表。</span><span class="sxs-lookup"><span data-stu-id="593ed-233">You can use the progress dimension on rows to create the following table.</span></span>  
  
|<span data-ttu-id="593ed-234">OrderProgress_Level1</span><span class="sxs-lookup"><span data-stu-id="593ed-234">OrderProgress_Level1</span></span>|<span data-ttu-id="593ed-235">Count</span><span class="sxs-lookup"><span data-stu-id="593ed-235">Count</span></span>|  
|---------------------------|-----------|  
|<span data-ttu-id="593ed-236">收到</span><span class="sxs-lookup"><span data-stu-id="593ed-236">Received</span></span>|<span data-ttu-id="593ed-237">1000</span><span class="sxs-lookup"><span data-stu-id="593ed-237">1000</span></span>|  
  
 <span data-ttu-id="593ed-238">然后可以打开 Received 流程查看更多详细信息有关进度的活动，例如：</span><span class="sxs-lookup"><span data-stu-id="593ed-238">You can then open the Received process to view further details about the progress of the activities, such as:</span></span>  
  
|||<span data-ttu-id="593ed-239">Count</span><span class="sxs-lookup"><span data-stu-id="593ed-239">Count</span></span>|  
|------|------|-----------|  
|<span data-ttu-id="593ed-240">收到</span><span class="sxs-lookup"><span data-stu-id="593ed-240">Received</span></span>|<span data-ttu-id="593ed-241">评估</span><span class="sxs-lookup"><span data-stu-id="593ed-241">Evaluating</span></span>|<span data-ttu-id="593ed-242">300</span><span class="sxs-lookup"><span data-stu-id="593ed-242">300</span></span>|  
||<span data-ttu-id="593ed-243">已批准</span><span class="sxs-lookup"><span data-stu-id="593ed-243">Approved</span></span>|<span data-ttu-id="593ed-244">500</span><span class="sxs-lookup"><span data-stu-id="593ed-244">500</span></span>|  
||<span data-ttu-id="593ed-245">拒绝</span><span class="sxs-lookup"><span data-stu-id="593ed-245">Denied</span></span>|<span data-ttu-id="593ed-246">200</span><span class="sxs-lookup"><span data-stu-id="593ed-246">200</span></span>|  
  
 <span data-ttu-id="593ed-247">这意味着，从你收到了 1000 个采购订单，500 个已批准、 已拒绝 200，300 个当前正在评估。</span><span class="sxs-lookup"><span data-stu-id="593ed-247">This means that from the 1000 purchase orders you received, 500 were approved, 200 were denied, and 300 are currently being evaluated.</span></span>  
  
 <span data-ttu-id="593ed-248">Received、 Approved 和 Denied 表示里程碑。</span><span class="sxs-lookup"><span data-stu-id="593ed-248">Received, Approved, and Denied represent milestones.</span></span> <span data-ttu-id="593ed-249">计数列中的相应数字显示多少订单已通过这些里程碑。</span><span class="sxs-lookup"><span data-stu-id="593ed-249">The corresponding numbers in the Count column show how many orders have passed through these milestones.</span></span> <span data-ttu-id="593ed-250">评估是订单已接收和 Approved 或 Denied 里程碑之间传递一个阶段。</span><span class="sxs-lookup"><span data-stu-id="593ed-250">Evaluating is a stage that the orders pass through between the Received and Approved or Denied milestones.</span></span>  
  
 <span data-ttu-id="593ed-251">与任何其他维度结合使用，可以使用进度维度。</span><span class="sxs-lookup"><span data-stu-id="593ed-251">You can use progress dimensions in combination with any other dimensions.</span></span> <span data-ttu-id="593ed-252">例如，通过在行和数据使用进度维度订单进度维度产品上的列，将出现以下结果：</span><span class="sxs-lookup"><span data-stu-id="593ed-252">For example, by using the progress dimension Order Progress on rows and the data dimension Product on columns, the following results occur:</span></span>  
  
|||<span data-ttu-id="593ed-253">网球拍</span><span class="sxs-lookup"><span data-stu-id="593ed-253">Tennis Racquets</span></span>|<span data-ttu-id="593ed-254">足球</span><span class="sxs-lookup"><span data-stu-id="593ed-254">Soccer Balls</span></span>|  
|------|------|---------------------|------------------|  
|<span data-ttu-id="593ed-255">收到</span><span class="sxs-lookup"><span data-stu-id="593ed-255">Received</span></span>|<span data-ttu-id="593ed-256">评估</span><span class="sxs-lookup"><span data-stu-id="593ed-256">Evaluating</span></span>|<span data-ttu-id="593ed-257">250</span><span class="sxs-lookup"><span data-stu-id="593ed-257">250</span></span>|<span data-ttu-id="593ed-258">50</span><span class="sxs-lookup"><span data-stu-id="593ed-258">50</span></span>|  
||<span data-ttu-id="593ed-259">已批准</span><span class="sxs-lookup"><span data-stu-id="593ed-259">Approved</span></span>|<span data-ttu-id="593ed-260">200</span><span class="sxs-lookup"><span data-stu-id="593ed-260">200</span></span>|<span data-ttu-id="593ed-261">300</span><span class="sxs-lookup"><span data-stu-id="593ed-261">300</span></span>|  
||<span data-ttu-id="593ed-262">拒绝</span><span class="sxs-lookup"><span data-stu-id="593ed-262">Denied</span></span>|<span data-ttu-id="593ed-263">150</span><span class="sxs-lookup"><span data-stu-id="593ed-263">150</span></span>|<span data-ttu-id="593ed-264">50</span><span class="sxs-lookup"><span data-stu-id="593ed-264">50</span></span>|  
  
 <span data-ttu-id="593ed-265">进度维度提供的基于实时聚合 (RTA) 的图表非常有用的信息。</span><span class="sxs-lookup"><span data-stu-id="593ed-265">Progress dimensions provide especially useful information for charts based on real-time aggregations (RTA).</span></span> <span data-ttu-id="593ed-266">Rta 允许您可以看到业务流程的当前状态，并能够轻松地确定流程瓶颈。</span><span class="sxs-lookup"><span data-stu-id="593ed-266">RTAs allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="593ed-267">进度维度可以是按顺序进行排序中购买的里程碑： 第一步完成后，才能开始下一步。</span><span class="sxs-lookup"><span data-stu-id="593ed-267">The milestones in a purchase order progress dimension can be sequential: the first step is completed before the next step is started.</span></span> <span data-ttu-id="593ed-268">或者，里程碑也可以在迁移后。</span><span class="sxs-lookup"><span data-stu-id="593ed-268">Or milestones can be completed in tandem.</span></span> <span data-ttu-id="593ed-269">按顺序的步骤是子步骤，并关联步骤是同级步骤。</span><span class="sxs-lookup"><span data-stu-id="593ed-269">Sequential steps are child steps, and tandem steps are sibling steps.</span></span> <span data-ttu-id="593ed-270">在采购订单流程中，验证后将立即开始接收采购订单。</span><span class="sxs-lookup"><span data-stu-id="593ed-270">In the purchase order process, verification begins as soon as the purchase order is received.</span></span> <span data-ttu-id="593ed-271">它是接收里程碑时将会发生，因此接收里程碑的同级的短暂步骤。</span><span class="sxs-lookup"><span data-stu-id="593ed-271">It is a transitory step that occurs at the same time as the received milestone, and is therefore a sibling to the receive milestone.</span></span> <span data-ttu-id="593ed-272">仅在接收后批准采购订单-已批准的子接收。</span><span class="sxs-lookup"><span data-stu-id="593ed-272">A purchase order is approved only after it is received — approved is a child of received.</span></span>  
  
## <a name="data-dimension"></a><span data-ttu-id="593ed-273">数据维度</span><span class="sxs-lookup"><span data-stu-id="593ed-273">Data dimension</span></span>  
 <span data-ttu-id="593ed-274">定义数据维度，可以在行或列上的 BAM 活动中使用某些文本项的值。</span><span class="sxs-lookup"><span data-stu-id="593ed-274">You define a data dimension to use the value of some text items in the BAM activity on rows or columns.</span></span> <span data-ttu-id="593ed-275">例如，名为产品的数据维度可用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="593ed-275">For example, a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="593ed-276">产品</span><span class="sxs-lookup"><span data-stu-id="593ed-276">Product</span></span>|<span data-ttu-id="593ed-277">Count</span><span class="sxs-lookup"><span data-stu-id="593ed-277">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="593ed-278">网球拍</span><span class="sxs-lookup"><span data-stu-id="593ed-278">Tennis racquets</span></span>|<span data-ttu-id="593ed-279">100</span><span class="sxs-lookup"><span data-stu-id="593ed-279">100</span></span>|  
|<span data-ttu-id="593ed-280">足球</span><span class="sxs-lookup"><span data-stu-id="593ed-280">Soccer balls</span></span>|<span data-ttu-id="593ed-281">200</span><span class="sxs-lookup"><span data-stu-id="593ed-281">200</span></span>|  
  
 <span data-ttu-id="593ed-282">此外，您可以在 BAM 视图向导中定义多个数据维度。</span><span class="sxs-lookup"><span data-stu-id="593ed-282">Also, you can define more than one data dimension in the BAM View Wizard.</span></span> <span data-ttu-id="593ed-283">例如，定义数据维度州和城市级别命名位置可用来创建以下表：</span><span class="sxs-lookup"><span data-stu-id="593ed-283">For example, defining a data dimension named Location with levels for State and City can be used to create the following table:</span></span>  
  
|<span data-ttu-id="593ed-284">产品</span><span class="sxs-lookup"><span data-stu-id="593ed-284">Product</span></span>|<span data-ttu-id="593ed-285">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="593ed-285">Los Angeles</span></span>|<span data-ttu-id="593ed-286">旧金山</span><span class="sxs-lookup"><span data-stu-id="593ed-286">San Francisco</span></span>|<span data-ttu-id="593ed-287">Seattle</span><span class="sxs-lookup"><span data-stu-id="593ed-287">Seattle</span></span>|  
|-------------|-----------------|-------------------|-------------|  
|<span data-ttu-id="593ed-288">网球拍</span><span class="sxs-lookup"><span data-stu-id="593ed-288">Tennis racquets</span></span>|<span data-ttu-id="593ed-289">50</span><span class="sxs-lookup"><span data-stu-id="593ed-289">50</span></span>|<span data-ttu-id="593ed-290">20</span><span class="sxs-lookup"><span data-stu-id="593ed-290">20</span></span>|<span data-ttu-id="593ed-291">30</span><span class="sxs-lookup"><span data-stu-id="593ed-291">30</span></span>|  
|<span data-ttu-id="593ed-292">足球</span><span class="sxs-lookup"><span data-stu-id="593ed-292">Soccer balls</span></span>|<span data-ttu-id="593ed-293">130</span><span class="sxs-lookup"><span data-stu-id="593ed-293">130</span></span>|<span data-ttu-id="593ed-294">50</span><span class="sxs-lookup"><span data-stu-id="593ed-294">50</span></span>|<span data-ttu-id="593ed-295">20</span><span class="sxs-lookup"><span data-stu-id="593ed-295">20</span></span>|  
  
 <span data-ttu-id="593ed-296">在此表中，产品维度用作行和位置维度用作列。</span><span class="sxs-lookup"><span data-stu-id="593ed-296">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="time-dimension"></a><span data-ttu-id="593ed-297">时间维度</span><span class="sxs-lookup"><span data-stu-id="593ed-297">Time dimension</span></span>  
 <span data-ttu-id="593ed-298">创建时间维度，可以创建有关时间的聚合。</span><span class="sxs-lookup"><span data-stu-id="593ed-298">You create a time dimension to create aggregations with respect to time.</span></span> <span data-ttu-id="593ed-299">例如，时间维度可以用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="593ed-299">For example, a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="593ed-300">Year</span><span class="sxs-lookup"><span data-stu-id="593ed-300">Year</span></span>|<span data-ttu-id="593ed-301">Month</span><span class="sxs-lookup"><span data-stu-id="593ed-301">Month</span></span>|<span data-ttu-id="593ed-302">Count</span><span class="sxs-lookup"><span data-stu-id="593ed-302">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="593ed-303">2003</span><span class="sxs-lookup"><span data-stu-id="593ed-303">2003</span></span>|<span data-ttu-id="593ed-304">January</span><span class="sxs-lookup"><span data-stu-id="593ed-304">January</span></span>|<span data-ttu-id="593ed-305">120</span><span class="sxs-lookup"><span data-stu-id="593ed-305">120</span></span>|  
||<span data-ttu-id="593ed-306">February</span><span class="sxs-lookup"><span data-stu-id="593ed-306">February</span></span>|<span data-ttu-id="593ed-307">230</span><span class="sxs-lookup"><span data-stu-id="593ed-307">230</span></span>|  
||<span data-ttu-id="593ed-308">March</span><span class="sxs-lookup"><span data-stu-id="593ed-308">March</span></span>|<span data-ttu-id="593ed-309">350</span><span class="sxs-lookup"><span data-stu-id="593ed-309">350</span></span>|  
||<span data-ttu-id="593ed-310">April</span><span class="sxs-lookup"><span data-stu-id="593ed-310">April</span></span>|<span data-ttu-id="593ed-311">280</span><span class="sxs-lookup"><span data-stu-id="593ed-311">280</span></span>|  
  
 <span data-ttu-id="593ed-312">可以结合任何其他维度的时间维度。</span><span class="sxs-lookup"><span data-stu-id="593ed-312">You can combine the time dimension with any other dimension.</span></span> <span data-ttu-id="593ed-313">例如，可以在行和列的数据维度使用时间维度创建以下表：</span><span class="sxs-lookup"><span data-stu-id="593ed-313">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|<span data-ttu-id="593ed-314">Month</span><span class="sxs-lookup"><span data-stu-id="593ed-314">Month</span></span>|<span data-ttu-id="593ed-315">网球拍</span><span class="sxs-lookup"><span data-stu-id="593ed-315">Tennis racquets</span></span>|<span data-ttu-id="593ed-316">足球</span><span class="sxs-lookup"><span data-stu-id="593ed-316">Soccer balls</span></span>|  
|-----------|---------------------|------------------|  
|<span data-ttu-id="593ed-317">January</span><span class="sxs-lookup"><span data-stu-id="593ed-317">January</span></span>|<span data-ttu-id="593ed-318">50</span><span class="sxs-lookup"><span data-stu-id="593ed-318">50</span></span>|<span data-ttu-id="593ed-319">70</span><span class="sxs-lookup"><span data-stu-id="593ed-319">70</span></span>|  
|<span data-ttu-id="593ed-320">February</span><span class="sxs-lookup"><span data-stu-id="593ed-320">February</span></span>|<span data-ttu-id="593ed-321">120</span><span class="sxs-lookup"><span data-stu-id="593ed-321">120</span></span>|<span data-ttu-id="593ed-322">110</span><span class="sxs-lookup"><span data-stu-id="593ed-322">110</span></span>|  
|<span data-ttu-id="593ed-323">March</span><span class="sxs-lookup"><span data-stu-id="593ed-323">March</span></span>|<span data-ttu-id="593ed-324">300</span><span class="sxs-lookup"><span data-stu-id="593ed-324">300</span></span>|<span data-ttu-id="593ed-325">50</span><span class="sxs-lookup"><span data-stu-id="593ed-325">50</span></span>|  
|<span data-ttu-id="593ed-326">April</span><span class="sxs-lookup"><span data-stu-id="593ed-326">April</span></span>|<span data-ttu-id="593ed-327">220</span><span class="sxs-lookup"><span data-stu-id="593ed-327">220</span></span>|<span data-ttu-id="593ed-328">60</span><span class="sxs-lookup"><span data-stu-id="593ed-328">60</span></span>|  
  
## <a name="numeric-range-dimension"></a><span data-ttu-id="593ed-329">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="593ed-329">Numeric range dimension</span></span>  
 <span data-ttu-id="593ed-330">使用数值范围维度可以创建根据友好名称分类的数字范围的聚合。</span><span class="sxs-lookup"><span data-stu-id="593ed-330">You use numeric range dimensions to create aggregations that categorize ranges of numbers by friendly names.</span></span> <span data-ttu-id="593ed-331">例如，业务分析员可以定义名 PO 大小为具有以下范围的数值范围维度：</span><span class="sxs-lookup"><span data-stu-id="593ed-331">For example, a business analyst can define a numeric range dimension named PO Size with the following ranges:</span></span>  
  
 <span data-ttu-id="593ed-332">小，表示采购订单在 0 和 100 美元之间</span><span class="sxs-lookup"><span data-stu-id="593ed-332">Small, for purchase orders between 0 and $100</span></span>  
  
 <span data-ttu-id="593ed-333">中： 表示采购订单在 $100 到 $1,000 之间</span><span class="sxs-lookup"><span data-stu-id="593ed-333">Medium, for purchase orders between $100 and $1,000</span></span>  
  
 <span data-ttu-id="593ed-334">大： 表示采购订单超过 $1,000</span><span class="sxs-lookup"><span data-stu-id="593ed-334">Large, for purchase orders exceeding $1,000</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="593ed-335">如果采购订单金额不在定义的范围内，例如，采购订单金额小于 0，则 bam 来容纳超出范围的数据自动创建一个"超出范围"行。</span><span class="sxs-lookup"><span data-stu-id="593ed-335">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
|<span data-ttu-id="593ed-336">PO 大小</span><span class="sxs-lookup"><span data-stu-id="593ed-336">PO Size</span></span>|<span data-ttu-id="593ed-337">Count</span><span class="sxs-lookup"><span data-stu-id="593ed-337">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="593ed-338">小</span><span class="sxs-lookup"><span data-stu-id="593ed-338">Small</span></span>|<span data-ttu-id="593ed-339">500</span><span class="sxs-lookup"><span data-stu-id="593ed-339">500</span></span>|  
|<span data-ttu-id="593ed-340">Medium</span><span class="sxs-lookup"><span data-stu-id="593ed-340">Medium</span></span>|<span data-ttu-id="593ed-341">350</span><span class="sxs-lookup"><span data-stu-id="593ed-341">350</span></span>|  
|<span data-ttu-id="593ed-342">大型</span><span class="sxs-lookup"><span data-stu-id="593ed-342">Large</span></span>|<span data-ttu-id="593ed-343">225</span><span class="sxs-lookup"><span data-stu-id="593ed-343">225</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="593ed-344">无法创建引用同一数据别名的两个数值范围维度。</span><span class="sxs-lookup"><span data-stu-id="593ed-344">You cannot create two numeric range dimensions that reference the same data alias.</span></span>