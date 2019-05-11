---
title: 如何安装群集 SSO 和 BizTalk 主机在同一群集组 1 中 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 413cc8f4-f343-4c1c-8b79-3b15cb4c101d
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e8fef44d59a12c42da35d85e0c4357ca7fce5b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342355"
---
# <a name="cluster-sso-and-a-biztalk-host-in-the-same-cluster-group"></a><span data-ttu-id="bc53e-102">群集 SSO 和 BizTalk 主机在同一群集组中</span><span class="sxs-lookup"><span data-stu-id="bc53e-102">Cluster SSO and a BizTalk Host in the Same Cluster Group</span></span>
<span data-ttu-id="bc53e-103">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]您可以在同一 Windows Server 群集上群集一个或多个 BizTalk 主机和企业单一登录 (SSO) 服务。</span><span class="sxs-lookup"><span data-stu-id="bc53e-103">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you can cluster one or more BizTalk hosts and the Enterprise Single Sign-On (SSO) service on the same Windows Server cluster.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc53e-104">正确实现此策略需要为群集资源在同一群集组中创建任何 BizTalk 主机实例和 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="bc53e-104">Correct implementation of this strategy requires that you create any BizTalk host instances and the SSO service as cluster resources in the same cluster group.</span></span>  
  
 <span data-ttu-id="bc53e-105">将 Windows 群集与一个或多个 BizTalk 主机和 SSO 通常属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="bc53e-105">The use of Windows Clustering with one or more BizTalk hosts and SSO typically falls into one of these categories:</span></span>  
  
1. <span data-ttu-id="bc53e-106">SSO 主密钥服务器和同一群集组中的一个或多个 BizTalk 主机，聚类分析。</span><span class="sxs-lookup"><span data-stu-id="bc53e-106">Clustering the SSO master secret server and one or more BizTalk hosts in the same cluster group.</span></span>  
  
    <span data-ttu-id="bc53e-107">在此方案中，群集的 BizTalk 主机和群集的 SSO 服务之间的依赖关系被维护，因此，如果群集组故障转移，所有资源都移动组。</span><span class="sxs-lookup"><span data-stu-id="bc53e-107">In this scenario, the dependency between the clustered BizTalk hosts and the clustered SSO service is maintained so that if the cluster group is failed over, all resources move with the group.</span></span>  
  
    <span data-ttu-id="bc53e-108">如果 SSO 服务配置为群集资源上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，你必须在同一群集组中创建群集的 IIS web 服务。</span><span class="sxs-lookup"><span data-stu-id="bc53e-108">If the SSO service is configured as a clustered resource on a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, you must create a clustered IIS web service in the same cluster group.</span></span> <span data-ttu-id="bc53e-109">这必须进行以确保所有独立的主机实例将在运行 SSO 服务的群集节点上运行。</span><span class="sxs-lookup"><span data-stu-id="bc53e-109">This must be done to ensure that all isolated host instances will run on the cluster node that the SSO service is running on.</span></span> <span data-ttu-id="bc53e-110">这可确保在独立主机实例中运行的任何适配器将具有为 SSO 服务的访问，因为独立主机实例在 IIS 中运行。</span><span class="sxs-lookup"><span data-stu-id="bc53e-110">This ensures that any adapters that run in an isolated host instance will have access to the SSO service since isolated host instances run in IIS.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bc53e-111">如果非群集的 BizTalk 主机的实例正在运行群集的 SSO 服务的实例在同一群集节点上，SSO 服务的群集的实例不能被故障转移，除非停止 BizTalk 主机的非群集的实例。</span><span class="sxs-lookup"><span data-stu-id="bc53e-111">If an unclustered instance of a BizTalk host is running on the same cluster node that a clustered instance of the SSO service is running, the clustered instance of the SSO service cannot be failed over unless the unclustered instance of the BizTalk host is stopped.</span></span> <span data-ttu-id="bc53e-112">非群集的 BizTalk 主机的实例维护依赖于群集节点上运行的 SSO 服务的群集实例，并阻止故障转移群集的 SSO 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="bc53e-112">An unclustered instance of the BizTalk host maintains a dependency upon the clustered instance of the SSO service running on the cluster node and prevents the clustered instance of the SSO service from failing over.</span></span> <span data-ttu-id="bc53e-113">出于此原因，建议您不要创建非群集的 BizTalk 主机，若要运行 SSO 服务的群集的实例在同一群集节点上运行的实例。</span><span class="sxs-lookup"><span data-stu-id="bc53e-113">For this reason, it is recommended that you do not create an unclustered instance of a BizTalk host to run on the same cluster node that is running a clustered instance of the SSO service.</span></span>  
  
