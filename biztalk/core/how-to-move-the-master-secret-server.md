---
title: 如何移动主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b71ee8252d0a268bb3d087f53607c8a58e831c85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384479"
---
# <a name="how-to-move-the-master-secret-server"></a><span data-ttu-id="a323f-102">如何移动主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="a323f-102">How to Move the Master Secret Server</span></span>
<span data-ttu-id="a323f-103">本主题介绍你可以遵循主密钥移到另一台服务器和您可以按照将主密钥从一台服务器移动到 Windows Server 群集的步骤中的步骤。</span><span class="sxs-lookup"><span data-stu-id="a323f-103">This topic documents the steps you can follow to move the master secret from one server to another and the steps you can follow to move the master secret from one server to a Windows Server Cluster.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a><span data-ttu-id="a323f-104">若要将主密钥从一台服务器移动到另一台服务器</span><span class="sxs-lookup"><span data-stu-id="a323f-104">To move the master secret from one server to another server</span></span>  
  
1.  <span data-ttu-id="a323f-105">如果尚未安装，请在新的主密钥服务器上安装 Microsoft 企业单一登录 (SSO) 服务器。</span><span class="sxs-lookup"><span data-stu-id="a323f-105">Install Microsoft Enterprise Single Sign-On (SSO) Server on the new master secret server if it is not already installed.</span></span> <span data-ttu-id="a323f-106">启动从 BizTalk Server CD 上的 \Platform\SSO\setup.exe Microsoft 企业单一登录服务器安装程序。</span><span class="sxs-lookup"><span data-stu-id="a323f-106">Launch Microsoft Enterprise Single Sign-On Server setup from \Platform\SSO\setup.exe on the BizTalk Server CD.</span></span>  
  
2.  <span data-ttu-id="a323f-107">如果未配置新的主密钥服务器上配置企业 SSO。</span><span class="sxs-lookup"><span data-stu-id="a323f-107">Configure Enterprise SSO on the new master secret server if it is not already configured.</span></span> <span data-ttu-id="a323f-108">请按照下列步骤来配置企业 SSO:</span><span class="sxs-lookup"><span data-stu-id="a323f-108">Follow these steps to configure Enterprise SSO:</span></span>  
  
    1.  <span data-ttu-id="a323f-109">打开配置工具。</span><span class="sxs-lookup"><span data-stu-id="a323f-109">Open the Configuration tool.</span></span> <span data-ttu-id="a323f-110">默认情况下，配置工具位于\<驱动器\>: \Program Files\Common Files\Enterprise Single On\Configuration.exe。</span><span class="sxs-lookup"><span data-stu-id="a323f-110">By default, the configuration tool is located at \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On\Configuration.exe.</span></span>  
  
    2.  <span data-ttu-id="a323f-111">单击此项可选择**企业 SSO**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="a323f-111">Click to select **Enterprise SSO** in the left pane.</span></span>  
  
    3.  <span data-ttu-id="a323f-112">选中复选框旁边**启用企业单一登录此计算机上**右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a323f-112">Select the check box next to **Enable Enterprise Single Sign-On on this computer** in the right pane.</span></span>  
  
    4.  <span data-ttu-id="a323f-113">单击选项**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="a323f-113">Click the option to **Join an existing SSO System**.</span></span>  
  
    5.  <span data-ttu-id="a323f-114">指定的现有**服务器名称**并**数据库名称**sso 数据库选项。</span><span class="sxs-lookup"><span data-stu-id="a323f-114">Specify the existing **Server Name** and **Database Name** for the SSO database options.</span></span>  
  
    6.  <span data-ttu-id="a323f-115">指定的现有企业 SSO 服务帐户**企业单一登录服务器 Windows 服务**选项。</span><span class="sxs-lookup"><span data-stu-id="a323f-115">Specify the existing Enterprise SSO service account for the **Enterprise Single Sign-On Server for the Windows Service** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a323f-116">这必须是域帐户。</span><span class="sxs-lookup"><span data-stu-id="a323f-116">This must be a domain account.</span></span>  
  
    7.  <span data-ttu-id="a323f-117">单击选项**应用配置**然后单击**配置**中配置向导对话框中，以完成配置。</span><span class="sxs-lookup"><span data-stu-id="a323f-117">Click the option to **Apply Configuration** and click **Configure** in the Configuration Wizard dialog box to complete the configuration.</span></span>  
  
    8.  <span data-ttu-id="a323f-118">单击**完成**并关闭配置工具。</span><span class="sxs-lookup"><span data-stu-id="a323f-118">Click **Finish** and close the Configuration tool.</span></span>  
  
