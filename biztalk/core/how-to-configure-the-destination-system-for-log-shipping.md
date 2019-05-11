---
title: 如何配置日志传送目标系统 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-03
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58951da7a59b041ef97b2b93e5153cc27d517b0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340862"
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="fc022-102">如何配置日志传送目标系统</span><span class="sxs-lookup"><span data-stu-id="fc022-102">How to Configure the Destination System for Log Shipping</span></span>
<span data-ttu-id="fc022-103">日志传送具有备用服务器功能，用以缩短出现系统故障时的停机时间。</span><span class="sxs-lookup"><span data-stu-id="fc022-103">Log shipping provides standby server capabilities to reduce downtime in the event of a system failure.</span></span> <span data-ttu-id="fc022-104">日志传送，您可以自动将源系统内的事务日志发送到目标系统。</span><span class="sxs-lookup"><span data-stu-id="fc022-104">Log shipping allows you to automatically send transaction logs from the source system to the destination system.</span></span> <span data-ttu-id="fc022-105">在目标系统中，事务日志还原到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库; 它们与源数据库紧密同步。</span><span class="sxs-lookup"><span data-stu-id="fc022-105">At the destination system, the transaction logs are restored to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases; keeping them closely synchronized with the source databases.</span></span>  
  
 <span data-ttu-id="fc022-106">日志传送在单个服务器和分布式的服务器环境中的工作原理。</span><span class="sxs-lookup"><span data-stu-id="fc022-106">Log shipping works in both single server and distributed server environments.</span></span> <span data-ttu-id="fc022-107">服务器或包含实时数据的服务器组称作源 （或主要） 系统。</span><span class="sxs-lookup"><span data-stu-id="fc022-107">The server or group of servers that contain live data is known as the source (or primary) system.</span></span> <span data-ttu-id="fc022-108">服务器或使用备份还原数据库备份的源生成 （或主要） 系统的服务器组称作目标 （或辅助） 系统。</span><span class="sxs-lookup"><span data-stu-id="fc022-108">The server or group of servers that are used to restore the database backups produced by the source (or primary) system is known as the destination (or secondary) system.</span></span>  
  
 <span data-ttu-id="fc022-109">[有关日志传送](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server)中的 SQL 文档提供了特定的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fc022-109">[About Log Shipping](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server) in the SQL documentation provides specific details.</span></span>  
  
 <span data-ttu-id="fc022-110">可以使用以下步骤以创建为单个源系统的一个服务器组成的目标系统。</span><span class="sxs-lookup"><span data-stu-id="fc022-110">You can use the following steps to create a destination system that consists of one server for a single source system.</span></span> <span data-ttu-id="fc022-111">如果目标系统包含多个服务器，重复每个目标服务器上的步骤。</span><span class="sxs-lookup"><span data-stu-id="fc022-111">If the destination system contains multiple servers, repeat the steps on each destination server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fc022-112">请总是在某个安全位置保留备份文件的一个副本。</span><span class="sxs-lookup"><span data-stu-id="fc022-112">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="fc022-113">即使你进行了日志备份，在没有备份文件的情况下也无法还原数据库。</span><span class="sxs-lookup"><span data-stu-id="fc022-113">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fc022-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="fc022-114">Prerequisites</span></span>  
* <span data-ttu-id="fc022-115">以的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="fc022-115">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
* <span data-ttu-id="fc022-116">在源和目标系统上使用相同版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="fc022-116">Use the same version of SQL Server on the source and destination systems.</span></span> <span data-ttu-id="fc022-117">SQL Server 必须安装在源和目标系统上的同一相对位置。</span><span class="sxs-lookup"><span data-stu-id="fc022-117">SQL Server must be installed in the same relative location on the source and destination systems.</span></span>  
  
