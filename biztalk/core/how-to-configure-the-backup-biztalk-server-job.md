---
title: "配置备份 BizTalk Server 作业 |Microsoft 文档"
ms.custom: 
ms.date: 11/02/2017
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
ms.openlocfilehash: 67765cfacc7753d649c14677c5399e9c2c7b1e39
ms.sourcegitcommit: 6095645d541bf84f39ff5f342f782284c22e875b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2017
---
# <a name="configure-the-backup-biztalk-server-job"></a><span data-ttu-id="06ca6-102">配置备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="06ca6-102">Configure the Backup BizTalk Server Job</span></span>
<span data-ttu-id="06ca6-103">列出配置 BizTalk Server 中备份作业所必需的步骤。</span><span class="sxs-lookup"><span data-stu-id="06ca6-103">Lists the steps necessary to configure the Backup BizTalk Server job.</span></span>  

## <a name="overview"></a><span data-ttu-id="06ca6-104">概述</span><span class="sxs-lookup"><span data-stu-id="06ca6-104">Overview</span></span>
<span data-ttu-id="06ca6-105">安装和配置 BizTalk Server 后，将备份配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业以备份你的数据。</span><span class="sxs-lookup"><span data-stu-id="06ca6-105">After you install and configure BizTalk Server, configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job to back up your data.</span></span> <span data-ttu-id="06ca6-106">**备份 BizTalk Server (BizTalkMgmtDb)**作业包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="06ca6-106">The **Backup BizTalk Server (BizTalkMgmtDb)** job includes the following steps:</span></span>

-   <span data-ttu-id="06ca6-107">步骤 1 – **Set 压缩选项**： 启用或禁用压缩功能在备份期间</span><span class="sxs-lookup"><span data-stu-id="06ca6-107">Step 1 – **Set Compression Option**: Enable or disable compression during backup</span></span>

-   <span data-ttu-id="06ca6-108">步骤 2 – **BackupFull**： 运行完整的 BizTalk Server 数据库的数据库备份</span><span class="sxs-lookup"><span data-stu-id="06ca6-108">Step 2 – **BackupFull**: Runs full database backups of the BizTalk Server databases</span></span>

-   <span data-ttu-id="06ca6-109">步骤 3 – **MarkAndBackUpLog**： 备份 BizTalk Server 数据库的日志</span><span class="sxs-lookup"><span data-stu-id="06ca6-109">Step 3 – **MarkAndBackUpLog**: Backs up the BizTalk Server database logs</span></span>

-   <span data-ttu-id="06ca6-110">步骤 4 –**清除备份历史记录**： 选择的备份历史记录的保留时间</span><span class="sxs-lookup"><span data-stu-id="06ca6-110">Step 4 – **Clear Backup History**: Choose how long the backup history is kept</span></span>

<span data-ttu-id="06ca6-111">若要配置此作业，你将需要：</span><span class="sxs-lookup"><span data-stu-id="06ca6-111">To configure this job, you'll need to:</span></span>  
  
-   <span data-ttu-id="06ca6-112">标识主服务器和目标 SQL 服务器和其他备份选项</span><span class="sxs-lookup"><span data-stu-id="06ca6-112">Identify the primary and destination SQL Servers and other backup options</span></span>
  
-   <span data-ttu-id="06ca6-113">选择一个 Windows 用户帐户来备份数据库，并为此帐户创建一个 SQL Server 登录名</span><span class="sxs-lookup"><span data-stu-id="06ca6-113">Choose a Windows user account to back up your databases and create a SQL Server login for this account</span></span>
  
-   <span data-ttu-id="06ca6-114">将 SQL Server 登录名映射到 BizTalk Server 数据库中的 BTS_BACKUP_USERS 数据库角色</span><span class="sxs-lookup"><span data-stu-id="06ca6-114">Map SQL Server logins to the BTS_BACKUP_USERS database role in the BizTalk Server databases</span></span>
  
-   <span data-ttu-id="06ca6-115">确保 MSDTC 服务在所有节点上都处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="06ca6-115">Ensure MSDTC service is active on all nodes.</span></span> <span data-ttu-id="06ca6-116">否则，添加源节点和目标节点之间的链接的服务器失败</span><span class="sxs-lookup"><span data-stu-id="06ca6-116">Else, adding a linked server between the source node and the destination node fails</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="06ca6-117">开始之前</span><span class="sxs-lookup"><span data-stu-id="06ca6-117">Before you begin</span></span>  
  
