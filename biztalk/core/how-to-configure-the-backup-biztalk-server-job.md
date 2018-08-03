---
title: 配置备份 BizTalk Server 作业 |Microsoft Docs
description: ''
ms.custom: ''
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64a6222ffbabad54d8908a7d8da5517786d9a0cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981086"
---
# <a name="configure-the-backup-biztalk-server-job"></a>配置备份 BizTalk Server 作业
安装和配置 BizTalk Server 后，将备份配置为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业备份你的数据。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，可以备份你的数据库和日志文件到 Azure blob 存储帐户。 


## <a name="overview"></a>概述
**备份 BizTalk Server (BizTalkMgmtDb)** 作业包括以下步骤：

-   步骤 1 –**设置压缩选项**： 启用或禁用备份过程中的压缩

-   步骤 2 – **BackupFull**： 运行完整数据库备份的 BizTalk Server 数据库

-   步骤 3 – **MarkAndBackUpLog**： 备份 BizTalk Server 数据库日志

-   步骤 4 –**清除备份历史记录**： 选择的备份历史记录保留多长

若要配置此作业，将需要：  
  
-   确定主服务器和目标 SQL Server 和其他备份选项
  
-   选择一个 Windows 用户帐户来备份数据库，并创建此帐户的 SQL Server 登录名
  
-   将 SQL Server 登录名映射到 BizTalk Server 数据库中的 BTS_BACKUP_USERS 数据库角色
  
-   确保 MSDTC 服务在所有节点上都处于活动状态。 否则，将添加源节点和目标节点之间的链接的服务器失败。
  
## <a name="before-you-begin"></a>开始之前  
  
- 某些配置和备份操作需要 sysadmin SQL Server 角色的成员身份。 若要备份你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，在主服务器是 SQL Server sysadmin 服务器角色的成员的帐户登录。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置将添加的 BTS_BACKUP_USERS 数据库角色。 您用来备份数据库的用户帐户不需要可能涉及在备份中，主服务器除外的所有 SQL Server 上的系统管理员 （sysadmin SQL Server 角色） 权限。  
  
- 确定哪个登录帐户，你使用运行在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份。 可以使用本地帐户，并且可以使用多个帐户。 但通常更简单且更安全，专门为此目的创建一个专用的 Windows 域用户帐户。 必须为此用户配置一个 SQL Server 登录帐户，并将此用户映射到所有参与备份过程的 SQL Server 的 SQL Server 登录名，这些 SQL Server 作为主（源）服务器或辅助（目标）服务器。 此用户分配 BizTalk BTS_BACKUP_USERS 数据库角色的每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]您备份数据库。  
  
- 由于备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业并不删除过期的备份文件，所以需要对这些备份文件进行手动管理，以节省磁盘空间。 为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。 请参阅[SSIS 包](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)用于管理这些文件。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不直接与 BizTalk 跟踪数据库中; 写入跟踪数据而是其缓存在 MessageBox 数据库中的数据，然后再将其移动到 BizTalk 跟踪数据库。 如果发生 MessageBox 数据丢失，则可能会丢失某些跟踪数据。  
  
## <a name="prerequisites"></a>必要條件  
* 登录到 SQL Server 使用该帐户是 sysadmin SQL Server 角色的成员。  
  
* 将 SQL Server 代理服务配置为在域帐户（尽管可以使用本地帐户，但推荐使用域帐户）下运行，并且在每个 SQL Server 实例上都有一个对应的用户登录名。  

* 若要使用的 Azure blob 存储帐户，需要[常规用途存储帐户](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account)，在 blob 存储帐户中，容器[共享的访问签名](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)(SAS) 和一个[SQL 凭据使用 SAS](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential)。 创建后，有了 blob 服务终结点 URL 准备就绪后，这类似于 https://<em>yourstorageaccount</em>.blob.core.windows.net/*containername*。 

    > [!TIP]
    > 如果你没有现有的 blob 存储帐户配置通过 SAS，然后[SAS PowerShell 脚本](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)可以创建它，并在容器。 [SQL Server 备份到 URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)提供概述和特定步骤。
  
## <a name="configure-the-job"></a>配置作业  
  
