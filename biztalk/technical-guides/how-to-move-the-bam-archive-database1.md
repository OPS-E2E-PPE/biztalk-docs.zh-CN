---
title: 如何移动 BAM 存档数据库 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84dda0937fc0c7b060e483b2ca1585a3d5160ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023403"
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="49fe4-102">如何移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="49fe4-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="49fe4-103">您可以使用此过程将 BAM 存档数据库移到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="49fe4-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  <span data-ttu-id="49fe4-104">从端到端方案的角度看，移动 BAM 存档数据库涉及两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="49fe4-104">From an end-to-end scenario perspective, moving the BAM Archive database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="49fe4-105">移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="49fe4-105">Moving the BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [<span data-ttu-id="49fe4-106">正在更新到新的 BAM 存档数据库的引用</span><span class="sxs-lookup"><span data-stu-id="49fe4-106">Updating References to the New BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a><span data-ttu-id="49fe4-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="49fe4-107">Prerequisites</span></span>  
 <span data-ttu-id="49fe4-108">若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。</span><span class="sxs-lookup"><span data-stu-id="49fe4-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_MovingArch"></a> <span data-ttu-id="49fe4-109">移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="49fe4-109">Moving the BAM Archive Database</span></span>  
 <span data-ttu-id="49fe4-110">以下过程来移动 BAM 存档数据库中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="49fe4-110">Perform the steps in the following procedure to move the BAM Archive database.</span></span>  
  
#### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="49fe4-111">移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="49fe4-111">To move the BAM Archive database</span></span>  
  
1. <span data-ttu-id="49fe4-112">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM 存档数据库的还原。</span><span class="sxs-lookup"><span data-stu-id="49fe4-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Archive database.</span></span>  
  
2. <span data-ttu-id="49fe4-113">停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="49fe4-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="49fe4-114">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="49fe4-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="49fe4-115">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="49fe4-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="49fe4-116">停止 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="49fe4-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="49fe4-117">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="49fe4-118">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="49fe4-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="49fe4-119">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="49fe4-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="49fe4-120">在旧服务器上备份 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="49fe4-120">Back up the BAM Archive database on the old server.</span></span> <span data-ttu-id="49fe4-121">备份数据库的说明，请遵循的说明[如何： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何备份数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="49fe4-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6. <span data-ttu-id="49fe4-122">将 BAM 存档数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="49fe4-122">Copy the BAM Archive database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="49fe4-123">还原新服务器上的 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="49fe4-123">Restore the BAM Archive database on the new server.</span></span> <span data-ttu-id="49fe4-124">对于还原数据库的说明，请按照的说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何还原数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="49fe4-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_UpdateArch"></a> <span data-ttu-id="49fe4-125">正在更新到新的 BAM 存档数据库的引用</span><span class="sxs-lookup"><span data-stu-id="49fe4-125">Updating References to the New BAM Archive Database</span></span>  
 <span data-ttu-id="49fe4-126">在移动数据库之后，必须更新到新的 BAM 存档数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="49fe4-126">After you have moved the database, you must update all the references to the new BAM Archive Database.</span></span> <span data-ttu-id="49fe4-127">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="49fe4-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="49fe4-128">使用新的数据库和服务器名称更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="49fe4-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="49fe4-129">请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig)。</span><span class="sxs-lookup"><span data-stu-id="49fe4-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig).</span></span>  
  
-   <span data-ttu-id="49fe4-130">更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="49fe4-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="49fe4-131">请参阅[来更新服务器和数据库名称在所有 BAM SSIS 程序包](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS)。</span><span class="sxs-lookup"><span data-stu-id="49fe4-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS).</span></span>  
  
###  <a name="BKMK_UpdateArchConfig"></a> <span data-ttu-id="49fe4-132">若要更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="49fe4-132">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="49fe4-133">获取用于还原 BAM 的 .xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="49fe4-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="49fe4-134">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="49fe4-135">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="49fe4-135">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="49fe4-136">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="49fe4-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="49fe4-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="49fe4-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="49fe4-138">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="49fe4-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="49fe4-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="49fe4-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="49fe4-140">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="49fe4-140">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="49fe4-141">**Bm.exe 获取配置 –filename:BAMConfiguration.xml-server:\<servername\> -数据库：\<数据库\>**</span><span class="sxs-lookup"><span data-stu-id="49fe4-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="49fe4-142">当运行此命令，替换从其获取的配置信息的服务器的实际名称\<servername\>并将其替换实际获取的配置信息的数据库的名称\<数据库\>。</span><span class="sxs-lookup"><span data-stu-id="49fe4-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="49fe4-143">有关使用 BAM 管理 (BM) 实用程序的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="49fe4-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="49fe4-144">编辑 BAMConfiguration.xml 文件，将**ServerName**中`<DeploymentUnit Name="ArchivingDatabase">`到新的服务器名称的部分。</span><span class="sxs-lookup"><span data-stu-id="49fe4-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="ArchivingDatabase">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="49fe4-145">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="49fe4-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="49fe4-146">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="49fe4-147">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="49fe4-147">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="49fe4-148">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="49fe4-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="49fe4-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="49fe4-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="49fe4-150">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="49fe4-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="49fe4-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="49fe4-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="49fe4-152">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="49fe4-152">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="49fe4-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="49fe4-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_UpdateArchSSIS"></a> <span data-ttu-id="49fe4-154">若要更新服务器和数据库名称中的所有 BAM SSIS 包</span><span class="sxs-lookup"><span data-stu-id="49fe4-154">To update server and database names in all BAM SSIS packages</span></span>  
  
