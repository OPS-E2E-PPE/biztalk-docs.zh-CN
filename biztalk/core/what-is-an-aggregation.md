---
title: "什么是聚合？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OLAP cubes, BAM
- BAM, aggregations
- BAM, OLAP cubes
- aggregations [BAM], OLAP cubes
- aggregations [BAM], about aggregations
- aggregations [BAM]
ms.assetid: 77d40602-ef56-4a5b-a18f-56ccbff573a4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24dced4d7075e85b8b002bf90b821ce745f91e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-an-aggregation"></a><span data-ttu-id="4df1f-103">什么是聚合？</span><span class="sxs-lookup"><span data-stu-id="4df1f-103">What Is an Aggregation?</span></span>
<span data-ttu-id="4df1f-104">Excel 将聚合定义为预先计算的数据汇总，通过在提问之前准备好答案的方式来提高查询响应时间。</span><span class="sxs-lookup"><span data-stu-id="4df1f-104">Excel defines aggregations as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="4df1f-105">例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。</span><span class="sxs-lookup"><span data-stu-id="4df1f-105">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="4df1f-106">然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。</span><span class="sxs-lookup"><span data-stu-id="4df1f-106">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="4df1f-107">下图显示的是预先计算的聚合数据的示例。</span><span class="sxs-lookup"><span data-stu-id="4df1f-107">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="4df1f-108">BAM OLAP 多维数据集</span><span class="sxs-lookup"><span data-stu-id="4df1f-108">BAM OLAP Cube</span></span>  
  
 <span data-ttu-id="4df1f-109">上图汇总了在两个月内发送到特定地点的各种产品的数量。</span><span class="sxs-lookup"><span data-stu-id="4df1f-109">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="4df1f-110">通常，Excel 将此数据定义为度量值。</span><span class="sxs-lookup"><span data-stu-id="4df1f-110">Excel typically defines this data as measure.</span></span> <span data-ttu-id="4df1f-111">Excel 将用于筛选和分类的数据定义为维度。</span><span class="sxs-lookup"><span data-stu-id="4df1f-111">The data used for filtering and categorization, Excel defines as dimension.</span></span>  
  
 <span data-ttu-id="4df1f-112">有关浏览多维数据的用户体验，请参阅 Excel 帮助中的透视表主题。</span><span class="sxs-lookup"><span data-stu-id="4df1f-112">For the user experience of browsing multidimensional data, see the PivotTable topic in Excel Help.</span></span>  
  
 <span data-ttu-id="4df1f-113">您可以基于特定视图中的可用数据创建多维活动聚合。</span><span class="sxs-lookup"><span data-stu-id="4df1f-113">You can create multidimensional activity aggregations based on the data available in a specific view.</span></span> <span data-ttu-id="4df1f-114">这些聚合包含度量值（要聚合的数据，如美元表示的金额）和维度（用于进行筛选或分组，如“州”和“城市”）。</span><span class="sxs-lookup"><span data-stu-id="4df1f-114">Those aggregations contain measures (data to aggregate, such as dollar amount) and dimensions (used for filtering or grouping, such as State and City).</span></span>  
  
 <span data-ttu-id="4df1f-115">可以创建联机分析处理 (OLAP) 多维数据集形式的聚合，用于表示特定时间的业务快照，也可以创建实时聚合，实时聚合由业务方案决定，您可以使用多维结构实时查看它。</span><span class="sxs-lookup"><span data-stu-id="4df1f-115">You can create the aggregations in the form of online analytical processing (OLAP) cubes, which represent a snapshot of the business at a specific time, or as real-time aggregations, which the business scenario determines and you see using the multidimensional structure in real time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4df1f-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="4df1f-116">In This Section</span></span>  
  
-   [<span data-ttu-id="4df1f-117">计划的聚合</span><span class="sxs-lookup"><span data-stu-id="4df1f-117">Scheduled Aggregations</span></span>](../core/scheduled-aggregations.md)  
  
-   [<span data-ttu-id="4df1f-118">实时聚合</span><span class="sxs-lookup"><span data-stu-id="4df1f-118">Real-Time Aggregations</span></span>](../core/real-time-aggregations.md)