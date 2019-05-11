---
title: 配置 BizTalk Server 日志传送 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcef31f7-30d1-4ada-b627-2a5c9ec7e43e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b03884a46c1b6a20baa3c54be38e3754e1027f61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253504"
---
# <a name="configuring-biztalk-server-log-shipping"></a>配置 BizTalk Server 日志传送
使用备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的数据库的所有备份作业在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]源系统，使用由业务活动监视 (BAM) 某些数据库除外。 源系统是服务器或组包含实时数据的服务器。 因为某些 BAM 数据库具有不同的备份和还原要求，这些数据库进行备份和还原使用其他方法。  
  
 备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和还原涉及以下步骤：  
  
1. **配置备份 BizTalk Server 作业**  
  
    在备份之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，必须先配置备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]源系统，以便将备份自动写入其中它们可以然后使用要还原到目标数据库的文件夹上的作业系统。 目标系统是服务器或组将用于还原由源系统生成的数据库备份的服务器。 有关此步骤的详细信息，请参阅[如何配置备份 BizTalk Server 作业](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md)。  
  
2. **配置日志传送的目标系统**  
  
    此外必须配置日志传送具有备用服务器功能，可以缩短出现系统故障时的停机时间的目标系统。 有关此步骤的详细信息，请参阅[如何配置目标系统](../technical-guides/how-to-configure-the-destination-system.md)。  
  
3. **还原数据库**  
  
    出现硬件故障时，可以通过使用备份和日志发送到目标系统中还原数据库。 有关此步骤的详细信息，请参阅[如何还原数据库备份 BizTalk Server 作业中](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
 下表描述了使用的数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并确定哪些方法可用来将数据库备份。  
  
### <a name="databases-backed-up-by-the-backup-biztalk-server-job"></a>备份的数据库的备份 BizTalk Server 作业  
 下表列出了备份和还原的备份 BizTalk Server 作业一部分的数据库。 您可以修改备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业，以通过将它们添加到 adm_OtherBackupDatabases 表来备份自定义数据库。 有关详细信息，请参阅[如何返回自定义数据库](http://go.microsoft.com/fwlink/?LinkID=151569)(<http://go.microsoft.com/fwlink/?LinkID=151569>)。  
  
|“数据库”|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 主导入数据库|BAMPrimaryImport|这是业务活动监视 (BAM) 从中收集原始跟踪数据的数据库。|  
|BAM Notification Services 应用程序数据库|BAMAlertsApplication|此数据库包含 BAM 通知的警报信息。 例如，在创建警报使用 BAM 门户时，会将条目插入在指定与警报相关，以及其他支持的数据项的警报的条件和事件的数据库中。|  
|BAM 通知服务实例数据库|BAMAlertsNSMain|此数据库包含指定 notification services 如何连接到 BAM 监视的系统的实例信息。|  
|BizTalk 跟踪数据库|BizTalkDTADb|此数据库存储运行状况监视 BizTalk Server 跟踪引擎所跟踪的数据。|  
|BizTalk 管理数据库|BizTalkMgmtDb|此数据库是 BizTalk Server 的所有实例的中央元信息存储区。|  
|BizTalk MessageBox 数据库|BizTalkMsgBoxDb|BizTalk Server 引擎使用此数据库的路由、 排队、 实例管理和各种其他任务。|  
|规则引擎数据库|BizTalkRuleEngineDb|此数据库是存储库：<br /><br /> -策略，这是一组相关的规则。<br />-词汇，即是规则中的数据引用的用户友好的特定于域的名称的集合。|  
|SSO 数据库|SSODB|此企业单一登录数据库更安全地存储配置信息的接收位置。|  
  
### <a name="databases-backed-up-when-backing-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>备份 BAM 分析和跟踪分析服务器数据库时备份数据库  
 下表列出了使用备份中的过程的数据库[备份 BAM 分析和跟踪分析服务器数据库](http://msdn.microsoft.com/library/aa578580\(v=bts.70\).aspx):  
  
|“数据库”|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 星型架构|BAMStarSchema|此数据库包含中间临时表、 和的度量值和维度表。|  
|BAM 分析|BAMAnalysis|此数据库包含 BAM OLAP 多维数据集以进行联机和脱机分析。|  
|BAM 存档|BAMArchive|此数据库存档旧的业务活动数据。 创建 BAM 存档数据库以最大程度减少 BAM 主导入数据库中的业务活动数据的累计。|  
|跟踪分析服务器|BizTalkAnalysisDb|此数据库存储运行状况监视联机分析处理 (OLAP) 多维数据集。|  
  
 操作指南的本部分介绍应遵循配置 BizTalk Server 的其他步骤日志传送。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置源系统](../technical-guides/configuring-the-source-system.md)  
  
-   [如何配置目标系统](../technical-guides/how-to-configure-the-destination-system.md)  
  
-   [为其他数据库配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping-for-additional-databases.md)  
  
-   [监视 BizTalk Server 日志传送](../technical-guides/monitoring-biztalk-server-log-shipping.md)