2. <span data-ttu-id="bc53e-114">群集 SSO 服务 （非主密钥服务器） 和同一群集组中的一个或多个 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="bc53e-114">Clustering the SSO service (non master secret server) and one or more BizTalk hosts in the same cluster group.</span></span> <span data-ttu-id="bc53e-115">此方案要求远程主密钥服务器可用。</span><span class="sxs-lookup"><span data-stu-id="bc53e-115">This scenario requires that a remote master secret server be available.</span></span> <span data-ttu-id="bc53e-116">在此方案中，因此，如果群集组故障转移，所有资源都移动与组维护群集的 BizTalk 主机和群集的 SSO 服务之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="bc53e-116">In this scenario, the dependency between the clustered BizTalk hosts and the clustered SSO service is maintained so if the cluster group is failed over, all resources move with the group.</span></span>  
  
    <span data-ttu-id="bc53e-117">如果 SSO 服务配置为群集资源上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，你必须在同一群集组中创建群集的 IIS web 服务。</span><span class="sxs-lookup"><span data-stu-id="bc53e-117">If the SSO service is configured as a clustered resource on a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, you must create a clustered IIS web service in the same cluster group.</span></span> <span data-ttu-id="bc53e-118">这必须进行以确保所有独立的主机实例将在运行 SSO 服务的群集节点上运行。</span><span class="sxs-lookup"><span data-stu-id="bc53e-118">This must be done to ensure that all isolated host instances will run on the cluster node that the SSO service is running on.</span></span> <span data-ttu-id="bc53e-119">这可确保在独立主机实例中运行的任何适配器将具有为 SSO 服务的访问，因为独立主机实例在 IIS 中运行。</span><span class="sxs-lookup"><span data-stu-id="bc53e-119">This ensures that any adapters that run in an isolated host instance will have access to the SSO service since isolated host instances run in IIS.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bc53e-120">除非停止 BizTalk 主机的非群集的实例，如果非群集的 BizTalk 主机实例运行相同的群集节点上群集的 SSO 服务的实例然后运行 SSO 服务的群集的实例无法故障转移。</span><span class="sxs-lookup"><span data-stu-id="bc53e-120">If an unclustered instance of a BizTalk host is running on the same cluster node that a clustered instance of the SSO service is running then the clustered instance of the SSO service cannot be failed over unless the unclustered instance of the BizTalk host is stopped.</span></span> <span data-ttu-id="bc53e-121">BizTalk 主机的非群集实例维护依赖于群集节点上运行的 SSO 服务的群集实例，并阻止 SSO 服务的群集的实例故障转移。</span><span class="sxs-lookup"><span data-stu-id="bc53e-121">An un-clustered instance of the BizTalk host maintains a dependency upon the clustered instance of the SSO service running on the cluster node and prevents the clustered instance of the SSO service from failing over.</span></span> <span data-ttu-id="bc53e-122">出于此原因，建议您创建的非群集的 BizTalk 主机，若要运行 SSO 服务的群集的实例在同一群集节点上运行的实例。</span><span class="sxs-lookup"><span data-stu-id="bc53e-122">For this reason, it is recommended that you not create a unclustered instance of a BizTalk host to run on the same cluster node that is running a clustered instance of the SSO service.</span></span>  
  
3. <span data-ttu-id="bc53e-123">不群集 SSO 服务的情况下，Windows Server 群集上群集一个或多个 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="bc53e-123">Clustering one or more BizTalk hosts on a Windows Server cluster without clustering the SSO service.</span></span> <span data-ttu-id="bc53e-124">在此方案中，一个或多个 BizTalk 主机配置为群集资源，但 SSO 服务未配置为群集资源。</span><span class="sxs-lookup"><span data-stu-id="bc53e-124">In this scenario, one or more BizTalk hosts are configured as cluster resources but the SSO service is not configured as a clustered resource.</span></span> <span data-ttu-id="bc53e-125">这种设计为群集的 BizTalk 主机提供高可用性，但不用于 SSO 服务提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="bc53e-125">This design provides high availability for the clustered BizTalk hosts but does not provide high availability for the SSO service.</span></span> <span data-ttu-id="bc53e-126">在此方案中，如果一个节点上的 SSO 服务失败然后在该节点依赖于 SSO 的 BizTalk Server 组件也将失败。</span><span class="sxs-lookup"><span data-stu-id="bc53e-126">In this scenario, if the SSO service on a node fails then BizTalk Server components that depend on SSO on that node will also fail.</span></span> <span data-ttu-id="bc53e-127">有关如何将 BizTalk Server 主机配置为群集资源的详细信息请参阅[将 BizTalk 主机配置为群集资源](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)。</span><span class="sxs-lookup"><span data-stu-id="bc53e-127">For more information about how to configure a BizTalk Server host as a cluster resource see [configure a BizTalk Host as a Cluster Resource](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md).</span></span>  
  
   <span data-ttu-id="bc53e-128">下面的过程介绍应遵循相同的 Windows Server 群集上群集 BizTalk 主机和 SSO 服务的步骤。</span><span class="sxs-lookup"><span data-stu-id="bc53e-128">The following procedures describe the steps that you should follow to cluster a BizTalk host and the SSO service on the same Windows Server cluster.</span></span>  
  
