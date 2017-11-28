---
title: "后配置步骤来优化您的环境 |Microsoft 文档"
description: "任务完成后安装和配置 BizTalk Server 中，包括配置 SQL 代理作业、 安装的 EDI 架构、 创建主机和主机实例以及 BizTalk Server 中的详细信息"
ms.custom: 
ms.prod: biztalk-server
ms.date: 09/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0fef6ea-e7cc-4ea9-936d-5d638bc43feb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad09a989bf3bcf85e41ce8165a9834a22520ba8b
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2017
---
# <a name="post-configuration-steps-to-optimize-your-environment"></a><span data-ttu-id="f89cf-103">用于优化环境的配置后步骤</span><span class="sxs-lookup"><span data-stu-id="f89cf-103">Post-configuration steps to optimize your environment</span></span>
<span data-ttu-id="f89cf-104">配置后步骤可帮助提高性能、维护 BizTalk 环境和安装 EDI 架构。</span><span class="sxs-lookup"><span data-stu-id="f89cf-104">Post-configuration steps to help improve performance, maintain your BizTalk environment, and install the EDI schemas.</span></span>

## <a name="disable-shared-memory-protocol-in-sql-server"></a><span data-ttu-id="f89cf-105">禁用 SQL Server 中的 Shared Memory 协议</span><span class="sxs-lookup"><span data-stu-id="f89cf-105">Disable Shared Memory protocol in SQL Server</span></span>

1. <span data-ttu-id="f89cf-106">打开“SQL Server 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-106">Open **SQL Server Configuration Manager**.</span></span>
2. <span data-ttu-id="f89cf-107">展开“SQL Server 网络配置”，然后选择“MSSQLSERVER 的协议”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-107">Expand **SQL Server Network Configuration**, and select **Protocols for MSSQLSERVER**.</span></span>
3. <span data-ttu-id="f89cf-108">右键单击“共享内存”，然后选择“禁用”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-108">Right-click **Shared Memory**, and select **Disable**.</span></span>
4. <span data-ttu-id="f89cf-109">选择“SQL Server 服务”，右键单击“SQL Server (MSSQLSERVER)”，然后再选择“重启”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-109">Select **SQL Server Services**, right-click **SQL Server (MSSQLServer)**, and select **Restart**.</span></span>
5. <span data-ttu-id="f89cf-110">关闭“SQL Server 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-110">Close **SQL Server Configuration Manager**.</span></span>

## <a name="configure-the-sql-agent-jobs"></a><span data-ttu-id="f89cf-111">配置 SQL 代理作业</span><span class="sxs-lookup"><span data-stu-id="f89cf-111">Configure the SQL Agent jobs</span></span>

