---
title: 在 BAM 中定义数据 |Microsoft 文档
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
ms.openlocfilehash: e6acbc0ea1d80ec129d691d6c54b6eefd626d0e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242933"
---
# <a name="defining-data-in-bam"></a><span data-ttu-id="eb4e2-102">定义 BAM 中的数据库</span><span class="sxs-lookup"><span data-stu-id="eb4e2-102">Defining Data in BAM</span></span>
<span data-ttu-id="eb4e2-103">您可以使用 BAM Excel 外接程序来定义需要 BAM 收集的数据，以及数据共享的方式。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-103">You use the BAM Excel Add-in to define the data you want BAM to collect, and define the way in which the data will be shared.</span></span> <span data-ttu-id="eb4e2-104">您可以使用 BAM 活动来定义数据，还可以使用 BAM 视图来定义其他用户可看到的数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-104">You use BAM activities to define the data, and you use BAM views to define the data that other users can see.</span></span>  
  
## <a name="activities"></a><span data-ttu-id="eb4e2-105">活动</span><span class="sxs-lookup"><span data-stu-id="eb4e2-105">Activities</span></span>  
 <span data-ttu-id="eb4e2-106">您可以创建 BAM 活动来定义有关要使用 BAM 监视的业务流程的信息。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-106">You create a BAM activity to define information about a business process that you want to monitor with BAM.</span></span> <span data-ttu-id="eb4e2-107">BAM 活动表示企业中某个具体的业务流程，例如处理采购订单或发运产品。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-107">A BAM activity represents a specific business process in the business, such as handling purchase orders or shipping a product.</span></span> <span data-ttu-id="eb4e2-108">每个业务流程具有一组定义的里程碑和业务数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-108">A business process has a defined set of milestones and business data.</span></span> <span data-ttu-id="eb4e2-109">例如，采购订单流程可能包含 Approved、Denied 和 Delivered 等里程碑，以及“客户名称”和“产品”等业务数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-109">For example, a purchase order process might have milestones such as Approved, Denied, and Delivered along with business data like Customer Name and Product.</span></span>  
  
 <span data-ttu-id="eb4e2-110">BAM 活动的目的是向信息工作者展示有关流程的历史记录（里程碑）和数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-110">The intention of a BAM activity is to show the history (milestones) and data about a process to information workers.</span></span> <span data-ttu-id="eb4e2-111">BAM 活动为高级抽象概念，它们与 BizTalk Server 的实际实现无关。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-111">BAM activities are high-level abstractions that are independent of the actual implementation of BizTalk Server.</span></span> <span data-ttu-id="eb4e2-112">有关 BAM 概念的综述，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的主题“业务活动监视”。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-112">For a conceptual overview of BAM, see the topic "Business Activity Monitoring" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="eb4e2-113">使用 BAM 活动向导可以定义至少包含一个活动项的 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-113">You use the BAM Activity Wizard to define BAM activities that contain at least one activity item.</span></span> <span data-ttu-id="eb4e2-114">您可以对活动中的相关活动项进行分组，以及使用活动项来描述在业务流程中可用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-114">You group related activity items in an activity, and you use activity items to describe the type of data you want to make available from a business process.</span></span>  
  
 <span data-ttu-id="eb4e2-115">下表介绍了 BAM 提供的活动项类型。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-115">The following table describes the types of activity items BAM provides.</span></span>  
  
|<span data-ttu-id="eb4e2-116">项类型</span><span class="sxs-lookup"><span data-stu-id="eb4e2-116">Item type</span></span>|<span data-ttu-id="eb4e2-117">Description</span><span class="sxs-lookup"><span data-stu-id="eb4e2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb4e2-118">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="eb4e2-118">Business Milestone</span></span>|<span data-ttu-id="eb4e2-119">日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-119">A date/time value.</span></span> <span data-ttu-id="eb4e2-120">例如，采购订单的批准日期。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-120">For example, an approval date for a purchase order.</span></span>|  
|<span data-ttu-id="eb4e2-121">业务数据的文本</span><span class="sxs-lookup"><span data-stu-id="eb4e2-121">Business Data - Text</span></span>|<span data-ttu-id="eb4e2-122">包含任何字母数字的字符串。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-122">A string containing any alphanumeric characters.</span></span> <span data-ttu-id="eb4e2-123">例如，交付到： 城市、 省/市/自治区和邮政编码代码。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-123">For example, Ship to: City, State/Province and Zip/Postal code.</span></span>|  
|<span data-ttu-id="eb4e2-124">业务数据 – Integer</span><span class="sxs-lookup"><span data-stu-id="eb4e2-124">Business Data - Integer</span></span>|<span data-ttu-id="eb4e2-125">一个整数值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-125">A whole number value.</span></span> <span data-ttu-id="eb4e2-126">例如，购买的总量。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-126">For example, the total number of purchases.</span></span>|  
|<span data-ttu-id="eb4e2-127">业务数据的 Float</span><span class="sxs-lookup"><span data-stu-id="eb4e2-127">Business Data - Float</span></span>|<span data-ttu-id="eb4e2-128">一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-128">A decimal value.</span></span> <span data-ttu-id="eb4e2-129">例如，PO 的美元总金额。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-129">For example the total dollar amount of the PO.</span></span>|  
  
 <span data-ttu-id="eb4e2-130">例如，在采购订单活动中，您可以创建下表中的活动项。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-130">For example, in a purchase order activity, you might create the activity items in the following table.</span></span>  
  
