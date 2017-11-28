---
title: "定义聚合 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], creating
- Excel add-in [BAM], creating aggregations
- aggregations [BAM], Excel add-in
- aggregations [BAM], about aggregations
ms.assetid: d5bf22d5-f491-4b08-a604-c7158e6e282f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3412615d03fc9a9776d86fddfb062ab343c5aaeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defining-aggregations"></a><span data-ttu-id="99b25-102">定义聚合</span><span class="sxs-lookup"><span data-stu-id="99b25-102">Defining Aggregations</span></span>
<span data-ttu-id="99b25-103">Excel 定义**聚合**为预先计算摘要任务具有的改进查询响应时间的数据的情况下，答案就绪之前进行提问。</span><span class="sxs-lookup"><span data-stu-id="99b25-103">Excel defines **aggregations** as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="99b25-104">例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。</span><span class="sxs-lookup"><span data-stu-id="99b25-104">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="99b25-105">然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。</span><span class="sxs-lookup"><span data-stu-id="99b25-105">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="99b25-106">下图显示的是预先计算的聚合数据的示例。</span><span class="sxs-lookup"><span data-stu-id="99b25-106">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="99b25-107">预先计算的聚合数据</span><span class="sxs-lookup"><span data-stu-id="99b25-107">Pre-calculated Aggregation Data</span></span>  
  
 <span data-ttu-id="99b25-108">上图汇总了在两个月内发送到特定地点的各种产品的数量。</span><span class="sxs-lookup"><span data-stu-id="99b25-108">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="99b25-109">Excel 通常定义此类数据作为**度量值**。</span><span class="sxs-lookup"><span data-stu-id="99b25-109">Excel typically defines this data as **measure**.</span></span> <span data-ttu-id="99b25-110">用于筛选和分类的数据，Excel 将定义为**维度**。</span><span class="sxs-lookup"><span data-stu-id="99b25-110">The data used for filtering and categorization, Excel defines as **dimension**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99b25-111">BAM 不支持使用 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services 的命名实例。</span><span class="sxs-lookup"><span data-stu-id="99b25-111">BAM does not support using named instances for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services.</span></span>  
  
 <span data-ttu-id="99b25-112">浏览多维数据的用户体验，请参阅 Excel 帮助中的数据透视表主题。</span><span class="sxs-lookup"><span data-stu-id="99b25-112">For the user experience of browsing multidimensional data, see the Pivot table topic in Excel Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99b25-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="99b25-113">In This Section</span></span>  
  
-   [<span data-ttu-id="99b25-114">如何定义度量值</span><span class="sxs-lookup"><span data-stu-id="99b25-114">How to Define Measures</span></span>](../core/how-to-define-measures.md)  
  
-   [<span data-ttu-id="99b25-115">定义维度</span><span class="sxs-lookup"><span data-stu-id="99b25-115">Defining Dimensions</span></span>](../core/defining-dimensions.md)  
  
-   [<span data-ttu-id="99b25-116">如何使用数据透视表</span><span class="sxs-lookup"><span data-stu-id="99b25-116">How to Use the PivotTable</span></span>](../core/how-to-use-the-pivottable.md)  
  
-   [<span data-ttu-id="99b25-117">定义实时聚合</span><span class="sxs-lookup"><span data-stu-id="99b25-117">Defining Real-Time Aggregations</span></span>](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a><span data-ttu-id="99b25-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99b25-118">See Also</span></span>  
 [<span data-ttu-id="99b25-119">定义 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="99b25-119">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)