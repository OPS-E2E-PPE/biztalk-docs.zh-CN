---
title: "查询计划的聚合数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, scheduled data
- queries [BAM], scheduled data
ms.assetid: fb785ec0-7862-4d83-bb6f-0ebd69a28ce6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aed1d63b1ebd1e54fd229236a94f3ac9a5f6837
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="querying-scheduled-aggregated-data"></a>查询计划的聚合数据
通过 BAM 分析数据库中动态创建的 OLAP 多维数据集可以对计划的聚合数据进行查询。  
  
 此多维数据集的名称与 BAM 定义 XML 中 View 元素的 Name 属性相同，这是在 Excel 向导中输入的视图名称。 BAM 刷新此多维数据集时运行数据转换服务 (DTS) 包 BAM_AN_\<*ViewName*\>，其中\< *ViewName* \>是视图的名称描述你在 Excel 向导中使用。  
  
 在查询计划的聚合数据时，请一定要注意下列情况：  
  
-   这是一个虚拟多维数据集，其中包含的业务快照恰好是在开始执行 DTS 包的时刻生成的。 此多维数据集包含已完成的活动的聚合以及仍在进行中的活动的聚合。 您可以使用进度维度对这些聚合相应地进行筛选或分组。  
  
-   如果要从不感兴趣的当前活动 （例如，如果在完成非常快） 可以查询相应的实际多维数据集\< *ViewName*\>#Completed。  
  
-   如果此外还有实时聚合，则可以安排 DTS 包，使用比为实时聚合设置的联机时段更高的频率刷新该多维数据集。 否则，就会出现一个没有聚合的时间段。  
  
## <a name="see-also"></a>另请参阅  
 [查询 BAM 数据](../core/querying-bam-data.md)