|<span data-ttu-id="eb4e2-131">活动项</span><span class="sxs-lookup"><span data-stu-id="eb4e2-131">Activity item</span></span>|<span data-ttu-id="eb4e2-132">项类型</span><span class="sxs-lookup"><span data-stu-id="eb4e2-132">Item type</span></span>|  
|-------------------|---------------|  
|<span data-ttu-id="eb4e2-133">Product</span><span class="sxs-lookup"><span data-stu-id="eb4e2-133">Product</span></span>|<span data-ttu-id="eb4e2-134">业务数据 — Text</span><span class="sxs-lookup"><span data-stu-id="eb4e2-134">Business Data — Text</span></span>|  
|<span data-ttu-id="eb4e2-135">City</span><span class="sxs-lookup"><span data-stu-id="eb4e2-135">City</span></span>|<span data-ttu-id="eb4e2-136">业务数据 — Text</span><span class="sxs-lookup"><span data-stu-id="eb4e2-136">Business Data — Text</span></span>|  
|<span data-ttu-id="eb4e2-137">State</span><span class="sxs-lookup"><span data-stu-id="eb4e2-137">State</span></span>|<span data-ttu-id="eb4e2-138">业务数据 — Text</span><span class="sxs-lookup"><span data-stu-id="eb4e2-138">Business Data — Text</span></span>|  
|<span data-ttu-id="eb4e2-139">Amount</span><span class="sxs-lookup"><span data-stu-id="eb4e2-139">Amount</span></span>|<span data-ttu-id="eb4e2-140">业务数据 — Float</span><span class="sxs-lookup"><span data-stu-id="eb4e2-140">Business Data — Float</span></span>|  
|<span data-ttu-id="eb4e2-141">数量</span><span class="sxs-lookup"><span data-stu-id="eb4e2-141">Quantity</span></span>|<span data-ttu-id="eb4e2-142">业务数据 — Integer</span><span class="sxs-lookup"><span data-stu-id="eb4e2-142">Business Data — Integer</span></span>|  
|<span data-ttu-id="eb4e2-143">已同意</span><span class="sxs-lookup"><span data-stu-id="eb4e2-143">Approved</span></span>|<span data-ttu-id="eb4e2-144">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="eb4e2-144">Business Milestone</span></span>|  
|<span data-ttu-id="eb4e2-145">Delivered</span><span class="sxs-lookup"><span data-stu-id="eb4e2-145">Delivered</span></span>|<span data-ttu-id="eb4e2-146">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="eb4e2-146">Business Milestone</span></span>|  
|<span data-ttu-id="eb4e2-147">拒绝</span><span class="sxs-lookup"><span data-stu-id="eb4e2-147">Denied</span></span>|<span data-ttu-id="eb4e2-148">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="eb4e2-148">Business Milestone</span></span>|  
|<span data-ttu-id="eb4e2-149">Received</span><span class="sxs-lookup"><span data-stu-id="eb4e2-149">Received</span></span>|<span data-ttu-id="eb4e2-150">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="eb4e2-150">Business Milestone</span></span>|  
  
 <span data-ttu-id="eb4e2-151">请注意，“金额”为浮点型，因为它可能是小数值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-151">Note that Amount is a float because it may be a decimal value.</span></span> <span data-ttu-id="eb4e2-152">“数量”为整型，因为在本示例中它通常是整数。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-152">Quantity is an integer because it will always be a whole number in this example.</span></span> <span data-ttu-id="eb4e2-153">Approved、Delivered、Denied 和 Received 都是采购订单流程中的里程碑。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-153">Approved, Delivered, Denied, and Received are all milestones in the purchase order process.</span></span>  
  
## <a name="views"></a><span data-ttu-id="eb4e2-154">视图</span><span class="sxs-lookup"><span data-stu-id="eb4e2-154">Views</span></span>  
 <span data-ttu-id="eb4e2-155">创建视图可以向用户公开活动的数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-155">You create views to expose data from an activity to users.</span></span> <span data-ttu-id="eb4e2-156">在创建基于采购订单活动的视图时，可以定义活动项背后的数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-156">When you create a view based on the purchase order activity, you define the data behind the activity items.</span></span> <span data-ttu-id="eb4e2-157">可以将 BAM 中的视图数据定义为维度、度量值、持续时间、里程碑组和进度维度。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-157">You define view data in BAM as dimensions, measures, durations, milestone groups, and progress dimensions.</span></span>  
  
 <span data-ttu-id="eb4e2-158">视图包含一个或多个视图项。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-158">A view contains one or more view items.</span></span> <span data-ttu-id="eb4e2-159">您可以创建以下类型的视图项：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-159">You can create the following types of view items:</span></span>  
  
-   <span data-ttu-id="eb4e2-160">持续时间</span><span class="sxs-lookup"><span data-stu-id="eb4e2-160">Durations</span></span>  
  
