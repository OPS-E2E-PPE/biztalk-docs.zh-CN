---
title: 还原数据库 |Microsoft Docs
description: 请参阅还原 BizTalk Server 数据库，包括使用 SQL 代理作业，并运行 UpdateDatabase.vbs 和 UpdateRegistry.vbs 脚本的步骤。 另请参阅要执行的操作后数据库被还原，包括更新 BizTalk 管理控制台中的 SQL Server 实例名称。
ms.custom: ''
ms.date: 04/22/19
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3213b22cb82d807b392e43d09b64a24cbc519cf
ms.sourcegitcommit: 5c3994bc9ccd688f3df74e2a49f84ada4baf5dfd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "60164507"
---
# <a name="restore-your-databases---biztalk-server"></a><span data-ttu-id="728df-104">还原数据库的 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="728df-104">Restore your databases - BizTalk Server</span></span>
<span data-ttu-id="728df-105">必须将所有数据库还原到相同的标记，以确保各个数据库间的事务状态一致。</span><span class="sxs-lookup"><span data-stu-id="728df-105">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="728df-106">请参见 [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md)。</span><span class="sxs-lookup"><span data-stu-id="728df-106">See [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
 <span data-ttu-id="728df-107">如果目标系统中只有一个服务器，请确保还原了所有日志备份集（除了最新日志备份集以外）。</span><span class="sxs-lookup"><span data-stu-id="728df-107">If there is only one server in the destination system, make sure that all of the log backup sets (except for the most recent set) have been restored.</span></span> <span data-ttu-id="728df-108">请参见 [Viewing the History of Restored Backups](../core/viewing-the-history-of-restored-backups.md)。</span><span class="sxs-lookup"><span data-stu-id="728df-108">See [Viewing the History of Restored Backups](../core/viewing-the-history-of-restored-backups.md).</span></span> <span data-ttu-id="728df-109">如果没有还原所有日志备份集，并且当前没有运行还原作业，请运行还原作业（必要时，请手动运行）。</span><span class="sxs-lookup"><span data-stu-id="728df-109">If all the log backup sets have not been restored, and the restore job is not currently running, run the restore job (manually if necessary).</span></span> <span data-ttu-id="728df-110">如果存在尚未完成的可还原备份集，则作业将处理它们，直到所有备份集全部还原为止。</span><span class="sxs-lookup"><span data-stu-id="728df-110">If there are outstanding backup sets that can be restored, the job processes them until they are all restored.</span></span>  
  
 <span data-ttu-id="728df-111">如果目标系统中有多个服务器，则必须将所有服务器还原到相同的备份集。</span><span class="sxs-lookup"><span data-stu-id="728df-111">If there are multiple servers in the destination system, all servers must be restored to the same backup set.</span></span> <span data-ttu-id="728df-112">查看每个服务器的还原历史记录，确保所有服务器上还原的最新日志备份集都是相同的。</span><span class="sxs-lookup"><span data-stu-id="728df-112">View the restore history on each server and make sure that the most recent log backup set restored is the same on all servers.</span></span> <span data-ttu-id="728df-113">如果不同，则必须在需要还原最新日志备份集的每个服务器上手动运行还原作业。</span><span class="sxs-lookup"><span data-stu-id="728df-113">If it is not, you must manually run the restore job on each server that needs the most recent log backup set restored.</span></span>  
  
 <span data-ttu-id="728df-114">当所有的服务器都还原为相同的备份集后，最终的备份集可以手动还原。</span><span class="sxs-lookup"><span data-stu-id="728df-114">After all of the servers are on the same backup set, the final set can be manually restored.</span></span>  
  
 <span data-ttu-id="728df-115">adm_BackupHistory 表是记录源系统日志传送过程历史记录的核心。</span><span class="sxs-lookup"><span data-stu-id="728df-115">The adm_BackupHistory table is the central history point for the log shipping process for the source system.</span></span> <span data-ttu-id="728df-116">所有执行的备份工作都记录到此表中。</span><span class="sxs-lookup"><span data-stu-id="728df-116">All backup work performed is recorded to this table.</span></span> <span data-ttu-id="728df-117">目标系统中的所有服务器都从此表读取信息，以获取执行其还原工作所需的信息。</span><span class="sxs-lookup"><span data-stu-id="728df-117">All servers in your destination system read from this table to receive the information needed to perform their restore work.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="728df-118">开始之前</span><span class="sxs-lookup"><span data-stu-id="728df-118">Before you begin</span></span>

- <span data-ttu-id="728df-119">如果从备份还原 BAM 主导入数据库，则还应该使用该 BAM 主导入数据库备份之前的备份来还原 BAM 存档数据库、BAM 星型架构数据库和 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="728df-119">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span> <span data-ttu-id="728df-120">请参见 [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="728df-120">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
- <span data-ttu-id="728df-121">如果移动完整或日志备份源数据库从备份 BizTalk Server 作业放置它们的位置，则应通过设置更新该数据库在目标系统上 bts_LogShippingDatabases 表中的相关的行LogFileLocation 或 DBFileLocation 到其中的目标系统应读取完整/日志备份文件的新位置。</span><span class="sxs-lookup"><span data-stu-id="728df-121">If you move the full or log backups for a source database from the location in which the Backup BizTalk Server job put them, you should update the associated row for that database in the bts_LogShippingDatabases table on the destination system by setting the LogFileLocation or DBFileLocation to the new location where the destination system should read the full/log backup files.</span></span> <span data-ttu-id="728df-122">运行 bts_ConfigureBtsLogShipping 存储过程时，将填充此表。</span><span class="sxs-lookup"><span data-stu-id="728df-122">This table is populated when you run the bts_ConfigureBtsLogShipping stored procedure.</span></span> <span data-ttu-id="728df-123">默认情况下，这些列设置为空，这表明目标系统应该从 adm_BackupHistory 表中存储的位置上读取这些备份文件。</span><span class="sxs-lookup"><span data-stu-id="728df-123">By default, these columns are set to null, which indicates that the destination system should read the backup files from the location stored in the adm_BackupHistory table.</span></span>  
- <span data-ttu-id="728df-124">请总是在某个安全位置保留备份文件的一个副本。</span><span class="sxs-lookup"><span data-stu-id="728df-124">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="728df-125">即使你进行了日志备份，在没有备份文件的情况下也无法还原数据库。</span><span class="sxs-lookup"><span data-stu-id="728df-125">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="728df-126">先决条件</span><span class="sxs-lookup"><span data-stu-id="728df-126">Prerequisites</span></span>  
<span data-ttu-id="728df-127">登录到 SQL Server 使用该帐户是 sysadmin SQL Server 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="728df-127">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
## <a name="restore-your-databases"></a><span data-ttu-id="728df-128">还原数据库</span><span class="sxs-lookup"><span data-stu-id="728df-128">Restore your databases</span></span>  
  
1. <span data-ttu-id="728df-129">在目标系统上，打开**SQL Server Management Studio**，并连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="728df-129">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span>  
  
2. <span data-ttu-id="728df-130">展开 **“SQL Server 代理”**，然后展开 **“作业”**。</span><span class="sxs-lookup"><span data-stu-id="728df-130">Expand **SQL Server Agent**, and expand **Jobs**.</span></span> <span data-ttu-id="728df-131">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="728df-131">Do the following:</span></span>  
  
   1. <span data-ttu-id="728df-132">右键单击 **“BTS 日志传送 - 获取备份历史记录”** 作业，然后选择 **“禁用”**。</span><span class="sxs-lookup"><span data-stu-id="728df-132">Right-click the **BTS Log Shipping - Get Backup History** job and select **Disable**.</span></span> <span data-ttu-id="728df-133">状态将更改为“成功”。</span><span class="sxs-lookup"><span data-stu-id="728df-133">The status changes to Success.</span></span>  
  
   2. <span data-ttu-id="728df-134">右键单击 **“BTS 日志传送 - 还原数据库”** 作业，然后选择 **“禁用”**。</span><span class="sxs-lookup"><span data-stu-id="728df-134">Right-click the **BTS Log Shipping - Restore Databases** job and select **Disable**.</span></span> <span data-ttu-id="728df-135">状态将更改为“成功”。</span><span class="sxs-lookup"><span data-stu-id="728df-135">The status changes to Success.</span></span>  
  
   3. <span data-ttu-id="728df-136">右键单击 **“BTS 日志传送 - 还原到标记”** ，然后选择 **“作业开始步骤”**。</span><span class="sxs-lookup"><span data-stu-id="728df-136">Right-click the **BTS Log Shipping - Restore To Mark** and select **Start Job at Step**.</span></span> <span data-ttu-id="728df-137">选择 **“步骤 ID 1”** ，然后选择 **“开始”**。</span><span class="sxs-lookup"><span data-stu-id="728df-137">Select **Step ID 1** and select **Start**.</span></span>  
  
       <span data-ttu-id="728df-138">当状态更改为**成功**，SQL Server 代理作业和 BizTalk Server 数据库还原到目标系统。</span><span class="sxs-lookup"><span data-stu-id="728df-138">When the status changes to **Success**, the SQL Server Agent jobs and BizTalk Server databases are restored to the destination system.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="728df-139">如果 **“状态”** 为“错误”，请选择“消息”字段中的链接以确定原因。</span><span class="sxs-lookup"><span data-stu-id="728df-139">If the **Status** is Error, select the link in the Message field to determine the cause.</span></span> <span data-ttu-id="728df-140">在继续前，这些作业的状态应为“成功”。</span><span class="sxs-lookup"><span data-stu-id="728df-140">These jobs should have a Success status before continuing.</span></span>  
  
3. <span data-ttu-id="728df-141">在 BizTalk 服务器上以前编辑 SampleUpdateInfo.xml 文件，打开命令提示符，并转到：</span><span class="sxs-lookup"><span data-stu-id="728df-141">On the BizTalk Server where you edited the SampleUpdateInfo.xml file, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="728df-142">32 位计算机： `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="728df-142">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="728df-143">64 位计算机： `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="728df-143">64-bit computer: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
4. <span data-ttu-id="728df-144">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="728df-144">At the command prompt, type:</span></span>
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`

    > [!NOTE]
    > <span data-ttu-id="728df-145">在使用 SQL Server 2016 环境时，可能需要使用 MSOLEDBSQL 中 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="728df-145">When using a SQL Server 2016 environment, you may need to use MSOLEDBSQL in UpdateDatabase.vbs.</span></span> <span data-ttu-id="728df-146">在 UpdateDatabase.vbs，转到`conn.Provider = "SQLOLEDB"`。</span><span class="sxs-lookup"><span data-stu-id="728df-146">In UpdateDatabase.vbs, go to `conn.Provider = "SQLOLEDB"`.</span></span> <span data-ttu-id="728df-147">更改`SQLOLEDB`到`MSOLEDBSQL`。</span><span class="sxs-lookup"><span data-stu-id="728df-147">Change `SQLOLEDB` to `MSOLEDBSQL`.</span></span> <span data-ttu-id="728df-148">否则，该脚本可能会失败，错误： `SQL Server: Invalid connection string attribute`。</span><span class="sxs-lookup"><span data-stu-id="728df-148">Otherwise, the script may fail with error: `SQL Server: Invalid connection string attribute`.</span></span>
    > 
    > <span data-ttu-id="728df-149">[下载 MSOLEDBSQL](https://www.microsoft.com/download/details.aspx?id=56730)。</span><span class="sxs-lookup"><span data-stu-id="728df-149">[Download MSOLEDBSQL](https://www.microsoft.com/download/details.aspx?id=56730).</span></span>
    > 
    > <span data-ttu-id="728df-150">此脚本可更新存储其他数据库的位置信息的所有表。</span><span class="sxs-lookup"><span data-stu-id="728df-150">This script updates all tables that store information about the location of other databases.</span></span>
  
    > [!IMPORTANT]
    >  - <span data-ttu-id="728df-151">在 BizTalk 组中的 **一个** 服务器上运行 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="728df-151">Run UpdateDatabase.vbs on **one** server in the BizTalk group.</span></span>  
    >  - <span data-ttu-id="728df-152">在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="728df-152">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span> <span data-ttu-id="728df-153">请注意，64 位计算机上的默认命令提示符是 64 位命令提示符下，位于 %systemdrive%\windows\system32\cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="728df-153">Note that the default command prompt on 64-bit computers is a 64-bit command prompt, and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
    >  - <span data-ttu-id="728df-154">还原数据库时，BizTalk EDI 引擎不需要任何 SampleUpdateInfo.xml 自己修改。</span><span class="sxs-lookup"><span data-stu-id="728df-154">The BizTalk EDI engine doesn't require any of its own modifications to SampleUpdateInfo.xml when restoring databases.</span></span>  <span data-ttu-id="728df-155">它依赖于与要访问的 EDI 表的 BizTalkDTADb 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="728df-155">It relies on connectivity to the BizTalkDTADb database to access the EDI tables.</span></span>  
  
5. <span data-ttu-id="728df-156">将已编辑的 SampleUpdateInfo.xml 文件复制到以下文件夹上**每个**此 BizTalk 组中运行 BizTalk Server 计算机：</span><span class="sxs-lookup"><span data-stu-id="728df-156">Copy the edited SampleUpdateInfo.xml file to the following folder on **every** computer running BizTalk Server in this BizTalk group:</span></span>  
  
    <span data-ttu-id="728df-157">32 位计算机：将复制到 `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="728df-157">32-bit computer: Copy to `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="728df-158">64 位计算机：将复制到 `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="728df-158">64-bit computer: Copy to `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
6. <span data-ttu-id="728df-159">上**每个**计算机在 BizTalk Server 组中，打开命令提示符，并转到：</span><span class="sxs-lookup"><span data-stu-id="728df-159">On **each** computer in the BizTalk Server group, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="728df-160">32 位计算机： `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="728df-160">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="728df-161">64 位计算机： `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="728df-161">64-bit computer: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
7. <span data-ttu-id="728df-162">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="728df-162">At the command prompt, type:</span></span>  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    <span data-ttu-id="728df-163">此脚本可更新存储其他数据库的位置信息的所有注册表项。</span><span class="sxs-lookup"><span data-stu-id="728df-163">This script updates all registry entries that store information about the location of other databases.</span></span>  
  
   > [!IMPORTANT]
   >  - <span data-ttu-id="728df-164">在 BizTalk 组中的 **每个** 服务器上运行 UpdateRegistry.vbs。</span><span class="sxs-lookup"><span data-stu-id="728df-164">Run UpdateRegistry.vbs on **every** server in the BizTalk group.</span></span>  
   >  - <span data-ttu-id="728df-165">在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateRegistry.vbs。</span><span class="sxs-lookup"><span data-stu-id="728df-165">On 64-bit computers, you must run UpdateRegistry.vbs from a 64-bit command prompt.</span></span>  <span data-ttu-id="728df-166">请注意，64 位计算机上的默认命令提示符是 64 位命令提示符，位于 %SystemDrive%\windows\System32\cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="728df-166">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
  
8. <span data-ttu-id="728df-167">重新启动所有 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="728df-167">Restart all the BizTalk Server services.</span></span> <span data-ttu-id="728df-168">请参见 [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="728df-168">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
9. <span data-ttu-id="728df-169">还原数据库后，重新启动 Windows 管理规范服务：</span><span class="sxs-lookup"><span data-stu-id="728df-169">After restoring your databases, restart the Windows Management Instrumentation service:</span></span>  
  
    1.  <span data-ttu-id="728df-170">打开 **“services.msc”**。</span><span class="sxs-lookup"><span data-stu-id="728df-170">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="728df-171">右键单击 **“Windows 管理规范”**，然后选择 **“重新启动”**。</span><span class="sxs-lookup"><span data-stu-id="728df-171">Right-click **Windows Management Instrumentation**, and then select **Restart**.</span></span>  
  
10. <span data-ttu-id="728df-172">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="728df-172">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="728df-173">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="728df-173">Do the following:</span></span>  
  
    1. <span data-ttu-id="728df-174">右键单击 **“BizTalk 组”** ，然后选择 **“删除”**。</span><span class="sxs-lookup"><span data-stu-id="728df-174">Right-click the **BizTalk Group** and select **Remove**.</span></span>  
  
    2. <span data-ttu-id="728df-175">右键单击 **“BizTalk Server 管理”** ，然后选择 **“连接到现有组”**。</span><span class="sxs-lookup"><span data-stu-id="728df-175">Right-click **BizTalk Server Administration** and select **Connect to Existing Group**.</span></span>  
  
    3. <span data-ttu-id="728df-176">在 **“SQL Server 名称”** 中，键入托管 BizTalk 管理数据库的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="728df-176">In **SQL Server name**, select the name of the SQL Server instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="728df-177">当选中 SQL Server 实例时，BizTalk Server 会自动检测该计算机上的 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="728df-177">When you select the SQL Server instance, BizTalk Server automatically detects the BizTalk Server databases on that computer.</span></span>  
  
    4. <span data-ttu-id="728df-178">在 **“数据库名称”** 中，选择 BizTalk 管理数据库（默认为 **“BizTalkMgmtDb”** ），然后选择 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="728df-178">In **Database name**, select your BizTalk Management database (**BizTalkMgmtDb** by default), and then select **OK**.</span></span>  
  
       <span data-ttu-id="728df-179">在 BizTalk Server 管理控制台将 BizTalk 组添加到管理控制台。</span><span class="sxs-lookup"><span data-stu-id="728df-179">The BizTalk Server Administration console adds the BizTalk group to the Administration console.</span></span>  
  
       <span data-ttu-id="728df-180">BizTalk Server 现已还原，并且应运行。</span><span class="sxs-lookup"><span data-stu-id="728df-180">Your BizTalk Server is now restored and should be running.</span></span> <span data-ttu-id="728df-181">接下来，配置备份 BizTalk Server 作业，以开始向新目标服务器写入备份。</span><span class="sxs-lookup"><span data-stu-id="728df-181">Next, configure the Backup BizTalk Server job to start writing backups to a new destination server.</span></span> <span data-ttu-id="728df-182">还应该重新配置新的目标系统。</span><span class="sxs-lookup"><span data-stu-id="728df-182">You should also reconfigure a new destination system.</span></span>  

## <a name="important"></a><span data-ttu-id="728df-183">重要提示\*\*</span><span class="sxs-lookup"><span data-stu-id="728df-183">Important</span></span>

- <span data-ttu-id="728df-184">如果您使用规则引擎中，在还原数据库后，必须重新规则引擎更新服务的每个服务器上启动 BizTalk Server 组中。</span><span class="sxs-lookup"><span data-stu-id="728df-184">If you're using the Rules Engine, after restoring the databases, you must restart the Rule Engine Update Service on every server in the BizTalk Server group.</span></span> <span data-ttu-id="728df-185">请参见 [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="728df-185">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
- <span data-ttu-id="728df-186">如果您使用 BAM，现在是还原 BAM 数据库的时间。</span><span class="sxs-lookup"><span data-stu-id="728df-186">If you're using BAM, now is the time to restore the BAM databases.</span></span> <span data-ttu-id="728df-187">请参见 [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="728df-187">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
- <span data-ttu-id="728df-188">如果要移动数据库，并使用 BizTalk EDI 或 RosettaNet 加速器，某些 SQL 端口可能会对 BizTalk 数据库的安装程序。</span><span class="sxs-lookup"><span data-stu-id="728df-188">If you're moving databases and you're using BizTalk EDI or the RosettaNet accelerator, then some SQL ports may be setup against the BizTalk databases.</span></span> <span data-ttu-id="728df-189">导出绑定，搜索旧数据库链接，并相应地替换数据库链接。</span><span class="sxs-lookup"><span data-stu-id="728df-189">Export the bindings, search for the old database links, and replace the database links accordingly.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="728df-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="728df-190">Next Steps</span></span>  
 [<span data-ttu-id="728df-191">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="728df-191">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a><span data-ttu-id="728df-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="728df-192">See Also</span></span>  

 <span data-ttu-id="728df-193">[配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="728df-193">[Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="728df-194">配置日志传送的目标系统</span><span class="sxs-lookup"><span data-stu-id="728df-194">Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)

