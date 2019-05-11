---
title: 如何移动 BAM 分析数据库 1 |Microsoft Docs
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
ms.openlocfilehash: 29ab7e205777af9403157811388e9955b0f4d08f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401814"
---
# <a name="how-to-move-the-bam-analysis-database"></a><span data-ttu-id="a5624-102">如何移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="a5624-102">How to Move the BAM Analysis Database</span></span>
<span data-ttu-id="a5624-103">可以使用此过程将 BAM 分析数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="a5624-103">You can use this procedure to move the BAM Analysis database to another server.</span></span>  <span data-ttu-id="a5624-104">从端到端方案的角度看，移动 BAM 分析数据库涉及两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="a5624-104">From an end-to-end scenario perspective, moving the BAM Analysis database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="a5624-105">移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="a5624-105">Moving the BAM Analysis Database</span></span>](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyMoveDB)  
  
-   [<span data-ttu-id="a5624-106">更新到新的 BAM 分析数据库的引用</span><span class="sxs-lookup"><span data-stu-id="a5624-106">Updating References to the New BAM Analysis Database</span></span>](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)  
  
## <a name="prerequisites"></a><span data-ttu-id="a5624-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="a5624-107">Prerequisites</span></span>  
 <span data-ttu-id="a5624-108">您必须是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="a5624-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_AnalyMoveDB"></a> <span data-ttu-id="a5624-109">移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="a5624-109">Moving the BAM Analysis Database</span></span>  
 <span data-ttu-id="a5624-110">以下过程来移动 BAM 分析数据库中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="a5624-110">Perform the steps in the following procedure to move the BAM Analysis database.</span></span>  
  
#### <a name="to-move-the-bam-analysis-database"></a><span data-ttu-id="a5624-111">移动 BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="a5624-111">To move the BAM Analysis database</span></span>  
  
1. <span data-ttu-id="a5624-112">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM 分析数据库的还原。</span><span class="sxs-lookup"><span data-stu-id="a5624-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Analysis database.</span></span>  
  
2. <span data-ttu-id="a5624-113">停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="a5624-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="a5624-114">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="a5624-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="a5624-115">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="a5624-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="a5624-116">停止 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="a5624-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="a5624-117">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="a5624-118">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="a5624-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="a5624-119">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="a5624-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="a5624-120">在旧服务器上备份 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="a5624-120">Back up the BAM Analysis database on the old server.</span></span> <span data-ttu-id="a5624-121">备份数据库的说明，请遵循的说明[如何：备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何备份数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="a5624-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6. <span data-ttu-id="a5624-122">将 BAM 分析数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="a5624-122">Copy the BAM Analysis database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="a5624-123">还原新服务器上的 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="a5624-123">Restore the BAM Analysis database on the new server.</span></span> <span data-ttu-id="a5624-124">对于还原数据库的说明，请按照的说明[如何：还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何还原数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="a5624-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_AnalyUpdate"></a> <span data-ttu-id="a5624-125">更新到新的 BAM 分析数据库的引用</span><span class="sxs-lookup"><span data-stu-id="a5624-125">Updating References to the New BAM Analysis Database</span></span>  
 <span data-ttu-id="a5624-126">在移动数据库之后，必须更新到新的 BAM 分析数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="a5624-126">After you have moved the database, you must update all the references to the new BAM Analysis Database.</span></span> <span data-ttu-id="a5624-127">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="a5624-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="a5624-128">使用新的数据库和服务器名称更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="a5624-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="a5624-129">请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig)。</span><span class="sxs-lookup"><span data-stu-id="a5624-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="a5624-130">更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="a5624-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="a5624-131">请参阅[来更新服务器和数据库名称在所有 BAM SSIS 程序包](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS)。</span><span class="sxs-lookup"><span data-stu-id="a5624-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS).</span></span>  
  
###  <a name="BKMK_AnalyUpdateBAMConfig"></a> <span data-ttu-id="a5624-132">若要更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="a5624-132">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="a5624-133">获取用于还原 BAM 的.xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="a5624-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="a5624-134">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="a5624-135">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a5624-135">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="a5624-136">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="a5624-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="a5624-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="a5624-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="a5624-138">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="a5624-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="a5624-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="a5624-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="a5624-140">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="a5624-140">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="a5624-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span><span class="sxs-lookup"><span data-stu-id="a5624-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="a5624-142">当运行此命令，替换从其获取的配置信息的服务器的实际名称\<servername\>并将其替换实际获取的配置信息的数据库的名称\<数据库\>。</span><span class="sxs-lookup"><span data-stu-id="a5624-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="a5624-143">有关使用 BAM 管理 (BM) 实用程序的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="a5624-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="a5624-144">编辑 BAMConfiguration.xml 文件，将**ServerName**中`<DeploymentUnit Name="AnalysisDatabase">`到新的服务器名称的部分。</span><span class="sxs-lookup"><span data-stu-id="a5624-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="AnalysisDatabase">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="a5624-145">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="a5624-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="a5624-146">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="a5624-147">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a5624-147">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="a5624-148">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="a5624-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="a5624-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="a5624-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="a5624-150">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="a5624-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="a5624-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="a5624-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="a5624-152">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="a5624-152">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="a5624-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="a5624-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_AnalyUpdateSSIS"></a> <span data-ttu-id="a5624-154">若要更新服务器和数据库名称中的所有 BAM SSIS 包</span><span class="sxs-lookup"><span data-stu-id="a5624-154">To update server and database names in all BAM SSIS packages</span></span>  
  
