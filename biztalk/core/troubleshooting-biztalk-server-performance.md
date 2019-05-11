---
title: BizTalk Server 性能故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbf21fb9-1ae1-48b5-a65a-e96839b23945
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec29254a43a86f29a16ddb5babe5d3c607689f68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401874"
---
# <a name="troubleshooting-biztalk-server-performance"></a><span data-ttu-id="3302b-102">BizTalk Server 性能故障排除</span><span class="sxs-lookup"><span data-stu-id="3302b-102">Troubleshooting BizTalk Server Performance</span></span>
<span data-ttu-id="3302b-103">本部分包含有关诊断和解决与 BizTalk 消息引擎相关的性能问题的常规指导原则。</span><span class="sxs-lookup"><span data-stu-id="3302b-103">This section contains general guidelines for diagnosing and resolving performance problems related to the BizTalk Messaging Engine.</span></span>  
  
## <a name="estimating-document-processing-requirements"></a><span data-ttu-id="3302b-104">评估文档处理要求</span><span class="sxs-lookup"><span data-stu-id="3302b-104">Estimating Document Processing Requirements</span></span>  
 <span data-ttu-id="3302b-105">计划和测试以确定消息引擎性能需求之前将解决方案部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="3302b-105">Plan and test to determine your Messaging Engine performance needs before deploying your solution into a production environment.</span></span> <span data-ttu-id="3302b-106">这将帮助您适当地构建您的 BizTalk Server 和 SQL Server 环境。</span><span class="sxs-lookup"><span data-stu-id="3302b-106">This will help you build out your BizTalk Server and SQL Server environments appropriately.</span></span>  
  
1.  <span data-ttu-id="3302b-107">计划相关的开销的任何容错、 备份和恢复需求</span><span class="sxs-lookup"><span data-stu-id="3302b-107">Plan for overhead associated with any fault tolerance or backup and recovery needs</span></span>  
  
    -   <span data-ttu-id="3302b-108">将 SQL Server 磁盘配置为 RAID 阵列？</span><span class="sxs-lookup"><span data-stu-id="3302b-108">Will the SQL Server disks be configured as RAID arrays?</span></span>  
  
    -   <span data-ttu-id="3302b-109">将 Windows 群集使用适用于 BizTalk 主机、 SQL Server 或企业单一登录？</span><span class="sxs-lookup"><span data-stu-id="3302b-109">Will Windows Clustering be used for BizTalk Hosts, SQL Server, or Enterprise Single Sign-On?</span></span> <span data-ttu-id="3302b-110">有关详细信息请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="3302b-110">For more information see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
    -   <span data-ttu-id="3302b-111">将使用网络负载平衡？</span><span class="sxs-lookup"><span data-stu-id="3302b-111">Will Network Load Balancing be used?</span></span>  
  
    -   <span data-ttu-id="3302b-112">环境的备份和恢复要求有哪些？</span><span class="sxs-lookup"><span data-stu-id="3302b-112">What are the backup and recovery requirements for the environment?</span></span> <span data-ttu-id="3302b-113">有关详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="3302b-113">For more information, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
2.  <span data-ttu-id="3302b-114">遵循中的准则[规划可持续性能](../core/planning-for-sustained-performance.md)计划、 测试和缩放你的 BizTalk Server 和 SQL Server 环境。</span><span class="sxs-lookup"><span data-stu-id="3302b-114">Follow the guidelines in [Planning for Sustained Performance](../core/planning-for-sustained-performance.md) to plan, test, and scale your BizTalk Server and SQL Server environment.</span></span>  
  
3.  <span data-ttu-id="3302b-115">遵循中的准则[跟踪性能特征](../core/tracking-performance-characteristics.md)规划与文档跟踪要求相关联的开销。</span><span class="sxs-lookup"><span data-stu-id="3302b-115">Follow the guidelines in [Tracking Performance Characteristics](../core/tracking-performance-characteristics.md) to plan for overhead associated with document tracking requirements.</span></span>  
  
## <a name="optimizing-an-existing-biztalk-server-environment"></a><span data-ttu-id="3302b-116">优化现有 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="3302b-116">Optimizing an Existing BizTalk Server Environment</span></span>  
 <span data-ttu-id="3302b-117">请执行以下步骤优化现有 BizTalk Server 环境：</span><span class="sxs-lookup"><span data-stu-id="3302b-117">Follow these steps to optimize an existing BizTalk Server environment:</span></span>  
  
1.  <span data-ttu-id="3302b-118">遵循中的准则[识别性能瓶颈](../core/identifying-performance-bottlenecks.md)以查明 BizTalk Server 环境中可能的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="3302b-118">Follow the guidelines in [Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) to pinpoint possible bottlenecks in your BizTalk Server environment.</span></span>  
  
2.  <span data-ttu-id="3302b-119">遵循中的准则[优化资源使用情况通过主机阻止](../core/optimizing-resource-usage-through-host-throttling.md)以使 BizTalk Server 环境的文档吞吐量最大化。</span><span class="sxs-lookup"><span data-stu-id="3302b-119">Follow the guidelines in [Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) to maximize document throughput for the BizTalk Server environment.</span></span>  
  