* <span data-ttu-id="fc022-118">SQL 事务日志的目录 (。LDF 文件） 在源系统必须也存在于目标系统。</span><span class="sxs-lookup"><span data-stu-id="fc022-118">The directory for SQL transaction log (.LDF files) on the source system must also exist on the destination system.</span></span> <span data-ttu-id="fc022-119">如果此目录不在目标系统上，创建具有相同名称和源系统上的权限的目录。</span><span class="sxs-lookup"><span data-stu-id="fc022-119">If this directory is not on the destination system, create the directory with the same name and permissions as on the source system.</span></span>  
  
### <a name="configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="fc022-120">配置日志传送的目标系统</span><span class="sxs-lookup"><span data-stu-id="fc022-120">Configure the destination system for log shipping</span></span>  
  
1. <span data-ttu-id="fc022-121">在目标系统上，打开**SQL Server Management Studio**，并连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="fc022-121">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span> <span data-ttu-id="fc022-122">选择**主**从可用数据库。</span><span class="sxs-lookup"><span data-stu-id="fc022-122">Select **master** from Available Databases.</span></span>  
  
2. <span data-ttu-id="fc022-123">上**文件**菜单中，**打开**以下 SQL 脚本：</span><span class="sxs-lookup"><span data-stu-id="fc022-123">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
   ```  
  
3. <span data-ttu-id="fc022-124">上**查询**菜单中，选择**Execute**。</span><span class="sxs-lookup"><span data-stu-id="fc022-124">On the **Query** menu, select **Execute**.</span></span>  
  
    <span data-ttu-id="fc022-125">*Logshipping_destination_schema 将*删除并重新创建用于还原目标系统上的源数据库的表。</span><span class="sxs-lookup"><span data-stu-id="fc022-125">The *LogShipping_Destination_Schema* drops and recreates the tables used for restoring the source databases on the destination system.</span></span> <span data-ttu-id="fc022-126">这包括表以存储数据库正在恢复的源系统的 BizTalkMgmtDb 数据库导入的备份历史记录副本的列表和有关 SQL Server 代理作业的信息配置为对源数据库运行。</span><span class="sxs-lookup"><span data-stu-id="fc022-126">This includes tables to store the list of databases being recovered, copies of the backup history imported from the source system's BizTalkMgmtDb database, and information about SQL Server Agent jobs configured to run against the source databases.</span></span>  
  
4. <span data-ttu-id="fc022-127">上**文件**菜单中，**打开**以下 SQL 脚本：</span><span class="sxs-lookup"><span data-stu-id="fc022-127">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
   ```  
  
5. <span data-ttu-id="fc022-128">上**查询**菜单中，选择**Execute**。</span><span class="sxs-lookup"><span data-stu-id="fc022-128">On the **Query** menu, select **Execute**.</span></span>  
  
6. <span data-ttu-id="fc022-129">在计算机或计算机已标识为目标系统中，打开**SQL Server Management Studio**并连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="fc022-129">On the computer or computers you have identified as the destination system, open **SQL Server Management Studio** and connect to the SQL Server.</span></span>  
  
7. <span data-ttu-id="fc022-130">选择**新查询**。</span><span class="sxs-lookup"><span data-stu-id="fc022-130">Select **New Query**.</span></span> <span data-ttu-id="fc022-131">在查询窗口中，粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="fc022-131">In the query window, paste the following command:</span></span>  
  
   ```  
   exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
   @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
   @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
   @SourceServerName = null, -- null indicates that this destination server restores all databases  
   @fLinkServers = 1 -- 1 automatically links the server to the management database  
   ```  
  
    <span data-ttu-id="fc022-132">然后：</span><span class="sxs-lookup"><span data-stu-id="fc022-132">Then:</span></span>  
  
   1.  <span data-ttu-id="fc022-133">在目标系统上启用 **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**。</span><span class="sxs-lookup"><span data-stu-id="fc022-133">On the destination system, enable **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**.</span></span>  
  
   2.  <span data-ttu-id="fc022-134">在查询窗口中，替换*\<MyLogShippingSolution\>* 的有意义的说明，用单引号引起。</span><span class="sxs-lookup"><span data-stu-id="fc022-134">In the query window, replace *\<MyLogShippingSolution\>* with a meaningful description, surrounded by single quotes.</span></span>  
  
   3.  <span data-ttu-id="fc022-135">在查询窗口中，替换*\<BizTalkServerManagementDatabaseName\>* 并*\<BizTalkServerManagementDatabaseServer\>* 与名称和源 BizTalk 管理数据库，用单引号引起的位置。</span><span class="sxs-lookup"><span data-stu-id="fc022-135">In the query window, replace *\<BizTalkServerManagementDatabaseName\>* and *\<BizTalkServerManagementDatabaseServer\>* with the name and location of your source BizTalk Management database, surrounded by single quotes.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fc022-136">如果你有多个源服务器，则可以每个源服务器还原到其自己的目标服务器。</span><span class="sxs-lookup"><span data-stu-id="fc022-136">If you have more than one source server, you can restore each source server to its own destination server.</span></span> <span data-ttu-id="fc022-137">每个目标服务器上，在 **@SourceServerName = null**参数，替换*null*具有适当的源服务器的名称，用单引号引起 (例如，  **@SourceServerName = 'MySourceServer'**)。</span><span class="sxs-lookup"><span data-stu-id="fc022-137">On each destination server, in the **@SourceServerName = null** parameter, replace *null* with the name of the appropriate source server, surrounded by single quotes (for example, **@SourceServerName = 'MySourceServer',**).</span></span>  
  
8. <span data-ttu-id="fc022-138">上**查询**菜单中，选择**Execute**。</span><span class="sxs-lookup"><span data-stu-id="fc022-138">On the **Query** menu, select **Execute**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="fc022-139">如果查询失败，则解决该问题与查询后，您必须重新开始此过程来重新配置目标系统的步骤 1 中。</span><span class="sxs-lookup"><span data-stu-id="fc022-139">If the query fails, after you fix the problem with the query, you must start over from step 1 of this procedure to reconfigure the destination system.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fc022-140">在目标系统上的还原作业尝试重新创建每个还原的数据库在同一位置中的日志和数据文件，因为它们存在于源数据库服务器上。</span><span class="sxs-lookup"><span data-stu-id="fc022-140">The restore jobs on the destination system attempt to recreate the log and data files for each restored database in the same location as they existed on the source database server.</span></span>  
  
9. <span data-ttu-id="fc022-141">在目标系统上**SQL Server Management Studio**，展开**SQL Server 代理**，然后展开**作业**。</span><span class="sxs-lookup"><span data-stu-id="fc022-141">On the destination system in **SQL Server Management Studio**, expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
     <span data-ttu-id="fc022-142">在详细信息窗格中，有三个新作业：</span><span class="sxs-lookup"><span data-stu-id="fc022-142">In the details pane, there are three new jobs:</span></span>  
  
   - <span data-ttu-id="fc022-143">**BTS 日志传送获取备份历史记录**</span><span class="sxs-lookup"><span data-stu-id="fc022-143">**BTS Log Shipping Get Backup History**</span></span>  
  
      <span data-ttu-id="fc022-144">此 BizTalk 作业将备份历史记录从源移到目标。</span><span class="sxs-lookup"><span data-stu-id="fc022-144">This BizTalk job moves backup history records from the source to the destination.</span></span> <span data-ttu-id="fc022-145">它是默认计划每分钟运行。</span><span class="sxs-lookup"><span data-stu-id="fc022-145">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="fc022-146">若要将历史记录从源分片移动到目标尽可能频繁地运行此作业。</span><span class="sxs-lookup"><span data-stu-id="fc022-146">This job runs as frequently as possible in order to move history records from the source to the destination.</span></span> <span data-ttu-id="fc022-147">出现系统故障到源系统时，标识为目标系统的服务器继续处理已导入的历史记录。</span><span class="sxs-lookup"><span data-stu-id="fc022-147">In the event of a system failure to the source system, the server that you identified as the destination system continues to process the history records that have already been imported.</span></span>  
  
   - <span data-ttu-id="fc022-148">**BTS 服务器日志传送还原数据库**</span><span class="sxs-lookup"><span data-stu-id="fc022-148">**BTS Server Log Shipping Restore Databases**</span></span>  
  
      <span data-ttu-id="fc022-149">此 BizTalk 作业可将指定数据库的源的备份文件还原到目标服务器。</span><span class="sxs-lookup"><span data-stu-id="fc022-149">This BizTalk job restores backup files for the given databases for the source to the destination server.</span></span> <span data-ttu-id="fc022-150">它是默认计划每分钟运行。</span><span class="sxs-lookup"><span data-stu-id="fc022-150">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="fc022-151">此作业会连续运行而无法完成，只要有要还原的备份文件。</span><span class="sxs-lookup"><span data-stu-id="fc022-151">This job runs continuously without completing as long as there are backup files to restore.</span></span> <span data-ttu-id="fc022-152">作为额外的预防措施，你可以运行此作业一次以确保其完成。</span><span class="sxs-lookup"><span data-stu-id="fc022-152">As an extra precaution, you can run this job an additional time to ensure that it is complete.</span></span>  
  
   - <span data-ttu-id="fc022-153">**BTS 日志传送还原到标记**</span><span class="sxs-lookup"><span data-stu-id="fc022-153">**BTS Log Shipping Restore To Mark**</span></span>  
  
      <span data-ttu-id="fc022-154">此 BizTalk 作业将所有数据库还原到上次日志备份中的一个标记。</span><span class="sxs-lookup"><span data-stu-id="fc022-154">This BizTalk job restores all of the databases to a mark in the last log backup.</span></span> <span data-ttu-id="fc022-155">这可确保所有数据库处于事务一致的状态。</span><span class="sxs-lookup"><span data-stu-id="fc022-155">This ensures that all of the databases are in a transactionally consistent state.</span></span> <span data-ttu-id="fc022-156">此外，此作业将重新创建所有源系统必须已在目标系统上的 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="fc022-156">In addition, this job re-creates all of the SQL Server Agent jobs on the destination system that had been on the source system.</span></span>  
  
     > [!IMPORTANT]
     >  <span data-ttu-id="fc022-157">你应监视这些作业，以确保它们不失败。</span><span class="sxs-lookup"><span data-stu-id="fc022-157">You should monitor these jobs to ensure that they do not fail.</span></span>  
  
10. <span data-ttu-id="fc022-158">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请转到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="fc022-158">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], go to the following folder:</span></span>  
  
     <span data-ttu-id="fc022-159">32 位计算机： %SystemDrive%\Program Files\Microsoft BizTalk Server\<版本\>\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="fc022-159">32-bit computer: %SystemDrive%\Program Files\Microsoft BizTalk Server \<version\>\Schema\Restore</span></span>  
  
     <span data-ttu-id="fc022-160">64 位计算机： %SystemDrive%\Program 文件 (x86) \Microsoft BizTalk Server\<版本\>\Bins32\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="fc022-160">64-bit computer: %SystemDrive%\Program Files (x86)\Microsoft BizTalk Server \<version\>\Bins32\Schema\Restore</span></span>  
  
