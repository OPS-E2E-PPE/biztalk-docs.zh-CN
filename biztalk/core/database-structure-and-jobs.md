---
title: 数据库结构和作业 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PurgeSubscriptionsJob_BizTalkMsgBoxDb job
- MessageBox database, jobs [SQL Server Agent]
- DTA Purge and Archive (BizTalkDTADb) job
- TrackedMessages_Copy_BizTalkMsgBoxDb job
- MessageBox_Message_Cleanup_BizTalkMsgBoxDb job
- MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job
- Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], MessageBox database
- CleanupBTFExpiredEntriesJob_BizTalkMgmtDb job
- databases, structure
- Tracking database, jobs [SQL Server Agent]
- jobs [SQL Server Agent], Management database
- Backup BizTalk Server (BizTalkMgmtDb) job
- databases, SQL Server Agent jobs
- Business Rules Engine, jobs [SQL Server Agent]
- jobs, databases
- Management database, jobs [SQL Server Agent]
- MessageBox_UpdateStats_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Business Rules Engine
- Rules_Database_Cleanup_BizTalkRuleEngineDb job
- MessageBox_Parts_Cleanup_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Tracking database
- MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb job
ms.assetid: f5f6b17d-0f5e-4821-a7eb-c345234ffc65
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5cf9b5ec724e0070b7425732a74c50d3873bd67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352590"
---
# <a name="database-structure-and-jobs"></a>数据库结构和作业
本主题讨论的数据库结构和数据库作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="database-write-diagram"></a>数据库写入关系图  
 下图显示的过程和写入到 BizTalk Server 数据库的实体。  
  
 ![写入到 BizTalk Server 数据库的进程](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a>BizTalk Server 数据库作业  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括以下的 SQL Server 代理作业，以协助你管理 BizTalk Server 数据库：  
  
> [!NOTE]
>  根据在配置期间给定的数据库名称更改的作业的名称。 如果已在环境中部署多个 MessageBox 数据库，将为每个 MessageBox 的多个作业。  
  
> [!WARNING]
>  在 BizTalk 管理 (BizTalkMgmtDb) 数据库中，没有名为存储的过程**adm_CleanupMgmtDB**。 **不要运行此存储的过程 ！** 如果运行此存储的过程，将删除数据库中的所有条目。  
  
|作业|Description|  
|---------|-----------------|  
|备份 BizTalk Server (BizTalkMgmtDb)|此作业执行完整数据库备份和日志备份的 BizTalk Server 数据库。 有关配置和运行此作业的详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)。|  
|CleanupBTFExpiredEntriesJob_BizTalkMgmtDb|此作业清除 BizTalk 管理 (BizTalkMgmtDb) 数据库中已过期的 BizTalk 框架 (BTF) 条目。|  
|DTA 清除和存档 (BizTalkDTADb)|此作业自动存档 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据，并清除过时的数据。 有关配置和运行此作业的详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。|  
|MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb|当 BizTalk Server 主机实例 （NT 服务） 已停止并释放所有已完成的该主机实例，以便它可以由另一个主机实例从事的工作，检测到此作业。|  
|MessageBox_Message_Cleanup_BizTalkMsgBoxDb|此作业删除 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库表中的任何订阅服务器将不再被引用的所有消息。 **注意：** 这是由 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业启动计划外的作业。 不要手动启动此作业。|  
|MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb|此作业管理消息的引用计数日志，并确定当一条消息都不再引用的任何订阅服务器。 **注意：** 即使此 SQL Server 代理作业计划运行后，每分钟调用此作业的存储的过程包含逻辑，以确保持续运行该存储的过程。 这是由设计行为并不应修改。|  
|MessageBox_Parts_Cleanup_BizTalkMsgBoxDb|此作业删除 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库表中的任何消息都不再被引用的所有消息部分。 所有消息都组成一个或多个消息部分，包含实际的消息数据。|  
|MessageBox_UpdateStats_BizTalkMsgBoxDb|此作业手动更新 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的统计信息。|  
|监视 BizTalk Server|此作业扫描 BizTalkMgmtDb、 BizTalkMsgBoxDb 和 BizTalkDTADb 数据库的任何已知问题，包括孤立实例。|  
|Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb|此作业需要多个 MessageBox 部署。 如批量终止主 MessageBox 上这些更改应用于从属 MessageBox 后，将以异步方式执行操作的操作。|  
|PurgeSubscriptionsJob_BizTalkMsgBoxDb|此作业从 BizTalk Server MessageBox (BizTalkMsgBoxDb) 数据库清除未使用的订阅谓词。|  
|Rules_Database_Cleanup_BizTalkRuleEngineDb|此作业会自动清除旧的审核数据从规则引擎 (BizTalkRuleEngineDb) 数据库每隔 90 天。 此作业还会清除掉旧的历史记录数据 （部署/取消部署通知） 从规则引擎 (BizTalkRuleEngineDb) 数据库每隔 3 天。|  
  
## <a name="see-also"></a>请参阅  
 [消息引擎](../core/the-messaging-engine.md)