---
title: 活动数据存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- databases [BAM], performance
- activities [BAM], peformance
- databases [BAM], partitioning
- BAM, performance
ms.assetid: 1f736599-3d16-496e-a459-8b0507d57fcb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0a4744f5022bfdc466460a25def23ea362d7b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361690"
---
# <a name="activity-data-storage"></a>活动数据存储
本主题介绍活动数据存储，随着时间推移，活动表中的增长和 BAM 如何解决了进行中的活动和已完成的活动的单独表的这些性能问题导致的性能问题。 本主题还介绍用于查询数据，以及如何使用更高的性能在 BAM 中的分区的联机时段。  
  
 活动数据存储的基本理念是具有一个单独的表的每个活动类型，在其中每个记录表示不同的活动实例 （例如，正在进行中或已完成）。  
  
 在此示例中，如果活动为采购订单表将所示，如下所示：  
  
|PO#|RecvTime|City|Quantity|ShipTime|DeliveryTime|  
|----------|--------------|----------|--------------|--------------|------------------|  
|123|上午 8:00|Seattle|150|8:24 am|12:45 pm|  
|124|上午 8:30|Seattle|234|8:45 am|下午 1:20|  
|125|上午 8:35|Redmond|87|9:05 am|下午 2:30|  
|126|8:45 am|Seattle|450|上午 9:20|3:10 pm|  
|127|8:55 am|Redmond|200|上午 9:30|\<NULL\>|  
|128|8:57 am|Seattle|340|上午 9:20|3:05 pm|  
|129|上午 9:12 点|Seattle|120|9:45 am|\<NULL\>|  
|130|上午 9:30|Redmond|25|上午 10:15|\<NULL\>|  
|131|9:45|Seattle|250|上午 10:35|\<NULL\>|  
|132|上午 10:00|Redmond|100|\<NULL\>|\<NULL\>|  
|133|上午 10:15|Seattle|230|\<NULL\>|\<NULL\>|  
|134|上午 10:25|Redmond|45|\<NULL\>|\<NULL\>|  
  
 在此表中，当 BAM 接收新的采购订单，它将插入新行，一些设置为非 null 值 （例如，RecvTime、 城市、 数量等） 的某些列。 更高版本，当您批准并发布此采购订单，BAM 会将 ShipTime 设置为非 null 值。 最后，当接收和确认货物时，BAM 会将 DeliveryTime 设置为非 null 值。  
  
 随着时间迅速下降的这个简单的实施性能。 在开始时，性能受 SQL server 可执行 (实质上是 CPU 绑定)、 事务数但在一些时间，急剧下降。 在同一时间，磁盘 IO 的平均队列长度增加到超出可接受的限制：  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig4.gif "ebiz_prog_bam_data_maint_fig4")  
BAM 写入性能与磁盘队列长度  
  
 这样做的原因是表的大小增长随着更多的业务流程实例完整。 例如，第一次，UPDATE 语句的存储的过程会导致搜索上的聚集索引的采购订单号和将在内存中的某些页读入。 因为采购订单流程的实例是独立 （某些需要较长的时间，但某些较短），存储过程的后续调用可能是一些其他采购订单实例，因此将需要不同的数据页在内存中读取。 只要采购订单记录的总数很小，SQL Server 将缓存在内存中的所有数据页。 当记录数增长到足够大时，缓存命中率将降低，并且每个操作需要读取物理磁盘。 显然，在这种情况下对表执行任何查询活动不是可能的。  
  
## <a name="bam-tables"></a>BAM 表  
 若要避免此问题，BAM 使用已完成与下图中的两个单独的表 – 一个用于仍在进行中，活动，另一个：  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig5.gif "ebiz_prog_bam_data_maint_fig5")  
BAM 表  
  
 在此图中，基本思想是使相对较小的表中发生更新的另一种不断增大，但可递增访问 (只使用 Insert)。 在示例中，仅在当前正在处理的订单将在活动表中，在已传递的所有订单将都进入已完成的表。  
  
 由于存在触发器，此表的结构比在开始时，单个表的 INSERT/UPDATE 慢，但会维护随着时间的推移稳定的写入性能。  
  
## <a name="online-window-for-activity-data"></a>活动数据的联机时段  
 活动存储主要处理对当前或最近完成的活动的查询。 BAM 存档，然后从 BAM 主导入数据库中清除非常旧的、 已完成的活动。 因此活动数据将流过 BAM 和在可配置的联机时段都可用于查询。  
  
## <a name="bam-partitioning"></a>BAM 分区  
 若要为提高性能并避免停机时间，活动存储使用分区时活动的完成基于时间戳。 BAM 通过与另一个空表的格式完全相同的已完成表定期交换来此实现。 BAM 完成此，一旦进一步已完成的活动进入新表中，而 BAM 将保留旧证书仅供查询，如图所示：  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig8.gif "ebiz_prog_bam_data_maint_fig8")  
BAM 分区交换  
  
 后一个分区完全联机时段之外，BAM 存档，然后删除它。 为了尽量减少用户这种复杂性，BAM 还维护分区的视图的窗体：  
  
```  
SELECT * FROM Active   
UNION ALL   
SELECT * FROM Completed   
UNION ALL  
  
```  
  
 BAM 会自动重新创建此视图每次创建或删除分区。  
  
 请注意以下关于 BAM 分区：  
  
-   已分区视图的名称是**bam_\<ActivityName\>_AllInstances**。 此视图不适用于直接查询，但对 BAM 规范进行故障排除时可能很有用。 您应查询每个类别创建在此视图顶部的业务用户的特定视图中的数据。 有关详细信息，请参阅[查询实例数据](../core/querying-instance-data.md)。  
  
-   通过修改的值设置联机时段**OnlineWindowTimeUnit**并**OnlineWindowLength**表中的当前活动的记录中**bam_Metadata_Activities**主导入数据库中。  
  
-   DTS 包， **BAM_DM_\<ActivityName\>**、 执行分区和存档/清除。 每次运行此包，它将截断其他分区并存档/删除联机时段之外的所有分区。  
  
-   如果没有配置存档数据库，然后 BAM 将删除旧的活动数据而不进行存档。  
  
## <a name="see-also"></a>请参阅  
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)