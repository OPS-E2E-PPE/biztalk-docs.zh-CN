---
title: "实时查询聚合数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b71c3adbcbe5aaaea4d9fa4bf25b2aa4191c580
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="querying-real-time-aggregated-data"></a><span data-ttu-id="0587d-102">查询实时的聚合的数据</span><span class="sxs-lookup"><span data-stu-id="0587d-102">Querying Real-Time Aggregated Data</span></span>
<span data-ttu-id="0587d-103">实时聚合 (RTA) 数据可在主导入数据库中动态创建的 SQL 视图内进行查询。</span><span class="sxs-lookup"><span data-stu-id="0587d-103">The real-time aggregation (RTA) data is available for queries in a dynamically created SQL View in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="0587d-104">此视图的名称是</span><span class="sxs-lookup"><span data-stu-id="0587d-104">The name of this view is</span></span>  
  
 <span data-ttu-id="0587d-105">**bam_\<**  *ViewName*  **\>_\<**  *RTAName*  **\>_RTAView**</span><span class="sxs-lookup"><span data-stu-id="0587d-105">**bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**</span></span>  
  
 <span data-ttu-id="0587d-106">位置</span><span class="sxs-lookup"><span data-stu-id="0587d-106">Where</span></span>  
  
 <span data-ttu-id="0587d-107">**\<***ViewName*  **\>** 为 BAM 定义 XML 中的视图元素的名称属性即相同在相关的 Microsoft Excel 向导中输入视图名称。</span><span class="sxs-lookup"><span data-stu-id="0587d-107">**\<** *ViewName* **\>** is the Name attribute of the View element in the BAM definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="0587d-108">**\<***RTAName*  **\>** 在 BAM 定义 XML 中，BAM 生成是唯一的 RealTimeAggregation 元素的名称属性基于的视图名称。</span><span class="sxs-lookup"><span data-stu-id="0587d-108">**\<** *RTAName* **\>** is the Name attribute of the RealTimeAggregation element in the BAM Definition XML, which BAM generates to be unique based on the view name.</span></span>  
  
 <span data-ttu-id="0587d-109">在查询实时聚合数据时，请一定要注意下列情况：</span><span class="sxs-lookup"><span data-stu-id="0587d-109">It is important to note the following conditions when querying real-time aggregated data:</span></span>  
  
-   <span data-ttu-id="0587d-110">必须对实时聚合进行配置，将聚合保留给定的时间（默认值为一天），而且要限制其大小，不能增长得太大。</span><span class="sxs-lookup"><span data-stu-id="0587d-110">The real-time aggregations must be configured to keep the aggregations for a given amount of time (the default is one day) and to never grow very large.</span></span> <span data-ttu-id="0587d-111">旧的聚合应该从 OLAP 多维数据集中获得。</span><span class="sxs-lookup"><span data-stu-id="0587d-111">The older aggregations should be available in the OLAP cubes instead.</span></span>  
  
-   <span data-ttu-id="0587d-112">任何针对 RTA 的查询都必须包括对处于 RTA 数据的联机时段内的时间维度所进行的筛选。</span><span class="sxs-lookup"><span data-stu-id="0587d-112">Any query against RTA must include filtering on a time dimension that will be inside the online window for the RTA data.</span></span> <span data-ttu-id="0587d-113">之所以必须这样做，是因为 BAM 基于 BAM 数据的时间戳执行 RTA 数据维护，并且 BAM 已优化为以块的形式删除数据。</span><span class="sxs-lookup"><span data-stu-id="0587d-113">This is necessary because BAM performs data maintenance for RTAs based  on the  timestamp on the BAM dataand is optimized to drop the data in chunks.</span></span> <span data-ttu-id="0587d-114">因此，如果发出 Transact-SQL 命令“`select *`”，其结果变动很大，难以预测。</span><span class="sxs-lookup"><span data-stu-id="0587d-114">Thus if you simply send the Transact-SQL command "`select *`", the results will fluctuate unpredictably.</span></span>  
  
-   <span data-ttu-id="0587d-115">如果活动数据通过 DirectEventStream 发送到 BAM，则实时聚合数据没有延迟，即这些数据在调用应用程序中的事务提交后立刻显示出来。</span><span class="sxs-lookup"><span data-stu-id="0587d-115">If the activity data is sent to BAM via the DirectEventStream, the real-time aggregated data has no latency – it appears instantaneously when the transaction in the calling Application commits.</span></span>  
  
-   <span data-ttu-id="0587d-116">如果活动数据通过 BufferedEventStream 发送到 BAM，则 RTA 数据将在查询几秒钟后显示，具体的时间取决于 BAM 事件总线服务的负载以及 BAM 主导入数据库的宿主 SQL 服务器。</span><span class="sxs-lookup"><span data-stu-id="0587d-116">If the activity data is sent to BAM via the BufferedEventStream, the RTA data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service(s) and the SQL server that hosts the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="0587d-117">BAM 基于一个自己维护的、与使用触发器的活动数据存储记录中的更改和插入内容保持同步的表进行实时聚合。</span><span class="sxs-lookup"><span data-stu-id="0587d-117">BAM bases the real-time aggregation on a table that it maintains in synchronization with the changes or insertions in the activity data storage records using triggers.</span></span> <span data-ttu-id="0587d-118">有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="0587d-118">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span> <span data-ttu-id="0587d-119">因此，实时聚合可以对性能有很大的影响。</span><span class="sxs-lookup"><span data-stu-id="0587d-119">Thus, the real-time aggregation can have a significant performance impact.</span></span> <span data-ttu-id="0587d-120">有关详细信息，请参阅[实时聚合](../core/real-time-aggregations.md)。</span><span class="sxs-lookup"><span data-stu-id="0587d-120">For more information, see [Real-Time Aggregations](../core/real-time-aggregations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0587d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0587d-121">See Also</span></span>  
 <span data-ttu-id="0587d-122">[查询计划的聚合数据](../core/querying-scheduled-aggregated-data.md) </span><span class="sxs-lookup"><span data-stu-id="0587d-122">[Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md) </span></span>  
 [<span data-ttu-id="0587d-123">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="0587d-123">Querying BAM Data</span></span>](../core/querying-bam-data.md)