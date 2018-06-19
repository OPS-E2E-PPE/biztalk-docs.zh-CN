---
title: 计划聚合 |Microsoft 文档
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
ms.openlocfilehash: 0cf2558b046d53deb6036553c5206beebd4d80ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269085"
---
# <a name="scheduled-aggregations"></a>计划聚合
BAM 的计划聚合基于动态生成的 OLAP 多维数据集和数据转换服务 (DTS) 包。 计划聚合中的数据是启动 DTS 包时对业务活动的快照。 若要实现此目的，分析 DTS 包的第一步是对存储过程的调用**bam_Metadata_BeginAnalysis** ，将检索快照组成：  
  
-   正在处理的所有活动实例的快照副本  
  
-   已完成活动实例自最近一次运行 DTS 包至生成快照时的增量时段视图  
  
 BAM 在执行过程中会对活动存储区以独占方式锁定很短的一段时间，以防止在此期间写入任何数据。 BAM 获取快照后，DTS 包可能会运行很长时间，在此处理过程中，BAM 会忽略到达的任何新数据。 下图说明了此活动：  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")  
BAM 计划聚合  
  
 在图中，BAM 将有关已完成活动实例的数据移到已完成实例 OLAP 多维数据集。 BAM 以增量方式处理此多维数据集。  
  
 同时，BAM 将有关仍在处理的活动的数据移到活动实例多维数据集，DTS 包会将其处理完毕。 这是可以接受的，因为 BAM 假定任一时刻只有数量相对较少的活动在处理中。  
  
 计划聚合的数据可从虚拟多维数据集获取，此虚拟多维数据集隐藏了已完成活动和当前活动的差异。 有关详细信息，请参阅[查询计划的聚合数据](../core/querying-scheduled-aggregated-data.md)。  
  
## <a name="see-also"></a>另请参阅  
 [聚合是什么？](../core/what-is-an-aggregation.md)