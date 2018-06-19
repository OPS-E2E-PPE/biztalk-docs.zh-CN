---
title: BAM 门户中的活动搜索 |Microsoft 文档
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
ms.openlocfilehash: 723848f61294cc710bd2292758383cf674093265
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966595"
---
# <a name="activity-searches-in-the-bam-portal"></a>BAM 门户中的活动搜索
您可以使用活动搜索对 BAM 数据进行搜索。搜索将基于 BAM 视图中可用的跟踪值和项，查找与指定的标准匹配的活动并显示活动，以便您可以编辑这些活动或基于它们创建警报。  
  
## <a name="parts-of-the-query-builder"></a>查询生成器的部分  
 您可以通过选择业务数据项来为活动搜索生成查询，选择的业务数据项就是所创建的用于提取目标数据的布尔比较所基于的业务数据项。 通过选择 BAM 视图从启动**我视图**门户的框架。 从所选视图中选择要针对其生成查询的活动。  
  
 ![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")  
  
 在选择活动后，门户的内容框架会显示查询生成器、列选择器和结果框。 您可以打开现有查询，也可以生成新的查询。  
  
 ![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")  
  
 若要生成一个新的查询，通过选择从业务的数据项目启动**业务数据**下拉列表。  
  
 ![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")  
  
 接下来，在“运算符”下拉列表中选择比较运算符。 利用比较运算符可以精确定义查询的结果。  
  
 ![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")  
  
 “值”下拉列表是基于业务数据项表示的数据类型的上下文相关的列表。 其用户界面 (UI) 会根据所允许的数据类型而更改。  
  
 可以将联接子句的查询中使用和或 OR 运算符以形成更复杂的查询，通过单击**添加**按钮。  
  
 ![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")  
  
> [!NOTE]
>  不能分组子句。 查询是由 AND/OR 运算符联接的多个子句的简单字符串。  
  
 下表说明了日期和时间字段。  
  
|运算符|Description|  
|--------------|-----------------|  
|**在**|指定完全匹配项。 等效于布尔运算中的等于 (=) 运算。 **注意：** 如果你选择**在**运算符和使用此门户使用的默认值为午夜没有时间部分指定一个日期。 如果这不是你的意图，使用**或之前**或**时或之后**运算符来获取所需的结果。|  
|**指定日期或之前**|指定只匹配等于或早于指定日期的事务。 等效于一个布尔值小于或等于 （≤） 操作。|  
|**或之后**|指定只匹配等于或晚于指定日期的事务。 等效于布尔值大于或等于 （≥） 操作。|  
|**早于**|指定只匹配早于指定日期的事务。 等效于一个布尔值小于 (<) 操作。|  
|**After**|指定只匹配晚于指定日期的事务。 等效于大于 (>) 的布尔操作。|  
|**在过去**|指定只匹配在上一个指定时间段内发生的事务。 时间段可以按秒、分钟、小时或天指定。|  
|**最后一个之前**|指定只匹配在指定时间段以前发生的事务。 时间段可以按秒、分钟、小时或天指定。|  
|**为空**|指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。|  
|**不为空**|指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。|  
  
 下表介绍数值字段和持续时间字段。 数值字段包含如数量或货币金额这样的数据。 持续时间字段指定一个时间段。  
  
|运算符|Description|  
|--------------|-----------------|  
|**等于**|指定完全匹配项。 等效于布尔运算中的等于 (=) 运算。|  
|**大于**|指定完全匹配项。 等效于布尔大于 (>) 操作。|  
|**大于或等于**|指定完全匹配项。 等效于 boolean 类型的值大于或等于 （≥） 操作。|  
|**小于**|指定完全匹配项。 等效于布尔小于 (<) 操作。|  
|**小于或等于**|指定完全匹配项。 等效于早于或等于 （≤） 操作。|  
|**不等于**|指定完全匹配项。 等效于不等于 （≠） 操作。|  
|**为空**|指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。|  
|**不为空**|指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。|  
  
 下表说明文本字段。  
  
|运算符|Description|  
|--------------|-----------------|  
|**正是**|指定完全匹配项。 等效于布尔运算中的等于 (=) 运算。|  
|**包含**|指定业务数据项中的文本包含指定的值。 这允许对数据执行部分匹配。|  
|**不包含**|指定业务数据项中的文本不包含指定的值。|  
|**为空**|指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。|  
|**不为空**|指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何创建活动搜索查询](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [如何设置警报](../core/how-to-set-an-alert.md)  
  
-   [如何查看活动搜索的结果](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a>另请参阅  
 [BAM 门户](../core/bam-portal.md)