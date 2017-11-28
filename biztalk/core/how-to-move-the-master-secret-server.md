---
title: "如何移动主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b35fae6551a95c1c2009ac9786aa791d189f338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-master-secret-server"></a><span data-ttu-id="41dad-102">如何移动主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="41dad-102">How to Move the Master Secret Server</span></span>
<span data-ttu-id="41dad-103">本主题将介绍将主密钥从一个服务器移至另一个服务器时可遵循的步骤以及将主密钥从一个服务器移至 Windows Server 群集时可遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="41dad-103">This topic documents the steps you can follow to move the master secret from one server to another and the steps you can follow to move the master secret from one server to a Windows Server Cluster.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a><span data-ttu-id="41dad-104">将主密钥从一个服务器移至另一个服务器</span><span class="sxs-lookup"><span data-stu-id="41dad-104">To move the master secret from one server to another server</span></span>  
  
1.  <span data-ttu-id="41dad-105">如果尚未在新的主密钥服务器上安装 Microsoft 企业单一登录 (SSO) 服务器，请安装它。</span><span class="sxs-lookup"><span data-stu-id="41dad-105">Install Microsoft Enterprise Single Sign-On (SSO) Server on the new master secret server if it is not already installed.</span></span> <span data-ttu-id="41dad-106">启动 Microsoft 企业单一登录服务器安装程序从 \Platform\SSO\setup.exe [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] CD。</span><span class="sxs-lookup"><span data-stu-id="41dad-106">Launch Microsoft Enterprise Single Sign-On Server setup from \Platform\SSO\setup.exe on the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] CD.</span></span>  
  
2.  <span data-ttu-id="41dad-107">如果尚未配置企业 SSO，则在新的主密钥服务器上对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="41dad-107">Configure Enterprise SSO on the new master secret server if it is not already configured.</span></span> <span data-ttu-id="41dad-108">遵循以下步骤可配置企业 SSO：</span><span class="sxs-lookup"><span data-stu-id="41dad-108">Follow these steps to configure Enterprise SSO:</span></span>  
  
    1.  <span data-ttu-id="41dad-109">打开配置工具。</span><span class="sxs-lookup"><span data-stu-id="41dad-109">Open the Configuration tool.</span></span> <span data-ttu-id="41dad-110">默认情况下，配置工具位于\<驱动器 >: \program Files\Enterprise 单一登录 On\Configuration.exe。</span><span class="sxs-lookup"><span data-stu-id="41dad-110">By default, the configuration tool is located at \<drive>:\Program Files\Common Files\Enterprise Single Sign-On\Configuration.exe.</span></span>  
  
    2.  <span data-ttu-id="41dad-111">单击以选择**企业 SSO**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="41dad-111">Click to select **Enterprise SSO** in the left pane.</span></span>  
  
    3.  <span data-ttu-id="41dad-112">选中的复选框旁边**启用企业单一登录此计算机上**右窗格中。</span><span class="sxs-lookup"><span data-stu-id="41dad-112">Select the check box next to **Enable Enterprise Single Sign-On on this computer** in the right pane.</span></span>  
  
    4.  <span data-ttu-id="41dad-113">单击选项**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="41dad-113">Click the option to **Join an existing SSO System**.</span></span>  
  
    5.  <span data-ttu-id="41dad-114">指定现有**服务器名称**和**数据库名称**对于的 SSO 数据库选项。</span><span class="sxs-lookup"><span data-stu-id="41dad-114">Specify the existing **Server Name** and **Database Name** for the SSO database options.</span></span>  
  
    6.  <span data-ttu-id="41dad-115">指定的现有企业 SSO 服务帐户**企业单一登录服务器 Windows 服务的**选项。</span><span class="sxs-lookup"><span data-stu-id="41dad-115">Specify the existing Enterprise SSO service account for the **Enterprise Single Sign-On Server for the Windows Service** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="41dad-116">此帐户必须为域帐户。</span><span class="sxs-lookup"><span data-stu-id="41dad-116">This must be a domain account.</span></span>  
  
    7.  <span data-ttu-id="41dad-117">单击选项**应用配置**单击**配置**中配置向导对话框中，以完成配置。</span><span class="sxs-lookup"><span data-stu-id="41dad-117">Click the option to **Apply Configuration** and click **Configure** in the Configuration Wizard dialog box to complete the configuration.</span></span>  
  
    8.  <span data-ttu-id="41dad-118">单击**完成**并关闭配置工具。</span><span class="sxs-lookup"><span data-stu-id="41dad-118">Click **Finish** and close the Configuration tool.</span></span>  
  
