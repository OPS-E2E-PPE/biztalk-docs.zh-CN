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
# <a name="time-dimension"></a>时间维度
使用时间维度可以根据时间创建聚合。 例如，使用时间维度可以创建下表：  
  
|Year|Month|Count|  
|----------|-----------|-----------|  
|2003|January|120|  
||February|230|  
||March|350|  
||April|280|  
  
 时间维度可以与任何其他维度结合使用。 例如，您可以对行使用时间维度，对列使用数据维度，以创建下表：  
  
|||网球拍|足球|  
|------|------|---------------------|------------------|  
||January|50|70|  
||February|120|110|  
||March|300|50|  
||April|220|60|  
  
## <a name="see-also"></a>另请参阅  
 [数值范围维度](../core/numeric-range-dimension.md)   
 [进度维度](../core/progress-dimension.md)   
 [数据维度](../core/data-dimension.md)   
 [定义维度](../core/defining-dimensions.md)