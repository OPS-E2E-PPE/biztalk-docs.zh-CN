---
title: BAM 门户中的活动搜索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- queries [BAM], field descriptions
- Query Builder [BAM portal], creating queries
- queries [BAM], activity searches
- Query Builder [BAM portal], about Query Builder
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal]
- Query Builder [BAM portal], field descriptions
- BAM portal, Query Builder
- BAM portal, activity searches
ms.assetid: 60ab8deb-ebe2-4959-97fd-261ff64d500c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b97f9577d43552ad51766ccc4178bb2d73fb7107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361589"
---
# <a name="activity-searches-in-the-bam-portal"></a>BAM 门户中的活动搜索
活动搜索，可对 BAM 数据，以查找对其基于您指定基于跟踪的值和项可在 BAM 视图中，并显示这些活动，以便可以对其进行编辑或创建警报的条件匹配的活动执行搜索。  
  
## <a name="parts-of-the-query-builder"></a>查询生成器的各个部分  
 通过选择将对其创建布尔比较中提取感兴趣的数据的业务数据的项，可以为活动搜索生成查询。 首先选择中的 BAM 视图**我的视图**门户的框架。 从所选视图中选择要生成查询的活动。  
  
 ![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")  
  
 当已选择活动时，在门户内容框架将显示查询生成器、 列选择器和结果框。 您可以打开现有查询，也可以生成一个新。  
  
 ![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")  
  
 若要生成一个新的查询首先选择一个业务数据项**业务数据**下拉列表。  
  
 ![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")  
  
 接下来，在运算符下拉列表中选择比较运算符。 比较运算符可以优化查询的结果。  
  
 ![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")  
  
 值下拉列表是上下文相关基于业务数据项表示的数据类型。 用户界面 (UI) 更改为允许的数据更改的类型。  
  
 可以将联接的查询的子句和 OR 运算符，以形成更复杂的查询，通过单击**添加**按钮。  
  
 ![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")  
  
> [!NOTE]
>  不能对子句进行分组。 查询是通过联接多个子句的简单字符串和/或运算符。  
  
 下表描述的日期和时间字段。  
  
|运算符|Description|  
|--------------|-----------------|  
|**At**|指定完全匹配。 等效于布尔等于 （=） 操作。 **注意：** 如果选择**在**运算符指定该门户会使用午夜作为默认值没有时间部分的日期。 如果这不是你的意图，使用**该位置或之前**或**符号处或紧**运算符以获取所需的结果。|  
|**晚于**|指定匹配的事务或早于指定日期。 等效于布尔值小于或等于 （≤） 运算。|  
|**等于或晚于**|指定匹配的唯一事务或晚于指定日期。 等效于布尔值大于或等于 （≥） 运算。|  
|**早于**|指定匹配的只是早于指定日期的事务。 等效于布尔值小于 (<) 操作。|  
|**After**|指定匹配晚于指定日期的唯一事务。 等效于布尔大于 (>) 运算。|  
|**在过去**|指定匹配的唯一发生的事务。 在以前指定的期限。 可以以秒、 分钟、 小时或天指定时间段。|  
|**早于最后**|指定匹配在指定的时间段之前发生的事务。 可以以秒、 分钟、 小时或天指定时间段。|  
|**为空**|指定返回的唯一事务为其业务数据项不包含数据 （数据字段的值为 NULL）。|  
|**不为空**|指定返回业务数据项包含的数据 （数据字段的值不为 NULL） 的事务。|  
  
 下表描述了数值的字段和持续时间字段。 数值字段包含如数量或货币金额的数据。 持续时间字段指定的时间段。  
  
|运算符|Description|  
|--------------|-----------------|  
|**等于**|指定完全匹配。 等效于布尔等于 （=） 操作。|  
|**大于**|指定完全匹配。 等效于布尔大于 (>) 操作。|  
|**大于或等于**|指定完全匹配。 等效于布尔值大于或等于 （≥） 操作。|  
|**小于**|指定完全匹配。 等效于布尔小于 (<) 操作。|  
|**小于或等于**|指定完全匹配。 等效于小于于或等于 （≤） 运算。|  
|**不等于**|指定完全匹配。 等效于不等于 （≠） 操作。|  
|**为空**|指定返回的唯一事务为其业务数据项不包含数据 （数据字段的值为 NULL）。|  
|**不为空**|指定返回业务数据项包含的数据 （数据字段的值不为 NULL） 的事务。|  
  
 下表描述的文本字段。  
  
|运算符|Description|  
|--------------|-----------------|  
|**正是**|指定完全匹配。 等效于布尔等于 （=） 操作。|  
|**包含**|指定业务数据项中的文本包含指定的值。 这允许您执行部分匹配的数据。|  
|**不包含**|指定业务数据项中的文本不包含指定的值。|  
|**为空**|指定返回的唯一事务为其业务数据项不包含数据 （数据字段的值为 NULL）。|  
|**不为空**|指定返回业务数据项包含的数据 （数据字段的值不为 NULL） 的事务。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何在活动搜索中创建查询](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [如何设置警报](../core/how-to-set-an-alert.md)  
  
-   [如何查看活动搜索的结果](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a>请参阅  
 [BAM 门户](../core/bam-portal.md)