---
title: 查询实时聚合数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72ee6612fc99d9411f0fb26c91c5d8ad6041edf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398294"
---
# <a name="querying-real-time-aggregated-data"></a>查询实时聚合的数据
实时聚合 (RTA) 数据是可在 BAM 主导入数据库中动态创建的 SQL 视图中进行查询。  
  
 此视图的名称是  
  
 **bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**  
  
 位置  
  
 **\<** *ViewName* **\>** 是 BAM 定义 XML 中 View 元素的 Name 属性即相同相关的 Microsoft Excel 向导中输入视图名称。  
  
 **\<** *RTAName* **\>** BAM 生成唯一 BAM 定义 XML 中 RealTimeAggregation 元素的 Name 属性基于视图名称。  
  
 请务必查询实时聚合的数据时，请注意以下条件：  
  
-   若要将聚合保留给定的时间 （默认值为一天） 内，并且永远不会变得很大，则必须配置实时聚合。 而是应在 OLAP 多维数据集中提供旧的聚合。  
  
-   任何针对 RTA 的查询必须包括筛选将为 RTA 数据的联机时段内的时间维度。 这是必需的因为 BAM 执行数据维护 rta 基于 BAM 数据，以及上的时间戳经过优化，可在区块中放置数据。 因此如果您只需发送 TRANSACT-SQL 命令"`select *`"，其结果变动不可预见。  
  
-   如果活动数据发送到 BAM 通过 DirectEventStream，实时聚合的数据没有延迟 – 调用应用程序中的事务提交后立刻显示。  
  
-   如果活动数据发送到 BAM 通过 BufferedEventStream，RTA 数据将显示查询几秒钟后，具体取决于 BAM 事件总线服务和承载 BAM 主导入数据库的 SQL server 的负载。  
  
-   BAM 基于它所维护与更改和活动数据存储记录使用触发器中的插入内容同步的表进行实时聚合。 有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。 因此，实时聚合可以产生显著的性能影响。 有关详细信息，请参阅[实时聚合](../core/real-time-aggregations.md)。  
  
## <a name="see-also"></a>请参阅  
 [查询计划的聚合数据](../core/querying-scheduled-aggregated-data.md)   
 [查询 BAM 数据](../core/querying-bam-data.md)