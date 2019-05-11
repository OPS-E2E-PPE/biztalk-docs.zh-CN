---
title: 计划聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- scheduling, aggregations [BAM]
- aggregations [BAM], scheduling
ms.assetid: 4e2da2eb-b1fc-4b27-98d6-564e6df719e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d7c272662dfdf7fdf9ee56744b202e54f445c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307921"
---
# <a name="scheduled-aggregations"></a>计划聚合
BAM 的计划的聚合基于动态生成的 OLAP 多维数据集和 Data Transformation Services (DTS) 包。 计划聚合中的数据表示对业务活动的快照时启动 DTS 包。 若要实现此目的，以进行分析的 DTS 包的第一步是对存储过程的调用**bam_Metadata_BeginAnalysis** ，将检索快照组成：  
  
- 正在进行中的所有活动实例的快照复制  
  
- 从那一刻起，运行 DTS 包是最后一次到快照的时间点表示已完成的活动实例的增量时段视图  
  
  BAM 来实现此通过将活动存储区以很短的时间，从而防止在同一时间写入任何数据上的排他锁。 BAM 获取快照后, DTS 包可能需要很长时间才能运行，但 BAM 会忽略到达在处理过程的任何新数据。 下图说明了此活动：  
  
  ![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")  
  BAM 计划聚合  
  
  在图中，BAM 将有关已完成的活动实例的数据移到已完成实例 OLAP 多维数据集。 BAM 以增量方式处理此多维数据集。  
  
  同时，BAM 将移活动有关的数据仍在进行到活动实例多维数据集，它会完全处理 DTS 包。 这是可以接受的，因为 BAM 假定任一时刻相对较少的活动是正在进行中。  
  
  可从虚拟多维数据集，可以隐藏已完成和当前活动之间的区别是计划聚合的数据。 有关详细信息，请参阅[查询计划的聚合数据](../core/querying-scheduled-aggregated-data.md)。  
  
## <a name="see-also"></a>请参阅  
 [聚合概述](../core/what-is-an-aggregation.md)