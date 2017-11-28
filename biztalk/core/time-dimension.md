---
title: "时间维度 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Time dimension [BAM]
- aggregations [BAM], Time dimension
ms.assetid: 8f83b758-09a1-4efb-ae0e-32753f56c4e4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 418afdc5b7507aba9a564628341c10495b2a740a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="time-dimension"></a><span data-ttu-id="f87c7-102">时间维度</span><span class="sxs-lookup"><span data-stu-id="f87c7-102">Time Dimension</span></span>
<span data-ttu-id="f87c7-103">使用时间维度可以根据时间创建聚合。</span><span class="sxs-lookup"><span data-stu-id="f87c7-103">The time dimension allows aggregations to be created with respect to time.</span></span> <span data-ttu-id="f87c7-104">例如，使用时间维度可以创建下表：</span><span class="sxs-lookup"><span data-stu-id="f87c7-104">For example a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="f87c7-105">Year</span><span class="sxs-lookup"><span data-stu-id="f87c7-105">Year</span></span>|<span data-ttu-id="f87c7-106">Month</span><span class="sxs-lookup"><span data-stu-id="f87c7-106">Month</span></span>|<span data-ttu-id="f87c7-107">Count</span><span class="sxs-lookup"><span data-stu-id="f87c7-107">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="f87c7-108">2003</span><span class="sxs-lookup"><span data-stu-id="f87c7-108">2003</span></span>|<span data-ttu-id="f87c7-109">January</span><span class="sxs-lookup"><span data-stu-id="f87c7-109">January</span></span>|<span data-ttu-id="f87c7-110">120</span><span class="sxs-lookup"><span data-stu-id="f87c7-110">120</span></span>|  
||<span data-ttu-id="f87c7-111">February</span><span class="sxs-lookup"><span data-stu-id="f87c7-111">February</span></span>|<span data-ttu-id="f87c7-112">230</span><span class="sxs-lookup"><span data-stu-id="f87c7-112">230</span></span>|  
||<span data-ttu-id="f87c7-113">March</span><span class="sxs-lookup"><span data-stu-id="f87c7-113">March</span></span>|<span data-ttu-id="f87c7-114">350</span><span class="sxs-lookup"><span data-stu-id="f87c7-114">350</span></span>|  
||<span data-ttu-id="f87c7-115">April</span><span class="sxs-lookup"><span data-stu-id="f87c7-115">April</span></span>|<span data-ttu-id="f87c7-116">280</span><span class="sxs-lookup"><span data-stu-id="f87c7-116">280</span></span>|  
  
 <span data-ttu-id="f87c7-117">时间维度可以与任何其他维度结合使用。</span><span class="sxs-lookup"><span data-stu-id="f87c7-117">The time dimension can be combined with any other dimension.</span></span> <span data-ttu-id="f87c7-118">例如，您可以对行使用时间维度，对列使用数据维度，以创建下表：</span><span class="sxs-lookup"><span data-stu-id="f87c7-118">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|||<span data-ttu-id="f87c7-119">网球拍</span><span class="sxs-lookup"><span data-stu-id="f87c7-119">Tennis racquets</span></span>|<span data-ttu-id="f87c7-120">足球</span><span class="sxs-lookup"><span data-stu-id="f87c7-120">Soccer balls</span></span>|  
|------|------|---------------------|------------------|  
||<span data-ttu-id="f87c7-121">January</span><span class="sxs-lookup"><span data-stu-id="f87c7-121">January</span></span>|<span data-ttu-id="f87c7-122">50</span><span class="sxs-lookup"><span data-stu-id="f87c7-122">50</span></span>|<span data-ttu-id="f87c7-123">70</span><span class="sxs-lookup"><span data-stu-id="f87c7-123">70</span></span>|  
||<span data-ttu-id="f87c7-124">February</span><span class="sxs-lookup"><span data-stu-id="f87c7-124">February</span></span>|<span data-ttu-id="f87c7-125">120</span><span class="sxs-lookup"><span data-stu-id="f87c7-125">120</span></span>|<span data-ttu-id="f87c7-126">110</span><span class="sxs-lookup"><span data-stu-id="f87c7-126">110</span></span>|  
||<span data-ttu-id="f87c7-127">March</span><span class="sxs-lookup"><span data-stu-id="f87c7-127">March</span></span>|<span data-ttu-id="f87c7-128">300</span><span class="sxs-lookup"><span data-stu-id="f87c7-128">300</span></span>|<span data-ttu-id="f87c7-129">50</span><span class="sxs-lookup"><span data-stu-id="f87c7-129">50</span></span>|  
||<span data-ttu-id="f87c7-130">April</span><span class="sxs-lookup"><span data-stu-id="f87c7-130">April</span></span>|<span data-ttu-id="f87c7-131">220</span><span class="sxs-lookup"><span data-stu-id="f87c7-131">220</span></span>|<span data-ttu-id="f87c7-132">60</span><span class="sxs-lookup"><span data-stu-id="f87c7-132">60</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f87c7-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f87c7-133">See Also</span></span>  
 <span data-ttu-id="f87c7-134">[数值范围维度](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="f87c7-134">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 <span data-ttu-id="f87c7-135">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="f87c7-135">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="f87c7-136">[数据维度](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="f87c7-136">[Data Dimension](../core/data-dimension.md) </span></span>  
 [<span data-ttu-id="f87c7-137">定义维度</span><span class="sxs-lookup"><span data-stu-id="f87c7-137">Defining Dimensions</span></span>](../core/defining-dimensions.md)