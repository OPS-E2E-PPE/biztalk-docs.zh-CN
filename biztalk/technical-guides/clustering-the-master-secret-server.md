---
title: 聚类分析主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c19702cfa7179399ee89f6799b65f1d2cec27a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977294"
---
# <a name="clustering-the-master-secret-server"></a><span data-ttu-id="3a443-102">聚类分析主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="3a443-102">Clustering the Master Secret Server</span></span>
<span data-ttu-id="3a443-103">BizTalk Server 应用程序服务维护硬编码依赖于随一起安装的企业单一登录 (SSO) 服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3a443-103">The BizTalk Server application service maintains a hard-coded dependency upon the Enterprise Single Sign-On (SSO) service that is installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3a443-104">SSO 服务必须能够与启动主密钥服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="3a443-104">The SSO service must be able to communicate with the master secret server to start.</span></span> <span data-ttu-id="3a443-105">我们建议您在主密钥服务器提供容错能力的主密钥服务器上群集 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="3a443-105">We recommend that you cluster the SSO service on the master secret server to provide fault tolerance for the master secret server.</span></span> <span data-ttu-id="3a443-106">有关详细信息，请参阅[高可用性 SSO 安装选项](http://go.microsoft.com/fwlink/?LinkId=156838)(<http://go.microsoft.com/fwlink/?LinkId=156838>) 在 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="3a443-106">For more information, see [High-Availability SSO Installation Options](http://go.microsoft.com/fwlink/?LinkId=156838) (<http://go.microsoft.com/fwlink/?LinkId=156838>) in BizTalk Server Help.</span></span>  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a><span data-ttu-id="3a443-107">准备进行群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="3a443-107">Preparing for Clustering the Master Secret Server</span></span>  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a><span data-ttu-id="3a443-108">决定是否要使用的专用的群集或 SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="3a443-108">Deciding Whether to Use a Dedicated Cluster or the SQL Server Cluster</span></span>  
 <span data-ttu-id="3a443-109">聚类分析硬件成本很高。</span><span class="sxs-lookup"><span data-stu-id="3a443-109">Clustering hardware is expensive.</span></span> <span data-ttu-id="3a443-110">若要减少高度可用的解决方案的硬件资源，可以添加在主密钥服务器为群集资源中你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集。</span><span class="sxs-lookup"><span data-stu-id="3a443-110">To reduce the hardware resources for a highly available solution, you can add the master secret server as a cluster resource in your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster.</span></span> <span data-ttu-id="3a443-111">如果使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集，我们建议您不要将主密钥服务器上作为 MessageBox 数据库的同一个活动节点。</span><span class="sxs-lookup"><span data-stu-id="3a443-111">If you use the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster, we recommend that you do not put the master secret server on the same active node as the MessageBox database.</span></span> <span data-ttu-id="3a443-112">MessageBox 数据库是通常较为繁忙比其他数据库。</span><span class="sxs-lookup"><span data-stu-id="3a443-112">The MessageBox database is usually busier than other databases.</span></span> <span data-ttu-id="3a443-113">即使在主密钥服务器不会消耗许多硬件资源，则最好从活动的 MessageBox 数据库节点将其移动到另一个活动群集节点。</span><span class="sxs-lookup"><span data-stu-id="3a443-113">Even though the master secret server doesn't consume many hardware resources, it is better to move it to a different active cluster node from the active MessageBox database node.</span></span>  
  
### <a name="clustering-the-sso-database"></a><span data-ttu-id="3a443-114">聚类分析的 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="3a443-114">Clustering the SSO Database</span></span>  
 <span data-ttu-id="3a443-115">主密钥服务器取决于 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="3a443-115">The master secret server depends on the SSO database.</span></span> <span data-ttu-id="3a443-116">若要构建一个高可用性 SSO，您必须将群集 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="3a443-116">To build a high-availability SSO, you must cluster the SSO database.</span></span> <span data-ttu-id="3a443-117">有关聚类分析 BizTalk 数据库的详细信息，请参阅[聚类分析 BizTalk Server 数据库 2](../technical-guides/clustering-the-biztalk-server-databases2.md)。</span><span class="sxs-lookup"><span data-stu-id="3a443-117">For more information about clustering BizTalk databases, see [Clustering the BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md).</span></span>  
  
### <a name="creating-domain-groups-and-accounts"></a><span data-ttu-id="3a443-118">创建域组和帐户</span><span class="sxs-lookup"><span data-stu-id="3a443-118">Creating Domain Groups and Accounts</span></span>  
 <span data-ttu-id="3a443-119">需要群集主密钥服务器之前，配置以下域组和帐户：</span><span class="sxs-lookup"><span data-stu-id="3a443-119">You need to configure the following domain groups and accounts before clustering the master secret server:</span></span>  
  
-   <span data-ttu-id="3a443-120">创建具有名称 SSO Administrators 和 SSO Affiliate Administrators 域组。</span><span class="sxs-lookup"><span data-stu-id="3a443-120">Create domain groups with the names SSO Administrators and SSO Affiliate Administrators.</span></span> <span data-ttu-id="3a443-121">若要创建企业 SSO 服务的群集的实例，必须为域组中创建的 SSO Administrators 和 SSO Affiliate Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="3a443-121">To create a clustered instance of the Enterprise SSO service, you must create the SSO Administrators and SSO Affiliate Administrators groups as domain groups.</span></span>  
  
-   <span data-ttu-id="3a443-122">创建或指定域帐户是 SSO Administrators 域组的成员。</span><span class="sxs-lookup"><span data-stu-id="3a443-122">Create or designate a domain account that is a member of the SSO Administrators domain group.</span></span> <span data-ttu-id="3a443-123">每个节点上的企业 SSO 服务将配置为作为此域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3a443-123">The Enterprise SSO service on each node will be configured to log on as this domain account.</span></span> <span data-ttu-id="3a443-124">此帐户必须在群集中每个节点上具有"作为服务登录"权限。</span><span class="sxs-lookup"><span data-stu-id="3a443-124">This account must have the "Log on as a service" right on each node in the cluster.</span></span> <span data-ttu-id="3a443-125">此帐户还必须授予对群集的完全控制访问。</span><span class="sxs-lookup"><span data-stu-id="3a443-125">This account must also be granted Full Control access to the cluster.</span></span>  
  
## <a name="clustering-the-master-secret-server"></a><span data-ttu-id="3a443-126">聚类分析主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="3a443-126">Clustering the Master Secret Server</span></span>  
 <span data-ttu-id="3a443-127">下面是聚类分析主密钥服务器的基本步骤：</span><span class="sxs-lookup"><span data-stu-id="3a443-127">Here are the basic steps for clustering the master secret server:</span></span>  
  
1. <span data-ttu-id="3a443-128">安装和配置企业 SSO 群集节点上。</span><span class="sxs-lookup"><span data-stu-id="3a443-128">Install and configure Enterprise SSO on the cluster nodes.</span></span>  
  
2. <span data-ttu-id="3a443-129">创建群集的企业 SSO 资源和从属资源。</span><span class="sxs-lookup"><span data-stu-id="3a443-129">Create the clustered Enterprise SSO resource and the dependent resources.</span></span>  
  
3. <span data-ttu-id="3a443-130">还原第二个群集节点上的主密钥。</span><span class="sxs-lookup"><span data-stu-id="3a443-130">Restore the master secret on the second cluster node.</span></span> <span data-ttu-id="3a443-131">如果将主密钥服务器移到群集时，必须还原的第一个的群集节点上的主密钥。</span><span class="sxs-lookup"><span data-stu-id="3a443-131">If you move the master secret server to the cluster, you must restore the master secret on the first cluster node as well.</span></span>  
  
4. <span data-ttu-id="3a443-132">将包含 SSO 服务，联机的群集组。</span><span class="sxs-lookup"><span data-stu-id="3a443-132">Bring the cluster group that contains the SSO service, online.</span></span>  
  
5. <span data-ttu-id="3a443-133">更新管理数据库中的主机密名称。</span><span class="sxs-lookup"><span data-stu-id="3a443-133">Update the master secret name in the Management database.</span></span>  
  
   <span data-ttu-id="3a443-134">有关群集主密钥服务器的详细步骤，请参阅[如何群集主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156839)(<http://go.microsoft.com/fwlink/?LinkId=156839>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="3a443-134">For detailed steps on clustering the master secret server, see [How to Cluster the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156839) (<http://go.microsoft.com/fwlink/?LinkId=156839>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a443-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a443-135">See Also</span></span>  
 [<span data-ttu-id="3a443-136">手动指定新主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="3a443-136">Designating a New Master Secret Server Manually</span></span>](../technical-guides/designating-a-new-master-secret-server-manually.md)