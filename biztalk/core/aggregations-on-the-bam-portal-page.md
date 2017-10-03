---
title: "BAM 门户上的聚合页 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a61df22bf5d07bd1b4d955f2baf884459de52998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="aggregations-on-the-bam-portal-page"></a><span data-ttu-id="1540c-102">BAM 门户上的聚合页</span><span class="sxs-lookup"><span data-stu-id="1540c-102">Aggregations on the BAM Portal Page</span></span>
<span data-ttu-id="1540c-103">当业务最终用户、开发人员和业务分析员需要显示聚合数据时可使用 BAM 门户页。聚合数据是某个数据集的预计算汇总，可以传达该数据集的典型特征。</span><span class="sxs-lookup"><span data-stu-id="1540c-103">Business end users, developers, and business analysts use the BAM portal page when they need to present aggregated data, which are precalculated summaries of a data set that convey representative characteristics of that data set.</span></span> <span data-ttu-id="1540c-104">使用 BAM 门户的“聚合”页，可以用图表形式以及随附的数据透视表显示聚合数据。</span><span class="sxs-lookup"><span data-stu-id="1540c-104">The Aggregations page of the BAM portal allows you to display aggregated data in the form of a graphical chart and accompanying PivotTable report.</span></span>  
  
## <a name="the-aggregations-page"></a><span data-ttu-id="1540c-105">“聚合”页</span><span class="sxs-lookup"><span data-stu-id="1540c-105">The Aggregations page</span></span>  
 <span data-ttu-id="1540c-106">“聚合”页显示传达流程或整个业务的总体运行情况的活动的结果。</span><span class="sxs-lookup"><span data-stu-id="1540c-106">The Aggregations page displays the results of an activity that collectively convey the health of the process or of the overall business.</span></span> <span data-ttu-id="1540c-107">例如，用户可能希望查看一个简单的饼图，其中显示 1,000 张发票按所在的处理阶段进行细分的结果（400 张仍在“评估”，400 张被拒绝，100 张已付款，还有 100 张仍处于“资金调拨”阶段）。</span><span class="sxs-lookup"><span data-stu-id="1540c-107">For example, a user may want to see a simple pie chart that shows a breakdown of the 1,000 invoices received in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
### <a name="creating-alerts-for-aggregations"></a><span data-ttu-id="1540c-108">创建聚合警报</span><span class="sxs-lookup"><span data-stu-id="1540c-108">Creating alerts for aggregations</span></span>  
 <span data-ttu-id="1540c-109">可以将聚合作为创建警报的依据，例如，“当处于流程‘评估’阶段的发票超过 500 张时通知我”。</span><span class="sxs-lookup"><span data-stu-id="1540c-109">You can use aggregations as the basis for creating an alert ("Notify me if there are ever more than 500 invoices in the "evaluation" stage of the process).</span></span> <span data-ttu-id="1540c-110">为此，右键单击任何数据透视表单元格，然后选择**设置警报**，或者单击单元格并单击**设置警报**数据透视表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="1540c-110">To do this, you right-click any PivotTable cell and select **Set Alert**, or you click a cell and click the **Set Alert** button to the right of the PivotTable report.</span></span> <span data-ttu-id="1540c-111">有关创建警报的详细信息，请参阅[如何设置警报](../core/how-to-set-an-alert.md)。</span><span class="sxs-lookup"><span data-stu-id="1540c-111">For more information about creating an alert, see [How to Set an Alert](../core/how-to-set-an-alert.md).</span></span>  
  
### <a name="viewing-individual-results-of-aggregations"></a><span data-ttu-id="1540c-112">查看聚合的各个结果</span><span class="sxs-lookup"><span data-stu-id="1540c-112">Viewing individual results of aggregations</span></span>  
 <span data-ttu-id="1540c-113">还可以选择任意聚合数量（例如，仍在“评估”的 400 张发票），然后查看该聚合的各个结果。</span><span class="sxs-lookup"><span data-stu-id="1540c-113">You can also select any aggregate amount (for example, 400 invoices still in "evaluation") and see the individual results for the aggregation.</span></span> <span data-ttu-id="1540c-114">右键单击任何数据透视表单元格并选择访问各个结果**显示结果**。</span><span class="sxs-lookup"><span data-stu-id="1540c-114">You access the individual results by right-clicking any PivotTable cell and selecting **Show Results**.</span></span> <span data-ttu-id="1540c-115">执行此操作后，您将进入“活动搜索”页，系统会自动构建搜索，然后显示出结果（对于此示例，400 张发票中的每张发票都有一条记录）。</span><span class="sxs-lookup"><span data-stu-id="1540c-115">In response to this action, you are sent to the Activity Search page, the search itself is automatically constructed, and the results are displayed (in this example, one record for each of the 400 invoices).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1540c-116">某些 BAM 视图没有与之相关联的聚合，因此可能没有任何可访问的信息，这取决于视图的创建方式。</span><span class="sxs-lookup"><span data-stu-id="1540c-116">Some BAM views do not have aggregations associated with them, and so there may be no information to access depending on how the view was created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1540c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1540c-117">See Also</span></span>  
 <span data-ttu-id="1540c-118">[BAM 门户](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="1540c-118">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="1540c-119">[BAM 门户上的活动搜索页](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="1540c-119">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="1540c-120">警报管理器上 BAM 门户页</span><span class="sxs-lookup"><span data-stu-id="1540c-120">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)