---
title: 数据维度 |Microsoft 文档
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
ms.openlocfilehash: b7138cf31a9cb86a9ba949142129ac5c906754b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238349"
---
# <a name="data-dimension"></a>数据维度
定义数据维度后，就可以将 BAM 活动中某些文本项的值用于行或列。 例如，使用名为“产品”的数据维度可以创建下表：  
  
|Product|Count|  
|-------------|-----------|  
|网球拍|100|  
|足球|200|  
  
 而且，在 BAM 视图向导中可以定义多个数据维度。 例如，定义一个名为的数据维度**位置**级别与**状态**和**城市**可以用于创建下表：  
  
|||||  
|-|-|-|-|  
||California||Washington|  
||Los Angeles|San Francisco|Seattle|  
|网球拍|50|20|30|  
|足球|130|50|20|  
  
 在此表格中，“产品”维度用作行，“位置”维度用作列。  
  
## <a name="see-also"></a>另请参阅  
 [时间维度](../core/time-dimension.md)   
 [进度维度](../core/progress-dimension.md)   
 [数值范围维度](../core/numeric-range-dimension.md)   
 [定义维度](../core/defining-dimensions.md)