-   <span data-ttu-id="06ca6-118">某些配置和备份操作需要 sysadmin SQL Server 角色的成员身份。</span><span class="sxs-lookup"><span data-stu-id="06ca6-118">Certain configuration and backup operations require membership in the sysadmin SQL Server role.</span></span> <span data-ttu-id="06ca6-119">若要备份你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，你必须登录主服务器是 SQL Server sysadmin 服务器角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="06ca6-119">To back up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must be signed in the primary server with an account that is a member of the SQL Server sysadmin Server role.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="06ca6-120">配置将添加 BTS_BACKUP_USERS 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="06ca6-120"> configuration adds the BTS_BACKUP_USERS database role.</span></span> <span data-ttu-id="06ca6-121">你用于备份数据库的用户帐户不需要可能会涉及到在备份中，主服务器除外的所有 SQL 服务器上的系统管理员 （sysadmin SQL Server 角色） 权限。</span><span class="sxs-lookup"><span data-stu-id="06ca6-121">The user account you use to back up your databases does not require System Administrator (sysadmin SQL Server role) permissions on all the SQL Servers that may be involved in a backup, except for the primary server.</span></span>  
  
-   <span data-ttu-id="06ca6-122">决定你用于运行帐户的登录你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份。</span><span class="sxs-lookup"><span data-stu-id="06ca6-122">Decide which sign in account you use to run your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backups.</span></span> <span data-ttu-id="06ca6-123">可以使用本地帐户，也可以使用多个帐户，但专门为此用途而创建一个专用 Windows 域用户帐户通常更为简单且更安全。</span><span class="sxs-lookup"><span data-stu-id="06ca6-123">You can use a local account, and you can use more than one account, but it is generally simpler and more secure to create one dedicated Windows domain user account specifically for this purpose.</span></span> <span data-ttu-id="06ca6-124">必须为此用户配置一个 SQL Server 登录帐户，并将此用户映射到所有参与备份过程的 SQL Server 的 SQL Server 登录名，这些 SQL Server 作为主（源）服务器或辅助（目标）服务器。</span><span class="sxs-lookup"><span data-stu-id="06ca6-124">You must configure a SQL Server logon account for this user, and the user must be mapped to a SQL Server login for all of the SQL Servers that participate in the backup process, either as primary (source) or secondary (destination) servers.</span></span> <span data-ttu-id="06ca6-125">向此用户分配到 BizTalk BTS_BACKUP_USERS 数据库角色的每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你数据库备份。</span><span class="sxs-lookup"><span data-stu-id="06ca6-125">Assign this user to the BizTalk BTS_BACKUP_USERS database role for each of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases you back up.</span></span>  
  
-   <span data-ttu-id="06ca6-126">由于备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业并不删除过期的备份文件，所以需要对这些备份文件进行手动管理，以节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="06ca6-126">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job does not delete outdated backup files, so you need to manually manage those backup files to conserve disk space.</span></span> <span data-ttu-id="06ca6-127">为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="06ca6-127">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span> <span data-ttu-id="06ca6-128">请参阅[SSIS 包](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)来管理这些文件。</span><span class="sxs-lookup"><span data-stu-id="06ca6-128">See the [SSIS packages](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) to manage these files.</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="06ca6-129">不会写入跟踪数据直接 BizTalk 跟踪数据库;而是它缓存在 MessageBox 数据库中的数据，然后将其移动到 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="06ca6-129"> does not write tracking data directly to the BizTalk Tracking database; rather it caches the data in the MessageBox database, and then moves it to the BizTalk Tracking database.</span></span> <span data-ttu-id="06ca6-130">如果发生 MessageBox 数据丢失，则可能会丢失某些跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="06ca6-130">If MessageBox data loss occurs, some tracking data may also be lost.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="06ca6-131">先决条件</span><span class="sxs-lookup"><span data-stu-id="06ca6-131">Prerequisites</span></span>  
* <span data-ttu-id="06ca6-132">登录到 SQL Server 使用的是 sysadmin SQL Server 角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="06ca6-132">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
* <span data-ttu-id="06ca6-133">将 SQL Server 代理服务配置为在域帐户（尽管可以使用本地帐户，但推荐使用域帐户）下运行，并且在每个 SQL Server 实例上都有一个对应的用户登录名。</span><span class="sxs-lookup"><span data-stu-id="06ca6-133">Configure the SQL Server Agent service to run under a domain account (recommended, although local accounts can be used), with a mapped user login on each instance of SQL Server.</span></span>  
  
