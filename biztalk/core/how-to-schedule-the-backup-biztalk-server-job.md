---
title: "如何安排备份 BizTalk Server 作业 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, scheduling
- backing up, backup jobs
- scheduling, backup jobs
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6b40ae933874e1c25cb3a93dbbeab514ef5dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-schedule-the-backup-biztalk-server-job"></a>如何安排备份 BizTalk Server 作业
备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为 SQL Server 代理服务计划的作业运行。 如果要修改备份频率，可使用 SQL Server Management Studio 来更改备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业的计划。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-schedule-the-backup-biztalk-server-job-sql-server-2008"></a>若要计划备份 BizTalk Server 作业 (SQL Server 2008)  
  
1.  在包含 BizTalk 管理数据库的计算机，单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**Microsoft SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，指定其中 BizTalk Server 数据库的 SQL server 名称驻留和键入，，然后单击适当的身份验证**连接**。  
  
3.  在对象资源管理器中，双击**SQL Server 代理**，然后单击**作业**。  
  
4.  在细节窗格中，右键单击**备份 BizTalk Server (BizTalkMgmtDb)**，然后单击**属性**。  
  
5.  在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**对话框中，在**选择页**，单击**步骤**。  
  
6.  在**作业步骤列表**，单击**BackupFull**，然后单击**编辑**。  
  
7.  在**作业步骤属性-BackupFull**对话框中，在**命令**框中，编辑该命令，通过更改为所需的间隔，在其中执行完整备份的频率： **'h'**（每小时），**具有**（每天）、 **w** （每周一次），**我**（按月） **y** （每年），然后单击**确定**.  
  
    > [!NOTE]
    >  当备份 BizTalk Server 作业在新周期内第一次运行时，就会执行一次完整备份。  
  
8.  在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**对话框中，在**选择页**，单击**计划**。  
  
9. 在**计划列表**，单击**MarkAndBackupLogSched**，然后单击**编辑**。  
  
10. 在**作业计划属性-MarkAndBackupLogSched**对话框中，在计划类型，选择**重复执行**从下拉列表框中 （如果尚未选择）。  
  
     默认情况下，作业每 15 分钟运行一次。  
  
11. 更新根据需要，计划，然后单击**确定**。  
  
    > [!NOTE]
    >  有关计划 SQL Server 代理作业的详细信息，请参阅"[计划作业](http://go.microsoft.com/fwlink/?LinkId=195887)。"  
  
12. 在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**对话框中，单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [如何为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [如何还原数据库](../core/how-to-restore-your-databases.md)   
 [有关备份和还原的高级的信息](../core/advanced-information-about-backup-and-restore1.md)