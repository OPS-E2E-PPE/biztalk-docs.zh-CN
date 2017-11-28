---
title: "配置备份 BizTalk Server 作业 |Microsoft 文档"
description: 
ms.custom: 
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1afb4f28584d65401220761dcee626fe63f913b
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2017
---
# <a name="configure-the-backup-biztalk-server-job"></a>配置备份 BizTalk Server 作业
安装和配置 BizTalk Server 后，将备份配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业以备份你的数据。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，你可以备份你的数据库和日志文件的 Azure blob 存储帐户。 


## <a name="overview"></a>概述
**备份 BizTalk Server (BizTalkMgmtDb)**作业包括以下步骤：

-   步骤 1 – **Set 压缩选项**： 启用或禁用压缩功能在备份期间

-   步骤 2 – **BackupFull**： 运行完整的 BizTalk Server 数据库的数据库备份

-   步骤 3 – **MarkAndBackUpLog**： 备份 BizTalk Server 数据库的日志

-   步骤 4 –**清除备份历史记录**： 选择的备份历史记录的保留时间

若要配置此作业，你将需要：  
  
-   标识主服务器和目标 SQL 服务器和其他备份选项
  
-   选择一个 Windows 用户帐户，以备份数据库，并创建此帐户的 SQL Server 登录名
  
-   将 SQL Server 登录名映射到 BizTalk Server 数据库中的 BTS_BACKUP_USERS 数据库角色
  
-   确保 MSDTC 服务在所有节点上都处于活动状态。 否则，添加源节点和目标节点之间的链接的服务器失败。
  
## <a name="before-you-begin"></a>开始之前  
  
-   某些配置和备份操作需要 sysadmin SQL Server 角色的成员身份。 若要备份你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请在主服务器是 SQL Server sysadmin 服务器角色的成员的帐户登录。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置将添加 BTS_BACKUP_USERS 数据库角色。 你用于备份数据库的用户帐户不需要可能会涉及到在备份中，主服务器除外的所有 SQL 服务器上的系统管理员 （sysadmin SQL Server 角色） 权限。  
  
-   决定你用于运行帐户的登录你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份。 你可以使用本地帐户，并且可以使用多个帐户。 但通常更简单且更安全，专为此目的创建一个专用的 Windows 域用户帐户。 必须为此用户配置一个 SQL Server 登录帐户，并将此用户映射到所有参与备份过程的 SQL Server 的 SQL Server 登录名，这些 SQL Server 作为主（源）服务器或辅助（目标）服务器。 向此用户分配到 BizTalk BTS_BACKUP_USERS 数据库角色的每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你数据库备份。  
  
-   由于备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业并不删除过期的备份文件，所以需要对这些备份文件进行手动管理，以节省磁盘空间。 为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。 请参阅[SSIS 包](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)来管理这些文件。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会写入跟踪数据直接 BizTalk 跟踪数据库;而是它缓存在 MessageBox 数据库中的数据，然后将其移动到 BizTalk 跟踪数据库。 如果发生 MessageBox 数据丢失，则可能会丢失某些跟踪数据。  
  
## <a name="prerequisites"></a>先决条件  
* 登录到 SQL Server 使用的是 sysadmin SQL Server 角色的成员的帐户。  
  
* 将 SQL Server 代理服务配置为在域帐户（尽管可以使用本地帐户，但推荐使用域帐户）下运行，并且在每个 SQL Server 实例上都有一个对应的用户登录名。  

* 若要使用的 Azure blob 存储帐户，你需要[常规用途存储帐户](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account)，你的 blob 存储帐户中的容器[共享的访问签名](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)(SAS)，和一个[SQL 凭据使用 SAS](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential)。 创建后，具有你 blob 服务终结点的 URL 准备好后，即 https:// 类似*yourstorageaccount*.blob.core.windows.net/*containername*。 

    > [!TIP]
    > 如果你没有现有的 blob 存储帐户配置了 SAS，则[SAS PowerShell 脚本](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)可以创建它，和容器。 [SQL Server 备份到 URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)提供概述和特定的步骤。
  
