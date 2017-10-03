---
title: "主密钥服务器的高可用性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b99cb04-61a5-41cc-a409-35897c17b789
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4c8c18f394b800ffeee9994294b2d2dbf0cb3a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="high-availability-for-the-master-secret-server"></a><span data-ttu-id="7402e-102">主密钥服务器的高可用性</span><span class="sxs-lookup"><span data-stu-id="7402e-102">High Availability for the Master Secret Server</span></span>
<span data-ttu-id="7402e-103">即使你不使用的企业单一登录 (SSO) 功能用于将凭据和单一登录映射，SSO 是整体 Microsoft 的关键部分[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]基础结构，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 SSO 来帮助为端口的安全信息配置。</span><span class="sxs-lookup"><span data-stu-id="7402e-103">Even if you do not use the Enterprise Single Sign-On (SSO) functionality for mapping credentials and single sign-on, SSO is a critical part of the overall Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] infrastructure, because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses SSO to help secure information for port configuration.</span></span> <span data-ttu-id="7402e-104">端口配置数据加密，并存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="7402e-104">The port configuration data is encrypted and stored in the SSO database.</span></span> <span data-ttu-id="7402e-105">每个 BizTalk server 提供用于加密和解密的端口配置数据使用了 SSO 服务服务 (ENTSSO.exe)。</span><span class="sxs-lookup"><span data-stu-id="7402e-105">Each BizTalk server has an SSO service (ENTSSO.exe) that is used for encrypting and decrypting the port configuration data.</span></span>  
  
 <span data-ttu-id="7402e-106">当 SSO 服务启动时，它从主密钥服务器检索加密密钥。</span><span class="sxs-lookup"><span data-stu-id="7402e-106">When an SSO service starts up, it retrieves the encryption key from the master secret server.</span></span> <span data-ttu-id="7402e-107">此加密密钥称为主密钥。</span><span class="sxs-lookup"><span data-stu-id="7402e-107">This encryption key is called the master secret.</span></span> <span data-ttu-id="7402e-108">主密钥服务器是另一个具有附加的子服务维护并分发主密钥的 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="7402e-108">The master secret server is another SSO service that has an additional subservice that maintains and distributes the master secret.</span></span> <span data-ttu-id="7402e-109">检索主密钥后，SSO 服务将其缓存。</span><span class="sxs-lookup"><span data-stu-id="7402e-109">After a master secret is retrieved, the SSO service caches it.</span></span> <span data-ttu-id="7402e-110">每隔 60 秒，SSO 服务主密钥将与同步主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="7402e-110">Every 60 seconds, the SSO service synchronizes the master secret with the master secret server.</span></span>  
  
 <span data-ttu-id="7402e-111">如果主密钥服务器失败，并且 SSO 服务将其刷新间隔之一检测故障，SSO 服务和服务器失败，包括凭据，解密之前运行的所有运行时操作将继续成功。</span><span class="sxs-lookup"><span data-stu-id="7402e-111">If the master secret server fails, and the SSO service detects the failure in one of its refresh intervals, the SSO service and all run-time operations that were running before the server failed, including decryption of credentials, continue successfully.</span></span> <span data-ttu-id="7402e-112">但是，您不能加密新凭据或端口配置数据。</span><span class="sxs-lookup"><span data-stu-id="7402e-112">However, you cannot encrypt new credentials or port configuration data.</span></span> <span data-ttu-id="7402e-113">因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境具有依赖关系的主密钥服务器的可用性。</span><span class="sxs-lookup"><span data-stu-id="7402e-113">Therefore, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment has a dependency on the availability of the master secret server.</span></span>  
  