## <a name="configure-the-job"></a><span data-ttu-id="06ca6-134">配置作业</span><span class="sxs-lookup"><span data-stu-id="06ca6-134">Configure the job</span></span>  
  
1.  <span data-ttu-id="06ca6-135">在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**，并连接到你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="06ca6-135">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="06ca6-136">展开 **“SQL Server 代理”**，然后展开 **“作业”**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-136">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="06ca6-137">右键单击 **“备份 BizTalk Server (BizTalkMgmtDb)”** ，然后选择 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-137">Right-click **Backup BizTalk Server (BizTalkMgmtDb)** and select **Properties**.</span></span> <span data-ttu-id="06ca6-138">在“作业属性”中，选择 **“步骤”**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-138">In the job properties, select **Steps**.</span></span>  
  
4.  <span data-ttu-id="06ca6-139">选择**设置压缩选项**单步执行，并选择**编辑**:</span><span class="sxs-lookup"><span data-stu-id="06ca6-139">Select the **Set Compression Option** step, and select **Edit**:</span></span>  

    <span data-ttu-id="06ca6-140">此步骤将调用`sp_SetBackupCompression`BizTalk 管理数据库 (BizTalkMgmtDb) 上设置的值中存储过程`adm_BackupSettings`表。</span><span class="sxs-lookup"><span data-stu-id="06ca6-140">This step calls the `sp_SetBackupCompression` stored procedure in the BizTalk management database (BizTalkMgmtDb) to set the value on the `adm_BackupSettings` table.</span></span> <span data-ttu-id="06ca6-141">存储的过程具有一个参数：  **@bCompression** 。</span><span class="sxs-lookup"><span data-stu-id="06ca6-141">The stored procedure has one parameter: **@bCompression**.</span></span> <span data-ttu-id="06ca6-142">默认情况下，它设置为**0** （备份压缩处于关闭状态）。</span><span class="sxs-lookup"><span data-stu-id="06ca6-142">By default, it is set to **0** (backup compression is off).</span></span> <span data-ttu-id="06ca6-143">若要应用压缩，请将值更改**1**:</span><span class="sxs-lookup"><span data-stu-id="06ca6-143">To apply compression, change the value to **1**:</span></span>  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     <span data-ttu-id="06ca6-144">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="06ca6-144">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="06ca6-145">选择**BackupFull**单步执行，并选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-145">Select the **BackupFull** step, and select **Edit**.</span></span> <span data-ttu-id="06ca6-146">在**命令**框中，更新参数值：</span><span class="sxs-lookup"><span data-stu-id="06ca6-146">In the **Command** box, update the parameter values:</span></span>  
  
    1. <span data-ttu-id="06ca6-147">**频率**： 默认值是**d** （每天）; 这是建议的设置。</span><span class="sxs-lookup"><span data-stu-id="06ca6-147">**Frequency**: The default is **d** (daily); which is the recommended setting.</span></span> <span data-ttu-id="06ca6-148">其他值包括 **h** （每小时）、 **w** （每周）、 **m** （每月）或 **y** （每年）。</span><span class="sxs-lookup"><span data-stu-id="06ca6-148">Other values include **h** (hourly), **w** (weekly), **m** (monthly), or **y** (yearly).</span></span>  
  
    2. <span data-ttu-id="06ca6-149">**名称**：默认值为 **BTS**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-149">**Name**: The default is **BTS**.</span></span> <span data-ttu-id="06ca6-150">该名称用作备份文件名的一部分。</span><span class="sxs-lookup"><span data-stu-id="06ca6-150">The name is used as part of the backup file name.</span></span>  
  
    3. <span data-ttu-id="06ca6-151">**备份文件的位置**： 替换*\<目标路径 >*替换为计算机和你想要备份的文件夹的完整路径 （的路径必须包括两个单引号） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="06ca6-151">**Location of backup files**: Replace '*\<destination path>*' with the full path (the path must include the single quotes) to the computer and folder where you want to back up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  

        > [!IMPORTANT]
        >  - <span data-ttu-id="06ca6-152">如果输入的本地路径，则你必须手动将所有文件都复制到目标系统上的相同文件夹每当备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业创建新的文件。</span><span class="sxs-lookup"><span data-stu-id="06ca6-152">If you enter a local path, then you have to manually copy all the files to the same folder on the destination system whenever the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job creates new files.</span></span>  
        >   
        >      <span data-ttu-id="06ca6-153">若要指定远程路径，输入 UNC 共享如\\ \\  *\<ServerName >*\\*\<SharedDrive >* \\其中 *\<ServerName >*是所需文件，其中的服务器的名称和 *\<SharedDrive >*是共享的驱动器或文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="06ca6-153">To specify a remote path, enter a UNC share such as \\\\*\<ServerName>*\\*\<SharedDrive>*\\, where *\<ServerName>* is the name of the server where you want the files, and *\<SharedDrive>* is name of the shared drive or folder.</span></span>  
        >   
        >      <span data-ttu-id="06ca6-154">通过网络备份数据可能会受网络问题的影响。</span><span class="sxs-lookup"><span data-stu-id="06ca6-154">Backing up data over a network is subject to any network issues.</span></span> <span data-ttu-id="06ca6-155">当使用远程位置时，在备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业完成后，请验证备份是否成功。</span><span class="sxs-lookup"><span data-stu-id="06ca6-155">When using a remote location, verify the backup succeeded when the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job finishes.</span></span>  
        > - <span data-ttu-id="06ca6-156">若要避免潜在的数据丢失，请将备份磁盘配置为除数据库数据和日志磁盘以外的磁盘。</span><span class="sxs-lookup"><span data-stu-id="06ca6-156">To avoid potential data loss, configure the backup disk to be a different disk than the database data and log disks.</span></span> <span data-ttu-id="06ca6-157">这样做是必需的，以便你可以在数据或日志磁盘出现故障时访问备份。</span><span class="sxs-lookup"><span data-stu-id="06ca6-157">This is necessary so you can access the backups if the data or log disk fails.</span></span>  

    4. <span data-ttu-id="06ca6-158">可选。</span><span class="sxs-lookup"><span data-stu-id="06ca6-158">Optional.</span></span> <span data-ttu-id="06ca6-159">**完整备份后部分备份失败的强制**(@ForceFullBackupAfterPartialSetFailure): 默认值是**0**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-159">**Force full backup after partial backup failures** (@ForceFullBackupAfterPartialSetFailure): The default is **0**.</span></span> <span data-ttu-id="06ca6-160">如果日志备份失败，没有完整备份是已运行，直至到达下一个完整备份的频率间隔。</span><span class="sxs-lookup"><span data-stu-id="06ca6-160">If a log backup fails, no full backups are ran until the next full backup frequency interval is reached.</span></span> <span data-ttu-id="06ca6-161">将替换**1**如果你想完整备份的每次日志备份失败发生时运行。</span><span class="sxs-lookup"><span data-stu-id="06ca6-161">Replace with **1** if you want a full backup ran whenever a log backup failure occurs.</span></span>
    
    5. <span data-ttu-id="06ca6-162">可选。</span><span class="sxs-lookup"><span data-stu-id="06ca6-162">Optional.</span></span> <span data-ttu-id="06ca6-163">**本地时间 （小时） 运行的备份进程**： 默认值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="06ca6-163">**Local time hour for the backup process to run**: The default is NULL.</span></span> <span data-ttu-id="06ca6-164">备份作业所关联的时区的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和运行在午夜 UTC 时间 (0000)。</span><span class="sxs-lookup"><span data-stu-id="06ca6-164">The backup job is not associated with the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, and runs at midnight UTC time (0000).</span></span> <span data-ttu-id="06ca6-165">如果你想要备份的时区中的特定小时在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上，输入一个整数值介于 0 （午夜） 到 23 （晚上 11 点） 作为本地时间小时**BackupHour**参数。</span><span class="sxs-lookup"><span data-stu-id="06ca6-165">If you want to backup at a specific hour in the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, enter an integer value from 0 (midnight) to 23 (11 PM) as the local time hour for the **BackupHour** parameter.</span></span> 

    6. <span data-ttu-id="06ca6-166">可选。</span><span class="sxs-lookup"><span data-stu-id="06ca6-166">Optional.</span></span> <span data-ttu-id="06ca6-167">**使用本地时间**(@UseLocalTime): 指示要使用本地时间的过程。</span><span class="sxs-lookup"><span data-stu-id="06ca6-167">**Use local time** (@UseLocalTime): Tells the procedure to use local time.</span></span> <span data-ttu-id="06ca6-168">默认值为 0，并使用当前 UTC 时间 – GETUTCDATE() – 2007年-05-04 上午 01:34:11.933。</span><span class="sxs-lookup"><span data-stu-id="06ca6-168">The default value is 0, and uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="06ca6-169">如果设置为 1，然后它将使用本地时间 – getdate （）-2007年-05-03 18:34:11.933</span><span class="sxs-lookup"><span data-stu-id="06ca6-169">If set to 1, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
    <span data-ttu-id="06ca6-170">在下面的示例中，每日备份凌晨 2 点创建并存储在 m:\ 驱动器：</span><span class="sxs-lookup"><span data-stu-id="06ca6-170">In the following example, daily backups are created at 2am, and stored in the m:\ drive:</span></span>  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    0 /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  
  
     <span data-ttu-id="06ca6-171">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="06ca6-171">Select **OK**.</span></span>  
  
