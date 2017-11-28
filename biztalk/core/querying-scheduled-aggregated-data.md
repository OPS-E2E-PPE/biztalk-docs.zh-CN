---
title: "查询计划的聚合数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, scheduled data
- queries [BAM], scheduled data
ms.assetid: fb785ec0-7862-4d83-bb6f-0ebd69a28ce6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30f59716ae94701aa793224500643563ece2681e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="querying-scheduled-aggregated-data"></a><span data-ttu-id="08685-102">查询计划的聚合数据</span><span class="sxs-lookup"><span data-stu-id="08685-102">Querying Scheduled Aggregated Data</span></span>
<span data-ttu-id="08685-103">通过 BAM 分析数据库中动态创建的 OLAP 多维数据集可以对计划的聚合数据进行查询。</span><span class="sxs-lookup"><span data-stu-id="08685-103">Scheduled aggregation data is available to queries through dynamically created OLAP cubes in the  BAM Analysis database.</span></span>  
  
 <span data-ttu-id="08685-104">此多维数据集的名称与 BAM 定义 XML 中 View 元素的 Name 属性相同，这是在 Excel 向导中输入的视图名称。</span><span class="sxs-lookup"><span data-stu-id="08685-104">The name of this cube is the same as the Name attribute of the View element in the BAM definition XML, which is the same as the view name entered in the Excel wizards.</span></span> <span data-ttu-id="08685-105">BAM 刷新此多维数据集时运行数据转换服务 (DTS) 包 BAM_AN_\<*ViewName*>，其中\< *ViewName*> 是所述的视图的名称你在 Excel 向导中使用。</span><span class="sxs-lookup"><span data-stu-id="08685-105">BAM refreshes this cube when you run the Data Transformation Services (DTS) package BAM_AN_\<*ViewName*>, where the \<*ViewName*> is the name of the view described you used in the Excel wizards.</span></span>  
  
 <span data-ttu-id="08685-106">在查询计划的聚合数据时，请一定要注意下列情况：</span><span class="sxs-lookup"><span data-stu-id="08685-106">It is important to note the following conditions when querying scheduled aggregated data:</span></span>  
  
-   <span data-ttu-id="08685-107">这是一个虚拟多维数据集，其中包含的业务快照恰好是在开始执行 DTS 包的时刻生成的。</span><span class="sxs-lookup"><span data-stu-id="08685-107">This is a virtual cube containing a snapshot of the business at the exact moment that the DTS package execution started.</span></span> <span data-ttu-id="08685-108">此多维数据集包含已完成的活动的聚合以及仍在进行中的活动的聚合。</span><span class="sxs-lookup"><span data-stu-id="08685-108">It contains aggregations both for the completed activities and for the ones still in progress.</span></span> <span data-ttu-id="08685-109">您可以使用进度维度对这些聚合相应地进行筛选或分组。</span><span class="sxs-lookup"><span data-stu-id="08685-109">You can use the progress dimension to filter or group the aggregations accordingly.</span></span>  
  
-   <span data-ttu-id="08685-110">如果要从不感兴趣的当前活动 （例如，如果在完成非常快） 可以查询相应的实际多维数据集\< *ViewName*> #Completed。</span><span class="sxs-lookup"><span data-stu-id="08685-110">If you are never interested in the current activities (for example, if they complete very fast) you can query the corresponding real cube \<*ViewName*>#Completed.</span></span>  
  
-   <span data-ttu-id="08685-111">如果此外还有实时聚合，则可以安排 DTS 包，使用比为实时聚合设置的联机时段更高的频率刷新该多维数据集。</span><span class="sxs-lookup"><span data-stu-id="08685-111">If you also have real-time aggregations, schedule the DTS package for refreshing the cube more frequently than the online window you set for the real-time aggregations.</span></span> <span data-ttu-id="08685-112">否则，就会出现一个没有聚合的时间段。</span><span class="sxs-lookup"><span data-stu-id="08685-112">Otherwise, there will be a window of time for which you do not have aggregations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08685-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08685-113">See Also</span></span>  
 [<span data-ttu-id="08685-114">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="08685-114">Querying BAM Data</span></span>](../core/querying-bam-data.md)