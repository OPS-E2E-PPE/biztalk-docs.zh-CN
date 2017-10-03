---
title: "BAM 门户中的聚合 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, pivot tables
- BAM, data analysis
- pivot tables [BAM portal]
- BAM portal, charts
- data, analysis [BAM]
- data, OLAP cubes
- aggregations [BAM], BAM portal
- charts, BAM portal
- BAM portal, aggregations
ms.assetid: 1c689563-714b-4573-9c18-a5b0efe97fb8
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43ef0adfacea0a29ea47584ed545884ffb8fa8bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="aggregations-in-the-bam-portal"></a><span data-ttu-id="23b00-102">BAM 门户中的聚合</span><span class="sxs-lookup"><span data-stu-id="23b00-102">Aggregations in the BAM Portal</span></span>
<span data-ttu-id="23b00-103">聚合是指预先计算的数据表，用于对 OLAP 多维数据集进行分析处理。</span><span class="sxs-lookup"><span data-stu-id="23b00-103">Aggregations are tables of precalculated data you can use for analytical processing with an OLAP cube.</span></span> <span data-ttu-id="23b00-104">使用聚合可以更有效地查询多维数据库。</span><span class="sxs-lookup"><span data-stu-id="23b00-104">Aggregations facilitate the efficient querying of multidimensional databases.</span></span> <span data-ttu-id="23b00-105">在使用用于 Excel 的 BAM 加载项创建和部署观察模型（业务数据的高级定义）时，所创建的聚合可以迅速对与关键性能指标 (KPI) 相关的数据集合进行计算。</span><span class="sxs-lookup"><span data-stu-id="23b00-105">When you create and deploy your observation model (the high-level definition of your business data) using the BAM Add-In for Excel, you create aggregations that you can use to quickly evaluate collections of data relating your Key Performance Indicators (KPIs).</span></span>  
  
## <a name="types-of-aggregations"></a><span data-ttu-id="23b00-106">聚合的类型</span><span class="sxs-lookup"><span data-stu-id="23b00-106">Types of aggregations</span></span>  
 <span data-ttu-id="23b00-107">聚合可以是计划聚合，也可以是实时聚合。</span><span class="sxs-lookup"><span data-stu-id="23b00-107">Aggregations can be either scheduled or real-time.</span></span> <span data-ttu-id="23b00-108">计划聚合是 OLAP 多维数据集，表示指定时间业务数据的快照。</span><span class="sxs-lookup"><span data-stu-id="23b00-108">Scheduled aggregations are OLAP cubes, which represent a snapshot of your business data at a time you specify.</span></span> <span data-ttu-id="23b00-109">使用实时聚合可以获得基于您所指定的触发点的业务数据的视图，使 BAM 系统能够在达到某个 KPI 时立即通过警报通知您。</span><span class="sxs-lookup"><span data-stu-id="23b00-109">Real-time aggregations allow a view of your business data based on trigger points that you specify, allowing the BAM system to notify you through an alert as soon as a KPI has been reached.</span></span>  
  
