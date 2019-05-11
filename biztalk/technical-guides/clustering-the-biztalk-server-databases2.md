---
title: 群集数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b68bc3f-c0c4-4050-8ca3-df6dd1927637
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676f3078974384579c113bdcd51d5d118d43b4f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277323"
---
# <a name="clustering-the-biztalk-server-databases"></a><span data-ttu-id="a1f20-102">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a1f20-102">Clustering the BizTalk Server Databases</span></span>
<span data-ttu-id="a1f20-103">如果 BizTalk Server 数据库变得不可用，BizTalk Server 环境将不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="a1f20-103">If the BizTalk Server databases become unavailable, the BizTalk Server environment will not function correctly.</span></span> <span data-ttu-id="a1f20-104">若要提供高可用性，可以创建 BizTalk Server 数据库的 Microsoft SQL Server 群集，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="a1f20-104">To provide high availability, you can create a Microsoft SQL Server cluster for the BizTalk Server databases, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="a1f20-105">![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="a1f20-105">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="a1f20-106">若要创建 BizTalk Server 数据库的高度可用的解决方案，必须具有至少两个群集中运行 SQL Server 和一个共享的磁盘阵列的计算机。</span><span class="sxs-lookup"><span data-stu-id="a1f20-106">To create a highly available solution for the BizTalk Server databases, you must have at least two computers that are running SQL Server and a shared disk array in the cluster.</span></span>  
  
## <a name="clustering-options"></a><span data-ttu-id="a1f20-107">聚类分析选项</span><span class="sxs-lookup"><span data-stu-id="a1f20-107">Clustering Options</span></span>  
 <span data-ttu-id="a1f20-108">确定 BizTalk Server 数据库来满足业务需求的最佳群集配置。</span><span class="sxs-lookup"><span data-stu-id="a1f20-108">Determine the best cluster configuration for the BizTalk Server databases for your business needs.</span></span> <span data-ttu-id="a1f20-109">下面是选项的列表：</span><span class="sxs-lookup"><span data-stu-id="a1f20-109">Here is a list of the options:</span></span>  
  
-   <span data-ttu-id="a1f20-110">**主动/被动**。</span><span class="sxs-lookup"><span data-stu-id="a1f20-110">**Active/passive**.</span></span> <span data-ttu-id="a1f20-111">BizTalk Server 数据库的高可用性通常由在主动/被动服务器群集配置中配置的两个或多个数据库计算机组成。</span><span class="sxs-lookup"><span data-stu-id="a1f20-111">High availability for the BizTalk Server databases typically consists of two or more database computers configured in an active/passive server cluster configuration.</span></span> <span data-ttu-id="a1f20-112">这些计算机共享公共的磁盘资源 (例如 RAID 1 + 0 SCSI 磁盘阵列或存储区域网络) 并使用 Windows 群集提供备份冗余和容错功能。</span><span class="sxs-lookup"><span data-stu-id="a1f20-112">These computers share a common disk resource (such as a RAID 1+0 SCSI disk array or storage area network) and use Windows Clustering to provide backup redundancy and fault tolerance.</span></span>  
  
-   <span data-ttu-id="a1f20-113">**主动/主动**。</span><span class="sxs-lookup"><span data-stu-id="a1f20-113">**Active/active**.</span></span> <span data-ttu-id="a1f20-114">Windows 群集和 SQL Server 允许您在主动/主动模式下运行 SQL Server 的群集的每个节点都是"活动"并运行一个或多个 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="a1f20-114">Windows Clustering and SQL Server allow you to run SQL Server in Active/Active mode where each node of the cluster is “active” and running one or more SQL Server instances.</span></span> <span data-ttu-id="a1f20-115">例如，这将允许您在其他节点上具有一个节点和所有其他 BizTalk Server 数据库上的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="a1f20-115">For example, this would allow you to have the MessageBox database on one node and all other BizTalk Server databases on the other node.</span></span> <span data-ttu-id="a1f20-116">这使您可以最大程度提高群集的硬件的使用情况，但应谨慎使用主动/主动 SQL Server 配置。</span><span class="sxs-lookup"><span data-stu-id="a1f20-116">This allows you to maximize cluster hardware usage, but an active/active SQL Server configuration should be used with care.</span></span>  
  
     <span data-ttu-id="a1f20-117">可以每个节点同时处理的所有 SQL Server 实例的负载在 SQL Server 群集节点故障转移方案期间？</span><span class="sxs-lookup"><span data-stu-id="a1f20-117">Can each node simultaneously handle the load of all SQL Server instances during a SQL Server cluster node failover scenario?</span></span> <span data-ttu-id="a1f20-118">是否有足够的 CPU 资源？</span><span class="sxs-lookup"><span data-stu-id="a1f20-118">Are there enough CPU resources?</span></span> <span data-ttu-id="a1f20-119">是否有足够的内存？</span><span class="sxs-lookup"><span data-stu-id="a1f20-119">Is there sufficient memory?</span></span> <span data-ttu-id="a1f20-120">网络带宽如何呢？</span><span class="sxs-lookup"><span data-stu-id="a1f20-120">What about network bandwidth?</span></span> <span data-ttu-id="a1f20-121">如何为磁盘 I/O 争用？</span><span class="sxs-lookup"><span data-stu-id="a1f20-121">How about disk I/O contention?</span></span>  
  
     <span data-ttu-id="a1f20-122">它们只是为了确定是否适合您的 BizTalk 应用程序的主动/被动 SQL Server 群集必须回答的问题的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1f20-122">These are just some of the questions that need to be answered in order to determine if an active/active SQL Server cluster is right for your BizTalk applications.</span></span> <span data-ttu-id="a1f20-123">如果确定一个节点不能处理故障转移方案中的所有 SQL Server 实例，一种替代方法是使用主动/主动/被动群集。</span><span class="sxs-lookup"><span data-stu-id="a1f20-123">If it is determined that one node cannot handle all SQL Server instances in a failover scenario, an alternative is to use active/active/passive clustering.</span></span>  
  
-   <span data-ttu-id="a1f20-124">**主动/主动/被动**。</span><span class="sxs-lookup"><span data-stu-id="a1f20-124">**Active/active/passive**.</span></span> <span data-ttu-id="a1f20-125">运行时进程写入到 BizTalk 管理数据库、 MessageBox 数据库、 跟踪 Analysis Services 数据库、 BAM 分析数据库、 BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="a1f20-125">The run-time processes write to the BizTalk Management database, MessageBox databases, Tracking Analysis Services database, BAM Analysis database, BAM Star Schema database, BAM Primary Import database, and BAM Archive database.</span></span> <span data-ttu-id="a1f20-126">因此，这些数据库是尤为重要，如果在灾难发生，并且确定哪些数据库移到群集时，必须具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="a1f20-126">Therefore, these databases are especially important if a disaster occurs, and must have greater priority when determining what databases to cluster.</span></span> <span data-ttu-id="a1f20-127">只有用户或工具写入其他数据库。</span><span class="sxs-lookup"><span data-stu-id="a1f20-127">Only users or tools write to the other databases.</span></span> <span data-ttu-id="a1f20-128">对于 MessageBox 数据库中，可以考虑要最大程度减少所需的硬件的主动/主动/被动或主动/主动/主动/被动配置。</span><span class="sxs-lookup"><span data-stu-id="a1f20-128">For the MessageBox databases, you can consider an active/active/passive or active/active/active/passive configuration to minimize the hardware needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1f20-129">SQL Server Standard Edition 支持 2 节点故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="a1f20-129">SQL Server Standard Edition supports 2-node failover clusters.</span></span> <span data-ttu-id="a1f20-130">如果您决定使用 SQL Server 上的主动/主动/被动配置，则必须使用 Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="a1f20-130">If you decide to use the active/active/passive configuration on SQL Server, you must use the Enterprise Edition.</span></span>  
  
## <a name="procedures-for-clustering-the-databases"></a><span data-ttu-id="a1f20-131">聚类分析数据库的过程</span><span class="sxs-lookup"><span data-stu-id="a1f20-131">Procedures for Clustering the Databases</span></span>  
 <span data-ttu-id="a1f20-132">请确保您满足以下先决条件，才能启动群集 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="a1f20-132">Make sure you meet the following prerequisites before you start clustering the BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="a1f20-133">BizTalk Server 环境中创建域组时，必须创建域全局帐户。</span><span class="sxs-lookup"><span data-stu-id="a1f20-133">When you create the domain groups for your BizTalk Server environment, you must create global domain accounts.</span></span>  
  
-   <span data-ttu-id="a1f20-134">安装和配置 BizTalk Server 之前，请配置 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="a1f20-134">Configure the SQL Server cluster before you install and configure BizTalk Server.</span></span> <span data-ttu-id="a1f20-135">请参阅[Windows Server 故障转移群集 (WSFC) 与 SQL Server](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)或[Alwayson 故障转移群集实例 (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="a1f20-135">See [Windows Server Failover Clustering (WSFC) with SQL Server](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server) or [Always On Failover Cluster Instances (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server).</span></span>  
  
-   <span data-ttu-id="a1f20-136">如果您要群集主密钥服务器，请首先配置该服务器。</span><span class="sxs-lookup"><span data-stu-id="a1f20-136">If you are also clustering the master secret server, configure that server first.</span></span> <span data-ttu-id="a1f20-137">请参阅[主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a1f20-137">See [High Availability for the Master Secret Server](../technical-guides/high-availability-for-the-master-secret-server.md).</span></span>  
  
#### <a name="run-biztalk-configuration"></a><span data-ttu-id="a1f20-138">运行 BizTalk 配置</span><span class="sxs-lookup"><span data-stu-id="a1f20-138">Run BizTalk Configuration</span></span>  
  
1. <span data-ttu-id="a1f20-139">在运行时服务器上安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="a1f20-139">Install BizTalk Server on a runtime server.</span></span>  
  
2. <span data-ttu-id="a1f20-140">打开**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="a1f20-140">Open **BizTalk Server Configuration**.</span></span>  
  
3. <span data-ttu-id="a1f20-141">若要应用自定义配置，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="a1f20-141">To apply a custom configuration, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span> <span data-ttu-id="a1f20-142">若要指定 SQL Server 群集在 BizTalk Server 数据库输入中的 SQL Server 群集的名称**数据库**配置的对话框。</span><span class="sxs-lookup"><span data-stu-id="a1f20-142">To specify the SQL Server cluster for the BizTalk Server databases enter the name of the SQL Server cluster in the **Databases** dialog of the configuration.</span></span>  
  
4. <span data-ttu-id="a1f20-143">完成 BizTalk Server 配置使用[自定义配置](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a1f20-143">Complete the BizTalk Server configuration using a [Custom Configuration](../install-and-config-guides/configure-biztalk-server.md).</span></span>
  
   <span data-ttu-id="a1f20-144">有关群集 BizTalk Server 数据库的详细信息，请参阅[通过使用 Windows Server 2008 故障转移群集或 Windows Server 2003 服务器群集的 BizTalk Server 中改进容错能力](https://www.microsoft.com/download/details.aspx?id=2290)。</span><span class="sxs-lookup"><span data-stu-id="a1f20-144">For more information about clustering BizTalk Server databases, see [Improving Fault Tolerance in BizTalk Server by Using a Windows Server 2008 Failover Cluster or Windows Server 2003 Server Cluster](https://www.microsoft.com/download/details.aspx?id=2290).</span></span>  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a><span data-ttu-id="a1f20-145">SQL Server 故障转移期间 BizTalk 主机实例的行为</span><span class="sxs-lookup"><span data-stu-id="a1f20-145">Behavior of BizTalk Host Instances During SQL Server Failover</span></span>  
 <span data-ttu-id="a1f20-146">有关详细信息行为 BizTalk 主机实例的 SQL Server 故障转移期间，请参阅[行为的 BizTalk Server 主机实例 SQL Server 故障转移期间](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)。</span><span class="sxs-lookup"><span data-stu-id="a1f20-146">For more information about behavior of BizTalk host instances during SQL Server failover, see [Behavior of BizTalk Server Host Instances during SQL Server Failover](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md).</span></span>  
  
## <a name="using-sql-server-database-mirroring"></a><span data-ttu-id="a1f20-147">使用 SQL Server 数据库镜像</span><span class="sxs-lookup"><span data-stu-id="a1f20-147">Using SQL Server Database Mirroring</span></span>  
 <span data-ttu-id="a1f20-148">有关使用 SQL Server 数据库镜像相对于 BizTalk Server 数据库的聚类分析的详细信息，请参阅[SQL Server 数据库镜像、 卷影复制服务和 AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)。</span><span class="sxs-lookup"><span data-stu-id="a1f20-148">For more information about using SQL Server database mirroring with respect to BizTalk Server database clustering, see [SQL Server database mirroring, Volume Shadow Copy service and AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f20-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1f20-149">See Also</span></span>  
 [<span data-ttu-id="a1f20-150">横向扩展 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a1f20-150">Scaling Out the BizTalk Server Databases</span></span>](../technical-guides/scaling-out-the-biztalk-server-databases.md)