## <a name="cluster-a-biztalk-host-and-the-sso-master-secret-server-on-the-same-windows-server-cluster"></a><span data-ttu-id="bc53e-129">在同一 Windows Server 群集上群集 BizTalk 主机和 SSO 主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="bc53e-129">Cluster a BizTalk host and the SSO master secret server on the same Windows Server cluster</span></span>  
  
1. <span data-ttu-id="bc53e-130">如果不使用群集分布式事务处理协调器 (MSDTC) 资源配置群集，对 MSDTC 进行群集上的 Windows Server 故障转移群集中的步骤[核对清单：在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/p/?LinkID=129677)(http://go.microsoft.com/fwlink/p/?LinkID=129677)。</span><span class="sxs-lookup"><span data-stu-id="bc53e-130">If the cluster is not configured with a clustered Distributed Transaction Coordinator (MSDTC) resource, cluster MSDTC on a Windows Server failover cluster by following the steps in [Checklist: Creating an MS DTC Resource in a Windows Server 2008 Failover Cluster](http://go.microsoft.com/fwlink/p/?LinkID=129677) (http://go.microsoft.com/fwlink/p/?LinkID=129677).</span></span>  
  
2. <span data-ttu-id="bc53e-131">安装和配置 Windows Server 群集上的 SSO 服务，按照中的步骤[群集主密钥服务器](how-to-cluster-the-master-secret-server1.md)。</span><span class="sxs-lookup"><span data-stu-id="bc53e-131">Install and configure the SSO service on the Windows Server cluster by following the steps in [Cluster the Master Secret Server](how-to-cluster-the-master-secret-server1.md).</span></span> <span data-ttu-id="bc53e-132">由于在 Windows Server 群集上运行 BizTalk Server，安装所有必需的 BizTalk Server 组件，即使您只配置 SSO 组件这一次也是如此。</span><span class="sxs-lookup"><span data-stu-id="bc53e-132">Since you will be running BizTalk Server on the Windows Server cluster, install all required BizTalk Server components even though you will only be configuring the SSO components at this time.</span></span>  
  
3. <span data-ttu-id="bc53e-133">按照中所述的步骤在 BizTalk Server 计算机上群集 IIS [Microsoft 知识库文章 970759"配置 IIS 7.0 中 Microsoft Windows Server 2008 故障转移群集"](http://go.microsoft.com/fwlink/p/?LinkId=152793) (<http://go.microsoft.com/fwlink/p/?LinkId=152793>)。</span><span class="sxs-lookup"><span data-stu-id="bc53e-133">Cluster IIS on the BizTalk Server computer by following the steps documented in [Microsoft Knowledge Base article 970759 "Configuring IIS 7.0 in a Microsoft Windows Server 2008 failover cluster"](http://go.microsoft.com/fwlink/p/?LinkId=152793) (<http://go.microsoft.com/fwlink/p/?LinkId=152793>).</span></span> <span data-ttu-id="bc53e-134">在与群集 SSO 服务相同的群集组中创建群集的 IIS Web 服务。</span><span class="sxs-lookup"><span data-stu-id="bc53e-134">Create the clustered IIS Web service in the same cluster group as the clustered SSO service.</span></span>  
  
4. <span data-ttu-id="bc53e-135">将包含群集的 SSO 服务到一个群集节点的群集组移并登录到此群集节点上。</span><span class="sxs-lookup"><span data-stu-id="bc53e-135">Move the cluster group that contains the clustered SSO service to one of the cluster nodes, and log on to this cluster node.</span></span>  
  
5. <span data-ttu-id="bc53e-136">启动 BizTalk Server 配置程序，并完成此群集节点上的 BizTalk Server 配置。</span><span class="sxs-lookup"><span data-stu-id="bc53e-136">Start the BizTalk Server Configuration program, and complete the configuration of BizTalk Server on this cluster node.</span></span> <span data-ttu-id="bc53e-137">由于这是组中的第一个 BizTalk Server 计算机，单击**创建新的 BizTalk 组**配置 BizTalk 组时。</span><span class="sxs-lookup"><span data-stu-id="bc53e-137">Since this is the first BizTalk Server computer in the group, click **Create a new BizTalk Group** when configuring the BizTalk Group.</span></span>  
  
6. <span data-ttu-id="bc53e-138">已成功完成 BizTalk Server 配置后，将包含群集的 SSO 服务到另一个群集节点，并登录到此群集节点的群集组。</span><span class="sxs-lookup"><span data-stu-id="bc53e-138">Once the BizTalk Server configuration has completed successfully, move the cluster group that contains the clustered SSO service to the other cluster node, and log on to this cluster node.</span></span>  
  
7. <span data-ttu-id="bc53e-139">启动 BizTalk Server 配置程序，并完成此群集节点上的 BizTalk Server 配置。</span><span class="sxs-lookup"><span data-stu-id="bc53e-139">Start the BizTalk Server Configuration program, and complete the configuration of BizTalk Server on this cluster node.</span></span> <span data-ttu-id="bc53e-140">单击**加入现有 BizTalk 组**此群集节点上，配置 BizTalk 组组件时，指定第一个节点创建的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="bc53e-140">Click **Join an existing BizTalk Group** when configuring the BizTalk Group component on this cluster node, and specify the BizTalk group that you created on the first node.</span></span>  
  
8. <span data-ttu-id="bc53e-141">已成功完成 BizTalk Server 配置后，创建一个或多个群集 BizTalk 主机中的步骤[将 BizTalk 主机配置为群集资源](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)。</span><span class="sxs-lookup"><span data-stu-id="bc53e-141">Once the BizTalk Server configuration has completed successfully, create one or more clustered BizTalk hosts by following the steps in [Configure a BizTalk Host as a Cluster Resource](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bc53e-142">在此方案中，所有 BizTalk 主机都必须都创建为群集 SSO 服务资源所在的群集组中的群集资源。</span><span class="sxs-lookup"><span data-stu-id="bc53e-142">In this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered SSO service resource.</span></span> <span data-ttu-id="bc53e-143">其中群集 SSO 服务的 Windows Server 群集节点上运行的非群集的 BizTalk 主机实例不是受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="bc53e-143">Running a unclustered BizTalk host instance on a Windows Server Cluster node where the SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="bc53e-144">这是因为当群集的 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集的 BizTalk 主机实例将失败。</span><span class="sxs-lookup"><span data-stu-id="bc53e-144">This is because the unclustered BizTalk host instance will fail when the clustered SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
## <a name="cluster-a-biztalk-host-and-sso-non-master-secret-server-on-the-same-windows-server-cluster-when-the-sso-master-secret-server-is-remote"></a><span data-ttu-id="bc53e-145">相同的 Windows Server 群集上群集 BizTalk 主机和 SSO （非主密钥服务器），当 SSO 主密钥服务器是远程数据库</span><span class="sxs-lookup"><span data-stu-id="bc53e-145">Cluster a BizTalk host and SSO (non master secret server) on the same Windows Server cluster when the SSO master secret server is remote</span></span>  
  
1. <span data-ttu-id="bc53e-146">如果不使用群集分布式事务处理协调器 (MSDTC) 资源配置群集，对 MSDTC 进行群集上的 Windows Server 故障转移群集中的步骤[核对清单：在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/p/?LinkID=129677)(http://go.microsoft.com/fwlink/p/?LinkID=129677)。</span><span class="sxs-lookup"><span data-stu-id="bc53e-146">If the cluster is not configured with a clustered Distributed Transaction Coordinator (MSDTC) resource, cluster MSDTC on a Windows Server failover cluster by following the steps in [Checklist: Creating an MS DTC Resource in a Windows Server 2008 Failover Cluster](http://go.microsoft.com/fwlink/p/?LinkID=129677) (http://go.microsoft.com/fwlink/p/?LinkID=129677).</span></span>  
  
2. <span data-ttu-id="bc53e-147">创建域组的名称**SSO Administrators**并**SSO Affiliate Administrators**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-147">Create domain groups with the names **SSO Administrators** and **SSO Affiliate Administrators**.</span></span> <span data-ttu-id="bc53e-148">若要创建群集的 SSO 服务的实例，必须创建**SSO Administrators**并**SSO Affiliate Administrators**为域组的组。</span><span class="sxs-lookup"><span data-stu-id="bc53e-148">To create a clustered instance of the SSO service, you must create the **SSO Administrators** and **SSO Affiliate Administrators** groups as domain groups.</span></span>  
  
3. <span data-ttu-id="bc53e-149">创建或指定的成员的域帐户**SSO Administrators**域组。</span><span class="sxs-lookup"><span data-stu-id="bc53e-149">Create or designate a domain account that is a member of the **SSO Administrators** domain group.</span></span> <span data-ttu-id="bc53e-150">每个节点上的 SSO 服务将配置为作为此域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bc53e-150">The SSO service on each node will be configured to log on as this domain account.</span></span> <span data-ttu-id="bc53e-151">此帐户必须具有**作为服务登录**直接在群集中每个节点上。</span><span class="sxs-lookup"><span data-stu-id="bc53e-151">This account must have the **Log on as a service** right on each node in the cluster.</span></span>  
  
4. <span data-ttu-id="bc53e-152">添加的帐户，您用来登录到域安装和配置流程期间**SSO Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="bc53e-152">Add the account that you are using to log on during the installation and configuration process to the domain **SSO Administrators** group.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="bc53e-153">如果未完成步骤 3 和 4，SSO 服务的配置将失败。</span><span class="sxs-lookup"><span data-stu-id="bc53e-153">Configuration of the SSO service will fail if steps 3 and 4 are not completed.</span></span>  
  
5. <span data-ttu-id="bc53e-154">登录到其中一个群集节点并安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="bc53e-154">Log on to one of the cluster nodes and install BizTalk Server.</span></span> <span data-ttu-id="bc53e-155">选择选项以启动配置程序时安装已成功完成。</span><span class="sxs-lookup"><span data-stu-id="bc53e-155">Select the option to start the configuration program when installation has completed successfully.</span></span>  
  
6. <span data-ttu-id="bc53e-156">选择**自定义配置**选项并输入相应的值**数据库服务器名称**，**用户名**和**密码**字段。</span><span class="sxs-lookup"><span data-stu-id="bc53e-156">Choose the **Custom Configuration** option and enter the appropriate values for the **Database server name**, **User name** and **Password** fields.</span></span> <span data-ttu-id="bc53e-157">输入这些值后，单击**配置**按钮以继续。</span><span class="sxs-lookup"><span data-stu-id="bc53e-157">After entering these values click the **Configure** button to continue.</span></span>  
  
7. <span data-ttu-id="bc53e-158">设置 SSO 功能的以下选项：</span><span class="sxs-lookup"><span data-stu-id="bc53e-158">Set the following options for the SSO feature:</span></span>  
  
   1.  <span data-ttu-id="bc53e-159">选中的复选框旁边**启用企业单一登录此计算机上**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-159">Select the check the box next to **Enable Enterprise Single Sign-On on this computer**.</span></span>  
  
   2.  <span data-ttu-id="bc53e-160">单击选项**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-160">Click the option to **Join an existing SSO system**.</span></span>  
  
   3.  <span data-ttu-id="bc53e-161">输入现有 SSO 数据库服务器名称和数据库名称的值。</span><span class="sxs-lookup"><span data-stu-id="bc53e-161">Enter values for the existing SSO Database Server Name and Database Name.</span></span>  
  
   4.  <span data-ttu-id="bc53e-162">指定要使用企业单一登录服务的帐户时，请输入现有 SSO 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="bc53e-162">Enter the existing SSO service account when specifying the account to use for the Enterprise Single Sign-On service.</span></span>  
  
8. <span data-ttu-id="bc53e-163">由于这是第一个 BizTalk Server 组中选择的选项**创建新的 BizTalk 组**配置 BizTalk 组组件时。</span><span class="sxs-lookup"><span data-stu-id="bc53e-163">Since this is the first BizTalk Server in the group choose the option to **Create a new BizTalk Group** when configuring the BizTalk Group component.</span></span>  
  
9. <span data-ttu-id="bc53e-164">根据需要指定剩余的配置选项并将 BizTalk Server 配置应用到此节点。</span><span class="sxs-lookup"><span data-stu-id="bc53e-164">Specify the remaining configuration options as needed and apply the BizTalk Server configuration to this node.</span></span>  
  
10. <span data-ttu-id="bc53e-165">已成功完成 BizTalk Server 配置后的第一个节点上，登录到第二个节点上并安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="bc53e-165">Once the BizTalk Server configuration has completed successfully on the first node, log on to the second node and install BizTalk Server.</span></span> <span data-ttu-id="bc53e-166">选择选项以启动配置程序时安装已成功完成。</span><span class="sxs-lookup"><span data-stu-id="bc53e-166">Select the option to start the configuration program when installation has completed successfully.</span></span>  
  
11. <span data-ttu-id="bc53e-167">选择**自定义配置**选项，然后再输入相应的值**数据库服务器名称**，**用户名**和**密码**字段。</span><span class="sxs-lookup"><span data-stu-id="bc53e-167">Choose the **Custom Configuration** option, and then enter the appropriate values for the **Database server name**, **User name** and **Password** fields.</span></span> <span data-ttu-id="bc53e-168">输入这些值后，单击**配置**按钮以继续。</span><span class="sxs-lookup"><span data-stu-id="bc53e-168">After entering these values, click the **Configure** button to continue.</span></span>  
  
12. <span data-ttu-id="bc53e-169">设置 SSO 功能的以下选项：</span><span class="sxs-lookup"><span data-stu-id="bc53e-169">Set the following options for the SSO feature:</span></span>  
  
    1.  <span data-ttu-id="bc53e-170">选中的复选框旁边**启用企业单一登录此计算机上**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-170">Select the check the box next to **Enable Enterprise Single Sign-On on this computer**.</span></span>  
  
    2.  <span data-ttu-id="bc53e-171">单击**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-171">Click **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="bc53e-172">输入现有 SSO 数据库服务器名称和数据库名称的值。</span><span class="sxs-lookup"><span data-stu-id="bc53e-172">Enter values for the existing SSO Database Server Name and Database Name.</span></span>  
  
    4.  <span data-ttu-id="bc53e-173">指定要使用企业单一登录服务的帐户时，请输入现有 SSO 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="bc53e-173">Enter the existing SSO service account when specifying the account to use for the Enterprise Single Sign-On service.</span></span>  
  
13. <span data-ttu-id="bc53e-174">选择选项**加入现有 BizTalk 组**此群集节点上，配置 BizTalk 组组件时，指定第一个节点创建的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="bc53e-174">Choose the option to **Join an existing BizTalk Group** when configuring the BizTalk Group component on this cluster node, and specify the BizTalk group that you created on the first node.</span></span>  
  
14. <span data-ttu-id="bc53e-175">根据需要指定剩余的配置选项并将 BizTalk Server 配置应用到此节点。</span><span class="sxs-lookup"><span data-stu-id="bc53e-175">Specify the remaining configuration options as needed and apply the BizTalk Server configuration to this node.</span></span>  
  
15. <span data-ttu-id="bc53e-176">已成功完成 BizTalk Server 配置后，请执行以下步骤群集 SSO 服务：</span><span class="sxs-lookup"><span data-stu-id="bc53e-176">After the BizTalk Server configuration has completed successfully, follow these steps to cluster the SSO service:</span></span>  
  
    1.  <span data-ttu-id="bc53e-177">通过键入以下命令从命令停止每个群集节点上的 SSO 服务：</span><span class="sxs-lookup"><span data-stu-id="bc53e-177">Stop the SSO service on each of the cluster nodes by typing the following command from a command:</span></span>  
  
        ```  
        net stop entsso  
        ```  
  
    2.  <span data-ttu-id="bc53e-178">在故障转移群集管理中，将所有群集组都移到一个节点，并登录到此节点上。</span><span class="sxs-lookup"><span data-stu-id="bc53e-178">In Failover Cluster Management, move all cluster groups to one node and log on to this node.</span></span>  
  
    3.  <span data-ttu-id="bc53e-179">在左侧窗格中，单击以选择群集的服务或应用程序中包含的 IP 地址和网络名称资源。</span><span class="sxs-lookup"><span data-stu-id="bc53e-179">In the left hand pane click to select a clustered service or application that contains an IP Address and Network Name resource.</span></span> <span data-ttu-id="bc53e-180">此群集的服务或应用程序将包含群集的 SSO 服务和群集的 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="bc53e-180">This clustered service or application will contain the clustered SSO service and the clustered BizTalk host.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bc53e-181">群集的 SSO 服务不会明确要求使用同一组中的群集物理磁盘资源。</span><span class="sxs-lookup"><span data-stu-id="bc53e-181">A clustered SSO service does not explicitly require the use of a clustered Physical Disk resource in the same group.</span></span>  
  
    4.  <span data-ttu-id="bc53e-182">右键单击群集的服务或应用程序，指向**将资源添加**，然后单击**通用服务**以显示**新建资源向导**对话框。</span><span class="sxs-lookup"><span data-stu-id="bc53e-182">Right-click the clustered service or application, point to **Add a resource**, and click **Generic Service** to display the **New Resource Wizard** dialog box.</span></span>  
  
    5.  <span data-ttu-id="bc53e-183">上**选择服务**页**新建资源向导**，选择**企业单一登录服务**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-183">On the **Select Service** page of the **New Resource Wizard**, select **Enterprise Single Sign-On Service**, and then click **Next**.</span></span>  
  
    6.  <span data-ttu-id="bc53e-184">上**确认**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-184">On the **Confirmation** page click **Next**.</span></span>  
  
    7.  <span data-ttu-id="bc53e-185">上**摘要**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-185">On the **Summary** page click **Finish**.</span></span> <span data-ttu-id="bc53e-186">企业单一登录服务的群集的实例将显示在下面**信息的其他资源**中的中心窗格**故障转移群集管理**接口。</span><span class="sxs-lookup"><span data-stu-id="bc53e-186">A clustered instance of the Enterprise Single Sign-On Service will appear under **Other Resources** in the center pane of the **Failover Cluster Management** interface.</span></span>  
  
    8.  <span data-ttu-id="bc53e-187">右键单击企业单一登录服务的群集的实例，然后选择**属性**以显示**企业单一登录服务属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="bc53e-187">Right-click the clustered instance of the Enterprise Single Sign-On Service and select **Properties** to display the **Enterprise Single Sign-On Service Properties** dialog box.</span></span>  
  
    9. <span data-ttu-id="bc53e-188">单击**依赖项**选项卡的属性对话框中，单击**插入**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-188">Click the **Dependencies** tab of the properties dialog box and click **Insert**.</span></span>  
  
    10. <span data-ttu-id="bc53e-189">单击下的下拉**资源**，选择**名称：** 资源，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-189">Click the drop down box under **Resource**, select the **Name:** resource and click **OK**.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="bc53e-190">如果不添加到依赖项**名称：** 资源，在尝试联系 SSO 服务的此群集的实例时，SSO 客户端计算机将生成类似于以下的错误：</span><span class="sxs-lookup"><span data-stu-id="bc53e-190">If you do not add the dependency to the **Name:** resource, SSO client computers will generate an error similar to the following when they try to contact this clustered instance of the SSO service:</span></span>  
        >   
        >  <span data-ttu-id="bc53e-191">检索主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="bc53e-191">Failed to retrieve master secrets.</span></span>  
        >   
        >  <span data-ttu-id="bc53e-192">验证主密钥服务器名称正确以及可用。</span><span class="sxs-lookup"><span data-stu-id="bc53e-192">Verify that the master secret server name is correct and that it is available.</span></span> <span data-ttu-id="bc53e-193">密钥服务器名称：ENTSSO 错误代码：0x800706D9，提供的终结点映射程序有没有更多的终结点。</span><span class="sxs-lookup"><span data-stu-id="bc53e-193">Secret Server Name: ENTSSO Error Code: 0x800706D9, there are no more endpoints available from the endpoint mapper.</span></span>  
  
16. <span data-ttu-id="bc53e-194">按照中所述的步骤在 BizTalk Server 计算机上群集 IIS [Microsoft 知识库文章 970759"配置 IIS 7.0 中 Microsoft Windows Server 2008 故障转移群集"](http://go.microsoft.com/fwlink/p/?LinkId=152793) (<http://go.microsoft.com/fwlink/p/?LinkId=152793>)。</span><span class="sxs-lookup"><span data-stu-id="bc53e-194">Cluster IIS on the BizTalk Server computer by following the steps documented in [Microsoft Knowledge Base article 970759 "Configuring IIS 7.0 in a Microsoft Windows Server 2008 failover cluster"](http://go.microsoft.com/fwlink/p/?LinkId=152793) (<http://go.microsoft.com/fwlink/p/?LinkId=152793>).</span></span> <span data-ttu-id="bc53e-195">在与群集 SSO 服务相同的群集组中创建群集的 IIS web 服务。</span><span class="sxs-lookup"><span data-stu-id="bc53e-195">Create the clustered IIS web service in the same cluster group as the clustered SSO service.</span></span>  
  
17. <span data-ttu-id="bc53e-196">在故障转移群集管理中，右键单击群集的服务或包含群集的企业单一登录服务的应用程序，然后单击**使此服务或应用程序联机**以启动所有中的资源群集的服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc53e-196">In Failover Cluster Management, right click the clustered service or application that contains the clustered Enterprise Single Sign-On service and then click **Bring this service or application online** to start all of the resources in the clustered service or application.</span></span>  
  
18. <span data-ttu-id="bc53e-197">右键单击群集的服务或应用程序，指向**将此服务或应用程序到另一个节点移动**，然后单击第二个节点。</span><span class="sxs-lookup"><span data-stu-id="bc53e-197">Right-click the clustered service or application, point to **Move this service or application to another node**, and click the second node.</span></span> <span data-ttu-id="bc53e-198">此步骤将群集的服务或包含群集的企业单一登录服务从第一个节点到第二个节点的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc53e-198">This step moves the clustered service or application that contains the clustered Enterprise Single Sign-On service from the first node to the second node.</span></span>  
  
19. <span data-ttu-id="bc53e-199">右键单击群集的企业单一登录服务，然后单击**使此服务或应用程序脱机**，然后右键单击 SSO 服务的群集的实例，并单击**使此服务或应用程序联机**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-199">Right-click the clustered Enterprise Single Sign-On service and click **Take this service or application offline**, then right-click the clustered instance of the SSO service and click **Bring this service or application online**.</span></span>  
  
20. <span data-ttu-id="bc53e-200">将所有用户的 SSO 服务器名称设置为群集 SSO 服务使用 ssomanage 命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="bc53e-200">Set the SSO server name for all users to the clustered SSO service with the ssomanage command line utility.</span></span> <span data-ttu-id="bc53e-201">此命令应在组中每个 BizTalk server 上运行的 SSO 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="bc53e-201">This command should be run from the SSO installation folder on each BizTalk server in the group.</span></span> <span data-ttu-id="bc53e-202">例如，下面的命令行将设置为群集 SSO 服务的所有用户的 SSO 服务器名称：</span><span class="sxs-lookup"><span data-stu-id="bc53e-202">For example, the following command line will set the SSO server name for all users to the clustered SSO service:</span></span>  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="bc53e-203">*SSOCLUSTER*是在包含群集的 SSO 服务的群集组中创建的实际网络名称资源的占位符。</span><span class="sxs-lookup"><span data-stu-id="bc53e-203">*SSOCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group that contains the clustered SSO service.</span></span>  
  
21. <span data-ttu-id="bc53e-204">更新可在中访问的 SSO 服务器名称**BizTalk 组属性**页后，可以引用群集的 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="bc53e-204">Update the SSO Server name accessible in the **BizTalk Group Properties** page to reference the clustered SSO service.</span></span> <span data-ttu-id="bc53e-205">打开**BizTalk Server 管理**，右键单击 BizTalk 组，选择**属性**菜单项，更新 SSO 服务器名称的条目，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bc53e-205">Open **BizTalk Server Administration**, right-click the BizTalk Group, select the **Properties** menu item, update the entry for SSO Server name, and then click **OK**.</span></span>  
  
22. <span data-ttu-id="bc53e-206">按照中的步骤[将 BizTalk 主机配置为群集资源](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)在创建群集的 SSO 服务的同一群集组中创建一个或多个群集的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="bc53e-206">Follow the steps in [Configure a BizTalk Host as a Cluster Resource](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md) to create one or more clustered BizTalk host instances in the same cluster group that you have created the clustered SSO service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc53e-207">在此方案中，所有 BizTalk 主机都必须都创建为群集 SSO 服务资源所在的群集组中的群集资源。</span><span class="sxs-lookup"><span data-stu-id="bc53e-207">In this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered SSO service resource.</span></span> <span data-ttu-id="bc53e-208">其中群集 SSO 服务的 Windows Server 群集节点上运行非群集的 BizTalk 主机实例不是受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="bc53e-208">Running an unclustered BizTalk host instance on a Windows Server Cluster node where the SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="bc53e-209">这是因为当群集的 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集的 BizTalk 主机实例将失败。</span><span class="sxs-lookup"><span data-stu-id="bc53e-209">This is because the unclustered BizTalk host instance will fail when the clustered SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>