11. <span data-ttu-id="fc022-161">右键单击**SampleUpdateInfo.xml**，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="fc022-161">Right-click **SampleUpdateInfo.xml**, and select **Edit**.</span></span> <span data-ttu-id="fc022-162">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc022-162">Do the following:</span></span>  
  
    -   <span data-ttu-id="fc022-163">所有实例替换都为**SourceServer**与源系统的名称。</span><span class="sxs-lookup"><span data-stu-id="fc022-163">Replace all instances of **"SourceServer"** with the name of the source system.</span></span>  
  
    -   <span data-ttu-id="fc022-164">所有实例替换都为**DestinationServer**与目标系统的名称。</span><span class="sxs-lookup"><span data-stu-id="fc022-164">Replace all instances of **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fc022-165">包括源和目标系统的名称周围的引号。</span><span class="sxs-lookup"><span data-stu-id="fc022-165">Include the quotation marks around the name of the source and destination systems.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="fc022-166">如果您重命名的任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，则还必须更新 XML 文件中的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="fc022-166">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names within the XML file.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="fc022-167">如果已配置 BAM，则必须添加以下行中的**OtherDatabases**一部分**SampleUpdateInfo.xml** BAMAlertsApplication 和 BAMAlertsNSMain 数据库的文件：</span><span class="sxs-lookup"><span data-stu-id="fc022-167">If you have configured BAM, you must add the following lines in the **OtherDatabases** section of the **SampleUpdateInfo.xml** file for the BAMAlertsApplication and BAMAlertsNSMain databases:</span></span>   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    > 
    >  <span data-ttu-id="fc022-168">如果更改这两个数据库的默认名称，请使用实际的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="fc022-168">If you changed the default name for these two databases, please use the actual database names.</span></span>  
  
