---
title: "如何配置备份 BizTalk Server 作业 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, backing up
- backing up, Tracking database
- backing up, user accounts
- backing up, MessageBox database
- databases, backing up
- MessageBox database, backing up
- backing up, databases
- backing up, prerequisites
- configuring, backup jobs
- backing up, warnings
- backing up, backup jobs
- user accounts, backing up
- backing up, configuring
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 488e76c3d29c58107e85ad58ed4fad50de671315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-backup-biztalk-server-job"></a>如何配置备份 BizTalk Server 作业
本主题列出配置备份 BizTalk Server 作业所需的步骤。  
  
 必须先配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业，才能备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 若要配置备份，需要执行下列大部分任务或所有任务：  
  
-   编辑 SQL Server 代理 **“备份 BizTalk Server (BizTalkMgmtDb)”** 作业，以标识主 SQL Server 和目标 SQL Server 以及其他备份选项。  
  
-   选择一个 Windows 用户帐户来备份数据库，并为此帐户创建一个 SQL Server 登录名。  
  
-   将 SQL Server 登录名映射到 BizTalk Server 数据库中的 BTS_BACKUP_USERS 数据库角色。  
  
-   确保 MSDTC 服务在所有节点上都处于活动状态。 否则，在源节点和目标节点之间添加链接服务器将失败。  
  
## <a name="before-you-begin"></a>开始之前  
  
-   特定配置和备份操作，如此项需要具备 sysadmin SQL Server 角色中的成员身份。 若要备份你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，你必须登录在主服务器是主服务器上的 SQL Server sysadmin 服务器角色的成员的帐户。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置将添加名为 BTS_BACKUP_USERS，以便你用于备份数据库的用户帐户不需要的所有可能会涉及到在备份中，除 SQL 服务器上的系统管理员 （sysadmin SQL Server 角色） 权限的数据库角色主服务器。  
  
-   你需要决定您用来执行的登录帐户你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份。 可以使用本地帐户，也可以使用多个帐户，但专门为此用途而创建一个专用 Windows 域用户帐户通常更为简单且更安全。 必须为此用户配置一个 SQL Server 登录帐户，并将此用户映射到所有参与备份过程的 SQL Server 的 SQL Server 登录名，这些 SQL Server 作为主（源）服务器或辅助（目标）服务器。 向此用户分配到 BizTalk BTS_BACKUP_USERS 数据库角色的每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你数据库备份。  
  
-   由于备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业并不删除过期的备份文件，所以需要对这些备份文件进行手动管理，以节省磁盘空间。 为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。 "BizTalk 帐单"具有可下载[SSIS 包](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)来管理这些文件。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不直接将跟踪数据写到 BizTalk 跟踪数据库中；而是将其缓存在 MessageBox 数据库中，然后再将其移动到 BizTalk 跟踪数据库中。 如果发生 MessageBox 数据丢失，则可能会丢失某些跟踪数据。  
  
## <a name="prerequisites"></a>先决条件  
* 登录到 SQL Server 使用的是 sysadmin SQL Server 角色的成员的帐户。  
  
* 将 SQL Server 代理服务配置为在域帐户（尽管可以使用本地帐户，但推荐使用域帐户）下运行，并且在每个 SQL Server 实例上都有一个对应的用户登录名。  
  
## <a name="configure-the-backup-biztalk-server-job"></a>配置 BizTalk Server 中备份作业  
  
1.  在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**，并连接到你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
2.  展开 **“SQL Server 代理”**，然后展开 **“作业”**。  
  
3.  右键单击 **“备份 BizTalk Server (BizTalkMgmtDb)”** ，然后选择 **“属性”**。 在“作业属性”中，选择 **“步骤”**。  
  
4.  选择 **“设置压缩选项”** 步骤，然后选择 **“编辑”**。 在 **“命令”** 框中，将值更改为 1：  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     选择“确定” 。  
  
