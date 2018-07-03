---
title: 什么是度量值和维度？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6b12a4c-9be5-4cac-b5b9-ece376d28cb1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb494246741699dfdbdab704c8fca0a3c9d55301
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994342"
---
# <a name="what-are-measures-and-dimensions"></a><span data-ttu-id="4df4b-103">什么是度量值和维度？</span><span class="sxs-lookup"><span data-stu-id="4df4b-103">What Are Measures and Dimensions?</span></span>
<span data-ttu-id="4df4b-104">维度和度量值都是数据聚合的物理特征。</span><span class="sxs-lookup"><span data-stu-id="4df4b-104">Dimensions and measures are the physical aspects of data aggregation.</span></span> <span data-ttu-id="4df4b-105">本主题以 BAM 方案为上下文环境来说明什么是度量值和维度。</span><span class="sxs-lookup"><span data-stu-id="4df4b-105">This topic describes what measures and dimensions are, using a BAM scenario to provide context.</span></span>  
  
## <a name="measures"></a><span data-ttu-id="4df4b-106">度量值组</span><span class="sxs-lookup"><span data-stu-id="4df4b-106">Measures</span></span>  
 <span data-ttu-id="4df4b-107">假设您为订单管理流程定义了一个非常简单的、包含以下三项的 BAM 活动：</span><span class="sxs-lookup"><span data-stu-id="4df4b-107">Suppose that you define a BAM activity for an order management process in extremely simple terms consisting of three items:</span></span>  
  
1. <span data-ttu-id="4df4b-108">流程开始时间（实际发生的事件）</span><span class="sxs-lookup"><span data-stu-id="4df4b-108">Process start time (an event in the real world)</span></span>  
  
2. <span data-ttu-id="4df4b-109">流程结束时间（也是实际发生的事件）</span><span class="sxs-lookup"><span data-stu-id="4df4b-109">Process end time (also a real-world event)</span></span>  
  
3. <span data-ttu-id="4df4b-110">流程持续时间（#2 - #1 的计算结果）</span><span class="sxs-lookup"><span data-stu-id="4df4b-110">Process duration (a calculation of #2 - #1)</span></span>  
  
   <span data-ttu-id="4df4b-111">在此示例中，聚合数据的过程只是将聚合函数（如平均值、最小值、最大值等）应用到一系列个别的持续时间值（即每个订单的流程持续时间）。</span><span class="sxs-lookup"><span data-stu-id="4df4b-111">Aggregating data in this case is simply a matter of applying an aggregation function (for example, average, minimum, maximum, etc.) to a series of individual duration values (that is, the processing duration for each order).</span></span>  
  
   <span data-ttu-id="4df4b-112">概念“平均持续时间”是一个度量值，且为单个值。</span><span class="sxs-lookup"><span data-stu-id="4df4b-112">The concept of "average duration" is a measure, and it is a single value.</span></span> <span data-ttu-id="4df4b-113">此度量值本身可给出与流程管理相关的信息，因为它表明整个流程在时间/吞吐量方面是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="4df4b-113">By itself, this measure yields information relevant to process management in that it indicates whether or not the process overall is behaving (in terms of timliness/throughput) as expected.</span></span> <span data-ttu-id="4df4b-114">但是，在缺少其他数据（因为“平均持续时间”为单个值）的情况下，很难理解该度量值实际值的含义。例如，为何本周的平均持续时间有个峰值？</span><span class="sxs-lookup"><span data-stu-id="4df4b-114">However, in the absence of any other data (because "average duration" is a single value), understanding the meaning of the measure's actual value is harder For example, why did we have a spike in average duration this week?</span></span> <span data-ttu-id="4df4b-115">是由于特定的合作伙伴、计划或产品造成的吗？</span><span class="sxs-lookup"><span data-stu-id="4df4b-115">Was it due to a particular partner, program, product?</span></span>  
  
## <a name="dimensions"></a><span data-ttu-id="4df4b-116">维度</span><span class="sxs-lookup"><span data-stu-id="4df4b-116">Dimensions</span></span>  
 <span data-ttu-id="4df4b-117">维度是帮助度量值使用者理解度量值含义的上下文。</span><span class="sxs-lookup"><span data-stu-id="4df4b-117">Dimensions are the context that help the consumer of measures understand the meaning of those measures.</span></span>  
  
 <span data-ttu-id="4df4b-118">继续上面的示例，假设再将下面三个项添加到该订单管理流程的 BAM 活动中：</span><span class="sxs-lookup"><span data-stu-id="4df4b-118">Continuing the above example, suppose you add three additional items to the BAM activity for the order management process:</span></span>  
  
1. <span data-ttu-id="4df4b-119">贸易合作伙伴名称（发出订单的人）</span><span class="sxs-lookup"><span data-stu-id="4df4b-119">trading partner name (who sent the order)</span></span>  
  
