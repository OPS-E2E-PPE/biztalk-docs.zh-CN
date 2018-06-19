---
title: 解决 BizTalk Server 性能的问题 |Microsoft 文档
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
ms.openlocfilehash: 21003c4d3565158945e91371fa760cf97692b472
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007966"
---
# <a name="troubleshooting-biztalk-server-performance"></a><span data-ttu-id="4c5ef-102">解决 BizTalk Server 性能</span><span class="sxs-lookup"><span data-stu-id="4c5ef-102">Troubleshooting BizTalk Server Performance</span></span>
<span data-ttu-id="4c5ef-103">本部分包含诊断和解决与 BizTalk 消息引擎相关的性能问题的一般准则。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-103">This section contains general guidelines for diagnosing and resolving performance problems related to the BizTalk Messaging Engine.</span></span>  
  
## <a name="estimating-document-processing-requirements"></a><span data-ttu-id="4c5ef-104">评估文档处理要求</span><span class="sxs-lookup"><span data-stu-id="4c5ef-104">Estimating Document Processing Requirements</span></span>  
 <span data-ttu-id="4c5ef-105">在将解决方案部署到生产环境之前，进行规划和测试，以确定消息引擎性能需求。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-105">Plan and test to determine your Messaging Engine performance needs before deploying your solution into a production environment.</span></span> <span data-ttu-id="4c5ef-106">这将有助于您正确地构建 BizTalk Server 和 SQL Server 环境。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-106">This will help you build out your BizTalk Server and SQL Server environments appropriately.</span></span>  
  
