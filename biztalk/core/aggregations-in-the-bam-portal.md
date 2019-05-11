---
title: BAM 门户中的聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1055a76039420024a5cbfacf8e63094e00b1b8b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360239"
---
# <a name="aggregations-in-the-bam-portal"></a><span data-ttu-id="ba980-102">BAM 门户中的聚合</span><span class="sxs-lookup"><span data-stu-id="ba980-102">Aggregations in the BAM Portal</span></span>
<span data-ttu-id="ba980-103">聚合是预先计算好的数据可用于分析的 OLAP 多维数据集处理的表。</span><span class="sxs-lookup"><span data-stu-id="ba980-103">Aggregations are tables of precalculated data you can use for analytical processing with an OLAP cube.</span></span> <span data-ttu-id="ba980-104">使用聚合可以更有效地查询多维数据库。</span><span class="sxs-lookup"><span data-stu-id="ba980-104">Aggregations facilitate the efficient querying of multidimensional databases.</span></span> <span data-ttu-id="ba980-105">创建和部署观察模型 （您的业务数据的高级定义） 时使用 excel BAM 外接程序，您创建可用于快速评估您的关键绩效指标 (Kpi) 相关的数据的集合的聚合。</span><span class="sxs-lookup"><span data-stu-id="ba980-105">When you create and deploy your observation model (the high-level definition of your business data) using the BAM Add-In for Excel, you create aggregations that you can use to quickly evaluate collections of data relating your Key Performance Indicators (KPIs).</span></span>  
  
## <a name="types-of-aggregations"></a><span data-ttu-id="ba980-106">聚合类型</span><span class="sxs-lookup"><span data-stu-id="ba980-106">Types of aggregations</span></span>  
 <span data-ttu-id="ba980-107">聚合可以实时或计划。</span><span class="sxs-lookup"><span data-stu-id="ba980-107">Aggregations can be either scheduled or real-time.</span></span> <span data-ttu-id="ba980-108">计划的聚合是 OLAP 多维数据集，它表示在指定的时间业务数据的快照。</span><span class="sxs-lookup"><span data-stu-id="ba980-108">Scheduled aggregations are OLAP cubes, which represent a snapshot of your business data at a time you specify.</span></span> <span data-ttu-id="ba980-109">使用实时聚合可以根据你指定的触发点使 BAM 系统能够通过警报通知你，一旦达到了 KPI 对业务数据的视图。</span><span class="sxs-lookup"><span data-stu-id="ba980-109">Real-time aggregations allow a view of your business data based on trigger points that you specify, allowing the BAM system to notify you through an alert as soon as a KPI has been reached.</span></span>  
  
## <a name="pivottable-view"></a><span data-ttu-id="ba980-110">数据透视表视图</span><span class="sxs-lookup"><span data-stu-id="ba980-110">PivotTable View</span></span>  
 <span data-ttu-id="ba980-111">数据透视表视图区域显示您设计使用 Excel BAM 外接程序的数据透视表报表。</span><span class="sxs-lookup"><span data-stu-id="ba980-111">The PivotTable View area displays the PivotTable report that you design using the BAM Add-In for Excel.</span></span> <span data-ttu-id="ba980-112">Office Web 组件使您可以操作数据透视表报表以显示最符合您需求的数据视图...</span><span class="sxs-lookup"><span data-stu-id="ba980-112">The Office Web Components allow you to manipulate the PivotTable report to present the view of the data that best fits your needs..</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba980-113">查看数据透视表报表时很可能某些行可能包含实时聚合 (Rta) 和预先计算的聚合 （OLAP 实现） 中的空数据，如果已达到活动中的里程碑，但不是使用正在进行中维度。</span><span class="sxs-lookup"><span data-stu-id="ba980-113">When viewing a PivotTable report it is possible that some rows could contain null data in both real-time aggregations (RTAs) and precalculated aggregations (an OLAP implementation) if the milestones in the activity have been reached but are not used in the progress dimension.</span></span> <span data-ttu-id="ba980-114">还有可能会遇到包含 null 数据行，如果时间维度的进度维度的上下文中使用和锚定到里程碑如"已确认"而不是"收到"。</span><span class="sxs-lookup"><span data-stu-id="ba980-114">It is also possible to encounter rows with null data if the time dimension is used in the context of a progress dimension and is anchored to a milestone such as "acknowledged" instead of "received."</span></span> <span data-ttu-id="ba980-115">活动实例在这种情况下收到并触发接收的里程碑，但该活动尚未触发确认里程碑和会在时间维度行中显示零。</span><span class="sxs-lookup"><span data-stu-id="ba980-115">In this case an activity instance is received and triggers the received milestone, but the activity has not yet triggered the acknowledge milestone and a zero will appear in the time dimension row.</span></span>  <span data-ttu-id="ba980-116">若要避免这种情况下，链接到接收里程碑的时间维度。</span><span class="sxs-lookup"><span data-stu-id="ba980-116">To avoid this situation, link the time dimension up to the received milestone.</span></span>  
  
 <span data-ttu-id="ba980-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span><span class="sxs-lookup"><span data-stu-id="ba980-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span></span>  
  
 <span data-ttu-id="ba980-118">在 BAM 门户中使用 Office Web 组件修改数据透视表报表时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="ba980-118">Keep these points in mind when using the Office Web Components in the BAM portal to modify your PivotTable report:</span></span>  
  
