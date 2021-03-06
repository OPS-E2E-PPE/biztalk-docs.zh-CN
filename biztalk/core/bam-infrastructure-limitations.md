---
title: BAM 基础结构限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e33d2f6c-8d26-4a76-810e-85d810cfdbee
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62933be0b8b72df49c707440bc63c7943d17ebd9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530559"
---
# <a name="bam-infrastructure-limitations"></a>BAM 基础结构限制
BAM 基础结构有以下设计此版本的 BizTalk Server 的限制：  
  
-   实时聚合 (Rta) 不支持 MIN 或 MAX 函数。  
  
-   不能通过在一个 RTA 视图中的多个数据维度引用一级别名。  
  
-   常规多维数据集和 RTA 均不支持非重复计数度量值。 BAM 管理实用程序创建常规多维数据集和 RTA 的默认计数度量值。 默认计数是事实 （也称为"活动实例"），总计数和未非重复计数。  
  
-   未定义使用同一个 BAM 活动的多个 Rta。 如果这样做，RTA 数据将不正确，当您存档 BAM 数据。  
  
## <a name="bam-maximum-number-of-objects"></a>BAM 的最大对象数  
 下表列出了 BAM 基础结构中的对象的最大数目。  
  
|Object|实现限制|Reason|  
|------------|--------------------------|------------|  
|中活动检查点|1,000|SQL Server 支持 1,024 个存储过程参数和 BizTalk Server 使用三种系统过程。|  
|活动中的索引|245|SQL Server 支持每个表的 245 非聚集索引。 BizTalk Server 始终创建关于 ActivityID 的索引。|  
|DataLength|4,000 个 Unicode 字符|使用 NVARCHAR 类型的 SQL 变量。|  
|ActivityRef|128|可以通过联接主导入数据库和表关系 （每个活动的两个） 获得该视图。 SQL Server 在 SELECT 语句中支持 256 个表。|  
|视图中的列<br /><br /> （别名、 持续时间和维度级别）|150|SQL Server 的临时表的 BAM 保留其中的 24 作为系统列 1,024 列的限制。|  
|在 OLAP 多维数据集维度|128|OLAP 限制-每个多维数据集 128 个维度|  
|OLAP 中的度量值|1,024|每个多维数据集的 OLAP 限制-1,024 个度量值。 始终创建计数度量值。|  
|OLAP 中的维度级别|64|OLAP 限制，并且每个多维数据集的 256 级别的其他限制。|  
|RTA 视图中的维度级别|14 个维度级别|BAM 在所有维度级别上创建索引、 最多 16 个列，可以创建 SQL Server 索引和 BAM 保留两个用于系统列。|  
|度量值、 隐藏的度量值 （默认计数、 AVG 的隐藏 SUM 度量值） 和 RTA 视图中的维度级别|1,024|SQL 表/视图中的 1,024 列的最大值。|  
|ActivityViews|63|当您配置一个警报时，你被限制为 63 活动 SQL Server 下。|  
  
## <a name="bam-object-names"></a>BAM 对象名称  
 下表列出了 BAM 定义架构和 Microsoft Excel 电子表格中的对象名称的限制。  
  
|对象名称|XSD 限制|Excel 限制|  
|------------------|--------------------|----------------------|  
|检查点的名称|50 个字符|50 个字符|  
|索引名称|100 个字符|100 个字符|  
|持续时间名|100 个字符|100 个字符|  
|别名名称|50 个字符|50 个字符|  
|活动名称|48 个字符|20 个字符|  
|视图名称|18 个字符|18 个字符|  
|ActivityView 名称|52 个字符 （名称中包含的前缀"View"加 48 个字符的视图名称。）|N/A （派生自活动名称）|  
|多维数据集名称|20 个字符|N/A （派生自视图名称）|  
|RealTimeAggregation 名称|48 个字符|N/A （派生自多维数据集名称）|  
|维度名称|20 个字符|20 个字符|  
|级别名称|20 个字符|20 个字符|  
|度量值名称|20 个字符|20 个字符|  
|警报名称|128 个字符|不可用|  
|警报消息|1024 个字符|不可用|  
|事件规则名称|255 个字符|不可用|  
|事件提供程序名称|255 个字符|不可用|  
  
## <a name="see-also"></a>请参阅  
 [BAM 配置架构](../core/bam-configuration-schema.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)