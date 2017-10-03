---
title: "群集主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674cbf64e11817c951d3841ebdc9f6ee979c0e8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-the-master-secret-server"></a><span data-ttu-id="01340-102">群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="01340-102">Clustering the Master Secret Server</span></span>
<span data-ttu-id="01340-103">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]应用程序服务维护硬编码依赖于随企业单一登录 (SSO) 服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="01340-103">The [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] application service maintains a hard-coded dependency upon the Enterprise Single Sign-On (SSO) service that is installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="01340-104">SSO 服务必须能够与启动的主密钥服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="01340-104">The SSO service must be able to communicate with the master secret server to start.</span></span> <span data-ttu-id="01340-105">我们建议你在主密钥服务器以提供容错功能的主密钥服务器上群集 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="01340-105">We recommend that you cluster the SSO service on the master secret server to provide fault tolerance for the master secret server.</span></span> <span data-ttu-id="01340-106">有关详细信息，请参阅[高可用性 SSO 安装选项](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838) 中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="01340-106">For more information, see [High-Availability SSO Installation Options](http://go.microsoft.com/fwlink/?LinkId=156838) (http://go.microsoft.com/fwlink/?LinkId=156838) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a><span data-ttu-id="01340-107">准备群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="01340-107">Preparing for Clustering the Master Secret Server</span></span>  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a><span data-ttu-id="01340-108">决定是否使用专用的群集或 SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="01340-108">Deciding Whether to Use a Dedicated Cluster or the SQL Server Cluster</span></span>  
 <span data-ttu-id="01340-109">群集硬件也是如此。</span><span class="sxs-lookup"><span data-stu-id="01340-109">Clustering hardware is expensive.</span></span> <span data-ttu-id="01340-110">若要减少高度可用的解决方案的硬件资源，可以添加的主密钥服务器中的群集资源作为你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集。</span><span class="sxs-lookup"><span data-stu-id="01340-110">To reduce the hardware resources for a highly available solution, you can add the master secret server as a cluster resource in your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster.</span></span> <span data-ttu-id="01340-111">如果你使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集中，我们建议不要为 MessageBox 数据库相同的活动节点上放置的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="01340-111">If you use the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster, we recommend that you do not put the master secret server on the same active node as the MessageBox database.</span></span> <span data-ttu-id="01340-112">MessageBox 数据库是通常更加繁忙比其他数据库。</span><span class="sxs-lookup"><span data-stu-id="01340-112">The MessageBox database is usually busier than other databases.</span></span> <span data-ttu-id="01340-113">即使是主密钥服务器不使用许多硬件资源，则最好从活动的 MessageBox 数据库节点将它移动到不同的活动群集节点。</span><span class="sxs-lookup"><span data-stu-id="01340-113">Even though the master secret server doesn't consume many hardware resources, it is better to move it to a different active cluster node from the active MessageBox database node.</span></span>  
  
### <a name="clustering-the-sso-database"></a><span data-ttu-id="01340-114">群集的 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="01340-114">Clustering the SSO Database</span></span>  
 <span data-ttu-id="01340-115">主密钥服务器依赖于 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="01340-115">The master secret server depends on the SSO database.</span></span> <span data-ttu-id="01340-116">若要生成高可用性 SSO，必须群集 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="01340-116">To build a high-availability SSO, you must cluster the SSO database.</span></span> <span data-ttu-id="01340-117">有关群集 BizTalk 数据库的详细信息，请参阅[群集 BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md)。</span><span class="sxs-lookup"><span data-stu-id="01340-117">For more information about clustering BizTalk databases, see [Clustering the BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md).</span></span>  
  
### <a name="creating-domain-groups-and-accounts"></a><span data-ttu-id="01340-118">创建域组和帐户</span><span class="sxs-lookup"><span data-stu-id="01340-118">Creating Domain Groups and Accounts</span></span>  
 <span data-ttu-id="01340-119">你需要在群集的主密钥服务器之前配置的以下域组和帐户：</span><span class="sxs-lookup"><span data-stu-id="01340-119">You need to configure the following domain groups and accounts before clustering the master secret server:</span></span>  
  
-   <span data-ttu-id="01340-120">使用 SSO Administrators 和 SSO Affiliate Administrators 的名称创建域组。</span><span class="sxs-lookup"><span data-stu-id="01340-120">Create domain groups with the names SSO Administrators and SSO Affiliate Administrators.</span></span> <span data-ttu-id="01340-121">若要创建企业 SSO 服务的群集的实例，必须为域组中创建的 SSO Administrators 和 SSO Affiliate Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="01340-121">To create a clustered instance of the Enterprise SSO service, you must create the SSO Administrators and SSO Affiliate Administrators groups as domain groups.</span></span>  
  
-   <span data-ttu-id="01340-122">创建或指定为 SSO Administrators 域组的成员的域帐户。</span><span class="sxs-lookup"><span data-stu-id="01340-122">Create or designate a domain account that is a member of the SSO Administrators domain group.</span></span> <span data-ttu-id="01340-123">每个节点上的企业 SSO 服务将配置为作为此域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="01340-123">The Enterprise SSO service on each node will be configured to log on as this domain account.</span></span> <span data-ttu-id="01340-124">此帐户必须具有群集中每个节点上的"作为服务登录"权限。</span><span class="sxs-lookup"><span data-stu-id="01340-124">This account must have the "Log on as a service" right on each node in the cluster.</span></span> <span data-ttu-id="01340-125">此帐户还必须授予访问群集的完全控制权限。</span><span class="sxs-lookup"><span data-stu-id="01340-125">This account must also be granted Full Control access to the cluster.</span></span>  
  
## <a name="clustering-the-master-secret-server"></a><span data-ttu-id="01340-126">群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="01340-126">Clustering the Master Secret Server</span></span>  
 <span data-ttu-id="01340-127">下面是群集的主密钥服务器的基本步骤：</span><span class="sxs-lookup"><span data-stu-id="01340-127">Here are the basic steps for clustering the master secret server:</span></span>  
  
1.  <span data-ttu-id="01340-128">安装和配置企业 SSO 在群集节点上。</span><span class="sxs-lookup"><span data-stu-id="01340-128">Install and configure Enterprise SSO on the cluster nodes.</span></span>  
  
2.  <span data-ttu-id="01340-129">创建群集的企业 SSO 资源和从属资源。</span><span class="sxs-lookup"><span data-stu-id="01340-129">Create the clustered Enterprise SSO resource and the dependent resources.</span></span>  
  
3.  <span data-ttu-id="01340-130">还原主密钥第二个群集节点上。</span><span class="sxs-lookup"><span data-stu-id="01340-130">Restore the master secret on the second cluster node.</span></span> <span data-ttu-id="01340-131">如果将主密钥服务器移到群集时，必须还原主密钥第一个的群集节点上。</span><span class="sxs-lookup"><span data-stu-id="01340-131">If you move the master secret server to the cluster, you must restore the master secret on the first cluster node as well.</span></span>  
  
4.  <span data-ttu-id="01340-132">将包含 SSO 服务，联机的群集组。</span><span class="sxs-lookup"><span data-stu-id="01340-132">Bring the cluster group that contains the SSO service, online.</span></span>  
  
5.  <span data-ttu-id="01340-133">更新管理数据库中的主密钥名称。</span><span class="sxs-lookup"><span data-stu-id="01340-133">Update the master secret name in the Management database.</span></span>  
  
 <span data-ttu-id="01340-134">有关群集的主密钥服务器的详细步骤，请参阅[如何安装群集主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156839)(http://go.microsoft.com/fwlink/?LinkId=156839) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="01340-134">For detailed steps on clustering the master secret server, see [How to Cluster the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156839) (http://go.microsoft.com/fwlink/?LinkId=156839) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01340-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01340-135">See Also</span></span>  
 [<span data-ttu-id="01340-136">手动指定新主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="01340-136">Designating a New Master Secret Server Manually</span></span>](../technical-guides/designating-a-new-master-secret-server-manually.md)