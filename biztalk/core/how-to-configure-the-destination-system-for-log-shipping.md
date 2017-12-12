---
title: "如何为日志传送配置的目标系统 |Microsoft 文档"
ms.custom: 
ms.date: 2015-12-03
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- system failures, preventing
- log shipping
- databases, backing up
- backing up, databases
- system failures, backing up
- backing up, system failures
ms.assetid: 7b4425f5-b105-4fb2-a503-94ca1e75ad55
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 611544e77de738c904fa673b56dbec75fd17d4bd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="b4537-102">如何配置日志传送的目标系统</span><span class="sxs-lookup"><span data-stu-id="b4537-102">How to Configure the Destination System for Log Shipping</span></span>
<span data-ttu-id="b4537-103">日志传送具有备用服务器功能，用以缩短出现系统故障时的停机时间。</span><span class="sxs-lookup"><span data-stu-id="b4537-103">Log shipping provides standby server capabilities to reduce downtime in the event of a system failure.</span></span> <span data-ttu-id="b4537-104">使用日志传送可以自动从源系统向目标系统发送事务日志。</span><span class="sxs-lookup"><span data-stu-id="b4537-104">Log shipping allows you to automatically send transaction logs from the source system to the destination system.</span></span> <span data-ttu-id="b4537-105">在目标系统中，事务日志还原到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库; 让他们可以与源数据库紧密同步。</span><span class="sxs-lookup"><span data-stu-id="b4537-105">At the destination system, the transaction logs are restored to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases; keeping them closely synchronized with the source databases.</span></span>  
  
 <span data-ttu-id="b4537-106">日志传送既可以在单服务器环境下工作，也可以在分布式服务器环境下工作。</span><span class="sxs-lookup"><span data-stu-id="b4537-106">Log shipping works in both single server and distributed server environments.</span></span> <span data-ttu-id="b4537-107">包含实时数据的服务器或服务器组称作源系统（或主系统）。</span><span class="sxs-lookup"><span data-stu-id="b4537-107">The server or group of servers that contain live data is known as the source (or primary) system.</span></span> <span data-ttu-id="b4537-108">用来还原由源系统（或主系统）生成的数据库备份的服务器或服务器组称作目标系统（或辅助系统）。</span><span class="sxs-lookup"><span data-stu-id="b4537-108">The server or group of servers that are used to restore the database backups produced by the source (or primary) system is known as the destination (or secondary) system.</span></span>  
  
 <span data-ttu-id="b4537-109">[有关日志传送](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server)在 SQL 文档提供的特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="b4537-109">[About Log Shipping](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server) in the SQL documentation provides specific details.</span></span>  
  
 <span data-ttu-id="b4537-110">你可以运用以下步骤为单个源系统创建由一个服务器组成的目标系统。</span><span class="sxs-lookup"><span data-stu-id="b4537-110">You can use the following steps to create a destination system that consists of one server for a single source system.</span></span> <span data-ttu-id="b4537-111">如果目标系统包含多个服务器，则在每个目标服务器上重复执行以下步骤即可。</span><span class="sxs-lookup"><span data-stu-id="b4537-111">If the destination system contains multiple servers, repeat the steps on each destination server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4537-112">请总是在某个安全位置保留备份文件的一个副本。</span><span class="sxs-lookup"><span data-stu-id="b4537-112">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="b4537-113">即使你进行了日志备份，在没有备份文件的情况下也无法还原数据库。</span><span class="sxs-lookup"><span data-stu-id="b4537-113">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b4537-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="b4537-114">Prerequisites</span></span>  
* <span data-ttu-id="b4537-115">作为的成员登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="b4537-115">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
* <span data-ttu-id="b4537-116">在源和目标系统上使用相同版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b4537-116">Use the same version of SQL Server on the source and destination systems.</span></span> <span data-ttu-id="b4537-117">SQL Server 必须安装在源和目标系统上的相同的相对位置。</span><span class="sxs-lookup"><span data-stu-id="b4537-117">SQL Server must be installed in the same relative location on the source and destination systems.</span></span>  
  
