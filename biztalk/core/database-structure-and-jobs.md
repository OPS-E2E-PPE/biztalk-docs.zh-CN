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
# <a name="database-structure-and-jobs"></a><span data-ttu-id="bf009-102">数据库结构和作业</span><span class="sxs-lookup"><span data-stu-id="bf009-102">Database Structure and Jobs</span></span>
<span data-ttu-id="bf009-103">本主题讨论数据库结构和数据库作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf009-103">This topic discusses the database structure and database jobs for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="database-write-diagram"></a><span data-ttu-id="bf009-104">数据库写入关系图</span><span class="sxs-lookup"><span data-stu-id="bf009-104">Database Write Diagram</span></span>  
 <span data-ttu-id="bf009-105">下图显示了写入 BizTalk Server 数据库的过程和实体：</span><span class="sxs-lookup"><span data-stu-id="bf009-105">The following figure shows the processes and entities that write to the BizTalk Server databases.</span></span>  
  
 <span data-ttu-id="bf009-106">![写入 BizTalk Server 数据库的进程](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")</span><span class="sxs-lookup"><span data-stu-id="bf009-106">![Processes that write to BizTalk Server databases](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")</span></span>  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a><span data-ttu-id="bf009-107">BizTalk Server 数据库作业</span><span class="sxs-lookup"><span data-stu-id="bf009-107">BizTalk Server Database Jobs</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bf009-108"> 包括以下 SQL Server 代理作业，以协助你管理 BizTalk Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="bf009-108"> includes the following SQL Server Agent jobs to assist you in managing the BizTalk Server databases:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf009-109">根据在配置期间给定的数据库名称的不同，作业名称也会发生相应更改。</span><span class="sxs-lookup"><span data-stu-id="bf009-109">The names of the jobs change depending on the database names given during configuration.</span></span> <span data-ttu-id="bf009-110">如果在环境中部署了多个 MessageBox 数据库，则对于每个 MessageBox 都将存在若干作业。</span><span class="sxs-lookup"><span data-stu-id="bf009-110">If you have deployed multiple MessageBox databases in your environment, there will be several jobs for each MessageBox.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bf009-111">在 BizTalk 管理 (BizTalkMgmtDb) 数据库中，没有名为的存储的过程**adm_CleanupMgmtDB**。</span><span class="sxs-lookup"><span data-stu-id="bf009-111">In the BizTalk Management (BizTalkMgmtDb) database, there's a stored procedure named **adm_CleanupMgmtDB**.</span></span> <span data-ttu-id="bf009-112">**不运行此存储的过程 ！**</span><span class="sxs-lookup"><span data-stu-id="bf009-112">**DO NOT RUN THIS STORED PROCEDURE!**</span></span> <span data-ttu-id="bf009-113">如果运行此存储过程，将删除数据库中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="bf009-113">If you do run this stored procedure, all the entries in the database will be deleted.</span></span>  
  
