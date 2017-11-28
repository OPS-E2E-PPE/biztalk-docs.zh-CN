---
title: "数据维度 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data dimension [BAM]
- aggregations [BAM], data dimensions
ms.assetid: 07b5e56a-4fd5-4c88-a98a-758e514d0621
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7138cf31a9cb86a9ba949142129ac5c906754b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-dimension"></a><span data-ttu-id="bb8e9-102">数据维度</span><span class="sxs-lookup"><span data-stu-id="bb8e9-102">Data Dimension</span></span>
<span data-ttu-id="bb8e9-103">定义数据维度后，就可以将 BAM 活动中某些文本项的值用于行或列。</span><span class="sxs-lookup"><span data-stu-id="bb8e9-103">Defining a data dimension allows the value of some text items in the BAM activity to be used on rows or columns.</span></span> <span data-ttu-id="bb8e9-104">例如，使用名为“产品”的数据维度可以创建下表：</span><span class="sxs-lookup"><span data-stu-id="bb8e9-104">For example a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="bb8e9-105">Product</span><span class="sxs-lookup"><span data-stu-id="bb8e9-105">Product</span></span>|<span data-ttu-id="bb8e9-106">Count</span><span class="sxs-lookup"><span data-stu-id="bb8e9-106">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="bb8e9-107">网球拍</span><span class="sxs-lookup"><span data-stu-id="bb8e9-107">Tennis racquets</span></span>|<span data-ttu-id="bb8e9-108">100</span><span class="sxs-lookup"><span data-stu-id="bb8e9-108">100</span></span>|  
|<span data-ttu-id="bb8e9-109">足球</span><span class="sxs-lookup"><span data-stu-id="bb8e9-109">Soccer balls</span></span>|<span data-ttu-id="bb8e9-110">200</span><span class="sxs-lookup"><span data-stu-id="bb8e9-110">200</span></span>|  
  
 <span data-ttu-id="bb8e9-111">而且，在 BAM 视图向导中可以定义多个数据维度。</span><span class="sxs-lookup"><span data-stu-id="bb8e9-111">Also, more than one data dimension can be defined in the BAM view wizard.</span></span> <span data-ttu-id="bb8e9-112">例如，定义一个名为的数据维度**位置**级别与**状态**和**城市**可以用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="bb8e9-112">For example, defining a data dimension named **Location** with levels for **State** and **City** can be used to create the following table:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="bb8e9-113">California</span><span class="sxs-lookup"><span data-stu-id="bb8e9-113">California</span></span>||<span data-ttu-id="bb8e9-114">Washington</span><span class="sxs-lookup"><span data-stu-id="bb8e9-114">Washington</span></span>|  
||<span data-ttu-id="bb8e9-115">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="bb8e9-115">Los Angeles</span></span>|<span data-ttu-id="bb8e9-116">San Francisco</span><span class="sxs-lookup"><span data-stu-id="bb8e9-116">San Francisco</span></span>|<span data-ttu-id="bb8e9-117">Seattle</span><span class="sxs-lookup"><span data-stu-id="bb8e9-117">Seattle</span></span>|  
|<span data-ttu-id="bb8e9-118">网球拍</span><span class="sxs-lookup"><span data-stu-id="bb8e9-118">Tennis racquets</span></span>|<span data-ttu-id="bb8e9-119">50</span><span class="sxs-lookup"><span data-stu-id="bb8e9-119">50</span></span>|<span data-ttu-id="bb8e9-120">20</span><span class="sxs-lookup"><span data-stu-id="bb8e9-120">20</span></span>|<span data-ttu-id="bb8e9-121">30</span><span class="sxs-lookup"><span data-stu-id="bb8e9-121">30</span></span>|  
|<span data-ttu-id="bb8e9-122">足球</span><span class="sxs-lookup"><span data-stu-id="bb8e9-122">Soccer balls</span></span>|<span data-ttu-id="bb8e9-123">130</span><span class="sxs-lookup"><span data-stu-id="bb8e9-123">130</span></span>|<span data-ttu-id="bb8e9-124">50</span><span class="sxs-lookup"><span data-stu-id="bb8e9-124">50</span></span>|<span data-ttu-id="bb8e9-125">20</span><span class="sxs-lookup"><span data-stu-id="bb8e9-125">20</span></span>|  
  
 <span data-ttu-id="bb8e9-126">在此表格中，“产品”维度用作行，“位置”维度用作列。</span><span class="sxs-lookup"><span data-stu-id="bb8e9-126">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8e9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb8e9-127">See Also</span></span>  
 <span data-ttu-id="bb8e9-128">[时间维度](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="bb8e9-128">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="bb8e9-129">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="bb8e9-129">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="bb8e9-130">[数值范围维度](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="bb8e9-130">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="bb8e9-131">定义维度</span><span class="sxs-lookup"><span data-stu-id="bb8e9-131">Defining Dimensions</span></span>](../core/defining-dimensions.md)