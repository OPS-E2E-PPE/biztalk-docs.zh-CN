---
title: 定义实时聚合 |Microsoft Docs
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
ms.openlocfilehash: 4b585ba7f07ba6cd0f36a3fe2e68b92c50f4e206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389701"
---
# <a name="defining-real-time-aggregations"></a><span data-ttu-id="54a6f-102">定义实时聚合</span><span class="sxs-lookup"><span data-stu-id="54a6f-102">Defining Real-Time Aggregations</span></span>
<span data-ttu-id="54a6f-103">在某些情况下，多维聚合的特定切片是时间非常敏感，希望它们在真实时间中不可用。</span><span class="sxs-lookup"><span data-stu-id="54a6f-103">In some cases, specific slices of the multi-dimensional aggregations are so time- sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="54a6f-104">例如，你的业务销售腐烂的产品和所需的产品数量传递要在真实时间中可用的不同阶段中的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="54a6f-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="54a6f-105">同时，您希望其他聚合，如年龄的典型客户，但只会在商业智能分析的月结束。</span><span class="sxs-lookup"><span data-stu-id="54a6f-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
-   <span data-ttu-id="54a6f-106">使用**数据透视表**工具栏中，如果适用，将所选的数据透视表标记为实时聚合 (RTA)。</span><span class="sxs-lookup"><span data-stu-id="54a6f-106">Using the **PivotTable** toolbar, mark the selected PivotTable as a real-time aggregation (RTA), if applicable.</span></span> <span data-ttu-id="54a6f-107">在数据透视表中包含的数据类型应确定其是否需要实时查看。</span><span class="sxs-lookup"><span data-stu-id="54a6f-107">The type of data contained in the PivotTable should determine whether it needs to be viewed in real time.</span></span> <span data-ttu-id="54a6f-108">例如，跟踪每小时 Web 订单的报表可能需要实时查看，而不会实时查看跟踪每日销售总额的报告。</span><span class="sxs-lookup"><span data-stu-id="54a6f-108">For example, a report that tracks hourly Web orders might need to viewed in real time, whereas a report that tracks daily sales totals would not be viewed in real time.</span></span>  
  
     <span data-ttu-id="54a6f-109">![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")</span><span class="sxs-lookup"><span data-stu-id="54a6f-109">![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")</span></span>  
<span data-ttu-id="54a6f-110">RTA 按钮</span><span class="sxs-lookup"><span data-stu-id="54a6f-110">RTA button</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="54a6f-111">未定义使用同一个 BAM 活动的多个 Rta。</span><span class="sxs-lookup"><span data-stu-id="54a6f-111">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="54a6f-112">如果这样做，RTA 数据将不正确，当您存档 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="54a6f-112">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="54a6f-113">有关数据透视表的详细信息，请参阅 Excel 联机帮助。</span><span class="sxs-lookup"><span data-stu-id="54a6f-113">For more information about Pivot tables, see Excel online help.</span></span> <span data-ttu-id="54a6f-114">创建数据透视表后，可以查看实时 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="54a6f-114">After you create your Pivot table, you can view your live BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a6f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="54a6f-115">See Also</span></span>  
 <span data-ttu-id="54a6f-116">[查看实时 BAM 数据](../core/viewing-live-bam-data.md) </span><span class="sxs-lookup"><span data-stu-id="54a6f-116">[Viewing Live BAM Data](../core/viewing-live-bam-data.md) </span></span>  
 <span data-ttu-id="54a6f-117">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="54a6f-117">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="54a6f-118">[数据维度](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="54a6f-118">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="54a6f-119">[时间维度](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="54a6f-119">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="54a6f-120">[数值范围维度](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="54a6f-120">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="54a6f-121">定义维度</span><span class="sxs-lookup"><span data-stu-id="54a6f-121">Defining Dimensions</span></span>](../core/defining-dimensions.md)