3.  <span data-ttu-id="3302b-120">请考虑修改中所述的参数[配置参数会影响适配器性能的](../core/configuration-parameters-that-affect-adapter-performance.md)以最大程度提高某些方案中的适配器性能。</span><span class="sxs-lookup"><span data-stu-id="3302b-120">Consider modifying the parameters documented in [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md) to maximize adapter performance in certain scenarios.</span></span>  
  
4.  <span data-ttu-id="3302b-121">遵循中的准则[如何 BizTalk Server 处理大消息](../core/how-biztalk-server-processes-large-messages.md)优化消息引擎性能时处理大消息 (超过 100 MB)。</span><span class="sxs-lookup"><span data-stu-id="3302b-121">Follow the guidelines in [How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) to optimize Messaging Engine performance when processing Large Messages (more than 100 MB).</span></span>  
  
5.  <span data-ttu-id="3302b-122">创建单独的主机和主机实例，以便发送适配器，接收适配器和业务流程。</span><span class="sxs-lookup"><span data-stu-id="3302b-122">Create separate hosts and host instances for send adapters, receive adapters, and orchestrations.</span></span> <span data-ttu-id="3302b-123">这将使每个适配器的单独的主机实例中运行，并确保该适配器不产生不利影响另一个。</span><span class="sxs-lookup"><span data-stu-id="3302b-123">This will give each adapter a separate host instance to run in and will ensure that one adapter does not adversely affect another.</span></span> <span data-ttu-id="3302b-124">由于在主机级别配置的主机阻止设置，处理逻辑分为不同的主机的分离还允许您配置基于每个主机的处理要求的限制设置。</span><span class="sxs-lookup"><span data-stu-id="3302b-124">Since host throttling settings are configurable at the host level, the separation of processing logic into different hosts will also permit you to configure throttling settings based upon the processing requirements of each host.</span></span>  
  
## <a name="diagnosing-performance-problems-in-an-existing-biztalk-server-environment"></a><span data-ttu-id="3302b-125">诊断现有 BizTalk Server 环境中的性能问题</span><span class="sxs-lookup"><span data-stu-id="3302b-125">Diagnosing Performance Problems in an Existing BizTalk Server Environment</span></span>  
 <span data-ttu-id="3302b-126">通常为 BizTalk Server 环境的以下组件之一被缩小性能问题：</span><span class="sxs-lookup"><span data-stu-id="3302b-126">Typically a performance problem can be narrowed down to one of the following components of a BizTalk Server environment:</span></span>  
  
- <span data-ttu-id="3302b-127">接收适配器或适配器正在接收来自文档的系统。</span><span class="sxs-lookup"><span data-stu-id="3302b-127">A receive adapter or the system that the adapter is receiving documents from.</span></span> <span data-ttu-id="3302b-128">例如，如果文档在接收 HTTP 适配器以非最优的速率，则问题可能是使用 HTTP 获得适配器或发布到 HTTP 适配器的客户端。</span><span class="sxs-lookup"><span data-stu-id="3302b-128">For example if documents are being received by the HTTP adapter at a suboptimal rate then the problem may be with the HTTP receive adapter or with the client that is posting to the HTTP adapter.</span></span>  
  
- <span data-ttu-id="3302b-129">业务流程服务实例。</span><span class="sxs-lookup"><span data-stu-id="3302b-129">An orchestration service instance.</span></span>  
  
- <span data-ttu-id="3302b-130">包含 Microsoft SQL server 的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="3302b-130">Performance of the Microsoft SQL server that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
- <span data-ttu-id="3302b-131">发送适配器或适配器正在发送到的文档的系统。</span><span class="sxs-lookup"><span data-stu-id="3302b-131">A send adapter or the system that the adapter is sending documents to.</span></span> <span data-ttu-id="3302b-132">例如，如果该问题可能是与 SQL 发送适配器或运行的计算机，然后费率非最优 SQL 适配器发送文档[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]更新 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="3302b-132">For example if documents are being sent by the SQL adapter at a suboptimal rate then the problem may be with the SQL send adapter or with the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that the SQL adapter is updating.</span></span>  
  
  <span data-ttu-id="3302b-133">使用以下准则来帮助识别的各组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]较差的环境：</span><span class="sxs-lookup"><span data-stu-id="3302b-133">Use the following guidelines to help identify the components of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment that are performing poorly:</span></span>  
  
- <span data-ttu-id="3302b-134">捕获的任何警告或错误中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]事件查看器。</span><span class="sxs-lookup"><span data-stu-id="3302b-134">Capture any warnings or errors generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Event Viewer.</span></span>  
  
- <span data-ttu-id="3302b-135">按照中的步骤[识别性能瓶颈](../core/identifying-performance-bottlenecks.md)来帮助确定性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="3302b-135">Follow the steps in [Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) to help identify performance bottlenecks.</span></span>  
  
  <span data-ttu-id="3302b-136">一旦确定差的组件，请执行相应的准则来帮助解决此问题：</span><span class="sxs-lookup"><span data-stu-id="3302b-136">Once the poorly performing component has been identified, follow the appropriate guidelines to help resolve the issue:</span></span>  
  
  <span data-ttu-id="3302b-137">**解决相关来发送和接收适配器的性能问题的准则**</span><span class="sxs-lookup"><span data-stu-id="3302b-137">**Guidelines for resolving performance problems related to send and receive adapters**</span></span>  
  
