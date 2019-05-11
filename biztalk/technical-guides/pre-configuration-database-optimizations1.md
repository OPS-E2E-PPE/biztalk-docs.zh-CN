---
title: 预配置数据库 Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebd0b32a-490d-4db2-a1fc-bf3bef93aeea
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30107d8cf3624e22099efb5d14daf59b4e256105
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399576"
---
# <a name="pre-configuration-database-optimizations"></a>预配置数据库优化
BizTalk Server 是非常占用大量数据库的应用程序可能要求的 Microsoft SQL Server 中最多 13 个单独的数据库创建的。 由于 SQL Server 在任何 BizTalk Server 环境中起着关键角色，它是极其重要，SQL Server 将配置/进行优化以获得最佳性能。 如果 SQL Server 不优化很好地运行，然后 BizTalk Server 使用的数据库将成为瓶颈，并在 BizTalk Server 环境的整体性能将会受到影响。 本主题介绍在安装 BizTalk Server 和配置 BizTalk Server 数据库之前应遵循的几个 SQL Server 性能优化。  
  
## <a name="set-ntfs-file-allocation-unit"></a>设置 NTFS 文件分配单元  
 SQL Server 将在其数据存储**区**，这是一组 8 8k 页。 因此，若要优化磁盘性能，设置 NTFS 分配单元大小为 64 KB 的最佳做法的文章"预部署 I/O 最佳实践"可在 SQL Server 的"磁盘配置最佳实践"部分中所述[ http://go.microsoft.com/fwlink/?LinkId=140818](http://go.microsoft.com/fwlink/?LinkId=140818). 有关 SQL Server 的详细信息页和区请参阅 SQL Server 联机丛书主题[了解页和区](http://go.microsoft.com/fwlink/?LinkId=148939)(超链接"<http://go.microsoft.com/fwlink/?LinkId=148939>" <http://go.microsoft.com/fwlink/?LinkId=148939>)。  
  
## <a name="database-planning-considerations"></a>数据库的规划注意事项  
 我们建议你托管在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]快速存储 （例如，快速 SAN 磁盘或快速 SCSI 磁盘） 上的数据库。 我们建议 RAID 10 (1 + 0) 而不是 RAID 5，因为 raid 5 是写入的速度要慢。 较新的 SAN 磁盘在这些情况下，就不那么重要 RAID 选择具有非常大的内存缓存。 若要提高性能，数据库和其日志文件可驻留在不同的物理磁盘。  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>安装适用于 SQL Server 最新 service pack 和累积更新  
 安装适用于 SQL Server 2005 和 SQL Server 2008，以及最新的.NET Framework service pack 的最新的 service pack 和最新的累积更新。  
  
## <a name="install-sql-service-packs-on-both-biztalk-server-and-sql-server"></a>在 BizTalk Server 和 SQL Server 上安装 SQL Service Pack  
 在安装 service pack 适用于 SQL Server 时，还在 BizTalk Server 计算机上安装 service pack。 BizTalk Server 使用更新的 SQL Server service pack 的 SQL 客户端组件。  
  
## <a name="consider-implementing-the-sql-server-2008-data-collector-and-management-data-warehouse"></a>请考虑实施 SQL Server 2008 数据收集器和管理数据仓库  
 SQL Server 2008 可使用新数据收集器和管理数据仓库收集环境/数据库性能相关的数据以进行测试和趋势分析。 数据收集器收集的所有数据保存到指定的管理数据仓库。 尽管这不是一种性能优化，这会十分有用的任何性能问题的分析。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>授予用于 SQL Server Windows 锁定页内存特权的帐户  
 授予 Windows"锁定内存页"特权到 SQL Server 服务帐户。 这应进行以锁定用于在物理内存中缓冲池分配的内存将 Windows 操作系统防止出 SQL Server 进程的缓冲池内存的分页。 详细信息，请参阅 Microsoft 知识库文章 914483"如何减少分页缓冲池内存中的 SQL Server 2005 的 64 位版本的"在[ http://go.microsoft.com/fwlink/?LinkId=148948 ](http://go.microsoft.com/fwlink/?LinkId=148948)。  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>授予 SQL Server 服务帐户从右到 SE_MANAGE_VOLUME_NAME  
 确保运行 SQL Server 服务帐户具有"执行卷维护任务"Windows 权限，或确保其所属的安全组，这会执行。 这样，确保获得最佳性能，如果数据库必须自动增长的即时文件初始化。  
  
## <a name="set-min-and-max-server-memory"></a>设置最小值和最大服务器内存  
 运行的计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应将 BizTalk Server 数据库专用于运行 SQL Server 的主机。 我们建议的"最小服务器内存"和每个 SQL Server 实例上的"最大服务器内存"选项设置为指定的固定要分配给 SQL Server 的内存量。 在这种情况下，您应将"min server memory"和"最大服务器内存"为相同的值 （设置为最大的 SQL Server 将使用的物理内存量）。 这将减少开销，否则将使用 SQL server 动态地管理这些值。 若要指定要分配到 SQL Server 的内存量固定每个 SQL Server 计算机上运行以下 T-SQL 命令：  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 为 SQL Server 设置的内存量之前，请通过减去总物理内存中适用于 Windows Server 所需的内存来确定适当的内存设置。 这是内存的最大可以为 SQL Server 分配量。  
  
> [!NOTE]  
>  如果运行该主机的 SQL Server 的计算机的 BizTalk Server 数据库还承载了企业单一登录主密钥服务器，然后您可能需要调整此值可确保有足够的内存可用于运行企业单一登录服务。 它不提供对主密钥服务器高可用性的 SQL Server 群集上运行企业单一登录服务的群集的实例不常见的做法。 有关群集企业单一登录主密钥服务器的详细信息，请参阅主题"如何为群集主密钥服务器"中在 BizTalk Serverdocumentation [ http://go.microsoft.com/fwlink/?LinkID=106874 ](http://go.microsoft.com/fwlink/?LinkID=106874)。  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件  
 确保使用的 tempdb 数据文件大小相等的非常重要，因为使用的按比例填充算法[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]取决于数据文件的大小。 此算法将尝试确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]成比例的可用空间的每个文件保持在该文件，以便达到了解同一时间在其最大容量的填充。 如果使用不相等大小创建数据文件，按比例填充算法将使用为 GAM 分配，而不是所有的文件，这违背创建多个数据文件的目的之间进行分配更多的最大文件。 Tempdb 数据库数据文件数应配置为至少等于分配适用于 SQL Server 的处理器数。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>启用跟踪标志 T1118 作为引导参数的所有实例的 SQL Server  
 实现跟踪标志-T1118 可帮助减少 SQL Server 实例之间的争用，通过删除几乎所有的单页分配。 有关详细信息，请参阅 Microsoft 知识库文章 328551"PRB:并发的增强功能，tempdb 数据库"处[ http://go.microsoft.com/fwlink/?LinkID=103713 ](http://go.microsoft.com/fwlink/?LinkID=103713)。  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>不更改默认的最大并行度、 SQL Server 统计信息或数据库索引重新生成和碎片整理的 SQL Server 设置  
 如果 SQL Server 实例将承载 BizTalk Server 数据库，则某些 SQL Server 设置应不会更改。 具体而言，SQL Server 最大并行度，MessageBox 数据库和数据库索引的设置的 SQL Server 统计信息重新生成，不应修改碎片整理。 有关详细信息，请在 BizTalk Server 操作指南 》 中参阅"SQL Server 设置，不应更改"主题[ http://go.microsoft.com/fwlink/?LinkId=114358 ](http://go.microsoft.com/fwlink/?LinkId=114358)。