1.  <span data-ttu-id="4c5ef-107">规划与容错、备份和恢复需要相关的开销</span><span class="sxs-lookup"><span data-stu-id="4c5ef-107">Plan for overhead associated with any fault tolerance or backup and recovery needs</span></span>  
  
    -   <span data-ttu-id="4c5ef-108">是否要将 SQL Server 磁盘配置为 RAID 阵列？</span><span class="sxs-lookup"><span data-stu-id="4c5ef-108">Will the SQL Server disks be configured as RAID arrays?</span></span>  
  
    -   <span data-ttu-id="4c5ef-109">是否要为 BizTalk 主机、SQL Server 或企业单一登录使用 Windows 群集？</span><span class="sxs-lookup"><span data-stu-id="4c5ef-109">Will Windows Clustering be used for BizTalk Hosts, SQL Server, or Enterprise Single Sign-On?</span></span> <span data-ttu-id="4c5ef-110">有关详细信息请参阅[高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-110">For more information see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
    -   <span data-ttu-id="4c5ef-111">是否将使用网络负载平衡？</span><span class="sxs-lookup"><span data-stu-id="4c5ef-111">Will Network Load Balancing be used?</span></span>  
  
    -   <span data-ttu-id="4c5ef-112">环境的备份和恢复要求是什么？</span><span class="sxs-lookup"><span data-stu-id="4c5ef-112">What are the backup and recovery requirements for the environment?</span></span> <span data-ttu-id="4c5ef-113">有关详细信息，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-113">For more information, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
2.  <span data-ttu-id="4c5ef-114">请按照中的准则[持续性能规划](../core/planning-for-sustained-performance.md)来计划、 测试和缩放你的 BizTalk Server 和 SQL Server 环境。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-114">Follow the guidelines in [Planning for Sustained Performance](../core/planning-for-sustained-performance.md) to plan, test, and scale your BizTalk Server and SQL Server environment.</span></span>  
  
3.  <span data-ttu-id="4c5ef-115">请按照中的准则[跟踪性能特征](../core/tracking-performance-characteristics.md)规划文档跟踪要求与关联的开销。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-115">Follow the guidelines in [Tracking Performance Characteristics](../core/tracking-performance-characteristics.md) to plan for overhead associated with document tracking requirements.</span></span>  
  
## <a name="optimizing-an-existing-biztalk-server-environment"></a><span data-ttu-id="4c5ef-116">优化现有 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="4c5ef-116">Optimizing an Existing BizTalk Server Environment</span></span>  
 <span data-ttu-id="4c5ef-117">按照以下步骤优化现有 BizTalk Server 环境：</span><span class="sxs-lookup"><span data-stu-id="4c5ef-117">Follow these steps to optimize an existing BizTalk Server environment:</span></span>  
  
1.  <span data-ttu-id="4c5ef-118">请按照中的准则[识别性能瓶颈](../core/identifying-performance-bottlenecks.md)定点 BizTalk Server 环境中可能的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-118">Follow the guidelines in [Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) to pinpoint possible bottlenecks in your BizTalk Server environment.</span></span>  
  
2.  <span data-ttu-id="4c5ef-119">请按照中的准则[优化资源使用通过主机限制](../core/optimizing-resource-usage-through-host-throttling.md)以最大化 BizTalk Server 环境的文档吞吐量。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-119">Follow the guidelines in [Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) to maximize document throughput for the BizTalk Server environment.</span></span>  
  
3.  <span data-ttu-id="4c5ef-120">请考虑修改中所述的参数[配置参数会影响适配器性能](../core/configuration-parameters-that-affect-adapter-performance.md)来最大化适配器性能在某些情况下。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-120">Consider modifying the parameters documented in [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md) to maximize adapter performance in certain scenarios.</span></span>  
  
4.  <span data-ttu-id="4c5ef-121">请按照中的准则[如何 BizTalk 服务器进程大消息](../core/how-biztalk-server-processes-large-messages.md)在处理大型消息 (超过 100 MB) 时优化消息引擎性能。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-121">Follow the guidelines in [How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) to optimize Messaging Engine performance when processing Large Messages (more than 100 MB).</span></span>  
  
5.  <span data-ttu-id="4c5ef-122">为发送适配器、接收适配器和业务流程创建单独的主机和主机实例。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-122">Create separate hosts and host instances for send adapters, receive adapters, and orchestrations.</span></span> <span data-ttu-id="4c5ef-123">这将使每个适配器都在单独的主机实例中运行，并确保一个适配器不会对另一个适配器产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-123">This will give each adapter a separate host instance to run in and will ensure that one adapter does not adversely affect another.</span></span> <span data-ttu-id="4c5ef-124">由于可在主机级别配置主机阻止设置，因而将处理逻辑分为不同的主机还可基于每个主机的处理要求来配置阻止设置。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-124">Since host throttling settings are configurable at the host level, the separation of processing logic into different hosts will also permit you to configure throttling settings based upon the processing requirements of each host.</span></span>  
  
## <a name="diagnosing-performance-problems-in-an-existing-biztalk-server-environment"></a><span data-ttu-id="4c5ef-125">诊断现有 BizTalk Server 环境中的性能问题</span><span class="sxs-lookup"><span data-stu-id="4c5ef-125">Diagnosing Performance Problems in an Existing BizTalk Server Environment</span></span>  
 <span data-ttu-id="4c5ef-126">通常，可以将性能问题的范围缩小到以下 BizTalk Server 环境的组件之一：</span><span class="sxs-lookup"><span data-stu-id="4c5ef-126">Typically a performance problem can be narrowed down to one of the following components of a BizTalk Server environment:</span></span>  
  
-   <span data-ttu-id="4c5ef-127">接收适配器或正向此适配器发送文档的系统。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-127">A receive adapter or the system that the adapter is receiving documents from.</span></span> <span data-ttu-id="4c5ef-128">例如，如果 HTTP 适配器正以非最佳速率接收文档，则导致性能问题的可能是 HTTP 接收适配器或正向此 HTTP 适配器发送内容的客户端。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-128">For example if documents are being received by the HTTP adapter at a suboptimal rate then the problem may be with the HTTP receive adapter or with the client that is posting to the HTTP adapter.</span></span>  
  
-   <span data-ttu-id="4c5ef-129">业务流程服务实例。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-129">An orchestration service instance.</span></span>  
  
-   <span data-ttu-id="4c5ef-130">保存的 Microsoft SQL server 的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-130">Performance of the Microsoft SQL server that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
-   <span data-ttu-id="4c5ef-131">发送适配器或正接收此适配器发送的文档的系统。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-131">A send adapter or the system that the adapter is sending documents to.</span></span> <span data-ttu-id="4c5ef-132">例如，如果文档发送速率并非最佳的 SQL 适配器则问题可能与 SQL 发送适配器或运行的计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]更新 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-132">For example if documents are being sent by the SQL adapter at a suboptimal rate then the problem may be with the SQL send adapter or with the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that the SQL adapter is updating.</span></span>  
  
 <span data-ttu-id="4c5ef-133">使用以下准则来帮助识别的各组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不良执行的环境：</span><span class="sxs-lookup"><span data-stu-id="4c5ef-133">Use the following guidelines to help identify the components of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment that are performing poorly:</span></span>  
  
-   <span data-ttu-id="4c5ef-134">捕获任何警告或错误中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]事件查看器。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-134">Capture any warnings or errors generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Event Viewer.</span></span>  
  
-   <span data-ttu-id="4c5ef-135">按照中的步骤[识别性能瓶颈](../core/identifying-performance-bottlenecks.md)有助于查明性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-135">Follow the steps in [Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) to help identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="4c5ef-136">确定了性能较差的组件后，请遵循以下相应的准则来帮助解决问题：</span><span class="sxs-lookup"><span data-stu-id="4c5ef-136">Once the poorly performing component has been identified, follow the appropriate guidelines to help resolve the issue:</span></span>  
  
 <span data-ttu-id="4c5ef-137">**用于解决相关发送和接收适配器的性能问题的指导原则**</span><span class="sxs-lookup"><span data-stu-id="4c5ef-137">**Guidelines for resolving performance problems related to send and receive adapters**</span></span>  
  