-   <span data-ttu-id="eb4e2-161">里程碑组</span><span class="sxs-lookup"><span data-stu-id="eb4e2-161">Milestone groups</span></span>  
  
-   <span data-ttu-id="eb4e2-162">Aggregations</span><span class="sxs-lookup"><span data-stu-id="eb4e2-162">Aggregations</span></span>  
  
### <a name="durations"></a><span data-ttu-id="eb4e2-163">持续时间</span><span class="sxs-lookup"><span data-stu-id="eb4e2-163">Durations</span></span>  
 <span data-ttu-id="eb4e2-164">持续时间为时间间隔。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-164">Durations are time intervals.</span></span> <span data-ttu-id="eb4e2-165">持续时间是通过定义时间间隔开始和结束时间的里程碑来描述的。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-165">Durations are described in terms of the milestones that define the start and end of time intervals.</span></span> <span data-ttu-id="eb4e2-166">下表显示了可从前一表中列出的里程碑得到的持续时间。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-166">The following table shows the durations you can make from the milestones listed in the previous table.</span></span>  
  
|<span data-ttu-id="eb4e2-167">Duration</span><span class="sxs-lookup"><span data-stu-id="eb4e2-167">Duration</span></span>|<span data-ttu-id="eb4e2-168">开始里程碑</span><span class="sxs-lookup"><span data-stu-id="eb4e2-168">Start milestone</span></span>|<span data-ttu-id="eb4e2-169">结束里程碑</span><span class="sxs-lookup"><span data-stu-id="eb4e2-169">End milestone</span></span>|  
|--------------|---------------------|-------------------|  
|<span data-ttu-id="eb4e2-170">1</span><span class="sxs-lookup"><span data-stu-id="eb4e2-170">1</span></span>|<span data-ttu-id="eb4e2-171">Received</span><span class="sxs-lookup"><span data-stu-id="eb4e2-171">Received</span></span>|<span data-ttu-id="eb4e2-172">已同意</span><span class="sxs-lookup"><span data-stu-id="eb4e2-172">Approved</span></span>|  
|<span data-ttu-id="eb4e2-173">2</span><span class="sxs-lookup"><span data-stu-id="eb4e2-173">2</span></span>|<span data-ttu-id="eb4e2-174">Received</span><span class="sxs-lookup"><span data-stu-id="eb4e2-174">Received</span></span>|<span data-ttu-id="eb4e2-175">Delivered</span><span class="sxs-lookup"><span data-stu-id="eb4e2-175">Delivered</span></span>|  
|<span data-ttu-id="eb4e2-176">3</span><span class="sxs-lookup"><span data-stu-id="eb4e2-176">3</span></span>|<span data-ttu-id="eb4e2-177">Received</span><span class="sxs-lookup"><span data-stu-id="eb4e2-177">Received</span></span>|<span data-ttu-id="eb4e2-178">拒绝</span><span class="sxs-lookup"><span data-stu-id="eb4e2-178">Denied</span></span>|  
|<span data-ttu-id="eb4e2-179">4</span><span class="sxs-lookup"><span data-stu-id="eb4e2-179">4</span></span>|<span data-ttu-id="eb4e2-180">已同意</span><span class="sxs-lookup"><span data-stu-id="eb4e2-180">Approved</span></span>|<span data-ttu-id="eb4e2-181">Delivered</span><span class="sxs-lookup"><span data-stu-id="eb4e2-181">Delivered</span></span>|  
  
 <span data-ttu-id="eb4e2-182">在本表中，可以看到第一个持续时间（持续时间 1）是从 BizTalk Server 收到采购订单到批准采购订单的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-182">In this table, you can see that the first duration (Duration 1) is the time interval that starts when a purchase order is received by BizTalk Server, and ends when the purchase order is approved.</span></span>  
  
### <a name="milestone-groups"></a><span data-ttu-id="eb4e2-183">里程碑组</span><span class="sxs-lookup"><span data-stu-id="eb4e2-183">Milestone groups</span></span>  
 <span data-ttu-id="eb4e2-184">您可以创建里程碑组，将一组里程碑看作一个简单实体，例如，流程的开始里程碑和结束里程碑。这可以创建一个里程碑来表示整个流程长度。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-184">You create milestone groups to treat a set of milestones as a single entity, for example, the beginning and ending milestones for a process, which creates a single milestone to represent the entire length of the process.</span></span>  
  
### <a name="aggregations"></a><span data-ttu-id="eb4e2-185">Aggregations</span><span class="sxs-lookup"><span data-stu-id="eb4e2-185">Aggregations</span></span>  
 <span data-ttu-id="eb4e2-186">使用聚合可以缩短刷新数据库数据的响应时间。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-186">You use aggregations to improve the response time for refreshing data from the database.</span></span> <span data-ttu-id="eb4e2-187">Excel 将聚合定义为预先计算的数据汇总，通过在提问之前准备好答案的方式来提高查询响应时间。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-187">Excel defines aggregations as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="eb4e2-188">例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-188">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="eb4e2-189">然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-189">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="eb4e2-190">下图显示的是预先计算的聚合数据的示例。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-190">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
  
 <span data-ttu-id="eb4e2-191">该图汇总了在两个月内发送到特定地点的各种产品的数量。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-191">The figure summarizes the numbers of each product shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="eb4e2-192">通常，Excel 将此数据定义为度量值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-192">Excel typically defines this data as measure.</span></span> <span data-ttu-id="eb4e2-193">Excel 将用于筛选和分类的数据定义为维度。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-193">The data used for filtering and categorization, Excel defines as dimension.</span></span>  
  
 <span data-ttu-id="eb4e2-194">在 BAM 工作簿中，可以定义两种类型的聚合：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-194">You can define two types of aggregations in the BAM workbook:</span></span>  
  
