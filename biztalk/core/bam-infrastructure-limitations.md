---
title: "BAM 基础结构限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e33d2f6c-8d26-4a76-810e-85d810cfdbee
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e42b2a6af04c2ff5d76d8ffb9489dfc2b92b6689
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="bam-infrastructure-limitations"></a>BAM 基础结构限制
BAM 基础结构具有以下设计此版本的 BizTalk Server 的限制：  
  
-   实时聚合 (RTA) 不支持 MIN 函数和 MAX 函数。  
  
-   在一个 RTA 视图中，不能按照多个数据维度引用一级别名。  
  
-   常规多维数据集和 RTA 均不支持非重复计数度量值。 BAM 管理实用程序能够为常规多维数据集和 RTA 创建默认的计数度量值。 默认计数是事实（也称为“活动实例”）的总数，不是非重复值计数。  
  
-   不要定义使用同一个 BAM 活动的多个 RTA。 否则，当您存档 BAM 数据时，RTA 数据将不正确。  
  
## <a name="bam-maximum-number-of-objects"></a>BAM 的对象最大数量  
 下表列出了 BAM 基础结构中对象的最大数量。  
  
|对象|实现限制|原因|  
|------------|--------------------------|------------|  
|活动中的检查点|1,000|SQL Server 支持 1,024 个存储过程参数，而 BizTalk Server 则使用三个系统过程。|  
|活动中的索引|245|SQL Server 每个表支持 245 个非聚集索引。 BizTalk Server 始终会创建一个关于 ActivityID 的索引。|  
|DataLength|4,000 个 Unicode 字符|系统使用 NVARCHAR 类型的 SQL 变量。|  
|ActivityRef|128|通过联接主导入数据库和关系表（每个活动两个），可以获得该视图。 SQL Server 在 SELECT 语句中支持 256 个表。|  
|视图中的列<br /><br /> （别名、持续时间和维度级别）|150|SQL Server 的中间临时表中的列数最多为 1,024 列，而 BAM 保留其中的 24 个列作为系统列。|  
|OLAP 多维数据集中的维度|128|OLAP 限制-128 每多维数据集维度|  
|OLAP 中的度量值|1,024|OLAP 限制 - 每个多维数据集 1,024 个度量值。 始终创建的 Count 度量值。|  
|OLAP 中的维度级别|64|OLAP 限制，并且每个多维数据集最多包含 256 个级别。|  
|RTA 视图中的维度级别|14 个维度级别|BAM 为所有维度级别创建一个索引，并且 SQL Server 索引最多只能针对 16 个列创建，而 BAM 保留两个列作为系统列。|  
|RTA 视图中的度量值、隐藏度量值（默认计数、AVG 的隐藏 SUM 度量值）和维度级别|1,024|在 SQL 表/视图中列数最多为 1,024。|  
|活动视图|63|当您配置一个警报时，你被限制为 63 个下 SQL Server。|  
  
## <a name="bam-object-names"></a>BAM 对象名称  
 下表列出 BAM 定义架构和 Microsoft Excel 电子表格中对象名称的限制。  
  
|对象名称|XSD 限制|Excel 限制|  
|------------------|--------------------|----------------------|  
|检查点名|50 个字符|50 个字符|  
|索引名称|100 个字符|100 个字符|  
|持续时间名|100 个字符|100 个字符|  
|别名名称|50 个字符|50 个字符|  
|活动名称|48 个字符|20 个字符|  
|视图名称|18 个字符|18 个字符|  
|ActivityView 名称|52 个字符（名称中包含前缀“View”，外加 48 个字符的视图名称。）|N/A（是从活动名派生的）|  
|多维数据集名称|20 个字符|N/A（是从视图名派生的）|  
|RealTimeAggregation 名称|48 个字符|N/A（是从多维数据集名称派生的）|  
|维度名|20 个字符|20 个字符|  
|级别名称|20 个字符|20 个字符|  
|度量值名称|20 个字符|20 个字符|  
|警报名称|128 个字符|N/A|  
|警报消息|1024 个字符|N/A|  
|事件规则名称|255 个字符|N/A|  
|事件提供程序名称|255 个字符|N/A|  
  
## <a name="see-also"></a>另请参阅  
 [BAM 配置架构](../core/bam-configuration-schema.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)