---
title: BAM 门户中的聚合 |Microsoft 文档
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
ms.openlocfilehash: 43ef0adfacea0a29ea47584ed545884ffb8fa8bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230541"
---
# <a name="aggregations-in-the-bam-portal"></a>BAM 门户中的聚合
聚合是指预先计算的数据表，用于对 OLAP 多维数据集进行分析处理。 使用聚合可以更有效地查询多维数据库。 在使用用于 Excel 的 BAM 加载项创建和部署观察模型（业务数据的高级定义）时，所创建的聚合可以迅速对与关键性能指标 (KPI) 相关的数据集合进行计算。  
  
## <a name="types-of-aggregations"></a>聚合的类型  
 聚合可以是计划聚合，也可以是实时聚合。 计划聚合是 OLAP 多维数据集，表示指定时间业务数据的快照。 使用实时聚合可以获得基于您所指定的触发点的业务数据的视图，使 BAM 系统能够在达到某个 KPI 时立即通过警报通知您。  
  
## <a name="pivottable-view"></a>数据透视表视图  
 “数据透视表视图”区域显示您使用用于 Excel 的 BAM 加载项设计的数据透视表。 Office Web 组件允许您将操作数据透视表来呈现最符合你的需求的数据视图...  
  
> [!NOTE]
>  在查看数据透视表时，如果已经到达活动中的里程碑，而这些里程碑并未在进度维度中使用，则实时聚合 (RTA) 和预先计算的聚合（OLAP 实现）中的一些行可能包含空数据。 如果进度维度的上下文中使用了时间维度，而时间维度锚定到了“已确认”而不是“已收到”里程碑，则也可能会出现包含空数据的行。 在这种情况下，将接收到一个活动实例并触发“已收到”里程碑，但该活动尚未触发“已确认”里程碑，因此，时间维度行中将出现零。  为避免出现这种情况，请将时间维度链接到“已收到”里程碑。  
  
 ![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")  
  
 在 BAM 门户中使用 Office Web 组件修改数据透视表时，请谨记以下几点：  
  
-   Excel 中的数据透视表内包含一个“页”字段，您可以在其中输入时间切片维度。 BAM 门户使用 Office Web Components 不包括页字段。 如果 Excel 数据透视表使用“页”字段来表示维度，此字段的数据不显示在 BAM 门户的数据透视表中。  
  
-   Office Web 组件在 BAM 门户的内容框架中显示数据。 因为此框架的空间有限，从字段列表向列区域添加维度时，会造成在显示的数据透视表中看不到部分或全部维度名。  
  
 有关数据透视表的详细信息，请参阅"数据透视表术语解释"网址[http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416)。  
  
## <a name="chart-view"></a>图表视图  
 “图表视图”区域以图形形式显示聚合。 使用 Office Web 组件，可以通过图表视图处理聚合的详细信息，根据需要调整报告的数据。 在拖放“图表字段”列表中的数据项调整聚合时，该聚合的数据透视表将自动更新，反映您所做的更改。 您可以细查数据透视表以在新聚合视图上创建警报。  
  
 ![](../core/media/aggregationchartview.gif "AggregationChartView")  
  
## <a name="more"></a>更多信息  
  
-   [如何设置警报](../core/how-to-set-an-alert.md)  
  
-   [如何查看活动搜索的结果](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [如何修改聚合](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a>另请参阅  
 [聚合是什么？](../core/what-is-an-aggregation.md)