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
# <a name="how-to-configure-the-backup-biztalk-server-job"></a><span data-ttu-id="a67c3-102">如何配置备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="a67c3-102">How to Configure the Backup BizTalk Server Job</span></span>
<span data-ttu-id="a67c3-103">本主题列出配置备份 BizTalk Server 作业所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="a67c3-103">This topic lists the steps necessary to configure the Backup BizTalk Server job.</span></span>  
  
 <span data-ttu-id="a67c3-104">必须先配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业，才能备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a67c3-104">You must configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job before you can back up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a67c3-105">若要配置备份，需要执行下列大部分任务或所有任务：</span><span class="sxs-lookup"><span data-stu-id="a67c3-105">To configure the backup, you need to perform most or all of the following tasks:</span></span>  
  
-   <span data-ttu-id="a67c3-106">编辑 SQL Server 代理 **“备份 BizTalk Server (BizTalkMgmtDb)”** 作业，以标识主 SQL Server 和目标 SQL Server 以及其他备份选项。</span><span class="sxs-lookup"><span data-stu-id="a67c3-106">Edit the SQL Server Agent **Backup BizTalk Server (BizTalkMgmtDb)** job to identify the primary and destination SQL Servers and other backup options.</span></span>  
  
-   <span data-ttu-id="a67c3-107">选择一个 Windows 用户帐户来备份数据库，并为此帐户创建一个 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="a67c3-107">Choose a Windows user account to back up your databases and create a SQL Server login for this account.</span></span>  
  
-   <span data-ttu-id="a67c3-108">将 SQL Server 登录名映射到 BizTalk Server 数据库中的 BTS_BACKUP_USERS 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="a67c3-108">Map SQL Server logins to the BTS_BACKUP_USERS database role in the BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="a67c3-109">确保 MSDTC 服务在所有节点上都处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a67c3-109">Ensure MSDTC service is active on all nodes.</span></span> <span data-ttu-id="a67c3-110">否则，在源节点和目标节点之间添加链接服务器将失败。</span><span class="sxs-lookup"><span data-stu-id="a67c3-110">Else, adding a linked server between the source node and the destination node fails.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="a67c3-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="a67c3-111">Before you begin</span></span>  
  
-   <span data-ttu-id="a67c3-112">特定配置和备份操作，如此项需要具备 sysadmin SQL Server 角色中的成员身份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-112">Certain configuration and backup operations such as this one require membership in the sysadmin SQL Server role.</span></span> <span data-ttu-id="a67c3-113">若要备份你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，你必须登录在主服务器是主服务器上的 SQL Server sysadmin 服务器角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="a67c3-113">To back up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must be logged on at the primary server with an account that is a member of the SQL Server sysadmin Server role on the primary server.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a67c3-114">配置将添加名为 BTS_BACKUP_USERS，以便你用于备份数据库的用户帐户不需要的所有可能会涉及到在备份中，除 SQL 服务器上的系统管理员 （sysadmin SQL Server 角色） 权限的数据库角色主服务器。</span><span class="sxs-lookup"><span data-stu-id="a67c3-114"> configuration adds a database role named BTS_BACKUP_USERS so that the user account you use to back up your databases does not require System Administrator (sysadmin SQL Server role) permissions on all of the SQL Servers that may be involved in a backup, except for the primary server.</span></span>  
  
