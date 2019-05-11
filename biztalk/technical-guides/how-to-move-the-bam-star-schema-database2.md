---
title: 如何移动 BAM 星型架构数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6832ac2-c8c5-4515-883e-26d125d6ace0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486e8bb9481a08c0f7d017362b6d2a9ab3940a05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393483"
---
# <a name="how-to-move-the-bam-star-schema-database"></a><span data-ttu-id="fcba3-102">如何移动 BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="fcba3-102">How to Move the BAM Star Schema Database</span></span>
<span data-ttu-id="fcba3-103">可以使用此过程将 BAM 星型架构数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="fcba3-103">You can use this procedure to move the BAM Star Schema database to another server.</span></span>  <span data-ttu-id="fcba3-104">从端到端方案的角度看，移动 BAM 星型架构数据库涉及两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="fcba3-104">From an end-to-end scenario perspective, moving the BAM Star Schema database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="fcba3-105">移动 BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="fcba3-105">Moving the BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarMoveDB)  
  
-   [<span data-ttu-id="fcba3-106">正在更新到新的 BAM 星型架构数据库的引用</span><span class="sxs-lookup"><span data-stu-id="fcba3-106">Updating References to the New BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)  
  
## <a name="prerequisites"></a><span data-ttu-id="fcba3-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="fcba3-107">Prerequisites</span></span>  
 <span data-ttu-id="fcba3-108">您必须是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="fcba3-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_StarMoveDB"></a> <span data-ttu-id="fcba3-109">移动 BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="fcba3-109">Moving the BAM Star Schema Database</span></span>  
 <span data-ttu-id="fcba3-110">以下过程来移动 BAM 星型架构数据库中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="fcba3-110">Perform the steps in the following procedure to move the BAM Star Schema database.</span></span>  
  
#### <a name="to-move-the-bam-star-schema-database"></a><span data-ttu-id="fcba3-111">移动 BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="fcba3-111">To move the BAM Star Schema database</span></span>  
  
1. <span data-ttu-id="fcba3-112">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM 星型架构数据库的还原。</span><span class="sxs-lookup"><span data-stu-id="fcba3-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Star Schema database.</span></span>  
  
2. <span data-ttu-id="fcba3-113">停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="fcba3-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="fcba3-114">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="fcba3-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="fcba3-115">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="fcba3-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="fcba3-116">停止 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="fcba3-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="fcba3-117">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="fcba3-118">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="fcba3-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="fcba3-119">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="fcba3-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="fcba3-120">在旧服务器上备份 BAM 星型架构数据库。</span><span class="sxs-lookup"><span data-stu-id="fcba3-120">Back up the BAM Star Schema database on the old server.</span></span> <span data-ttu-id="fcba3-121">备份数据库的说明，请遵循的说明[如何：备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何备份数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="fcba3-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6. <span data-ttu-id="fcba3-122">将 BAM 星型架构数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="fcba3-122">Copy the BAM Star Schema database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="fcba3-123">还原新服务器上的 BAM 星型架构数据库。</span><span class="sxs-lookup"><span data-stu-id="fcba3-123">Restore the BAM Star Schema database on the new server.</span></span> <span data-ttu-id="fcba3-124">对于还原数据库的说明，请按照的说明[如何：还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何还原数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="fcba3-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_StarUpdate"></a> <span data-ttu-id="fcba3-125">正在更新到新的 BAM 星型架构数据库的引用</span><span class="sxs-lookup"><span data-stu-id="fcba3-125">Updating References to the New BAM Star Schema Database</span></span>  
 <span data-ttu-id="fcba3-126">在移动数据库之后，必须更新到新的 BAM 星型架构数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="fcba3-126">After you have moved the database, you must update all the references to the new BAM Star Schema Database.</span></span> <span data-ttu-id="fcba3-127">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="fcba3-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="fcba3-128">使用新的数据库和服务器名称更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="fcba3-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="fcba3-129">请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig)。</span><span class="sxs-lookup"><span data-stu-id="fcba3-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="fcba3-130">更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="fcba3-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="fcba3-131">请参阅[来更新服务器和数据库名称在所有 BAM SSIS 程序包](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef)。</span><span class="sxs-lookup"><span data-stu-id="fcba3-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef).</span></span>  
  
-   <span data-ttu-id="fcba3-132">更新新服务器和数据库名称在数据源中的所有非 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="fcba3-132">Update the new server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="fcba3-133">请参阅[来更新服务器和数据源中的所有非 OLAP 多维数据集的数据库名称](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP)。</span><span class="sxs-lookup"><span data-stu-id="fcba3-133">See [To update server and database names in data sources for all non-OLAP cubes](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP).</span></span>  
  
