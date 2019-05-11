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
# <a name="pre-configuration-database-optimizations"></a>预配置数据库优化
由于 SQL Server 在任何 BizTalk Server 环境中起着关键角色，它是一项极其重要 SQL 服务器进行配置/优化以获得最佳性能问题。 如果 SQL Server 不优化很好地运行，然后 BizTalk Server 使用的数据库将成为瓶颈，并在 BizTalk Server 环境的整体性能将会受到影响。 本主题介绍在安装 BizTalk Server 和配置 BizTalk Server 数据库之前应遵循的几个 SQL Server 性能优化。  
  
## <a name="set-ntfs-file-allocation-unit"></a>设置 NTFS 文件分配单元  
 SQL Server 将在其数据存储**区**，这是八个物理上连续的 8k 页，即 64 KB 的集合。 因此，若要优化磁盘性能，将设置为 64 KB NTFS 分配单元大小"磁盘配置最佳实践"中所述在[预部署 I/O 最佳实践](https://msdn.microsoft.com/library/cc966412.aspx)。  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a>有关版本和版本的 SQL Server 的注意事项  
 各种版本和版本的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]提供了会影响性能的不同功能在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 例如，在高负载情况下，可用于 32 位版本的数据库锁的数目[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可能超过了，这是对 BizTalk 解决方案的性能造成不利影响。 请考虑保存 MessageBox 数据库上的 SQL Server 的 64 位版本，如果您在测试环境中遇到"内存不足"错误。 可用锁的数目是 64 位版本的 SQL Server 上高得多。  
  
 确定所需的 BizTalk 环境的数据库引擎功能时，请考虑下表。 对于大量的、 需要聚类分析的企业级解决方案支持，BizTalk Server 日志传送的支持，或 Analysis Services 支持，则需要 SQL Server Enterprise Edition 主机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。   

 SQL Server 各个版本支持的功能的完整列表，请参阅[SQL Server 版本和支持的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)。
  
## <a name="database-planning-considerations"></a>数据库的规划注意事项  
 我们建议你托管 SQL Server 数据库上快速存储 （例如，快速 SAN 磁盘或快速 SCSI 磁盘）。 我们建议使用 RAID 10 (1 + 0) 而不是 RAID 5 因为 raid 5 是写入的速度要慢。 较新的 SAN 磁盘具有非常大的内存缓存，因此在这些情况下选择的 raid 并不那么重要。 若要提高性能，数据库和其日志文件可驻留在不同的物理磁盘。  
  
 此外请考虑如果使用的存储区域网络 (SAN) 进行优化的主机总线适配器 (HBA) 队列深度。 这可能会显著影响 I/O 吞吐量和扩展的框值可以是 SQL Server 的不足。 测试是必需的来确定最佳值，但队列深度为 64 通常被认为最好先在缺少的任何特定供应商建议  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>安装适用于 SQL Server 最新 service pack 和累积更新  
 安装适用于 SQL Server，以及最新的.NET Framework service pack 的最新的 service pack 和最新的累积更新。  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a>在 BizTalk Server 和 SQL Server 上安装 SQL Service Pack 和累积更新  
 当安装 SQL Server service pack 或累积更新，还在 BizTalk Server 计算机上安装 service pack 或累积更新。 BizTalk Server 使用更新的 SQL Server service pack 和累积更新的 SQL 客户端组件。  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a>请考虑使用快速固态硬盘 (SSD) 来存放 SQL Server tembdb  
 请考虑使用一个或多个固态磁盘 (SSD) 驱动器来存放 TempDB。 SSD 驱动器提供显著的性能优于传统硬盘驱动器，并在进入主流市场快速删除价格中。 因为 TempDB 的性能通常是整体的关键因素[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能，添加了的驱动器的初始成本将通常会快速得到了补偿的整体增加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能，尤其在运行企业应用程序为其[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能至关重要。  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a>请考虑实施 SQL Server 2008 R2 数据收集器和管理数据仓库  
 SQL Server 2008 R2 可使用新数据收集器和管理数据仓库收集环境/数据库性能相关的数据以进行测试和趋势分析。 数据收集器收集的所有数据保存到指定的管理数据仓库。 尽管这不是一种性能优化这会十分有用的任何性能问题的分析。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>授予用于 SQL Server Windows 锁定页内存特权的帐户  
 授予内存特权仅授予对 SQL Server 服务帐户中的 Windows 锁定页。 这应进行以锁定用于在物理内存中缓冲池分配的内存将 Windows 操作系统防止出 SQL Server 进程的缓冲池内存的分页。  
  
 在我们的实验室环境，Windows 策略**锁定内存页**选项默认情况下已启用。 请参阅[启用锁定页中内存选项](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)。  
  
> [!IMPORTANT]  
>  授予 Windows 锁定页内存权限中的 SQL Server 服务帐户时受到某些限制。 请参阅以下内容： 
>   
> - [缓冲池扩展](https://docs.microsoft.com/sql/database-engine/configure-windows/buffer-pool-extension)  
> - [启用锁定页中内存选项 ](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>权限将 SE_MANAGE_VOLUME_NAME 授予 SQL Server 服务帐户  
 确保运行 SQL Server 服务帐户具有执行卷维护任务 Windows 权限，或确保其所属的组。 如果数据库必须自动增长，这将允许即时文件初始化确保获得最佳性能。  
  
## <a name="set-min-and-max-server-memory"></a>设置最小值和最大服务器内存  
 运行该主机的 SQL Server 的计算机应将 BizTalk Server 数据库专用于运行 SQL Server。 当运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库专用于运行 SQL Server 中时，我们建议的最小服务器内存和每个 SQL Server 实例上的最大服务器内存选项设置为指定的固定的内存量将分配给 SQL Server。 在这种情况下，您应将"min server memory"和"最大服务器内存"为相同的值 （设置为最大的 SQL Server 将使用的物理内存量）。 这将减少开销，否则将使用 SQL server 动态地管理这些值。 运行 SQL Server 以指定要分配到 SQL Server 的内存量固定每台计算机上运行以下 T-SQL 命令：  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 为 SQL Server 设置的内存量之前，请通过减去总物理内存中适用于 Windows Server 所需的内存来确定适当的内存设置。 这是内存的最大可以为 SQL Server 分配量。  
  
> [!NOTE]  
>  如果运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库还承载了企业单一登录主密钥服务器，然后您可能需要调整此值可确保有足够的内存可用于运行企业单一登录服务。 它不提供对主密钥服务器高可用性的 SQL Server 群集上运行企业单一登录服务的群集的实例不常见的做法。 请参阅[聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件  
 确保使用的 tempdb 数据文件大小相等的很关键，因为 SQL Server 使用的按比例填充算法基于数据文件的大小。 如果使用不相等大小创建数据文件，按比例填充算法将使用为 GAM 分配，而不是所有的文件，这违背创建多个数据文件的目的之间进行分配更多的最大文件。 Tempdb 数据文件的最佳数量取决于在 tempdb 中看到的闩锁争用的程度。 作为常规经验，数据文件数应小于或等于其中的 Cpu 数是 8 的处理器内核/Cpu 数。 对于超过 8 个 Cpu 的服务器，创建数据文件的一半数目的 Cpu （同样，您只有闩锁争用）。  
  
 在我们的实验室环境，我们使用下面的脚本创建 8 TempDB 数据文件，其中每个所包含的文件大小为 1024 MB，增长 100 MB 具有和 512 MB 的日志文件，增长 100 MB。 数据文件移到 h： 驱动器和日志文件移到 i： 驱动器。  
  
> [!IMPORTANT]  
>  提供"按原样，"用于演示或培训目的，并且将使用您自己承担，此脚本。 使用此脚本不受 Microsoft，因此 Microsoft 不保证此脚本的适用性。  
  
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
 进程关联选项可以提供在具有 16 个或多个 Cpu 的非 NUMA 计算机运行的高端的企业级 SQL Server 环境中的性能改进。 这是在其中对 MessageBox 数据库中的共享表具有争用的高吞吐量 BizTalk 环境中尤其如此。 在我们的实验室环境中使用的 SQL Server 计算机未启用 NUMA 的并具有 16 个内核，以优化性能，因为我们使用以下命令来设置进程关联：  
  
 **若要手动设置 SQL Server 进程关联从 0 到 15**  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 有关详细信息，请参阅[ALTER SERVER CONFIGURATION (TRANSACT-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql)。
  
## <a name="configure-msdtc"></a>配置 MSDTC  
 若要简化 SQL Server 和 BizTalk Server 之间的事务，必须启用 Microsoft 分布式事务处理协调器 (MS DTC)。 若要配置 SQL Server 上的 MSDTC，请参阅主题[提高操作系统性能的通用指南](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>启用跟踪标志 T1118 作为引导参数的所有实例的 SQL Server  
 实现跟踪标志-T1118 可帮助减少 SQL Server 实例之间的争用，通过删除几乎所有的单页分配。 有关详细信息，请参阅[KB 328551:PRB:Tempdb 数据库的并发性增强功能](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database)。
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>不更改默认的最大并行度、 SQL Server 统计信息或数据库索引重新生成和碎片整理的 SQL Server 设置  
 如果 SQL Server 实例将承载 BizTalk Server 数据库，则不应更改某些 SQL Server 设置。 具体而言，SQL Server 最大并行度，MessageBox 数据库和数据库索引的设置的 SQL Server 统计信息重新生成，不应修改碎片整理。 请参阅[不应更改的 SQL Server 设置](../technical-guides/sql-server-settings-that-should-not-be-changed.md)。
  
## <a name="see-also"></a>请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)
