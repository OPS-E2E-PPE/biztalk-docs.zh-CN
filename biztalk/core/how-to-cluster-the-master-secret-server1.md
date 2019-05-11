---
title: 如何群集主密钥机密 Server1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, second node
- Master Secret server, restoring
- clustering, Master Secret server
- Master Secret server, clustering
ms.assetid: ef817fa4-e43d-4e3d-8686-5bd675708001
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88f7b25a8cf3138862e65f7c8bd96f041fc512d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386956"
---
# <a name="how-to-cluster-the-master-secret-server"></a><span data-ttu-id="98473-102">如何群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="98473-102">How to Cluster the Master Secret Server</span></span>
<span data-ttu-id="98473-103">我们建议你遵循本部分中的说明已成功在主密钥服务器上群集企业单一登录 (SSO) 服务。</span><span class="sxs-lookup"><span data-stu-id="98473-103">We recommended that you follow the instructions in this section to cluster the Enterprise Single Sign-On (SSO) service on the master secret server successfully.</span></span>  
  
 <span data-ttu-id="98473-104">当群集主密钥服务器时，实现单一登录服务器将与主密钥服务器的主动群集实例通信。</span><span class="sxs-lookup"><span data-stu-id="98473-104">When you cluster the master secret server, the Single Sign-On servers communicate with the active clustered instance of the master secret server.</span></span> <span data-ttu-id="98473-105">同样，主密钥服务器的主动群集的实例与 SSO 数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="98473-105">Similarly, the active clustered instance of the master secret server communicates with the SSO database.</span></span>  
  
 <span data-ttu-id="98473-106">必须是 SSO 管理员才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="98473-106">You must be an SSO administrator to perform this procedure.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="98473-107">不能在网络负载平衡 (NLB) 群集上安装主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="98473-107">You cannot install the master secret server on a Network Load Balancing (NLB) cluster.</span></span>  
  
### <a name="to-install-and-configure-enterprise-sso-on-the-cluster-nodes"></a><span data-ttu-id="98473-108">若要安装和群集节点上配置企业 SSO</span><span class="sxs-lookup"><span data-stu-id="98473-108">To install and configure Enterprise SSO on the cluster nodes</span></span>  
  
1. <span data-ttu-id="98473-109">安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]每个群集节点上。</span><span class="sxs-lookup"><span data-stu-id="98473-109">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on each cluster node.</span></span> <span data-ttu-id="98473-110">在中**组件安装**，选择**企业单一登录管理模块**并**企业单一登录主密钥服务器**。</span><span class="sxs-lookup"><span data-stu-id="98473-110">In **Component Installation**, select **Enterprise Single Sign-On Administration Module** and **Enterprise Single Sign-On Master Secret Server**.</span></span> <span data-ttu-id="98473-111">安装已成功完成后，请执行**不**运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。</span><span class="sxs-lookup"><span data-stu-id="98473-111">After installation has completed successfully, do **not** run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
2. <span data-ttu-id="98473-112">创建**SSO Administrators**并**SSO Affiliate Administrators**域组。</span><span class="sxs-lookup"><span data-stu-id="98473-112">Create **SSO Administrators** and **SSO Affiliate Administrators** domain groups.</span></span> <span data-ttu-id="98473-113">若要创建企业 SSO 服务的群集的实例，必须为域组中创建这些组。</span><span class="sxs-lookup"><span data-stu-id="98473-113">To create a clustered instance of the Enterprise SSO service, you must create these groups as domain groups.</span></span>  
  
3. <span data-ttu-id="98473-114">创建或指定的成员的域帐户**SSO Administrators**域组。</span><span class="sxs-lookup"><span data-stu-id="98473-114">Create or designate a domain account that is a member of the **SSO Administrators** domain group.</span></span> <span data-ttu-id="98473-115">每个节点上的企业 SSO 服务配置为作为此域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="98473-115">The Enterprise SSO service on each node is configured to log on as this domain account.</span></span> <span data-ttu-id="98473-116">此帐户必须具有**作为服务登录**直接在群集中每个节点上。</span><span class="sxs-lookup"><span data-stu-id="98473-116">This account must have the **Log on as a service** right on each node in the cluster.</span></span>  
  
