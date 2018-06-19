---
title: 如何移动 BAM 分析 Database1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8094153-072b-427a-b3a0-7310a37cf584
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b21168c1955db8bbbae3e29019632807231b40a1
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "26010478"
---
# <a name="how-to-move-the-bam-analysis-database"></a><span data-ttu-id="d8d62-102">如何移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="d8d62-102">How to Move the BAM Analysis Database</span></span>
<span data-ttu-id="d8d62-103">可以使用此过程将 BAM 分析数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="d8d62-103">You can use this procedure to move the BAM Analysis database to another server.</span></span>  <span data-ttu-id="d8d62-104">从端到端方案的角度看，移动 BAM 分析数据库涉及到两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="d8d62-104">From an end-to-end scenario perspective, moving the BAM Analysis database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="d8d62-105">移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="d8d62-105">Moving the BAM Analysis Database</span></span>](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyMoveDB)  
  
-   [<span data-ttu-id="d8d62-106">更新到新的 BAM 分析数据库的引用</span><span class="sxs-lookup"><span data-stu-id="d8d62-106">Updating References to the New BAM Analysis Database</span></span>](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)  
  
## <a name="prerequisites"></a><span data-ttu-id="d8d62-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="d8d62-107">Prerequisites</span></span>  
 <span data-ttu-id="d8d62-108">若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。</span><span class="sxs-lookup"><span data-stu-id="d8d62-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_AnalyMoveDB"></a> <span data-ttu-id="d8d62-109">移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="d8d62-109">Moving the BAM Analysis Database</span></span>  
 <span data-ttu-id="d8d62-110">执行以下过程将 BAM 分析数据库中的步骤。</span><span class="sxs-lookup"><span data-stu-id="d8d62-110">Perform the steps in the following procedure to move the BAM Analysis database.</span></span>  
  
#### <a name="to-move-the-bam-analysis-database"></a><span data-ttu-id="d8d62-111">若要移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="d8d62-111">To move the BAM Analysis database</span></span>  
  
1.  <span data-ttu-id="d8d62-112">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM 分析数据库的还原完成为止。</span><span class="sxs-lookup"><span data-stu-id="d8d62-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Analysis database.</span></span>  
  
2.  <span data-ttu-id="d8d62-113">停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="d8d62-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="d8d62-114">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="d8d62-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="d8d62-115">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="d8d62-115">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="d8d62-116">停止 BAM 警报通知服务：</span><span class="sxs-lookup"><span data-stu-id="d8d62-116">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="d8d62-117">单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d8d62-118">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d8d62-118">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d8d62-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="d8d62-119">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="d8d62-120">旧服务器上备份 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="d8d62-120">Back up the BAM Analysis database on the old server.</span></span> <span data-ttu-id="d8d62-121">有关备份数据库的说明，请遵循的说明[How to： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510)中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何备份数据库联机丛书。</span><span class="sxs-lookup"><span data-stu-id="d8d62-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6.  <span data-ttu-id="d8d62-122">BAM 分析数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="d8d62-122">Copy the BAM Analysis database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="d8d62-123">还原新服务器上的 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="d8d62-123">Restore the BAM Analysis database on the new server.</span></span> <span data-ttu-id="d8d62-124">对于说明还原数据库，请按照说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511)中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何还原数据库联机丛书。</span><span class="sxs-lookup"><span data-stu-id="d8d62-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_AnalyUpdate"></a> <span data-ttu-id="d8d62-125">更新到新的 BAM 分析数据库的引用</span><span class="sxs-lookup"><span data-stu-id="d8d62-125">Updating References to the New BAM Analysis Database</span></span>  
 <span data-ttu-id="d8d62-126">将数据库移动后，你必须更新到新的 BAM 分析数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="d8d62-126">After you have moved the database, you must update all the references to the new BAM Analysis Database.</span></span> <span data-ttu-id="d8d62-127">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="d8d62-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="d8d62-128">使用新的数据库和服务器名称更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="d8d62-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="d8d62-129">请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig)。</span><span class="sxs-lookup"><span data-stu-id="d8d62-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="d8d62-130">更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d8d62-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="d8d62-131">请参阅[更新服务器和数据库名称中的所有 BAM SSIS 包](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS)。</span><span class="sxs-lookup"><span data-stu-id="d8d62-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS).</span></span>  
  
###  <a name="BKMK_AnalyUpdateBAMConfig"></a> <span data-ttu-id="d8d62-132">若要更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="d8d62-132">To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="d8d62-133">获取用于还原 BAM 的 .xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="d8d62-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="d8d62-134">单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d8d62-135">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d8d62-135">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="d8d62-136">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：</span><span class="sxs-lookup"><span data-stu-id="d8d62-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="d8d62-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d8d62-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="d8d62-138">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="d8d62-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="d8d62-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d8d62-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="d8d62-140">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d8d62-140">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d8d62-141">**Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -数据库：\<数据库\>**</span><span class="sxs-lookup"><span data-stu-id="d8d62-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d8d62-142">运行此命令时, 替换从其获取的配置信息的服务器的实际名称\<servername\>和替换从其获取的配置信息的数据库的实际名称\<数据库\>。</span><span class="sxs-lookup"><span data-stu-id="d8d62-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="d8d62-143">有关使用 BAM 管理 (BM) 实用工具的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="d8d62-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="d8d62-144">编辑 BAMConfiguration.xml 文件并将更改**ServerName**中`<DeploymentUnit Name="AnalysisDatabase">`到新的服务器名称的部分。</span><span class="sxs-lookup"><span data-stu-id="d8d62-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="AnalysisDatabase">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="d8d62-145">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="d8d62-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="d8d62-146">单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d8d62-147">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d8d62-147">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="d8d62-148">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：</span><span class="sxs-lookup"><span data-stu-id="d8d62-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="d8d62-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d8d62-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="d8d62-150">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="d8d62-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="d8d62-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d8d62-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="d8d62-152">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d8d62-152">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="d8d62-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="d8d62-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_AnalyUpdateSSIS"></a> <span data-ttu-id="d8d62-154">更新服务器和所有 BAM SSIS 包中的数据库名称</span><span class="sxs-lookup"><span data-stu-id="d8d62-154">To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="d8d62-155">更新中的所有 BAM 分析 SSIS 包，以"BAM_AN_"作为前缀的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d8d62-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_".</span></span> <span data-ttu-id="d8d62-156">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="d8d62-157">在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="d8d62-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="d8d62-158">单击 **文件**, ，单击 **新建**, ，然后单击 **项目**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d8d62-159">在**新项目**对话框中，在**项目类型**框中，单击**商业智能项目**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="d8d62-160">在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d8d62-161">在**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="d8d62-162">在**添加现有包副本**对话框中，在**服务器**下拉列表框中，选择包含 BAM_AN_ \* 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="d8d62-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_\* packages.</span></span>  
  