-   <span data-ttu-id="eb4e2-195">实时聚合</span><span class="sxs-lookup"><span data-stu-id="eb4e2-195">Real-time aggregations</span></span>  
  
-   <span data-ttu-id="eb4e2-196">计划的聚合</span><span class="sxs-lookup"><span data-stu-id="eb4e2-196">Scheduled aggregations</span></span>  
  
### <a name="real-time-aggregations"></a><span data-ttu-id="eb4e2-197">实时聚合</span><span class="sxs-lookup"><span data-stu-id="eb4e2-197">Real-time aggregations</span></span>  
 <span data-ttu-id="eb4e2-198">使用实时聚合 (RTA) 您可以看到业务流程的当前状态，并能够轻松地确定流程瓶颈。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-198">Real-time aggregations (RTA) allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="eb4e2-199">BAM 数据显示在透视表中。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-199">BAM data is displayed in a pivot table.</span></span> <span data-ttu-id="eb4e2-200">您可以将 BAM 透视表定义为 RTA 或计划的聚合。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-200">You can define a BAM pivot table as an RTA or a scheduled aggregation.</span></span> <span data-ttu-id="eb4e2-201">RTA 可为您提供最新的数据视图，例如，特定 PO 在发货流程中所处的位置。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-201">An RTA gives you an up-to-the-minute view of your data, for example, where a particular PO is in the shipping process.</span></span> <span data-ttu-id="eb4e2-202">您可以随时刷新屏幕以更新数据视图。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-202">You can refresh your screen to update the view of the data throughout the day.</span></span>  
  
 <span data-ttu-id="eb4e2-203">在某些情况下，多维聚合的特定切片对时间非常敏感，需要它们实时可用。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-203">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="eb4e2-204">例如，您的企业出售的是容易腐烂的产品，因而您希望各个交货阶段的产品数量的聚合实时可用。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-204">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="eb4e2-205">同时，您还需要在月底获得其他聚合，如典型客户的年龄，以便进行商业智能分析。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-205">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb4e2-206">不要定义使用同一个 BAM 活动的多个 RTA。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-206">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="eb4e2-207">否则，当您存档 BAM 数据时，RTA 数据将不正确。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-207">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="eb4e2-208">有关浏览多维数据的信息，请参阅 Excel 帮助中的透视表主题。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-208">For information about browsing multidimensional data, see the PivotTable topic in Excel Help.</span></span>  
  
### <a name="scheduled-aggregations"></a><span data-ttu-id="eb4e2-209">计划的聚合</span><span class="sxs-lookup"><span data-stu-id="eb4e2-209">Scheduled aggregations</span></span>  
 <span data-ttu-id="eb4e2-210">默认情况下，所有 BAM 聚合都是计划聚合。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-210">All BAM aggregations are scheduled aggregations by default.</span></span> <span data-ttu-id="eb4e2-211">计划聚合表示特定时间的业务快照，例如，今天上午发货活动的摘要。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-211">A scheduled aggregation represents a snapshot of the business at a specific time, for example, a summary of this morning's shipments.</span></span> <span data-ttu-id="eb4e2-212">请询问数据库管理员何时处理聚合，然后您可以查看历史数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-212">Ask your database administrator when your aggregations are processed, and then you can look at the historical data.</span></span>  
  
### <a name="dimensions-and-measures"></a><span data-ttu-id="eb4e2-213">维度和度量值</span><span class="sxs-lookup"><span data-stu-id="eb4e2-213">Dimensions and Measures</span></span>  
 <span data-ttu-id="eb4e2-214">使用维度和度量值可以创建数据聚合：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-214">You use dimensions and measures to create data aggregations:</span></span>  
  
-   <span data-ttu-id="eb4e2-215">维度描述事实。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-215">Dimensions describe a fact.</span></span>  
  
