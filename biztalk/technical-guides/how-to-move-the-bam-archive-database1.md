---
title: "如何移动 BAM 存档 Database1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3de3efa20057d39585a005168f7a08fc2d914a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="d22ac-102">如何移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="d22ac-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="d22ac-103">您可以使用此过程将 BAM 存档数据库移到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="d22ac-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  <span data-ttu-id="d22ac-104">从端到端方案的角度看，移动 BAM 存档数据库涉及到两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="d22ac-104">From an end-to-end scenario perspective, moving the BAM Archive database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="d22ac-105">移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="d22ac-105">Moving the BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [<span data-ttu-id="d22ac-106">更新到新的 BAM 存档数据库的引用</span><span class="sxs-lookup"><span data-stu-id="d22ac-106">Updating References to the New BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a><span data-ttu-id="d22ac-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="d22ac-107">Prerequisites</span></span>  
 <span data-ttu-id="d22ac-108">若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。</span><span class="sxs-lookup"><span data-stu-id="d22ac-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <span data-ttu-id="d22ac-109"><a name="BKMK_MovingArch"></a>移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="d22ac-109"><a name="BKMK_MovingArch"></a> Moving the BAM Archive Database</span></span>  
 <span data-ttu-id="d22ac-110">执行以下过程来移动 BAM 存档数据库中的步骤。</span><span class="sxs-lookup"><span data-stu-id="d22ac-110">Perform the steps in the following procedure to move the BAM Archive database.</span></span>  
  
#### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="d22ac-111">移动 BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="d22ac-111">To move the BAM Archive database</span></span>  
  
1.  <span data-ttu-id="d22ac-112">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或防止它们运行，直到您已还原 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="d22ac-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Archive database.</span></span>  
  
2.  <span data-ttu-id="d22ac-113">停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="d22ac-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="d22ac-114">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="d22ac-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="d22ac-115">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="d22ac-115">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="d22ac-116">停止 BAM 警报通知服务：</span><span class="sxs-lookup"><span data-stu-id="d22ac-116">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="d22ac-117">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d22ac-118">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d22ac-118">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d22ac-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="d22ac-119">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="d22ac-120">旧服务器上备份 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="d22ac-120">Back up the BAM Archive database on the old server.</span></span> <span data-ttu-id="d22ac-121">有关备份数据库的说明，请遵循的说明[How to： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何备份数据库联机丛书。</span><span class="sxs-lookup"><span data-stu-id="d22ac-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6.  <span data-ttu-id="d22ac-122">BAM 存档数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="d22ac-122">Copy the BAM Archive database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="d22ac-123">还原新的服务器上的 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="d22ac-123">Restore the BAM Archive database on the new server.</span></span> <span data-ttu-id="d22ac-124">对于说明还原数据库，请按照说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何还原数据库联机丛书。</span><span class="sxs-lookup"><span data-stu-id="d22ac-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <span data-ttu-id="d22ac-125"><a name="BKMK_UpdateArch"></a>更新到新的 BAM 存档数据库的引用</span><span class="sxs-lookup"><span data-stu-id="d22ac-125"><a name="BKMK_UpdateArch"></a> Updating References to the New BAM Archive Database</span></span>  
 <span data-ttu-id="d22ac-126">将数据库移动后，你必须更新到新的 BAM 存档数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="d22ac-126">After you have moved the database, you must update all the references to the new BAM Archive Database.</span></span> <span data-ttu-id="d22ac-127">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="d22ac-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="d22ac-128">使用新的数据库和服务器名称更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="d22ac-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="d22ac-129">请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig)。</span><span class="sxs-lookup"><span data-stu-id="d22ac-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig).</span></span>  
  
-   <span data-ttu-id="d22ac-130">更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d22ac-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="d22ac-131">请参阅[更新服务器和数据库名称中的所有 BAM SSIS 包](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS)。</span><span class="sxs-lookup"><span data-stu-id="d22ac-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS).</span></span>  
  
