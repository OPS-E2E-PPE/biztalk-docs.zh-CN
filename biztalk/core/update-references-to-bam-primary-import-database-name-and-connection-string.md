---
title: 更新 BAM 主导入数据库名称和连接字符串 |Microsoft Docs
ms.custom: ''
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846aa3b08ce6cce9b2334da72440cf5ba918e5d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003134"
---
# <a name="update-references-to-the-bam-primary-import-database-name-and-connection-string"></a><span data-ttu-id="da0c0-102">更新对 BAM 主导入数据库名称和连接字符串引用</span><span class="sxs-lookup"><span data-stu-id="da0c0-102">Update References to the BAM Primary Import Database Name and Connection String</span></span>
<span data-ttu-id="da0c0-103">如果备份了 BAMPrimaryImport 数据库，则在系统或数据发生故障时，可以将该备份还原到其他计算机上，然后重命名该备份。</span><span class="sxs-lookup"><span data-stu-id="da0c0-103">If you backed up your BAMPrimaryImport database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="da0c0-104">BAM 事件总线服务将事件数据从 MessageBox 数据库移到 BAMPrimaryImport 数据库。</span><span class="sxs-lookup"><span data-stu-id="da0c0-104">The BAM Event Bus service moves event data from the MessageBox database to the BAMPrimaryImport database.</span></span> <span data-ttu-id="da0c0-105">BAM 事件总线服务包括故障容错逻辑，使它能够恢复并重新启动从意外故障而不会丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="da0c0-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="da0c0-106">有关 BAM 事件总线服务的详细信息，请参阅[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)。</span><span class="sxs-lookup"><span data-stu-id="da0c0-106">For more information about the BAM Event Bus service, see [Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md).</span></span>  
  
 <span data-ttu-id="da0c0-107">若要还原 BAMPrimaryImport 数据库，请执行中的步骤[如何还原您数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="da0c0-107">To restore the BAMPrimaryImport database, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="da0c0-108">此外，还必须执行下列常规步骤后, 跟介绍详细信息中的步骤的过程：</span><span class="sxs-lookup"><span data-stu-id="da0c0-108">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="da0c0-109">更新所有 BAM DTS 包中的 SQL 连接 1，以引用新数据库名称。</span><span class="sxs-lookup"><span data-stu-id="da0c0-109">Update the SQL Connection 1 in all BAM DTS packages to refer to the new database name.</span></span>  
  
-   <span data-ttu-id="da0c0-110">使用新的数据库名称更新 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="da0c0-110">Update the web.config file with the new database name.</span></span>  
  
-   <span data-ttu-id="da0c0-111">更新对 BAMPrimaryImport 数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="da0c0-111">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="da0c0-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="da0c0-112">Prerequisites</span></span>  
<span data-ttu-id="da0c0-113">以 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="da0c0-113">Sign in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-references"></a><span data-ttu-id="da0c0-114">更新引用</span><span class="sxs-lookup"><span data-stu-id="da0c0-114">Update the references</span></span>  
  
1. <span data-ttu-id="da0c0-115">停止任何 BAM 多维数据集更新和数据维护数据转换服务 (DTS) 包，或者阻止它们运行，直到 BAMPrimaryImport 数据库的还原完成为止。</span><span class="sxs-lookup"><span data-stu-id="da0c0-115">Stop any BAM cube update and data maintenance Data Transformation Services (DTS) packages, or prevent them from running until you have restored the BAMPrimaryImport database.</span></span>  
  
2. <span data-ttu-id="da0c0-116">停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试导入数据库的更多的数据。</span><span class="sxs-lookup"><span data-stu-id="da0c0-116">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
   1.  <span data-ttu-id="da0c0-117">从**启动**菜单中，键入**services.msc**，然后打开**Services**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-117">From the **Start** menu, type **services.msc**, and open **Services**.</span></span>  
  
   2.  <span data-ttu-id="da0c0-118">右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后**停止**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-118">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service, and then **Stop**.</span></span>  
  
3. <span data-ttu-id="da0c0-119">还原 BAMPrimaryImport 数据库 (中的步骤[如何还原您数据库](../core/how-to-restore-your-databases.md))。</span><span class="sxs-lookup"><span data-stu-id="da0c0-119">Restore the BAMPrimaryImport database (steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md)).</span></span>  
  
