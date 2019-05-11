---
title: 数据维度 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data dimension [BAM]
- aggregations [BAM], data dimensions
ms.assetid: 07b5e56a-4fd5-4c88-a98a-758e514d0621
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 036491d9f0fdb946c748850b7c25c959854f2098
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353198"
---
# <a name="data-dimension"></a><span data-ttu-id="d3f70-102">数据维度</span><span class="sxs-lookup"><span data-stu-id="d3f70-102">Data Dimension</span></span>
<span data-ttu-id="d3f70-103">通过定义数据维度，BAM 活动用于行或列中的某些文本项的值。</span><span class="sxs-lookup"><span data-stu-id="d3f70-103">Defining a data dimension allows the value of some text items in the BAM activity to be used on rows or columns.</span></span> <span data-ttu-id="d3f70-104">例如名为产品的数据维度可用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="d3f70-104">For example a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="d3f70-105">产品</span><span class="sxs-lookup"><span data-stu-id="d3f70-105">Product</span></span>|<span data-ttu-id="d3f70-106">Count</span><span class="sxs-lookup"><span data-stu-id="d3f70-106">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="d3f70-107">网球拍</span><span class="sxs-lookup"><span data-stu-id="d3f70-107">Tennis racquets</span></span>|<span data-ttu-id="d3f70-108">100</span><span class="sxs-lookup"><span data-stu-id="d3f70-108">100</span></span>|  
|<span data-ttu-id="d3f70-109">足球</span><span class="sxs-lookup"><span data-stu-id="d3f70-109">Soccer balls</span></span>|<span data-ttu-id="d3f70-110">200</span><span class="sxs-lookup"><span data-stu-id="d3f70-110">200</span></span>|  
  
 <span data-ttu-id="d3f70-111">此外，可以在 BAM 视图向导中定义多个数据维度。</span><span class="sxs-lookup"><span data-stu-id="d3f70-111">Also, more than one data dimension can be defined in the BAM view wizard.</span></span> <span data-ttu-id="d3f70-112">例如，定义一个名为的数据维度**位置**与级别**状态**并**城市**可用于创建下表：</span><span class="sxs-lookup"><span data-stu-id="d3f70-112">For example, defining a data dimension named **Location** with levels for **State** and **City** can be used to create the following table:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="d3f70-113">California</span><span class="sxs-lookup"><span data-stu-id="d3f70-113">California</span></span>||<span data-ttu-id="d3f70-114">Washington</span><span class="sxs-lookup"><span data-stu-id="d3f70-114">Washington</span></span>|  
||<span data-ttu-id="d3f70-115">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="d3f70-115">Los Angeles</span></span>|<span data-ttu-id="d3f70-116">旧金山</span><span class="sxs-lookup"><span data-stu-id="d3f70-116">San Francisco</span></span>|<span data-ttu-id="d3f70-117">Seattle</span><span class="sxs-lookup"><span data-stu-id="d3f70-117">Seattle</span></span>|  
|<span data-ttu-id="d3f70-118">网球拍</span><span class="sxs-lookup"><span data-stu-id="d3f70-118">Tennis racquets</span></span>|<span data-ttu-id="d3f70-119">50</span><span class="sxs-lookup"><span data-stu-id="d3f70-119">50</span></span>|<span data-ttu-id="d3f70-120">20</span><span class="sxs-lookup"><span data-stu-id="d3f70-120">20</span></span>|<span data-ttu-id="d3f70-121">30</span><span class="sxs-lookup"><span data-stu-id="d3f70-121">30</span></span>|  
|<span data-ttu-id="d3f70-122">足球</span><span class="sxs-lookup"><span data-stu-id="d3f70-122">Soccer balls</span></span>|<span data-ttu-id="d3f70-123">130</span><span class="sxs-lookup"><span data-stu-id="d3f70-123">130</span></span>|<span data-ttu-id="d3f70-124">50</span><span class="sxs-lookup"><span data-stu-id="d3f70-124">50</span></span>|<span data-ttu-id="d3f70-125">20</span><span class="sxs-lookup"><span data-stu-id="d3f70-125">20</span></span>|  
  
 <span data-ttu-id="d3f70-126">在此表中，产品维度用作行和位置维度用作列。</span><span class="sxs-lookup"><span data-stu-id="d3f70-126">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f70-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3f70-127">See Also</span></span>  
 <span data-ttu-id="d3f70-128">[时间维度](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="d3f70-128">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="d3f70-129">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="d3f70-129">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="d3f70-130">[数值范围维度](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="d3f70-130">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="d3f70-131">定义维度</span><span class="sxs-lookup"><span data-stu-id="d3f70-131">Defining Dimensions</span></span>](../core/defining-dimensions.md)