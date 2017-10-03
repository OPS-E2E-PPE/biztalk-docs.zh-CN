---
title: "预配置数据库 Optimizations2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c525c3a-249c-4694-b287-a8c35a6aa524
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd8bb0ba839d656dd99959a3352ea8da42457d16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="pre-configuration-database-optimizations"></a>预配置数据库优化
由于 SQL Server 在任何 BizTalk Server 环境中所扮演的重要角色，它是一项极其重要 SQL Server 能为了获得最佳性能配置/优化问题。 如果 SQL Server 不优化很好地运行，然后使用 BizTalk Server 的数据库将成为瓶颈和 BizTalk Server 环境的整体性能将会降低。 本主题介绍在安装 BizTalk Server 并配置 BizTalk Server 数据库之前，应遵循的几个 SQL Server 性能优化。  
  
## <a name="set-ntfs-file-allocation-unit"></a>设置 NTFS 文件分配单元  
 SQL Server 将在其数据存储**扩展盘区**，这是八个物理上连续的 8k 页或 64 KB 的集合。 因此，若要优化磁盘性能，NTFS 分配单元大小设置为 64 KB SQL Server 最佳做法文章的"磁盘配置最佳做法"部分中所述["预部署 I/O 最佳实践"](http://go.microsoft.com/fwlink/?LinkId=140818) (http://go.microsoft.com/fwlink/？LinkId = 140818)。  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a>版本和版本的 SQL Server 的注意事项  
 各种版本和版本的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]提供可能会影响的性能的不同功能你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 例如，在高负载情况下，可用于的 32 位版本的数据库锁的数目[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可能超过了，这是对 BizTalk 解决方案的性能造成不利影响。 请考虑存放在 64 位版本的 SQL Server 上你 MessageBox 的数据库，如果你在测试环境中遇到"超出锁"错误。 在 64 位版本的 SQL Server 上，可用锁定的数目将大大增加。  
  
 在决定将需要为您的 BizTalk 环境的数据库引擎功能，请考虑下表。 对于大比例，需要群集的企业级解决方案支持，BizTalk Server 日志传送支持，或 Analysis Services 支持，则你将需要[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]或[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]Enterprise 版本到内部[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。  
  
|版本和版本的 SQL Server|64 位支持|多实例支持|群集的支持|Analysis Services|  
|---------------------------------------|---------------------|-----------------------------|------------------------|-----------------------|  
|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Enterprise Edition|是|是 (50)|是|是|  
|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 标准版|是|是 (16)|是 （2 个节点）|是|  
|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Workgroup Edition|是|是 (16)|是|是|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] Enterprise Edition|是|是|是|是|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] 标准版|是|是|是 （2 个节点）|是|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]Workgroup Edition|是|是|“否”|是|  
  
 有关的各个版本支持的功能的完整列表[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]，请参阅[支持的版本的 SQL Server 2008 R2 功能](http://go.microsoft.com/fwlink/?LinkId=140465)(http://go.microsoft.com/fwlink/?LinkId=140465) 中[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]文档。  
  
## <a name="database-planning-considerations"></a>数据库的规划注意事项  
 我们建议你托管位于快速存储 （例如，快速 SAN 磁盘或快速 SCSI 磁盘） 上的 SQL Server 数据库。 由于 raid 5 是写入速度要慢，我们建议 RAID 10 (1 + 0) 而不是 RAID 5。 较新的 SAN 磁盘具有非常大的内存缓存，因此在这些情况下 raid 选择项不一样重要。 若要提高性能，数据库和其日志文件可以位于不同的物理磁盘。  
  
 此外请考虑优化主机总线适配器 (HBA) 队列深度，如果使用存储区域网络 (SAN)。 这可能会显著影响 I/O 吞吐量和扩展的框值可以是不足以 SQL Server。 测试是必需的来确定最佳值，但队列深度为 64 通常被认为的良好开端中不存在的任何特定的供应商建议  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>为 SQL Server 安装的最新 service pack 和累积更新  
 安装最新的 service pack 和为最新累积更新[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]以及最新的.NET Framework service pack。  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a>在 BizTalk Server 和 SQL Server 上安装 SQL Service Pack 和累积更新  
 安装 SQL Server 时的 service pack 或累积更新，还在 BizTalk Server 计算机上安装的 service pack 或累积更新。 BizTalk Server 使用的 SQL Server service pack 和累积更新查询更新的 SQL 客户端组件。  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a>请考虑使用快速固态驱动器 (SSD) 来承载 SQL Server tembdb  
 请考虑使用一个或多个实体状态磁盘 (SSD) 驱动器以容纳 TempDB。 SSD 驱动器提供比传统硬盘的显著的性能优点，并在进入主流市场快速删除在价格。 因为 TempDB 性能通常是整体的关键因素[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能、 增加的驱动器的初始成本将通常要快速而得到了弥补通过整体增加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能，尤其在运行企业应用程序为其[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能非常重要。  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a>请考虑实施的 SQL Server 2008 R2 数据收集器和管理数据仓库  
 SQL Server 2008 R2 还包含新的使用数据收集器和管理数据仓库收集环境/数据库性能相关的数据以进行测试和趋势分析。 数据收集器保持到指定的管理数据仓库收集的所有数据。 尽管这不是一种性能优化这将是可用于分析的任何性能问题。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>授予用于针对 SQL Server Windows 锁定页内存特权的帐户  
 授予内存特权仅授予对 SQL Server 服务帐户中的 Windows 锁定页。 这应为了防止出 SQL Server 进程的缓冲池内存分页 Windows 操作系统通过锁定在物理内存中缓冲池分配的内存。  
  
 在实验室环境中，Windows 策略**锁定内存页**选项已按默认启用。 有关如何启用**锁定内存页**选项，请参阅[如何： 启用内存选项 (Windows) 中的锁定页](http://go.microsoft.com/fwlink/?LinkID=208267)(http://go.microsoft.com/fwlink/?LinkID=208267)。  
  
> [!IMPORTANT]  
>  在 Windows 中锁定页面内存权限授予 SQL Server 服务帐户受到某些限制。 请参阅以下 Microsoft 知识库文章有关详细信息：  
>   
>  -   [918483，"如何减少的 64 位版本的 SQL Server 2005 的缓冲池内存分页"](http://go.microsoft.com/fwlink/?LinkID=148948) (http://go.microsoft.com/fwlink/?LinkID=148948)。  
> -   [970070，"支持已锁定页在 SQL Server 2005 Standard Edition 64 位系统上并且在 SQL Server 2008 Standard Edition 64 位系统上的"](http://go.microsoft.com/fwlink/?LinkId=160474) (http://go.microsoft.com/fwlink/?LinkId=160474)。  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>权限将 SE_MANAGE_VOLUME_NAME 授予 SQL Server 服务帐户  
 确保运行 SQL Server 服务的帐户具有执行卷维护任务 Windows 特权，或确保它所属的组。 如果数据库必须自动增长，这将允许即时文件初始化确保最佳性能。  
  
## <a name="set-min-and-max-server-memory"></a>设置最小值和最大服务器内存  
 运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库应将专用于运行 SQL Server。 当运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库专用于运行 SQL Server 中时，我们建议的 min server memory 和最大服务器内存选项卡上的每个 SQL Server 实例设置为指定的固定到的内存量分配给 SQL Server。 在这种情况下，应将设置为"min server memory"和"最大服务器内存"为相同的值 （等于最大的 SQL Server 将使用的物理内存量）。 这将减少开销，否则将使用 SQL server 动态地管理这些值。 在运行 SQL Server 以指定要分配给 SQL Server 的内存固定的量每台计算机上运行以下 T-SQL 命令：  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 为 SQL Server 设置的内存量之前，请通过减去所需的总物理内存从 Windows Server 的内存确定适当的内存设置。 这是内存的最大可以为 SQL Server 分配量。  
  
> [!NOTE]  
>  如果运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库也承载企业单一登录在主密钥服务器，然后你可能需要调整此值，以确保有足够的内存可用于运行 Enterprise 上单一登录服务。 它不是一种常见的做法，在 SQL Server 群集，以便提供高可用性的主密钥服务器上运行企业单一登录服务的群集的实例。 有关群集企业单一登录在主密钥服务器的详细信息，请参阅主题[如何安装群集主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=158251)(http://go.microsoft.com/fwlink/?LinkId=158251) BizTalk Server 文档中。  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件  
 确保用于 tempdb 数据文件为相等的大小很关键，因为 SQL Server 使用的按比例填充算法根据数据文件的大小。 如果数据文件创建不相等的大小，按比例填充算法将使用多个 GAM 分配，而无需分配所有的文件，从而与将创建多个数据文件的目的之间分配的最大文件。 Tempdb 数据文件的最佳数量取决于在 tempdb 中看到的闩锁争用的程度。 作为一个常规的经验法则，数据文件数应小于或等于其中的 Cpu 数是 8 的处理器内核/Cpu 数。 对于有 8 个以上的 Cpu 的服务器，请为一半数目的 Cpu 创建数据文件 （同样，只有你拥有闩锁争用）。  
  
 在我们实验室环境中，我们将使用下面的脚本来创建 8 TempDB 数据文件，其中每个所包含的文件大小为 100 MB 增长 1024 MB 和 100 MB 增长 512 MB 的日志文件。 数据文件移至驱动器 h： 和日志文件移至驱动器 i:。  
  
> [!IMPORTANT]  
>  此脚本是提供的"按原样，"旨在演示或教学目的，，要使用您自己承担。 使用此脚本不支持由 Microsoft 和 Microsoft 则没有此脚本的适用性的保证。  
  
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
  
 使用 SQL Server 2008 活动监视器或 SQL Server 2005 性能面板报告中所述[监视 SQL Server 性能](../technical-guides/monitoring-sql-server-performance.md)来标识闩锁争用问题。  
  
## <a name="manually-set-sql-server-process-affinity"></a>手动设置 SQL Server 进程关联  
 Process Affinity 选项可以提供高端的企业级在有 16 个或多个 Cpu 的非 NUMA 计算机运行的 SQL Server 环境中的性能增强功能。 这是在其中具有 MessageBox 数据库中的共享表的争用的高吞吐量 BizTalk 环境中尤其如此。 在本实验室环境中使用的 SQL Server 计算机未启用 NUMA 的且必须 16 核，以优化性能，因为我们使用以下命令设置进程关联：  
  
 **若要手动设置 SQL Server Process Affinity 从 0 到 15**  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 有关详细信息，请参阅[ALTER SERVER CONFIGURATION (TRANSACT-SQL)](http://go.microsoft.com/fwlink/?LinkID=208269) (http://go.microsoft.com/fwlink/?LinkID=208269)。  
  
## <a name="configure-msdtc"></a>配置 MSDTC  
 若要简化 SQL Server 和 BizTalk Server 之间的事务，必须启用 Microsoft 分布式事务处理协调器 (MS DTC)。 若要配置 SQL Server 上的 MSDTC，请参阅主题[提高操作系统性能的一般准则](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>启用跟踪标志 T1118 作为引导参数的 SQL Server 的所有实例  
 实现跟踪标志-T1118 可帮助减少争用跨 SQL Server 实例删除几乎所有的单页分配。 有关详细信息，请参阅 Microsoft 知识库文章[328551，"PRB： 并发增强功能的 tempdb 数据库"](http://go.microsoft.com/fwlink/?LinkID=153694) (http://go.microsoft.com/fwlink/?LinkID=153694)。  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>不更改默认的最大并行度、 SQL Server 统计信息或数据库索引重新生成和碎片整理度的 SQL Server 设置  
 如果 SQL Server 实例将承载 BizTalk Server 数据库，则不应更改某些 SQL Server 设置。 具体而言，SQL Server 最大并行度，MessageBox 数据库和数据库索引的设置的 SQL Server 统计信息将重新生成并不应修改碎片整理。 有关详细信息，请参阅主题[SQL Server 设置，不应更改](http://go.microsoft.com/fwlink/?LinkId=160068)(http://go.microsoft.com/fwlink/?LinkId=160068) BizTalk Server 2010 操作指南中。  
  
## <a name="see-also"></a>另请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)