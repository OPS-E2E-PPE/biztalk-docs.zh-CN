---
title: "如何更新对 BAM 主导入数据库名称和连接字符串引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring [BAM], connection strings
- Primary Import database [BAM], updating references
- connection strings, restoring
- connection strings, BAM
- restoring, BAM
- restoring [BAM], Primary Import database
- restoring [BAM], updating references
- Primary Import database [BAM], restoring
- BAM, restoring
- restoring, connection strings
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23efa3df9c59732c8459018a886f7f499d268eff
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-references-to-the-bam-primary-import-database-name-and-connection-string"></a><span data-ttu-id="f98f9-102">如何更新对 BAM 主导入数据库名称和连接字符串的引用</span><span class="sxs-lookup"><span data-stu-id="f98f9-102">How to Update References to the BAM Primary Import Database Name and Connection String</span></span>
<span data-ttu-id="f98f9-103">如果备份了 BAMPrimaryImport 数据库，则在系统或数据发生故障时，可以将该备份还原到其他计算机上，然后重命名该备份。</span><span class="sxs-lookup"><span data-stu-id="f98f9-103">If you backed up your BAMPrimaryImport database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="f98f9-104">BAM 事件总线服务将事件数据从 MessageBox 数据库移到 BAMPrimaryImport 数据库。</span><span class="sxs-lookup"><span data-stu-id="f98f9-104">The BAM Event Bus service moves event data from the MessageBox database to the BAMPrimaryImport database.</span></span> <span data-ttu-id="f98f9-105">BAM 事件 Bus 服务包括故障容错逻辑，使它能够恢复并重新启动从意外的故障，而不会丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="f98f9-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="f98f9-106">有关 BAM 事件总线服务的详细信息，请参阅[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)。</span><span class="sxs-lookup"><span data-stu-id="f98f9-106">For more information about the BAM Event Bus service, see [Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md).</span></span>  
  
 <span data-ttu-id="f98f9-107">若要还原 BAMPrimaryImport 数据库，请执行中的步骤[如何还原您的数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="f98f9-107">To restore the BAMPrimaryImport database, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="f98f9-108">此外，你必须执行下列常规步骤后, 跟一个描述各步骤的详细信息的过程：</span><span class="sxs-lookup"><span data-stu-id="f98f9-108">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="f98f9-109">更新所有 BAM DTS 包中的 SQL 连接 1，以引用新的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="f98f9-109">Update the SQL Connection 1 in all BAM DTS packages to refer to the new database name.</span></span>  
  
-   <span data-ttu-id="f98f9-110">使用新的数据库名称更新 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="f98f9-110">Update the web.config file with the new database name.</span></span>  
  
-   <span data-ttu-id="f98f9-111">更新对 BAMPrimaryImport 所有 BAM Livedata Microsoft Excel 文件中的数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="f98f9-111">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f98f9-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="f98f9-112">Prerequisites</span></span>  
 <span data-ttu-id="f98f9-113">必须以 BizTalk Server Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="f98f9-113">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bamprimaryimport-database-name-and-connection-string"></a><span data-ttu-id="f98f9-114">更新对 BAMPrimaryImport 数据库名称和连接字符串的引用</span><span class="sxs-lookup"><span data-stu-id="f98f9-114">To update references to the BAMPrimaryImport database name and connection string</span></span>  
  
1.  <span data-ttu-id="f98f9-115">停止任何 BAM 多维数据集更新和数据维护数据转换服务 (DTS) 包，或者阻止它们运行，直到 BAMPrimaryImport 数据库的还原完成为止。</span><span class="sxs-lookup"><span data-stu-id="f98f9-115">Stop any BAM cube update and data maintenance Data Transformation Services (DTS) packages, or prevent them from running until you have restored the BAMPrimaryImport database.</span></span>  
  
2.  <span data-ttu-id="f98f9-116">停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试将更多的数据导入到数据库。</span><span class="sxs-lookup"><span data-stu-id="f98f9-116">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
    1.  <span data-ttu-id="f98f9-117">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-117">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="f98f9-118">右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-118">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="f98f9-119">还原 BAMPrimaryImport 数据库，请执行中的步骤[如何还原您的数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="f98f9-119">Restore the BAMPrimaryImport database, performing the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span>  
  
4.  <span data-ttu-id="f98f9-120">更新以下的 Web.Config 文件：</span><span class="sxs-lookup"><span data-stu-id="f98f9-120">Update the following Web.Config files:</span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f98f9-121">BAMPortal\BamManagementService\Web.Config。</span><span class="sxs-lookup"><span data-stu-id="f98f9-121">BAMPortal\BamManagementService\Web.Config.</span></span>  
  
         <span data-ttu-id="f98f9-122">替换 *\<ServerName\>* 字符串替换为新的服务器名称和 *\<DatabaseName\>* 使用新的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="f98f9-122">Replace the *\<ServerName\>* string with the new server name and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="f98f9-123">更新的以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="f98f9-123">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="f98f9-124">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="f98f9-124">\<appSettings\></span></span>  
  
         <span data-ttu-id="f98f9-125">< 添加 key ="BamServer"value ="*\<ServerName\>*"/\></span><span class="sxs-lookup"><span data-stu-id="f98f9-125"><add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
         <span data-ttu-id="f98f9-126">< 添加 key ="BamDatabase"value ="*\<DatabaseName\>*"/\></span><span class="sxs-lookup"><span data-stu-id="f98f9-126"><add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
         <span data-ttu-id="f98f9-127">\<添加项 ="MaxResultRows"value ="2000"/\></span><span class="sxs-lookup"><span data-stu-id="f98f9-127">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
         <span data-ttu-id="f98f9-128">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="f98f9-128">\</appSettings\></span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f98f9-129">BAMPortal\BamQueryService\Web.Config。</span><span class="sxs-lookup"><span data-stu-id="f98f9-129">BAMPortal\BamQueryService\Web.Config.</span></span>  
  
         <span data-ttu-id="f98f9-130">替换 *\<ServerName\>* 字符串替换为新的服务器名称和 *\<DatabaseName\>* 使用新的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="f98f9-130">Replace the *\<ServerName\>* string with the new server name and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="f98f9-131">更新的以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="f98f9-131">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="f98f9-132">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="f98f9-132">\<appSettings\></span></span>  
  
         <span data-ttu-id="f98f9-133">\<添加项 ="BamServer"value ="*\<ServerName\>*"/\></span><span class="sxs-lookup"><span data-stu-id="f98f9-133">\<add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
         <span data-ttu-id="f98f9-134">\<添加项 ="BamDatabase"value ="*\<DatabaseName\>*"/\></span><span class="sxs-lookup"><span data-stu-id="f98f9-134">\<add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
         <span data-ttu-id="f98f9-135">\<添加项 ="MaxResultRows"value ="2000"/\></span><span class="sxs-lookup"><span data-stu-id="f98f9-135">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
         <span data-ttu-id="f98f9-136">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="f98f9-136">\</appSettings\></span></span>  
  
5.  <span data-ttu-id="f98f9-137">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f98f9-138">导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore。</span><span class="sxs-lookup"><span data-stu-id="f98f9-138">Navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore.</span></span>  
  
7.  <span data-ttu-id="f98f9-139">右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-139">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
    1.  <span data-ttu-id="f98f9-140">注释掉所有除外 BizTalkMgmtDb、 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的数据库部分。</span><span class="sxs-lookup"><span data-stu-id="f98f9-140">Comment out all of the database sections except for the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span>  
  
    2.  <span data-ttu-id="f98f9-141">BizTalkMgmtDb、 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase，和警报的部分，设置**"SourceServer"**和**"目标服务器"**为这些数据库驻留的现有服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f98f9-141">For the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the **"SourceServer"** and **"Destination Server"** to the name of the existing server where those databases reside.</span></span>  
  
    3.  <span data-ttu-id="f98f9-142">对于 PrimaryImportDatabase，设置**"SourceServer"**移动了 BAM 主导入数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f98f9-142">For PrimaryImportDatabase, set the **"SourceServer"** to the name of the server where you have moved the BAM Primary Import database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="f98f9-143">用引号将源系统和目标系统的名称括起来。</span><span class="sxs-lookup"><span data-stu-id="f98f9-143">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f98f9-144">如果对任何 BizTalk Server 数据库进行了重命名，则必须也相应地更新这些数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f98f9-144">If you renamed any of the BizTalk Server databases, you must also update the database names as appropriate.</span></span>  
  
    4.  <span data-ttu-id="f98f9-145">编辑完此文件后，请进行保存然后退出。</span><span class="sxs-lookup"><span data-stu-id="f98f9-145">When you are finished editing the file, save it and exit.</span></span>  
  
8.  <span data-ttu-id="f98f9-146">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="f98f9-146">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="f98f9-147">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="f98f9-147">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f98f9-148">只需运行 UpdateDatabase.vbs 一次。</span><span class="sxs-lookup"><span data-stu-id="f98f9-148">You only need to run UpdateDatabase.vbs once.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f98f9-149">在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="f98f9-149">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span>  
  
9. <span data-ttu-id="f98f9-150">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="f98f9-150">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f98f9-151">Tracking</span><span class="sxs-lookup"><span data-stu-id="f98f9-151">Tracking</span></span>  
  
10. <span data-ttu-id="f98f9-152">在命令提示符下，编辑 bm.exe.config，将密钥的值更改为新的服务器名称 ="DefaultServer"，然后保存该文件。</span><span class="sxs-lookup"><span data-stu-id="f98f9-152">At the command prompt, edit bm.exe.config, change the value of key="DefaultServer" to the new server name, and then save the file.</span></span>  
  
11. <span data-ttu-id="f98f9-153">更新对 BAMPrimaryImport 所有 BAM Livedata Microsoft Excel 文件中的数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="f98f9-153">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="f98f9-154">对于每个文件：</span><span class="sxs-lookup"><span data-stu-id="f98f9-154">For each file:</span></span>  
  
    1.  <span data-ttu-id="f98f9-155">打开 Excel 实时数据文件。</span><span class="sxs-lookup"><span data-stu-id="f98f9-155">Open the Excel live data file.</span></span> <span data-ttu-id="f98f9-156">以 _LiveData.xls 结尾的文件名称。</span><span class="sxs-lookup"><span data-stu-id="f98f9-156">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="f98f9-157">上**BAM**菜单上，单击**BAM 数据库连接**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-157">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="f98f9-158">在**选择 BAM 数据库**对话框中，输入 SQL Server 和 BAMPrimaryImport 数据库，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-158">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="f98f9-159">上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-159">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="f98f9-160">在“文件”菜单上，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="f98f9-160">On the **File** menu, click **Save**.</span></span>  
  
12. <span data-ttu-id="f98f9-161">重新启动 BizTalk 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="f98f9-161">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="f98f9-162">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-162">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="f98f9-163">右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="f98f9-163">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
13. <span data-ttu-id="f98f9-164">启用任何 BAM 多维数据集更新和数据维护 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="f98f9-164">Enable any BAM cube update and data maintenance DTS packages.</span></span>  
  
14. <span data-ttu-id="f98f9-165">若要解决任何不完整的跟踪实例，请参阅[如何解决未完成的活动实例](../core/how-to-resolve-incomplete-activity-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="f98f9-165">To resolve any incomplete trace instances, see [How to Resolve Incomplete Activity Instances](../core/how-to-resolve-incomplete-activity-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98f9-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f98f9-166">See Also</span></span>  
 [<span data-ttu-id="f98f9-167">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="f98f9-167">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)