1. <span data-ttu-id="a5624-155">更新所有 BAM 分析 SSIS 包中，带有"BAM_AN_"前缀的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="a5624-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_".</span></span> <span data-ttu-id="a5624-156">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。</span><span class="sxs-lookup"><span data-stu-id="a5624-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2. <span data-ttu-id="a5624-157">在 SQL Server Business Intelligence Development Studio，创建新项目。</span><span class="sxs-lookup"><span data-stu-id="a5624-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="a5624-158">单击**文件**，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="a5624-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="a5624-159">在中**新的项目**对话框中**项目类型**框中，单击**商业智能项目**。</span><span class="sxs-lookup"><span data-stu-id="a5624-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="a5624-160">在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="a5624-161">在中**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。</span><span class="sxs-lookup"><span data-stu-id="a5624-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5. <span data-ttu-id="a5624-162">在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_AN_ \* 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="a5624-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_\* packages.</span></span>  
  
6. <span data-ttu-id="a5624-163">在中**包路径**，请单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="a5624-163">In **Package Path**, click the ellipses button.</span></span>  
  
7. <span data-ttu-id="a5624-164">在中**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="a5624-165">包现在列在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="a5624-165">The package is now listed in Solution Explorer.</span></span>  
  
8. <span data-ttu-id="a5624-166">在解决方案资源管理器，双击上一步中添加的包。</span><span class="sxs-lookup"><span data-stu-id="a5624-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="a5624-167">在中**连接管理器**选项卡 （可用于在屏幕下半部分） 中，双击数据源数 2 （BAMArchive 数据库）。</span><span class="sxs-lookup"><span data-stu-id="a5624-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="a5624-168">在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5624-169">数据源编号 3(MSDB 数据库） 重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="a5624-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="a5624-170">在中**连接管理器**选项卡上，双击数据源编号 4 （BAMAnalysis 数据库）。</span><span class="sxs-lookup"><span data-stu-id="a5624-170">In the **Connection Managers** tab, double-click data source number 4 (BAMAnalysis database).</span></span> <span data-ttu-id="a5624-171">在中**添加 Analysis Services 连接管理器**对话框中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a5624-171">In the **Add Analysis Services Connection Manager** dialog box, click **Edit**.</span></span>  
  
11. <span data-ttu-id="a5624-172">在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-172">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, click **OK**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="a5624-173">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后将更新的值**AnalysisDatabase**， **AnalysisServer**， **PrimaryImportDatabase**， **PrimaryImportServer**， **StarSchemaDatabase**，和**StarSchemaServer**变量。</span><span class="sxs-lookup"><span data-stu-id="a5624-173">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **AnalysisDatabase**, **AnalysisServer**, **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, and **StarSchemaServer** variables.</span></span> <span data-ttu-id="a5624-174">必须更新为指向新的服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="a5624-174">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5624-175">重复步骤 4 到 12 的你想要更新的所有包。</span><span class="sxs-lookup"><span data-stu-id="a5624-175">Repeat step 4 through 12 for all the packages that you want to update.</span></span>  
  
13. <span data-ttu-id="a5624-176">然后单击**文件**菜单，并单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="a5624-176">Click then **File** menu, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="a5624-177">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="a5624-177">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="a5624-178">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="a5624-178">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
15. <span data-ttu-id="a5624-179">在中**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="a5624-179">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
16. <span data-ttu-id="a5624-180">指定服务器名称和凭据以连接到服务器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-180">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
17. <span data-ttu-id="a5624-181">在中**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="a5624-181">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
18. <span data-ttu-id="a5624-182">在中**对象资源管理器详细信息**选项卡上，右键单击之前更新的程序包，然后单击**导入包**。</span><span class="sxs-lookup"><span data-stu-id="a5624-182">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
19. <span data-ttu-id="a5624-183">在中**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="a5624-183">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
20. <span data-ttu-id="a5624-184">在中**包路径**，导航到保存的项目，选择你想要导入，然后单击的包.dtsx 文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="a5624-184">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
21. <span data-ttu-id="a5624-185">在包名称框以自动填充此框内单击。</span><span class="sxs-lookup"><span data-stu-id="a5624-185">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5624-186">你想要更新的所有包重复步骤 18 通过 21。</span><span class="sxs-lookup"><span data-stu-id="a5624-186">Repeat step 18 through 21 for all the packages that you want to update.</span></span>  
  
22. <span data-ttu-id="a5624-187">单击**确定**，然后单击**是**覆盖。</span><span class="sxs-lookup"><span data-stu-id="a5624-187">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
23. <span data-ttu-id="a5624-188">启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="a5624-188">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="a5624-189">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="a5624-189">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
24. <span data-ttu-id="a5624-190">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="a5624-190">Start the IIS service.</span></span>  
  
25. <span data-ttu-id="a5624-191">启动 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="a5624-191">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="a5624-192">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5624-192">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="a5624-193">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="a5624-193">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="a5624-194">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="a5624-194">**Net start NS$BamAlerts**</span></span>  
  
26. <span data-ttu-id="a5624-195">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="a5624-195">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5624-196">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5624-196">See Also</span></span>  
 [<span data-ttu-id="a5624-197">移动数据库</span><span class="sxs-lookup"><span data-stu-id="a5624-197">Moving Databases</span></span>](../technical-guides/moving-databases.md)