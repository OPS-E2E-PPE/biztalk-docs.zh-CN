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
# <a name="marked-transactions-full-backups-and-log-backups"></a>标记的事务、完整备份和日志备份
备份 BizTalk Server 作业创建的所有类型的名为的事务与结合使用完整数据库备份和事务日志备份，BizTalk Server 数据库的同步的备份*标记的事务*。 标记的事务是在事务中放到事务日志中的所有数据库参与的标记的事务。 标记的事务会阻止新的分布式的事务，无法启动，等待当前正在运行要完成，则分布式事务，则会执行放置标记。  
  
 该标记所表示的所有数据库; 在都是一致的事务点你可以使用标记后续日志备份将数据库还原到该点。  
  
 对于每个 BizTalk Server 数据库，备份的 BizTalk Server 作业创建标记的事务日志备份，每次运行，并创建根据你指定的时间段的完整备份。  
  
## <a name="full-backups"></a>完整备份  
 当你运行备份的 BizTalk Server 作业它运行第一个备份过程中， *BackupFull*，一次每个句点 （非每次该作业运行时）。 有关如何安排备份 BizTalk Server 作业的详细信息，请参阅[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。  
  
 首次备份的 BizTalk Server 作业运行时在新的期间，它将执行完整备份。 例如，如果你计划要运行的作业每隔一小时但配置段为每日备份的 BizTalk Server 作业执行首次运行，且然后每天午夜的完整备份。  
  
## <a name="transaction-log-backups"></a>事务日志备份  
 备份 BizTalk Server 作业将执行的第二个过程*MarkAndBackupLog*。 此过程中所有 BizTalk Server 数据库和每次作业执行时执行事务日志备份都放置标记。  
  
 标记是通过使用创建的字符串 *\<ServerName >*_*\<DatabaseName >*（_l)\_*\<LogMarkName >*\_ *\<时间戳 >*.bak，其中*\<日志标记名称 >*配置中的 SQL Server 代理作业。 还原到每个数据库的最新的日志时，必须使用此标记。  
  
 有关详细信息，请参阅 SQL Server 联机丛书中的“事务日志备份”和“相关数据库的备份和恢复”。  
  
## <a name="see-also"></a>另请参阅  
 [有关备份和还原的高级的信息](../core/advanced-information-about-backup-and-restore1.md)