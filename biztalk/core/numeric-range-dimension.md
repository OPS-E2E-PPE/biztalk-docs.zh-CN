---
title: 数值范围维度 |Microsoft Docs
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
ms.openlocfilehash: 0cde21a4cf30dd6f46af226bf056aa0efc398ca5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263212"
---
# <a name="numeric-range-dimension"></a><span data-ttu-id="96600-102">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="96600-102">Numeric Range Dimension</span></span>
<span data-ttu-id="96600-103">数值范围维度可以聚合进行分类基于的友好名称给定范围。</span><span class="sxs-lookup"><span data-stu-id="96600-103">The numeric range dimension allows aggregations to be categorized based on friendly names of given ranges.</span></span> <span data-ttu-id="96600-104">例如，业务分析员可以定义名 PO 大小与较小的范围为表示采购订单在 0-$100 之间，100 美元到 1,000 美元，或 Large 采购订单金额超过 1,000 美元的采购订单的介质的数值范围维度。</span><span class="sxs-lookup"><span data-stu-id="96600-104">For example, a business analyst can define a numeric range dimension named PO Size with the ranges Small for purchase orders between 0-$100, Medium for purchase orders between $100 to $1,000, and Large for purchase orders exceeding $1,000.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96600-105">如果采购订单金额不在定义的范围内，例如，采购订单金额小于 0，然后一个"超出范围"行将会自动创建和 bam 来容纳超出范围的数据。</span><span class="sxs-lookup"><span data-stu-id="96600-105">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, and then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96600-106">无法创建引用同一数据别名的两个数值范围维度。</span><span class="sxs-lookup"><span data-stu-id="96600-106">You cannot create two numeric range dimensions that reference the same data alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96600-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="96600-107">See Also</span></span>  
 <span data-ttu-id="96600-108">[如何使用该数据透视表](../core/how-to-use-the-pivottable.md) </span><span class="sxs-lookup"><span data-stu-id="96600-108">[How to Use the PivotTable](../core/how-to-use-the-pivottable.md) </span></span>  
 <span data-ttu-id="96600-109">[进度维度](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="96600-109">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="96600-110">[数据维度](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="96600-110">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="96600-111">[时间维度](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="96600-111">[Time Dimension](../core/time-dimension.md) </span></span>  
 [<span data-ttu-id="96600-112">定义维度</span><span class="sxs-lookup"><span data-stu-id="96600-112">Defining Dimensions</span></span>](../core/defining-dimensions.md)