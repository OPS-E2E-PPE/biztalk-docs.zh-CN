---
title: 管理 BAM 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], databases
- databases [BAM], managing
- databases, BAM
ms.assetid: ce3c472e-2da1-4d67-816a-befe4ded20d9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dbe8cdb2c7806ab62b67db80c4741d64560fba9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262573"
---
# <a name="managing-bam-databases"></a>管理 BAM 数据库
管理员使用 BAM 管理实用程序 (bm.exe) 可以安装、管理和更新 BAM 数据库。 本部分介绍如何使用 BAM 管理实用程序来执行 BAM 数据库的这些通用管理员任务，如下表所述。  
  
 有关备份和还原的 BAM 数据库的信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
  
|数据库|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 主导入数据库|BAMPrimaryImport|BAM 收集原始跟踪数据的地方。|  
|BAM 通知服务应用程序数据库|BAMAlertsApplication|包含 BAM 通知的警报信息。 例如，在使用 BAM 门户创建警报时，会将指定与警报相关的条件和事件的条目以及支持警报数据项的其他条目插入该数据库中。|  
|BAM 通知服务实例数据库|BAMAlertsNSMain|包含指定 Notification Services 如何连接到 BAM 正在监视的系统的实例信息。|  
|BAM 星型架构数据库|BAMStarSchema|包含中间临时表、度量值表和维度表。|  
|BAM 分析数据库|BAMAnalysis|包含用于进行联机和脱机分析的 BAM OLAP 多维数据集。|  
|BAM 存档数据库|BAMArchive|存档旧的业务活动数据。 您可以创建 BAM 存档数据库，以最大限度地减少 BAM 主导入数据库中的业务活动数据的累积。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [将主导入数据库数据存档](../core/archiving-primary-import-database-data.md)  
  
-   [在存档数据库中创建分区的视图](../core/creating-a-partitioned-view-in-the-archiving-database.md)  
  
-   [计划 SQL Server Integration Services 包](../core/scheduling-sql-server-integration-services-packages.md)  
  
-   [如何使用 BAM 管理实用工具 BAM 数据库设置](../core/how-to-set-up-the-bam-databases-using-the-bam-management-utility.md)  
  
-   [如何检索 BAM 配置文件使用 BAM 管理实用工具](../core/how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility.md)  
  
-   [如何更新 BAM 配置使用 BAM 管理实用工具](../core/how-to-update-the-bam-configuration-using-the-bam-management-utility.md)  
  
-   [如何引用其他 BAM 主导入数据库](../core/how-to-reference-additional-bam-primary-import-databases.md)  
  
-   [如何禁用 BAM 主导入数据库参考](../core/how-to-disable-a-bam-primary-import-database-reference.md)  
  
-   [如何列出所有引用数据库](../core/how-to-list-all-referenced-databases.md)  
  
-   [如何删除不完整的活动实例](../core/how-to-remove-incomplete-activity-instances.md)  
  
-   [如何更新后的备份和还原的 BAM 管理实用程序配置](../core/update-the-bam-management-utility-configuration-after-a-backup-and-restore.md)  
  
-   [如何将与 SQL Server Reporting Services 集成 BAM](../core/how-to-integrate-bam-with-sql-server-reporting-services.md)  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM](../core/managing-bam.md)