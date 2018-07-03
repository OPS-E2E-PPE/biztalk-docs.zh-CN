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
ms.openlocfilehash: 6cfb7d2c50b011743f652fd261eed68e810db10f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981038"
---
# <a name="real-time-aggregations"></a>实时聚合
在某些情况下，多维聚合的特定切片对时间非常敏感，需要它们实时可用。 例如，您的企业出售的是容易腐烂的产品，因而您希望各个交货阶段的产品数量的聚合实时可用。 同时，您还需要在月底获得其他聚合，如典型客户的年龄，以便进行商业智能分析。  
  
 BAM 将实时聚合 (RTA) 实现为活动存储表中由触发器维护的表。 当您的企业处理采购订单 (PO) 时，RTA 视图可能类似下图中的示例。  
  
 ![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")  
BAM 实时聚合  
  
 在此图中，如果接收到来自 Redmond 的 $100 新采购订单，则 BAM 将执行 `Count=Count+1` 和 `Amount=Amount+$100` 操作，在相应行 {Redmond, InProcess} 的单元格中加入新项的值。  
  
 随后，如果该订单已发货，则 BAM 将从行 {Redmond, InProgress} 中减去此项的值，并将它添加到行 {Redmond, Shipped} 中。  
  
 BAM 在给定联机时段内维护 RTA 的数据，过后则删除这些数据。 可以通过更改相应的行的表的配置的联机时段**bam_Metadata_RealTimeAggregations**。  
  
 使用实时聚合还应注意以下问题：  
  
- 实时聚合会显著影响 BAM 写入数据的速度。 因而，应该只将最重要的聚合结构切片定义为 RTA。  
  
- 实时聚合的维度级别限制为 14。 例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。 对于进度维度，级别数为树的深度，而对于时间维度，级别数是所有子单位的数目。 例如，如果时间维度为年、月、日和小时，则计为四个级别。  
  
- BAM 不支持类型的实时聚合**最小**并**最大**。 BAM 支持聚合**计数**， **Sum**，并**平均**。  
  
- 必须始终为 RTA 创建时间维度，并且始终将它用于所有数据切片，这是因为 RTA 中的数据是基于服务器时间戳（而不是任何特定的业务里程碑）老化的。  
  
- 不要定义使用同一个 BAM 活动的多个 RTA。 否则，当您存档 BAM 数据时，RTA 数据将不正确。  
  
  实时聚合会显著影响 BAM 写入数据的速度。 因而，应该只将最重要的聚合结构切片定义为 RTA。  
  
  实时聚合的维度级别限制为 14。 例如，如果州和城市创建数据维度位置，则将计为两个级别 （状态和 City）。 对于进度维度，级别数为树的深度，而对于时间维度，级别数是所有子单位的数目。 例如，如果时间维度为年、月、日和小时，则计为四个级别。  
  
  BAM 不支持类型的实时聚合**最小**并**最大**。 BAM 支持聚合**计数**， **Sum**，并**平均**。  
  
  不要定义使用同一个 BAM 活动的多个 RTA。 否则，当您存档 BAM 数据时，RTA 数据将不正确。  
  
## <a name="see-also"></a>请参阅  
 [聚合概述](../core/what-is-an-aggregation.md)