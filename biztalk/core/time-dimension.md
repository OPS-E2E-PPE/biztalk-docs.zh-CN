---
title: 时间维度 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Time dimension [BAM]
- aggregations [BAM], Time dimension
ms.assetid: 8f83b758-09a1-4efb-ae0e-32753f56c4e4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ac4e3d64b2bfee949ca0adca06dc79c9b944192
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399471"
---
# <a name="time-dimension"></a><span data-ttu-id="bd071-102">时间维度</span><span class="sxs-lookup"><span data-stu-id="bd071-102">Time Dimension</span></span>
<span data-ttu-id="bd071-103">时间维度，您可以根据时间创建的聚合。</span><span class="sxs-lookup"><span data-stu-id="bd071-103">The time dimension allows aggregations to be created with respect to time.</span></span> <span data-ttu-id="bd071-104">例如时间维度可以用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="bd071-104">For example a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="bd071-105">Year</span><span class="sxs-lookup"><span data-stu-id="bd071-105">Year</span></span>|<span data-ttu-id="bd071-106">Month</span><span class="sxs-lookup"><span data-stu-id="bd071-106">Month</span></span>|<span data-ttu-id="bd071-107">Count</span><span class="sxs-lookup"><span data-stu-id="bd071-107">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="bd071-108">2003</span><span class="sxs-lookup"><span data-stu-id="bd071-108">2003</span></span>|<span data-ttu-id="bd071-109">January</span><span class="sxs-lookup"><span data-stu-id="bd071-109">January</span></span>|<span data-ttu-id="bd071-110">120</span><span class="sxs-lookup"><span data-stu-id="bd071-110">120</span></span>|  
||<span data-ttu-id="bd071-111">February</span><span class="sxs-lookup"><span data-stu-id="bd071-111">February</span></span>|<span data-ttu-id="bd071-112">230</span><span class="sxs-lookup"><span data-stu-id="bd071-112">230</span></span>|  
||<span data-ttu-id="bd071-113">March</span><span class="sxs-lookup"><span data-stu-id="bd071-113">March</span></span>|<span data-ttu-id="bd071-114">350</span><span class="sxs-lookup"><span data-stu-id="bd071-114">350</span></span>|  
||<span data-ttu-id="bd071-115">April</span><span class="sxs-lookup"><span data-stu-id="bd071-115">April</span></span>|<span data-ttu-id="bd071-116">280</span><span class="sxs-lookup"><span data-stu-id="bd071-116">280</span></span>|  
  
 <span data-ttu-id="bd071-117">可以与任何其他维度结合使用时间维度。</span><span class="sxs-lookup"><span data-stu-id="bd071-117">The time dimension can be combined with any other dimension.</span></span> <span data-ttu-id="bd071-118">例如，可以在行和列的数据维度使用时间维度创建以下表：</span><span class="sxs-lookup"><span data-stu-id="bd071-118">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|||<span data-ttu-id="bd071-119">网球拍</span><span class="sxs-lookup"><span data-stu-id="bd071-119">Tennis racquets</span></span>|<span data-ttu-id="bd071-120">足球</span><span class="sxs-lookup"><span data-stu-id="bd071-120">Soccer balls</span></span>|  
|------|------|---------------------|------------------|  
||<span data-ttu-id="bd071-121">January</span><span class="sxs-lookup"><span data-stu-id="bd071-121">January</span></span>|<span data-ttu-id="bd071-122">50</span><span class="sxs-lookup"><span data-stu-id="bd071-122">50</span></span>|<span data-ttu-id="bd071-123">70</span><span class="sxs-lookup"><span data-stu-id="bd071-123">70</span></span>|  
||<span data-ttu-id="bd071-124">February</span><span class="sxs-lookup"><span data-stu-id="bd071-124">February</span></span>|<span data-ttu-id="bd071-125">120</span><span class="sxs-lookup"><span data-stu-id="bd071-125">120</span></span>|<span data-ttu-id="bd071-126">110</span><span class="sxs-lookup"><span data-stu-id="bd071-126">110</span></span>|  
||<span data-ttu-id="bd071-127">March</span><span class="sxs-lookup"><span data-stu-id="bd071-127">March</span></span>|<span data-ttu-id="bd071-128">300</span><span class="sxs-lookup"><span data-stu-id="bd071-128">300</span></span>|<span data-ttu-id="bd071-129">50</span><span class="sxs-lookup"><span data-stu-id="bd071-129">50</span></span>|  
||<span data-ttu-id="bd071-130">April</span><span class="sxs-lookup"><span data-stu-id="bd071-130">April</span></span>|<span data-ttu-id="bd071-131">220</span><span class="sxs-lookup"><span data-stu-id="bd071-131">220</span></span>|<span data-ttu-id="bd071-132">60</span><span class="sxs-lookup"><span data-stu-id="bd071-132">60</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd071-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd071-133">See Also</span></span>  
 <span data-ttu-id="bd071-134">[数值范围维度](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="bd071-134">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 <span data-ttu-id="bd071-135">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="bd071-135">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="bd071-136">[数据维度](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="bd071-136">[Data Dimension](../core/data-dimension.md) </span></span>  
 [<span data-ttu-id="bd071-137">定义维度</span><span class="sxs-lookup"><span data-stu-id="bd071-137">Defining Dimensions</span></span>](../core/defining-dimensions.md)