-   <span data-ttu-id="eb4e2-216">度量值为事实的值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-216">Measures are fact values.</span></span>  
  
 <span data-ttu-id="eb4e2-217">例如，事实可以是库存中有“3 辆红色轿车”。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-217">For example, a fact could be “3 red cars” in inventory.</span></span> <span data-ttu-id="eb4e2-218">产品的说明:"car"和"红色"是维度。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-218">The description of the product: "car" and "red" are dimensions.</span></span> <span data-ttu-id="eb4e2-219">事实的值“3”为度量值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-219">The value of the fact "3" is a measure.</span></span> <span data-ttu-id="eb4e2-220">如果每辆轿车的价格包括在事实中，则轿车价格是维度，而库存中轿车的平均价格是度量值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-220">If the price of each car is included in the fact, the car price is a dimension, but the average price of cars in inventory is a measure.</span></span> <span data-ttu-id="eb4e2-221">Microsoft SQL Server 联机丛书将度量值描述为“经过聚合和分析的中心值”。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-221">Microsoft SQL Server Books Online describes a measure as "the central values that are aggregated and analyzed."</span></span> <span data-ttu-id="eb4e2-222">换言之，如果可以计算某个值、对其求平均数，或者通过执行数学函数运算来得到值，则该值为度量值。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-222">In other words, if you can count it, average it, or otherwise perform mathematical functions to get it, it is a measure.</span></span>  
  
 <span data-ttu-id="eb4e2-223">您可以创建以下类型的维度：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-223">You can create the following types of dimensions:</span></span>  
  
-   <span data-ttu-id="eb4e2-224">进度维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-224">Progress dimension</span></span>  
  
-   <span data-ttu-id="eb4e2-225">数据维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-225">Data dimension</span></span>  
  
-   <span data-ttu-id="eb4e2-226">时间维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-226">Time dimension</span></span>  
  
-   <span data-ttu-id="eb4e2-227">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-227">Numeric range dimension</span></span>  
  
## <a name="progress-dimensions"></a><span data-ttu-id="eb4e2-228">进度维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-228">Progress dimensions</span></span>  
 <span data-ttu-id="eb4e2-229">BAM 引入了新的维度类型： 进度维度。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-229">BAM introduces a new type of dimension: the progress dimension.</span></span> <span data-ttu-id="eb4e2-230">通过创建进度维度，可以创建与正在进行的活动的进度相关的聚合。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-230">You create progress dimensions to create aggregations that relate to the progress of activities still in process.</span></span>  
  
 <span data-ttu-id="eb4e2-231">例如，请考虑一个您将接收 1,000 个采购订单的采购业务流程。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-231">For example, consider a purchasing business process where you receive 1,000 purchase orders.</span></span> <span data-ttu-id="eb4e2-232">可以在行中使用进度维度来创建下表。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-232">You can use the progress dimension on rows to create the following table.</span></span>  
  
|<span data-ttu-id="eb4e2-233">OrderProgress_Level1</span><span class="sxs-lookup"><span data-stu-id="eb4e2-233">OrderProgress_Level1</span></span>|<span data-ttu-id="eb4e2-234">Count</span><span class="sxs-lookup"><span data-stu-id="eb4e2-234">Count</span></span>|  
|---------------------------|-----------|  
|<span data-ttu-id="eb4e2-235">Received</span><span class="sxs-lookup"><span data-stu-id="eb4e2-235">Received</span></span>|<span data-ttu-id="eb4e2-236">1000</span><span class="sxs-lookup"><span data-stu-id="eb4e2-236">1000</span></span>|  
  
 <span data-ttu-id="eb4e2-237">然后，可以打开 Received 流程查看有关活动进度的详细信息，例如：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-237">You can then open the Received process to view further details about the progress of the activities, such as:</span></span>  
  
|||<span data-ttu-id="eb4e2-238">Count</span><span class="sxs-lookup"><span data-stu-id="eb4e2-238">Count</span></span>|  
|------|------|-----------|  
|<span data-ttu-id="eb4e2-239">Received</span><span class="sxs-lookup"><span data-stu-id="eb4e2-239">Received</span></span>|<span data-ttu-id="eb4e2-240">Evaluating</span><span class="sxs-lookup"><span data-stu-id="eb4e2-240">Evaluating</span></span>|<span data-ttu-id="eb4e2-241">300</span><span class="sxs-lookup"><span data-stu-id="eb4e2-241">300</span></span>|  
||<span data-ttu-id="eb4e2-242">已同意</span><span class="sxs-lookup"><span data-stu-id="eb4e2-242">Approved</span></span>|<span data-ttu-id="eb4e2-243">500</span><span class="sxs-lookup"><span data-stu-id="eb4e2-243">500</span></span>|  
||<span data-ttu-id="eb4e2-244">拒绝</span><span class="sxs-lookup"><span data-stu-id="eb4e2-244">Denied</span></span>|<span data-ttu-id="eb4e2-245">200</span><span class="sxs-lookup"><span data-stu-id="eb4e2-245">200</span></span>|  
  
 <span data-ttu-id="eb4e2-246">这表示在您收到的 1000 个采购订单中，500 个已批准，200 个已拒绝，其他 300 个当前正在评估。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-246">This means that from the 1000 purchase orders you received, 500 were approved, 200 were denied, and 300 are currently being evaluated.</span></span>  
  
 <span data-ttu-id="eb4e2-247">Received、Approved 和 Denied 表示里程碑。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-247">Received, Approved, and Denied represent milestones.</span></span> <span data-ttu-id="eb4e2-248">“数量”列中的相应数字显示了已通过这些里程碑的订单数。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-248">The corresponding numbers in the Count column show how many orders have passed through these milestones.</span></span> <span data-ttu-id="eb4e2-249">Evaluating 是一个阶段，指订单从 Received 里程碑到 Approved 里程碑或从 Received 里程碑到 Denied 里程碑的过程。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-249">Evaluating is a stage that the orders pass through between the Received and Approved or Denied milestones.</span></span>  
  
 <span data-ttu-id="eb4e2-250">可以将进度维度与任何其他维度一起使用。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-250">You can use progress dimensions in combination with any other dimensions.</span></span> <span data-ttu-id="eb4e2-251">例如，如果在行中使用名为“订单进度”的进度维度，在列中使用名为“产品”的数据维度，则将出现以下结果：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-251">For example, by using the progress dimension Order Progress on rows and the data dimension Product on columns, the following results occur:</span></span>  
  