3.  <span data-ttu-id="a323f-119">备份现有主密钥中的步骤[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="a323f-119">Back up the existing master secret following the steps in [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
4.  <span data-ttu-id="a323f-120">更改主密钥服务器名称以引用新的主密钥服务器在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="a323f-120">Change the master secret server name in the SSO database to reference the new master secret server.</span></span> <span data-ttu-id="a323f-121">例如，新的主密钥服务器的名称可能**NewMSSServer**。</span><span class="sxs-lookup"><span data-stu-id="a323f-121">For example, the name of the new master secret server may be **NewMSSServer**.</span></span> <span data-ttu-id="a323f-122">若要执行此操作，请在原始主服务器上执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a323f-122">To do this, follow these steps on the original master secret server:</span></span>  
  
    1.  <span data-ttu-id="a323f-123">以下代码粘贴到 notepad.exe 等文本编辑器中：</span><span class="sxs-lookup"><span data-stu-id="a323f-123">Paste the following code in a text editor such as notepad.exe:</span></span>  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  <span data-ttu-id="a323f-124">将文件保存为.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="a323f-124">Save the file as .xml file.</span></span> <span data-ttu-id="a323f-125">例如，将该文件作为**NewMSSServer.xml**。</span><span class="sxs-lookup"><span data-stu-id="a323f-125">For example, save the file as **NewMSSServer.xml**.</span></span>  
  
    3.  <span data-ttu-id="a323f-126">在命令提示符下，将更改为企业 SSO 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="a323f-126">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="a323f-127">默认情况下，安装文件夹是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="a323f-127">By default, the installation folder is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="a323f-128">类型**ssomanage-updatedb** *XMLFile*更新数据库中的主密钥服务器名称。</span><span class="sxs-lookup"><span data-stu-id="a323f-128">Type **ssomanage -updatedb** *XMLFile* to update the master secret server name in the database.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a323f-129">替换*XMLFile*与保存的.xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a323f-129">Replace *XMLFile* with the name of the .xml file that you saved.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a323f-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="a323f-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="a323f-131">重新启动新的主密钥服务器上的企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="a323f-131">Restart the Enterprise Single Sign-On service on the new master secret server.</span></span>  
  
6.  <span data-ttu-id="a323f-132">按照中的步骤来还原到新的主密钥服务器上备份主密钥[如何还原主密钥](../core/how-to-restore-the-master-secret.md)上新的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="a323f-132">Restore the backed-up master secret onto the new master secret server by following the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on the new master secret server.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a><span data-ttu-id="a323f-133">若要将主密钥从一台服务器移动到 Windows Server 群集</span><span class="sxs-lookup"><span data-stu-id="a323f-133">To move the master secret from one server to a Windows Server Cluster</span></span>  
  
1.  <span data-ttu-id="a323f-134">安装和配置企业 SSO 服务上的 Windows Server 群集中的步骤[如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。</span><span class="sxs-lookup"><span data-stu-id="a323f-134">Install and configure the Enterprise SSO service on a Windows Server cluster by following the steps in [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span> <span data-ttu-id="a323f-135">完成的步骤中所述的步骤除了本主题中的所有**还原第二个群集节点上的主密钥**部分。</span><span class="sxs-lookup"><span data-stu-id="a323f-135">Complete all of the steps in this topic except for the steps described in the **Restore the master secret on the second cluster node** section.</span></span> <span data-ttu-id="a323f-136">由于要将现有的主密钥服务器移动到群集未选择的选项**创建新的 SSO 系统**群集节点上配置企业 SSO 时。</span><span class="sxs-lookup"><span data-stu-id="a323f-136">Since you will be moving the existing master secret server to the cluster do not choose the option to **Create a new SSO system** when configuring Enterprise SSO on the cluster nodes.</span></span> <span data-ttu-id="a323f-137">在配置每个群集节点时，BizTalk Server 配置程序中设置企业 SSO 功能的以下选项：</span><span class="sxs-lookup"><span data-stu-id="a323f-137">When configuring each cluster node, set the following options for the Enterprise SSO feature in the BizTalk Server Configuration program:</span></span>  
  
    1.  <span data-ttu-id="a323f-138">旁边的复选框**启用企业单一登录此计算机上**。</span><span class="sxs-lookup"><span data-stu-id="a323f-138">Check the box next to **Enable Enterprise Single Sign-On on this computer**.</span></span>  
  
    2.  <span data-ttu-id="a323f-139">单击选项**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="a323f-139">Click the option to **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="a323f-140">输入现有 SSO 数据库服务器名称和数据库名称的值。</span><span class="sxs-lookup"><span data-stu-id="a323f-140">Enter values for the existing SSO Database Server Name and Database Name.</span></span>  
  
    4.  <span data-ttu-id="a323f-141">指定要使用企业单一登录服务的帐户时，请输入现有 SSO 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="a323f-141">Enter the existing SSO Service account when specifying the account to use for the Enterprise Single Sign-On Service.</span></span>  
  
2.  <span data-ttu-id="a323f-142">将现有主密钥备份文件复制到文件夹每个群集节点上 \Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="a323f-142">Copy the existing master secret backup file to the \Enterprise Single Sign-On folder on each cluster node.</span></span>  
  
3.  <span data-ttu-id="a323f-143">如果该 Windows Server 群集将承载一个或多个群集的 BizTalk 主机，则设置为群集主密钥服务器使用 ssomanage 命令行实用工具的所有用户的 SSO 服务器名称。</span><span class="sxs-lookup"><span data-stu-id="a323f-143">If this Windows Server Cluster will host one or more clustered BizTalk hosts, set the SSO Server name for all users to the clustered master secret server with the ssomanage command line utility.</span></span> <span data-ttu-id="a323f-144">此命令应在组中每个 BizTalk Server 上运行的企业 SSO 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="a323f-144">This command should be run from the Enterprise SSO installation folder on each BizTalk Server in the group.</span></span> <span data-ttu-id="a323f-145">例如，下面的命令行将设置为群集主密钥服务器的所有用户的 SSO 服务器名称：</span><span class="sxs-lookup"><span data-stu-id="a323f-145">For example, the following command line will set the SSO Server name for all users to the clustered master secret server:</span></span>  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a323f-146">*SSOCLUSTER*是实际网络名称资源的占位符在包含群集主密钥服务器资源的群集组中创建这种情况下，所有 BizTalk 主机必须都创建为群集资源在同一个在群集企业 SSO 服务资源的群集组。</span><span class="sxs-lookup"><span data-stu-id="a323f-146">*SSOCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group that contains the clustered master secret server resourceIn this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="a323f-147">其中群集企业 SSO 服务的 Windows Server 群集节点上运行的非群集 BizTalk 主机实例不是受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="a323f-147">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="a323f-148">这是因为当群集的企业 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集 BizTalk 主机实例将失败。</span><span class="sxs-lookup"><span data-stu-id="a323f-148">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a323f-149">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="a323f-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="a323f-150">在群集管理器中，右键单击包含群集的企业 SSO 服务资源，群集组，然后单击**使联机**以启动群集组中所有资源。</span><span class="sxs-lookup"><span data-stu-id="a323f-150">In Cluster Administrator, right-click the cluster group that contains the clustered Enterprise SSO service resource, and click **Bring Online** to start all of the resources in the cluster group.</span></span>  
  
5.  <span data-ttu-id="a323f-151">如果该 Windows Server 群集将承载一个或多个群集 BizTalk 主机，更新可在中访问的 SSO 服务器名称**BizTalk 组属性**页以引用群集主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="a323f-151">If this Windows Server Cluster will host one or more clustered BizTalk hosts, update the SSO Server name accessible in the **BizTalk Group Properties** page to reference the clustered master secret server.</span></span> <span data-ttu-id="a323f-152">启动**BizTalk Server 管理**，右键单击 BizTalk 组，然后选择**属性**菜单项，然后更新的条目**SSO 服务器名称**单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a323f-152">Launch **BizTalk Server Administration**, right-click the BizTalk Group and select the **Properties** menu item, then update the entry for **SSO Server name** and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a323f-153">在此方案中，所有 BizTalk 主机都必须都创建为群集企业 SSO 服务资源的同一群集组中的群集资源。</span><span class="sxs-lookup"><span data-stu-id="a323f-153">In this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="a323f-154">其中群集企业 SSO 服务的 Windows Server 群集节点上运行的非群集 BizTalk 主机实例不是受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="a323f-154">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="a323f-155">这是因为当群集的企业 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集 BizTalk 主机实例将失败。</span><span class="sxs-lookup"><span data-stu-id="a323f-155">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
6.  <span data-ttu-id="a323f-156">右键单击企业 SSO 服务的群集的实例，然后单击**转为脱机**，右键单击企业 SSO 服务的群集的实例，然后单击**联机**。</span><span class="sxs-lookup"><span data-stu-id="a323f-156">Right-click the clustered instance of the Enterprise SSO service and click **Take Offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring Online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a323f-157">如果未完成此步骤中，可能会不成功尝试还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="a323f-157">If this step is not completed, attempts to restore the master secret may not succeed.</span></span>  
  
7.  <span data-ttu-id="a323f-158">还原包含群集主密钥服务器的 Windows 群集的每个节点上的备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="a323f-158">Restore the backed-up master secret on each node of the Windows cluster that houses the clustered master secret server.</span></span> <span data-ttu-id="a323f-159">按照中的步骤[如何还原主密钥](../core/how-to-restore-the-master-secret.md)包含群集主密钥服务器在 Windows 群集的每个节点上。</span><span class="sxs-lookup"><span data-stu-id="a323f-159">Follow the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on each node of the Windows cluster that houses the clustered master secret server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a323f-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="a323f-160">See Also</span></span>  
 [<span data-ttu-id="a323f-161">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="a323f-161">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)