12. <span data-ttu-id="fc022-169">如果您有多个 MessageBox 数据库您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统中，到列表中，添加其他 MessageBoxDB 行，然后设置**IsMaster ="0"** 为非主数据库。</span><span class="sxs-lookup"><span data-stu-id="fc022-169">If you have more than one MessageBox database in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system, add another MessageBoxDB line to the list, and then set **IsMaster="0"** for the non-master databases.</span></span>  
  
13. <span data-ttu-id="fc022-170">如果使用 BAM 或规则引擎，取消注释根据这些行。</span><span class="sxs-lookup"><span data-stu-id="fc022-170">If you are using BAM or the Rules Engine, uncomment these lines as appropriate.</span></span>  
  
14. <span data-ttu-id="fc022-171">如果有任何自定义数据库，将其下添加**\<OtherDatabases\>** 部分。</span><span class="sxs-lookup"><span data-stu-id="fc022-171">If you have any custom databases, add them under the **\<OtherDatabases\>** section.</span></span> <span data-ttu-id="fc022-172">请参阅[如何备份自定义数据库](../core/how-to-back-up-custom-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="fc022-172">See [How to Back Up Custom Databases](../core/how-to-back-up-custom-databases.md).</span></span>  
  
15. <span data-ttu-id="fc022-173">在完成编辑文件，请保存该文件，并退出。</span><span class="sxs-lookup"><span data-stu-id="fc022-173">When you are finished editing the file, save it, and exit.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fc022-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fc022-174">Next Steps</span></span>  
 [<span data-ttu-id="fc022-175">如何还原数据库</span><span class="sxs-lookup"><span data-stu-id="fc022-175">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc022-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc022-176">See Also</span></span>  
 <span data-ttu-id="fc022-177">[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="fc022-177">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="fc022-178">[如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="fc022-178">[How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="fc022-179">如何备份自定义数据库</span><span class="sxs-lookup"><span data-stu-id="fc022-179">How to Back Up Custom Databases</span></span>](../core/how-to-back-up-custom-databases.md)