###  <a name="BKMK_StarUpdateBAMConfig"></a> <span data-ttu-id="fcba3-134">若要更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="fcba3-134">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="fcba3-135">获取用于还原 BAM 的.xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="fcba3-135">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="fcba3-136">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-136">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="fcba3-137">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="fcba3-137">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="fcba3-138">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="fcba3-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="fcba3-139">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="fcba3-139">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="fcba3-140">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="fcba3-140">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="fcba3-141">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="fcba3-141">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="fcba3-142">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="fcba3-142">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="fcba3-143">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span><span class="sxs-lookup"><span data-stu-id="fcba3-143">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="fcba3-144">当运行此命令，替换从其获取的配置信息的服务器的实际名称\<servername\>并将其替换实际获取的配置信息的数据库的名称\<数据库\>。</span><span class="sxs-lookup"><span data-stu-id="fcba3-144">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="fcba3-145">有关使用 BAM 管理 (BM) 实用程序的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="fcba3-145">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="fcba3-146">编辑 BAMConfiguration.xml 文件，将**ServerName**中`<DeploymentUnit Name="StarSchemaDatabase">`到新的服务器名称的部分。</span><span class="sxs-lookup"><span data-stu-id="fcba3-146">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="StarSchemaDatabase">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="fcba3-147">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="fcba3-147">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="fcba3-148">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-148">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="fcba3-149">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="fcba3-149">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="fcba3-150">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="fcba3-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="fcba3-151">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="fcba3-151">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="fcba3-152">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="fcba3-152">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="fcba3-153">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="fcba3-153">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="fcba3-154">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="fcba3-154">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="fcba3-155">**bm.exe update-config -FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="fcba3-155">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_StarUpdateRef"></a> <span data-ttu-id="fcba3-156">若要更新服务器和数据库名称中的所有 BAM SSIS 包</span><span class="sxs-lookup"><span data-stu-id="fcba3-156">To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="fcba3-157">更新所有 BAM 分析 SSIS 包中，带有"BAM_AN_"前缀的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="fcba3-157">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_".</span></span> <span data-ttu-id="fcba3-158">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-158">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="fcba3-159">在 SQL Server Business Intelligence Development Studio，创建新项目。</span><span class="sxs-lookup"><span data-stu-id="fcba3-159">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="fcba3-160">单击**文件**，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-160">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="fcba3-161">在中**新的项目**对话框中**项目类型**框中，单击**商业智能项目**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-161">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="fcba3-162">在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-162">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fcba3-163">在中**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-163">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="fcba3-164">在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_AN_ \* 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="fcba3-164">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_\* packages.</span></span>  
  
6.  <span data-ttu-id="fcba3-165">在中**包路径**，请单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="fcba3-165">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="fcba3-166">在中**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-166">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="fcba3-167">包现在列在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="fcba3-167">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="fcba3-168">在解决方案资源管理器，双击上一步中添加的包。</span><span class="sxs-lookup"><span data-stu-id="fcba3-168">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="fcba3-169">在中**连接管理器**选项卡 （可用于在屏幕下半部分） 中，双击数据源数 2 （BAMStarSchema 数据库）。</span><span class="sxs-lookup"><span data-stu-id="fcba3-169">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMStarSchema database).</span></span>  
  
