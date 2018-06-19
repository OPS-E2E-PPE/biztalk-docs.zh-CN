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
# <a name="numeric-range-dimension"></a>数值范围维度
使用数值范围维度，您可以根据给定数值范围的友好名称对聚合进行分类。 例如，业务分析员可以定义一个名为“采购订单大小”的数值范围维度，其中范围“小”表示采购订单金额在 0-$100 之间，范围“中”代表采购订单金额在 $100 到 $1,000 之间，范围“大”代表采购订单金额超过 $1,000。  
  
> [!NOTE]
>  如果某个采购订单金额不在定义的范围内，例如采购订单金额小于 0，则 BAM 将自动创建一个“超出范围”行来容纳超出范围的数据。  
  
> [!NOTE]
>  您不能创建引用同一数据别名的两个数值范围维度。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用数据透视表](../core/how-to-use-the-pivottable.md)   
 [进度维度](../core/progress-dimension.md)   
 [数据维度](../core/data-dimension.md)   
 [时间维度](../core/time-dimension.md)   
 [定义维度](../core/defining-dimensions.md)