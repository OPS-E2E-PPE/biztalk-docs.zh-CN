---
title: "实时查询聚合数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b71c3adbcbe5aaaea4d9fa4bf25b2aa4191c580
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="querying-real-time-aggregated-data"></a>查询实时的聚合的数据
实时聚合 (RTA) 数据可在主导入数据库中动态创建的 SQL 视图内进行查询。  
  
 此视图的名称是  
  
 **bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**  
  
 位置  
  
 **\<***ViewName*  **\>** 为 BAM 定义 XML 中的视图元素的名称属性即相同在相关的 Microsoft Excel 向导中输入视图名称。  
  
 **\<***RTAName*  **\>** 在 BAM 定义 XML 中，BAM 生成是唯一的 RealTimeAggregation 元素的名称属性基于的视图名称。  
  
 在查询实时聚合数据时，请一定要注意下列情况：  
  
-   必须对实时聚合进行配置，将聚合保留给定的时间（默认值为一天），而且要限制其大小，不能增长得太大。 旧的聚合应该从 OLAP 多维数据集中获得。  
  
-   任何针对 RTA 的查询都必须包括对处于 RTA 数据的联机时段内的时间维度所进行的筛选。 之所以必须这样做，是因为 BAM 基于 BAM 数据的时间戳执行 RTA 数据维护，并且 BAM 已优化为以块的形式删除数据。 因此，如果发出 Transact-SQL 命令“`select *`”，其结果变动很大，难以预测。  
  
-   如果活动数据通过 DirectEventStream 发送到 BAM，则实时聚合数据没有延迟，即这些数据在调用应用程序中的事务提交后立刻显示出来。  
  
-   如果活动数据通过 BufferedEventStream 发送到 BAM，则 RTA 数据将在查询几秒钟后显示，具体的时间取决于 BAM 事件总线服务的负载以及 BAM 主导入数据库的宿主 SQL 服务器。  
  
-   BAM 基于一个自己维护的、与使用触发器的活动数据存储记录中的更改和插入内容保持同步的表进行实时聚合。 有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。 因此，实时聚合可以对性能有很大的影响。 有关详细信息，请参阅[实时聚合](../core/real-time-aggregations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [查询计划的聚合数据](../core/querying-scheduled-aggregated-data.md)   
 [查询 BAM 数据](../core/querying-bam-data.md)