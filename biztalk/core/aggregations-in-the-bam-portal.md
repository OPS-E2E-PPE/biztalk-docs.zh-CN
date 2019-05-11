---
title: BAM 门户中的聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, pivot tables
- BAM, data analysis
- pivot tables [BAM portal]
- BAM portal, charts
- data, analysis [BAM]
- data, OLAP cubes
- aggregations [BAM], BAM portal
- charts, BAM portal
- BAM portal, aggregations
ms.assetid: 1c689563-714b-4573-9c18-a5b0efe97fb8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1055a76039420024a5cbfacf8e63094e00b1b8b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360239"
---
# <a name="aggregations-in-the-bam-portal"></a>BAM 门户中的聚合
聚合是预先计算好的数据可用于分析的 OLAP 多维数据集处理的表。 使用聚合可以更有效地查询多维数据库。 创建和部署观察模型 （您的业务数据的高级定义） 时使用 excel BAM 外接程序，您创建可用于快速评估您的关键绩效指标 (Kpi) 相关的数据的集合的聚合。  
  
## <a name="types-of-aggregations"></a>聚合类型  
 聚合可以实时或计划。 计划的聚合是 OLAP 多维数据集，它表示在指定的时间业务数据的快照。 使用实时聚合可以根据你指定的触发点使 BAM 系统能够通过警报通知你，一旦达到了 KPI 对业务数据的视图。  
  
## <a name="pivottable-view"></a>数据透视表视图  
 数据透视表视图区域显示您设计使用 Excel BAM 外接程序的数据透视表报表。 Office Web 组件使您可以操作数据透视表报表以显示最符合您需求的数据视图...  
  
> [!NOTE]
>  查看数据透视表报表时很可能某些行可能包含实时聚合 (Rta) 和预先计算的聚合 （OLAP 实现） 中的空数据，如果已达到活动中的里程碑，但不是使用正在进行中维度。 还有可能会遇到包含 null 数据行，如果时间维度的进度维度的上下文中使用和锚定到里程碑如"已确认"而不是"收到"。 活动实例在这种情况下收到并触发接收的里程碑，但该活动尚未触发确认里程碑和会在时间维度行中显示零。  若要避免这种情况下，链接到接收里程碑的时间维度。  
  
 ![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")  
  
 在 BAM 门户中使用 Office Web 组件修改数据透视表报表时，请记住以下几点：  
  
- 在 Excel 中的数据透视表报告包括时间切片维度的放置位置的页字段。 使用 BAM 门户的 Office Web 组件不包括页字段。 如果 Excel 数据透视表报表页字段用于任何维度，此字段的数据不是显示在 BAM 门户中的数据透视表报表中。  
  
- Office Web 组件在 BAM 门户内容框架中显示数据。 因为此框架的空间有限，从字段列表向列区域添加维度会造成数据透视表移出视图的维度名称部分或全部的显示。  
  
  有关数据透视表的详细信息，请参阅"数据透视表术语揭密"网址[ http://go.microsoft.com/fwlink/?LinkId=55416 ](http://go.microsoft.com/fwlink/?LinkId=55416)。  
  
## <a name="chart-view"></a>图表视图  
 图表视图区域以图形方式显示聚合。 Office Web 组件使您可以操作通过图表视图，以根据需要调整报告的数据聚合的详细信息。 当您通过拖放图表字段列表中的数据项调整聚合时，聚合的数据透视表报表自动更新以反映所做的更改。 您可以钻取数据透视表在新的聚合视图上创建警报。  
  
 ![](../core/media/aggregationchartview.gif "AggregationChartView")  
  
## <a name="more"></a>更多  
  
-   [如何设置警报](../core/how-to-set-an-alert.md)  
  
-   [如何查看活动搜索的结果](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [如何修改聚合](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a>请参阅  
 [聚合概述](../core/what-is-an-aggregation.md)