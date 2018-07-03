---
title: 如何还原数据库 |Microsoft Docs
ms.custom: ''
ms.date: 2016-05-10
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- restoring [BAM], Star Schema database, Star Schema database [BAM], restoring
- restoring, 64-bit environments
- Star Schema database [BAM], restoring
- restoring [BAM], Analysis database
- log shipping
- databases, restoring
- Archive database [BAM], restoring
- backing up, restoring
- Analysis database [BAM], restoring
- restoring [BAM], Archive database
- restoring [BAM], Star Schema database
- databases, restoring [64-bit environment]
- Primary Import database [BAM], restoring
- 64-bit environments, restoring databases
- restoring, databases
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5ecebcb4a9d322ab67339008abaa251a26b867
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977942"
---
# <a name="how-to-restore-your-databases"></a><span data-ttu-id="a8ff0-102">如何还原数据库</span><span class="sxs-lookup"><span data-stu-id="a8ff0-102">How to Restore Your Databases</span></span>
<span data-ttu-id="a8ff0-103">必须将所有数据库还原到相同的标记，以确保各个数据库间的事务状态一致。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-103">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="a8ff0-104">请参阅[标记的事务，完整备份，备份和日志备份](../core/marked-transactions-full-backups-and-log-backups.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-104">See [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
 <span data-ttu-id="a8ff0-105">如果目标系统中只有一个服务器，请确保还原了所有日志备份集（除了最新日志备份集以外）。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-105">If there is only one server in the destination system, make sure that all of the log backup sets (except for the most recent set) have been restored.</span></span> <span data-ttu-id="a8ff0-106">请参阅[查看的历史记录备份还原](../core/viewing-the-history-of-restored-backups.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-106">See [Viewing the History of Restored Backups](../core/viewing-the-history-of-restored-backups.md).</span></span> <span data-ttu-id="a8ff0-107">如果没有还原所有日志备份集，并且当前没有运行还原作业，请运行还原作业（必要时，请手动运行）。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-107">If all the log backup sets have not been restored, and the restore job is not currently running, run the restore job (manually if necessary).</span></span> <span data-ttu-id="a8ff0-108">如果存在尚未完成的可还原备份集，则作业将处理它们，直到所有备份集全部还原为止。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-108">If there are outstanding backup sets that can be restored, the job processes them until they are all restored.</span></span>  
  
 <span data-ttu-id="a8ff0-109">如果目标系统中有多个服务器，则必须将所有服务器还原到相同的备份集。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-109">If there are multiple servers in the destination system, all servers must be restored to the same backup set.</span></span> <span data-ttu-id="a8ff0-110">查看每个服务器的还原历史记录，确保所有服务器上还原的最新日志备份集都是相同的。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-110">View the restore history on each server and make sure that the most recent log backup set restored is the same on all servers.</span></span> <span data-ttu-id="a8ff0-111">如果不同，则必须在需要还原最新日志备份集的每个服务器上手动运行还原作业。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-111">If it is not, you must manually run the restore job on each server that needs the most recent log backup set restored.</span></span>  
  
 <span data-ttu-id="a8ff0-112">当所有的服务器都还原为相同的备份集后，最终的备份集可以手动还原。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-112">After all of the servers are on the same backup set, the final set can be manually restored.</span></span>  
  
 <span data-ttu-id="a8ff0-113">adm_BackupHistory 表是记录源系统日志传送过程历史记录的核心。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-113">The adm_BackupHistory table is the central history point for the log shipping process for the source system.</span></span> <span data-ttu-id="a8ff0-114">所有执行的备份工作都记录到此表中。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-114">All backup work performed is recorded to this table.</span></span> <span data-ttu-id="a8ff0-115">目标系统中的所有服务器都从此表读取信息，以获取执行其还原工作所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-115">All servers in your destination system read from this table to receive the information needed to perform their restore work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8ff0-116">如果从备份还原 BAM 主导入数据库，则还应该使用该 BAM 主导入数据库备份之前的备份来还原 BAM 存档数据库、BAM 星型架构数据库和 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-116">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span> <span data-ttu-id="a8ff0-117">请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-117">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a8ff0-118">如果将源数据库的完整备份或日志备份从备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业放置它们的位置上移走，则应该更新目标系统上 bts_LogShippingDatabases 表中该数据库的相关行，将 LogFileLocation 或 DBFileLocation 设置为目标系统应从中读取完整/日志备份文件的新位置。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-118">If you move the full or log backups for a source database from the location in which the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job put them, you should update the associated row for that database in the bts_LogShippingDatabases table on the destination system by setting the LogFileLocation or DBFileLocation to the new location where the destination system should read the full/log backup files.</span></span> <span data-ttu-id="a8ff0-119">运行 bts_ConfigureBtsLogShipping 存储过程时，将填充此表。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-119">This table is populated when you run the bts_ConfigureBtsLogShipping stored procedure.</span></span> <span data-ttu-id="a8ff0-120">默认情况下，这些列设置为空，这表明目标系统应该从 adm_BackupHistory 表中存储的位置上读取这些备份文件。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-120">By default, these columns are set to null, which indicates that the destination system should read the backup files from the location stored in the adm_BackupHistory table.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="a8ff0-121">请总是在某个安全位置保留备份文件的一个副本。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-121">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="a8ff0-122">即使你进行了日志备份，在没有备份文件的情况下也无法还原数据库。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-122">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8ff0-123">必要條件</span><span class="sxs-lookup"><span data-stu-id="a8ff0-123">Prerequisites</span></span>  
 <span data-ttu-id="a8ff0-124">使用作为 sysadmin SQL Server 角色成员的帐户登录到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-124">Log in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
### <a name="to-restore-your-databases"></a><span data-ttu-id="a8ff0-125">还原数据库</span><span class="sxs-lookup"><span data-stu-id="a8ff0-125">To restore your databases</span></span>  
  
1. <span data-ttu-id="a8ff0-126">在目标系统上，打开**SQL Server Management Studio**，并连接到你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-126">On the destination system, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="a8ff0-127">展开 **“SQL Server 代理”**，然后展开 **“作业”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span> <span data-ttu-id="a8ff0-128">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-128">Do the following:</span></span>  
  
   1. <span data-ttu-id="a8ff0-129">右键单击 **“BTS 日志传送 - 获取备份历史记录”** 作业，然后选择 **“禁用”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-129">Right-click the **BTS Log Shipping - Get Backup History** job and select **Disable**.</span></span> <span data-ttu-id="a8ff0-130">状态将更改为“成功”。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-130">The status changes to Success.</span></span>  
  
   2. <span data-ttu-id="a8ff0-131">右键单击 **“BTS 日志传送 - 还原数据库”** 作业，然后选择 **“禁用”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-131">Right-click the **BTS Log Shipping - Restore Databases** job and select **Disable**.</span></span> <span data-ttu-id="a8ff0-132">状态将更改为“成功”。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-132">The status changes to Success.</span></span>  
  
   3. <span data-ttu-id="a8ff0-133">右键单击 **“BTS 日志传送 - 还原到标记”** ，然后选择 **“作业开始步骤”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-133">Right-click the **BTS Log Shipping - Restore To Mark** and select **Start Job at Step**.</span></span> <span data-ttu-id="a8ff0-134">选择 **“步骤 ID 1”** ，然后选择 **“开始”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-134">Select **Step ID 1** and select **Start**.</span></span>  
  
       <span data-ttu-id="a8ff0-135">当状态更改为**成功**，SQL Server 代理作业和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库还原到目标系统。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-135">When the status changes to **Success**, the SQL Server Agent jobs and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are restored to the destination system.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="a8ff0-136">如果 **“状态”** 为“错误”，请选择“消息”字段中的链接以确定原因。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-136">If the **Status** is Error, select the link in the Message field to determine the cause.</span></span> <span data-ttu-id="a8ff0-137">在继续前，这些作业的状态应为“成功”。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-137">These jobs should have a Success status before continuing.</span></span>  
  
3. <span data-ttu-id="a8ff0-138">在编辑了 SampleUpdateInfo.xml 文件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上，打开命令提示符并转到：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-138">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] where you edited the SampleUpdateInfo.xml file, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="a8ff0-139">32 位计算机： `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a8ff0-139">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="a8ff0-140">64 位计算机： `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a8ff0-140">64-bit computer: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
4. <span data-ttu-id="a8ff0-141">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-141">At the command prompt, type:</span></span>  
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
    <span data-ttu-id="a8ff0-142">此脚本可更新存储其他数据库的位置信息的所有表。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-142">This script updates all tables that store information about the location of other databases.</span></span>  
  
   > [!IMPORTANT]
   > - <span data-ttu-id="a8ff0-143">在 BizTalk 组中的 **一个** 服务器上运行 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-143">Run UpdateDatabase.vbs on **one** server in the BizTalk group.</span></span>  
   >   -   <span data-ttu-id="a8ff0-144">在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-144">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span> <span data-ttu-id="a8ff0-145">请注意，64 位计算机上的默认命令提示符是 64 位命令提示符，位于 %SystemDrive%\windows\System32\cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-145">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
   >   -   <span data-ttu-id="a8ff0-146">还原数据库时，BizTalk EDI 引擎不需要任何 SampleUpdateInfo.xml 自己修改。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-146">The BizTalk EDI engine does not require any of its own modifications to SampleUpdateInfo.xml when restoring databases.</span></span>  <span data-ttu-id="a8ff0-147">它依赖于与要访问的 EDI 表的 BizTalkDTADb 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-147">It relies on connectivity to the BizTalkDTADb database to access the EDI tables.</span></span>  
  
5. <span data-ttu-id="a8ff0-148">将已编辑的 SampleUpdateInfo.xml 文件复制到以下文件夹上**每个**运行计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此 BizTalk 组中：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-148">Copy the edited SampleUpdateInfo.xml file to the following folder on **every** computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in this BizTalk group:</span></span>  
  
    <span data-ttu-id="a8ff0-149">32 位计算机： 复制到 `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a8ff0-149">32-bit computer: Copy to `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="a8ff0-150">64 位计算机： 复制到 `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a8ff0-150">64-bit computer: Copy to `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
6. <span data-ttu-id="a8ff0-151">上**每个**中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组，打开命令提示符，并转到：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-151">On **each** computer in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="a8ff0-152">32 位计算机： `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a8ff0-152">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="a8ff0-153">64 位计算机： `%SystemDrive%Program Files (x86)Microsoft BizTalk Server <version>Bins32SchemaRestore`</span><span class="sxs-lookup"><span data-stu-id="a8ff0-153">64-bit computer: `%SystemDrive%Program Files (x86)Microsoft BizTalk Server <version>Bins32SchemaRestore`</span></span>  
  
7. <span data-ttu-id="a8ff0-154">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-154">At the command prompt, type:</span></span>  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    <span data-ttu-id="a8ff0-155">此脚本可更新存储其他数据库的位置信息的所有注册表项。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-155">This script updates all registry entries that store information about the location of other databases.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="a8ff0-156">在 BizTalk 组中的 **每个** 服务器上运行 UpdateRegistry.vbs。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-156">Run UpdateRegistry.vbs on **every** server in the BizTalk group.</span></span>  
   >   
   >  <span data-ttu-id="a8ff0-157">在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateRegistry.vbs。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-157">On 64-bit computers, you must run UpdateRegistry.vbs from a 64-bit command prompt.</span></span>  <span data-ttu-id="a8ff0-158">请注意，64 位计算机上的默认命令提示符是 64 位命令提示符，位于 %SystemDrive%\windows\System32\cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-158">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
  
8. <span data-ttu-id="a8ff0-159">重新启动所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-159">Restart all the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="a8ff0-160">请参阅[如何启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-160">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
9. <span data-ttu-id="a8ff0-161">还原数据库后，重新启动 Windows 管理规范服务：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-161">After restoring your databases, restart the Windows Management Instrumentation service:</span></span>  
  
    1.  <span data-ttu-id="a8ff0-162">打开 **“services.msc”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-162">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="a8ff0-163">右键单击 **“Windows 管理规范”**，然后选择 **“重新启动”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-163">Right-click **Windows Management Instrumentation**, and then select **Restart**.</span></span>  
  
10. <span data-ttu-id="a8ff0-164">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-164">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="a8ff0-165">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a8ff0-165">Do the following:</span></span>  
  
    1. <span data-ttu-id="a8ff0-166">右键单击 **“BizTalk 组”** ，然后选择 **“删除”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-166">Right-click the **BizTalk Group** and select **Remove**.</span></span>  
  
    2. <span data-ttu-id="a8ff0-167">右键单击 **“BizTalk Server 管理”** ，然后选择 **“连接到现有组”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-167">Right-click **BizTalk Server Administration** and select **Connect to Existing Group**.</span></span>  
  
    3. <span data-ttu-id="a8ff0-168">在 **“SQL Server 名称”** 中，键入托管 BizTalk 管理数据库的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-168">In **SQL Server name**, select the name of the SQL Server instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="a8ff0-169">在选择 SQL Server 实例时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将自动检测该计算机上的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-169">When you select the SQL Server instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically detects the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases on that computer.</span></span>  
  
    4. <span data-ttu-id="a8ff0-170">在 **“数据库名称”** 中，选择 BizTalk 管理数据库（默认为 **“BizTalkMgmtDb”** ），然后选择 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-170">In **Database name**, select your BizTalk Management database (**BizTalkMgmtDb** by default), and then select **OK**.</span></span>  
  
       <span data-ttu-id="a8ff0-171">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台将 BizTalk 组添加到管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-171">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console adds the BizTalk group to the Administration console.</span></span>  
  
       <span data-ttu-id="a8ff0-172">你的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 现已还原，应该正在运行。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-172">Your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is now restored and should be running.</span></span> <span data-ttu-id="a8ff0-173">接下来，配置备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业，以开始向新目标服务器写入备份。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-173">Next, configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job to start writing backups to a new destination server.</span></span> <span data-ttu-id="a8ff0-174">还应该重新配置新的目标系统。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-174">You should also reconfigure a new destination system.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8ff0-175">如果使用的是规则引擎，则在还原数据库后，必须重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组中的每个服务器上的规则引擎更新服务。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-175">If you are using the Rules Engine, after restoring the databases, you must restart the Rule Engine Update Service on every server in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="a8ff0-176">请参阅[如何启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-176">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a8ff0-177">如果使用的是 BAM，则此时还原 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-177">If you are using BAM, this is the time to restore the BAM databases.</span></span> <span data-ttu-id="a8ff0-178">请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ff0-178">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a8ff0-179">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a8ff0-179">Next Steps</span></span>  
 [<span data-ttu-id="a8ff0-180">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="a8ff0-180">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8ff0-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ff0-181">See Also</span></span>  
 <span data-ttu-id="a8ff0-182">[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="a8ff0-182">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="a8ff0-183">如何配置日志传送目标系统</span><span class="sxs-lookup"><span data-stu-id="a8ff0-183">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)