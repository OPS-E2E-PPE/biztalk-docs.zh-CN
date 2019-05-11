---
title: 查询计划的聚合数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, scheduled data
- queries [BAM], scheduled data
ms.assetid: fb785ec0-7862-4d83-bb6f-0ebd69a28ce6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d088f0affe630ecf2df727cc89ceffc6f82855d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398271"
---
# <a name="querying-scheduled-aggregated-data"></a><span data-ttu-id="a33ea-102">查询计划的聚合数据</span><span class="sxs-lookup"><span data-stu-id="a33ea-102">Querying Scheduled Aggregated Data</span></span>
<span data-ttu-id="a33ea-103">可通过 BAM 分析数据库中的动态创建 OLAP 多维数据集的查询计划的聚合数据。</span><span class="sxs-lookup"><span data-stu-id="a33ea-103">Scheduled aggregation data is available to queries through dynamically created OLAP cubes in the  BAM Analysis database.</span></span>  
  
 <span data-ttu-id="a33ea-104">此多维数据集的名称是相同的 BAM 定义 XML 中 View 元素的 Name 属性与在 Excel 向导中输入的视图名称相同。</span><span class="sxs-lookup"><span data-stu-id="a33ea-104">The name of this cube is the same as the Name attribute of the View element in the BAM definition XML, which is the same as the view name entered in the Excel wizards.</span></span> <span data-ttu-id="a33ea-105">BAM 将刷新此多维数据集时运行数据转换服务 (DTS) 包 BAM_AN_\<*ViewName*\>，其中\< *ViewName* \>是的名称描述你在 Excel 向导中使用。</span><span class="sxs-lookup"><span data-stu-id="a33ea-105">BAM refreshes this cube when you run the Data Transformation Services (DTS) package BAM_AN_\<*ViewName*\>, where the \<*ViewName*\> is the name of the view described you used in the Excel wizards.</span></span>  
  
 <span data-ttu-id="a33ea-106">请务必在查询计划的聚合的数据时注意下列情况：</span><span class="sxs-lookup"><span data-stu-id="a33ea-106">It is important to note the following conditions when querying scheduled aggregated data:</span></span>  
  
-   <span data-ttu-id="a33ea-107">这是业务的虚拟多维数据集包含快照，在开始执行 DTS 包的确切时间。</span><span class="sxs-lookup"><span data-stu-id="a33ea-107">This is a virtual cube containing a snapshot of the business at the exact moment that the DTS package execution started.</span></span> <span data-ttu-id="a33ea-108">它包含聚合已完成的活动以及与仍在进行中。</span><span class="sxs-lookup"><span data-stu-id="a33ea-108">It contains aggregations both for the completed activities and for the ones still in progress.</span></span> <span data-ttu-id="a33ea-109">您可以使用进度维度对筛选器或组聚合相应地。</span><span class="sxs-lookup"><span data-stu-id="a33ea-109">You can use the progress dimension to filter or group the aggregations accordingly.</span></span>  
  
-   <span data-ttu-id="a33ea-110">如果您不感兴趣的当前活动 （例如，如果他们完成非常快） 可以查询相应的真实多维数据集\< *ViewName*\>#Completed。</span><span class="sxs-lookup"><span data-stu-id="a33ea-110">If you are never interested in the current activities (for example, if they complete very fast) you can query the corresponding real cube \<*ViewName*\>#Completed.</span></span>  
  
-   <span data-ttu-id="a33ea-111">如果此外还有实时聚合，安排 DTS 包，比为实时聚合设置联机时段更频繁地刷新多维数据集。</span><span class="sxs-lookup"><span data-stu-id="a33ea-111">If you also have real-time aggregations, schedule the DTS package for refreshing the cube more frequently than the online window you set for the real-time aggregations.</span></span> <span data-ttu-id="a33ea-112">否则，将有一个没有聚合的时段。</span><span class="sxs-lookup"><span data-stu-id="a33ea-112">Otherwise, there will be a window of time for which you do not have aggregations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33ea-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a33ea-113">See Also</span></span>  
 [<span data-ttu-id="a33ea-114">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="a33ea-114">Querying BAM Data</span></span>](../core/querying-bam-data.md)