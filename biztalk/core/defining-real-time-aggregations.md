---
title: 定义实时聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b585ba7f07ba6cd0f36a3fe2e68b92c50f4e206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389701"
---
# <a name="defining-real-time-aggregations"></a>定义实时聚合
在某些情况下，多维聚合的特定切片是时间非常敏感，希望它们在真实时间中不可用。 例如，你的业务销售腐烂的产品和所需的产品数量传递要在真实时间中可用的不同阶段中的聚合函数。 同时，您希望其他聚合，如年龄的典型客户，但只会在商业智能分析的月结束。  
  
-   使用**数据透视表**工具栏中，如果适用，将所选的数据透视表标记为实时聚合 (RTA)。 在数据透视表中包含的数据类型应确定其是否需要实时查看。 例如，跟踪每小时 Web 订单的报表可能需要实时查看，而不会实时查看跟踪每日销售总额的报告。  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
RTA 按钮  
  
> [!IMPORTANT]
>  未定义使用同一个 BAM 活动的多个 Rta。 如果这样做，RTA 数据将不正确，当您存档 BAM 数据。  
  
 有关数据透视表的详细信息，请参阅 Excel 联机帮助。 创建数据透视表后，可以查看实时 BAM 数据。  
  
## <a name="see-also"></a>请参阅  
 [查看实时 BAM 数据](../core/viewing-live-bam-data.md)   
 [进度维度](../core/progress-dimension.md)   
 [数据维度](../core/data-dimension.md)   
 [时间维度](../core/time-dimension.md)   
 [数值范围维度](../core/numeric-range-dimension.md)   
 [定义维度](../core/defining-dimensions.md)