-   <span data-ttu-id="4c5ef-138">请参阅[疑难解答 BizTalk Server 适配器](../core/troubleshooting-biztalk-server-adapters.md)来排查问题的一般信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-138">See [Troubleshooting BizTalk Server Adapters](../core/troubleshooting-biztalk-server-adapters.md) for general information to troubleshoot problems with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span> <span data-ttu-id="4c5ef-139">本部分包含常规疑难解答信息，包括有关如何设置某些适配器的日志记录的信息，还包括可用于诊断网络问题、与 MSDTC 相关的问题、与注册表相关的问题、与文件系统相关的问题以及与 IIS 相关的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-139">This section contains general troubleshooting information including information about how to set up logging for certain adapters and information that can be used diagnose network problems, problems with MSDTC, problems with the registry, problems with the file system, and problems with IIS.</span></span>  
  
-   <span data-ttu-id="4c5ef-140">请参阅的相应部分[疑难解答 BizTalk Server 依赖项](../core/troubleshooting-biztalk-server-dependencies.md)解决与 MSDTC、 证书、 Enterprise 上单一登录，问题的一般信息和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-140">See the appropriate section of [Troubleshooting BizTalk Server Dependencies](../core/troubleshooting-biztalk-server-dependencies.md) for general information to troubleshoot problems with MSDTC, Certificates, Enterprise Single Sign-On, and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4c5ef-141">**以解决与业务流程相关的性能问题的指导原则**</span><span class="sxs-lookup"><span data-stu-id="4c5ef-141">**Guidelines for resolving performance problems related to orchestrations**</span></span>  
  
-   <span data-ttu-id="4c5ef-142">修改 BTSNTSvc.exe.config 文件中所述的相应部分[业务流程引擎配置](../core/orchestration-engine-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-142">Modify the appropriate sections of the BTSNTSvc.exe.config file documented in [Orchestration Engine Configuration](../core/orchestration-engine-configuration.md).</span></span>  
  
 <span data-ttu-id="4c5ef-143">**以解决与 SQL Server 相关的性能问题的指导原则**</span><span class="sxs-lookup"><span data-stu-id="4c5ef-143">**Guidelines for resolving performance problems related to SQL Server**</span></span>  
  
-   <span data-ttu-id="4c5ef-144">SQL Server Profiler 可用于捕获发送至 SQL Server 的 Transact-SQL 语句和这些语句的 SQL Server 结果集。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-144">SQL Server Profiler can be used to capture Transact-SQL statements that are sent to SQL Server and the SQL Server result sets from these statements.</span></span> <span data-ttu-id="4c5ef-145">由于 BizTalk Server 与 SQL Server 紧密集成，因此，对于在从 SQL Server 数据库读取和向 SQL Server 数据库写入时在 BizTalk Server 中发生的问题，SQL Server 配置文件跟踪分析将是一个非常有用的问题分析工具。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-145">Since BizTalk Server is tightly integrated with SQL Server, the analysis of a SQL Server Profile trace can be a useful tool for analyzing problems that may occur in BizTalk Server when reading from and writing to SQL Server databases.</span></span> <span data-ttu-id="4c5ef-146">有关如何使用 SQL Server Profiler 的信息，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-146">For information about how to use SQL Server Profiler see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="4c5ef-147">SQL Server 查询编辑器可以用于执行直接针对 SQL Server 数据库的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-147">The SQL Server Query Editor can be used to execute SQL statements directly against SQL Server databases.</span></span> <span data-ttu-id="4c5ef-148">在某些情况下，此功能对于查询 BizTalk Server 数据库或更新 BizTalk Server 数据库很有用。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-148">This functionality may be useful for querying the BizTalk Server databases or for updating the BizTalk Server databases in certain scenarios.</span></span> <span data-ttu-id="4c5ef-149">有关查询编辑器的详细信息请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-149">For more information about Query Editor see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="4c5ef-150">查看[故障排除 SQL Server](../core/troubleshooting-sql-server.md)有关其他信息。</span><span class="sxs-lookup"><span data-stu-id="4c5ef-150">Review [Troubleshooting SQL Server](../core/troubleshooting-sql-server.md) for additional information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5ef-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c5ef-151">See Also</span></span>  
 [<span data-ttu-id="4c5ef-152">故障排除</span><span class="sxs-lookup"><span data-stu-id="4c5ef-152">Troubleshooting</span></span>](../core/troubleshooting.md)