|<span data-ttu-id="bf009-114">作业</span><span class="sxs-lookup"><span data-stu-id="bf009-114">Job</span></span>|<span data-ttu-id="bf009-115">Description</span><span class="sxs-lookup"><span data-stu-id="bf009-115">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="bf009-116">备份 BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="bf009-116">Backup BizTalk Server (BizTalkMgmtDb)</span></span>|<span data-ttu-id="bf009-117">此作业执行 BizTalk Server 数据库的完全数据库和日志备份。</span><span class="sxs-lookup"><span data-stu-id="bf009-117">This job performs full database and log backups of the BizTalk Server databases.</span></span> <span data-ttu-id="bf009-118">有关配置和运行此作业的详细信息，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="bf009-118">For more information about configuring and running this job, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>|  
|<span data-ttu-id="bf009-119">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="bf009-119">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>|<span data-ttu-id="bf009-120">此作业清除 BizTalk 管理 (BizTalkMgmtDb) 数据库中过期的 BizTalk Framework (BTF) 条目。</span><span class="sxs-lookup"><span data-stu-id="bf009-120">This job cleans up expired BizTalk Framework (BTF) entries in the BizTalk Management (BizTalkMgmtDb) database.</span></span>|  
|<span data-ttu-id="bf009-121">DTA 清除和存档 (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="bf009-121">DTA Purge and Archive (BizTalkDTADb)</span></span>|<span data-ttu-id="bf009-122">此作业自动存档 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据并清除过时的数据。</span><span class="sxs-lookup"><span data-stu-id="bf009-122">This job automatically archives data in the BizTalk Tracking (BizTalkDTADb) database and purges obsolete data.</span></span> <span data-ttu-id="bf009-123">有关配置和运行此作业的详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。</span><span class="sxs-lookup"><span data-stu-id="bf009-123">For more information about configuring and running this job, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>|  
|<span data-ttu-id="bf009-124">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="bf009-124">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="bf009-125">此作业检测 BizTalk Server 主机实例（NT 服务）停止的时间，并释放该主机实例已完成的所有工作，以便可以由其他主机实例进行处理。</span><span class="sxs-lookup"><span data-stu-id="bf009-125">This job detects when a BizTalk Server host instance (NT service) has stopped and releases all work that was being done by that host instance so that it can be worked on by another host instance.</span></span>|  
|<span data-ttu-id="bf009-126">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="bf009-126">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="bf009-127">此作业删除 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库表中不再被任何订户引用的所有消息。</span><span class="sxs-lookup"><span data-stu-id="bf009-127">This job removes all messages that are no longer being referenced by any subscribers in the BizTalk MessageBox (BizTalkMsgBoxDb) database tables.</span></span> <span data-ttu-id="bf009-128">**注意：**这是通过 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业来启动这些计划的作业。</span><span class="sxs-lookup"><span data-stu-id="bf009-128">**Caution:**  This is an unscheduled job which is started by the MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job.</span></span> <span data-ttu-id="bf009-129">不要手动启动此作业。</span><span class="sxs-lookup"><span data-stu-id="bf009-129">Do not manually start this job.</span></span>|  
|<span data-ttu-id="bf009-130">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="bf009-130">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="bf009-131">此作业管理消息的引用计数日志，并确定消息何时不再被任何订户引用。</span><span class="sxs-lookup"><span data-stu-id="bf009-131">This job manages the reference count logs for messages and determines when a message is no longer referenced by any subscriber.</span></span> <span data-ttu-id="bf009-132">**注意：**即使此 SQL Server 代理作业计划运行一次，每分钟，此作业由调用的存储的过程包含逻辑，以确保持续运行此存储的过程。</span><span class="sxs-lookup"><span data-stu-id="bf009-132">**Note:**  Even thought this SQL Server Agent job is scheduled to run once per minute, the stored procedure that is called by this job contains logic to ensure that the stored procedure runs continually.</span></span> <span data-ttu-id="bf009-133">这是由设计行为实现的，不应修改。</span><span class="sxs-lookup"><span data-stu-id="bf009-133">This is by design behavior and should not be modified.</span></span>|  
|<span data-ttu-id="bf009-134">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="bf009-134">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="bf009-135">此作业删除 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库表中不再被任何消息引用的所有消息部分。</span><span class="sxs-lookup"><span data-stu-id="bf009-135">This job removes all message parts that are no longer being referenced by any messages in the BizTalk MessageBox (BizTalkMsgBoxDb) database tables.</span></span> <span data-ttu-id="bf009-136">所有消息都由一个或多个消息部分组成，这些消息部分包含实际的消息数据。</span><span class="sxs-lookup"><span data-stu-id="bf009-136">All messages are made up of one or more message parts, which contain the actual message data.</span></span>|  
|<span data-ttu-id="bf009-137">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="bf009-137">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="bf009-138">此作业手动更新 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的统计信息。</span><span class="sxs-lookup"><span data-stu-id="bf009-138">This job manually updates the statistics for the BizTalk MessageBox (BizTalkMsgBoxDb) database.</span></span>|  
|<span data-ttu-id="bf009-139">监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bf009-139">Monitor BizTalk Server</span></span>|<span data-ttu-id="bf009-140">此作业在 BizTalkMgmtDb、BizTalkMsgBoxDb 和 BizTalkDTADb 数据库中扫描任何已知的问题，包括孤立实例。</span><span class="sxs-lookup"><span data-stu-id="bf009-140">This job scans the BizTalkMgmtDb, BizTalkMsgBoxDb and BizTalkDTADb database for any known issues, including orphaned instances.</span></span>|  
|<span data-ttu-id="bf009-141">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="bf009-141">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="bf009-142">此作业是多个 MessageBox 部署所需的作业。</span><span class="sxs-lookup"><span data-stu-id="bf009-142">This job is needed for multiple MessageBox deployments.</span></span> <span data-ttu-id="bf009-143">它通过异步方式执行运行操作，例如在将这些更改应用于从属 MessageBox 后对主 MessageBox 执行批量终止。</span><span class="sxs-lookup"><span data-stu-id="bf009-143">It asynchronously performs operational actions such as bulk terminate on the master MessageBox after those changes have been applied to the subordinate MessageBox.</span></span>|  
|<span data-ttu-id="bf009-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="bf009-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="bf009-145">此作业从 BizTalk Server MessageBox (BizTalkMsgBoxDb) 数据库清除未使用的订阅谓词。</span><span class="sxs-lookup"><span data-stu-id="bf009-145">This job purges unused subscription predicates from the BizTalk Server MessageBox (BizTalkMsgBoxDb) database.</span></span>|  
|<span data-ttu-id="bf009-146">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="bf009-146">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>|<span data-ttu-id="bf009-147">此作业每隔 90 天从规则引擎 (BizTalkRuleEngineDb) 数据库中自动清除旧的审核数据。</span><span class="sxs-lookup"><span data-stu-id="bf009-147">This job automatically purges old audit data from the Rule Engine (BizTalkRuleEngineDb) database every 90 days.</span></span> <span data-ttu-id="bf009-148">此作业还每隔 3 天从规则引擎 (BizTalkRuleEngineDb) 数据库中清除旧的历史记录数据（部署/取消部署通知）。</span><span class="sxs-lookup"><span data-stu-id="bf009-148">This job also purges old history data (deploy/undeploy notifications) from the Rule Engine (BizTalkRuleEngineDb) database every 3 days.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf009-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf009-149">See Also</span></span>  
 [<span data-ttu-id="bf009-150">消息传送的引擎</span><span class="sxs-lookup"><span data-stu-id="bf009-150">The Messaging Engine</span></span>](../core/the-messaging-engine.md)