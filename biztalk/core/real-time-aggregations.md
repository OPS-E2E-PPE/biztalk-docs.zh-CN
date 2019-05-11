---
title: 实时聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- aggregations [BAM], real-time data
ms.assetid: 0ef44641-e067-4108-b318-f4373ca8fa8f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d76a61fef1f25933e4ac35071e5890ab16606768
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398277"
---
# <a name="real-time-aggregations"></a>实时聚合
在某些情况下，多维聚合的特定切片是时间非常敏感，希望它们在真实时间中不可用。 例如，你的业务销售腐烂的产品和所需的产品数量传递要在真实时间中可用的不同阶段中的聚合函数。 同时，您希望其他聚合，如年龄的典型客户，但只会在商业智能分析的月结束。  
  
 BAM 为活动存储表中由触发器维护的表实现实时聚合 (RTA)。 在这种情况时你的业务处理采购订单 (PO) 时，RTA 视图可能类似下图中的示例。  
  
 ![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")  
BAM 实时聚合  
  
 在此图中，如果收到来自 Redmond 的新采购订单，则 BAM 将对应行中单元格的供稿 {redmond，InProcess} 执行等操作`Count=Count+1`和`Amount=Amount+$100`。  
  
 更高版本，如果订单，然后 BAM 从行 {Redmond，InProcess} 中删除此发布内容并将其添加到行 {Redmond，Shipped}。  
  
 BAM 在给定的联机时段内 RTA 数据维护，然后删除它。 可以通过更改相应的行的表的配置的联机时段**bam_Metadata_RealTimeAggregations**。  
  
 以下语句也适用于实时聚合：  
  
- 实时聚合会显著影响 BAM 写入数据的速度。 因此，只应定义为 RTA 的最重要的聚合结构切片。  
  
- 实时聚合的维度级别限制为 14。 例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。 对于进度维度的级别数是树的深度，最好为时间维度的所有子单位计数。 例如，时间维度为年、 月、 日和小时，则计为四个级别。  
  
- BAM 不支持类型的实时聚合**最小**并**最大**。 BAM 支持聚合**计数**， **Sum**，并**平均**。  
  
- 必须始终为 RTA 创建时间维度，并始终使用其所有数据切片，因为 RTA 中的数据过期的基于服务器时间戳，而不依赖任何特定的业务里程碑。  
  
- 未定义使用同一个 BAM 活动的多个 Rta。 如果这样做，RTA 数据将不正确，当您存档 BAM 数据。  
  
  实时聚合会显著影响 BAM 写入数据的速度。 因此，只应定义为 RTA 的最重要的聚合结构切片。  
  
  实时聚合的维度级别限制为 14。 例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。 对于进度维度的级别数是树的深度，最好为时间维度的所有子单位计数。 例如，时间维度为年、 月、 日和小时，则计为四个级别。  
  
  BAM 不支持类型的实时聚合**最小**并**最大**。 BAM 支持聚合**计数**， **Sum**，并**平均**。  
  
  未定义使用同一个 BAM 活动的多个 Rta。 如果这样做，RTA 数据将不正确，当您存档 BAM 数据。  
  
## <a name="see-also"></a>请参阅  
 [聚合概述](../core/what-is-an-aggregation.md)