-   <span data-ttu-id="a67c3-115">你需要决定您用来执行的登录帐户你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-115">You need to decide which login account you use to perform your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backups.</span></span> <span data-ttu-id="a67c3-116">可以使用本地帐户，也可以使用多个帐户，但专门为此用途而创建一个专用 Windows 域用户帐户通常更为简单且更安全。</span><span class="sxs-lookup"><span data-stu-id="a67c3-116">You can use a local account, and you can use more than one account, but it is generally simpler and more secure to create one dedicated Windows domain user account specifically for this purpose.</span></span> <span data-ttu-id="a67c3-117">必须为此用户配置一个 SQL Server 登录帐户，并将此用户映射到所有参与备份过程的 SQL Server 的 SQL Server 登录名，这些 SQL Server 作为主（源）服务器或辅助（目标）服务器。</span><span class="sxs-lookup"><span data-stu-id="a67c3-117">You must configure a SQL Server logon account for this user, and the user must be mapped to a SQL Server login for all of the SQL Servers that participate in the backup process, either as primary (source) or secondary (destination) servers.</span></span> <span data-ttu-id="a67c3-118">向此用户分配到 BizTalk BTS_BACKUP_USERS 数据库角色的每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你数据库备份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-118">Assign this user to the BizTalk BTS_BACKUP_USERS database role for each of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases you back up.</span></span>  
  
-   <span data-ttu-id="a67c3-119">由于备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业并不删除过期的备份文件，所以需要对这些备份文件进行手动管理，以节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="a67c3-119">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job does not delete outdated backup files, so you need to manually manage those backup files to conserve disk space.</span></span> <span data-ttu-id="a67c3-120">为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="a67c3-120">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span> <span data-ttu-id="a67c3-121">"BizTalk 帐单"具有可下载[SSIS 包](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)来管理这些文件。</span><span class="sxs-lookup"><span data-stu-id="a67c3-121">"BizTalk Bill" has downloadable [SSIS packages](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) to manage these files.</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a67c3-122"> 不直接将跟踪数据写到 BizTalk 跟踪数据库中；而是将其缓存在 MessageBox 数据库中，然后再将其移动到 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="a67c3-122"> does not write tracking data directly to the BizTalk Tracking database; rather it caches the data in the MessageBox database and then moves it to the BizTalk Tracking database.</span></span> <span data-ttu-id="a67c3-123">如果发生 MessageBox 数据丢失，则可能会丢失某些跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="a67c3-123">If MessageBox data loss occurs, some tracking data may also be lost.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a67c3-124">先决条件</span><span class="sxs-lookup"><span data-stu-id="a67c3-124">Prerequisites</span></span>  
* <span data-ttu-id="a67c3-125">登录到 SQL Server 使用的是 sysadmin SQL Server 角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="a67c3-125">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
* <span data-ttu-id="a67c3-126">将 SQL Server 代理服务配置为在域帐户（尽管可以使用本地帐户，但推荐使用域帐户）下运行，并且在每个 SQL Server 实例上都有一个对应的用户登录名。</span><span class="sxs-lookup"><span data-stu-id="a67c3-126">Configure the SQL Server Agent service to run under a domain account (recommended, although local accounts can be used), with a mapped user login on each instance of SQL Server.</span></span>  
  
## <a name="configure-the-backup-biztalk-server-job"></a><span data-ttu-id="a67c3-127">配置 BizTalk Server 中备份作业</span><span class="sxs-lookup"><span data-stu-id="a67c3-127">Configure the Backup BizTalk Server job</span></span>  
  
1.  <span data-ttu-id="a67c3-128">在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**，并连接到你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a67c3-128">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="a67c3-129">展开 **“SQL Server 代理”**，然后展开 **“作业”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-129">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="a67c3-130">右键单击 **“备份 BizTalk Server (BizTalkMgmtDb)”** ，然后选择 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-130">Right-click **Backup BizTalk Server (BizTalkMgmtDb)** and select **Properties**.</span></span> <span data-ttu-id="a67c3-131">在“作业属性”中，选择 **“步骤”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-131">In the job properties, select **Steps**.</span></span>  
  
