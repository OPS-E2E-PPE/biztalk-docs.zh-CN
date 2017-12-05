---
title: "活动数据存储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- databases [BAM], performance
- activities [BAM], peformance
- databases [BAM], partitioning
- BAM, performance
ms.assetid: 1f736599-3d16-496e-a459-8b0507d57fcb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0139e76512eb9ca60089cb3c5f1e71b4f5524690
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="activity-data-storage"></a>活动数据存储
本主题介绍以下内容：关于活动数据存储的内容，由于活动表随着时间而不断增加所导致的性能问题，以及 BAM 如何通过对正进行的活动和已完成的活动使用不同的表来解决这些性能问题。 本主题还将介绍用于查询数据的联机时段，以及在 BAM 中如何使用分区来提高性能。  
  
 活动数据存储的基本思想是，每种活动类型都具有各自的表，在表中的每条记录都代表一个不同的活动实例（例如，正进行的活动或者已完成的活动）。  
  
 在下面的示例中，如果活动为采购订单，则表将如下所示：  
  
|PO#|RecvTime|City|数量|ShipTime|DeliveryTime|  
|----------|--------------|----------|--------------|--------------|------------------|  
|123|上午 8:00|Seattle|150|8:24 am|12:45pm|  
|124|上午 8:30|Seattle|234|8:45 am|下午 1:20|  
|125|上午 8:35|Redmond|87|上午 9:05|2:30 pm|  
|126|8:45 am|Seattle|450|上午 9:20|3:10 pm|  
|127|上午 8:55|Redmond|200|上午 9:30|\<NULL\>|  
|128|8:57 am|Seattle|340|上午 9:20|3:05 pm|  
|129|上午 9:12|Seattle|120|上午 9:45|\<NULL\>|  
|130|上午 9:30|Redmond|25|10:15 am|\<NULL\>|  
|131|9:45|Seattle|250|上午 10:35|\<NULL\>|  
|132|上午 10:00|Redmond|100|\<NULL\>|\<NULL\>|  
|133|10:15 am|Seattle|230|\<NULL\>|\<NULL\>|  
|134|上午 10:25|Redmond|45|\<NULL\>|\<NULL\>|  
  
 在此表中，当 BAM 接收到新采购订单时，它将插入一个新行，并且将某些列（例如，RecvTime、城市、数量等）设置为非空值。 随后，当审批此采购订单并发货时，BAM 会将 ShipTime 设置为非空值。 最后，当接收和确认货物时，BAM 会将 DeliveryTime 设置为非空值。  
  
 此采购订单的简单实现的性能将随着时间迅速下降。 在开始时，性能只受到 SQL Server 可执行的事务数的限制（实际上是 CPU 限制），但是一段时间后，其性能急剧下降。 同时，磁盘 IO 的平均队列长度将超过可接受的程度。  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig4.gif "ebiz_prog_bam_data_maint_fig4")  
BAM 写入性能与磁盘队列长度  
  
 出现此问题的原因在于，随着完成的业务流程实例的增多，表的大小也将不断增加。 例如，最初存储过程的 UPDATE 语句对采购订单号的聚集索引执行搜索，并将某些页读入内存。 由于采购订单流程的实例是相互独立的（有些实例需要很长时间，有些实例则需要较短时间），对存储过程的下一次调用可能是为某个其他采购订单实例调用的，因而需要将不同的数据页读入内存。 只要采购订单记录的总数足够小，SQL Server 就能够将所有数据页都缓存到内存中。 当记录数增长到足够大时，高速缓存命中率将降低，每个操作就都需要读取物理磁盘。 显然，在这种情况下，不可能对表执行任何查询活动。  
  
## <a name="bam-tables"></a>BAM 表  
 为了避免出现这种问题 ， BAM 使用了两个不同的表 – 一个表用于正在处理的活动 ， 一个表用于已完成的活动 ， 如下图所示 ：  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig5.gif "ebiz_prog_bam_data_maint_fig5")  
BAM 表  
  
 在此图中，基本思想是使进行更新的表相对较小，而另一个表可以不断增大，但可递增访问（只使用 INSERT）。 在本例中，只有当时正在处理的订单才位于活动表中，而已交付的所有订单都将进入已完成的表中。  
  
 由于存在触发器，使用这种结构的表在开始时要比单个表的 INSERT/UPDATE 慢，但是可一直维持稳定的写入性能。  
  
## <a name="online-window-for-activity-data"></a>活动数据的联机时段  
 活动存储主要处理对当前活动或最近完成的活动的查询。 BAM 对很久以前的、已完成的活动进行存档，然后将其从 BAM 主导入数据库中清除。 因而，活动数据将流过 BAM，并且在可配置的联机时段可对其进行查询。  
  
## <a name="bam-partitioning"></a>BAM 分区  
 为提高性能并避免故障，活动存储基于活动完成时的时间戳来使用分区。 BAM 通过将已完成的表与另一个相同格式的空表定期交换来实现此操作。 BAM 完成此操作后，新的已完成活动将进入新表，而 BAM 将保留旧表仅供查询，如下图所示：  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig8.gif "ebiz_prog_bam_data_maint_fig8")  
BAM 分区交换  
  
 当分区完全处于联机时段之外时，BAM 将对该分区进行存档，然后删除它。 为了从用户角度最大限度地降低这种复杂性，BAM 还维护一个以下形式的分区视图：  
  
```  
SELECT * FROM Active   
UNION ALL   
SELECT * FROM Completed   
UNION ALL  
  
```  
  
 BAM 每次创建或删除分区时都自动重新创建此视图。  
  
 关于 BAM 分区，请注意以下几点：  
  
-   分区视图的名称是**bam_\<ActivityName\>_AllInstances**。 此视图不适用于直接查询，但在对 BAM 规范进行疑难解答时可能非常有用。 查询数据时，应该从您在此视图顶部为业务用户的每个类别创建的特定视图中查询数据。 有关详细信息，请参阅[查询实例数据](../core/querying-instance-data.md)。  
  
-   通过修改的值设置联机窗口**OnlineWindowTimeUnit**和**OnlineWindowLength**表中的当前活动的记录中**bam_Metadata_Activities**主导入数据库中。  
  
-   DTS 包， **BAM_DM_\<ActivityName\>**、 执行分区和存档/清除。 每次此程序包运行时，它将截断其他分区，并对处于联机时段之外的所有分区进行存档/删除。  
  
-   如果没有配置存档数据库，则 BAM 将直接删除旧的活动数据而不进行存档。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)