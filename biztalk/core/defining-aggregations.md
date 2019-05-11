---
title: 定义聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], creating
- Excel add-in [BAM], creating aggregations
- aggregations [BAM], Excel add-in
- aggregations [BAM], about aggregations
ms.assetid: d5bf22d5-f491-4b08-a604-c7158e6e282f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a379e27e7805aa7e4b67ad3c94afba65b546c7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352471"
---
# <a name="defining-aggregations"></a><span data-ttu-id="60a04-102">定义聚合</span><span class="sxs-lookup"><span data-stu-id="60a04-102">Defining Aggregations</span></span>
<span data-ttu-id="60a04-103">Excel 将定义**聚合**预先计算的数据汇总，通过缩短查询响应时间作为答案就绪问题提出之前。</span><span class="sxs-lookup"><span data-stu-id="60a04-103">Excel defines **aggregations** as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="60a04-104">例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。</span><span class="sxs-lookup"><span data-stu-id="60a04-104">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="60a04-105">然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。</span><span class="sxs-lookup"><span data-stu-id="60a04-105">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="60a04-106">下图显示的是预先计算的聚合数据的示例。</span><span class="sxs-lookup"><span data-stu-id="60a04-106">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 <span data-ttu-id="60a04-107">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="60a04-107">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
<span data-ttu-id="60a04-108">预先计算的聚合数据</span><span class="sxs-lookup"><span data-stu-id="60a04-108">Pre-calculated Aggregation Data</span></span>  
  
 <span data-ttu-id="60a04-109">上图汇总了在两个月内发送到特定地点的各种产品的数量。</span><span class="sxs-lookup"><span data-stu-id="60a04-109">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="60a04-110">通常，Excel 将定义此类数据作为**度量值**。</span><span class="sxs-lookup"><span data-stu-id="60a04-110">Excel typically defines this data as **measure**.</span></span> <span data-ttu-id="60a04-111">用于筛选和分类的数据，Excel 将定义为**维度**。</span><span class="sxs-lookup"><span data-stu-id="60a04-111">The data used for filtering and categorization, Excel defines as **dimension**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60a04-112">BAM 不支持使用的命名的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services。</span><span class="sxs-lookup"><span data-stu-id="60a04-112">BAM does not support using named instances for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services.</span></span>  
  
 <span data-ttu-id="60a04-113">有关浏览多维数据的用户体验，请参阅 Excel 帮助中的数据透视表主题。</span><span class="sxs-lookup"><span data-stu-id="60a04-113">For the user experience of browsing multidimensional data, see the Pivot table topic in Excel Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60a04-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="60a04-114">In This Section</span></span>  
  
-   [<span data-ttu-id="60a04-115">如何定义度量值</span><span class="sxs-lookup"><span data-stu-id="60a04-115">How to Define Measures</span></span>](../core/how-to-define-measures.md)  
  
-   [<span data-ttu-id="60a04-116">定义维度</span><span class="sxs-lookup"><span data-stu-id="60a04-116">Defining Dimensions</span></span>](../core/defining-dimensions.md)  
  
-   [<span data-ttu-id="60a04-117">如何使用该数据透视表</span><span class="sxs-lookup"><span data-stu-id="60a04-117">How to Use the PivotTable</span></span>](../core/how-to-use-the-pivottable.md)  
  
-   [<span data-ttu-id="60a04-118">定义实时聚合</span><span class="sxs-lookup"><span data-stu-id="60a04-118">Defining Real-Time Aggregations</span></span>](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a><span data-ttu-id="60a04-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="60a04-119">See Also</span></span>  
 [<span data-ttu-id="60a04-120">定义 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="60a04-120">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)