|||<span data-ttu-id="eb4e2-252">网球 Racquets</span><span class="sxs-lookup"><span data-stu-id="eb4e2-252">Tennis Racquets</span></span>|<span data-ttu-id="eb4e2-253">足球</span><span class="sxs-lookup"><span data-stu-id="eb4e2-253">Soccer Balls</span></span>|  
|------|------|---------------------|------------------|  
|<span data-ttu-id="eb4e2-254">Received</span><span class="sxs-lookup"><span data-stu-id="eb4e2-254">Received</span></span>|<span data-ttu-id="eb4e2-255">Evaluating</span><span class="sxs-lookup"><span data-stu-id="eb4e2-255">Evaluating</span></span>|<span data-ttu-id="eb4e2-256">250</span><span class="sxs-lookup"><span data-stu-id="eb4e2-256">250</span></span>|<span data-ttu-id="eb4e2-257">50</span><span class="sxs-lookup"><span data-stu-id="eb4e2-257">50</span></span>|  
||<span data-ttu-id="eb4e2-258">已同意</span><span class="sxs-lookup"><span data-stu-id="eb4e2-258">Approved</span></span>|<span data-ttu-id="eb4e2-259">200</span><span class="sxs-lookup"><span data-stu-id="eb4e2-259">200</span></span>|<span data-ttu-id="eb4e2-260">300</span><span class="sxs-lookup"><span data-stu-id="eb4e2-260">300</span></span>|  
||<span data-ttu-id="eb4e2-261">拒绝</span><span class="sxs-lookup"><span data-stu-id="eb4e2-261">Denied</span></span>|<span data-ttu-id="eb4e2-262">150</span><span class="sxs-lookup"><span data-stu-id="eb4e2-262">150</span></span>|<span data-ttu-id="eb4e2-263">50</span><span class="sxs-lookup"><span data-stu-id="eb4e2-263">50</span></span>|  
  
 <span data-ttu-id="eb4e2-264">进度维度提供图表根据实时聚合 (RTA) 尤其有用的信息。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-264">Progress dimensions provide especially useful information for charts based on real-time aggregations (RTA).</span></span> <span data-ttu-id="eb4e2-265">使用 RTA 您可以看到业务流程的当前状态，并能够轻松地确定流程瓶颈。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-265">RTAs allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="eb4e2-266">在购买的里程碑排序进度维度可以是连续： 第一步完成之后才开始下一步。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-266">The milestones in a purchase order progress dimension can be sequential: the first step is completed before the next step is started.</span></span> <span data-ttu-id="eb4e2-267">或者，里程碑可以按关联顺序一前一后地完成。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-267">Or milestones can be completed in tandem.</span></span> <span data-ttu-id="eb4e2-268">后续步骤是子步骤，关联步骤是同级步骤。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-268">Sequential steps are child steps, and tandem steps are sibling steps.</span></span> <span data-ttu-id="eb4e2-269">在采购订单流程中，一接收到采购订单，验证就开始了。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-269">In the purchase order process, verification begins as soon as the purchase order is received.</span></span> <span data-ttu-id="eb4e2-270">由于 verification 里程碑是与 receive 里程碑同时发生的短暂步骤，因此它是 receive 里程碑的同级。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-270">It is a transitory step that occurs at the same time as the received milestone, and is therefore a sibling to the receive milestone.</span></span> <span data-ttu-id="eb4e2-271">采购订单只有在收到之后才能进行审批，因此 approved 里程碑是 received 里程碑的子级。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-271">A purchase order is approved only after it is received — approved is a child of received.</span></span>  
  
## <a name="data-dimension"></a><span data-ttu-id="eb4e2-272">数据维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-272">Data dimension</span></span>  
 <span data-ttu-id="eb4e2-273">通过定义数据维度，可以将 BAM 活动中某些文本项的值用于行或列。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-273">You define a data dimension to use the value of some text items in the BAM activity on rows or columns.</span></span> <span data-ttu-id="eb4e2-274">例如，名为“产品”的数据维度可用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-274">For example, a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="eb4e2-275">Product</span><span class="sxs-lookup"><span data-stu-id="eb4e2-275">Product</span></span>|<span data-ttu-id="eb4e2-276">Count</span><span class="sxs-lookup"><span data-stu-id="eb4e2-276">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="eb4e2-277">网球拍</span><span class="sxs-lookup"><span data-stu-id="eb4e2-277">Tennis racquets</span></span>|<span data-ttu-id="eb4e2-278">100</span><span class="sxs-lookup"><span data-stu-id="eb4e2-278">100</span></span>|  