1. 在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**，并连接到你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
2. 展开 **“SQL Server 代理”**，然后展开 **“作业”**。  
  
3. 右键单击 **“备份 BizTalk Server (BizTalkMgmtDb)”** ，然后选择 **“属性”**。 在“作业属性”中，选择 **“步骤”**。  
  
4. 选择**设置压缩选项**步骤，，然后选择**编辑**:  

   此步骤将调用`sp_SetBackupCompression`存储过程在 BizTalk 管理数据库 (BizTalkMgmtDb) 上设置值`adm_BackupSettings`表。 存储的过程具有一个参数： <strong>@bCompression</strong>。 默认情况下它设置为**0** （备份压缩处于关闭状态）。 若要应用压缩，将值更改为**1**:  
  
   ```  
   exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
   ```  
  
    选择“确定”。  
  
5. 选择**BackupFull**步骤，，然后选择**编辑**。 在中**命令**框中，更新参数值：  
  
   1. **频率**： 默认值是**d** （每天）; 这是建议的设置。 其他值包括 **h** （每小时）、 **w** （每周）、 **m** （每月）或 **y** （每年）。  
  
   2. **名称**：默认值为 **BTS**。 该名称用作备份文件名的一部分。  
  
   3. **备份文件的位置**： 将 '*\<目标路径\>* 替换为计算机和想要备份文件夹的完整路径（该路径必须包含单引号）[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或 Azure blob 存储帐户的 blob 服务终结点 URL。  

      > [!IMPORTANT]
      > - 如果输入本地路径，则必须将所有文件手动都复制到目标系统上的同一文件夹时备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业创建新文件。  
      > 
      >      若要使用的远程路径，请如输入 UNC 共享\\ \\  *\<ServerName\>*\\*\<SharedDrive\>*  \\，其中*\<ServerName\>* 想文件，其中的服务器的名称和*\<SharedDrive\>* 是共享的驱动器或文件夹的名称。  
      > 
      >      通过网络备份数据可能会受网络问题的影响。 当使用远程位置时，在备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业完成后，请验证备份是否成功。  
      > - 若要避免潜在的数据丢失，请将备份磁盘配置为除数据库数据和日志磁盘以外的磁盘。 这样做是必需的，以便你可以在数据或日志磁盘出现故障时访问备份。  
      > - 当备份到 Azure blob 帐户，输入**Blob 服务终结点**URL 和容器名称中的 blob 服务属性中列出了这些[Azure 门户](https://portal.azure.com)。

   4. 可选。 **部分备份失败后强制完全备份**(@ForceFullBackupAfterPartialSetFailure): 默认值是**0**。 如果日志备份失败，直到到达下一个完整备份频率间隔运行完整备份。 将替换为**1**如果您希望完整备份的日志备份失败时运行。
    
   5. 可选。 **备份过程运行的本地时间**(@BackupHour): 默认值是**NULL**。 备份作业不是与时区的关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和运行在午夜 UTC 时间 (0000) 运行。 如果想要备份的时区中的特定小时在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上，输入一个整数值介于 0 （午夜） 到 23 （晚上 11 点） 作为本地时间 （小时）。 

   6. 可选。 **使用本地时间**(@UseLocalTime): 指示要使用本地时间的过程。 默认值是**0**，并使用当前 UTC 时间 – getutcdate （） – 2007年-05-04 01:34:11.933。 如果设置为**1**，然后，它使用本地时间 – getdate （） – 2007年-05-03 18:34:11.933
  
   在以下示例中，每日备份会在凌晨 2 点创建并存储在 m:\ 驱动器：  
  
   ```  
   exec [dbo].[sp_BackupAllFull_Schedule]   
   'd' /* Frequency */,   
   'BTS' /* Name */,   
   'm:\BizTalkBackups' /* location of backup files */,   
   '0' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
   '2' /* local time hour for the backup process to run */  
   ```  

   在以下示例中，每周备份会在午夜 UTC 时间，创建并存储在 Azure blob 帐户： 

   ```  
   exec [dbo].[sp_BackupAllFull_Schedule]   
   'w' /* Frequency */,   
   'BTS' /* Name */,   
   'http://yourstorageaccount.blob.core.windows.net/yourcontainer/' /* location of backup files */,   
   '1' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */
   ```  

    选择“确定”。  
  
6. 选择**MarkAndBackupLog**步骤，，然后选择**编辑**。 在中**命令**框中，更新参数值：  
  
   1. <strong>@MarkName</strong>： 这是备份文件的命名约定的一部分：\<服务器名称\>\_\<数据库名称\>**\_日志\_** \<日志标记名称\> \_\<时间戳\>  
    
   2. <strong>@BackupPath</strong>： 完整的目标路径 （包括单引号） 的计算机和文件夹以存储[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库日志，或 Azure blob 存储帐户和容器。 *\<目标路径\>* 也可以是本地或另一台服务器的 UNC 路径。  
  
      MarkAndBackupLog 步骤将日志标记为备份，然后对其进行备份。  
  
   > [!IMPORTANT]
   >  若要避免**潜在的数据丢失**和有关**性能改进**，则*\<目标路径\>* 应设置为另一台计算机或硬盘，不同于用于存储原始数据库日志。  
  
    选择“确定”。  
  
7. 选择**清除备份历史记录**步骤，，然后选择**编辑**。 在中**命令**框中，更新参数值：  
  
   1. <strong>@DaysToKeep</strong>： 默认值是**14 天**。 确定多长时间的备份历史记录保留在`Adm_BackupHistory`表。 定期清除备份历史记录有助于保持`Adm_BackupHistory`到适当大小的表。 
    
   2. 可选。 <strong>@UseLocalTime</strong>： 告知要使用本地时间的过程。 默认值为 0。 它使用当前 UTC 时间 – getutcdate （） – 2007年-05-04 01:34:11.933。 如果设置为 1，然后使用本地时间 – getdate （） – 2007年-05-03 18:34:11.933
  
   ```  
   exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
   ```  
  
   > [!NOTE]
   >  此步骤**却不**目标路径中删除备份文件。  
    
    选择 **“确定”** ，然后关闭所有的属性窗口。  
  
8. 可选。 更改备份计划。 请参阅[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。  
  
   > [!NOTE]
   >  第一次配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业时将运行该作业。 默认情况下，在后续运行中，备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业完成一次一天的完整备份和完成每隔 15 分钟的日志备份。  
  
9. 右键单击**备份 BizTalk Server**作业，然后选择**启用**。 状态应更改为 **“成功”**。  

## <a name="execute-backupsetupallprocssql-and-logshippingdestinationlogicsql"></a>执行 Backup_Setup_All_Procs.sql 和 LogShipping_Destination_Logic.sql

**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 功能包 2 (FP2)** 使用中的 Backup_Setup_All_Procs.sql 和 LogShipping_Destination_Logic.sql 脚本`\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`。 

如果已配置备份 BizTalk Server 作业，并且你想要切换到使用 Azure blob （而不是磁盘），则还执行以下操作： 

1. 在 SQL Server 上执行`Backup_Setup_All_Procs.sql`对正在由备份 BizTalk Server 作业备份的所有自定义数据库的脚本。 默认情况下，FP2 自动更新 BizTalk 数据库;它不会更新任何自定义数据库 (在这些数据库`adm_OtherBackupDatabases`BizTalkMgmtDb 中的表)。

    [返回自定义数据库](how-to-back-up-custom-databases.md)提供自定义数据库有关的更多详细信息。 

2. **如果您使用[日志传送](log-shipping.md)**，SQL Server 中的目标系统上执行 LogShipping_Destination_Logic.sql 脚本。 如果不使用日志传送，则不执行此脚本。

    [为使日志传送配置的目标系统](how-to-configure-the-destination-system-for-log-shipping.md)目标系统上提供更多详细信息。

## <a name="spforcefullbackup-stored-procedure"></a>sp_ForceFullBackup 存储过程  
  
**Sp_ForceFullBackup**中存储过程**BizTalkMgmtDb**数据库可用于运行即席数据和日志文件的完整备份。 存储的流程会使用值 1 来更新 adm_ForceFullBackup 表。 下一次备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行作业时，创建完整数据库备份集。  
  
## <a name="next-steps"></a>后续步骤  
 [为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)  
 [Azure 存储帐户](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)  
 [SQL Server 备份到 URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)