###  <span data-ttu-id="d22ac-132"><a name="BKMK_UpdateArchConfig"></a>若要更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="d22ac-132"><a name="BKMK_UpdateArchConfig"></a> To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="d22ac-133">获取用于还原 BAM 的 .xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="d22ac-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="d22ac-134">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d22ac-135">在运行 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的计算机中，浏览至以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d22ac-135">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="d22ac-136">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：</span><span class="sxs-lookup"><span data-stu-id="d22ac-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="d22ac-137">**%Programfiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d22ac-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="d22ac-138">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="d22ac-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="d22ac-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d22ac-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="d22ac-140">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d22ac-140">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d22ac-141">**Bm.exe get-config –filename:BAMConfiguration.xml-server:\<服务器名称 >-数据库：\<数据库 >**</span><span class="sxs-lookup"><span data-stu-id="d22ac-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername> -database:\<database>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d22ac-142">运行此命令时, 替换从其获取的配置信息的服务器的实际名称\<servername >，用替换从其获取的配置信息的数据库的实际名称\<数据库 >。</span><span class="sxs-lookup"><span data-stu-id="d22ac-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername> and substitute the actual name of the database from which to get the configuration information for \<database>.</span></span> <span data-ttu-id="d22ac-143">有关使用 BAM 管理 (BM) 实用工具的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="d22ac-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="d22ac-144">编辑 BAMConfiguration.xml 文件并将更改**ServerName**中`<DeploymentUnit Name="ArchivingDatabase">`到新的服务器名称的部分。</span><span class="sxs-lookup"><span data-stu-id="d22ac-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="ArchivingDatabase">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="d22ac-145">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="d22ac-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="d22ac-146">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d22ac-147">在运行 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的计算机中，浏览至以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d22ac-147">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="d22ac-148">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：</span><span class="sxs-lookup"><span data-stu-id="d22ac-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="d22ac-149">**%Programfiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d22ac-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="d22ac-150">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="d22ac-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="d22ac-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d22ac-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="d22ac-152">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d22ac-152">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="d22ac-153">**bm.exe 更新-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="d22ac-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <span data-ttu-id="d22ac-154"><a name="BKMK_UpdateArchSSIS"></a>更新服务器和所有 BAM SSIS 包中的数据库名称</span><span class="sxs-lookup"><span data-stu-id="d22ac-154"><a name="BKMK_UpdateArchSSIS"></a> To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="d22ac-155">更新中的所有 BAM 分析 SSIS 包，以"BAM_DM_"作为前缀的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d22ac-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_DM_".</span></span> <span data-ttu-id="d22ac-156">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="d22ac-157">在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="d22ac-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="d22ac-158">单击**文件**，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d22ac-159">在**新项目**对话框中，在**项目类型**框中，单击**商业智能项目**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="d22ac-160">在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d22ac-161">在**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="d22ac-162">在**添加现有包副本**对话框中，在**服务器**下拉列表框中，选择包含 BAM_DM_ * 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="d22ac-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM_* packages.</span></span>  
  
6.  <span data-ttu-id="d22ac-163">在**包路径**，单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="d22ac-163">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="d22ac-164">在**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d22ac-165">现在，该包列在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="d22ac-165">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="d22ac-166">在解决方案资源管理器中，双击上一步中添加的程序包。</span><span class="sxs-lookup"><span data-stu-id="d22ac-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="d22ac-167">在**连接管理器**选项卡 （可向屏幕的下半部分） 中，双击号为 2 （BAMArchive 数据库） 的数据源。</span><span class="sxs-lookup"><span data-stu-id="d22ac-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="d22ac-168">在**连接管理器**对话框中，在**服务器名称**框中，输入服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d22ac-169">数据源数量 3 （MSDB 数据库） 重复此过程。</span><span class="sxs-lookup"><span data-stu-id="d22ac-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="d22ac-170">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新的值**ArchivingDatabase**， **ArchivingServer**， **PrimaryImportDatabase**，和**PrimaryImportServer**变量。</span><span class="sxs-lookup"><span data-stu-id="d22ac-170">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **ArchivingDatabase**, **ArchivingServer**, **PrimaryImportDatabase**, and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="d22ac-171">你必须更新为指向新的服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="d22ac-171">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d22ac-172">你想要更新的所有包重复步骤 4 到 10。</span><span class="sxs-lookup"><span data-stu-id="d22ac-172">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="d22ac-173">然后单击**文件**菜单，，然后单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-173">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="d22ac-174">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="d22ac-174">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="d22ac-175">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-175">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="d22ac-176">在**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-176">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="d22ac-177">指定服务器名称和凭据以连接到服务器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-177">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="d22ac-178">在**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-178">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="d22ac-179">在**对象资源管理器详细信息**选项卡上，右键单击之前更新的包，然后单击**导入包**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-179">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="d22ac-180">在**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-180">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="d22ac-181">在**包路径**，导航到已保存项目，选择你想要导入，然后单击程序包的.dtsx 文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-181">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="d22ac-182">若要在框中自动填充的包名称框内单击。</span><span class="sxs-lookup"><span data-stu-id="d22ac-182">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d22ac-183">你想要更新的所有包重复步骤 16 至 19。</span><span class="sxs-lookup"><span data-stu-id="d22ac-183">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="d22ac-184">单击**确定**，然后单击**是**覆盖。</span><span class="sxs-lookup"><span data-stu-id="d22ac-184">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="d22ac-185">启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="d22ac-185">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="d22ac-186">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="d22ac-186">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
22. <span data-ttu-id="d22ac-187">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="d22ac-187">Start the IIS service.</span></span>  
  
23. <span data-ttu-id="d22ac-188">启动 BAM 警报通知服务：</span><span class="sxs-lookup"><span data-stu-id="d22ac-188">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="d22ac-189">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d22ac-189">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d22ac-190">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d22ac-190">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d22ac-191">**Net 开始 NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="d22ac-191">**Net start NS$BamAlerts**</span></span>  
  
24. <span data-ttu-id="d22ac-192">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="d22ac-192">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d22ac-193">作为一种良好做法，还应将 BAM_DM_ * SSIS 包移动到承载 BAMArchive 数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="d22ac-193">As a good practice, you should also move the BAM_DM_* SSIS packages to the server hosting the BAMArchive database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d22ac-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d22ac-194">See Also</span></span>  
 [<span data-ttu-id="d22ac-195">移动数据库</span><span class="sxs-lookup"><span data-stu-id="d22ac-195">Moving Databases</span></span>](../technical-guides/moving-databases.md)