4. <span data-ttu-id="98473-117">您用来登录到域在配置过程中的帐户添加**SSO Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="98473-117">Add the account that you are using to log on during the configuration process to the domain **SSO Administrators** group.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="98473-118">如果未完成步骤 3 和 4，企业 SSO 服务的配置将失败。</span><span class="sxs-lookup"><span data-stu-id="98473-118">Configuration of the Enterprise SSO service fails if steps 3 and 4 are not completed.</span></span>  
  
5. <span data-ttu-id="98473-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。</span><span class="sxs-lookup"><span data-stu-id="98473-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
6. <span data-ttu-id="98473-120">选择**自定义配置**选项并输入**数据库服务器名称**，**用户名**，以及**密码**值。</span><span class="sxs-lookup"><span data-stu-id="98473-120">Select **Custom Configuration** option and enter the **Database server name**, **User name**, and **Password** values.</span></span> <span data-ttu-id="98473-121">选择**配置**以继续。</span><span class="sxs-lookup"><span data-stu-id="98473-121">Select **Configure** to continue.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="98473-122">因为您只是这次配置企业 SSO 服务，你可以只输入前面步骤中创建的域帐户。</span><span class="sxs-lookup"><span data-stu-id="98473-122">Since you are only be configuring the Enterprise SSO service at this time, you can just enter the domain account that you created earlier here.</span></span>  
  
7. <span data-ttu-id="98473-123">选择**企业 SSO**选项在左窗格中，并设置以下选项为企业 SSO 功能：</span><span class="sxs-lookup"><span data-stu-id="98473-123">Select the **Enterprise SSO** option from the left pane and set the following options for the Enterprise SSO feature:</span></span>  
  
   1.  <span data-ttu-id="98473-124">选择**启用企业单一登录此计算机上**复选框。</span><span class="sxs-lookup"><span data-stu-id="98473-124">Select the **Enable Enterprise Single Sign-On on this computer** check box.</span></span>  
  
   2.  <span data-ttu-id="98473-125">选择**创建新的 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="98473-125">Select **Create a new SSO system**.</span></span>  
  
   3.  <span data-ttu-id="98473-126">输入**数据存储区**有关**服务器名称**并**数据库名称**值。</span><span class="sxs-lookup"><span data-stu-id="98473-126">Enter the **Data stores** for **Server Name** and **Database Name** values.</span></span>  
  
   4.  <span data-ttu-id="98473-127">验证前面创建的域帐户是与企业 SSO 服务相关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="98473-127">Verify that the domain account that you created earlier is the account that is associated with the Enterprise SSO service.</span></span>  
  
   5.  <span data-ttu-id="98473-128">输入先前作为与 SSO 管理员角色关联的组创建的 SSO Administrators 域组。</span><span class="sxs-lookup"><span data-stu-id="98473-128">Enter the domain SSO Administrators group that you created earlier as the group associated with the SSO Administrator(s) role.</span></span>  
  
   6.  <span data-ttu-id="98473-129">输入先前作为与 SSO 关联管理员角色关联的组创建的 SSO Affiliate Administrators 域组。</span><span class="sxs-lookup"><span data-stu-id="98473-129">Enter the domain SSO Affiliate Administrators group that you created earlier as the group associated with the SSO Affiliate Administrator(s) role.</span></span>  
  
8. <span data-ttu-id="98473-130">选择**企业 SSO 密钥备份**选项在左窗格中，并提供用于备份企业 SSO 密钥的适当的参数。</span><span class="sxs-lookup"><span data-stu-id="98473-130">Select the **Enterprise SSO Secret Backup** option from the left pane and provide the appropriate parameters for backing up the Enterprise SSO secret.</span></span> <span data-ttu-id="98473-131">默认情况下，企业 SSO 密钥备份到*\<驱动器\>*: Files\Enterprise Single Sign-on \Program Files\Common\\*SSOxxxx*.bak。</span><span class="sxs-lookup"><span data-stu-id="98473-131">By default, the Enterprise SSO secret is backed up to *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On\\*SSOxxxx*.bak.</span></span>  
  
9. <span data-ttu-id="98473-132">单击**应用配置**并查看摘要。</span><span class="sxs-lookup"><span data-stu-id="98473-132">Click the **Apply Configuration** and review the Summary.</span></span>  
  
10. <span data-ttu-id="98473-133">单击**下一步**以应用配置。</span><span class="sxs-lookup"><span data-stu-id="98473-133">Click **Next** to apply the configuration.</span></span>  
  