1. <span data-ttu-id="f89cf-112">启动 **SQL Server Management Studio**，然后连接到**数据库引擎**。</span><span class="sxs-lookup"><span data-stu-id="f89cf-112">**SQL Server Management Studio**, and connect to **Database Engine**.</span></span>
2. <span data-ttu-id="f89cf-113">展开“SQL Server 代理”，再展开“作业”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-113">Expand **SQL Server Agent**, and expand **Jobs**.</span></span> <span data-ttu-id="f89cf-114">配置下列作业：</span><span class="sxs-lookup"><span data-stu-id="f89cf-114">Configure the following jobs:</span></span>  

    <span data-ttu-id="f89cf-115">作业名称</span><span class="sxs-lookup"><span data-stu-id="f89cf-115">Job Name</span></span>  |<span data-ttu-id="f89cf-116">说明</span><span class="sxs-lookup"><span data-stu-id="f89cf-116">Description</span></span>  |<span data-ttu-id="f89cf-117">为什么需要它</span><span class="sxs-lookup"><span data-stu-id="f89cf-117">Why you need it</span></span>  
    ---------|---------|---------
    <span data-ttu-id="f89cf-118">备份 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f89cf-118">Backup BizTalk Server</span></span> | <span data-ttu-id="f89cf-119">备份 BizTalk Server 数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="f89cf-119">Backs up the BizTalk Server databases and the log files.</span></span> <span data-ttu-id="f89cf-120">在配置该作业时，需要确定频率和文件位置等参数。</span><span class="sxs-lookup"><span data-stu-id="f89cf-120">When configuring the job, you determine parameters like frequency and file location.</span></span><br/><br/><span data-ttu-id="f89cf-121">以下链接介绍了 SQL 代理作业及其参数：</span><span class="sxs-lookup"><span data-stu-id="f89cf-121">The following links describe the SQL Agent job and its parameters:</span></span><br/><br/>[<span data-ttu-id="f89cf-122">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="f89cf-122">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)<br/>[<span data-ttu-id="f89cf-123">如何配置备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="f89cf-123">How to Configure the Backup BizTalk Server Job</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)|<span data-ttu-id="f89cf-124">此 SQL 代理作业还会截断事务日志，这有助于改进性能。</span><span class="sxs-lookup"><span data-stu-id="f89cf-124">This SQL Agent job also truncates the transaction logs, which helps improve performance.</span></span><br/><br/><span data-ttu-id="f89cf-125">作业不会移除或删除备份文件，包括较早的文件。</span><span class="sxs-lookup"><span data-stu-id="f89cf-125">This job does not remove or delete backup files, including older files.</span></span> <span data-ttu-id="f89cf-126">要删除备份文件，请参阅《当备份文件在 Microsoft BizTalk Server 数据库服务器中累积一段时间后，“备份 BizTalk Server”作业失败》。</span><span class="sxs-lookup"><span data-stu-id="f89cf-126">To delete backup files, refer to The "Backup BizTalk Server" job fails when backup files accumulate over time in the Microsoft BizTalk Server database server.</span></span>
    <span data-ttu-id="f89cf-127">DTA 清除和存档</span><span class="sxs-lookup"><span data-stu-id="f89cf-127">DTA Purge and Archive</span></span> |<span data-ttu-id="f89cf-128">截断并存档 BizTalk Server 跟踪数据库 (BizTalkDTADb)。</span><span class="sxs-lookup"><span data-stu-id="f89cf-128">Truncates and archives the BizTalk Server Tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="f89cf-129">在配置该作业时，需要确定已完成实例的保留天数以及所有数据的保留天数等参数。</span><span class="sxs-lookup"><span data-stu-id="f89cf-129">When configuring the job, you determine parameters like how many days to keep completed instances and how many to days to keep all data.</span></span><br/><br/><span data-ttu-id="f89cf-130">以下链接介绍了 SQL 代理作业及其参数：</span><span class="sxs-lookup"><span data-stu-id="f89cf-130">The following links describe the SQL Agent job and its parameters:</span></span> <br/><br/>[<span data-ttu-id="f89cf-131">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="f89cf-131">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)<br/>[<span data-ttu-id="f89cf-132">如何配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="f89cf-132">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)|<span data-ttu-id="f89cf-133">此 SQL 代理作业通过维护跟踪主机和清除跟踪事件直接影响性能。</span><span class="sxs-lookup"><span data-stu-id="f89cf-133">This SQL Agent job directly impacts performance by maintaining the Tracking host and purging tracking events.</span></span>

## <a name="maintain-your-backup-files"></a><span data-ttu-id="f89cf-134">维护备份文件</span><span class="sxs-lookup"><span data-stu-id="f89cf-134">Maintain your backup files</span></span>

<span data-ttu-id="f89cf-135">BizTalk Server 不包括任何会删除备份文件的作业。</span><span class="sxs-lookup"><span data-stu-id="f89cf-135">BizTalk Server does not include any job to delete backup files.</span></span> <span data-ttu-id="f89cf-136">结果是，维护备份文件的方式由用户决定。</span><span class="sxs-lookup"><span data-stu-id="f89cf-136">As a result, how you maintain your backup files is up to you.</span></span> <span data-ttu-id="f89cf-137">许多用户创建 sp_DeleteBackupHistoryAndFiles 存储过程，然后再在备份 BizTalk Server 作业中直接调用此存储过程。</span><span class="sxs-lookup"><span data-stu-id="f89cf-137">Many users create the sp_DeleteBackupHistoryAndFiles stored procedure, and then call this stored procedure directly in the Backup BizTalk Server job.</span></span> <span data-ttu-id="f89cf-138">某些用户会创建维护计划。</span><span class="sxs-lookup"><span data-stu-id="f89cf-138">Some users create a maintenance plan.</span></span> <span data-ttu-id="f89cf-139">由你进行选择。</span><span class="sxs-lookup"><span data-stu-id="f89cf-139">The choice is yours.</span></span> <span data-ttu-id="f89cf-140">本主题列出了这两个选项。</span><span class="sxs-lookup"><span data-stu-id="f89cf-140">This topic lists both options.</span></span>

