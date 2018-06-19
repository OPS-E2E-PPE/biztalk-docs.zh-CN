---
title: 定义实时聚合 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b2df32149f67a002a5a6281b6f1abd848523a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238677"
---
# <a name="defining-real-time-aggregations"></a><span data-ttu-id="b6af4-102">定义实时聚合</span><span class="sxs-lookup"><span data-stu-id="b6af4-102">Defining Real-Time Aggregations</span></span>
<span data-ttu-id="b6af4-103">在某些情况下，特定的多维聚合切片都因此时效性你希望它们在实时中不可用。</span><span class="sxs-lookup"><span data-stu-id="b6af4-103">In some cases, specific slices of the multi-dimensional aggregations are so time- sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="b6af4-104">例如，您的企业出售的是容易腐烂的产品，因而您希望各个交货阶段的产品数量的聚合实时可用。</span><span class="sxs-lookup"><span data-stu-id="b6af4-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="b6af4-105">同时，您还需要在月底获得其他聚合，如典型客户的年龄，以便进行商业智能分析。</span><span class="sxs-lookup"><span data-stu-id="b6af4-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
-   <span data-ttu-id="b6af4-106">使用**数据透视表**工具栏上，将所选数据透视表标记为实时聚合 (RTA)，如果适用。</span><span class="sxs-lookup"><span data-stu-id="b6af4-106">Using the **PivotTable** toolbar, mark the selected PivotTable as a real-time aggregation (RTA), if applicable.</span></span> <span data-ttu-id="b6af4-107">数据透视表中包含的数据的类型决定了该透视表是否需要实时进行查看。</span><span class="sxs-lookup"><span data-stu-id="b6af4-107">The type of data contained in the PivotTable should determine whether it needs to be viewed in real time.</span></span> <span data-ttu-id="b6af4-108">例如，跟踪每小时 Web 订单的报告可能需要实时查看，而跟踪每日销售总额的报告不需要实时查看。</span><span class="sxs-lookup"><span data-stu-id="b6af4-108">For example, a report that tracks hourly Web orders might need to viewed in real time, whereas a report that tracks daily sales totals would not be viewed in real time.</span></span>  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
<span data-ttu-id="b6af4-109">RTA 按钮</span><span class="sxs-lookup"><span data-stu-id="b6af4-109">RTA button</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b6af4-110">不要定义使用同一个 BAM 活动的多个 RTA。</span><span class="sxs-lookup"><span data-stu-id="b6af4-110">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="b6af4-111">否则，当您存档 BAM 数据时，RTA 数据将不正确。</span><span class="sxs-lookup"><span data-stu-id="b6af4-111">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="b6af4-112">有关透视表的详细信息，请参阅 Excel 的联机帮助。</span><span class="sxs-lookup"><span data-stu-id="b6af4-112">For more information about Pivot tables, see Excel online help.</span></span> <span data-ttu-id="b6af4-113">创建透视表之后，可以查看实时的 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="b6af4-113">After you create your Pivot table, you can view your live BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6af4-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6af4-114">See Also</span></span>  
 <span data-ttu-id="b6af4-115">[查看实时 BAM 数据](../core/viewing-live-bam-data.md) </span><span class="sxs-lookup"><span data-stu-id="b6af4-115">[Viewing Live BAM Data](../core/viewing-live-bam-data.md) </span></span>  
 <span data-ttu-id="b6af4-116">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="b6af4-116">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="b6af4-117">[数据维度](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="b6af4-117">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="b6af4-118">[时间维度](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="b6af4-118">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="b6af4-119">[数值范围维度](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="b6af4-119">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="b6af4-120">定义维度</span><span class="sxs-lookup"><span data-stu-id="b6af4-120">Defining Dimensions</span></span>](../core/defining-dimensions.md)