11. <span data-ttu-id="98473-134">单击**完成**以关闭配置向导。</span><span class="sxs-lookup"><span data-stu-id="98473-134">Click **Finish** to close the Configuration wizard.</span></span>  
  
12. <span data-ttu-id="98473-135">关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。</span><span class="sxs-lookup"><span data-stu-id="98473-135">Close the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration.</span></span>  
  
13. <span data-ttu-id="98473-136">登录到被动群集节点并启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。</span><span class="sxs-lookup"><span data-stu-id="98473-136">Log on to the passive cluster node and start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
14. <span data-ttu-id="98473-137">选择**自定义配置**选项并输入相同的值**数据库服务器名称**，**用户名**，以及**密码**，你输入时配置的第一个群集节点。</span><span class="sxs-lookup"><span data-stu-id="98473-137">Choose the **Custom Configuration** option and enter the same values for the **Database server name**, **User name**, and **Password** that you entered when configuring the first cluster node.</span></span> <span data-ttu-id="98473-138">输入这些值后，单击**配置**以继续。</span><span class="sxs-lookup"><span data-stu-id="98473-138">After entering these values, click **Configure** to continue.</span></span>  
  
15. <span data-ttu-id="98473-139">选择**企业 SSO**选项在左窗格中，并设置以下选项为企业 SSO 功能：</span><span class="sxs-lookup"><span data-stu-id="98473-139">Select the **Enterprise SSO** option from the left pane and set the following options for the Enterprise SSO feature:</span></span>  
  
    1.  <span data-ttu-id="98473-140">选择**启用企业单一登录此计算机上**选项。</span><span class="sxs-lookup"><span data-stu-id="98473-140">Select the **Enable Enterprise Single Sign-On on this computer** option.</span></span>  
  
    2.  <span data-ttu-id="98473-141">选择**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="98473-141">Select **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="98473-142">为 SSO 数据库中输入相同的值**服务器名称**并**数据库名称**输入时配置的第一个群集节点。</span><span class="sxs-lookup"><span data-stu-id="98473-142">Enter the same values for the SSO Database **Server Name** and **Database Name** that you entered when configuring the first cluster node.</span></span>  
  
    4.  <span data-ttu-id="98473-143">配置第一个群集节点时的域帐户输入相同的值。</span><span class="sxs-lookup"><span data-stu-id="98473-143">Enter the same value for the domain account that you entered when configuring the first cluster node.</span></span>  
  
16. <span data-ttu-id="98473-144">选择**应用配置**以显示摘要。</span><span class="sxs-lookup"><span data-stu-id="98473-144">Select **Apply Configuration** to display the Summary.</span></span>  
  
17. <span data-ttu-id="98473-145">选择**下一步**以应用配置。</span><span class="sxs-lookup"><span data-stu-id="98473-145">Select **Next** to apply the configuration.</span></span>  
  
18. <span data-ttu-id="98473-146">选择**完成**以关闭配置向导。</span><span class="sxs-lookup"><span data-stu-id="98473-146">Select **Finish** to close the Configuration wizard.</span></span>  
  
19. <span data-ttu-id="98473-147">关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。</span><span class="sxs-lookup"><span data-stu-id="98473-147">Close the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
### <a name="to-update-the-master-secret-server-name-in-the-sso-database"></a><span data-ttu-id="98473-148">若要更新 SSO 数据库中的主密钥服务器名称</span><span class="sxs-lookup"><span data-stu-id="98473-148">To update the master secret server name in the SSO database</span></span>  
  
1.  <span data-ttu-id="98473-149">若要停止并重新启动企业 SSO 服务在活动群集节点上键入以下命令从命令提示符：</span><span class="sxs-lookup"><span data-stu-id="98473-149">Type the following commands from a command prompt on the active cluster node to stop and restart the Enterprise SSO service:</span></span>  
  
    ```  
    net stop entsso  
    ```  
  
     <span data-ttu-id="98473-150">和</span><span class="sxs-lookup"><span data-stu-id="98473-150">and</span></span>  
  
    ```  
    net start entsso  
    ```  
  