6.  <span data-ttu-id="06ca6-172">选择**MarkAndBackupLog**单步执行，并选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-172">Select the **MarkAndBackupLog** step, and select **Edit**.</span></span> <span data-ttu-id="06ca6-173">在**命令**框中，更新参数值：</span><span class="sxs-lookup"><span data-stu-id="06ca6-173">In the **Command** box, update the parameter values:</span></span>  
  
    1.  <span data-ttu-id="06ca6-174">**@MarkName**： 这是备份文件的命名约定的一部分： <Server Name>  _<Database Name> **_日志_**< 日志标记名称 >_<Timestamp></span><span class="sxs-lookup"><span data-stu-id="06ca6-174">**@MarkName**: This is part of the naming convention for backup files: <Server Name>_<Database Name>**_Log_**< Log Mark Name >_<Timestamp></span></span>  
    
    2.  <span data-ttu-id="06ca6-175">**@BackupPath**： 完整的目标路径 （包括单引号） 的计算机和要存储的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库日志。</span><span class="sxs-lookup"><span data-stu-id="06ca6-175">**@BackupPath**: Full destination path (including single quotes) to the computer and folder where you want to store the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database logs.</span></span> <span data-ttu-id="06ca6-176">*\<目标路径 >*可能是本地或另一台服务器的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="06ca6-176">The *\<destination path>* may be local or a UNC path to another server.</span></span>  
  
     <span data-ttu-id="06ca6-177">MarkAndBackupLog 步骤将日志标记为备份，然后对其进行备份。</span><span class="sxs-lookup"><span data-stu-id="06ca6-177">The MarkAndBackupLog step marks the logs for backup, and then backs them up.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="06ca6-178">若要避免**潜在的数据丢失**和**性能改善**、 *\<目标路径 >*应设置为不同的计算机或硬盘空间不同于用来存储原始的数据库日志。</span><span class="sxs-lookup"><span data-stu-id="06ca6-178">To avoid **potential data loss** and for **performance improvement**, the *\<destination path>* should be set to a different computer, or hard drive, different from what is used to store the original database logs.</span></span>  
  
     <span data-ttu-id="06ca6-179">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="06ca6-179">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="06ca6-180">选择**清除备份历史记录**单步执行，并选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-180">Select the **Clear Backup History** step, and select **Edit**.</span></span> <span data-ttu-id="06ca6-181">在**命令**框中，更新参数值：</span><span class="sxs-lookup"><span data-stu-id="06ca6-181">In the **Command** box, update the parameter values:</span></span>  
  
    1.  <span data-ttu-id="06ca6-182">**@DaysToKeep**： 默认值是**14 天**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-182">**@DaysToKeep**: Default value is **14 days**.</span></span> <span data-ttu-id="06ca6-183">确定多长时间的备份历史记录的保留`Adm_BackupHistory`表。</span><span class="sxs-lookup"><span data-stu-id="06ca6-183">Determines how long the backup history is kept in the `Adm_BackupHistory` table.</span></span> <span data-ttu-id="06ca6-184">定期清除的备份历史记录可帮助维护`Adm_BackupHistory`为合适的大小的表。</span><span class="sxs-lookup"><span data-stu-id="06ca6-184">Periodically clearing the backup history helps maintain the `Adm_BackupHistory` table to an appropriate size.</span></span> 
    
    2.  <span data-ttu-id="06ca6-185">可选。</span><span class="sxs-lookup"><span data-stu-id="06ca6-185">Optional.</span></span> <span data-ttu-id="06ca6-186">**@UseLocalTime**： 指示要使用本地时间的过程。</span><span class="sxs-lookup"><span data-stu-id="06ca6-186">**@UseLocalTime**: Tells the procedure to use local time.</span></span> <span data-ttu-id="06ca6-187">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="06ca6-187">The default value is 0.</span></span> <span data-ttu-id="06ca6-188">它使用当前 UTC 时间 – GETUTCDATE() – 2007年-05-04 上午 01:34:11.933。</span><span class="sxs-lookup"><span data-stu-id="06ca6-188">It uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="06ca6-189">如果设置为 1，然后它将使用本地时间 – getdate （）-2007年-05-03 18:34:11.933</span><span class="sxs-lookup"><span data-stu-id="06ca6-189">If set to 1, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="06ca6-190">此步骤**不**目标路径中删除备份文件。</span><span class="sxs-lookup"><span data-stu-id="06ca6-190">This step **does not** delete backup files from the destination path.</span></span>  
    
     <span data-ttu-id="06ca6-191">选择 **“确定”** ，然后关闭所有的属性窗口。</span><span class="sxs-lookup"><span data-stu-id="06ca6-191">Select **OK** and close all property windows.</span></span>  
  
