---
title: 预配置数据库 Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c525c3a-249c-4694-b287-a8c35a6aa524
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b5486c3a18473998a11a98f6741097d2f751128
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399567"
---
# <a name="pre-configuration-database-optimizations"></a><span data-ttu-id="4b30a-102">预配置数据库优化</span><span class="sxs-lookup"><span data-stu-id="4b30a-102">Pre-Configuration Database Optimizations</span></span>
<span data-ttu-id="4b30a-103">由于 SQL Server 在任何 BizTalk Server 环境中起着关键角色，它是一项极其重要 SQL 服务器进行配置/优化以获得最佳性能问题。</span><span class="sxs-lookup"><span data-stu-id="4b30a-103">Because of the critical role that SQL Server plays in any BizTalk Server environment, it is of paramount importance that SQL Server be configured/tuned for optimal performance.</span></span> <span data-ttu-id="4b30a-104">如果 SQL Server 不优化很好地运行，然后 BizTalk Server 使用的数据库将成为瓶颈，并在 BizTalk Server 环境的整体性能将会受到影响。</span><span class="sxs-lookup"><span data-stu-id="4b30a-104">If SQL Server is not tuned to perform well, then the databases used by BizTalk Server will become a bottleneck and the overall performance of the BizTalk Server environment will suffer.</span></span> <span data-ttu-id="4b30a-105">本主题介绍在安装 BizTalk Server 和配置 BizTalk Server 数据库之前应遵循的几个 SQL Server 性能优化。</span><span class="sxs-lookup"><span data-stu-id="4b30a-105">This topic describes several SQL Server performance optimizations that should be followed before installing BizTalk Server and configuring the BizTalk Server databases.</span></span>  
  
