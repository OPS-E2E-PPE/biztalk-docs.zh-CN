---
title: 数值范围维度 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], Numeric Range dimension
- Numeric Range dimension [BAM]
ms.assetid: a874ce44-b034-498f-ba58-114028dbef2c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fb6d4c21e0a207cfeec3e592569ca0f48f3badf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263397"
---
# <a name="numeric-range-dimension"></a><span data-ttu-id="ba08b-102">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="ba08b-102">Numeric Range Dimension</span></span>
<span data-ttu-id="ba08b-103">使用数值范围维度，您可以根据给定数值范围的友好名称对聚合进行分类。</span><span class="sxs-lookup"><span data-stu-id="ba08b-103">The numeric range dimension allows aggregations to be categorized based on friendly names of given ranges.</span></span> <span data-ttu-id="ba08b-104">例如，业务分析员可以定义一个名为“采购订单大小”的数值范围维度，其中范围“小”表示采购订单金额在 0-$100 之间，范围“中”代表采购订单金额在 $100 到 $1,000 之间，范围“大”代表采购订单金额超过 $1,000。</span><span class="sxs-lookup"><span data-stu-id="ba08b-104">For example, a business analyst can define a numeric range dimension named PO Size with the ranges Small for purchase orders between 0-$100, Medium for purchase orders between $100 to $1,000, and Large for purchase orders exceeding $1,000.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba08b-105">如果某个采购订单金额不在定义的范围内，例如采购订单金额小于 0，则 BAM 将自动创建一个“超出范围”行来容纳超出范围的数据。</span><span class="sxs-lookup"><span data-stu-id="ba08b-105">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, and then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba08b-106">您不能创建引用同一数据别名的两个数值范围维度。</span><span class="sxs-lookup"><span data-stu-id="ba08b-106">You cannot create two numeric range dimensions that reference the same data alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba08b-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba08b-107">See Also</span></span>  
 <span data-ttu-id="ba08b-108">[如何使用数据透视表](../core/how-to-use-the-pivottable.md) </span><span class="sxs-lookup"><span data-stu-id="ba08b-108">[How to Use the PivotTable](../core/how-to-use-the-pivottable.md) </span></span>  
 <span data-ttu-id="ba08b-109">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="ba08b-109">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="ba08b-110">[数据维度](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="ba08b-110">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="ba08b-111">[时间维度](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="ba08b-111">[Time Dimension](../core/time-dimension.md) </span></span>  
 [<span data-ttu-id="ba08b-112">定义维度</span><span class="sxs-lookup"><span data-stu-id="ba08b-112">Defining Dimensions</span></span>](../core/defining-dimensions.md)