6.  <span data-ttu-id="d8d62-163">在 **包路径**, ，单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="d8d62-163">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="d8d62-164">在**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d8d62-165">现在，该包列在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="d8d62-165">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="d8d62-166">在解决方案资源管理器中，双击上一步中添加的程序包。</span><span class="sxs-lookup"><span data-stu-id="d8d62-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="d8d62-167">在**连接管理器**选项卡 （可向屏幕的下半部分） 中，双击号为 2 （BAMArchive 数据库） 的数据源。</span><span class="sxs-lookup"><span data-stu-id="d8d62-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="d8d62-168">在**连接管理器**对话框中，在**服务器名称**框中，输入服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8d62-169">数据源数量 3 （MSDB 数据库） 重复此过程。</span><span class="sxs-lookup"><span data-stu-id="d8d62-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="d8d62-170">在**连接管理器**选项卡上，双击数据源编号 4 （BAMAnalysis 数据库）。</span><span class="sxs-lookup"><span data-stu-id="d8d62-170">In the **Connection Managers** tab, double-click data source number 4 (BAMAnalysis database).</span></span> <span data-ttu-id="d8d62-171">在**添加 Analysis Services 连接管理器**对话框中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-171">In the **Add Analysis Services Connection Manager** dialog box, click **Edit**.</span></span>  
  
11. <span data-ttu-id="d8d62-172">在**连接管理器**对话框中，在**服务器名称**框中，输入服务器的名称，单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-172">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, click **OK**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="d8d62-173">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新的值**AnalysisDatabase**， **AnalysisServer**， **PrimaryImportDatabase**， **PrimaryImportServer**， **StarSchemaDatabase**，和**StarSchemaServer**变量。</span><span class="sxs-lookup"><span data-stu-id="d8d62-173">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **AnalysisDatabase**, **AnalysisServer**, **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, and **StarSchemaServer** variables.</span></span> <span data-ttu-id="d8d62-174">你必须更新为指向新的服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="d8d62-174">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8d62-175">你想要更新的所有包重复步骤 4 到 12。</span><span class="sxs-lookup"><span data-stu-id="d8d62-175">Repeat step 4 through 12 for all the packages that you want to update.</span></span>  
  
13. <span data-ttu-id="d8d62-176">然后单击**文件**菜单，，然后单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-176">Click then **File** menu, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="d8d62-177">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="d8d62-177">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="d8d62-178">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-178">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
15. <span data-ttu-id="d8d62-179">在**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-179">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
16. <span data-ttu-id="d8d62-180">指定服务器名称和凭据以连接到服务器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-180">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
17. <span data-ttu-id="d8d62-181">在**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-181">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
18. <span data-ttu-id="d8d62-182">在**对象资源管理器详细信息**选项卡上，右键单击之前更新的包，然后单击**导入包**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-182">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
19. <span data-ttu-id="d8d62-183">在**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-183">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
20. <span data-ttu-id="d8d62-184">在**包路径**，导航到已保存项目，选择你想要导入，然后单击程序包的.dtsx 文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-184">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
21. <span data-ttu-id="d8d62-185">若要在框中自动填充的包名称框内单击。</span><span class="sxs-lookup"><span data-stu-id="d8d62-185">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8d62-186">你想要更新的所有包重复步骤 18 至 21。</span><span class="sxs-lookup"><span data-stu-id="d8d62-186">Repeat step 18 through 21 for all the packages that you want to update.</span></span>  
  
22. <span data-ttu-id="d8d62-187">单击 **确定**, ，然后单击 **是** 覆盖。</span><span class="sxs-lookup"><span data-stu-id="d8d62-187">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
23. <span data-ttu-id="d8d62-188">启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="d8d62-188">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="d8d62-189">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="d8d62-189">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
24. <span data-ttu-id="d8d62-190">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="d8d62-190">Start the IIS service.</span></span>  
  
25. <span data-ttu-id="d8d62-191">启动 BAM 警报通知服务：</span><span class="sxs-lookup"><span data-stu-id="d8d62-191">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="d8d62-192">单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="d8d62-192">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d8d62-193">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="d8d62-193">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d8d62-194">**Net 开始 NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="d8d62-194">**Net start NS$BamAlerts**</span></span>  
  
26. <span data-ttu-id="d8d62-195">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="d8d62-195">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d62-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8d62-196">See Also</span></span>  
 [<span data-ttu-id="d8d62-197">移动数据库</span><span class="sxs-lookup"><span data-stu-id="d8d62-197">Moving Databases</span></span>](../technical-guides/moving-databases.md)