2. <span data-ttu-id="4df4b-120">帐户经理名称（销售联系人）</span><span class="sxs-lookup"><span data-stu-id="4df4b-120">account manager name (who is the sales contact)</span></span>  
  
3. <span data-ttu-id="4df4b-121">销售区域</span><span class="sxs-lookup"><span data-stu-id="4df4b-121">sales region</span></span>  
  
   <span data-ttu-id="4df4b-122">由于活动现在包括三个可能的数据透视表（合作伙伴、帐户经理和区域），逐个聚合这些数据将会创建一个三维的多维数据集。</span><span class="sxs-lookup"><span data-stu-id="4df4b-122">Since the activity now includes three possible data pivots (partner, account manager, region), aggregating this data now literally results in the creation of a three-dimensional cube at run-time.</span></span>  
  
   <span data-ttu-id="4df4b-123">该 BAM 活动依然从第一个工作项开始，最后创建单个“平均持续时间”度量值。</span><span class="sxs-lookup"><span data-stu-id="4df4b-123">It still begins with the first item of work, resulting in the creation of a single "average duration" measure.</span></span> <span data-ttu-id="4df4b-124">在由另一个采购订单到达所启动的下一个工作项完成时，如果贸易合作伙伴、帐户经理及区域都与第一个工作项相同，则该 BAM 活动所执行的操作就是基于这两项重新计算“平均持续时间”度量值（即两个持续时间的平均值），得出一个“平均持续时间”度量值。</span><span class="sxs-lookup"><span data-stu-id="4df4b-124">When the next item of work (initiated by the arrival of another purchase order) completes, if trading partner, account manager, and region are all the same as they were for the first item of work, then all that happens is that the "average duration" measure is recalculated, based now on two items (for example, the average of the two durations), to achieve a single "average duration" measure value.</span></span>  
  
   <span data-ttu-id="4df4b-125">一旦进入该 BAM 活动的某个工作项的贸易合作伙伴、帐户经理或区域设置中，有任何一项与该活动到目前为止遇到的工作项的设置不同，就会创建一个新的“平均持续时间”度量值，并与第一个度量值分开维护。</span><span class="sxs-lookup"><span data-stu-id="4df4b-125">As soon as an item comes where any of trading partner, account manager, or region are different than the set encountered so far, a new "average duration" measure value is created and maintained separate from the first one.</span></span>  
  
   <span data-ttu-id="4df4b-126">例如，如果第三个工作项的贸易合作伙伴与前两个不同，则沿着贸易合作伙伴维度创建第二个“平均持续时间”度量值。</span><span class="sxs-lookup"><span data-stu-id="4df4b-126">For example, if the trading partner on the third item of work was different than the previous two, the result is creation of a second "average duration" measure value along the trading partner dimension.</span></span> <span data-ttu-id="4df4b-127">现在您可以按贸易合作伙伴维度来查看“平均持续时间”度量值，这样就可以发现像“来自合作伙伴 X 的订单的平均处理时间几乎是合作伙伴 Y 的两倍”这类信息。</span><span class="sxs-lookup"><span data-stu-id="4df4b-127">Now you can review "average duration" values along the trading partner dimension and see things like "it takes us almost twice as long on average to process the orders from TradingPartnerX as it does for TradingPartnerY."</span></span> <span data-ttu-id="4df4b-128">而且在查看时可将维度折叠，以便仍然能够查看独立于任何贸易合作伙伴或其他维度的流程的整个“平均持续时间”。</span><span class="sxs-lookup"><span data-stu-id="4df4b-128">And dimensions can be collapsed for viewing so that one can still see the overall "average duration" for the process independent of any trading partner or other dimension.</span></span>  
  
   <span data-ttu-id="4df4b-129">最终，如果贸易合作伙伴、帐户经理和区域都有且只有三个不同的值，则所有不同情况都出现后，就会产生一个数据的 Rubik's® 多维数据集，在该多维数据集中，用户可以查看独立维护的 27 个“平均持续时间”值中的每一个，而维度就是该多维数据集的三个边。</span><span class="sxs-lookup"><span data-stu-id="4df4b-129">Finally, if trading partner, account manager, and region each have three and only three distinct values, once all permutations have occurred, the result is a Rubik's® Cube of data, where users can view each of 27 independently maintained "average duration" values, and the dimensions are each of three edges on the cube.</span></span>  
  
   <span data-ttu-id="4df4b-130">有关维度和度量值的其他信息，请参阅 Excel 帮助中的“关于 PivotTable 和 PivotChart 报告中的 OLAP 源数据”。</span><span class="sxs-lookup"><span data-stu-id="4df4b-130">For additional information about dimensions and measures, see "About OLAP source data in PivotTable and PivotChart reports" in Excel Help.</span></span>