---
title: 标记的事务，完整备份，备份和日志备份 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, transaction logs
- backing up, full backups
- transaction logs
- backing up, backup jobs
ms.assetid: a383a16d-1e40-4b0b-a515-f1cb90bfb4d2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22f02fe6dde63c01707d15f4210c29f52f112e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974838"
---
# <a name="marked-transactions-full-backups-and-log-backups"></a><span data-ttu-id="d4327-102">标记的事务、完整备份和日志备份</span><span class="sxs-lookup"><span data-stu-id="d4327-102">Marked Transactions, Full Backups, and Log Backups</span></span>
<span data-ttu-id="d4327-103">备份 BizTalk Server 作业创建的所有 BizTalk Server 数据库使用完整数据库备份和事务日志备份，以及一种称为事务中的同步的备份*标记的事务*。</span><span class="sxs-lookup"><span data-stu-id="d4327-103">The Backup BizTalk Server Job creates synchronized backups of all BizTalk Server databases by using full database backups and transaction log backups, in conjunction with a type of transaction known as a *marked transaction*.</span></span> <span data-ttu-id="d4327-104">标记的事务是在事务中放置到的参与的所有数据库的事务日志标记的事务。</span><span class="sxs-lookup"><span data-stu-id="d4327-104">Marked transactions are transactions that place a mark into the transaction log of all databases participating in the transaction.</span></span> <span data-ttu-id="d4327-105">标记的事务阻止启动新的分布式的事务，等待当前正在运行才能完成，则分布式事务，然后执行以放置标记。</span><span class="sxs-lookup"><span data-stu-id="d4327-105">The marked transaction blocks new distributed transactions from starting, waits for the distributed transactions that are currently running to complete, and then executes to place the mark.</span></span>  
  
 <span data-ttu-id="d4327-106">该标记所表示的事务点是一致的跨所有数据库;可用于标记和后续日志备份将数据库还原到该点。</span><span class="sxs-lookup"><span data-stu-id="d4327-106">The mark represents a transaction point that is consistent across all databases; you can use the mark with subsequent log backups to restore your databases to that point.</span></span>  
  
 <span data-ttu-id="d4327-107">对于每个 BizTalk Server 数据库，备份 BizTalk Server 作业在每次运行，并创建根据你指定的时间段的完整备份创建标记的事务日志备份。</span><span class="sxs-lookup"><span data-stu-id="d4327-107">For each BizTalk Server database, the Backup BizTalk Server job creates a marked transaction log backup every time it runs, and it creates a full backup based on a time period that you specify.</span></span>  
  
## <a name="full-backups"></a><span data-ttu-id="d4327-108">完整备份</span><span class="sxs-lookup"><span data-stu-id="d4327-108">Full backups</span></span>  
 <span data-ttu-id="d4327-109">在运行备份 BizTalk Server 作业时运行第一个备份过程中， *BackupFull*，一次每个句点 （非每次作业运行时）。</span><span class="sxs-lookup"><span data-stu-id="d4327-109">When you run the Backup BizTalk Server job it runs the first backup process, *BackupFull*, once every period (not every time the job runs).</span></span> <span data-ttu-id="d4327-110">有关如何安排备份 BizTalk Server 作业的详细信息，请参阅[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="d4327-110">For more information about how to schedule the Backup BizTalk Server job, see [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
 <span data-ttu-id="d4327-111">首次备份 BizTalk Server 作业运行时在新的期间，它将执行完整备份。</span><span class="sxs-lookup"><span data-stu-id="d4327-111">The first time the Backup BizTalk Server job runs during a new period, it performs a full backup.</span></span> <span data-ttu-id="d4327-112">例如，如果您计划要运行的作业每隔一小时但配置段要备份 BizTalk Server 作业每天执行首次运行，且然后每天午夜的完整备份。</span><span class="sxs-lookup"><span data-stu-id="d4327-112">For example, if you schedule the job to run every hour but configure the period to be daily, the Backup BizTalk Server job performs a full backup the first time it runs, and then every day at midnight.</span></span>  
  
## <a name="transaction-log-backups"></a><span data-ttu-id="d4327-113">事务日志备份</span><span class="sxs-lookup"><span data-stu-id="d4327-113">Transaction log backups</span></span>  
 <span data-ttu-id="d4327-114">备份 BizTalk Server 作业将执行的第二个过程*MarkAndBackupLog*。</span><span class="sxs-lookup"><span data-stu-id="d4327-114">The second process that the Backup BizTalk Server job performs is *MarkAndBackupLog*.</span></span> <span data-ttu-id="d4327-115">此过程将标记置于在所有 BizTalk Server 数据库和每次作业执行时执行事务日志备份。</span><span class="sxs-lookup"><span data-stu-id="d4327-115">This process places a mark in all BizTalk Server databases and performs a transaction log backup every time the job executes.</span></span>  
  
 <span data-ttu-id="d4327-116">标记，通过使用创建的字符串 *\<ServerName\>*<em>*\<DatabaseName\>*（_l)\\</em>   *\<LogMarkName\>*\_*\<时间戳\>*.bak，其中 *\<日志标记名称\>* 配置中的 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="d4327-116">The mark is the string created by using *\<ServerName\>*<em>*\<DatabaseName\>*_Log\\</em>*\<LogMarkName\>*\_*\<Timestamp\>*.bak, where the *\<Log Mark Name\>* is configured in the SQL Server Agent job.</span></span> <span data-ttu-id="d4327-117">最后一个日志还原到每个数据库时，必须使用此标记。</span><span class="sxs-lookup"><span data-stu-id="d4327-117">This mark must be used when restoring the last log to each database.</span></span>  
  
 <span data-ttu-id="d4327-118">有关详细信息，请参阅 SQL Server 联机丛书中的“事务日志备份”和“相关数据库的备份和恢复”。</span><span class="sxs-lookup"><span data-stu-id="d4327-118">For more information, see "Transaction Log Backups" and "Backup and Recovery of Related Databases" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4327-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4327-119">See Also</span></span>  
 [<span data-ttu-id="d4327-120">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="d4327-120">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)