|<span data-ttu-id="eb4e2-279">足球</span><span class="sxs-lookup"><span data-stu-id="eb4e2-279">Soccer balls</span></span>|<span data-ttu-id="eb4e2-280">200</span><span class="sxs-lookup"><span data-stu-id="eb4e2-280">200</span></span>|  
  
 <span data-ttu-id="eb4e2-281">此外，您可以在 BAM 视图向导中定义多个数据维度。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-281">Also, you can define more than one data dimension in the BAM View Wizard.</span></span> <span data-ttu-id="eb4e2-282">例如，可以定义名为“位置”，包括“州”和“城市”两个级别的数据维度，使用该数据维度可创建下表：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-282">For example, defining a data dimension named Location with levels for State and City can be used to create the following table:</span></span>  
  
|<span data-ttu-id="eb4e2-283">Product</span><span class="sxs-lookup"><span data-stu-id="eb4e2-283">Product</span></span>|<span data-ttu-id="eb4e2-284">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="eb4e2-284">Los Angeles</span></span>|<span data-ttu-id="eb4e2-285">San Francisco</span><span class="sxs-lookup"><span data-stu-id="eb4e2-285">San Francisco</span></span>|<span data-ttu-id="eb4e2-286">Seattle</span><span class="sxs-lookup"><span data-stu-id="eb4e2-286">Seattle</span></span>|  
|-------------|-----------------|-------------------|-------------|  
|<span data-ttu-id="eb4e2-287">网球拍</span><span class="sxs-lookup"><span data-stu-id="eb4e2-287">Tennis racquets</span></span>|<span data-ttu-id="eb4e2-288">50</span><span class="sxs-lookup"><span data-stu-id="eb4e2-288">50</span></span>|<span data-ttu-id="eb4e2-289">20</span><span class="sxs-lookup"><span data-stu-id="eb4e2-289">20</span></span>|<span data-ttu-id="eb4e2-290">30</span><span class="sxs-lookup"><span data-stu-id="eb4e2-290">30</span></span>|  
|<span data-ttu-id="eb4e2-291">足球</span><span class="sxs-lookup"><span data-stu-id="eb4e2-291">Soccer balls</span></span>|<span data-ttu-id="eb4e2-292">130</span><span class="sxs-lookup"><span data-stu-id="eb4e2-292">130</span></span>|<span data-ttu-id="eb4e2-293">50</span><span class="sxs-lookup"><span data-stu-id="eb4e2-293">50</span></span>|<span data-ttu-id="eb4e2-294">20</span><span class="sxs-lookup"><span data-stu-id="eb4e2-294">20</span></span>|  
  
 <span data-ttu-id="eb4e2-295">在此表格中，“产品”维度用作行，“位置”维度用作列。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-295">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="time-dimension"></a><span data-ttu-id="eb4e2-296">时间维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-296">Time dimension</span></span>  
 <span data-ttu-id="eb4e2-297">通过创建时间维度，可以创建有关时间的聚合。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-297">You create a time dimension to create aggregations with respect to time.</span></span> <span data-ttu-id="eb4e2-298">例如，时间维度可用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-298">For example, a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="eb4e2-299">Year</span><span class="sxs-lookup"><span data-stu-id="eb4e2-299">Year</span></span>|<span data-ttu-id="eb4e2-300">Month</span><span class="sxs-lookup"><span data-stu-id="eb4e2-300">Month</span></span>|<span data-ttu-id="eb4e2-301">Count</span><span class="sxs-lookup"><span data-stu-id="eb4e2-301">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="eb4e2-302">2003</span><span class="sxs-lookup"><span data-stu-id="eb4e2-302">2003</span></span>|<span data-ttu-id="eb4e2-303">January</span><span class="sxs-lookup"><span data-stu-id="eb4e2-303">January</span></span>|<span data-ttu-id="eb4e2-304">120</span><span class="sxs-lookup"><span data-stu-id="eb4e2-304">120</span></span>|  
||<span data-ttu-id="eb4e2-305">February</span><span class="sxs-lookup"><span data-stu-id="eb4e2-305">February</span></span>|<span data-ttu-id="eb4e2-306">230</span><span class="sxs-lookup"><span data-stu-id="eb4e2-306">230</span></span>|  
||<span data-ttu-id="eb4e2-307">March</span><span class="sxs-lookup"><span data-stu-id="eb4e2-307">March</span></span>|<span data-ttu-id="eb4e2-308">350</span><span class="sxs-lookup"><span data-stu-id="eb4e2-308">350</span></span>|  
||<span data-ttu-id="eb4e2-309">April</span><span class="sxs-lookup"><span data-stu-id="eb4e2-309">April</span></span>|<span data-ttu-id="eb4e2-310">280</span><span class="sxs-lookup"><span data-stu-id="eb4e2-310">280</span></span>|  
  
 <span data-ttu-id="eb4e2-311">可以将时间维度与任何其他维度一起使用。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-311">You can combine the time dimension with any other dimension.</span></span> <span data-ttu-id="eb4e2-312">例如，您可以对行使用时间维度，对列使用数据维度，以创建下表：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-312">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|<span data-ttu-id="eb4e2-313">Month</span><span class="sxs-lookup"><span data-stu-id="eb4e2-313">Month</span></span>|<span data-ttu-id="eb4e2-314">网球拍</span><span class="sxs-lookup"><span data-stu-id="eb4e2-314">Tennis racquets</span></span>|<span data-ttu-id="eb4e2-315">足球</span><span class="sxs-lookup"><span data-stu-id="eb4e2-315">Soccer balls</span></span>|  