4.  <span data-ttu-id="a67c3-132">选择 **“设置压缩选项”** 步骤，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-132">Select the **Set Compression Option** step and select **Edit**.</span></span> <span data-ttu-id="a67c3-133">在 **“命令”** 框中，将值更改为 1：</span><span class="sxs-lookup"><span data-stu-id="a67c3-133">In the **Command** box, change the value to 1:</span></span>  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     <span data-ttu-id="a67c3-134">选择“确定” 。</span><span class="sxs-lookup"><span data-stu-id="a67c3-134">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="a67c3-135">选择 **“BackupFull”** 步骤，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-135">Select the **BackupFull** step and select **Edit**.</span></span> <span data-ttu-id="a67c3-136">在 **“命令”** 框中，编辑参数值：</span><span class="sxs-lookup"><span data-stu-id="a67c3-136">In the **Command** box, edit the parameter values:</span></span>  
  
    1.  <span data-ttu-id="a67c3-137">**频率**：默认值为 **d** （每日）。</span><span class="sxs-lookup"><span data-stu-id="a67c3-137">**Frequency**: The default is **d** (daily).</span></span> <span data-ttu-id="a67c3-138">建议使用此设置。</span><span class="sxs-lookup"><span data-stu-id="a67c3-138">This is the recommended setting.</span></span> <span data-ttu-id="a67c3-139">其他值包括 **h** （每小时）、 **w** （每周）、 **m** （每月）或 **y** （每年）。</span><span class="sxs-lookup"><span data-stu-id="a67c3-139">Other values include **h** (hourly), **w** (weekly), **m** (monthly), or **y** (yearly).</span></span>  
  
    2.  <span data-ttu-id="a67c3-140">**名称**：默认值为 **BTS**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-140">**Name**: The default is **BTS**.</span></span> <span data-ttu-id="a67c3-141">该名称用作备份文件名的一部分。</span><span class="sxs-lookup"><span data-stu-id="a67c3-141">The name is used as part of the backup file name.</span></span>  
  
    3.  <span data-ttu-id="a67c3-142">**备份文件的位置**： 替换*\<目标路径 >*替换为计算机和你想要备份的文件夹的完整路径 （的路径必须包括两个单引号） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="a67c3-142">**Location of backup files**: Replace '*\<destination path>*' with the full path (the path must include the single quotes) to the computer and folder where you want to back up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
        > [!IMPORTANT]
        >  -   <span data-ttu-id="a67c3-143">如果指定本地路径，则每当备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业创建新文件时，都必须将所有文件手动复制到目标系统上的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a67c3-143">If you specify a local path, then you have to manually copy all the files to the same folder on the destination system whenever the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job creates new files.</span></span>  
        >   
        >      <span data-ttu-id="a67c3-144">若要指定远程路径，输入 UNC 共享如\\ \\  *\<ServerName >*\\*\<SharedDrive >* \\其中 *\<ServerName >*是所需文件，其中的服务器的名称和 *\<SharedDrive >*是共享的驱动器或文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="a67c3-144">To specify a remote path, enter a UNC share such as \\\\*\<ServerName>*\\*\<SharedDrive>*\\, where *\<ServerName>* is the name of the server where you want the files, and *\<SharedDrive>* is name of the shared drive or folder.</span></span>  
        >   
        >      <span data-ttu-id="a67c3-145">通过网络备份数据可能会受网络问题的影响。</span><span class="sxs-lookup"><span data-stu-id="a67c3-145">Backing up data over a network is subject to any network issues.</span></span> <span data-ttu-id="a67c3-146">当使用远程位置时，在备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业完成后，请验证备份是否成功。</span><span class="sxs-lookup"><span data-stu-id="a67c3-146">When using a remote location, verify the backup succeeded when the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job finishes.</span></span>  
        > -   <span data-ttu-id="a67c3-147">若要避免潜在的数据丢失，请将备份磁盘配置为除数据库数据和日志磁盘以外的磁盘。</span><span class="sxs-lookup"><span data-stu-id="a67c3-147">To avoid potential data loss, configure the backup disk to be a different disk than the database data and log disks.</span></span> <span data-ttu-id="a67c3-148">这样做是必需的，以便你可以在数据或日志磁盘出现故障时访问备份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-148">This is necessary so you can access the backups if the data or log disk fails.</span></span>  
  
    4.  <span data-ttu-id="a67c3-149">**部分备份失败后强制执行完整备份**：若未指定，则默认值为 **0** ，这意味着如果日志备份失败，则直至达到下一次完整备份频率间隔时才执行完整备份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-149">**Force full backup after partial backup failures**: The default is **0** when not specified, which means that if a log backup fails, no full backups are done until the next full backup frequency interval is reached.</span></span> <span data-ttu-id="a67c3-150">如果你希望每次在日志备份失败时进行完全备份，请将该值替换为 **1** 。</span><span class="sxs-lookup"><span data-stu-id="a67c3-150">Replace with **1** if you want a full backup to be made whenever a log backup failure occurs.</span></span>  
  
    5.  <span data-ttu-id="a67c3-151">**本地时间 （小时） 运行的备份进程**： 默认值为 NULL 时未指定，这意味着该备份作业未与关联的时区[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，因此在午夜 UTC 运行时间 (0000)。</span><span class="sxs-lookup"><span data-stu-id="a67c3-151">**Local time hour for the backup process to run**: The default is NULL when not specified, which means that backup job is not associated with the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and therefore runs at midnight UTC time (0000).</span></span> <span data-ttu-id="a67c3-152">如果你想要备份的时间区域中某特定小时数在运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上，输入一个整数值介于 0 （午夜） 到 23 （晚上 11 点） 作为本地时间小时**BackupHour**参数。</span><span class="sxs-lookup"><span data-stu-id="a67c3-152">If you want to backup to run at a particular hour in the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, enter an integer value from 0 (midnight) to 23 (11 PM) as the local time hour for the **BackupHour** parameter.</span></span>  
  
     <span data-ttu-id="a67c3-153">在下面的示例中，在凌晨两点创建每日备份，并将其存储在 m:\ 驱动器中：</span><span class="sxs-lookup"><span data-stu-id="a67c3-153">In the following example, daily backups are created at 2am and stored in the m:\ drive:</span></span>  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    0 /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  
  
     <span data-ttu-id="a67c3-154">选择“确定” 。</span><span class="sxs-lookup"><span data-stu-id="a67c3-154">Select **OK**.</span></span>  
  
6.  <span data-ttu-id="a67c3-155">选择 **“MarkAndBackupLog”** 步骤，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-155">Select the **MarkAndBackupLog** step and select **Edit**.</span></span> <span data-ttu-id="a67c3-156">在**命令**框中，替换*\<目标路径 >*替换为的完整路径 （包括单引号）计算机和要存储的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库日志。</span><span class="sxs-lookup"><span data-stu-id="a67c3-156">In the **Command** box, replace **'***\<destination path>***'** with the full path (including single quotes) to the computer and folder where you want to store the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database logs.</span></span> <span data-ttu-id="a67c3-157">*\<目标路径 >*可能是本地或另一台服务器的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="a67c3-157">The *\<destination path>* may be local or a UNC path to another server.</span></span>  
  
     <span data-ttu-id="a67c3-158">MarkAndBackupLog 步骤将日志标记为备份，然后对其进行备份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-158">The MarkAndBackupLog step marks the logs for backup, and then backs them up.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a67c3-159">若要避免潜在的数据丢失， *\<目标路径 >*应指定要存储数据库日志不同于原始的数据库日志的计算机的计算机。</span><span class="sxs-lookup"><span data-stu-id="a67c3-159">To avoid potential data loss, the *\<destination path>* should specify a computer to store the database logs that is different from the computer with the original database logs.</span></span>  
  
     <span data-ttu-id="a67c3-160">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="a67c3-160">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="a67c3-161">选择 **“清除备份历史记录”** 步骤，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-161">Select the **Clear Backup History** step and select **Edit**.</span></span> <span data-ttu-id="a67c3-162">在**命令**框中，更改**DaysToKeep =***\<数 >*到你想要保留的备份历史记录的天数：</span><span class="sxs-lookup"><span data-stu-id="a67c3-162">In the **Command** box, change **DaysToKeep=***\<number>* to the number of days you want to keep the backup history:</span></span>  
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a67c3-163">**DaysToKeep** 参数指定备份历史记录在 Adm_BackupHistory 表中保留的时长。</span><span class="sxs-lookup"><span data-stu-id="a67c3-163">The **DaysToKeep** parameter specifies how long the backup history is kept in the Adm_BackupHistory table.</span></span> <span data-ttu-id="a67c3-164">定期清除备份历史记录有助于使 Adm_BackupHistory 表保持适当的大小。</span><span class="sxs-lookup"><span data-stu-id="a67c3-164">Periodically clearing the backup history helps to maintain the Adm_BackupHistory table at an appropriate size.</span></span> <span data-ttu-id="a67c3-165">**DaysToKeep** 参数的默认值为 14 天。</span><span class="sxs-lookup"><span data-stu-id="a67c3-165">The default value for the **DaysToKeep** parameter is 14 days.</span></span>  
  
     <span data-ttu-id="a67c3-166">选择 **“确定”** ，然后关闭所有的属性窗口。</span><span class="sxs-lookup"><span data-stu-id="a67c3-166">Select **OK** and close all property windows.</span></span>  
  
8.  <span data-ttu-id="a67c3-167">可选。</span><span class="sxs-lookup"><span data-stu-id="a67c3-167">Optional.</span></span> <span data-ttu-id="a67c3-168">更改备份计划。</span><span class="sxs-lookup"><span data-stu-id="a67c3-168">Change the backup schedule.</span></span> <span data-ttu-id="a67c3-169">请参阅 [如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="a67c3-169">See [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a67c3-170">第一次配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业时将运行该作业。</span><span class="sxs-lookup"><span data-stu-id="a67c3-170">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs the first time you configure it.</span></span> <span data-ttu-id="a67c3-171">默认情况下，在以后的运行中，备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业每天执行一次完整备份，每 15 分钟执行一次日志备份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-171">By default, on subsequent runs, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job performs a full backup once a day and performs log backups every 15 minutes.</span></span>  
  
9. <span data-ttu-id="a67c3-172">右键单击 **“备份 BizTalk Server”** 作业，然后选择 **“启用”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-172">Right-click the **Backup BizTalk Server** job and select **Enable**.</span></span> <span data-ttu-id="a67c3-173">状态应更改为 **“成功”**。</span><span class="sxs-lookup"><span data-stu-id="a67c3-173">The status should change to **Success**.</span></span>  
  
## <a name="spforcefullbackup-stored-procedure"></a><span data-ttu-id="a67c3-174">sp_ForceFullBackup 存储过程</span><span class="sxs-lookup"><span data-stu-id="a67c3-174">sp_ForceFullBackup stored procedure</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a67c3-175">BizTalkMgmtDb 数据库中的 sp_ForceFullBackup 存储过程可用于帮助对数据和日志文件执行临时完整备份。</span><span class="sxs-lookup"><span data-stu-id="a67c3-175">The sp_ForceFullBackup stored procedure in the BizTalkMgmtDb database can be used to help perform an ad-hoc full backup of the data and log files.</span></span> <span data-ttu-id="a67c3-176">存储的流程会使用值 1 来更新 adm_ForceFullBackup 表。</span><span class="sxs-lookup"><span data-stu-id="a67c3-176">The stored procedure updates the adm_ForceFullBackup table with a value 1.</span></span> <span data-ttu-id="a67c3-177">下一次备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行作业，会创建完整数据库备份集。</span><span class="sxs-lookup"><span data-stu-id="a67c3-177">The next time the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job is ran, a full database backup set is created.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a67c3-178">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a67c3-178">Next Steps</span></span>  
 [<span data-ttu-id="a67c3-179">如何为日志传送配置的目标系统</span><span class="sxs-lookup"><span data-stu-id="a67c3-179">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="a67c3-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a67c3-180">See Also</span></span>  
 [<span data-ttu-id="a67c3-181">如何安排备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="a67c3-181">How to Schedule the Backup BizTalk Server Job</span></span>](../core/how-to-schedule-the-backup-biztalk-server-job.md)