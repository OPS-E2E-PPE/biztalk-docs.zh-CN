---
title: BAM 门户上的聚合页面 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5b242091e72ec4bc0ae56fdf27be5228583b7b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360151"
---
# <a name="aggregations-on-the-bam-portal-page"></a><span data-ttu-id="36a97-102">BAM 门户上的聚合页</span><span class="sxs-lookup"><span data-stu-id="36a97-102">Aggregations on the BAM Portal Page</span></span>
<span data-ttu-id="36a97-103">业务最终用户、 开发人员和业务分析员使用 BAM 门户页时需要显示聚合的数据，这是传达该数据集的典型特征的预先计算的汇总的数据集。</span><span class="sxs-lookup"><span data-stu-id="36a97-103">Business end users, developers, and business analysts use the BAM portal page when they need to present aggregated data, which are precalculated summaries of a data set that convey representative characteristics of that data set.</span></span> <span data-ttu-id="36a97-104">BAM 门户的聚合页上，可在图形图表和随附的数据透视表的形式显示聚合的数据。</span><span class="sxs-lookup"><span data-stu-id="36a97-104">The Aggregations page of the BAM portal allows you to display aggregated data in the form of a graphical chart and accompanying PivotTable report.</span></span>  
  
## <a name="the-aggregations-page"></a><span data-ttu-id="36a97-105">聚合页</span><span class="sxs-lookup"><span data-stu-id="36a97-105">The Aggregations page</span></span>  
 <span data-ttu-id="36a97-106">聚合页显示传达的运行状况的过程或整个业务的活动的结果。</span><span class="sxs-lookup"><span data-stu-id="36a97-106">The Aggregations page displays the results of an activity that collectively convey the health of the process or of the overall business.</span></span> <span data-ttu-id="36a97-107">例如，用户可能想要查看简单的饼图，显示 1,000 张发票按所处的阶段的处理已达到通过每个发票 （400 张仍在"评估"，400 个已拒绝，100 付款，还有 100 仍处于"资金调拨"中） 的细分。</span><span class="sxs-lookup"><span data-stu-id="36a97-107">For example, a user may want to see a simple pie chart that shows a breakdown of the 1,000 invoices received in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
### <a name="creating-alerts-for-aggregations"></a><span data-ttu-id="36a97-108">创建聚合警报</span><span class="sxs-lookup"><span data-stu-id="36a97-108">Creating alerts for aggregations</span></span>  
 <span data-ttu-id="36a97-109">创建警报时通知我"如果"评估"阶段的过程中有超过 500 发票） 可作为基础用于聚合。</span><span class="sxs-lookup"><span data-stu-id="36a97-109">You can use aggregations as the basis for creating an alert ("Notify me if there are ever more than 500 invoices in the "evaluation" stage of the process).</span></span> <span data-ttu-id="36a97-110">若要执行此操作，请右键单击任何数据透视表单元，并选择**设置警报**，或单击的单元格，然后单击**设置警报**按钮右侧的数据透视表报表。</span><span class="sxs-lookup"><span data-stu-id="36a97-110">To do this, you right-click any PivotTable cell and select **Set Alert**, or you click a cell and click the **Set Alert** button to the right of the PivotTable report.</span></span> <span data-ttu-id="36a97-111">有关创建警报的详细信息，请参阅[如何设置警报](../core/how-to-set-an-alert.md)。</span><span class="sxs-lookup"><span data-stu-id="36a97-111">For more information about creating an alert, see [How to Set an Alert](../core/how-to-set-an-alert.md).</span></span>  
  
### <a name="viewing-individual-results-of-aggregations"></a><span data-ttu-id="36a97-112">查看聚合的各个结果</span><span class="sxs-lookup"><span data-stu-id="36a97-112">Viewing individual results of aggregations</span></span>  
 <span data-ttu-id="36a97-113">您还可以选择任意聚合数量 （例如，400 张发票仍在"评估"），并查看聚合的各个结果。</span><span class="sxs-lookup"><span data-stu-id="36a97-113">You can also select any aggregate amount (for example, 400 invoices still in "evaluation") and see the individual results for the aggregation.</span></span> <span data-ttu-id="36a97-114">右键单击数据透视表的任何单元格并选择访问各个结果**显示结果**。</span><span class="sxs-lookup"><span data-stu-id="36a97-114">You access the individual results by right-clicking any PivotTable cell and selecting **Show Results**.</span></span> <span data-ttu-id="36a97-115">此操作的响应，发送到的活动搜索页、 自动构建搜索本身，和结果显示 （在此示例中，为每个 400 张发票的一条记录）。</span><span class="sxs-lookup"><span data-stu-id="36a97-115">In response to this action, you are sent to the Activity Search page, the search itself is automatically constructed, and the results are displayed (in this example, one record for each of the 400 invoices).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36a97-116">某些 BAM 视图没有与其相关联的聚合，因此可能没有要具体取决于如何创建视图访问信息。</span><span class="sxs-lookup"><span data-stu-id="36a97-116">Some BAM views do not have aggregations associated with them, and so there may be no information to access depending on how the view was created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a97-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="36a97-117">See Also</span></span>  
 <span data-ttu-id="36a97-118">[BAM 门户](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="36a97-118">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="36a97-119">[在 BAM 门户网站上的活动搜索页](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="36a97-119">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="36a97-120">“BAM 门户”页中的警报管理器</span><span class="sxs-lookup"><span data-stu-id="36a97-120">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)