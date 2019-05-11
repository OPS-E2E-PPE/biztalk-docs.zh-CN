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
# <a name="numeric-range-dimension"></a>数值范围维度
数值范围维度可以聚合进行分类基于的友好名称给定范围。 例如，业务分析员可以定义名 PO 大小与较小的范围为表示采购订单在 0-$100 之间，100 美元到 1,000 美元，或 Large 采购订单金额超过 1,000 美元的采购订单的介质的数值范围维度。  
  
> [!NOTE]
>  如果采购订单金额不在定义的范围内，例如，采购订单金额小于 0，然后一个"超出范围"行将会自动创建和 bam 来容纳超出范围的数据。  
  
> [!NOTE]
>  无法创建引用同一数据别名的两个数值范围维度。  
  
## <a name="see-also"></a>请参阅  
 [如何使用该数据透视表](../core/how-to-use-the-pivottable.md)   
 [进度维度](../core/progress-dimension.md)   
 [数据维度](../core/data-dimension.md)   
 [时间维度](../core/time-dimension.md)   
 [定义维度](../core/defining-dimensions.md)