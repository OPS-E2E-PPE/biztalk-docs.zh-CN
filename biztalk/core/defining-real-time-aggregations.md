---
title: 定义实时聚合 |Microsoft 文档
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
ms.openlocfilehash: b2b2df32149f67a002a5a6281b6f1abd848523a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238677"
---
# <a name="defining-real-time-aggregations"></a>定义实时聚合
在某些情况下，特定的多维聚合切片都因此时效性你希望它们在实时中不可用。 例如，您的企业出售的是容易腐烂的产品，因而您希望各个交货阶段的产品数量的聚合实时可用。 同时，您还需要在月底获得其他聚合，如典型客户的年龄，以便进行商业智能分析。  
  
-   使用**数据透视表**工具栏上，将所选数据透视表标记为实时聚合 (RTA)，如果适用。 数据透视表中包含的数据的类型决定了该透视表是否需要实时进行查看。 例如，跟踪每小时 Web 订单的报告可能需要实时查看，而跟踪每日销售总额的报告不需要实时查看。  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
RTA 按钮  
  
> [!IMPORTANT]
>  不要定义使用同一个 BAM 活动的多个 RTA。 否则，当您存档 BAM 数据时，RTA 数据将不正确。  
  
 有关透视表的详细信息，请参阅 Excel 的联机帮助。 创建透视表之后，可以查看实时的 BAM 数据。  
  
## <a name="see-also"></a>另请参阅  
 [查看实时 BAM 数据](../core/viewing-live-bam-data.md)   
 [进度维度](../core/progress-dimension.md)   
 [数据维度](../core/data-dimension.md)   
 [时间维度](../core/time-dimension.md)   
 [数值范围维度](../core/numeric-range-dimension.md)   
 [定义维度](../core/defining-dimensions.md)