1. <span data-ttu-id="49fe4-155">更新所有 BAM 分析 SSIS 包中，带有"BAM_DM_"前缀的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="49fe4-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_DM_".</span></span> <span data-ttu-id="49fe4-156">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2. <span data-ttu-id="49fe4-157">在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="49fe4-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="49fe4-158">单击**文件**，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="49fe4-159">在中**新的项目**对话框中**项目类型**框中，单击**商业智能项目**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="49fe4-160">在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="49fe4-161">在中**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5. <span data-ttu-id="49fe4-162">在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_DM_ \* 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="49fe4-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM_\* packages.</span></span>  
  
6. <span data-ttu-id="49fe4-163">在中**包路径**，请单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="49fe4-163">In **Package Path**, click the ellipses button.</span></span>  
  
7. <span data-ttu-id="49fe4-164">在中**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="49fe4-165">现在，该包列在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="49fe4-165">The package is now listed in Solution Explorer.</span></span>  
  
8. <span data-ttu-id="49fe4-166">在解决方案资源管理器，双击上一步中添加的包。</span><span class="sxs-lookup"><span data-stu-id="49fe4-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="49fe4-167">在中**连接管理器**选项卡 （可用于在屏幕下半部分） 中，双击数据源数 2 （BAMArchive 数据库）。</span><span class="sxs-lookup"><span data-stu-id="49fe4-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="49fe4-168">在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49fe4-169">数据源编号 3(MSDB 数据库） 重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="49fe4-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="49fe4-170">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后将更新的值**ArchivingDatabase**， **ArchivingServer**， **PrimaryImportDatabase**，和**PrimaryImportServer**变量。</span><span class="sxs-lookup"><span data-stu-id="49fe4-170">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **ArchivingDatabase**, **ArchivingServer**, **PrimaryImportDatabase**, and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="49fe4-171">必须更新为指向新的服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="49fe4-171">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49fe4-172">你想要更新的所有包重复步骤 4 到 10。</span><span class="sxs-lookup"><span data-stu-id="49fe4-172">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="49fe4-173">然后单击**文件**菜单，并单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-173">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="49fe4-174">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="49fe4-174">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="49fe4-175">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-175">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="49fe4-176">在中**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-176">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="49fe4-177">指定服务器名称和凭据以连接到服务器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-177">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="49fe4-178">在中**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-178">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="49fe4-179">在中**对象资源管理器详细信息**选项卡上，右键单击之前更新的程序包，然后单击**导入包**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-179">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="49fe4-180">在中**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-180">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="49fe4-181">在中**包路径**，导航到保存的项目，选择你想要导入，然后单击的包.dtsx 文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-181">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="49fe4-182">在包名称框以自动填充此框内单击。</span><span class="sxs-lookup"><span data-stu-id="49fe4-182">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49fe4-183">重复步骤 16 至 19 的你想要更新的所有包。</span><span class="sxs-lookup"><span data-stu-id="49fe4-183">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="49fe4-184">单击**确定**，然后单击**是**覆盖。</span><span class="sxs-lookup"><span data-stu-id="49fe4-184">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="49fe4-185">启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="49fe4-185">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="49fe4-186">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="49fe4-186">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
22. <span data-ttu-id="49fe4-187">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="49fe4-187">Start the IIS service.</span></span>  
  
23. <span data-ttu-id="49fe4-188">启动 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="49fe4-188">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="49fe4-189">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49fe4-189">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="49fe4-190">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="49fe4-190">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="49fe4-191">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="49fe4-191">**Net start NS$BamAlerts**</span></span>  
  
24. <span data-ttu-id="49fe4-192">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="49fe4-192">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="49fe4-193">很好的做法是，还应将 BAM_DM_ \* SSIS 包移动到 BAMArchive 数据库的宿主服务器。</span><span class="sxs-lookup"><span data-stu-id="49fe4-193">As a good practice, you should also move the BAM_DM_\* SSIS packages to the server hosting the BAMArchive database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fe4-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="49fe4-194">See Also</span></span>  
 [<span data-ttu-id="49fe4-195">移动数据库</span><span class="sxs-lookup"><span data-stu-id="49fe4-195">Moving Databases</span></span>](../technical-guides/moving-databases.md)