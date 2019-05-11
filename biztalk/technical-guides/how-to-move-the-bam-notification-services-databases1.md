---
title: 如何移动 BAM Notification Services Databases1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 735a0e5d1d84c589948dcf5e075a665c66c50a94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393505"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a><span data-ttu-id="824c1-102">如何移动 BAM Notification Services 数据库</span><span class="sxs-lookup"><span data-stu-id="824c1-102">How to Move the BAM Notification Services Databases</span></span>
<span data-ttu-id="824c1-103">可以使用此过程将 BAM Notification Services 数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="824c1-103">You can use this procedure to move the BAM Notification Services database to another server.</span></span>  <span data-ttu-id="824c1-104">从端到端方案的角度看，移动 BAM Notification Services 数据库涉及到两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="824c1-104">From an end-to-end scenario perspective, moving the BAM Notification Services database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="824c1-105">移动 BAM 通知服务数据库</span><span class="sxs-lookup"><span data-stu-id="824c1-105">Moving the BAM Notification Services Database</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [<span data-ttu-id="824c1-106">正在更新引用对新的 BAM Notification Services 数据库</span><span class="sxs-lookup"><span data-stu-id="824c1-106">Updating References to the New BAM Notification Services Databases</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  <span data-ttu-id="824c1-107">必须一起移动 BAM Notification Services 应用程序 (BAMAlertsApplication) 数据库和 BAM Notification Services 实例 (BAMAlertsNSMain) 数据库。</span><span class="sxs-lookup"><span data-stu-id="824c1-107">You must move the BAM Notification Services Application (BAMAlertsApplication) database and the BAM Notification Services Instance (BAMAlertsNSMain) database together.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="824c1-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="824c1-108">Prerequisites</span></span>  
 <span data-ttu-id="824c1-109">您必须是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="824c1-109">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_NotiMoveDB"></a> <span data-ttu-id="824c1-110">移动 BAM 通知服务数据库</span><span class="sxs-lookup"><span data-stu-id="824c1-110">Moving the BAM Notification Services Database</span></span>  
 <span data-ttu-id="824c1-111">以下过程来移动 BAM Notification Services 数据库中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="824c1-111">Perform the steps in the following procedure to move the BAM Notification Services database.</span></span>  
  
#### <a name="to-move-the-bam-notification-services-database"></a><span data-ttu-id="824c1-112">移动 BAM Notification Services 数据库</span><span class="sxs-lookup"><span data-stu-id="824c1-112">To move the BAM Notification Services database</span></span>  
  
1. <span data-ttu-id="824c1-113">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM Notification Services 数据库的还原。</span><span class="sxs-lookup"><span data-stu-id="824c1-113">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Notification Services database.</span></span>  
  
2. <span data-ttu-id="824c1-114">停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="824c1-114">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="824c1-115">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="824c1-115">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="824c1-116">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="824c1-116">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="824c1-117">停止 BAM 警报 Notification service:</span><span class="sxs-lookup"><span data-stu-id="824c1-117">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="824c1-118">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="824c1-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="824c1-119">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="824c1-119">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="824c1-120">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="824c1-120">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="824c1-121">在旧服务器上备份 BAM Notification Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="824c1-121">Back up the BAM Notification Services database on the old server.</span></span> <span data-ttu-id="824c1-122">备份数据库的说明，请遵循的说明[如何：备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何备份数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="824c1-122">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="824c1-123">BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="824c1-123">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
6. <span data-ttu-id="824c1-124">将 BAM Notification Services 数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="824c1-124">Copy the BAM Notification Services database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="824c1-125">还原新服务器上的 BAM Notification Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="824c1-125">Restore the BAM Notification Services database on the new server.</span></span> <span data-ttu-id="824c1-126">对于还原数据库的说明，请按照的说明[如何：还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何还原数据库的联机丛书。</span><span class="sxs-lookup"><span data-stu-id="824c1-126">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="824c1-127">BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="824c1-127">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
##  <a name="BKMK_NotiUpdate"></a> <span data-ttu-id="824c1-128">正在更新引用对新的 BAM Notification Services 数据库</span><span class="sxs-lookup"><span data-stu-id="824c1-128">Updating References to the New BAM Notification Services Databases</span></span>  
 <span data-ttu-id="824c1-129">在移动数据库之后，必须更新到新的 BAM Notification Services 数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="824c1-129">After you have moved the database, you must update all the references to the new BAM Notification Services databases.</span></span> <span data-ttu-id="824c1-130">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="824c1-130">The following references must be updated:</span></span>  
  
- <span data-ttu-id="824c1-131">使用新的数据库和服务器名称更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="824c1-131">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="824c1-132">请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig)。</span><span class="sxs-lookup"><span data-stu-id="824c1-132">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig).</span></span>  
  
