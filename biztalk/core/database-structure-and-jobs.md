---
title: "数据库结构和作业 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf98ef7fe236261fd3ee65ac6f4695455ba8c704
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="database-structure-and-jobs"></a>数据库结构和作业
本主题讨论数据库结构和数据库作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="database-write-diagram"></a>数据库写入关系图  
 下图显示了写入 BizTalk Server 数据库的过程和实体：  
  
 ![写入 BizTalk Server 数据库的进程](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a>BizTalk Server 数据库作业  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括以下 SQL Server 代理作业，以协助你管理 BizTalk Server 数据库：  
  
> [!NOTE]
>  根据在配置期间给定的数据库名称的不同，作业名称也会发生相应更改。 如果在环境中部署了多个 MessageBox 数据库，则对于每个 MessageBox 都将存在若干作业。  
  
> [!WARNING]
>  在 BizTalk 管理 (BizTalkMgmtDb) 数据库中，没有名为的存储的过程**adm_CleanupMgmtDB**。 **不运行此存储的过程 ！** 如果运行此存储过程，将删除数据库中的所有条目。  
  
|作业|Description|  
|---------|-----------------|  
|备份 BizTalk Server (BizTalkMgmtDb)|此作业执行 BizTalk Server 数据库的完全数据库和日志备份。 有关配置和运行此作业的详细信息，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。|  
|CleanupBTFExpiredEntriesJob_BizTalkMgmtDb|此作业清除 BizTalk 管理 (BizTalkMgmtDb) 数据库中过期的 BizTalk Framework (BTF) 条目。|  
|DTA 清除和存档 (BizTalkDTADb)|此作业自动存档 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据并清除过时的数据。 有关配置和运行此作业的详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。|  
|MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb|此作业检测 BizTalk Server 主机实例（NT 服务）停止的时间，并释放该主机实例已完成的所有工作，以便可以由其他主机实例进行处理。|  
|MessageBox_Message_Cleanup_BizTalkMsgBoxDb|此作业删除 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库表中不再被任何订户引用的所有消息。 **注意：**这是通过 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业来启动这些计划的作业。 不要手动启动此作业。|  
|MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb|此作业管理消息的引用计数日志，并确定消息何时不再被任何订户引用。 **注意：**即使此 SQL Server 代理作业计划运行一次，每分钟，此作业由调用的存储的过程包含逻辑，以确保持续运行此存储的过程。 这是由设计行为实现的，不应修改。|  
|MessageBox_Parts_Cleanup_BizTalkMsgBoxDb|此作业删除 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库表中不再被任何消息引用的所有消息部分。 所有消息都由一个或多个消息部分组成，这些消息部分包含实际的消息数据。|  
|MessageBox_UpdateStats_BizTalkMsgBoxDb|此作业手动更新 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的统计信息。|  
|监视 BizTalk Server|此作业在 BizTalkMgmtDb、BizTalkMsgBoxDb 和 BizTalkDTADb 数据库中扫描任何已知的问题，包括孤立实例。|  
|Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb|此作业是多个 MessageBox 部署所需的作业。 它通过异步方式执行运行操作，例如在将这些更改应用于从属 MessageBox 后对主 MessageBox 执行批量终止。|  
|PurgeSubscriptionsJob_BizTalkMsgBoxDb|此作业从 BizTalk Server MessageBox (BizTalkMsgBoxDb) 数据库清除未使用的订阅谓词。|  
|Rules_Database_Cleanup_BizTalkRuleEngineDb|此作业每隔 90 天从规则引擎 (BizTalkRuleEngineDb) 数据库中自动清除旧的审核数据。 此作业还每隔 3 天从规则引擎 (BizTalkRuleEngineDb) 数据库中清除旧的历史记录数据（部署/取消部署通知）。|  
  
## <a name="see-also"></a>另请参阅  
 [消息传送的引擎](../core/the-messaging-engine.md)