## <a name="set-ntfs-file-allocation-unit"></a><span data-ttu-id="4b30a-106">设置 NTFS 文件分配单元</span><span class="sxs-lookup"><span data-stu-id="4b30a-106">Set NTFS File Allocation Unit</span></span>  
 <span data-ttu-id="4b30a-107">SQL Server 将在其数据存储**区**，这是八个物理上连续的 8k 页，即 64 KB 的集合。</span><span class="sxs-lookup"><span data-stu-id="4b30a-107">SQL Server stores its data in **Extents**, which are collections of eight physically contiguous 8K pages, or 64 KB.</span></span> <span data-ttu-id="4b30a-108">因此，若要优化磁盘性能，将设置为 64 KB NTFS 分配单元大小"磁盘配置最佳实践"中所述在[预部署 I/O 最佳实践](https://msdn.microsoft.com/library/cc966412.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-108">Therefore, to optimize disk performance, set the NTFS Allocation Unit size to 64KB as described in the “Disk Configuration Best Practices” at  [Predeployment I/O Best Practices](https://msdn.microsoft.com/library/cc966412.aspx).</span></span>  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a><span data-ttu-id="4b30a-109">有关版本和版本的 SQL Server 的注意事项</span><span class="sxs-lookup"><span data-stu-id="4b30a-109">Considerations for the version and edition of SQL Server</span></span>  
 <span data-ttu-id="4b30a-110">各种版本和版本的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]提供了会影响性能的不同功能在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="4b30a-110">Various versions and editions of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] provide different features that can affect the performance of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="4b30a-111">例如，在高负载情况下，可用于 32 位版本的数据库锁的数目[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可能超过了，这是对 BizTalk 解决方案的性能造成不利影响。</span><span class="sxs-lookup"><span data-stu-id="4b30a-111">For example, under high-load conditions, the number of database locks that are available for the 32-bit version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] might be exceeded, which is detrimental to the performance of the BizTalk solution.</span></span> <span data-ttu-id="4b30a-112">请考虑保存 MessageBox 数据库上的 SQL Server 的 64 位版本，如果您在测试环境中遇到"内存不足"错误。</span><span class="sxs-lookup"><span data-stu-id="4b30a-112">Consider housing your MessageBox database on a 64-bit version of SQL Server if you are experiencing "out of lock" errors in your test environment.</span></span> <span data-ttu-id="4b30a-113">可用锁的数目是 64 位版本的 SQL Server 上高得多。</span><span class="sxs-lookup"><span data-stu-id="4b30a-113">The number of available locks is significantly higher on the 64-bit version of SQL Server.</span></span>  
  
 <span data-ttu-id="4b30a-114">确定所需的 BizTalk 环境的数据库引擎功能时，请考虑下表。</span><span class="sxs-lookup"><span data-stu-id="4b30a-114">Consider the following table when deciding on the database engine features that you will need for your BizTalk environment.</span></span> <span data-ttu-id="4b30a-115">对于大量的、 需要聚类分析的企业级解决方案支持，BizTalk Server 日志传送的支持，或 Analysis Services 支持，则需要 SQL Server Enterprise Edition 主机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="4b30a-115">For large scale, enterprise-level solutions that require clustering support, BizTalk Server log shipping support, or Analysis Services support, then you need SQL Server Enterprise Edition to host the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases.</span></span>   

 <span data-ttu-id="4b30a-116">SQL Server 各个版本支持的功能的完整列表，请参阅[SQL Server 版本和支持的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-116">For a complete list of the features supported by the SQL Server editions, see [SQL Server Editions and supported features](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016).</span></span>
  
## <a name="database-planning-considerations"></a><span data-ttu-id="4b30a-117">数据库的规划注意事项</span><span class="sxs-lookup"><span data-stu-id="4b30a-117">Database planning considerations</span></span>  
 <span data-ttu-id="4b30a-118">我们建议你托管 SQL Server 数据库上快速存储 （例如，快速 SAN 磁盘或快速 SCSI 磁盘）。</span><span class="sxs-lookup"><span data-stu-id="4b30a-118">We recommend that you host your SQL Server databases on fast storage (for example, fast SAN disks or fast SCSI disks).</span></span> <span data-ttu-id="4b30a-119">我们建议使用 RAID 10 (1 + 0) 而不是 RAID 5 因为 raid 5 是写入的速度要慢。</span><span class="sxs-lookup"><span data-stu-id="4b30a-119">We recommend RAID 10 (1+0) instead of RAID 5 since raid 5 is slower at writing.</span></span> <span data-ttu-id="4b30a-120">较新的 SAN 磁盘具有非常大的内存缓存，因此在这些情况下选择的 raid 并不那么重要。</span><span class="sxs-lookup"><span data-stu-id="4b30a-120">Newer SAN disks have very large memory caches, so in these cases the raid selection is not as important.</span></span> <span data-ttu-id="4b30a-121">若要提高性能，数据库和其日志文件可驻留在不同的物理磁盘。</span><span class="sxs-lookup"><span data-stu-id="4b30a-121">To increase performance, databases and their log files can reside on different physical disks.</span></span>  
  
 <span data-ttu-id="4b30a-122">此外请考虑如果使用的存储区域网络 (SAN) 进行优化的主机总线适配器 (HBA) 队列深度。</span><span class="sxs-lookup"><span data-stu-id="4b30a-122">Also consider tuning the host bus adapter (HBA) queue depth if using a storage area network (SAN).</span></span> <span data-ttu-id="4b30a-123">这可能会显著影响 I/O 吞吐量和扩展的框值可以是 SQL Server 的不足。</span><span class="sxs-lookup"><span data-stu-id="4b30a-123">This can significantly impact I/O throughput and out-of-the box values can be insufficient for SQL Server.</span></span> <span data-ttu-id="4b30a-124">测试是必需的来确定最佳值，但队列深度为 64 通常被认为最好先在缺少的任何特定供应商建议</span><span class="sxs-lookup"><span data-stu-id="4b30a-124">Testing is required to determine optimal value, although queue depth of 64 is generally accepted as a good starting point in the absence of any specific vendor recommendations</span></span>  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a><span data-ttu-id="4b30a-125">安装适用于 SQL Server 最新 service pack 和累积更新</span><span class="sxs-lookup"><span data-stu-id="4b30a-125">Install the latest service pack and cumulative updates for SQL Server</span></span>  
 <span data-ttu-id="4b30a-126">安装适用于 SQL Server，以及最新的.NET Framework service pack 的最新的 service pack 和最新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="4b30a-126">Install the latest service packs and the latest cumulative updates for SQL Server as well as the latest .NET Framework service packs.</span></span>  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a><span data-ttu-id="4b30a-127">在 BizTalk Server 和 SQL Server 上安装 SQL Service Pack 和累积更新</span><span class="sxs-lookup"><span data-stu-id="4b30a-127">Install SQL Service Packs and cumulative updates on both BizTalk Server and SQL Server</span></span>  
 <span data-ttu-id="4b30a-128">当安装 SQL Server service pack 或累积更新，还在 BizTalk Server 计算机上安装 service pack 或累积更新。</span><span class="sxs-lookup"><span data-stu-id="4b30a-128">When installing service packs or cumulative updates for SQL Server, also install the service pack or cumulative update on the BizTalk Server computer.</span></span> <span data-ttu-id="4b30a-129">BizTalk Server 使用更新的 SQL Server service pack 和累积更新的 SQL 客户端组件。</span><span class="sxs-lookup"><span data-stu-id="4b30a-129">BizTalk Server uses SQL Client components that are updated by SQL Server service packs and cumulative updates.</span></span>  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a><span data-ttu-id="4b30a-130">请考虑使用快速固态硬盘 (SSD) 来存放 SQL Server tembdb</span><span class="sxs-lookup"><span data-stu-id="4b30a-130">Consider using a fast solid state drive (SSD) to house the SQL Server tembdb</span></span>  
 <span data-ttu-id="4b30a-131">请考虑使用一个或多个固态磁盘 (SSD) 驱动器来存放 TempDB。</span><span class="sxs-lookup"><span data-stu-id="4b30a-131">Consider using one or more Solid State Disk (SSD) drives to house the TempDB.</span></span> <span data-ttu-id="4b30a-132">SSD 驱动器提供显著的性能优于传统硬盘驱动器，并在进入主流市场快速删除价格中。</span><span class="sxs-lookup"><span data-stu-id="4b30a-132">SSD drives offer significant performance advantages over traditional hard drives and are quickly dropping in price as they enter mainstream markets.</span></span> <span data-ttu-id="4b30a-133">因为 TempDB 的性能通常是整体的关键因素[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能，添加了的驱动器的初始成本将通常会快速得到了补偿的整体增加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能，尤其在运行企业应用程序为其[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能至关重要。</span><span class="sxs-lookup"><span data-stu-id="4b30a-133">Because TempDB performance is often a key factor for overall [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, the added initial cost of the drives will often be quickly recouped by the overall increased [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, especially when running enterprise applications for which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance is critical.</span></span>  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a><span data-ttu-id="4b30a-134">请考虑实施 SQL Server 2008 R2 数据收集器和管理数据仓库</span><span class="sxs-lookup"><span data-stu-id="4b30a-134">Consider implementing the SQL Server 2008 R2 Data Collector and Management Data Warehouse</span></span>  
 <span data-ttu-id="4b30a-135">SQL Server 2008 R2 可使用新数据收集器和管理数据仓库收集环境/数据库性能相关的数据以进行测试和趋势分析。</span><span class="sxs-lookup"><span data-stu-id="4b30a-135">SQL Server 2008 R2 accommodates the use of the new Data Collector and Management Data Warehouse to collect environment/database performance related data for test and trend analysis.</span></span> <span data-ttu-id="4b30a-136">数据收集器收集的所有数据保存到指定的管理数据仓库。</span><span class="sxs-lookup"><span data-stu-id="4b30a-136">The Data Collector persists all collected data to the specified Management Data Warehouse.</span></span> <span data-ttu-id="4b30a-137">尽管这不是一种性能优化这会十分有用的任何性能问题的分析。</span><span class="sxs-lookup"><span data-stu-id="4b30a-137">While this is not a performance optimization this will be useful for analysis of any performance issues.</span></span>  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a><span data-ttu-id="4b30a-138">授予用于 SQL Server Windows 锁定页内存特权的帐户</span><span class="sxs-lookup"><span data-stu-id="4b30a-138">Grant the account which is used for SQL Server the Windows Lock Pages In Memory privilege</span></span>  
 <span data-ttu-id="4b30a-139">授予内存特权仅授予对 SQL Server 服务帐户中的 Windows 锁定页。</span><span class="sxs-lookup"><span data-stu-id="4b30a-139">Grant the Windows Lock Pages in Memory privilege to the SQL Server service account.</span></span> <span data-ttu-id="4b30a-140">这应进行以锁定用于在物理内存中缓冲池分配的内存将 Windows 操作系统防止出 SQL Server 进程的缓冲池内存的分页。</span><span class="sxs-lookup"><span data-stu-id="4b30a-140">This should be done to prevent the Windows operating system from paging out the buffer pool memory of the SQL Server process by locking memory that is allocated for the buffer pool in physical memory.</span></span>  
  
 <span data-ttu-id="4b30a-141">在我们的实验室环境，Windows 策略**锁定内存页**选项默认情况下已启用。</span><span class="sxs-lookup"><span data-stu-id="4b30a-141">In our lab environment, the Windows policy **Lock Pages in Memory** option was enabled by default.</span></span> <span data-ttu-id="4b30a-142">请参阅[启用锁定页中内存选项](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-142">See [Enable the Lock Pages in Memory Option](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4b30a-143">授予 Windows 锁定页内存权限中的 SQL Server 服务帐户时受到某些限制。</span><span class="sxs-lookup"><span data-stu-id="4b30a-143">Certain limitations apply when granting the SQL Server service account the Windows Lock Pages in Memory privilege.</span></span> <span data-ttu-id="4b30a-144">请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="4b30a-144">See the following:</span></span> 
>   
> - [<span data-ttu-id="4b30a-145">缓冲池扩展</span><span class="sxs-lookup"><span data-stu-id="4b30a-145">Buffer Pool Extension</span></span>](https://docs.microsoft.com/sql/database-engine/configure-windows/buffer-pool-extension)  
> - [<span data-ttu-id="4b30a-146">启用锁定页中内存选项 </span><span class="sxs-lookup"><span data-stu-id="4b30a-146">Enable the Lock Pages in Memory Option </span></span>](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a><span data-ttu-id="4b30a-147">权限将 SE_MANAGE_VOLUME_NAME 授予 SQL Server 服务帐户</span><span class="sxs-lookup"><span data-stu-id="4b30a-147">Grant the SE_MANAGE_VOLUME_NAME right to the SQL Server Service Account</span></span>  
 <span data-ttu-id="4b30a-148">确保运行 SQL Server 服务帐户具有执行卷维护任务 Windows 权限，或确保其所属的组。</span><span class="sxs-lookup"><span data-stu-id="4b30a-148">Ensure the account running the SQL Server service has the ‘Perform Volume Maintenance Tasks’ Windows privilege or ensure it belongs to a group that does.</span></span> <span data-ttu-id="4b30a-149">如果数据库必须自动增长，这将允许即时文件初始化确保获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="4b30a-149">This will allow instant file Initialization ensuring optimum performance if a database has to Auto-grow.</span></span>  
  
## <a name="set-min-and-max-server-memory"></a><span data-ttu-id="4b30a-150">设置最小值和最大服务器内存</span><span class="sxs-lookup"><span data-stu-id="4b30a-150">Set Min and Max Server Memory</span></span>  
 <span data-ttu-id="4b30a-151">运行该主机的 SQL Server 的计算机应将 BizTalk Server 数据库专用于运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4b30a-151">The computers running SQL Server that host the BizTalk Server databases should be dedicated to running SQL Server.</span></span> <span data-ttu-id="4b30a-152">当运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库专用于运行 SQL Server 中时，我们建议的最小服务器内存和每个 SQL Server 实例上的最大服务器内存选项设置为指定的固定的内存量将分配给 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4b30a-152">When the computers running SQL Server that host the BizTalk Server databases are dedicated to running SQL Server, we recommend that the 'min server memory' and 'max server memory' options on each SQL Server instance are set to specify the fixed amount of memory to allocate to SQL Server.</span></span> <span data-ttu-id="4b30a-153">在这种情况下，您应将"min server memory"和"最大服务器内存"为相同的值 （设置为最大的 SQL Server 将使用的物理内存量）。</span><span class="sxs-lookup"><span data-stu-id="4b30a-153">In this case, you should set the “min server memory” and “max server memory” to the same value (equal to the maximum amount of physical memory that SQL Server will use).</span></span> <span data-ttu-id="4b30a-154">这将减少开销，否则将使用 SQL server 动态地管理这些值。</span><span class="sxs-lookup"><span data-stu-id="4b30a-154">This will reduce overhead that would otherwise be used by SQL Server dynamically managing these values.</span></span> <span data-ttu-id="4b30a-155">运行 SQL Server 以指定要分配到 SQL Server 的内存量固定每台计算机上运行以下 T-SQL 命令：</span><span class="sxs-lookup"><span data-stu-id="4b30a-155">Run the following T-SQL commands on each computer running SQL Server to specify the fixed amount of memory to allocate to SQL Server:</span></span>  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 <span data-ttu-id="4b30a-156">为 SQL Server 设置的内存量之前，请通过减去总物理内存中适用于 Windows Server 所需的内存来确定适当的内存设置。</span><span class="sxs-lookup"><span data-stu-id="4b30a-156">Before you set the amount of memory for SQL Server, determine the appropriate memory setting by subtracting the memory required for Windows Server from the total physical memory.</span></span> <span data-ttu-id="4b30a-157">这是内存的最大可以为 SQL Server 分配量。</span><span class="sxs-lookup"><span data-stu-id="4b30a-157">This is the maximum amount of memory you can assign to SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b30a-158">如果运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库还承载了企业单一登录主密钥服务器，然后您可能需要调整此值可确保有足够的内存可用于运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="4b30a-158">If the computers running SQL Server that host the BizTalk Server databases also host the Enterprise Single Sign-On Master Secret Server, then you may need to adjust this value to ensure that there is sufficient memory available to run the Enterprise Single Sign-On Service.</span></span> <span data-ttu-id="4b30a-159">它不提供对主密钥服务器高可用性的 SQL Server 群集上运行企业单一登录服务的群集的实例不常见的做法。</span><span class="sxs-lookup"><span data-stu-id="4b30a-159">It is not an uncommon practice to run a clustered instance of the Enterprise Single Sign-On service on a SQL Server cluster to provide high availability for the Master Secret Server.</span></span> <span data-ttu-id="4b30a-160">请参阅[聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)</span><span class="sxs-lookup"><span data-stu-id="4b30a-160">See [Clustering the Master Secret Server](../technical-guides/clustering-the-master-secret-server.md)</span></span>  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a><span data-ttu-id="4b30a-161">将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件</span><span class="sxs-lookup"><span data-stu-id="4b30a-161">Split the tempdb database into multiple data files of equal size on each SQL Server instance used by BizTalk Server</span></span>  
 <span data-ttu-id="4b30a-162">确保使用的 tempdb 数据文件大小相等的很关键，因为 SQL Server 使用的按比例填充算法基于数据文件的大小。</span><span class="sxs-lookup"><span data-stu-id="4b30a-162">Ensuring that the data files used for the tempdb are of equal size is critical because the proportional fill algorithm used by SQL Server is based on the size of the data files.</span></span> <span data-ttu-id="4b30a-163">如果使用不相等大小创建数据文件，按比例填充算法将使用为 GAM 分配，而不是所有的文件，这违背创建多个数据文件的目的之间进行分配更多的最大文件。</span><span class="sxs-lookup"><span data-stu-id="4b30a-163">If data files are created with unequal sizes, the proportional fill algorithm will use the largest file more for GAM allocations rather than spreading the allocations between all the files, thereby defeating the purpose of creating multiple data files.</span></span> <span data-ttu-id="4b30a-164">Tempdb 数据文件的最佳数量取决于在 tempdb 中看到的闩锁争用的程度。</span><span class="sxs-lookup"><span data-stu-id="4b30a-164">The optimal number of tempdb data files depends on the degree of latch contention seen in tempdb.</span></span> <span data-ttu-id="4b30a-165">作为常规经验，数据文件数应小于或等于其中的 Cpu 数是 8 的处理器内核/Cpu 数。</span><span class="sxs-lookup"><span data-stu-id="4b30a-165">As a general rule of thumb, the number of data files should be equal to number of processor cores/CPUs where number of CPUs is 8 or less.</span></span> <span data-ttu-id="4b30a-166">对于超过 8 个 Cpu 的服务器，创建数据文件的一半数目的 Cpu （同样，您只有闩锁争用）。</span><span class="sxs-lookup"><span data-stu-id="4b30a-166">For servers with more than 8 CPUs, create data files for half the number of CPUs (again, only you have latch contention).</span></span>  
  
 <span data-ttu-id="4b30a-167">在我们的实验室环境，我们使用下面的脚本创建 8 TempDB 数据文件，其中每个所包含的文件大小为 1024 MB，增长 100 MB 具有和 512 MB 的日志文件，增长 100 MB。</span><span class="sxs-lookup"><span data-stu-id="4b30a-167">In our lab environment, we used the script below to create 8 TempDB data files each of which had a file size of 1024 MB with 100 MB growth and a log file of 512 MB with 100 MB growth.</span></span> <span data-ttu-id="4b30a-168">数据文件移到 h： 驱动器和日志文件移到 i： 驱动器。</span><span class="sxs-lookup"><span data-stu-id="4b30a-168">The data files are moved to drive H: and log file are moved to drive I:.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4b30a-169">提供"按原样，"用于演示或培训目的，并且将使用您自己承担，此脚本。</span><span class="sxs-lookup"><span data-stu-id="4b30a-169">This script is provided “as is,” is intended for demo or educational purposes only, and is to be used at your own risk.</span></span> <span data-ttu-id="4b30a-170">使用此脚本不受 Microsoft，因此 Microsoft 不保证此脚本的适用性。</span><span class="sxs-lookup"><span data-stu-id="4b30a-170">Use of this script is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this script.</span></span>  
  
```  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
-- Use of included script samples are subject to the terms specified at   
-- http://www.microsoft.com/info/cpyright.htm  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--***Instructions***  
-- 1. If running the script from a remote server, change the context in SSMS to target instance  
-- 2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
-- 3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
-- 4. Examine servername & temp configuration  
-- 5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
      --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
-- 6. Resume script execution  
-- 7. If necessary, create new folders  
-- 8. Modify/Add data & log files   
-- 9. Recycle SQL service using sqlservermanager10.msc  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--1. If running the script from a remote server, change the context in SSMS to target instance  
--2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
--3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
--4. Examine servername & temp configuration  
SELECT @@SERVERNAME  
EXEC dbo.sp_helpdb tempdb  
--tempdev   1   C:\tempdb.mdf   PRIMARY  8192 KB  Unlimited  10%  data only  
--templog   2   C:\templog.ldf  NULL      512 KB  Unlimited  10%  log only  
GO  
--5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
     --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
--6. Resume script execution  
--7. If necessary, create new folders  
--!!md H:\MSSQL10.<instance>  
--!!md H:\MSSQL10.<instance>\MSSQL  
--!!md H:\MSSQL10.<instance>\MSSQL\DATA  
GO  
-- 8. Modify/Add data & log files   
 --note: even if the out-of-box mdf is already where it needs to be,   
   --the first command is necessary to modify size & filegrowth  
ALTER DATABASE tempdb MODIFY FILE (NAME = tempdev  , FILENAME = 'H:\tempdb.mdf'   , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat2 , FILENAME = 'H:\tempdat2.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat3 , FILENAME = 'H:\tempdat3.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat4 , FILENAME = 'H:\tempdat4.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat5 , FILENAME = 'H:\tempdat5.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat6 , FILENAME = 'H:\tempdat6.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat7 , FILENAME = 'H:\tempdat7.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat8 , FILENAME = 'H:\tempdat8.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
GO  
ALTER DATABASE tempdb MODIFY FILE (NAME = templog , FILENAME = 'I:\templog.ldf', SIZE =  512MB , FILEGROWTH = 100MB)  
GO  
--8b. Modify log file:  modify drive & instance name to reflect designated destination for tempdb log   
--!!md I:\MSSQL10.<instance>  
--!!md I:\MSSQL10.<instance>\MSSQL  
--!!md I:\MSSQL10.<instance>\MSSQL\DATA  
GO  
-- 9. Recycle SQL service in SQL Server Services node of sqlservermanager10.msc  
    --note, if running script from a UNC share, SSMS will report an error,   
      --but SQL Server Configuration Manager will open if its location is in %path%  
!!sqlservermanager10.msc  
  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
EXEC dbo.sp_helpdb tempdb  
--!!del C:\tempdb.mdf     
--!!del C:\templog.ldf  
GO  
  
```  
  
 <span data-ttu-id="4b30a-171">使用 SQL Server 2008 活动监视器或 SQL Server 2005 性能面板报告中所述[监视 SQL Server 性能](../technical-guides/monitoring-sql-server-performance.md)来标识闩锁争用问题。</span><span class="sxs-lookup"><span data-stu-id="4b30a-171">Use the SQL Server 2008 Activity Monitor or the SQL Server 2005 Performance Dashboard Reports described in [Monitoring SQL Server Performance](../technical-guides/monitoring-sql-server-performance.md) to identify problems with latch contention.</span></span>  
  
## <a name="manually-set-sql-server-process-affinity"></a><span data-ttu-id="4b30a-172">手动设置 SQL Server 进程关联</span><span class="sxs-lookup"><span data-stu-id="4b30a-172">Manually set SQL Server Process Affinity</span></span>  
 <span data-ttu-id="4b30a-173">进程关联选项可以提供在具有 16 个或多个 Cpu 的非 NUMA 计算机运行的高端的企业级 SQL Server 环境中的性能改进。</span><span class="sxs-lookup"><span data-stu-id="4b30a-173">The Process Affinity option can provide performance enhancements in high-end, enterprise-level SQL Server environments that are running on non-NUMA computers with 16 or more CPUs.</span></span> <span data-ttu-id="4b30a-174">这是在其中对 MessageBox 数据库中的共享表具有争用的高吞吐量 BizTalk 环境中尤其如此。</span><span class="sxs-lookup"><span data-stu-id="4b30a-174">This is especially true in high-throughput BizTalk environments where you have contention on shared tables in the MessageBox database.</span></span> <span data-ttu-id="4b30a-175">在我们的实验室环境中使用的 SQL Server 计算机未启用 NUMA 的并具有 16 个内核，以优化性能，因为我们使用以下命令来设置进程关联：</span><span class="sxs-lookup"><span data-stu-id="4b30a-175">Because the SQL Server computers that were used in our lab environment were not NUMA-enabled and had 16 cores, to optimize performance, we used the commands below to set process affinity:</span></span>  
  
 <span data-ttu-id="4b30a-176">**若要手动设置 SQL Server 进程关联从 0 到 15**</span><span class="sxs-lookup"><span data-stu-id="4b30a-176">**To manually set the SQL Server Process Affinity from 0 to 15**</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 <span data-ttu-id="4b30a-177">有关详细信息，请参阅[ALTER SERVER CONFIGURATION (TRANSACT-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-177">For more information, see [ALTER SERVER CONFIGURATION (Transact-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql).</span></span>
  
## <a name="configure-msdtc"></a><span data-ttu-id="4b30a-178">配置 MSDTC</span><span class="sxs-lookup"><span data-stu-id="4b30a-178">Configure MSDTC</span></span>  
 <span data-ttu-id="4b30a-179">若要简化 SQL Server 和 BizTalk Server 之间的事务，必须启用 Microsoft 分布式事务处理协调器 (MS DTC)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-179">To facilitate transactions between SQL Server and BizTalk Server, you must enable Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="4b30a-180">若要配置 SQL Server 上的 MSDTC，请参阅主题[提高操作系统性能的通用指南](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-180">To configure MSDTC on SQL Server, see the topic [General Guidelines for Improving Operating System Performance](../technical-guides/general-guidelines-for-improving-operating-system-performance.md).</span></span>  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a><span data-ttu-id="4b30a-181">启用跟踪标志 T1118 作为引导参数的所有实例的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b30a-181">Enable Trace Flag T1118 as a startup parameter for all instances of SQL Server</span></span>  
 <span data-ttu-id="4b30a-182">实现跟踪标志-T1118 可帮助减少 SQL Server 实例之间的争用，通过删除几乎所有的单页分配。</span><span class="sxs-lookup"><span data-stu-id="4b30a-182">Implementing Trace Flag –T1118 helps reduce contention across the SQL Server instances by removing almost all single page allocations.</span></span> <span data-ttu-id="4b30a-183">有关详细信息，请参阅[KB 328551:PRB:Tempdb 数据库的并发性增强功能](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-183">For more information, see [KB 328551: PRB: Concurrency enhancements for the tempdb database](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database).</span></span>
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a><span data-ttu-id="4b30a-184">不更改默认的最大并行度、 SQL Server 统计信息或数据库索引重新生成和碎片整理的 SQL Server 设置</span><span class="sxs-lookup"><span data-stu-id="4b30a-184">Do not change default SQL Server settings for max degree of parallelism, SQL Server statistics, or database index rebuilds and defragmentation</span></span>  
 <span data-ttu-id="4b30a-185">如果 SQL Server 实例将承载 BizTalk Server 数据库，则不应更改某些 SQL Server 设置。</span><span class="sxs-lookup"><span data-stu-id="4b30a-185">If a SQL Server instance will house BizTalk Server databases, then there are certain SQL Server settings that should not be changed.</span></span> <span data-ttu-id="4b30a-186">具体而言，SQL Server 最大并行度，MessageBox 数据库和数据库索引的设置的 SQL Server 统计信息重新生成，不应修改碎片整理。</span><span class="sxs-lookup"><span data-stu-id="4b30a-186">Specifically, the SQL Server max degree of parallelism, the SQL Server statistics on the MessageBox database, and the settings for the database index rebuilds and defragmentation should not be modified.</span></span> <span data-ttu-id="4b30a-187">请参阅[不应更改的 SQL Server 设置](../technical-guides/sql-server-settings-that-should-not-be-changed.md)。</span><span class="sxs-lookup"><span data-stu-id="4b30a-187">See [SQL Server Settings That Should Not Be Changed](../technical-guides/sql-server-settings-that-should-not-be-changed.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b30a-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b30a-188">See Also</span></span>  
 [<span data-ttu-id="4b30a-189">优化数据库性能</span><span class="sxs-lookup"><span data-stu-id="4b30a-189">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)