* <span data-ttu-id="b4537-118">源系统上的 SQL 事务日志（.LDF 文件）目录在目标系统上也必须存在。</span><span class="sxs-lookup"><span data-stu-id="b4537-118">The directory for SQL transaction log (.LDF files) on the source system must also exist on the destination system.</span></span> <span data-ttu-id="b4537-119">如果该目录在目标系统上不存在，请使用与源系统上的目录相同的名称和权限创建该目录。</span><span class="sxs-lookup"><span data-stu-id="b4537-119">If this directory is not on the destination system, create the directory with the same name and permissions as on the source system.</span></span>  
  
### <a name="configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="b4537-120">配置日志传送目标系统</span><span class="sxs-lookup"><span data-stu-id="b4537-120">Configure the destination system for log shipping</span></span>  
  
1.  <span data-ttu-id="b4537-121">在目标系统上，打开**SQL Server Management Studio**，并连接到你的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b4537-121">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span> <span data-ttu-id="b4537-122">选择**master**从可用数据库。</span><span class="sxs-lookup"><span data-stu-id="b4537-122">Select **master** from Available Databases.</span></span>  
  
2.  <span data-ttu-id="b4537-123">上**文件**菜单上，**打开**以下 SQL 脚本：</span><span class="sxs-lookup"><span data-stu-id="b4537-123">On the **File** menu, **Open** the following SQL script:</span></span>  
  
    ```    
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
    ```  
  
3.  <span data-ttu-id="b4537-124">上**查询**菜单上，选择**执行**。</span><span class="sxs-lookup"><span data-stu-id="b4537-124">On the **Query** menu, select **Execute**.</span></span>  
  
     <span data-ttu-id="b4537-125">*LogShipping_Destination_Schema*将删除并重新创建用于还原目标系统上的源数据库的表。</span><span class="sxs-lookup"><span data-stu-id="b4537-125">The *LogShipping_Destination_Schema* drops and recreates the tables used for restoring the source databases on the destination system.</span></span> <span data-ttu-id="b4537-126">这些表存储了以下信息：要恢复的数据库的列表、从源系统的 BizTalkMgmtDb 数据库导入的备份历史记录的副本、有关 SQL Server 代理作业（配置为针对源数据库运行）的信息。</span><span class="sxs-lookup"><span data-stu-id="b4537-126">This includes tables to store the list of databases being recovered, copies of the backup history imported from the source system's BizTalkMgmtDb database, and information about SQL Server Agent jobs configured to run against the source databases.</span></span>  
  
4.  <span data-ttu-id="b4537-127">上**文件**菜单上，**打开**以下 SQL 脚本：</span><span class="sxs-lookup"><span data-stu-id="b4537-127">On the **File** menu, **Open** the following SQL script:</span></span>  
  
    ```    
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
    ```  
  
5.  <span data-ttu-id="b4537-128">上**查询**菜单上，选择**执行**。</span><span class="sxs-lookup"><span data-stu-id="b4537-128">On the **Query** menu, select **Execute**.</span></span>  
  
6.  <span data-ttu-id="b4537-129">在计算机或已标识为目标系统的计算机中，打开**SQL Server Management Studio**并连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b4537-129">On the computer or computers you have identified as the destination system, open **SQL Server Management Studio** and connect to the SQL Server.</span></span>  
  