- <span data-ttu-id="824c1-133">重新注册中的所有计算机上的通知服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。</span><span class="sxs-lookup"><span data-stu-id="824c1-133">Re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="824c1-134">请参阅[注册 Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister)。</span><span class="sxs-lookup"><span data-stu-id="824c1-134">See [Register the Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister).</span></span>  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a> <span data-ttu-id="824c1-135">若要更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="824c1-135">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="824c1-136">获取用于还原 BAM 的.xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="824c1-136">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="824c1-137">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="824c1-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="824c1-138">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="824c1-138">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="824c1-139">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="824c1-139">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="824c1-140">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="824c1-140">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="824c1-141">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="824c1-141">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="824c1-142">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="824c1-142">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="824c1-143">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="824c1-143">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="824c1-144">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span><span class="sxs-lookup"><span data-stu-id="824c1-144">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="824c1-145">当运行此命令，替换从其获取的配置信息的服务器的实际名称<servername>并将其替换从其获取的配置信息的数据库的实际名称<database>。</span><span class="sxs-lookup"><span data-stu-id="824c1-145">When running this command, substitute the actual name of the server from which to get the configuration information for <servername> and substitute the actual name of the database from which to get the configuration information for <database>.</span></span> <span data-ttu-id="824c1-146">有关使用 BAM 管理 (BM) 实用程序的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="824c1-146">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="824c1-147">编辑 BAMConfiguration.xml 文件，将**数据库服务器**中的属性`<DeploymentUnit Name="Alert">`到新的服务器名称的部分。</span><span class="sxs-lookup"><span data-stu-id="824c1-147">Edit the BAMConfiguration.xml file and change the **DBServer** properties in the `<DeploymentUnit Name="Alert">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="824c1-148">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="824c1-148">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="824c1-149">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="824c1-149">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="824c1-150">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="824c1-150">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="824c1-151">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="824c1-151">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="824c1-152">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="824c1-152">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="824c1-153">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="824c1-153">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="824c1-154">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="824c1-154">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="824c1-155">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="824c1-155">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="824c1-156">**bm.exe update-config -FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="824c1-156">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_NotiRegister"></a> <span data-ttu-id="824c1-157">注册 Notification Services</span><span class="sxs-lookup"><span data-stu-id="824c1-157">Register the Notification Services</span></span>  
 <span data-ttu-id="824c1-158">移动 BAM Notification Services 数据库后，必须重新注册 Notification Service 的 BizTalk Server 组中运行 Notification Services (NSservice.exe) 的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="824c1-158">After you have moved the BAM Notification Services database, you must re-register the Notification Service on all computers in the BizTalk Server group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="824c1-159">这可使 Notification Services 连接到其新位置中的数据库。</span><span class="sxs-lookup"><span data-stu-id="824c1-159">This enables Notification Services to connect to the databases in their new location.</span></span> <span data-ttu-id="824c1-160">有关如何注册 Notification Services 的说明，请按照步骤 5 到 11[如何更新对 BAM Notification Services 数据库的引用](http://go.microsoft.com/fwlink/?LinkId=156684)(<http://go.microsoft.com/fwlink/?LinkId=156684>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="824c1-160">For instructions on how to register the Notification Services, follow steps 5 through 11 at [How to Update References to the BAM Notification Services Databases](http://go.microsoft.com/fwlink/?LinkId=156684) (<http://go.microsoft.com/fwlink/?LinkId=156684>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="824c1-161">请注意以下时执行上述链接中所述的步骤：</span><span class="sxs-lookup"><span data-stu-id="824c1-161">Note the following while performing steps mentioned in the preceding link:</span></span>  
  
-   <span data-ttu-id="824c1-162">必须在 BAM 配置 XML 中的以下属性中列出的服务器上执行步骤 5 和 6 上述链接中：</span><span class="sxs-lookup"><span data-stu-id="824c1-162">Steps 5 and 6 in the preceding link must be performed on the servers listed in the BAM configuration XML for the following properties:</span></span>  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   <span data-ttu-id="824c1-163">步骤 7 至 11 必须在承载 BAM 门户的计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="824c1-163">Step 7 through 11 must be performed on the computer that hosts the BAM portal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824c1-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="824c1-164">See Also</span></span>  
 [<span data-ttu-id="824c1-165">移动数据库</span><span class="sxs-lookup"><span data-stu-id="824c1-165">Moving Databases</span></span>](../technical-guides/moving-databases.md)