4. <span data-ttu-id="da0c0-120">更新以下 Web.Config 文件：</span><span class="sxs-lookup"><span data-stu-id="da0c0-120">Update the following Web.Config files:</span></span>  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="da0c0-121">\BAMPortal\BamManagementService\Web.Config。</span><span class="sxs-lookup"><span data-stu-id="da0c0-121">\BAMPortal\BamManagementService\Web.Config.</span></span>  
  
      <span data-ttu-id="da0c0-122">替换*\<ServerName\>* 具有新的服务器名称的字符串并*\<DatabaseName\>* 使用新的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="da0c0-122">Replace the *\<ServerName\>* string with the new server name, and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="da0c0-123">更新以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="da0c0-123">Update the following connection strings:</span></span>  
  
      <span data-ttu-id="da0c0-124">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="da0c0-124">\<appSettings\></span></span>  
  
      <span data-ttu-id="da0c0-125"><add key="BamServer" value="*\<ServerName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="da0c0-125"><add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
      <span data-ttu-id="da0c0-126">< 添加 key ="BamDatabase"value ="*\<DatabaseName\>*"/\></span><span class="sxs-lookup"><span data-stu-id="da0c0-126"><add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
      <span data-ttu-id="da0c0-127">\<add key="MaxResultRows" value="2000" /\></span><span class="sxs-lookup"><span data-stu-id="da0c0-127">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
      <span data-ttu-id="da0c0-128">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="da0c0-128">\</appSettings\></span></span>  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="da0c0-129">\BAMPortal\BamQueryService\Web.Config。</span><span class="sxs-lookup"><span data-stu-id="da0c0-129">\BAMPortal\BamQueryService\Web.Config.</span></span>  
  
      <span data-ttu-id="da0c0-130">替换*\<ServerName\>* 具有新的服务器名称的字符串并*\<DatabaseName\>* 使用新的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="da0c0-130">Replace the *\<ServerName\>* string with the new server name and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="da0c0-131">更新以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="da0c0-131">Update the following connection strings:</span></span>  
  
      <span data-ttu-id="da0c0-132">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="da0c0-132">\<appSettings\></span></span>  
  
      <span data-ttu-id="da0c0-133">\<add key="BamServer" value="*\<ServerName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="da0c0-133">\<add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
      <span data-ttu-id="da0c0-134">\<添加键 ="BamDatabase"value ="*\<DatabaseName\>*"/\></span><span class="sxs-lookup"><span data-stu-id="da0c0-134">\<add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
      <span data-ttu-id="da0c0-135">\<add key="MaxResultRows" value="2000" /\></span><span class="sxs-lookup"><span data-stu-id="da0c0-135">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
      <span data-ttu-id="da0c0-136">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="da0c0-136">\</appSettings\></span></span>  
  
5. <span data-ttu-id="da0c0-137">打开命令提示符 (开始菜单 > 命令提示符下)，并导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore。</span><span class="sxs-lookup"><span data-stu-id="da0c0-137">Open a command prompt (Start menu > Command Prompt), and navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore.</span></span>  
  