#### <a name="option-1-create-the-spdeletebackuphistoryandfiles-stored-procedure"></a><span data-ttu-id="f89cf-141">选项 1：创建 sp_DeleteBackupHistoryAndFiles 存储过程</span><span class="sxs-lookup"><span data-stu-id="f89cf-141">Option 1: Create the sp_DeleteBackupHistoryAndFiles stored procedure</span></span>

1. <span data-ttu-id="f89cf-142">在“SQL Server Management Studio”中，选择 BizTalk 管理数据库 (BizTalkMgmtDb)。</span><span class="sxs-lookup"><span data-stu-id="f89cf-142">In SQL Server Management Studio, select the BizTalk Management database (BizTalkMgmtDb).</span></span> 
2. <span data-ttu-id="f89cf-143">选择“新建查询”，然后运行下面的 T-SQL 脚本创建 sp_DeleteBackupHistoryAndFiles 存储过程：</span><span class="sxs-lookup"><span data-stu-id="f89cf-143">Select **New Query**, and run the following T-SQL script to create the sp_DeleteBackupHistoryAndFiles stored procedure:</span></span> 

    ```
    CREATE PROCEDURE [dbo].[sp_DeleteBackupHistoryAndFiles] @DaysToKeep smallint = null
    AS

    BEGIN
    set nocount on
    IF @DaysToKeep IS NULL OR @DaysToKeep \<= 1
    RETURN
    /*
    Only delete full sets
    If a set spans a day in such a way that some items fall into the deleted group and the other does not, do not delete the set
    */

    DECLARE DeleteBackupFiles CURSOR
    FOR SELECT 'del "' + [BackupFileLocation] + '\' + [BackupFileName] + '"' FROM [adm_BackupHistory]
    WHERE  datediff( dd, [BackupDateTime], getdate() ) >= @DaysToKeep
    AND [BackupSetId] NOT IN ( SELECT [BackupSetId] FROM [dbo].[adm_BackupHistory] [h2] WHERE [h2].[BackupSetId] = [BackupSetId] AND datediff( dd, [h2].[BackupDateTime], getdate() ) < @DaysToKeep )
 
    DECLARE @cmd varchar(400)
    OPEN DeleteBackupFiles
    FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    WHILE (@@fetch_status <> -1)
    BEGIN
        IF (@@fetch_status <> -2)
        BEGIN
            EXEC master.dbo.xp_cmdshell @cmd, NO_OUTPUT
            delete from [adm_BackupHistory] WHERE CURRENT OF DeleteBackupFiles
            print @cmd
        END
        FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    END

    CLOSE DeleteBackupFiles
    DEALLOCATE DeleteBackupFiles
    END
    GO
    ```

3. <span data-ttu-id="f89cf-144">打开“备份 BizTalk Server”作业，然后选择“步骤”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-144">Open the Backup BizTalk Server job, and select **Steps**.</span></span>
4. <span data-ttu-id="f89cf-145">编辑“清除备份历史记录”步骤，以便调用新的 *sp_DeleteBackupHistoryAndFiles* 存储过程，而非上一个 *sp_DeleteBackupHistory* 存储过程。</span><span class="sxs-lookup"><span data-stu-id="f89cf-145">Edit the **Clear Backup History** step so that it calls the new *sp_DeleteBackupHistoryAndFiles* stored procedure instead of the previous *sp_DeleteBackupHistory* stored procedure.</span></span>
5. <span data-ttu-id="f89cf-146">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="f89cf-146">Select **OK** to save your changes.</span></span>

#### <a name="option-2-create-a-maintenance-plan"></a><span data-ttu-id="f89cf-147">选项 2：创建维护计划</span><span class="sxs-lookup"><span data-stu-id="f89cf-147">Option 2: Create a maintenance plan</span></span>