- <span data-ttu-id="ba980-119">在 Excel 中的数据透视表报告包括时间切片维度的放置位置的页字段。</span><span class="sxs-lookup"><span data-stu-id="ba980-119">PivotTable reports in Excel include a Page field where you can put a time slice dimension.</span></span> <span data-ttu-id="ba980-120">使用 BAM 门户的 Office Web 组件不包括页字段。</span><span class="sxs-lookup"><span data-stu-id="ba980-120">The Office Web Components used by the BAM portal do not include a Page field.</span></span> <span data-ttu-id="ba980-121">如果 Excel 数据透视表报表页字段用于任何维度，此字段的数据不是显示在 BAM 门户中的数据透视表报表中。</span><span class="sxs-lookup"><span data-stu-id="ba980-121">If your Excel PivotTable report uses the Page field for any dimensions, the data for this field is not displayed in your PivotTable report in the BAM portal.</span></span>  
  
- <span data-ttu-id="ba980-122">Office Web 组件在 BAM 门户内容框架中显示数据。</span><span class="sxs-lookup"><span data-stu-id="ba980-122">The Office Web Components display data in the content frame of the BAM portal.</span></span> <span data-ttu-id="ba980-123">因为此框架的空间有限，从字段列表向列区域添加维度会造成数据透视表移出视图的维度名称部分或全部的显示。</span><span class="sxs-lookup"><span data-stu-id="ba980-123">Because of the space limitations of this frame, adding dimensions from the field list to the columns area can cause the display of the PivotTable to move dimension names partly or wholly out of view.</span></span>  
  
  <span data-ttu-id="ba980-124">有关数据透视表的详细信息，请参阅"数据透视表术语揭密"网址[ http://go.microsoft.com/fwlink/?LinkId=55416 ](http://go.microsoft.com/fwlink/?LinkId=55416)。</span><span class="sxs-lookup"><span data-stu-id="ba980-124">For more information about PivotTables, see "PivotTable terminology demystified" at [http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416).</span></span>  
  
## <a name="chart-view"></a><span data-ttu-id="ba980-125">图表视图</span><span class="sxs-lookup"><span data-stu-id="ba980-125">Chart View</span></span>  
 <span data-ttu-id="ba980-126">图表视图区域以图形方式显示聚合。</span><span class="sxs-lookup"><span data-stu-id="ba980-126">The Chart View area displays the aggregation in a graphical manner.</span></span> <span data-ttu-id="ba980-127">Office Web 组件使您可以操作通过图表视图，以根据需要调整报告的数据聚合的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ba980-127">The Office Web Components allow you to manipulate the details of the aggregation through the chart view to adjust the reported data as needed.</span></span> <span data-ttu-id="ba980-128">当您通过拖放图表字段列表中的数据项调整聚合时，聚合的数据透视表报表自动更新以反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ba980-128">When you adjust the aggregation by dragging and dropping data items from the Chart Field list, the PivotTable report for the aggregation is automatically updated to reflect your changes.</span></span> <span data-ttu-id="ba980-129">您可以钻取数据透视表在新的聚合视图上创建警报。</span><span class="sxs-lookup"><span data-stu-id="ba980-129">You can drill through the PivotTable to create an alert on the new aggregation view.</span></span>  
  
 <span data-ttu-id="ba980-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span><span class="sxs-lookup"><span data-stu-id="ba980-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span></span>  
  
## <a name="more"></a><span data-ttu-id="ba980-131">更多</span><span class="sxs-lookup"><span data-stu-id="ba980-131">More</span></span>  
  
-   [<span data-ttu-id="ba980-132">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="ba980-132">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="ba980-133">如何查看活动搜索的结果</span><span class="sxs-lookup"><span data-stu-id="ba980-133">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [<span data-ttu-id="ba980-134">如何修改聚合</span><span class="sxs-lookup"><span data-stu-id="ba980-134">How to Modify an Aggregation</span></span>](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba980-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba980-135">See Also</span></span>  
 [<span data-ttu-id="ba980-136">聚合概述</span><span class="sxs-lookup"><span data-stu-id="ba980-136">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)