7.  <span data-ttu-id="b4537-130">选择**新查询**。</span><span class="sxs-lookup"><span data-stu-id="b4537-130">Select **New Query**.</span></span> <span data-ttu-id="b4537-131">在查询窗口中粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="b4537-131">In the query window, paste the following command:</span></span>  
  
    ```  
    exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
    @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
    @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
    @SourceServerName = null, -- null indicates that this destination server restores all databases  
    @fLinkServers = 1 -- 1 automatically links the server to the management database  
    ```  
  
     <span data-ttu-id="b4537-132">然后：</span><span class="sxs-lookup"><span data-stu-id="b4537-132">Then:</span></span>  
  
    1.  <span data-ttu-id="b4537-133">在目标系统上，启用**[即席分布式查询](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**。</span><span class="sxs-lookup"><span data-stu-id="b4537-133">On the destination system, enable **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**.</span></span>  
  
    2.  <span data-ttu-id="b4537-134">在查询窗口中，将替换为 *\<MyLogShippingSolution\>* 使用有意义的描述，括在单引号。</span><span class="sxs-lookup"><span data-stu-id="b4537-134">In the query window, replace *\<MyLogShippingSolution\>* with a meaningful description, surrounded by single quotes.</span></span>  
  
    3.  <span data-ttu-id="b4537-135">在查询窗口中，将替换为 *\<BizTalkServerManagementDatabaseName\>* 和 *\<BizTalkServerManagementDatabaseServer\>* 与名称和源 BizTalk 管理数据库括在单引号中的位置。</span><span class="sxs-lookup"><span data-stu-id="b4537-135">In the query window, replace *\<BizTalkServerManagementDatabaseName\>* and *\<BizTalkServerManagementDatabaseServer\>* with the name and location of your source BizTalk Management database, surrounded by single quotes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b4537-136">如果有多个源服务器，则可将每个源服务器还原到它自己的目标服务器。</span><span class="sxs-lookup"><span data-stu-id="b4537-136">If you have more than one source server, you can restore each source server to its own destination server.</span></span> <span data-ttu-id="b4537-137">在每个目标服务器上，在 **@SourceServerName = null**参数，替换*null*具有合适的源服务器的名称，括在单引号 (例如，  **@SourceServerName = MySourceServer**)。</span><span class="sxs-lookup"><span data-stu-id="b4537-137">On each destination server, in the **@SourceServerName = null** parameter, replace *null* with the name of the appropriate source server, surrounded by single quotes (for example, **@SourceServerName = 'MySourceServer',**).</span></span>  
  
8.  <span data-ttu-id="b4537-138">上**查询**菜单上，选择**执行**。</span><span class="sxs-lookup"><span data-stu-id="b4537-138">On the **Query** menu, select **Execute**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b4537-139">如果查询失败，在修复的问题查询之后，则必须通过启动此过程重新配置目标系统中的步骤 1 中。</span><span class="sxs-lookup"><span data-stu-id="b4537-139">If the query fails, after you fix the problem with the query, you must start over from step 1 of this procedure to reconfigure the destination system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b4537-140">目标系统上的还原作业将尝试重新创建每个还原的数据库的日志和数据文件，这些文件的创建位置与它们在源数据库服务器上的位置相同。</span><span class="sxs-lookup"><span data-stu-id="b4537-140">The restore jobs on the destination system attempt to recreate the log and data files for each restored database in the same location as they existed on the source database server.</span></span>  
  
9. <span data-ttu-id="b4537-141">在目标系统上**SQL Server Management Studio**，展开**SQL Server 代理**，然后展开**作业**。</span><span class="sxs-lookup"><span data-stu-id="b4537-141">On the destination system in **SQL Server Management Studio**, expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
     <span data-ttu-id="b4537-142">在“详细信息”窗格中，有三个新作业：</span><span class="sxs-lookup"><span data-stu-id="b4537-142">In the details pane, there are three new jobs:</span></span>  
  
    -   <span data-ttu-id="b4537-143">**BTS 日志传送获取备份历史记录**</span><span class="sxs-lookup"><span data-stu-id="b4537-143">**BTS Log Shipping Get Backup History**</span></span>  
  
         <span data-ttu-id="b4537-144">此 BizTalk 作业将备份历史记录从源移到目标。</span><span class="sxs-lookup"><span data-stu-id="b4537-144">This BizTalk job moves backup history records from the source to the destination.</span></span> <span data-ttu-id="b4537-145">默认情况下，安排该作业每分钟运行一次。</span><span class="sxs-lookup"><span data-stu-id="b4537-145">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="b4537-146">应尽可能频繁地运行此作业，以便将备份历史记录从源系统移到目标系统。</span><span class="sxs-lookup"><span data-stu-id="b4537-146">This job runs as frequently as possible in order to move history records from the source to the destination.</span></span> <span data-ttu-id="b4537-147">如果源系统出现故障，则已标识为目标系统的服务器会继续处理已导入的历史记录。</span><span class="sxs-lookup"><span data-stu-id="b4537-147">In the event of a system failure to the source system, the server that you identified as the destination system continues to process the history records that have already been imported.</span></span>  
  
    -   <span data-ttu-id="b4537-148">**BTS 服务器日志传送还原数据库**</span><span class="sxs-lookup"><span data-stu-id="b4537-148">**BTS Server Log Shipping Restore Databases**</span></span>  
  
         <span data-ttu-id="b4537-149">此 BizTalk 作业可将源服务器中给定数据库的备份文件还原到目标服务器。</span><span class="sxs-lookup"><span data-stu-id="b4537-149">This BizTalk job restores backup files for the given databases for the source to the destination server.</span></span> <span data-ttu-id="b4537-150">默认情况下，安排该作业每分钟运行一次。</span><span class="sxs-lookup"><span data-stu-id="b4537-150">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="b4537-151">只要存在要还原的备份文件，则该作业将一直运行下去，而不会完成。</span><span class="sxs-lookup"><span data-stu-id="b4537-151">This job runs continuously without completing as long as there are backup files to restore.</span></span> <span data-ttu-id="b4537-152">为了安全起见，你可多运行该作业一次，以确保已经没有要还原的备份文件。</span><span class="sxs-lookup"><span data-stu-id="b4537-152">As an extra precaution, you can run this job an additional time to ensure that it is complete.</span></span>  
  
    -   <span data-ttu-id="b4537-153">**BTS 日志传送还原到标记**</span><span class="sxs-lookup"><span data-stu-id="b4537-153">**BTS Log Shipping Restore To Mark**</span></span>  
  
         <span data-ttu-id="b4537-154">此 BizTalk 作业可将所有数据库还原到上次日志备份中的一个标记。</span><span class="sxs-lookup"><span data-stu-id="b4537-154">This BizTalk job restores all of the databases to a mark in the last log backup.</span></span> <span data-ttu-id="b4537-155">这可确保所有数据库在事务性上处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="b4537-155">This ensures that all of the databases are in a transactionally consistent state.</span></span> <span data-ttu-id="b4537-156">此外，该作业还将在目标系统上重新创建源系统上的所有 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="b4537-156">In addition, this job re-creates all of the SQL Server Agent jobs on the destination system that had been on the source system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b4537-157">应监视这些作业，以确保它们不会失败。</span><span class="sxs-lookup"><span data-stu-id="b4537-157">You should monitor these jobs to ensure that they do not fail.</span></span>  
  
10. <span data-ttu-id="b4537-158">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上，转到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="b4537-158">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], go to the following folder:</span></span>  
  
     <span data-ttu-id="b4537-159">32 位计算机： %SystemDrive%\Program Files\Microsoft BizTalk Server\<版本\>\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="b4537-159">32-bit computer: %SystemDrive%\Program Files\Microsoft BizTalk Server \<version\>\Schema\Restore</span></span>  
  
     <span data-ttu-id="b4537-160">64 位计算机： %SystemDrive%\Program Files (x86) \Microsoft BizTalk Server\<版本\>\Bins32\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="b4537-160">64-bit computer: %SystemDrive%\Program Files (x86)\Microsoft BizTalk Server \<version\>\Bins32\Schema\Restore</span></span>  
  