9. <span data-ttu-id="fcba3-170">在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-170">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcba3-171">数据源编号 3(MSDB 数据库） 重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="fcba3-171">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="fcba3-172">在中**连接管理器**选项卡上，双击数据源编号 4 （BAMAnalysis 数据库）。</span><span class="sxs-lookup"><span data-stu-id="fcba3-172">In the **Connection Managers** tab, double-click data source number 4 (BAMAnalysis database).</span></span> <span data-ttu-id="fcba3-173">在中**添加 Analysis Services 连接管理器**对话框中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-173">In the **Add Analysis Services Connection Manager** dialog box, click **Edit**.</span></span>  
  
11. <span data-ttu-id="fcba3-174">在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-174">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, click **OK**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="fcba3-175">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后将更新的值**AnalysisDatabase**， **AnalysisServer**， **PrimaryImportDatabase**， **PrimaryImportServer**， **StarSchemaDatabase**，和**StarSchemaServer**变量。</span><span class="sxs-lookup"><span data-stu-id="fcba3-175">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **AnalysisDatabase**, **AnalysisServer**, **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, and **StarSchemaServer** variables.</span></span> <span data-ttu-id="fcba3-176">必须更新为指向新的服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="fcba3-176">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcba3-177">重复步骤 4 到 12 的你想要更新的所有包。</span><span class="sxs-lookup"><span data-stu-id="fcba3-177">Repeat step 4 through 12 for all the packages that you want to update.</span></span>  
  
13. <span data-ttu-id="fcba3-178">然后单击**文件**菜单，并单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-178">Click then **File** menu, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="fcba3-179">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="fcba3-179">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="fcba3-180">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-180">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
15. <span data-ttu-id="fcba3-181">在中**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-181">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
16. <span data-ttu-id="fcba3-182">指定服务器名称和凭据以连接到服务器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-182">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
17. <span data-ttu-id="fcba3-183">在中**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-183">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
18. <span data-ttu-id="fcba3-184">在中**对象资源管理器详细信息**选项卡上，右键单击之前更新的程序包，然后单击**导入包**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-184">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
19. <span data-ttu-id="fcba3-185">在中**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-185">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
20. <span data-ttu-id="fcba3-186">在中**包路径**，导航到保存的项目，选择你想要导入，然后单击的包.dtsx 文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-186">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
21. <span data-ttu-id="fcba3-187">在包名称框以自动填充此框内单击。</span><span class="sxs-lookup"><span data-stu-id="fcba3-187">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcba3-188">你想要更新的所有包重复步骤 18 通过 21。</span><span class="sxs-lookup"><span data-stu-id="fcba3-188">Repeat step 18 through 21 for all the packages that you want to update.</span></span>  
  
22. <span data-ttu-id="fcba3-189">单击**确定**，然后单击**是**覆盖。</span><span class="sxs-lookup"><span data-stu-id="fcba3-189">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
23. <span data-ttu-id="fcba3-190">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="fcba3-190">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
###  <a name="BKMK_UpdateDS_non_OLAP"></a> <span data-ttu-id="fcba3-191">若要更新服务器和数据源中的所有非 OLAP 多维数据集的数据库名称</span><span class="sxs-lookup"><span data-stu-id="fcba3-191">To update server and database names in data sources for all non-OLAP cubes</span></span>  
  
1. <span data-ttu-id="fcba3-192">更新服务器和数据库名称在数据源中的所有非 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="fcba3-192">Update the server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="fcba3-193">若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-193">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="fcba3-194">在中**连接到服务器**对话框中，对于**服务器类型**下拉列表中，选择**Analysis Services**，提供服务器名称、 选择身份验证方法 （和提供凭据如果需要），然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-194">In the **Connect to Server** dialog box, for the **Server type** drop-down list select **Analysis Services**, provide the server name, select an authentication method (and provide credentials if required), and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="fcba3-195">在对象资源管理器，展开**数据库**，展开**BAMAnalysis**，展开**数据源**，然后双击数据源。</span><span class="sxs-lookup"><span data-stu-id="fcba3-195">In the Object Explorer, expand **Databases**, expand **BAMAnalysis**, expand **Data Sources**, and then double-click a data source.</span></span>  
  
4. <span data-ttu-id="fcba3-196">在中**数据源属性**对话框框中，单击省略号按钮 **（...）** 针对**连接字符串**属性。</span><span class="sxs-lookup"><span data-stu-id="fcba3-196">In the **Data Source Properties** dialog box, click the ellipsis button **(…)** against the **Connection String** property.</span></span>  
  
5. <span data-ttu-id="fcba3-197">在中**连接管理器**对话框中**服务器名称**框中，输入承载 BAMStarSchema 数据库的服务器的名称，单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-197">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server hosting the BAMStarSchema database, click **OK**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="fcba3-198">启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="fcba3-198">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="fcba3-199">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="fcba3-199">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
7. <span data-ttu-id="fcba3-200">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="fcba3-200">Start the IIS service.</span></span>  
  
8. <span data-ttu-id="fcba3-201">启动 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="fcba3-201">Start the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="fcba3-202">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fcba3-202">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="fcba3-203">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="fcba3-203">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="fcba3-204">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="fcba3-204">**Net start NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="fcba3-205">解决任何未完成的跟踪实例。</span><span class="sxs-lookup"><span data-stu-id="fcba3-205">Resolve any incomplete trace instances.</span></span>  <span data-ttu-id="fcba3-206">有关解决不完整的 BAM 活动实例的信息，请参阅[如何解析不完整活动实例](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)。</span><span class="sxs-lookup"><span data-stu-id="fcba3-206">For information about resolving incomplete BAM activity instances, see [How to Resolve Incomplete Activity Instances](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="fcba3-207">很好的做法是，还应将 BAM_AN_ \* SSIS 包移动到 BAMStarSchema 数据库的宿主服务器。</span><span class="sxs-lookup"><span data-stu-id="fcba3-207">As a good practice, you should also move the BAM_AN_\* SSIS packages to the server hosting the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcba3-208">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcba3-208">See Also</span></span>  
 [<span data-ttu-id="fcba3-209">移动数据库</span><span class="sxs-lookup"><span data-stu-id="fcba3-209">Moving Databases</span></span>](../technical-guides/moving-databases.md)