3.  <span data-ttu-id="41dad-119">备份现有主密钥中的步骤[如何返回向上主密钥](../core/how-to-back-up-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="41dad-119">Back up the existing master secret following the steps in [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
4.  <span data-ttu-id="41dad-120">更改 SSO 数据库中的主密钥服务器名称以引用新的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="41dad-120">Change the master secret server name in the SSO database to reference the new master secret server.</span></span> <span data-ttu-id="41dad-121">例如，新主密钥服务器的名称可能**NewMSSServer**。</span><span class="sxs-lookup"><span data-stu-id="41dad-121">For example, the name of the new master secret server may be **NewMSSServer**.</span></span> <span data-ttu-id="41dad-122">若要执行此操作，请对原始主密钥服务器执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="41dad-122">To do this, follow these steps on the original master secret server:</span></span>  
  
    1.  <span data-ttu-id="41dad-123">将以下代码粘贴在诸如 notepad.exe 之类的文本编辑器中：</span><span class="sxs-lookup"><span data-stu-id="41dad-123">Paste the following code in a text editor such as notepad.exe:</span></span>  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  <span data-ttu-id="41dad-124">将文件保存为.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="41dad-124">Save the file as .xml file.</span></span> <span data-ttu-id="41dad-125">例如，将文件另存**NewMSSServer.xml**。</span><span class="sxs-lookup"><span data-stu-id="41dad-125">For example, save the file as **NewMSSServer.xml**.</span></span>  
  
    3.  <span data-ttu-id="41dad-126">在命令提示符下，将目录更改为企业 SSO 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="41dad-126">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="41dad-127">默认情况下，安装文件夹是\<驱动器 >: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="41dad-127">By default, the installation folder is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="41dad-128">类型**ssomanage updatedb** *XMLFile*来更新数据库中的主密钥服务器名称。</span><span class="sxs-lookup"><span data-stu-id="41dad-128">Type **ssomanage -updatedb** *XMLFile* to update the master secret server name in the database.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="41dad-129">替换*XMLFile*与保存的.xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="41dad-129">Replace *XMLFile* with the name of the .xml file that you saved.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="41dad-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="41dad-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="41dad-131">在新的主密钥服务器上重新启动企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="41dad-131">Restart the Enterprise Single Sign-On service on the new master secret server.</span></span>  
  
6.  <span data-ttu-id="41dad-132">按照中的步骤来还原到新主密钥服务器上的备份主密钥[如何还原主密钥](../core/how-to-restore-the-master-secret.md)新主密钥服务器上。</span><span class="sxs-lookup"><span data-stu-id="41dad-132">Restore the backed-up master secret onto the new master secret server by following the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on the new master secret server.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a><span data-ttu-id="41dad-133">将主密钥从一台服务器移至 Windows Server 群集</span><span class="sxs-lookup"><span data-stu-id="41dad-133">To move the master secret from one server to a Windows Server Cluster</span></span>  
  
1.  <span data-ttu-id="41dad-134">安装和配置企业 SSO 服务在 Windows Server 群集上的中的步骤[如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。</span><span class="sxs-lookup"><span data-stu-id="41dad-134">Install and configure the Enterprise SSO service on a Windows Server cluster by following the steps in [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span> <span data-ttu-id="41dad-135">完成所有中所述的步骤除外本主题中的步骤**还原第二个群集节点上的主密钥**部分。</span><span class="sxs-lookup"><span data-stu-id="41dad-135">Complete all of the steps in this topic except for the steps described in the **Restore the master secret on the second cluster node** section.</span></span> <span data-ttu-id="41dad-136">由于要将现有的主密钥服务器移动到群集不选择此选项**创建新的 SSO 系统**企业 SSO 配置在群集节点上时。</span><span class="sxs-lookup"><span data-stu-id="41dad-136">Since you will be moving the existing master secret server to the cluster do not choose the option to **Create a new SSO system** when configuring Enterprise SSO on the cluster nodes.</span></span> <span data-ttu-id="41dad-137">配置每个群集节点时，请在 BizTalk Server 配置程序中为企业 SSO 功能设置下列选项：</span><span class="sxs-lookup"><span data-stu-id="41dad-137">When configuring each cluster node, set the following options for the Enterprise SSO feature in the BizTalk Server Configuration program:</span></span>  
  
    1.  <span data-ttu-id="41dad-138">旁边的复选框**启用企业单一登录此计算机上**。</span><span class="sxs-lookup"><span data-stu-id="41dad-138">Check the box next to **Enable Enterprise Single Sign-On on this computer**.</span></span>  
  
    2.  <span data-ttu-id="41dad-139">单击选项**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="41dad-139">Click the option to **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="41dad-140">输入现有 SSO 数据库服务器名称和数据库名称的值。</span><span class="sxs-lookup"><span data-stu-id="41dad-140">Enter values for the existing SSO Database Server Name and Database Name.</span></span>  
  
    4.  <span data-ttu-id="41dad-141">在指定用于企业单一登录服务的帐户时指定现有 SSO 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="41dad-141">Enter the existing SSO Service account when specifying the account to use for the Enterprise Single Sign-On Service.</span></span>  
  
2.  <span data-ttu-id="41dad-142">将现有主密钥备份文件复制到每个群集节点上的 \Enterprise Single Sign-On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="41dad-142">Copy the existing master secret backup file to the \Enterprise Single Sign-On folder on each cluster node.</span></span>  
  
3.  <span data-ttu-id="41dad-143">如果该 Windows Server 群集将承载一个或多个群集 BizTalk 主机，请使用 ssomanage 命令行实用工具将所有用户的 SSO 服务器名称设置为群集主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="41dad-143">If this Windows Server Cluster will host one or more clustered BizTalk hosts, set the SSO Server name for all users to the clustered master secret server with the ssomanage command line utility.</span></span> <span data-ttu-id="41dad-144">组中每个 BizTalk 服务器上，应从企业 SSO 安装文件夹运行此命令。</span><span class="sxs-lookup"><span data-stu-id="41dad-144">This command should be run from the Enterprise SSO installation folder on each BizTalk Server in the group.</span></span> <span data-ttu-id="41dad-145">例如，以下命令行会将所有用户的 SSO 服务器名称设置为群集主密钥服务器：</span><span class="sxs-lookup"><span data-stu-id="41dad-145">For example, the following command line will set the SSO Server name for all users to the clustered master secret server:</span></span>  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="41dad-146">*SSOCLUSTER*是实际的网络的占位符名称包含群集的主密钥服务器中在群集组中创建的资源这种情况下，所有 BizTalk 主机必须都创建作为在同一个群集资源为群集的企业 SSO 服务资源的群集组。</span><span class="sxs-lookup"><span data-stu-id="41dad-146">*SSOCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group that contains the clustered master secret server resourceIn this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="41dad-147">不支持在群集企业 SSO 服务的 Windows Server 群集节点上运行非群集 BizTalk 主机实例的配置。</span><span class="sxs-lookup"><span data-stu-id="41dad-147">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="41dad-148">这是因为当群集企业 SSO 服务由于与 SSO 服务上的 BizTalk 主机实例存在依赖关系而将故障转移至另一节点时，非群集 BizTalk 主机实例将失败。</span><span class="sxs-lookup"><span data-stu-id="41dad-148">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41dad-149">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="41dad-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="41dad-150">在群集管理器中，右键单击包含群集的企业 SSO 服务资源的群集组，然后单击**联机**群集组中启动的所有资源。</span><span class="sxs-lookup"><span data-stu-id="41dad-150">In Cluster Administrator, right-click the cluster group that contains the clustered Enterprise SSO service resource, and click **Bring Online** to start all of the resources in the cluster group.</span></span>  
  
5.  <span data-ttu-id="41dad-151">如果此 Windows 服务器群集将承载一个或多个聚集 BizTalk 主机，更新 SSO 服务器名称以访问**BizTalk 组属性**页后，可以引用群集的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="41dad-151">If this Windows Server Cluster will host one or more clustered BizTalk hosts, update the SSO Server name accessible in the **BizTalk Group Properties** page to reference the clustered master secret server.</span></span> <span data-ttu-id="41dad-152">启动**BizTalk Server 管理**，右键单击 BizTalk 组，然后选择**属性**菜单项，然后更新的条目**SSO 服务器名称**单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="41dad-152">Launch **BizTalk Server Administration**, right-click the BizTalk Group and select the **Properties** menu item, then update the entry for **SSO Server name** and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41dad-153">在此情况下，所有 BizTalk 主机都必须在群集企业 SSO 服务资源所在的群集组中创建为群集资源。</span><span class="sxs-lookup"><span data-stu-id="41dad-153">In this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="41dad-154">不支持在群集企业 SSO 服务的 Windows Server 群集节点上运行非群集 BizTalk 主机实例的配置。</span><span class="sxs-lookup"><span data-stu-id="41dad-154">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="41dad-155">这是因为当群集企业 SSO 服务由于与 SSO 服务上的 BizTalk 主机实例存在依赖关系而将故障转移至另一节点时，非群集 BizTalk 主机实例将失败。</span><span class="sxs-lookup"><span data-stu-id="41dad-155">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
6.  <span data-ttu-id="41dad-156">右键单击企业 SSO 服务的群集的实例，然后单击**脱机**、 右键单击企业 SSO 服务的群集的实例，然后单击**联机**。</span><span class="sxs-lookup"><span data-stu-id="41dad-156">Right-click the clustered instance of the Enterprise SSO service and click **Take Offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring Online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41dad-157">如果未完成此步骤，则尝试还原主密钥的操作可能失败。</span><span class="sxs-lookup"><span data-stu-id="41dad-157">If this step is not completed, attempts to restore the master secret may not succeed.</span></span>  
  
7.  <span data-ttu-id="41dad-158">在包含群集主密钥服务器的 Windows 群集的每一个节点上恢复备份的主密钥。</span><span class="sxs-lookup"><span data-stu-id="41dad-158">Restore the backed-up master secret on each node of the Windows cluster that houses the clustered master secret server.</span></span> <span data-ttu-id="41dad-159">按照中的步骤[如何还原主密钥](../core/how-to-restore-the-master-secret.md)保存群集主密钥服务器的 Windows 群集的每个节点上。</span><span class="sxs-lookup"><span data-stu-id="41dad-159">Follow the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on each node of the Windows cluster that houses the clustered master secret server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41dad-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41dad-160">See Also</span></span>  
 [<span data-ttu-id="41dad-161">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="41dad-161">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)