## <a name="making-the-master-secret-server-available"></a><span data-ttu-id="7402e-114">确保主密钥服务器可用</span><span class="sxs-lookup"><span data-stu-id="7402e-114">Making the Master Secret Server Available</span></span>  
 <span data-ttu-id="7402e-115">SSO 系统的可用性，因此的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，很重要只要它在生成备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="7402e-115">For availability of the SSO system, and therefore of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, it is critical that you back up the master secret as soon as it is generated.</span></span> <span data-ttu-id="7402e-116">如果您丢失主密钥，则会丢失 SSO 系统使用该主密钥加密的数据。</span><span class="sxs-lookup"><span data-stu-id="7402e-116">If you lose it, you lose the data that the SSO system encrypted by using that master secret.</span></span> <span data-ttu-id="7402e-117">有关备份主密钥的详细信息，请参阅[如何返回向上主密钥](http://go.microsoft.com/fwlink/?LinkID=151934)(http://go.microsoft.com/fwlink/?LinkID=151934) 中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="7402e-117">For more information about backing up the master secret, see [How to Back Up the Master Secret](http://go.microsoft.com/fwlink/?LinkID=151934) (http://go.microsoft.com/fwlink/?LinkID=151934) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="7402e-118">主密钥服务器有两种可用方式：</span><span class="sxs-lookup"><span data-stu-id="7402e-118">You can make the master secret server available in two ways:</span></span>  
  
-   <span data-ttu-id="7402e-119">**可用，但不是高可用**。</span><span class="sxs-lookup"><span data-stu-id="7402e-119">**Available, but not highly available**.</span></span> <span data-ttu-id="7402e-120">你可以创建主密钥服务器变得不可用，并且你可以手动升级另一台主服务器和还原主密钥此服务器上的 SSO 服务器时通知你的 Microsoft System Center Operations Manager 事件。</span><span class="sxs-lookup"><span data-stu-id="7402e-120">You can create a Microsoft System Center Operations Manager event to notify you when the master secret server becomes unavailable, and you can then manually promote another SSO server to master secret server and restore the master secret on this server.</span></span>  
  
     <span data-ttu-id="7402e-121">尽管此配置不是高可用的它可以是令人满意在大多数情况下，与向外扩展接收和发送，处理主机保持一致。</span><span class="sxs-lookup"><span data-stu-id="7402e-121">Although this configuration is not highly available, it can be satisfactory for most scenarios and it is consistent with scaling out the receiving, sending, and processing hosts.</span></span>  
  
-   <span data-ttu-id="7402e-122">**高度可用**。</span><span class="sxs-lookup"><span data-stu-id="7402e-122">**Highly available**.</span></span> <span data-ttu-id="7402e-123">若要为主密钥服务器提供冗余，请在单独的主密钥服务器群集上使用 Windows 群集，或者在现有数据库群集上配置主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="7402e-123">To provide redundancy for the master secret server, use Windows Clustering on a separate master secret server cluster, or configure the master secret server on an existing database cluster.</span></span> <span data-ttu-id="7402e-124">主密钥服务器提供的服务使用的资源不多，安装在数据库群集上时通常不会影响数据库的功能或性能。</span><span class="sxs-lookup"><span data-stu-id="7402e-124">The services provided by the master secret server do not consume many resources, and typically do not affect database functionality or performance when installed on a database cluster.</span></span> <span data-ttu-id="7402e-125">下图显示了如何确保主密钥服务器高度可用：</span><span class="sxs-lookup"><span data-stu-id="7402e-125">The following figure shows how you can make the master secret server highly available.</span></span>  
  
     <span data-ttu-id="7402e-126">![高度可用主密钥服务器](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")</span><span class="sxs-lookup"><span data-stu-id="7402e-126">![Highly Available Master Secret Server](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")</span></span>  
  
     <span data-ttu-id="7402e-127">尽管此配置具备高可用性，但它仍需要其他硬件资源。</span><span class="sxs-lookup"><span data-stu-id="7402e-127">While this configuration is highly available, it requires additional hardware resources.</span></span> <span data-ttu-id="7402e-128">有关为 SSO 的高可用性安装选项的详细信息，请参阅[高可用性 SSO 安装选项](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838) 中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="7402e-128">For more information about high-availability installation options for SSO, see [High-Availability SSO Installation Options](http://go.microsoft.com/fwlink/?LinkId=156838) (http://go.microsoft.com/fwlink/?LinkId=156838) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
     <span data-ttu-id="7402e-129">本部分包括有关在上配置为高度可用的群集资源的 SSO 主密钥服务器的详细的信息[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集。</span><span class="sxs-lookup"><span data-stu-id="7402e-129">This section includes detailed information about configuring the SSO master secret server as a highly available cluster resource on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7402e-130">若要减少高度可用的解决方案的硬件资源，可以添加的主密钥服务器中的群集资源作为你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集。</span><span class="sxs-lookup"><span data-stu-id="7402e-130">To reduce the hardware resources for a highly available solution, you can add the master secret server as a cluster resource in your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span> <span data-ttu-id="7402e-131">请注意，你不必购买其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]许可证以便安装 SSO 服务在运行 SQL Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="7402e-131">Note that you do not need to purchase additional [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] licenses to install the SSO service on the computer running the SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7402e-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="7402e-132">In This Section</span></span>  
  
-   [<span data-ttu-id="7402e-133">群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="7402e-133">Clustering the Master Secret Server</span></span>](../technical-guides/clustering-the-master-secret-server.md)  
  
-   [<span data-ttu-id="7402e-134">手动指定新主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="7402e-134">Designating a New Master Secret Server Manually</span></span>](../technical-guides/designating-a-new-master-secret-server-manually.md)  
  
## <a name="see-also"></a><span data-ttu-id="7402e-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7402e-135">See Also</span></span>  
 <span data-ttu-id="7402e-136">[规划高 Availability2](../technical-guides/planning-for-high-availability2.md) </span><span class="sxs-lookup"><span data-stu-id="7402e-136">[Planning for High Availability2](../technical-guides/planning-for-high-availability2.md) </span></span>  
 <span data-ttu-id="7402e-137">[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="7402e-137">[High Availability for BizTalk Hosts](../technical-guides/high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="7402e-138">数据库的高可用性</span><span class="sxs-lookup"><span data-stu-id="7402e-138">High Availability for Databases</span></span>](../technical-guides/high-availability-for-databases.md)