2.  <span data-ttu-id="98473-151">将 SSO 数据库中的主密钥服务器名称更改为群集名称，通过执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="98473-151">Change the master secret server name in the SSO database to the cluster name by following these steps:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98473-152">群集名称是定义已在群集中创建的网络名称资源的名称组 / 群集服务或应用程序将包含群集的企业 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="98473-152">The cluster name is the name defined for the network name resource that you have created in the cluster group / clustered service or application that will contain the clustered Enterprise SSO service.</span></span> <span data-ttu-id="98473-153">例如，名称可能*BIZTALKCLUSTER*。</span><span class="sxs-lookup"><span data-stu-id="98473-153">For example, the name may be *BIZTALKCLUSTER*.</span></span>  
  
    1.  <span data-ttu-id="98473-154">在文本编辑器中粘贴以下代码：</span><span class="sxs-lookup"><span data-stu-id="98473-154">Paste the following code in a text editor:</span></span>  
  
        ```  
        <sso>  
          <globalInfo>  
            <secretServer>BIZTALKCLUSTER</secretServer>  
          </globalInfo>  
        </sso>  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="98473-155">*BIZTALKCLUSTER*是占位符，在群集中创建的实际网络名称资源组 / 群集服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="98473-155">*BIZTALKCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group / clustered service or application.</span></span>  
  
    2.  <span data-ttu-id="98473-156">将文件保存为.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="98473-156">Save the file as an .xml file.</span></span> <span data-ttu-id="98473-157">例如，保存该文件另存为 SSOCLUSTER.xml。</span><span class="sxs-lookup"><span data-stu-id="98473-157">For example, save the file as SSOCLUSTER.xml.</span></span>  
  
    3.  <span data-ttu-id="98473-158">在命令提示符下，将更改为企业 SSO 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="98473-158">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="98473-159">默认情况下，安装文件夹是*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="98473-159">By default, the installation folder is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="98473-160">若要更新数据库中的主密钥服务器名称的命令提示符处键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="98473-160">Type the following command at the command prompt to update the master secret server name in the database:</span></span>  
  
        ```  
        ssomanage -updatedb XMLFile  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="98473-161">*XMLFile*是之前保存的.xml 文件的名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="98473-161">*XMLFile* is a placeholder for the name of the .xml file that you saved earlier.</span></span>  
  
### <a name="to-create-the-clustered-enterprise-sso-resource"></a><span data-ttu-id="98473-162">若要创建群集的企业 SSO 资源</span><span class="sxs-lookup"><span data-stu-id="98473-162">To create the clustered Enterprise SSO resource</span></span>  
  
