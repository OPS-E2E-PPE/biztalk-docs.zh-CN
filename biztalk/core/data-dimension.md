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
# <a name="data-dimension"></a>数据维度
通过定义数据维度，BAM 活动用于行或列中的某些文本项的值。 例如名为产品的数据维度可用于创建下表：  
  
|产品|Count|  
|-------------|-----------|  
|网球拍|100|  
|足球|200|  
  
 此外，可以在 BAM 视图向导中定义多个数据维度。 例如，定义一个名为的数据维度**位置**与级别**状态**并**城市**可用于创建下表：  
  
|||||  
|-|-|-|-|  
||California||Washington|  
||Los Angeles|旧金山|Seattle|  
|网球拍|50|20|30|  
|足球|130|50|20|  
  
 在此表中，产品维度用作行和位置维度用作列。  
  
## <a name="see-also"></a>请参阅  
 [时间维度](../core/time-dimension.md)   
 [进度维度](../core/progress-dimension.md)   
 [数值范围维度](../core/numeric-range-dimension.md)   
 [定义维度](../core/defining-dimensions.md)