11. <span data-ttu-id="b4537-161">右键单击**SampleUpdateInfo.xml**，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="b4537-161">Right-click **SampleUpdateInfo.xml**, and select **Edit**.</span></span> <span data-ttu-id="b4537-162">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b4537-162">Do the following:</span></span>  
  
    -   <span data-ttu-id="b4537-163">所有实例都替换**"SourceServer"**与源系统的名称。</span><span class="sxs-lookup"><span data-stu-id="b4537-163">Replace all instances of **"SourceServer"** with the name of the source system.</span></span>  
  
    -   <span data-ttu-id="b4537-164">所有实例都替换**"DestinationServer"**与目标系统的名称。</span><span class="sxs-lookup"><span data-stu-id="b4537-164">Replace all instances of **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b4537-165">用引号将源系统和目标系统的名称括起来。</span><span class="sxs-lookup"><span data-stu-id="b4537-165">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b4537-166">如果对任何 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库进行了重命名，则还必须更新 XML 文件中的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="b4537-166">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names within the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b4537-167">如果已配置 BAM，则必须添加中的以下行将**OtherDatabases**部分**SampleUpdateInfo.xml**让 BAMAlertsApplication、 BAMAlertsNSMain 数据库的文件：</span><span class="sxs-lookup"><span data-stu-id="b4537-167">If you have configured BAM, you must add the following lines in the **OtherDatabases** section of the **SampleUpdateInfo.xml** file for the BAMAlertsApplication and BAMAlertsNSMain databases:</span></span>   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    >   
    >  <span data-ttu-id="b4537-168">如果更改了这两个数据库的默认名称，请使用实际的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="b4537-168">If you changed the default name for these two databases, please use the actual database names.</span></span>  
  
