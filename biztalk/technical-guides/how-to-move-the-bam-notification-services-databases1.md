---
title: 如何移动 BAM 通知 Services Databases1 |Microsoft 文档
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
ms.openlocfilehash: 6d0ae3e4b5af7304eb07973fd5e19efce2e68c99
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009798"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a><span data-ttu-id="b09b0-102">如何移动 BAM 通知 Services 数据库</span><span class="sxs-lookup"><span data-stu-id="b09b0-102">How to Move the BAM Notification Services Databases</span></span>
<span data-ttu-id="b09b0-103">可以使用此过程将 BAM Notification Services 数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="b09b0-103">You can use this procedure to move the BAM Notification Services database to another server.</span></span>  <span data-ttu-id="b09b0-104">从端到端方案的角度看，移动 BAM Notification Services 数据库涉及到两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="b09b0-104">From an end-to-end scenario perspective, moving the BAM Notification Services database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="b09b0-105">移动 BAM 通知服务数据库</span><span class="sxs-lookup"><span data-stu-id="b09b0-105">Moving the BAM Notification Services Database</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [<span data-ttu-id="b09b0-106">更新到新的 BAM 通知引用 Services 数据库</span><span class="sxs-lookup"><span data-stu-id="b09b0-106">Updating References to the New BAM Notification Services Databases</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  <span data-ttu-id="b09b0-107">必须一起移动 BAM 通知服务应用程序 (BAMAlertsApplication) 数据库和 BAM 通知服务实例 (BAMAlertsNSMain) 数据库。</span><span class="sxs-lookup"><span data-stu-id="b09b0-107">You must move the BAM Notification Services Application (BAMAlertsApplication) database and the BAM Notification Services Instance (BAMAlertsNSMain) database together.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b09b0-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="b09b0-108">Prerequisites</span></span>  
 <span data-ttu-id="b09b0-109">若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。</span><span class="sxs-lookup"><span data-stu-id="b09b0-109">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_NotiMoveDB"></a><span data-ttu-id="b09b0-110">移动 BAM 通知服务数据库</span><span class="sxs-lookup"><span data-stu-id="b09b0-110">Moving the BAM Notification Services Database</span></span>  
 <span data-ttu-id="b09b0-111">执行以下过程来移动 BAM Notification Services 数据库中的步骤。</span><span class="sxs-lookup"><span data-stu-id="b09b0-111">Perform the steps in the following procedure to move the BAM Notification Services database.</span></span>  
  
#### <a name="to-move-the-bam-notification-services-database"></a><span data-ttu-id="b09b0-112">若要移动 BAM Notification Services 数据库</span><span class="sxs-lookup"><span data-stu-id="b09b0-112">To move the BAM Notification Services database</span></span>  
  
1.  <span data-ttu-id="b09b0-113">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或防止它们运行，直到您已还原 BAM Notification Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="b09b0-113">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Notification Services database.</span></span>  
  
2.  <span data-ttu-id="b09b0-114">停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="b09b0-114">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="b09b0-115">有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="b09b0-115">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="b09b0-116">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="b09b0-116">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="b09b0-117">停止 BAM 警报通知服务：</span><span class="sxs-lookup"><span data-stu-id="b09b0-117">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="b09b0-118">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b09b0-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="b09b0-119">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="b09b0-119">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="b09b0-120">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="b09b0-120">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="b09b0-121">旧服务器上备份 BAM Notification Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="b09b0-121">Back up the BAM Notification Services database on the old server.</span></span> <span data-ttu-id="b09b0-122">有关备份数据库的说明，请遵循的说明[How to： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何备份数据库联机丛书。</span><span class="sxs-lookup"><span data-stu-id="b09b0-122">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b09b0-123">BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="b09b0-123">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
6.  <span data-ttu-id="b09b0-124">BAM Notification Services 数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="b09b0-124">Copy the BAM Notification Services database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="b09b0-125">还原新的服务器上的 BAM Notification Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="b09b0-125">Restore the BAM Notification Services database on the new server.</span></span> <span data-ttu-id="b09b0-126">对于说明还原数据库，请按照说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何还原数据库联机丛书。</span><span class="sxs-lookup"><span data-stu-id="b09b0-126">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b09b0-127">BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="b09b0-127">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
##  <a name="BKMK_NotiUpdate"></a><span data-ttu-id="b09b0-128">更新到新的 BAM 通知引用 Services 数据库</span><span class="sxs-lookup"><span data-stu-id="b09b0-128">Updating References to the New BAM Notification Services Databases</span></span>  
 <span data-ttu-id="b09b0-129">将数据库移动后，你必须更新到新的 BAM Notification Services 数据库的所有引用。</span><span class="sxs-lookup"><span data-stu-id="b09b0-129">After you have moved the database, you must update all the references to the new BAM Notification Services databases.</span></span> <span data-ttu-id="b09b0-130">必须更新以下引用：</span><span class="sxs-lookup"><span data-stu-id="b09b0-130">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="b09b0-131">使用新的数据库和服务器名称更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="b09b0-131">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="b09b0-132">请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig)。</span><span class="sxs-lookup"><span data-stu-id="b09b0-132">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="b09b0-133">重新注册中的所有计算机上的通知服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。</span><span class="sxs-lookup"><span data-stu-id="b09b0-133">Re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="b09b0-134">请参阅[注册 Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister)。</span><span class="sxs-lookup"><span data-stu-id="b09b0-134">See [Register the Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister).</span></span>  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a><span data-ttu-id="b09b0-135">若要更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="b09b0-135">To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="b09b0-136">获取用于还原 BAM 的 .xml 文件的副本：</span><span class="sxs-lookup"><span data-stu-id="b09b0-136">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="b09b0-137">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b09b0-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="b09b0-138">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="b09b0-138">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="b09b0-139">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：</span><span class="sxs-lookup"><span data-stu-id="b09b0-139">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="b09b0-140">**%Programfiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="b09b0-140">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="b09b0-141">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="b09b0-141">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="b09b0-142">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="b09b0-142">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="b09b0-143">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="b09b0-143">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="b09b0-144">**Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -数据库：\<数据库\>**</span><span class="sxs-lookup"><span data-stu-id="b09b0-144">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b09b0-145">运行此命令时, 替换从其获取的配置信息的服务器的实际名称<servername>和替换从其获取的配置信息的数据库的实际名称<database>。</span><span class="sxs-lookup"><span data-stu-id="b09b0-145">When running this command, substitute the actual name of the server from which to get the configuration information for <servername> and substitute the actual name of the database from which to get the configuration information for <database>.</span></span> <span data-ttu-id="b09b0-146">有关使用 BAM 管理 (BM) 实用工具的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="b09b0-146">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="b09b0-147">编辑 BAMConfiguration.xml 文件并将更改**DBServer**中的属性`<DeploymentUnit Name="Alert">`到新的服务器名称的部分。</span><span class="sxs-lookup"><span data-stu-id="b09b0-147">Edit the BAMConfiguration.xml file and change the **DBServer** properties in the `<DeploymentUnit Name="Alert">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="b09b0-148">保存并关闭 BAMConfiguration.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="b09b0-148">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="b09b0-149">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b09b0-149">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b09b0-150">在运行 BizTalk Server 的计算机，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="b09b0-150">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="b09b0-151">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：</span><span class="sxs-lookup"><span data-stu-id="b09b0-151">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="b09b0-152">**%Programfiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="b09b0-152">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="b09b0-153">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：</span><span class="sxs-lookup"><span data-stu-id="b09b0-153">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="b09b0-154">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="b09b0-154">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="b09b0-155">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="b09b0-155">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="b09b0-156">**bm.exe 更新-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="b09b0-156">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_NotiRegister"></a><span data-ttu-id="b09b0-157">注册通知服务</span><span class="sxs-lookup"><span data-stu-id="b09b0-157">Register the Notification Services</span></span>  
 <span data-ttu-id="b09b0-158">将 BAM Notification Services 数据库移动后，你必须重新注册 BizTalk Server 组中所有正在运行通知服务 (NSservice.exe) 的计算机上的通知服务。</span><span class="sxs-lookup"><span data-stu-id="b09b0-158">After you have moved the BAM Notification Services database, you must re-register the Notification Service on all computers in the BizTalk Server group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="b09b0-159">这样可使 Notification Services 连接到新位置上的数据库。</span><span class="sxs-lookup"><span data-stu-id="b09b0-159">This enables Notification Services to connect to the databases in their new location.</span></span> <span data-ttu-id="b09b0-160">有关如何注册通知服务的说明，请按照步骤 5 至 11[如何对 BAM 通知服务数据库的更新引用](http://go.microsoft.com/fwlink/?LinkId=156684)(http://go.microsoft.com/fwlink/?LinkId=156684) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="b09b0-160">For instructions on how to register the Notification Services, follow steps 5 through 11 at [How to Update References to the BAM Notification Services Databases](http://go.microsoft.com/fwlink/?LinkId=156684) (http://go.microsoft.com/fwlink/?LinkId=156684) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="b09b0-161">注意在执行前面的链接中所述的步骤时以下信息：</span><span class="sxs-lookup"><span data-stu-id="b09b0-161">Note the following while performing steps mentioned in the preceding link:</span></span>  
  
-   <span data-ttu-id="b09b0-162">必须针对以下属性的 BAM 配置 XML 中列出的服务器上执行步骤 5 和 6 上述链接中：</span><span class="sxs-lookup"><span data-stu-id="b09b0-162">Steps 5 and 6 in the preceding link must be performed on the servers listed in the BAM configuration XML for the following properties:</span></span>  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   <span data-ttu-id="b09b0-163">步骤 7 至 11，必须在承载 BAM 门户的计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="b09b0-163">Step 7 through 11 must be performed on the computer that hosts the BAM portal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09b0-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b09b0-164">See Also</span></span>  
 [<span data-ttu-id="b09b0-165">移动数据库</span><span class="sxs-lookup"><span data-stu-id="b09b0-165">Moving Databases</span></span>](../technical-guides/moving-databases.md)