8.  <span data-ttu-id="06ca6-192">可选。</span><span class="sxs-lookup"><span data-stu-id="06ca6-192">Optional.</span></span> <span data-ttu-id="06ca6-193">更改备份计划。</span><span class="sxs-lookup"><span data-stu-id="06ca6-193">Change the backup schedule.</span></span> <span data-ttu-id="06ca6-194">请参阅[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="06ca6-194">See [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06ca6-195">第一次配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业时将运行该作业。</span><span class="sxs-lookup"><span data-stu-id="06ca6-195">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs the first time you configure it.</span></span> <span data-ttu-id="06ca6-196">默认情况下，在后续运行中，备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业完成的完整备份每天一次，并完成每隔 15 分钟的日志备份。</span><span class="sxs-lookup"><span data-stu-id="06ca6-196">By default, on subsequent runs, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job completes a full backup once a day, and completes log backups every 15 minutes.</span></span>  
  
9. <span data-ttu-id="06ca6-197">右键单击**备份 BizTalk Server**作业，并选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-197">Right-click the **Backup BizTalk Server** job, and select **Enable**.</span></span> <span data-ttu-id="06ca6-198">状态应更改为 **“成功”**。</span><span class="sxs-lookup"><span data-stu-id="06ca6-198">The status should change to **Success**.</span></span>  
  
## <a name="spforcefullbackup-stored-procedure"></a><span data-ttu-id="06ca6-199">sp_ForceFullBackup 存储过程</span><span class="sxs-lookup"><span data-stu-id="06ca6-199">sp_ForceFullBackup stored procedure</span></span>  
  
<span data-ttu-id="06ca6-200">**Sp_ForceFullBackup**存储中的过程**BizTalkMgmtDb**数据库可以用于运行即席数据和日志文件的完整备份。</span><span class="sxs-lookup"><span data-stu-id="06ca6-200">The **sp_ForceFullBackup** stored procedure in the **BizTalkMgmtDb** database can be used to run an ad-hoc full backup of the data and log files.</span></span> <span data-ttu-id="06ca6-201">存储的流程会使用值 1 来更新 adm_ForceFullBackup 表。</span><span class="sxs-lookup"><span data-stu-id="06ca6-201">The stored procedure updates the adm_ForceFullBackup table with a value 1.</span></span> <span data-ttu-id="06ca6-202">下一次备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行作业，会创建完整数据库备份集。</span><span class="sxs-lookup"><span data-stu-id="06ca6-202">The next time the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job is ran, a full database backup set is created.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="06ca6-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="06ca6-203">Next Steps</span></span>  
 <span data-ttu-id="06ca6-204">[如何为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="06ca6-204">[How to Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 [<span data-ttu-id="06ca6-205">如何安排备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="06ca6-205">How to Schedule the Backup BizTalk Server Job</span></span>](../core/how-to-schedule-the-backup-biztalk-server-job.md)