|-----------|---------------------|------------------|  
|<span data-ttu-id="eb4e2-316">January</span><span class="sxs-lookup"><span data-stu-id="eb4e2-316">January</span></span>|<span data-ttu-id="eb4e2-317">50</span><span class="sxs-lookup"><span data-stu-id="eb4e2-317">50</span></span>|<span data-ttu-id="eb4e2-318">70</span><span class="sxs-lookup"><span data-stu-id="eb4e2-318">70</span></span>|  
|<span data-ttu-id="eb4e2-319">February</span><span class="sxs-lookup"><span data-stu-id="eb4e2-319">February</span></span>|<span data-ttu-id="eb4e2-320">120</span><span class="sxs-lookup"><span data-stu-id="eb4e2-320">120</span></span>|<span data-ttu-id="eb4e2-321">110</span><span class="sxs-lookup"><span data-stu-id="eb4e2-321">110</span></span>|  
|<span data-ttu-id="eb4e2-322">March</span><span class="sxs-lookup"><span data-stu-id="eb4e2-322">March</span></span>|<span data-ttu-id="eb4e2-323">300</span><span class="sxs-lookup"><span data-stu-id="eb4e2-323">300</span></span>|<span data-ttu-id="eb4e2-324">50</span><span class="sxs-lookup"><span data-stu-id="eb4e2-324">50</span></span>|  
|<span data-ttu-id="eb4e2-325">April</span><span class="sxs-lookup"><span data-stu-id="eb4e2-325">April</span></span>|<span data-ttu-id="eb4e2-326">220</span><span class="sxs-lookup"><span data-stu-id="eb4e2-326">220</span></span>|<span data-ttu-id="eb4e2-327">60</span><span class="sxs-lookup"><span data-stu-id="eb4e2-327">60</span></span>|  
  
## <a name="numeric-range-dimension"></a><span data-ttu-id="eb4e2-328">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="eb4e2-328">Numeric range dimension</span></span>  
 <span data-ttu-id="eb4e2-329">使用数值范围维度，可以创建根据友好名称对数值范围进行分类的聚合。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-329">You use numeric range dimensions to create aggregations that categorize ranges of numbers by friendly names.</span></span> <span data-ttu-id="eb4e2-330">例如，业务分析员可以定义一个名为“PO 大小”的数值范围维度，它具有以下范围：</span><span class="sxs-lookup"><span data-stu-id="eb4e2-330">For example, a business analyst can define a numeric range dimension named PO Size with the following ranges:</span></span>  
  
 <span data-ttu-id="eb4e2-331">小：表示采购订单在 0-$100 之间</span><span class="sxs-lookup"><span data-stu-id="eb4e2-331">Small, for purchase orders between 0 and $100</span></span>  
  
 <span data-ttu-id="eb4e2-332">中：表示采购订单在 $100 到 $1,000 之间</span><span class="sxs-lookup"><span data-stu-id="eb4e2-332">Medium, for purchase orders between $100 and $1,000</span></span>  
  
 <span data-ttu-id="eb4e2-333">大：表示采购订单超过 $1,000</span><span class="sxs-lookup"><span data-stu-id="eb4e2-333">Large, for purchase orders exceeding $1,000</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb4e2-334">如果采购订单金额不在定义的范围内（例如采购订单金额小于 0），则 BAM 将自动创建“超出范围”行来容纳超出范围的数据。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-334">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
|<span data-ttu-id="eb4e2-335">PO 大小</span><span class="sxs-lookup"><span data-stu-id="eb4e2-335">PO Size</span></span>|<span data-ttu-id="eb4e2-336">Count</span><span class="sxs-lookup"><span data-stu-id="eb4e2-336">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="eb4e2-337">小</span><span class="sxs-lookup"><span data-stu-id="eb4e2-337">Small</span></span>|<span data-ttu-id="eb4e2-338">500</span><span class="sxs-lookup"><span data-stu-id="eb4e2-338">500</span></span>|  
|<span data-ttu-id="eb4e2-339">Medium</span><span class="sxs-lookup"><span data-stu-id="eb4e2-339">Medium</span></span>|<span data-ttu-id="eb4e2-340">350</span><span class="sxs-lookup"><span data-stu-id="eb4e2-340">350</span></span>|  
|<span data-ttu-id="eb4e2-341">大</span><span class="sxs-lookup"><span data-stu-id="eb4e2-341">Large</span></span>|<span data-ttu-id="eb4e2-342">225</span><span class="sxs-lookup"><span data-stu-id="eb4e2-342">225</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="eb4e2-343">您不能创建引用同一数据别名的两个数值范围维度。</span><span class="sxs-lookup"><span data-stu-id="eb4e2-343">You cannot create two numeric range dimensions that reference the same data alias.</span></span>