6. <span data-ttu-id="da0c0-138">右键单击**SampleUpdateInfo.xml**，并**编辑**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-138">Right-click **SampleUpdateInfo.xml**, and **Edit**.</span></span>  
  
   1.  <span data-ttu-id="da0c0-139">注释掉所有除外 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的数据库部分。</span><span class="sxs-lookup"><span data-stu-id="da0c0-139">Comment out all of the database sections except for the  OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span> 
   2.  <span data-ttu-id="da0c0-140">对于 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报部分，设置**SourceServer**并**目标服务器**到这些数据库所在的现有服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="da0c0-140">For the OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the **SourceServer** and **Destination Server** to the name of the existing server where those databases reside.</span></span>  
  
   3.  <span data-ttu-id="da0c0-141">对于 PrimaryImportDatabase，设置**SourceServer**到移动 BAM 主导入数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="da0c0-141">For PrimaryImportDatabase, set the **"SourceServer"** to the name of the server where you have moved the BAM Primary Import database.</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="da0c0-142">用引号将源系统和目标系统的名称括起来。</span><span class="sxs-lookup"><span data-stu-id="da0c0-142">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="da0c0-143">如果您重命名任何 BizTalk Server 数据库，请务必也更新数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="da0c0-143">If you renamed any of the BizTalk Server databases, be sure to also update the database names.</span></span>  
  
   4.  <span data-ttu-id="da0c0-144">在完成编辑文件，请保存该文件，并退出。</span><span class="sxs-lookup"><span data-stu-id="da0c0-144">When you are finished editing the file, save it, and exit.</span></span>  
  
7. <span data-ttu-id="da0c0-145">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="da0c0-145">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="da0c0-146">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="da0c0-146">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="da0c0-147">一次只能运行 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="da0c0-147">Only run UpdateDatabase.vbs once.</span></span>  
   > 
   >  <span data-ttu-id="da0c0-148">在 64 位计算机上 64 位命令提示符下运行 UpdateDatabase.vbs。</span><span class="sxs-lookup"><span data-stu-id="da0c0-148">On 64-bit computers, run UpdateDatabase.vbs from a 64-bit command prompt.</span></span>  
  
8. <span data-ttu-id="da0c0-149">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="da0c0-149">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="da0c0-150">\Tracking</span><span class="sxs-lookup"><span data-stu-id="da0c0-150">\Tracking</span></span>  
  
9. <span data-ttu-id="da0c0-151">在命令提示符下，编辑 bm.exe.config、 将项值更改为新的服务器名称，="DefaultServer"，然后保存该文件。</span><span class="sxs-lookup"><span data-stu-id="da0c0-151">At the command prompt, edit bm.exe.config, change the value of key="DefaultServer" to the new server name, and then save the file.</span></span>  
  
10. <span data-ttu-id="da0c0-152">更新对 BAMPrimaryImport 数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="da0c0-152">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="da0c0-153">对于每个文件：</span><span class="sxs-lookup"><span data-stu-id="da0c0-153">For each file:</span></span>  
  
    1.  <span data-ttu-id="da0c0-154">打开 Excel 实时数据文件。</span><span class="sxs-lookup"><span data-stu-id="da0c0-154">Open the Excel live data file.</span></span> <span data-ttu-id="da0c0-155">以 _LiveData.xls 结尾的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="da0c0-155">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="da0c0-156">上**BAM**菜单上，单击**BAM 数据库连接**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-156">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="da0c0-157">在中**选择 BAM 数据库**对话框中，输入 SQL Server 和 BAMPrimaryImport 数据库，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-157">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="da0c0-158">上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-158">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="da0c0-159">在“文件”菜单上，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="da0c0-159">On the **File** menu, click **Save**.</span></span>  
  
11. <span data-ttu-id="da0c0-160">重新启动 BizTalk 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="da0c0-160">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="da0c0-161">打开 **“services.msc”**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-161">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="da0c0-162">右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后**启动**。</span><span class="sxs-lookup"><span data-stu-id="da0c0-162">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service, and then **Start**.</span></span>  
  
12. <span data-ttu-id="da0c0-163">启用任何 BAM 多维数据集更新和数据维护 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="da0c0-163">Enable any BAM cube update and data maintenance DTS packages.</span></span>  
  
13. <span data-ttu-id="da0c0-164">若要解决任何未完成的跟踪实例，请参阅[解决未完成的活动实例](../core/how-to-resolve-incomplete-activity-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="da0c0-164">To resolve any incomplete trace instances, see [Resolve Incomplete Activity Instances](../core/how-to-resolve-incomplete-activity-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da0c0-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="da0c0-165">See Also</span></span>  
 [<span data-ttu-id="da0c0-166">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="da0c0-166">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
