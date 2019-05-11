---
title: 查询实时聚合数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72ee6612fc99d9411f0fb26c91c5d8ad6041edf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398294"
---
# <a name="querying-real-time-aggregated-data"></a><span data-ttu-id="3cad0-102">查询实时聚合的数据</span><span class="sxs-lookup"><span data-stu-id="3cad0-102">Querying Real-Time Aggregated Data</span></span>
<span data-ttu-id="3cad0-103">实时聚合 (RTA) 数据是可在 BAM 主导入数据库中动态创建的 SQL 视图中进行查询。</span><span class="sxs-lookup"><span data-stu-id="3cad0-103">The real-time aggregation (RTA) data is available for queries in a dynamically created SQL View in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="3cad0-104">此视图的名称是</span><span class="sxs-lookup"><span data-stu-id="3cad0-104">The name of this view is</span></span>  
  
 <span data-ttu-id="3cad0-105">**bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**</span><span class="sxs-lookup"><span data-stu-id="3cad0-105">**bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**</span></span>  
  
 <span data-ttu-id="3cad0-106">位置</span><span class="sxs-lookup"><span data-stu-id="3cad0-106">Where</span></span>  
  
 <span data-ttu-id="3cad0-107">**\<** *ViewName* **\>** 是 BAM 定义 XML 中 View 元素的 Name 属性即相同相关的 Microsoft Excel 向导中输入视图名称。</span><span class="sxs-lookup"><span data-stu-id="3cad0-107">**\<** *ViewName* **\>** is the Name attribute of the View element in the BAM definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="3cad0-108">**\<** *RTAName* **\>** BAM 生成唯一 BAM 定义 XML 中 RealTimeAggregation 元素的 Name 属性基于视图名称。</span><span class="sxs-lookup"><span data-stu-id="3cad0-108">**\<** *RTAName* **\>** is the Name attribute of the RealTimeAggregation element in the BAM Definition XML, which BAM generates to be unique based on the view name.</span></span>  
  
 <span data-ttu-id="3cad0-109">请务必查询实时聚合的数据时，请注意以下条件：</span><span class="sxs-lookup"><span data-stu-id="3cad0-109">It is important to note the following conditions when querying real-time aggregated data:</span></span>  
  
-   <span data-ttu-id="3cad0-110">若要将聚合保留给定的时间 （默认值为一天） 内，并且永远不会变得很大，则必须配置实时聚合。</span><span class="sxs-lookup"><span data-stu-id="3cad0-110">The real-time aggregations must be configured to keep the aggregations for a given amount of time (the default is one day) and to never grow very large.</span></span> <span data-ttu-id="3cad0-111">而是应在 OLAP 多维数据集中提供旧的聚合。</span><span class="sxs-lookup"><span data-stu-id="3cad0-111">The older aggregations should be available in the OLAP cubes instead.</span></span>  
  
-   <span data-ttu-id="3cad0-112">任何针对 RTA 的查询必须包括筛选将为 RTA 数据的联机时段内的时间维度。</span><span class="sxs-lookup"><span data-stu-id="3cad0-112">Any query against RTA must include filtering on a time dimension that will be inside the online window for the RTA data.</span></span> <span data-ttu-id="3cad0-113">这是必需的因为 BAM 执行数据维护 rta 基于 BAM 数据，以及上的时间戳经过优化，可在区块中放置数据。</span><span class="sxs-lookup"><span data-stu-id="3cad0-113">This is necessary because BAM performs data maintenance for RTAs based  on the  timestamp on the BAM dataand is optimized to drop the data in chunks.</span></span> <span data-ttu-id="3cad0-114">因此如果您只需发送 TRANSACT-SQL 命令"`select *`"，其结果变动不可预见。</span><span class="sxs-lookup"><span data-stu-id="3cad0-114">Thus if you simply send the Transact-SQL command "`select *`", the results will fluctuate unpredictably.</span></span>  
  
-   <span data-ttu-id="3cad0-115">如果活动数据发送到 BAM 通过 DirectEventStream，实时聚合的数据没有延迟 – 调用应用程序中的事务提交后立刻显示。</span><span class="sxs-lookup"><span data-stu-id="3cad0-115">If the activity data is sent to BAM via the DirectEventStream, the real-time aggregated data has no latency – it appears instantaneously when the transaction in the calling Application commits.</span></span>  
  
-   <span data-ttu-id="3cad0-116">如果活动数据发送到 BAM 通过 BufferedEventStream，RTA 数据将显示查询几秒钟后，具体取决于 BAM 事件总线服务和承载 BAM 主导入数据库的 SQL server 的负载。</span><span class="sxs-lookup"><span data-stu-id="3cad0-116">If the activity data is sent to BAM via the BufferedEventStream, the RTA data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service(s) and the SQL server that hosts the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="3cad0-117">BAM 基于它所维护与更改和活动数据存储记录使用触发器中的插入内容同步的表进行实时聚合。</span><span class="sxs-lookup"><span data-stu-id="3cad0-117">BAM bases the real-time aggregation on a table that it maintains in synchronization with the changes or insertions in the activity data storage records using triggers.</span></span> <span data-ttu-id="3cad0-118">有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="3cad0-118">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span> <span data-ttu-id="3cad0-119">因此，实时聚合可以产生显著的性能影响。</span><span class="sxs-lookup"><span data-stu-id="3cad0-119">Thus, the real-time aggregation can have a significant performance impact.</span></span> <span data-ttu-id="3cad0-120">有关详细信息，请参阅[实时聚合](../core/real-time-aggregations.md)。</span><span class="sxs-lookup"><span data-stu-id="3cad0-120">For more information, see [Real-Time Aggregations](../core/real-time-aggregations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cad0-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cad0-121">See Also</span></span>  
 <span data-ttu-id="3cad0-122">[查询计划的聚合数据](../core/querying-scheduled-aggregated-data.md) </span><span class="sxs-lookup"><span data-stu-id="3cad0-122">[Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md) </span></span>  
 [<span data-ttu-id="3cad0-123">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="3cad0-123">Querying BAM Data</span></span>](../core/querying-bam-data.md)