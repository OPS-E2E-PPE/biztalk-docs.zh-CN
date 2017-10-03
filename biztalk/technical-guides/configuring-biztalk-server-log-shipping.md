---
title: "配置 BizTalk Server 日志传送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcef31f7-30d1-4ada-b627-2a5c9ec7e43e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3209d96c4516c603510f3cbb7fb48e3b1eb3209
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-biztalk-server-log-shipping"></a>配置 BizTalk Server 日志传送
使用备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业可以备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 源系统中的所有数据库，但业务活动监视 (BAM) 所使用的某些数据库除外。 源系统是包含实时数据的服务器或服务器组。 因为某些 BAM 数据库具有不同的备份和还原要求，这些数据库进行备份和还原使用其他方法。  
  
 备份和还原 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库包括以下步骤：  
  
1.  **配置 BizTalk Server 中备份作业**  
  
     备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库之前，必须先在源系统中配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业，以便将备份自动写入一个文件夹中，然后可以使用该文件夹将数据库还原到目标系统。 目标系统是用于还原由源系统生成的数据库备份的服务器或服务器组。 有关此步骤的详细信息，请参阅[如何配置备份 BizTalk Server 作业](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md)。  
  
2.  **配置日志传送目标系统**  
  
     您还必须配置日志传送的目标系统，该系统具有备用服务器功能，它可以缩短出现系统失败时的停机时间。 有关此步骤的详细信息，请参阅[如何配置目标系统](../technical-guides/how-to-configure-the-destination-system.md)。  
  
3.  **还原数据库**  
  
     在发生硬件故障时，通过使用发送到目标系统的备份和日志，可以还原数据库。 有关此步骤的详细信息，请参阅[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
 下表介绍了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用的数据库，并指出采用哪些方法来备份数据库。  
  
### <a name="databases-backed-up-by-the-backup-biztalk-server-job"></a>通过备份 BizTalk Server 作业备份的数据库  
 下表列出了在备份 BizTalk Server 作业的过程中备份和还原的数据库。 可以修改备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业，以通过将自定义数据库添加到 adm_OtherBackupDatabases 表来备份自定义数据库。 有关详细信息，请参阅[如何返回自定义数据库](http://go.microsoft.com/fwlink/?LinkID=151569)(http://go.microsoft.com/fwlink/?LinkID=151569)。  
  
|数据库|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 主导入数据库|BAMPrimaryImport|此数据库是业务活动监视 (BAM) 从中收集原始跟踪数据的数据库。|  
|BAM 通知服务应用程序数据库|BAMAlertsApplication|此数据库包含用于 BAM 通知的警报信息。 例如，在使用 BAM 门户创建警报时，会将指定与警报相关的条件和事件的条目以及支持警报数据项的其他条目插入该数据库中。|  
|BAM 通知服务实例数据库|BAMAlertsNSMain|此数据库包含指定通知服务如何连接到 BAM 所监视的系统的实例信息。|  
|BizTalk 跟踪数据库|BizTalkDTADb|此数据库存储 BizTalk Server 跟踪引擎所跟踪的运行状况监视数据。|  
|BizTalk 管理数据库|BizTalkMgmtDb|此数据库是所有 BizTalk Server 实例的中央元信息存储区。|  
|BizTalk MessageBox 数据库|BizTalkMsgBoxDb|BizTalk Server 引擎使用此数据库来执行路由、排队、实例管理和其他各种任务。|  
|规则引擎数据库|BizTalkRuleEngineDb|此数据库是包含以下内容的存储库：<br /><br /> -策略，它是相关的规则集。<br />-词汇，它们是在规则中的数据引用的用户友好的特定于域的名称的集合。|  
|SSO 数据库|SSODB|此企业单一登录数据库更安全地存储配置的信息接收位置。|  
  
### <a name="databases-backed-up-when-backing-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>当备份 BAM 分析和跟踪 Analysis Server 数据库备份的数据库  
 下表列出了使用中的过程进行备份的数据库[备份 BAM 分析和跟踪 Analysis Server 数据库](http://msdn.microsoft.com/library/aa578580\(v=bts.70\).aspx):  
  
|数据库|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 星型架构|BAMStarSchema|此数据库包含中间临时表、度量值表和维度表。|  
|BAM 分析|BAMAnalysis|此数据库包含用于进行联机和脱机分析的 BAM OLAP 多维数据集。|  
|BAM 存档|BAMArchive|此数据库存档旧的业务活动数据。 创建 BAM 存档数据库以最大限度地减少 BAM 主导入数据库中业务活动数据的累积。|  
|跟踪分析服务器|BizTalkAnalysisDb|此数据库存储运行状况监视联机分析处理 (OLAP) 多维数据集。|  
  
 操作指南的本部分介绍你应遵循的配置 BizTalk Server 的其他步骤日志传送。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置源系统](../technical-guides/configuring-the-source-system.md)  
  
-   [如何配置目标系统](../technical-guides/how-to-configure-the-destination-system.md)  
  
-   [配置 BizTalk Server 日志传送有关的其他数据库](../technical-guides/configuring-biztalk-server-log-shipping-for-additional-databases.md)  
  
-   [监视 BizTalk Server 日志传送](../technical-guides/monitoring-biztalk-server-log-shipping.md)