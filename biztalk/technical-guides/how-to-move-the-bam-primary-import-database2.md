---
title: 如何移动 BAM 主导入数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72c43e5048d55c028bb689bd06e5f8c5844cc064
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986702"
---
# <a name="how-to-move-the-bam-primary-import-database"></a><span data-ttu-id="5c6e8-102">如何移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="5c6e8-102">How to Move the BAM Primary Import Database</span></span>
<span data-ttu-id="5c6e8-103">您可以使用此过程将 BAM 主导入数据库移至其他服务器。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-103">You can use this procedure to move the BAM Primary Import database to another server.</span></span> <span data-ttu-id="5c6e8-104">从端到端方案的角度看，移动 BAM 主导入数据库涉及两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-104">From an end-to-end scenario perspective, moving the BAM Primary Import database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="5c6e8-105">移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="5c6e8-105">Moving the BAM Primary Import Database</span></span>](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [<span data-ttu-id="5c6e8-106">正在更新到新的 BAM 主导入数据库引用</span><span class="sxs-lookup"><span data-stu-id="5c6e8-106">Updating References to the New BAM Primary Import Database</span></span>](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a><span data-ttu-id="5c6e8-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="5c6e8-107">Prerequisites</span></span>  
 <span data-ttu-id="5c6e8-108">若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_MovingBAMPI"></a> <span data-ttu-id="5c6e8-109">移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="5c6e8-109">Moving the BAM Primary Import Database</span></span>  
 <span data-ttu-id="5c6e8-110">以下过程来移动 BAM 主导入数据库中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-110">Perform the steps in the following procedure to move the BAM Primary Import database.</span></span>  
  
#### <a name="to-move-the-bam-primary-import-database"></a><span data-ttu-id="5c6e8-111">移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="5c6e8-111">To move the BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="5c6e8-112">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM 主导入数据库的还原。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Primary Import database.</span></span>  
  
2. <span data-ttu-id="5c6e8-113">停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="5c6e8-114">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="5c6e8-115">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="5c6e8-116">停止 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="5c6e8-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="5c6e8-117">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="5c6e8-118">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="5c6e8-119">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="5c6e8-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="5c6e8-120">备份 BAM 主导导入旧服务器上的数据库。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-120">Back up the BAM Primary import database on the old server.</span></span> <span data-ttu-id="5c6e8-121">有关备份数据库的说明，按照如何备份在数据库上的说明[如何： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-121">For instructions on backing up a database, follow the instructions on how to back up a database at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
6. <span data-ttu-id="5c6e8-122">将 BAM 主导入数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-122">Copy the BAM Primary Import database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="5c6e8-123">还原新服务器上的 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-123">Restore the BAM Primary import database on the new server.</span></span> <span data-ttu-id="5c6e8-124">有关还原数据库，说明如何还原的数据库时按照的说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-124">For instructions on restoring the database, follow the instructions on how to restore a database at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="5c6e8-125">如果从备份还原 BAM 主导入数据库，则还应该使用该 BAM 主导入数据库备份之前的备份来还原 BAM 存档数据库、BAM 星型架构数据库和 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-125">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span>  
  
##  <a name="BKMK_BAMPIRef"></a> <span data-ttu-id="5c6e8-126">正在更新到新的 BAM 主导入数据库引用</span><span class="sxs-lookup"><span data-stu-id="5c6e8-126">Updating References to the New BAM Primary Import Database</span></span>  
 <span data-ttu-id="5c6e8-127">在移动数据库之后，必须更新到新的 BAM 主导入数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-127">After you have moved the database, you must update all the references to the new BAM Primary Import Database.</span></span> <span data-ttu-id="5c6e8-128">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-128">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="5c6e8-129">使用新的服务器名称更新所有 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-129">Update all the BizTalk databases with the new server name.</span></span> <span data-ttu-id="5c6e8-130">可以使用 UpdateDatabase.vbs 脚本来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-130">You can do so by using the UpdateDatabase.vbs script.</span></span> <span data-ttu-id="5c6e8-131">请参阅[若要使用新的服务器名称更新 BizTalk 数据库](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB)。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-131">See [To update BizTalk Databases with the new server name](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB).</span></span>  
  
-   <span data-ttu-id="5c6e8-132">更新 BAM 门户 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-132">Update the Web.config file for the BAM portal.</span></span> <span data-ttu-id="5c6e8-133">请参阅[更新 BAM 门户 Web.config 文件](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config)。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-133">See [To update the Web.config file for the BAM portal](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config).</span></span>  
  
-   <span data-ttu-id="5c6e8-134">更新对 BAM 主导入数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-134">Update the reference to the BAM Primary Import Database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="5c6e8-135">请参阅[更新 BAM 实时数据 Microsoft Excel 文件中的引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel)。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-135">See [To update reference in BAM Livedata Microsoft Excel files](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel).</span></span>  
  
-   <span data-ttu-id="5c6e8-136">更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-136">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="5c6e8-137">请参阅[来更新服务器和数据库名称在所有 BAM SSIS 程序包](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg)。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-137">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg).</span></span>  
  
-   <span data-ttu-id="5c6e8-138">更新新服务器和数据库名称在数据源中的所有 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-138">Update the new server and database names in data sources for all OLAP cubes.</span></span> <span data-ttu-id="5c6e8-139">请参阅[来更新服务器和数据源中的所有 OLAP 多维数据集的数据库名称](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP)。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-139">See [To update server and database names in data sources for all OLAP cubes](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP).</span></span>  
  
###  <a name="BKMK_UpdateDB"></a> <span data-ttu-id="5c6e8-140">若要使用新的服务器名称更新 BizTalk 数据库</span><span class="sxs-lookup"><span data-stu-id="5c6e8-140">To update BizTalk Databases with the new server name</span></span>  
  
1. <span data-ttu-id="5c6e8-141">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-141">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="5c6e8-142">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-142">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="5c6e8-143">**%Programfiles (x86) %\Microsoft BizTalk Server 2010\bins32\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="5c6e8-143">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\bins32\Schema\Restore**</span></span>  
  
   - <span data-ttu-id="5c6e8-144">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-144">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="5c6e8-145">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="5c6e8-145">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
2. <span data-ttu-id="5c6e8-146">右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-146">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
3. <span data-ttu-id="5c6e8-147">注释掉所有除外 BizTalkMgmtDb、 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的数据库部分。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-147">Comment out all of the database sections except for the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span>  
  
4. <span data-ttu-id="5c6e8-148">中`OldPrimaryImportDatabase`部分中的文件，对于`ServerName`属性，替换**SourceServer**与数据库所在的现有服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-148">In the `OldPrimaryImportDatabase` section of the file, for the `ServerName` property, replace **SourceServer** with the name of existing server where the database resides.</span></span>  
  
5. <span data-ttu-id="5c6e8-149">中`PrimaryImportDatabase`部分中的文件，对于`ServerName`属性，替换**DestinationServer**与移动 BAM 主导入数据库的服务器的名称</span><span class="sxs-lookup"><span data-stu-id="5c6e8-149">In the `PrimaryImportDatabase` section of the file, for the `ServerName` property, replace **DestinationServer** with the name of the server where you have moved the BAM Primary Import database</span></span>  
  
6. <span data-ttu-id="5c6e8-150">对于的 BizTalkMgmtDb、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报部分，设置"SourceServer"和"目标服务器"的现有服务器的名称到这些数据库所在。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-150">For the BizTalkMgmtDb, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the "SourceServer" and "Destination Server" to the name of the existing server where those databases reside.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5c6e8-151">用引号将源系统和目标系统的名称括起来。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-151">Include the quotation marks around the name of the source and destination systems.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="5c6e8-152">如果对任何 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库进行了重命名，则必须也相应地更新这些数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-152">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names as appropriate.</span></span>  
  
7. <span data-ttu-id="5c6e8-153">编辑完此文件后，请进行保存然后退出。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-153">When you are finished editing the file, save it and exit.</span></span>  
  
8. <span data-ttu-id="5c6e8-154">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-154">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="5c6e8-155">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-155">At the command prompt, navigate to the following directory:</span></span>  
  
   - <span data-ttu-id="5c6e8-156">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-156">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="5c6e8-157">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="5c6e8-157">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
   - <span data-ttu-id="5c6e8-158">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-158">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="5c6e8-159">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="5c6e8-159">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
10. <span data-ttu-id="5c6e8-160">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-160">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="5c6e8-161">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="5c6e8-161">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
###  <a name="BKMK_Config"></a> <span data-ttu-id="5c6e8-162">若要更新 BAM 门户的 Web.config 文件</span><span class="sxs-lookup"><span data-stu-id="5c6e8-162">To update the Web.config file for the BAM portal</span></span>  
  
1.  <span data-ttu-id="5c6e8-163">在运行 BizTalk Server 的计算机，更新下的 Web.config 文件**\<驱动器\>: \Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config**。更新的 web.config 文件中的以下部分中的服务器和数据库名称：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-163">On a computer running BizTalk Server, update the Web.config files under **\<drive\>:\Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config**. Update the server and database names in the following section in the Web.config:</span></span>  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  <span data-ttu-id="5c6e8-164">在运行 BizTalk Server 的计算机，更新下的 Web.config 文件**\<驱动器\>: \Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config**。更新的 web.config 文件中的以下部分中的服务器和数据库名称：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-164">On a computer running BizTalk Server, update the Web.config files under **\<drive\>:\Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config**. Update the server and database names in the following section in the Web.config:</span></span>  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  <span data-ttu-id="5c6e8-165">保存并关闭文件。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-165">Save and close the files.</span></span>  
  
###  <a name="BKMK_UpdateExcel"></a> <span data-ttu-id="5c6e8-166">若要在 BAM 实时数据 Microsoft Excel 文件中更新引用</span><span class="sxs-lookup"><span data-stu-id="5c6e8-166">To update reference in BAM Livedata Microsoft Excel files</span></span>  
  
1. <span data-ttu-id="5c6e8-167">打开 Excel 实时数据文件。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-167">Open the Excel live data file.</span></span> <span data-ttu-id="5c6e8-168">以 _LiveData.xls 结尾的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-168">The file name ends with _LiveData.xls.</span></span>  
  
2. <span data-ttu-id="5c6e8-169">上**BAM**菜单上，单击**BAM 数据库连接**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-169">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
3. <span data-ttu-id="5c6e8-170">在中**选择 BAM 数据库**对话框框中，输入[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机和 BAMPrimaryImport 数据库，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-170">In the **Select BAM Database** dialog box, enter the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer and the BAMPrimaryImport database, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="5c6e8-171">上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-171">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
5. <span data-ttu-id="5c6e8-172">在“文件”菜单上，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-172">On the **File** menu, click **Save**.</span></span>  
  
###  <a name="BKMK_UpdatePckg"></a> <span data-ttu-id="5c6e8-173">若要更新服务器和数据库名称中的所有 BAM SSIS 包</span><span class="sxs-lookup"><span data-stu-id="5c6e8-173">To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="5c6e8-174">更新所有 BAM 分析 SSIS 包中，带有"BAM_AN_"或"BAM_DM_"前缀的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-174">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_" or "BAM_DM_".</span></span> <span data-ttu-id="5c6e8-175">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-175">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="5c6e8-176">在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-176">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="5c6e8-177">单击**文件**，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-177">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="5c6e8-178">在中**新的项目**对话框中**项目类型**框中，单击**商业智能项目**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-178">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="5c6e8-179">在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-179">In the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5c6e8-180">在中**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-180">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="5c6e8-181">在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_AN_ * 和 BAM_DM_ * 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-181">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_* and BAM_DM_* packages.</span></span>  
  
6.  <span data-ttu-id="5c6e8-182">在中**包路径**，请单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-182">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="5c6e8-183">在中**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-183">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="5c6e8-184">现在，该包列在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-184">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="5c6e8-185">在解决方案资源管理器，双击上一步中添加的包。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-185">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="5c6e8-186">在中**连接管理器**选项卡 （可用于在屏幕下半部分） 中，双击数据源数字 1 （BAMPrimaryImport 数据库）。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-186">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 1 (BAMPrimaryImport database).</span></span>  
  
9. <span data-ttu-id="5c6e8-187">在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-187">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="5c6e8-188">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后将更新的值**PrimaryImportDatabase**和**PrimaryImportServer**变量。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-188">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **PrimaryImportDatabase** and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="5c6e8-189">必须更新为指向新的服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-189">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c6e8-190">你想要更新的所有包重复步骤 4 到 10。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-190">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="5c6e8-191">然后单击**文件**菜单，并单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-191">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="5c6e8-192">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-192">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="5c6e8-193">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-193">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="5c6e8-194">在中**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-194">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="5c6e8-195">指定服务器名称和凭据以连接到服务器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-195">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="5c6e8-196">在中**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-196">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="5c6e8-197">在中**对象资源管理器详细信息**选项卡上，右键单击之前更新的程序包，然后单击**导入包**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-197">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="5c6e8-198">在中**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-198">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="5c6e8-199">在中**包路径**，导航到保存的项目，选择你想要导入，然后单击的包.dtsx 文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-199">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="5c6e8-200">在包名称框以自动填充此框内单击。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-200">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c6e8-201">重复步骤 16 至 19 的你想要更新的所有包。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-201">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="5c6e8-202">单击**确定**，然后单击**是**覆盖。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-202">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="5c6e8-203">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-203">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
###  <a name="BKMK_UpdateDSOLAP"></a> <span data-ttu-id="5c6e8-204">若要更新服务器和数据源中的所有 OLAP 多维数据集的数据库名称</span><span class="sxs-lookup"><span data-stu-id="5c6e8-204">To update server and database names in data sources for all OLAP cubes</span></span>  
  
1. <span data-ttu-id="5c6e8-205">更新服务器和数据库名称在数据源中的所有 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-205">Update the server and database names in data sources for all OLAP cubes.</span></span> <span data-ttu-id="5c6e8-206">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-206">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="5c6e8-207">在中**连接到服务器**对话框中，对于**服务器类型**下拉列表中，选择**Analysis Services**，提供服务器名称、 选择身份验证方法 （和提供凭据如果需要），然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-207">In the **Connect to Server** dialog box, for the **Server type** drop-down list select **Analysis Services**, provide the server name, select an authentication method (and provide credentials if required), and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="5c6e8-208">在对象资源管理器，展开**数据库**，展开**BAMAnalysis**，展开**数据源**，然后双击数据源。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-208">In the Object Explorer, expand **Databases**, expand **BAMAnalysis**, expand **Data Sources**, and then double-click a data source.</span></span>  
  
4. <span data-ttu-id="5c6e8-209">在中**数据源属性**对话框框中，单击省略号按钮 **（...）** 针对**连接字符串**属性。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-209">In the **Data Source Properties** dialog box, click the ellipsis button **(…)** against the **Connection String** property.</span></span>  
  
5. <span data-ttu-id="5c6e8-210">在中**连接管理器**对话框中**服务器名称**框中，输入承载 BAMPrimaryImport 数据库的服务器的名称，单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-210">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server hosting the BAMPrimaryImport database, click **OK**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="5c6e8-211">启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-211">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="5c6e8-212">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-212">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
7. <span data-ttu-id="5c6e8-213">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-213">Start the IIS service.</span></span>  
  
8. <span data-ttu-id="5c6e8-214">启动 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="5c6e8-214">Start the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="5c6e8-215">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-215">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="5c6e8-216">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="5c6e8-216">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="5c6e8-217">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="5c6e8-217">**Net start NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="5c6e8-218">解决任何未完成的跟踪实例。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-218">Resolve any incomplete trace instances.</span></span>  <span data-ttu-id="5c6e8-219">有关解决不完整的 BAM 活动实例的信息，请参阅[如何解析不完整活动实例](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)。</span><span class="sxs-lookup"><span data-stu-id="5c6e8-219">For information about resolving incomplete BAM activity instances, see [How to Resolve Incomplete Activity Instances](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6e8-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c6e8-220">See Also</span></span>  
 [<span data-ttu-id="5c6e8-221">移动数据库</span><span class="sxs-lookup"><span data-stu-id="5c6e8-221">Moving Databases</span></span>](../technical-guides/moving-databases.md)