## <a name="pivottable-view"></a><span data-ttu-id="23b00-110">数据透视表视图</span><span class="sxs-lookup"><span data-stu-id="23b00-110">PivotTable View</span></span>  
 <span data-ttu-id="23b00-111">“数据透视表视图”区域显示您使用用于 Excel 的 BAM 加载项设计的数据透视表。</span><span class="sxs-lookup"><span data-stu-id="23b00-111">The PivotTable View area displays the PivotTable report that you design using the BAM Add-In for Excel.</span></span> <span data-ttu-id="23b00-112">Office Web 组件允许您将操作数据透视表来呈现最符合你的需求的数据视图...</span><span class="sxs-lookup"><span data-stu-id="23b00-112">The Office Web Components allow you to manipulate the PivotTable report to present the view of the data that best fits your needs..</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23b00-113">在查看数据透视表时，如果已经到达活动中的里程碑，而这些里程碑并未在进度维度中使用，则实时聚合 (RTA) 和预先计算的聚合（OLAP 实现）中的一些行可能包含空数据。</span><span class="sxs-lookup"><span data-stu-id="23b00-113">When viewing a PivotTable report it is possible that some rows could contain null data in both real-time aggregations (RTAs) and precalculated aggregations (an OLAP implementation) if the milestones in the activity have been reached but are not used in the progress dimension.</span></span> <span data-ttu-id="23b00-114">如果进度维度的上下文中使用了时间维度，而时间维度锚定到了“已确认”而不是“已收到”里程碑，则也可能会出现包含空数据的行。</span><span class="sxs-lookup"><span data-stu-id="23b00-114">It is also possible to encounter rows with null data if the time dimension is used in the context of a progress dimension and is anchored to a milestone such as "acknowledged" instead of "received."</span></span> <span data-ttu-id="23b00-115">在这种情况下，将接收到一个活动实例并触发“已收到”里程碑，但该活动尚未触发“已确认”里程碑，因此，时间维度行中将出现零。</span><span class="sxs-lookup"><span data-stu-id="23b00-115">In this case an activity instance is received and triggers the received milestone, but the activity has not yet triggered the acknowledge milestone and a zero will appear in the time dimension row.</span></span>  <span data-ttu-id="23b00-116">为避免出现这种情况，请将时间维度链接到“已收到”里程碑。</span><span class="sxs-lookup"><span data-stu-id="23b00-116">To avoid this situation, link the time dimension up to the received milestone.</span></span>  
  
 ![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")  
  
 <span data-ttu-id="23b00-117">在 BAM 门户中使用 Office Web 组件修改数据透视表时，请谨记以下几点：</span><span class="sxs-lookup"><span data-stu-id="23b00-117">Keep these points in mind when using the Office Web Components in the BAM portal to modify your PivotTable report:</span></span>  
  
-   <span data-ttu-id="23b00-118">Excel 中的数据透视表内包含一个“页”字段，您可以在其中输入时间切片维度。</span><span class="sxs-lookup"><span data-stu-id="23b00-118">PivotTable reports in Excel include a Page field where you can put a time slice dimension.</span></span> <span data-ttu-id="23b00-119">BAM 门户使用 Office Web Components 不包括页字段。</span><span class="sxs-lookup"><span data-stu-id="23b00-119">The Office Web Components used by the BAM portal do not include a Page field.</span></span> <span data-ttu-id="23b00-120">如果 Excel 数据透视表使用“页”字段来表示维度，此字段的数据不显示在 BAM 门户的数据透视表中。</span><span class="sxs-lookup"><span data-stu-id="23b00-120">If your Excel PivotTable report uses the Page field for any dimensions, the data for this field is not displayed in your PivotTable report in the BAM portal.</span></span>  
  
-   <span data-ttu-id="23b00-121">Office Web 组件在 BAM 门户的内容框架中显示数据。</span><span class="sxs-lookup"><span data-stu-id="23b00-121">The Office Web Components display data in the content frame of the BAM portal.</span></span> <span data-ttu-id="23b00-122">因为此框架的空间有限，从字段列表向列区域添加维度时，会造成在显示的数据透视表中看不到部分或全部维度名。</span><span class="sxs-lookup"><span data-stu-id="23b00-122">Because of the space limitations of this frame, adding dimensions from the field list to the columns area can cause the display of the PivotTable to move dimension names partly or wholly out of view.</span></span>  
  
 <span data-ttu-id="23b00-123">有关数据透视表的详细信息，请参阅"数据透视表术语解释"网址[http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416)。</span><span class="sxs-lookup"><span data-stu-id="23b00-123">For more information about PivotTables, see "PivotTable terminology demystified" at [http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416).</span></span>  
  
## <a name="chart-view"></a><span data-ttu-id="23b00-124">图表视图</span><span class="sxs-lookup"><span data-stu-id="23b00-124">Chart View</span></span>  
 <span data-ttu-id="23b00-125">“图表视图”区域以图形形式显示聚合。</span><span class="sxs-lookup"><span data-stu-id="23b00-125">The Chart View area displays the aggregation in a graphical manner.</span></span> <span data-ttu-id="23b00-126">使用 Office Web 组件，可以通过图表视图处理聚合的详细信息，根据需要调整报告的数据。</span><span class="sxs-lookup"><span data-stu-id="23b00-126">The Office Web Components allow you to manipulate the details of the aggregation through the chart view to adjust the reported data as needed.</span></span> <span data-ttu-id="23b00-127">在拖放“图表字段”列表中的数据项调整聚合时，该聚合的数据透视表将自动更新，反映您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="23b00-127">When you adjust the aggregation by dragging and dropping data items from the Chart Field list, the PivotTable report for the aggregation is automatically updated to reflect your changes.</span></span> <span data-ttu-id="23b00-128">您可以细查数据透视表以在新聚合视图上创建警报。</span><span class="sxs-lookup"><span data-stu-id="23b00-128">You can drill through the PivotTable to create an alert on the new aggregation view.</span></span>  
  
 ![](../core/media/aggregationchartview.gif "AggregationChartView")  
  
## <a name="more"></a><span data-ttu-id="23b00-129">更多信息</span><span class="sxs-lookup"><span data-stu-id="23b00-129">More</span></span>  
  
-   [<span data-ttu-id="23b00-130">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="23b00-130">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="23b00-131">如何查看活动搜索的结果</span><span class="sxs-lookup"><span data-stu-id="23b00-131">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [<span data-ttu-id="23b00-132">如何修改聚合</span><span class="sxs-lookup"><span data-stu-id="23b00-132">How to Modify an Aggregation</span></span>](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a><span data-ttu-id="23b00-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23b00-133">See Also</span></span>  
 [<span data-ttu-id="23b00-134">聚合是什么？</span><span class="sxs-lookup"><span data-stu-id="23b00-134">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)