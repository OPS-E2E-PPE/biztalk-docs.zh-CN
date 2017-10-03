---
title: "备份和还原 BizTalk Server 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up [BAM]
- databases, backing up
- databases, restoring
- backing up, restoring
- backing up, databases
- restoring, BAM
- backing up, BAM
- backing up, backup jobs
- BAM, restoring
- restoring, databases
- restoring [BAM]
- BAM, backing up
ms.assetid: 82fc1af2-1389-4c79-80dc-f2df5656d201
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dba0e9e7cb5d01bf845eaa4adf3557dc3b6ea34a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-biztalk-server-databases"></a>备份和还原 BizTalk Server 数据库
使用备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业可以备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 源系统中的所有数据库，但业务活动监视 (BAM) 所使用的某些数据库除外。 源系统是包含实时数据的服务器或服务器组。 由于 BAM 数据库的备份和还原要求不同，因此，要使用其他方法对这些数据库进行备份和还原。  
  
 备份和还原 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库包括以下步骤：  
  
1.  **配置 BizTalk Server 中备份作业**  
  
     备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库之前，必须先在源系统中配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业，以便将备份自动写入一个文件夹中，然后可以使用该文件夹将数据库还原到目标系统。 目标系统是用于还原由源系统生成的数据库备份的服务器或服务器组。 有关此步骤的详细信息，请参阅[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)。  
  
2.  **配置日志传送目标系统**  
  
     您还必须配置日志传送的目标系统，该系统具有备用服务器功能，它可以缩短出现系统失败时的停机时间。 有关此步骤的详细信息，请参阅[如何为日志传送配置目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)。  
  
3.  **还原数据库**  
  
     在发生硬件故障时，通过使用发送到目标系统的备份和日志，可以还原数据库。 有关此步骤的详细信息，请参阅[如何还原您的数据库](../core/how-to-restore-your-databases.md)。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
 下表介绍了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用的数据库，并指出采用哪些方法来备份数据库。  
  
### <a name="databases-backed-up-by-the-backup-biztalk-server-job"></a>通过备份 BizTalk Server 作业备份的数据库  
 下表列出了在备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业的过程中备份和还原的数据库。 可以修改备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业，以通过将自定义数据库添加到 adm_OtherBackupDatabases 表来备份自定义数据库。 有关详细信息，请参阅[如何返回自定义数据库](../core/how-to-back-up-custom-databases.md)。  
  
|数据库|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 主导入数据库|BAMPrimaryImport|此数据库是业务活动监视 (BAM) 从中收集原始跟踪数据的数据库。|  
|BAM 通知服务应用程序数据库|BAMAlertsApplication|此数据库包含用于 BAM 通知的警报信息。 例如，在使用 BAM 门户创建警报时，会将指定与警报相关的条件和事件的条目以及支持警报数据项的其他条目插入该数据库中。|  
|BAM 通知服务实例数据库|BAMAlertsNSMain|此数据库包含指定通知服务如何连接到 BAM 所监视的系统的实例信息。|  
|BizTalk 跟踪数据库|BizTalkDTADb|此数据库存储 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 跟踪引擎所跟踪的运行状况监视数据。|  
|BizTalk 管理数据库|BizTalkMgmtDb|此数据库是所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 实例的中央元信息存储区。|  
|BizTalk MessageBox 数据库|BizTalkMsgBoxDb|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎使用此数据库来执行路由、排队、实例管理和其他各种任务。|  
|规则引擎数据库|BizTalkRuleEngineDb|此数据库是包含以下内容的存储库：<br /><br /> -策略，它是相关的规则集。<br />-词汇，它们是在规则中的数据引用的用户友好的特定于域的名称的集合。|  
|SSO 数据库|SSODB|此企业单一登录数据库安全地存储接收位置的配置信息。|  
  
### <a name="databases-backed-up-by-the-bam-backup-process"></a>通过 BAM 备份过程备份的数据库  
 下表列出的数据库的备份，使用中的过程还原[备份和还原 BAM](../core/backing-up-and-restoring-bam.md):  
  
|数据库|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 星型架构|BAMStarSchema|此数据库包含中间临时表、度量值表和维度表。|  
|BAM 分析|BAMAnalysis|此数据库包含用于进行联机和脱机分析的 BAM OLAP 多维数据集。|  
|BAM 存档|BAMArchive|此数据库存档旧的业务活动数据。 创建 BAM 存档数据库以最大限度地减少 BAM 主导入数据库中业务活动数据的累积。|  
|跟踪分析服务器|BizTalkAnalysisDb|此数据库存储运行状况监视联机分析处理 (OLAP) 多维数据集。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)  
  
-   [如何为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)  
  
-   [如何还原数据库](../core/how-to-restore-your-databases.md)  
  
-   [如何备份和还原 SQL 代理作业](../core/how-to-back-up-and-restore-sql-agent-jobs.md)  
  
-   [如何备份和还原 SQL Server 登录名](../core/how-to-back-up-and-restore-sql-server-logins.md)