1.  <span data-ttu-id="98473-163">如果未使用群集分布式事务处理协调器 (MSDTC) 资源配置群集然后按照"提高容错容差在 BizTalk Server 通过使用 Windows Server 群集中"白皮书，网址中的步骤[ http://go.microsoft.com/fwlink/?LinkId=69207 ](http://go.microsoft.com/fwlink/?LinkId=69207)若要创建群集的 MSDTC 资源。</span><span class="sxs-lookup"><span data-stu-id="98473-163">If the cluster is not configured with a clustered Distributed Transaction Coordinator (MSDTC) resource then follow the steps in the "Improving Fault Tolerance in BizTalk Server by Using a Windows Server Cluster" white paper at [http://go.microsoft.com/fwlink/?LinkId=69207](http://go.microsoft.com/fwlink/?LinkId=69207) to create a clustered MSDTC resource.</span></span>  
  
2.  <span data-ttu-id="98473-164">单击**启动**，**程序**，**管理工具**，然后**故障转移群集管理**启动故障转移群集管理程序。</span><span class="sxs-lookup"><span data-stu-id="98473-164">Click **Start**, **Programs**, **Administrative Tools**, and then **Failover Cluster Management** to start the Failover Cluster Management program.</span></span>  
  
3.  <span data-ttu-id="98473-165">在左侧窗格中，右键单击**故障转移群集管理**然后单击**管理群集**。</span><span class="sxs-lookup"><span data-stu-id="98473-165">In the left hand pane, right-click **Failover Cluster Management** and click **Manage a Cluster**.</span></span>  
  
4.  <span data-ttu-id="98473-166">上**选择要管理的群集**对话框框中，输入群集进行管理，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="98473-166">On the **Select a cluster to manage** dialog box, enter the cluster to be managed and click **OK**.</span></span>  
  
5.  <span data-ttu-id="98473-167">在左侧窗格中，单击以选择群集的服务或应用程序中包含的 IP 地址和网络名称资源。</span><span class="sxs-lookup"><span data-stu-id="98473-167">In the left hand pane click to select a clustered service or application that contains an IP Address and Network Name resource.</span></span> <span data-ttu-id="98473-168">按照中的步骤[如何创建具有磁盘、 IP 地址和名称资源的群集组](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)若要创建具有 IP 地址和网络名称资源的组，如果尚不存在。</span><span class="sxs-lookup"><span data-stu-id="98473-168">Follow the steps in [How to Create a Cluster Group with a Disk, IP Address, and Name Resource](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md) to create a group with an IP Address and Network Name resource if one does not already exist.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98473-169">群集的企业 SSO 服务不会明确要求使用同一组中的群集物理磁盘资源。</span><span class="sxs-lookup"><span data-stu-id="98473-169">A clustered Enterprise SSO service does not explicitly require the use of a clustered Physical Disk resource in the same group.</span></span>  
  
6.  <span data-ttu-id="98473-170">右键单击群集的服务或应用程序，指向**将资源添加**，然后单击**通用服务**以显示**新建资源向导**对话框。</span><span class="sxs-lookup"><span data-stu-id="98473-170">Right-click the clustered service or application, point to **Add a resource**, and click **Generic Service** to display the **New Resource Wizard** dialog.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="98473-171">在中**一般服务参数**对话框中，如果未单击以选中**将网络名用作计算机名**复选框，SSO 客户端计算机将生成类似于以下的错误时它们尝试联系企业 SSO 服务的此群集的实例：</span><span class="sxs-lookup"><span data-stu-id="98473-171">In the **Generic Service Parameters** dialog box, if you do not click to select the **Use Network Name for computer name** check box, SSO client computers will generate an error similar to the following when they try to contact this clustered instance of the Enterprise SSO service:</span></span>  
    >   
    >  <span data-ttu-id="98473-172">检索主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="98473-172">Failed to retrieve master secrets.</span></span>  
    >   
    >  <span data-ttu-id="98473-173">验证主密钥服务器名称正确以及可用。</span><span class="sxs-lookup"><span data-stu-id="98473-173">Verify that the master secret server name is correct and that it is available.</span></span> <span data-ttu-id="98473-174">密钥服务器名称：ENTSSO 错误代码：0x800706D9，提供的终结点映射程序有没有更多的终结点。</span><span class="sxs-lookup"><span data-stu-id="98473-174">Secret Server Name: ENTSSO Error Code: 0x800706D9, there are no more endpoints available from the endpoint mapper.</span></span>  
  
7.  <span data-ttu-id="98473-175">上**选择服务**页**新建资源向导**，单击以选择**企业单一登录服务**然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="98473-175">On the **Select Service** page of the **New Resource Wizard**, click to select **Enterprise Single Sign-On Service** and click **Next**.</span></span>  
  
8.  <span data-ttu-id="98473-176">上**确认**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="98473-176">On the **Confirmation** page click **Next**.</span></span>  
  
9. <span data-ttu-id="98473-177">上**摘要**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="98473-177">On the **Summary** page click **Finish**.</span></span> <span data-ttu-id="98473-178">企业单一登录服务的群集的实例将显示在下面**信息的其他资源**中的中心窗格**故障转移群集管理**接口。</span><span class="sxs-lookup"><span data-stu-id="98473-178">A clustered instance of the Enterprise Single Sign-On Service will appear under **Other Resources** in the center pane of the **Failover Cluster Management** interface.</span></span>  
  
10. <span data-ttu-id="98473-179">右键单击企业单一登录服务的群集的实例，然后选择**属性**以显示**企业单一登录服务属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="98473-179">Right-click the clustered instance of the Enterprise Single Sign-On Service and select **Properties** to display the **Enterprise Single Sign-On Service Properties** dialog box.</span></span>  
  
11. <span data-ttu-id="98473-180">单击**依赖项**选项卡的属性对话框中，单击**插入**。</span><span class="sxs-lookup"><span data-stu-id="98473-180">Click the **Dependencies** tab of the properties dialog box and click **Insert**.</span></span>  
  
12. <span data-ttu-id="98473-181">单击下的下拉**资源**，选择**名称：** 资源，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="98473-181">Click the drop down box under **Resource**, select the **Name:** resource and click **OK**.</span></span>  
  
### <a name="to-restore-the-master-secret-on-the-second-cluster-node"></a><span data-ttu-id="98473-182">若要还原第二个群集节点上的主密钥</span><span class="sxs-lookup"><span data-stu-id="98473-182">To restore the master secret on the second cluster node</span></span>  
  
1.  <span data-ttu-id="98473-183">在故障转移群集管理中，右键单击群集的服务或包含群集的企业单一登录服务的应用程序，然后单击**使此服务或应用程序联机**以启动所有中的资源群集的服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="98473-183">In Failover Cluster Management, right click the clustered service or application that contains the clustered Enterprise Single Sign-On service and then click **Bring this service or application online** to start all of the resources in the clustered service or application.</span></span>  
  
2.  <span data-ttu-id="98473-184">右键单击群集的服务或应用程序，指向**将此服务或应用程序到另一个节点移动**，然后单击第二个节点。</span><span class="sxs-lookup"><span data-stu-id="98473-184">Right-click the clustered service or application, point to **Move this service or application to another node**, and click the second node.</span></span> <span data-ttu-id="98473-185">此步骤将群集的服务或包含群集的企业单一登录服务从第一个节点到第二个节点的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98473-185">This step moves the clustered service or application that contains the clustered Enterprise Single Sign-On service from the first node to the second node.</span></span>  
  
3.  <span data-ttu-id="98473-186">右键单击群集的企业单一登录服务，然后单击**使此服务或应用程序脱机**，然后右键单击企业 SSO 服务的群集的实例，并单击**使此服务或应用程序联机**。</span><span class="sxs-lookup"><span data-stu-id="98473-186">Right-click the clustered Enterprise Single Sign-On service and click **Take this service or application offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring this service or application online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98473-187">如果未完成此步骤可能会不成功尝试还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="98473-187">If this step is not completed the attempt to restore the master secret may not succeed.</span></span>  
  
4.  <span data-ttu-id="98473-188">将第一个节点的主密钥备份文件复制到的 \Enterprise Single Sign-on 安装文件夹的第二个节点上。</span><span class="sxs-lookup"><span data-stu-id="98473-188">Copy the master secret backup file from the first node to the \Enterprise Single Sign-On installation folder on the second node.</span></span> <span data-ttu-id="98473-189">默认情况下，安装文件夹是*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="98473-189">By default, the installation folder is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5.  <span data-ttu-id="98473-190">登录到第二个节点，并在命令提示符下，更改为企业 SSO 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="98473-190">Log on to the second node and at a command prompt, change to the Enterprise SSO installation folder.</span></span>  
  
6.  <span data-ttu-id="98473-191">键入以下命令从命令提示符将主密钥还原到第二个节点：</span><span class="sxs-lookup"><span data-stu-id="98473-191">Type the following command from the command prompt to restore the master secret to the second node:</span></span>  
  
    ```  
    ssoconfig -restoresecret RestoreFile  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="98473-192">替换*RestoreFile*使用的路径和包含主密钥的备份文件的名称。</span><span class="sxs-lookup"><span data-stu-id="98473-192">Replace *RestoreFile* with the path of and the name of the backup file that contains the master secret.</span></span>  
  
     <span data-ttu-id="98473-193">主密钥存储在注册表中的以下位置：</span><span class="sxs-lookup"><span data-stu-id="98473-193">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="98473-194">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span><span class="sxs-lookup"><span data-stu-id="98473-194">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span></span>  
  
7.  <span data-ttu-id="98473-195">移动群集的服务或包含群集的企业单一登录服务从此群集节点到其他群集节点，以确保故障转移功能的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98473-195">Move the clustered service or application that contains the clustered Enterprise Single Sign-On service from this cluster node to other cluster node to ensure failover functionality.</span></span> <span data-ttu-id="98473-196">然后将群集组移回验证故障回复功能。</span><span class="sxs-lookup"><span data-stu-id="98473-196">Then move the cluster group back to verify fail-back functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98473-197">请参阅</span><span class="sxs-lookup"><span data-stu-id="98473-197">See Also</span></span>  
 [<span data-ttu-id="98473-198">如何创建具有磁盘、 IP 地址和名称资源的群集组</span><span class="sxs-lookup"><span data-stu-id="98473-198">How to Create a Cluster Group with a Disk, IP Address, and Name Resource</span></span>](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)