1. <span data-ttu-id="f89cf-148">在“SQL Server Management Studio”中，展开“管理”，右键单击“维护计划”，然后选择“维护计划向导”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-148">In SQL Server Management Studio, expand **Management**, right-click **Maintenance Plans**, and select **Maintenance Plan Wizard**.</span></span>
2. <span data-ttu-id="f89cf-149">命名计划（例如，将其命名为“清除备份文件”，然后选择“计划”旁边的“更改”按钮。</span><span class="sxs-lookup"><span data-stu-id="f89cf-149">Name the plan (for example, name it *Purge Backup Files*), and then select the **Change** button next to **Schedule**.</span></span>
3. <span data-ttu-id="f89cf-150">选择备份文件的清除频率。</span><span class="sxs-lookup"><span data-stu-id="f89cf-150">Choose how frequently you want to purge the backup files.</span></span> <span data-ttu-id="f89cf-151">这些设置完全由用户决定。</span><span class="sxs-lookup"><span data-stu-id="f89cf-151">These settings are completely up to you.</span></span> <span data-ttu-id="f89cf-152">选择“确定”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-152">Select **OK**, and then select **Next**.</span></span>
4. <span data-ttu-id="f89cf-153">选择“维护清除任务”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-153">Select **Maintenance Cleanup Task**, and select **Next**.</span></span>
5. <span data-ttu-id="f89cf-154">在“清理任务”窗口中。转到“搜索文件夹并删除文件...”，选择备份文件夹（可能是 f：\BizTalkBackUps），然后输入文件扩展名 **.bak**。</span><span class="sxs-lookup"><span data-stu-id="f89cf-154">In the **Cleanup Task** window, go to **Search folder and delete files...**, select your backup Folder (maybe f:\BizTalkBackUps), and enter **.bak** for the File extension.</span></span> <span data-ttu-id="f89cf-155">还可以选择根据保留时间删除文件。</span><span class="sxs-lookup"><span data-stu-id="f89cf-155">You can also choose to delete files based on their age.</span></span> <span data-ttu-id="f89cf-156">例如，如果想删除早于 3 周的文件，则输入 3。</span><span class="sxs-lookup"><span data-stu-id="f89cf-156">For example, enter 3 if you want to delete files that are older than 3 weeks.</span></span> <span data-ttu-id="f89cf-157">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-157">Select **Next**.</span></span>
6. <span data-ttu-id="f89cf-158">完成向导并输入所需的任何其他信息。</span><span class="sxs-lookup"><span data-stu-id="f89cf-158">Finish going through the wizard and enter any additional information you want.</span></span> <span data-ttu-id="f89cf-159">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-159">Select **Finish**.</span></span>

  
## <a name="install-edi-schemas-and-more-edi-as2-configuration"></a><span data-ttu-id="f89cf-160">安装 EDI 架构和更多 EDI AS2 配置</span><span class="sxs-lookup"><span data-stu-id="f89cf-160">Install EDI schemas and more EDI AS2 configuration</span></span>
 <span data-ttu-id="f89cf-161">EANCOM、EDIFACT、HIPAA 和 X12 架构文件都包括在名为 MicrosoftEdiXSDTemplates.exe 的自解压缩可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="f89cf-161">The EANCOM, EDIFACT, HIPAA, and X12 schema files are included in a self-extracting executable file named  MicrosoftEdiXSDTemplates.exe.</span></span> <span data-ttu-id="f89cf-162">若要创建 EDI 解决方案，请解压缩这些文件，并与项目一起部署。</span><span class="sxs-lookup"><span data-stu-id="f89cf-162">To create EDI solutions, extract these files, and deploy with your projects.</span></span> <span data-ttu-id="f89cf-163">若要安装并解压缩这些文件：</span><span class="sxs-lookup"><span data-stu-id="f89cf-163">To install and extract these files:</span></span>  
  
