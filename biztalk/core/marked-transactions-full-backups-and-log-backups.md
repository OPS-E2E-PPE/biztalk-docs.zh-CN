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
ms.openlocfilehash: f6359031b4e05f737c8b209b94ae8f8967939a68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380052"
---
# <a name="marked-transactions-full-backups-and-log-backups"></a>标记的事务、完整备份和日志备份
备份 BizTalk Server 作业创建的所有 BizTalk Server 数据库使用完整数据库备份和事务日志备份，以及一种称为事务中的同步的备份*标记的事务*。 标记的事务是在事务中放置到的参与的所有数据库的事务日志标记的事务。 标记的事务阻止启动新的分布式的事务，等待当前正在运行才能完成，则分布式事务，然后执行以放置标记。  
  
 该标记所表示的事务点是一致的跨所有数据库;可用于标记和后续日志备份将数据库还原到该点。  
  
 对于每个 BizTalk Server 数据库，备份 BizTalk Server 作业在每次运行，并创建根据你指定的时间段的完整备份创建标记的事务日志备份。  
  
## <a name="full-backups"></a>完整备份  
 在运行备份 BizTalk Server 作业时运行第一个备份过程中， *BackupFull*，一次每个句点 （非每次作业运行时）。 有关如何安排备份 BizTalk Server 作业的详细信息，请参阅[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。  
  
 首次备份 BizTalk Server 作业运行时在新的期间，它将执行完整备份。 例如，如果您计划要运行的作业每隔一小时但配置段要备份 BizTalk Server 作业每天执行首次运行，且然后每天午夜的完整备份。  
  
## <a name="transaction-log-backups"></a>事务日志备份  
 备份 BizTalk Server 作业将执行的第二个过程*MarkAndBackupLog*。 此过程将标记置于在所有 BizTalk Server 数据库和每次作业执行时执行事务日志备份。  
  
 标记，通过使用创建的字符串 *\<ServerName\>*<em>*\<DatabaseName\>*（_l)\\</em>   *\<LogMarkName\>*\_*\<时间戳\>*.bak，其中 *\<日志标记名称\>* 配置中的 SQL Server 代理作业。 最后一个日志还原到每个数据库时，必须使用此标记。  
  
 有关详细信息，请参阅"事务日志备份"和"备份和恢复相关数据库的"SQL Server 联机丛书中。  
  
## <a name="see-also"></a>请参阅  
 [有关备份和还原的高级信息](../core/advanced-information-about-backup-and-restore1.md)