12. <span data-ttu-id="b4537-169">如果你有多个 MessageBox 数据库你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统，将另一个 MessageBoxDB 行添加到列表中，并将**IsMaster ="0"**非 master 数据库。</span><span class="sxs-lookup"><span data-stu-id="b4537-169">If you have more than one MessageBox database in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system, add another MessageBoxDB line to the list, and then set **IsMaster="0"** for the non-master databases.</span></span>  
  
13. <span data-ttu-id="b4537-170">如果使用 BAM 或规则引擎，请相应地取消这些行的注释。</span><span class="sxs-lookup"><span data-stu-id="b4537-170">If you are using BAM or the Rules Engine, uncomment these lines as appropriate.</span></span>  
  
14. <span data-ttu-id="b4537-171">如果你有任何自定义的数据库，则将其下添加 **\<OtherDatabases\>** 部分。</span><span class="sxs-lookup"><span data-stu-id="b4537-171">If you have any custom databases, add them under the **\<OtherDatabases\>** section.</span></span> <span data-ttu-id="b4537-172">请参阅[如何备份自定义数据库](../core/how-to-back-up-custom-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="b4537-172">See [How to Back Up Custom Databases](../core/how-to-back-up-custom-databases.md).</span></span>  
  
15. <span data-ttu-id="b4537-173">在完成编辑文件，请保存它，并退出。</span><span class="sxs-lookup"><span data-stu-id="b4537-173">When you are finished editing the file, save it, and exit.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b4537-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b4537-174">Next Steps</span></span>  
 [<span data-ttu-id="b4537-175">如何还原数据库</span><span class="sxs-lookup"><span data-stu-id="b4537-175">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4537-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4537-176">See Also</span></span>  
 <span data-ttu-id="b4537-177">[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="b4537-177">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="b4537-178">[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="b4537-178">[How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="b4537-179">如何备份自定义数据库</span><span class="sxs-lookup"><span data-stu-id="b4537-179">How to Back Up Custom Databases</span></span>](../core/how-to-back-up-custom-databases.md)