1.  <span data-ttu-id="f89cf-164">运行 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 安装，然后安装**开发人员工具和 SDK** 组件。</span><span class="sxs-lookup"><span data-stu-id="f89cf-164">Run the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] installation, and install the **Developer Tools and SDK** component.</span></span> <span data-ttu-id="f89cf-165">此组件将 MicrosoftEdiXSDTemplates.exe EDI 架构文件下载到 \XSD_Schema\EDI 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f89cf-165">This component  downloads the MicrosoftEdiXSDTemplates.exe EDI schema file to the \XSD_Schema\EDI folder.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f89cf-166">如果升级 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，则与升级关联的新的 MicrosoftEdiXSDTemplates.exe 文件将替换安装中的 MicrosoftEdiXSDTemplates.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="f89cf-166">If you upgrade [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], the MicrosoftEdiXSDTemplates.exe file in your installation is replaced with the new MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="f89cf-167">如果需要上一个架构，则备份上一个 MicrosoftEdiXSDTemplates.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="f89cf-167">If you need the previous the schemas, then back up the previous MicrosoftEdiXSDTemplates.exe file.</span></span>  
  
    > [!NOTE] 
    > <span data-ttu-id="f89cf-168">如果在将 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 升级到更高版本时对消息架构进行升级，则在使用升级后的架构时可能会遇到问题，或者可能需要执行其他升级步骤。</span><span class="sxs-lookup"><span data-stu-id="f89cf-168">If you upgrade message schemas when you upgrade [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to a later build, you may encounter issues using the updated schemas, or you may have to perform additional updating steps.</span></span> <span data-ttu-id="f89cf-169">请参阅[更新应用程序时的重要注意事项](../core/important-considerations-for-updating-applications.md)中的“更新架构时的注意事项”部分</span><span class="sxs-lookup"><span data-stu-id="f89cf-169">See the "Considerations for updating schemas" section in [Important Considerations for Updating Applications](../core/important-considerations-for-updating-applications.md)</span></span>
  
2.  <span data-ttu-id="f89cf-170">转到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI，然后双击 MicrosoftEdiXSDTemplates.exe。</span><span class="sxs-lookup"><span data-stu-id="f89cf-170">Go  to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI, and double-click MicrosoftEdiXSDTemplates.exe.</span></span>  
  
3.  <span data-ttu-id="f89cf-171">将架构解压缩到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI。</span><span class="sxs-lookup"><span data-stu-id="f89cf-171">Extract the schemas to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI.</span></span> <span data-ttu-id="f89cf-172">解压缩架构时，它们存储在 EANCOM、EDIFACT、HIPAA 和 X12 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f89cf-172">When you extract the schemas, they are stored in EANCOM, EDIFACT, HIPAA, and X12 folders.</span></span>  
  
#### <a name="add-a-reference-to-the-biztalk-server-edi-application"></a><span data-ttu-id="f89cf-173">添加对 BizTalk Server EDI 应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="f89cf-173">Add a reference to the BizTalk Server EDI application</span></span>  
 <span data-ttu-id="f89cf-174">EDI 架构、管道和业务流程都在 **BizTalk EDI 应用程序**中部署。</span><span class="sxs-lookup"><span data-stu-id="f89cf-174">EDI schemas, pipelines, and orchestrations are deployed in the **BizTalk EDI Application**.</span></span> <span data-ttu-id="f89cf-175">若要使用任何其他应用程序作为 EDI 应用程序，则添加对 **BizTalk EDI 应用程序**的引用。</span><span class="sxs-lookup"><span data-stu-id="f89cf-175">To use any other application as an EDI application, add a reference to the **BizTalk EDI Application**.</span></span> <span data-ttu-id="f89cf-176">步骤：</span><span class="sxs-lookup"><span data-stu-id="f89cf-176">Steps:</span></span>  
  
1.  <span data-ttu-id="f89cf-177">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，展开“应用程序”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-177">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand  **Applications**.</span></span> <span data-ttu-id="f89cf-178">右键单击要用于 EDI 的应用程序（例如 *BizTalk 应用程序 1*），选择“添加”，然后选择“引用”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-178">Right-click the application that you want to use for EDI (such as *BizTalk Application 1*), select **Add**, and then select **References**.</span></span>  
  
2.  <span data-ttu-id="f89cf-179">选择“BizTalk EDI 应用程序”，然后选择“确定”以保存更改。</span><span class="sxs-lookup"><span data-stu-id="f89cf-179">Select **BizTalk EDI Application**, and select **OK** to save your changes.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="f89cf-180">若要查看对其他应用程序的引用，右键单击任何应用程序，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-180">To see references to other applications, right-click any application, and select **Properties**.</span></span> <span data-ttu-id="f89cf-181">选择“引用”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-181">Select **References**.</span></span> <span data-ttu-id="f89cf-182">还可以添加新的引用，然后删除现有的引用。</span><span class="sxs-lookup"><span data-stu-id="f89cf-182">You can also add new references, and remove existing references.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89cf-183">请勿将自定义项目添加到 BizTalk EDI 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="f89cf-183">Do not add custom artifacts to the BizTalk EDI Application.</span></span> <span data-ttu-id="f89cf-184">最好是将应用程序保留原样。</span><span class="sxs-lookup"><span data-stu-id="f89cf-184">It's best to leave this application as-is.</span></span>  
  
#### <a name="start-batch-orchestrations"></a><span data-ttu-id="f89cf-185">开始批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="f89cf-185">Start batch orchestrations</span></span>  
 <span data-ttu-id="f89cf-186">若要使参与方能够接收和/或发送 EDI 批，则启动批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="f89cf-186">If you enable a party to receive and/or send EDI batches, then start the batching orchestrations.</span></span> <span data-ttu-id="f89cf-187">这些业务流程不是由安装向导或配置向导启动的。</span><span class="sxs-lookup"><span data-stu-id="f89cf-187">These orchestrations are not started by the installation wizard or the configuration wizard.</span></span> <span data-ttu-id="f89cf-188">步骤：</span><span class="sxs-lookup"><span data-stu-id="f89cf-188">Steps:</span></span>  
  
1.  <span data-ttu-id="f89cf-189">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，展开“BizTalk EDI 应用程序”，然后选择“业务流程”。</span><span class="sxs-lookup"><span data-stu-id="f89cf-189">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk EDI Application**, and select**Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="f89cf-190">右键单击以下每个业务流程，然后选择“开始”：</span><span class="sxs-lookup"><span data-stu-id="f89cf-190">Right-click each of the following orchestrations, and select **Start**:</span></span>  
  
    -   <span data-ttu-id="f89cf-191">Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService（程序集：Microsoft.BizTalk.Edi.BatchingOrchestration.dll）</span><span class="sxs-lookup"><span data-stu-id="f89cf-191">Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService (assembly: Microsoft.BizTalk.Edi.BatchingOrchestration.dll)</span></span>  
  
    -   <span data-ttu-id="f89cf-192">Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService（程序集：Microsoft.BizTalk.Edi.BatchingOrchestration.dll）</span><span class="sxs-lookup"><span data-stu-id="f89cf-192">Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService (assembly: Microsoft.BizTalk.Edi.BatchingOrchestration.dll)</span></span>  
  
    -   <span data-ttu-id="f89cf-193">Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService（程序集：Microsoft.BizTalk.Edi.RoutingOrchestration.dll）</span><span class="sxs-lookup"><span data-stu-id="f89cf-193">Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService (assembly: Microsoft.BizTalk.Edi.RoutingOrchestration.dll)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89cf-194">EDI 批处理业务流程只能在要接收和/或发送 EDI 批的情况下启动。</span><span class="sxs-lookup"><span data-stu-id="f89cf-194">The EDI batching orchestrations should only be started if you receive and/or send EDI batches.</span></span> <span data-ttu-id="f89cf-195">如果在系统不接收或发送 EDI 批的情况下启动该业务流程可能会影响系统性能。</span><span class="sxs-lookup"><span data-stu-id="f89cf-195">Starting them when the system is not receiving or sending EDI batches could affect system performance.</span></span>  
  
#### <a name="migrate-edi-artifacts-from-a-previous-biztalk-version"></a><span data-ttu-id="f89cf-196">将 EDI 项目迁移从以前的 BizTalk 版本</span><span class="sxs-lookup"><span data-stu-id="f89cf-196">Migrate EDI artifacts from a previous BizTalk version</span></span>  
 <span data-ttu-id="f89cf-197">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 及更新版本中已对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中管理贸易合作伙伴的方式进行了更新。</span><span class="sxs-lookup"><span data-stu-id="f89cf-197">The way trading partners are managed in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] was updated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 and newer versions.</span></span> <span data-ttu-id="f89cf-198">在早期版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，仅为贸易合作伙伴创建了参与方，而不为承载 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的合作伙伴创建参与方。</span><span class="sxs-lookup"><span data-stu-id="f89cf-198">In the previous [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versions, a party was created only for the trading partner, and not for the partner hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f89cf-199">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 及更新版本中，必须为所有贸易合作伙伴创建参与方，包括承载 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="f89cf-199">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 and newer, a party must be created for all the trading partners, including the partner hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f89cf-200">在早期版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，以参与方级别定义编码（X12 和 EDIFACT）和传输 (AS2) 协议属性。</span><span class="sxs-lookup"><span data-stu-id="f89cf-200">In previous [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versions, the encoding (X12 and EDIFACT) and transport (AS2) protocol properties are defined at the party level.</span></span> <span data-ttu-id="f89cf-201">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 和更高版本中，通过协议定义这些属性。</span><span class="sxs-lookup"><span data-stu-id="f89cf-201">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 and newer versions, these properties are defined through agreements.</span></span>  
  
 <span data-ttu-id="f89cf-202">为了从早期版本迁移参与方数据，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含了参与方迁移工具。</span><span class="sxs-lookup"><span data-stu-id="f89cf-202">To migrate party data from previous versions, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes a Party Migration Tool.</span></span> <span data-ttu-id="f89cf-203">请考虑以下迁移路径：</span><span class="sxs-lookup"><span data-stu-id="f89cf-203">Consider the following migration paths:</span></span>  
  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f89cf-204"> 版本</span><span class="sxs-lookup"><span data-stu-id="f89cf-204"> Version</span></span>|<span data-ttu-id="f89cf-205">迁移路径</span><span class="sxs-lookup"><span data-stu-id="f89cf-205">Migration Path</span></span>|  
|---------------------------------------------------------------------------------------|--------------------|  
|**[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]**|<span data-ttu-id="f89cf-206">升级到 BizTalk Server 2009。</span><span class="sxs-lookup"><span data-stu-id="f89cf-206">Upgrade to BizTalk Server 2009.</span></span> <span data-ttu-id="f89cf-207">然后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 附带的参与方迁移工具迁移到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2。</span><span class="sxs-lookup"><span data-stu-id="f89cf-207">Then, use the Party Migration Tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 to migrate to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2.</span></span><br /><br /> <span data-ttu-id="f89cf-208">**或者**，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 附带的参与方迁移工具迁移到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010。</span><span class="sxs-lookup"><span data-stu-id="f89cf-208">**Or**, use the Party Migration Tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 to migrate to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010.</span></span> <span data-ttu-id="f89cf-209">然后，升级到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2。</span><span class="sxs-lookup"><span data-stu-id="f89cf-209">Then, upgrade to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2.</span></span>|  
|<span data-ttu-id="f89cf-210">**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009**</span><span class="sxs-lookup"><span data-stu-id="f89cf-210">**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009**</span></span>|<span data-ttu-id="f89cf-211">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 附带的参与方迁移工具直接迁移到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2。</span><span class="sxs-lookup"><span data-stu-id="f89cf-211">Use the Party Migration Tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 to migrate directly to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2.</span></span>|  
|<span data-ttu-id="f89cf-212">**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010**</span><span class="sxs-lookup"><span data-stu-id="f89cf-212">**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010**</span></span>|<span data-ttu-id="f89cf-213">升级到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2。</span><span class="sxs-lookup"><span data-stu-id="f89cf-213">Upgrade to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2.</span></span>|  
  
 <span data-ttu-id="f89cf-214">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 介质的 \PartyMigrationTool 文件夹下提供了参与方迁移工具。</span><span class="sxs-lookup"><span data-stu-id="f89cf-214">The Party Migration Tool is available on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] media under the \PartyMigrationTool folder.</span></span>  

  
## <a name="install-biztalk-health-monitor-bhm"></a><span data-ttu-id="f89cf-215">BizTalk 运行状况监视器 (BHM)</span><span class="sxs-lookup"><span data-stu-id="f89cf-215">Install BizTalk Health Monitor (BHM)</span></span>

<span data-ttu-id="f89cf-216">BizTalk 运行状况监视器提供了仪表板，可创建和查看 MessageBox 查看器报表、创建自定义查询、运行终止符任务、监视多个 BizTalk 环境等。</span><span class="sxs-lookup"><span data-stu-id="f89cf-216">BizTalk Health Monitor provides a dashboard to create and view MessageBox Viewer reports, create custom queries, run Terminator tasks, monitor multiple BizTalk environments, and more.</span></span> <span data-ttu-id="f89cf-217">如果负责 BizTalk 环境，建议安装并使用此工具检查 BizTalk 环境的运行状况，以及对其进行维护。</span><span class="sxs-lookup"><span data-stu-id="f89cf-217">If you are responsible for a BizTalk envrionment, we suggest you install and use this tool to check the health of your BizTalk environment, and also maintain it.</span></span>

<span data-ttu-id="f89cf-218">关键链接：</span><span class="sxs-lookup"><span data-stu-id="f89cf-218">Key links:</span></span>

[<span data-ttu-id="f89cf-219">下载 BHM</span><span class="sxs-lookup"><span data-stu-id="f89cf-219">Download BHM</span></span>](https://www.microsoft.com/download/details.aspx?id=43716)  
[<span data-ttu-id="f89cf-220">安装 BHM</span><span class="sxs-lookup"><span data-stu-id="f89cf-220">Install BHM</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/26466.biztalk-server-how-to-install-the-new-biztalk-health-monitor-snap-in.aspx)  
[<span data-ttu-id="f89cf-221">BHM 官方博客</span><span class="sxs-lookup"><span data-stu-id="f89cf-221">BHM Official Blog</span></span>](https://blogs.msdn.microsoft.com/biztalkhealthmonitor/)

## <a name="create-your-hosts-and-host-instances"></a><span data-ttu-id="f89cf-222">创建主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="f89cf-222">Create your hosts and host instances</span></span>
<span data-ttu-id="f89cf-223">建议将某些关键任务分到不同的主机。</span><span class="sxs-lookup"><span data-stu-id="f89cf-223">It is recommended to separate some key tasks into separate hosts.</span></span> <span data-ttu-id="f89cf-224">例如，始终创建只专用于跟踪的独立主机。</span><span class="sxs-lookup"><span data-stu-id="f89cf-224">For example, always create a separate host that is dedicated to only tracking.</span></span> <span data-ttu-id="f89cf-225">创建另一个主机/主机实例以侧重于接收消息，再创建另一个主机/主机实例用于发送消息，以及另一个用于业务流程的主机/主机实例。</span><span class="sxs-lookup"><span data-stu-id="f89cf-225">Create another host/host instance that focuses on receiving messages, another host/host instance for sending messages, and another host/host instance for orchestration.</span></span> 

<span data-ttu-id="f89cf-226">这一领域有许多相关建议。</span><span class="sxs-lookup"><span data-stu-id="f89cf-226">There are many recommendations in this area.</span></span> <span data-ttu-id="f89cf-227">下面是一些可帮助入门的建议：</span><span class="sxs-lookup"><span data-stu-id="f89cf-227">Here are a few to get you started:</span></span> 

[<span data-ttu-id="f89cf-228">管理 BizTalk 主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="f89cf-228">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)  
[<span data-ttu-id="f89cf-229">为 BizTalk 主机提供高可用性</span><span class="sxs-lookup"><span data-stu-id="f89cf-229">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)  
[<span data-ttu-id="f89cf-230">最佳做法：创建并配置 BizTalk Server 主机和主机</span><span class="sxs-lookup"><span data-stu-id="f89cf-230">Best Practices: Create and Configure BizTalk Server Host and Host</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/19701.biztalk-server-best-practices-create-and-configure-biztalk-server-host-and-host-instances.aspx)  
[<span data-ttu-id="f89cf-231">在同一台计算机上的多个主机中运行业务流程</span><span class="sxs-lookup"><span data-stu-id="f89cf-231">Running Orchestrations in Multiple Hosts on the Same Computer</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/31183.biztalk-server-running-orchestrations-in-multiple-hosts-on-the-same-computer.aspx)  
[<span data-ttu-id="f89cf-232">PowerShell 创建和配置 BizTalk Server 主机、 主机实例和处理程序</span><span class="sxs-lookup"><span data-stu-id="f89cf-232">PowerShell to Create and Configure BizTalk Server Host, Host Instances and Handlers</span></span>](https://gallery.technet.microsoft.com/PowerShell-to-Configure-43d77916)  
<span data-ttu-id="f89cf-233">[BizTalk Server Resources on the TechNet Wiki](http://social.technet.microsoft.com/wiki/contents/articles/2240.biztalk-server-resources-on-the-technet-wiki.aspx)（TechNet Wiki 上的 BizTalk Server 资源）</span><span class="sxs-lookup"><span data-stu-id="f89cf-233">[BizTalk Server Resources on the TechNet Wiki](http://social.technet.microsoft.com/wiki/contents/articles/2240.biztalk-server-resources-on-the-technet-wiki.aspx)</span></span>
