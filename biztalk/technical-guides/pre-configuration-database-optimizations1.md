---
title: "预配置数据库 Optimizations1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebd0b32a-490d-4db2-a1fc-bf3bef93aeea
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1333f956afc4411ff8b105c777214467155ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="pre-configuration-database-optimizations"></a>预配置数据库优化
BizTalk Server 是极占用大量数据库的应用程序可能需要在创建 Microsoft SQL Server 中的最多 13 单独数据库。 由于 SQL Server 在任何 BizTalk Server 环境中所扮演的重要角色，它是一项极其重要，SQL Server 配置/优化以获得最佳性能。 如果 SQL Server 不优化很好地运行，然后使用 BizTalk Server 的数据库将成为瓶颈和 BizTalk Server 环境的整体性能将会降低。 本主题介绍在安装 BizTalk Server 并配置 BizTalk Server 数据库之前，应遵循的几个 SQL Server 性能优化。  
  
## <a name="set-ntfs-file-allocation-unit"></a>设置 NTFS 文件分配单元  
 SQL Server 将在其数据存储**扩展盘区**，这是组的八个 8k 页。 因此，若要优化磁盘性能，NTFS 分配单元大小设置为 64 KB 最佳做法文章预部署 I/O 最佳实践"在 SQL Server 的"磁盘配置最佳做法"部分中所述[http://go.microsoft.com/fwlink/？LinkId = 140818](http://go.microsoft.com/fwlink/?LinkId=140818)。 有关 SQL Server 页和区的详细信息请参阅[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]联机丛书主题[了解页和区](http://go.microsoft.com/fwlink/?LinkId=148939)(超链接"http://go.microsoft.com/fwlink/?LinkId=148939"http://go.microsoft.com/fwlink/?LinkId=148939)。  
  
## <a name="database-planning-considerations"></a>数据库的规划注意事项  
 我们建议你托管你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]快速存储 （例如，快速 SAN 磁盘或快速 SCSI 磁盘） 上的数据库。 我们建议而不是 RAID 5 RAID 10 (1 + 0)，因为 raid 5 是写入速度要慢。 较新的 SAN 磁盘具有非常大的内存缓存，在这些情况下，RAID 选择不是那么重要。 若要提高性能，数据库和其日志文件可以位于不同的物理磁盘。  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>为 SQL Server 安装的最新 service pack 和累积更新  
 为 SQL Server 2005 和 SQL Server 2008，以及最新的.NET Framework service pack 安装最新的 service pack 和最新的累积更新。  
  
## <a name="install-sql-service-packs-on-both-biztalk-server-and-sql-server"></a>在 BizTalk Server 和 SQL Server 上安装 SQL Service Pack  
 安装时 SQL Server service pack，还在 BizTalk Server 计算机上安装 service pack。 BizTalk Server 使用的 SQL Server service pack 更新的 SQL 客户端组件。  
  
## <a name="consider-implementing-the-sql-server-2008-data-collector-and-management-data-warehouse"></a>请考虑实施的 SQL Server 2008 数据收集器和管理数据仓库  
 SQL Server 2008 还包含新的使用数据收集器和管理数据仓库收集环境/数据库性能相关的数据以进行测试和趋势分析。 数据收集器保持到指定的管理数据仓库收集的所有数据。 虽然这不是一种性能优化，这将是可用于分析的任何性能问题。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>授予用于针对 SQL Server Windows 锁定页内存特权的帐户  
 授予 Windows"锁定内存页"权限的 SQL Server 服务帐户。 这应为了防止出 SQL Server 进程的缓冲池内存分页 Windows 操作系统通过锁定在物理内存中缓冲池分配的内存。 有关详细信息，请在参阅 Microsoft 知识库文章 914483"如何减少的 64 位版本的 SQL Server 2005 的缓冲池内存分页" [http://go.microsoft.com/fwlink/?LinkId=148948](http://go.microsoft.com/fwlink/?LinkId=148948)。  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>授予 SQL Server 服务帐户从右到 SE_MANAGE_VOLUME_NAME  
 确保运行 SQL Server 服务的帐户具有"执行卷维护任务"Windows 特权，或确保它属于安全组的作用。 这将允许确保最佳性能，如果数据库必须自动增长的即时文件初始化。  
  
## <a name="set-min-and-max-server-memory"></a>设置最小值和最大服务器内存  
 运行的计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应将专用于运行 SQL Server 的 BizTalk Server 数据库，将该主机。 我们建议的"min server memory"和"最大服务器内存"选项卡上的每个 SQL Server 实例设置为指定的固定要分配给 SQL Server 的内存量。 在这种情况下，应将设置为"min server memory"和"最大服务器内存"为相同的值 （等于最大的 SQL Server 将使用的物理内存量）。 这将减少开销，否则将使用 SQL server 动态地管理这些值。 若要指定要分配给 SQL Server 的内存固定的量每个 SQL Server 计算机上运行以下 T-SQL 命令：  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 为 SQL Server 设置的内存量之前，请通过减去所需的总物理内存从 Windows Server 的内存确定适当的内存设置。 这是内存的最大可以为 SQL Server 分配量。  
  
> [!NOTE]  
>  如果该主机在运行 SQL Server 的计算机的 BizTalk Server 数据库也承载企业单一登录在主密钥服务器，然后你可能需要调整此值，以确保有足够的内存可用于运行 Enterprise 上单一登录服务。 它不是一种常见的做法，在 SQL Server 群集，以便提供高可用性的主密钥服务器上运行企业单一登录服务的群集的实例。 有关群集企业单一登录在主密钥服务器的详细信息，请参阅主题"如何群集主机密服务器"中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]文档[http://go.microsoft.com/fwlink/?LinkID=106874](http://go.microsoft.com/fwlink/?LinkID=106874)。  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件  
 确保用于 tempdb 数据文件为相等的大小非常重要，因为按比例填充算法使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]取决于数据文件的大小。 此算法将尝试确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]与成比例的可用空间的每个文件保留在该文件，以便到达几乎同时在其最大容量的填充。 如果数据文件创建不相等的大小，按比例填充算法将使用多个 GAM 分配，而无需分配所有的文件，从而与将创建多个数据文件的目的之间分配的最大文件。 Tempdb 数据库的数据文件数应配置为至少等于分配给 SQL Server 的处理器数。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>启用跟踪标志 T1118 作为引导参数的 SQL Server 的所有实例  
 实现跟踪标志-T1118 可帮助减少争用跨 SQL Server 实例删除几乎所有的单页分配。 有关详细信息，请参阅 Microsoft 知识库文章 328551"PRB： 并发增强功能 tempdb 数据库的"在[http://go.microsoft.com/fwlink/?LinkID=103713](http://go.microsoft.com/fwlink/?LinkID=103713)。  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>不更改默认的最大并行度、 SQL Server 统计信息或数据库索引重新生成和碎片整理度的 SQL Server 设置  
 如果 SQL Server 实例将承载 BizTalk Server 数据库，则某些 SQL Server 设置应不会更改。 具体而言，SQL Server 最大并行度，MessageBox 数据库和数据库索引的设置的 SQL Server 统计信息将重新生成并不应修改碎片整理。 详细信息，请参阅主题"SQL Server 设置，不应更改"在 BizTalk Server 操作指南中[http://go.microsoft.com/fwlink/?LinkId=114358](http://go.microsoft.com/fwlink/?LinkId=114358)。