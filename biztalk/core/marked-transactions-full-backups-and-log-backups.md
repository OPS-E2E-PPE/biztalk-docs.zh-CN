---
title: "标记的事务，完整备份，备份和日志备份 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, transaction logs
- backing up, full backups
- transaction logs
- backing up, backup jobs
ms.assetid: a383a16d-1e40-4b0b-a515-f1cb90bfb4d2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c7eab426bfc19c082d8c9651cf4d02eae0075a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="marked-transactions-full-backups-and-log-backups"></a><span data-ttu-id="3e8b1-102">标记的事务、完整备份和日志备份</span><span class="sxs-lookup"><span data-stu-id="3e8b1-102">Marked Transactions, Full Backups, and Log Backups</span></span>
<span data-ttu-id="3e8b1-103">备份 BizTalk Server 作业创建的所有类型的名为的事务与结合使用完整数据库备份和事务日志备份，BizTalk Server 数据库的同步的备份*标记的事务*。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-103">The Backup BizTalk Server Job creates synchronized backups of all BizTalk Server databases by using full database backups and transaction log backups, in conjunction with a type of transaction known as a *marked transaction*.</span></span> <span data-ttu-id="3e8b1-104">标记的事务是在事务中放到事务日志中的所有数据库参与的标记的事务。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-104">Marked transactions are transactions that place a mark into the transaction log of all databases participating in the transaction.</span></span> <span data-ttu-id="3e8b1-105">标记的事务会阻止新的分布式的事务，无法启动，等待当前正在运行要完成，则分布式事务，则会执行放置标记。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-105">The marked transaction blocks new distributed transactions from starting, waits for the distributed transactions that are currently running to complete, and then executes to place the mark.</span></span>  
  
 <span data-ttu-id="3e8b1-106">该标记所表示的所有数据库; 在都是一致的事务点你可以使用标记后续日志备份将数据库还原到该点。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-106">The mark represents a transaction point that is consistent across all databases; you can use the mark with subsequent log backups to restore your databases to that point.</span></span>  
  
 <span data-ttu-id="3e8b1-107">对于每个 BizTalk Server 数据库，备份的 BizTalk Server 作业创建标记的事务日志备份，每次运行，并创建根据你指定的时间段的完整备份。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-107">For each BizTalk Server database, the Backup BizTalk Server job creates a marked transaction log backup every time it runs, and it creates a full backup based on a time period that you specify.</span></span>  
  
## <a name="full-backups"></a><span data-ttu-id="3e8b1-108">完整备份</span><span class="sxs-lookup"><span data-stu-id="3e8b1-108">Full backups</span></span>  
 <span data-ttu-id="3e8b1-109">当你运行备份的 BizTalk Server 作业它运行第一个备份过程中， *BackupFull*，一次每个句点 （非每次该作业运行时）。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-109">When you run the Backup BizTalk Server job it runs the first backup process, *BackupFull*, once every period (not every time the job runs).</span></span> <span data-ttu-id="3e8b1-110">有关如何安排备份 BizTalk Server 作业的详细信息，请参阅[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-110">For more information about how to schedule the Backup BizTalk Server job, see [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
 <span data-ttu-id="3e8b1-111">首次备份的 BizTalk Server 作业运行时在新的期间，它将执行完整备份。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-111">The first time the Backup BizTalk Server job runs during a new period, it performs a full backup.</span></span> <span data-ttu-id="3e8b1-112">例如，如果你计划要运行的作业每隔一小时但配置段为每日备份的 BizTalk Server 作业执行首次运行，且然后每天午夜的完整备份。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-112">For example, if you schedule the job to run every hour but configure the period to be daily, the Backup BizTalk Server job performs a full backup the first time it runs, and then every day at midnight.</span></span>  
  
## <a name="transaction-log-backups"></a><span data-ttu-id="3e8b1-113">事务日志备份</span><span class="sxs-lookup"><span data-stu-id="3e8b1-113">Transaction log backups</span></span>  
 <span data-ttu-id="3e8b1-114">备份 BizTalk Server 作业将执行的第二个过程*MarkAndBackupLog*。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-114">The second process that the Backup BizTalk Server job performs is *MarkAndBackupLog*.</span></span> <span data-ttu-id="3e8b1-115">此过程中所有 BizTalk Server 数据库和每次作业执行时执行事务日志备份都放置标记。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-115">This process places a mark in all BizTalk Server databases and performs a transaction log backup every time the job executes.</span></span>  
  
 <span data-ttu-id="3e8b1-116">标记是通过使用创建的字符串 *\<ServerName >*_*\<DatabaseName >*（_l)\_*\<LogMarkName >*\_ *\<时间戳 >*.bak，其中*\<日志标记名称 >*配置中的 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-116">The mark is the string created by using *\<ServerName>*_*\<DatabaseName>*_Log\_*\<LogMarkName>*\_*\<Timestamp>*.bak, where the *\<Log Mark Name>* is configured in the SQL Server Agent job.</span></span> <span data-ttu-id="3e8b1-117">还原到每个数据库的最新的日志时，必须使用此标记。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-117">This mark must be used when restoring the last log to each database.</span></span>  
  
 <span data-ttu-id="3e8b1-118">有关详细信息，请参阅 SQL Server 联机丛书中的“事务日志备份”和“相关数据库的备份和恢复”。</span><span class="sxs-lookup"><span data-stu-id="3e8b1-118">For more information, see "Transaction Log Backups" and "Backup and Recovery of Related Databases" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e8b1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e8b1-119">See Also</span></span>  
 [<span data-ttu-id="3e8b1-120">有关备份和还原的高级的信息</span><span class="sxs-lookup"><span data-stu-id="3e8b1-120">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)