- <span data-ttu-id="3302b-138">请参阅[故障排除 BizTalk Server 适配器](../core/troubleshooting-biztalk-server-adapters.md)问题的疑难解答的一般信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。</span><span class="sxs-lookup"><span data-stu-id="3302b-138">See [Troubleshooting BizTalk Server Adapters](../core/troubleshooting-biztalk-server-adapters.md) for general information to troubleshoot problems with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span> <span data-ttu-id="3302b-139">本部分包含常规故障排除信息，包括有关如何设置日志记录对于某些适配器的信息和可用的信息诊断网络问题，问题与 MSDTC、 注册表、 文件出现问题的问题系统，并使用 IIS 的问题。</span><span class="sxs-lookup"><span data-stu-id="3302b-139">This section contains general troubleshooting information including information about how to set up logging for certain adapters and information that can be used diagnose network problems, problems with MSDTC, problems with the registry, problems with the file system, and problems with IIS.</span></span>  
  
- <span data-ttu-id="3302b-140">请参阅的相应部分[故障排除的 BizTalk Server 依赖项](../core/troubleshooting-biztalk-server-dependencies.md)解决与 MSDTC、 证书、 企业单一登录，问题的常规信息和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3302b-140">See the appropriate section of [Troubleshooting BizTalk Server Dependencies](../core/troubleshooting-biztalk-server-dependencies.md) for general information to troubleshoot problems with MSDTC, Certificates, Enterprise Single Sign-On, and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
  <span data-ttu-id="3302b-141">**解决与业务流程相关的性能问题的准则**</span><span class="sxs-lookup"><span data-stu-id="3302b-141">**Guidelines for resolving performance problems related to orchestrations**</span></span>  
  
- <span data-ttu-id="3302b-142">修改 BTSNTSvc.exe.config 文件中所述的相应部分[业务流程引擎配置](../core/orchestration-engine-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="3302b-142">Modify the appropriate sections of the BTSNTSvc.exe.config file documented in [Orchestration Engine Configuration](../core/orchestration-engine-configuration.md).</span></span>  
  
  <span data-ttu-id="3302b-143">**解决与 SQL Server 相关的性能问题的准则**</span><span class="sxs-lookup"><span data-stu-id="3302b-143">**Guidelines for resolving performance problems related to SQL Server**</span></span>  
  
- <span data-ttu-id="3302b-144">SQL Server Profiler 可用于捕获发送到 SQL Server 的 TRANSACT-SQL 语句和 SQL Server 结果集从这些语句。</span><span class="sxs-lookup"><span data-stu-id="3302b-144">SQL Server Profiler can be used to capture Transact-SQL statements that are sent to SQL Server and the SQL Server result sets from these statements.</span></span> <span data-ttu-id="3302b-145">由于 BizTalk Server 与 SQL Server 紧密集成，SQL Server 配置文件跟踪分析可以是用于分析在 BizTalk Server 中读取和写入到 SQL Server 数据库时可能发生的问题的有用工具。</span><span class="sxs-lookup"><span data-stu-id="3302b-145">Since BizTalk Server is tightly integrated with SQL Server, the analysis of a SQL Server Profile trace can be a useful tool for analyzing problems that may occur in BizTalk Server when reading from and writing to SQL Server databases.</span></span> <span data-ttu-id="3302b-146">有关如何使用 SQL Server Profiler 的信息请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="3302b-146">For information about how to use SQL Server Profiler see the SQL Server documentation.</span></span>  
  
- <span data-ttu-id="3302b-147">SQL Server 查询编辑器可以用于直接对 SQL Server 数据库执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="3302b-147">The SQL Server Query Editor can be used to execute SQL statements directly against SQL Server databases.</span></span> <span data-ttu-id="3302b-148">此功能可能对于查询 BizTalk Server 数据库，或者在某些情况下 BizTalk Server 数据库更新。</span><span class="sxs-lookup"><span data-stu-id="3302b-148">This functionality may be useful for querying the BizTalk Server databases or for updating the BizTalk Server databases in certain scenarios.</span></span> <span data-ttu-id="3302b-149">有关查询编辑器的详细信息请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="3302b-149">For more information about Query Editor see the SQL Server documentation.</span></span>  
  
- <span data-ttu-id="3302b-150">审阅[故障排除 SQL Server](../core/troubleshooting-sql-server.md)有关其他信息。</span><span class="sxs-lookup"><span data-stu-id="3302b-150">Review [Troubleshooting SQL Server](../core/troubleshooting-sql-server.md) for additional information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3302b-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="3302b-151">See Also</span></span>  
 [<span data-ttu-id="3302b-152">故障排除</span><span class="sxs-lookup"><span data-stu-id="3302b-152">Troubleshooting</span></span>](../core/troubleshooting.md)