5.  选择 **“BackupFull”** 步骤，然后选择 **“编辑”**。 在 **“命令”** 框中，编辑参数值：  
  
    1.  **频率**：默认值为 **d** （每日）。 建议使用此设置。 其他值包括 **h** （每小时）、 **w** （每周）、 **m** （每月）或 **y** （每年）。  
  
    2.  **名称**：默认值为 **BTS**。 该名称用作备份文件名的一部分。  
  
    3.  **备份文件的位置**： 替换*\<目标路径 >*替换为计算机和你想要备份的文件夹的完整路径 （的路径必须包括两个单引号） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
        > [!IMPORTANT]
        >  -   如果指定本地路径，则每当备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业创建新文件时，都必须将所有文件手动复制到目标系统上的同一文件夹中。  
        >   
        >      若要指定远程路径，输入 UNC 共享如\\ \\  *\<ServerName >*\\*\<SharedDrive >* \\其中 *\<ServerName >*是所需文件，其中的服务器的名称和 *\<SharedDrive >*是共享的驱动器或文件夹的名称。  
        >   
        >      通过网络备份数据可能会受网络问题的影响。 当使用远程位置时，在备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业完成后，请验证备份是否成功。  
        > -   若要避免潜在的数据丢失，请将备份磁盘配置为除数据库数据和日志磁盘以外的磁盘。 这样做是必需的，以便你可以在数据或日志磁盘出现故障时访问备份。  
  
    4.  **部分备份失败后强制执行完整备份**：若未指定，则默认值为 **0** ，这意味着如果日志备份失败，则直至达到下一次完整备份频率间隔时才执行完整备份。 如果你希望每次在日志备份失败时进行完全备份，请将该值替换为 **1** 。  
  
    5.  **本地时间 （小时） 运行的备份进程**： 默认值为 NULL 时未指定，这意味着该备份作业未与关联的时区[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，因此在午夜 UTC 运行时间 (0000)。 如果你想要备份的时间区域中某特定小时数在运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上，输入一个整数值介于 0 （午夜） 到 23 （晚上 11 点） 作为本地时间小时**BackupHour**参数。  
  
     在下面的示例中，在凌晨两点创建每日备份，并将其存储在 m:\ 驱动器中：  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    0 /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  
  
     选择“确定” 。  
  
6.  选择 **“MarkAndBackupLog”** 步骤，然后选择 **“编辑”**。 在**命令**框中，替换*\<目标路径 >*替换为的完整路径 （包括单引号）计算机和要存储的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库日志。 *\<目标路径 >*可能是本地或另一台服务器的 UNC 路径。  
  
     MarkAndBackupLog 步骤将日志标记为备份，然后对其进行备份。  
  
    > [!IMPORTANT]
    >  若要避免潜在的数据丢失， *\<目标路径 >*应指定要存储数据库日志不同于原始的数据库日志的计算机的计算机。  
  
     选择“确定”。  
  
7.  选择 **“清除备份历史记录”** 步骤，然后选择 **“编辑”**。 在**命令**框中，更改**DaysToKeep =***\<数 >*到你想要保留的备份历史记录的天数：  
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14  
    ```  
  
    > [!NOTE]
    >  **DaysToKeep** 参数指定备份历史记录在 Adm_BackupHistory 表中保留的时长。 定期清除备份历史记录有助于使 Adm_BackupHistory 表保持适当的大小。 **DaysToKeep** 参数的默认值为 14 天。  
  
     选择 **“确定”** ，然后关闭所有的属性窗口。  
  
8.  可选。 更改备份计划。 请参阅 [如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。  
  
    > [!NOTE]
    >  第一次配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业时将运行该作业。 默认情况下，在以后的运行中，备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业每天执行一次完整备份，每 15 分钟执行一次日志备份。  
  
9. 右键单击 **“备份 BizTalk Server”** 作业，然后选择 **“启用”**。 状态应更改为 **“成功”**。  
  
## <a name="spforcefullbackup-stored-procedure"></a>sp_ForceFullBackup 存储过程  
  
> [!NOTE]
>  BizTalkMgmtDb 数据库中的 sp_ForceFullBackup 存储过程可用于帮助对数据和日志文件执行临时完整备份。 存储的流程会使用值 1 来更新 adm_ForceFullBackup 表。 下一次备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行作业，会创建完整数据库备份集。  
  
## <a name="next-steps"></a>后续步骤  
 [如何为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)  
  
## <a name="see-also"></a>另请参阅  
 [如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)