## <a name="configure-the-job"></a>配置作业  
  
1.  在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**，并连接到你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
2.  展开 **“SQL Server 代理”**，然后展开 **“作业”**。  
  
3.  右键单击 **“备份 BizTalk Server (BizTalkMgmtDb)”** ，然后选择 **“属性”**。 在“作业属性”中，选择 **“步骤”**。  
  
4.  选择**设置压缩选项**单步执行，并选择**编辑**:  

    此步骤将调用`sp_SetBackupCompression`BizTalk 管理数据库 (BizTalkMgmtDb) 上设置的值中存储过程`adm_BackupSettings`表。 存储的过程具有一个参数：  **@bCompression** 。 默认情况下，它设置为**0** （备份压缩处于关闭状态）。 若要应用压缩，请将值更改**1**:  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     选择“确定”。  
  
5.  选择**BackupFull**单步执行，并选择**编辑**。 在**命令**框中，更新参数值：  
  
    1. **频率**： 默认值是**d** （每天）; 这是建议的设置。 其他值包括 **h** （每小时）、 **w** （每周）、 **m** （每月）或 **y** （每年）。  
  
    2. **名称**：默认值为 **BTS**。 该名称用作备份文件名的一部分。  
  
    3. **备份文件的位置**： 替换*\<目标路径 >*替换为计算机和你想要备份的文件夹的完整路径 （的路径必须包括两个单引号） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或 Azure blob 存储帐户的 blob 服务终结点 URL。  

        > [!IMPORTANT]
        > - 如果输入的本地路径，则你必须手动将所有文件都复制到目标系统上的相同文件夹每当备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业创建新的文件。  
        >   
        >      若要使用的远程路径，输入 UNC 共享如\\ \\  *\<ServerName >*\\*\<SharedDrive >*\\，其中 *\<ServerName >*是所需文件，其中的服务器的名称和 *\<SharedDrive >*是共享的驱动器或文件夹的名称。  
        >   
        >      通过网络备份数据可能会受网络问题的影响。 当使用远程位置时，在备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业完成后，请验证备份是否成功。  
        > - 若要避免潜在的数据丢失，请将备份磁盘配置为除数据库数据和日志磁盘以外的磁盘。 这样做是必需的，以便你可以在数据或日志磁盘出现故障时访问备份。  
        > - 当备份到 Azure blob 的帐户中，输入**Blob 服务终结点**URL 和容器名称中中的 blob 服务属性中列出了这些[Azure 门户](https://portal.azure.com)。

    4. 可选。 **完整备份后部分备份失败的强制**(@ForceFullBackupAfterPartialSetFailure): 默认值是**0**。 如果日志备份失败，没有完整备份是已运行，直至到达下一个完整备份的频率间隔。 将替换**1**如果你想完整备份的每次日志备份失败发生时运行。
    
    5. 可选。 **本地时间 （小时） 运行的备份进程**(@BackupHour): 默认值是**NULL**。 备份作业所关联的时区的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和运行在午夜 UTC 时间 (0000)。 如果你想要备份的时区中的特定小时在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上，输入一个整数值介于 0 （午夜） 到 23 （晚上 11 点） 作为本地时间 （小时）。 

    6. 可选。 **使用本地时间**(@UseLocalTime): 指示要使用本地时间的过程。 默认值是**0**，并使用当前 UTC 时间 – GETUTCDATE() – 2007年-05-04 上午 01:34:11.933。 如果设置为**1**，然后，它使用本地时间 – getdate （）-2007年-05-03 18:34:11.933
  
    在下面的示例中，每日备份凌晨 2 点创建并存储在 m:\ 驱动器：  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    '0' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  

    在下面的示例中，每周备份在午夜 UTC 时间，创建并存储在你的 Azure blob 帐户： 

    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'w' /* Frequency */,   
    'BTS' /* Name */,   
    'http://yourstorageaccount.blob.core.windows.net/yourcontainer/' /* location of backup files */,   
    '1' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */
    ```  

     选择“确定”。  
  
6.  选择**MarkAndBackupLog**单步执行，并选择**编辑**。 在**命令**框中，更新参数值：  
  
    1.  **@MarkName**： 这是备份文件的命名约定的一部分： <Server Name>  _<Database Name> **_日志_**< 日志标记名称 >_<Timestamp>  
    
    2.  **@BackupPath**： 完整的目标路径 （包括单引号） 的计算机和文件夹来存储[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库日志，或 Azure blob 存储帐户和容器。 *\<目标路径 >*也可以是本地或另一台服务器的 UNC 路径。  
  
     MarkAndBackupLog 步骤将日志标记为备份，然后对其进行备份。  
  
    > [!IMPORTANT]
    >  若要避免**潜在的数据丢失**和**性能改善**、 *\<目标路径 >*应设置为不同的计算机或硬盘空间不同于用来存储原始的数据库日志。  
  
     选择“确定”。  
  
7.  选择**清除备份历史记录**单步执行，并选择**编辑**。 在**命令**框中，更新参数值：  
  
    1.  **@DaysToKeep**： 默认值是**14 天**。 确定多长时间的备份历史记录的保留`Adm_BackupHistory`表。 定期清除的备份历史记录可帮助维护`Adm_BackupHistory`为合适的大小的表。 
    
    2.  可选。 **@UseLocalTime**： 指示要使用本地时间的过程。 默认值为 0。 它使用当前 UTC 时间 – GETUTCDATE() – 2007年-05-04 上午 01:34:11.933。 如果设置为 1，然后它将使用本地时间 – getdate （）-2007年-05-03 18:34:11.933
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
    ```  
  
    > [!NOTE]
    >  此步骤**不**目标路径中删除备份文件。  
    
     选择 **“确定”** ，然后关闭所有的属性窗口。  
  
8.  可选。 更改备份计划。 请参阅[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。  
  
    > [!NOTE]
    >  第一次配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业时将运行该作业。 默认情况下，在后续运行中，备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业完成的完整备份每天一次，并完成每隔 15 分钟的日志备份。  
  
9. 右键单击**备份 BizTalk Server**作业，并选择**启用**。 状态应更改为 **“成功”**。  

## <a name="execute-backupsetupallprocssql-and-logshippingdestinationlogicsql"></a>执行 Backup_Setup_All_Procs.sql 和 LogShipping_Destination_Logic.sql

**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2 (FP2)**使用中的 Backup_Setup_All_Procs.sql 和 LogShipping_Destination_Logic.sql 脚本`\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`。 

如果已配置你的 BizTalk Server 中备份作业，并且你想要切换到使用 Azure blob （而不是磁盘），则还执行以下： 

1. 在 SQL 服务器上，执行`Backup_Setup_All_Procs.sql`对正在备份的备份 BizTalk Server 作业的所有自定义数据库的脚本。 默认情况下，FP2 自动更新 BizTalk 数据库;它不会更新任何自定义的数据库 (在这些数据库`adm_OtherBackupDatabases`BizTalkMgmtDb 中的表)。

    [返回自定义数据库](how-to-back-up-custom-databases.md)提供了自定义数据库中的详细信息。 

2. **如果你使用[日志传送](log-shipping.md)**，SQL Server 中的目标系统上执行 LogShipping_Destination_Logic.sql 脚本。 如果不使用日志传送，则不会执行此脚本。

    [为日志传送配置目标系统](how-to-configure-the-destination-system-for-log-shipping.md)目标系统上提供更多详细信息。

## <a name="spforcefullbackup-stored-procedure"></a>sp_ForceFullBackup 存储过程  
  
**Sp_ForceFullBackup**存储中的过程**BizTalkMgmtDb**数据库可以用于运行即席数据和日志文件的完整备份。 存储的流程会使用值 1 来更新 adm_ForceFullBackup 表。 下一次备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行作业，会创建完整数据库备份集。  
  
## <a name="next-steps"></a>后续步骤  
 [为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)  
 [Azure 存储帐户](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)  
 [SQL Server 备份到 URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)
