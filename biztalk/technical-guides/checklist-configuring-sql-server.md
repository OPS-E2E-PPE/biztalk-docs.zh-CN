---
title: 清单：配置 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: edd20f24-8a72-40b7-abee-81fbd3ceefda
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11ddb15c9086d8aeadf65da399a99598ae91a895
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291457"
---
# <a name="checklist-configuring-sql-server"></a>清单：配置 SQL Server
要执行准备为 SQL Server 时的步骤使用在 BizTalk Server 生产环境中。    
 
<a name="BKMK_Config"></a>   
## <a name="configuring-sql-server"></a>配置 SQL Server  
  
|步骤|参考|  
|-----------|---------------|  
|监视和减少 BizTalk Server 数据库文件磁盘 I/O 争用。|-我们建议你主动监视存放的数据和事务日志文件的磁盘的磁盘 I/O 使用情况。<br />-我们建议，数据文件和事务日志文件的每个将置于专门的驱动器来减少磁盘 I/O 争用成为问题的可能性。<br />-你可以减少磁盘 I/O 争用，通过将 MessageBox 和跟踪 (DTA) 的数据库，并通过分离数据库文件和事务日志文件在不同的物理磁盘上。<br /><br /> 有关详细信息，请参阅[监视和降低数据库 IO 争用](monitoring-and-reducing-database-i-o-contention.md)|  
|请确保正确地对齐磁盘分区上配置 SQL Server|正确地对齐的磁盘分区可能会导致延迟，从而改进 SQL Server 性能，又可以提高 BizTalk Server 性能显著降低。 相反，非对齐的磁盘分区产生负面影响 I/O 性能，从而降低 SQL Server 和 BizTalk Server 性能。<br /><br /> 有关如何正确对齐磁盘分区的详细信息时可能会影响性能，请参阅[磁盘分区对齐方式适用于 SQL Server 的最佳做法](http://go.microsoft.com/fwlink/?LinkId=154073)。|  
|保留您使用 SQL Server Profiler 来监视的事件|使用 SQL Server Profiler 来监视感兴趣的事件。 如果跟踪变得太大，可以筛选它们基于所需的信息，以便收集事件数据的一个子集。 监视过多事件会增加服务器和监视进程的开销，并且可能导致跟踪文件或跟踪表变得很大，尤其是当监视进程持续很长时间时。|  
|监视和降低 DTC 日志文件磁盘 I/O 争用。|[监视和降低 DTC 日志文件磁盘 IO 争用](monitoring-and-reducing-dtc-log-file-disk-i-o-contention.md)|  
|为 SQL Server 数据库提供高可用性。|[规划数据库可用性](planning-for-database-availability.md)|  
|查看故障转移方案的主动/主动 SQL Server 群集配置。|[查看和测试故障转移方案的 SQL Server 群集配置](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|使用默认配置设置：<br /><br /> -最大并行度 (MDOP)。<br />的在 BizTalk Server MessageBox 数据库上 SQL Server 统计信息。<br />-SQL Server 数据库索引重新生成和碎片整理。|[不可更改的 SQL Server 设置](sql-server-settings-that-should-not-be-changed.md)|  
|启用跟踪标志 1118 (TF1118) 作为启动参数的 SQL Server 的所有实例。|实现 TF1118 有助于减少 SQL Server 实例之间的争用，通过删除几乎所有的单页分配。 有关详细信息，请参阅 Microsoft 知识库文章[tempdb 数据库的并发性增强功能](https://support.microsoft.com/en-us/help/328551/concurrency-enhancements-for-the-tempdb-database)。 <br/><br/>**注意：** 有关 TF1118 的详细信息请参阅[围绕 TF1118 误解](https://www.sqlskills.com/blogs/paul/misconceptions-around-tf-1118/)。 请注意，此链接中的内容不由 Microsoft 拥有，Microsoft 不保证内容的准确性。|  
|将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件。|确保使用的 tempdb 数据文件大小相等。 这是关键，因为 SQL Server 使用的按比例填充算法基于数据文件的大小。 如果使用不相等大小创建数据文件，按比例填充算法将使用更多全局分配映射 (GAM) 分配，而不是所有的文件，从而达到监控目的创建多个之间进行分配的最大文件数据文件。 一般原则是，为每个 CPU 的服务器上创建一个数据文件，然后调整根据需要向上或向下文件数。 请注意，双核心 CPU 视为两个 cpu。 在任何情况下，数据文件数不能大于 8 无论多少个内核，以便在计算机上可用。 有关 tempdb 文件的详细信息，请参阅[优化 tempdb 性能](https://docs.microsoft.com/sql/relational-databases/databases/tempdb-database)。|  
|设置最小值，并为 SQL Server 上的相同值的最大服务器内存个该主机实例的 BizTalk Server 数据库。|运行该主机的 SQL Server 的计算机应将 BizTalk Server 数据库专用于运行 SQL Server。 当运行该主机的 SQL Server 的计算机 BizTalk Server 数据库**是**专用于运行 SQL Server，我们建议，min server memory 和最大服务器内存设置每个 SQL Server 实例上的选项来指定要分配到 SQL Server 的内存量固定。 在这种情况下，您应将 min server memory 和最大服务器内存为相同的值 （设置为最大的 SQL Server 将使用的物理内存量）。 这将减少开销，否则将使用 SQL server 动态地管理这些值。 在运行 SQL Server 以指定要分配到 SQL Server 的内存量固定每台计算机上执行以下 T-SQL 命令：<br /><br /> sp_configure 最大服务器内存 (MB)，（以 mb 为单位的最大大小） sp_configure 最小服务器内存 (MB)，（以 mb 为单位的最小大小）<br /><br /> 为 SQL Server 设置的内存量之前，请通过减去总物理内存中适用于 Windows Server 所需的内存来确定适当的内存设置。 这是内存的最大可以为 SQL Server 分配量。 **注意：** 如果运行 BizTalk Server 数据库也承载的 SQL Server 的计算机托管企业单一登录主密钥，如本主题中所述[聚类分析主密钥服务器](clustering-the-master-secret-server.md)则可能需要调整此值设置为确保有足够的内存可用于运行企业单一登录服务。|  
|BizTalk 跟踪数据库的大小|-当确定 BizTalk 跟踪 (DTA) 数据库中的消息的大小，向消息上下文的平均大小的消息大小如果这一点非常重要的消息大小。<br />-若要将 BizTalk 跟踪数据库中的消息大小限制，限制提升的属性的数目。<br />-如果启用了业务流程调试器选项，请考虑在业务流程中每个形状的状态保存在 BizTalk 跟踪数据库中。|  
  
<a name="BKMK_Maintain"></a>   
## <a name="performing-sql-server-maintenance-procedures"></a>执行 SQL Server 维护过程  
  
|步骤|参考|  
|-----------|---------------|  
|定义 BizTalk Server 数据库的自动增长设置。|尤其对于 MessageBox 和跟踪数据库，数据库自动增长应设置为固定数量的而不是百分比，兆字节为单位。 具体取决于您的 BizTalk Server 应用程序和吞吐量，MessageBox 和跟踪数据库可能会非常大。 如果自动增长设置为百分比，则自动增长可能是重大。<br />-即时文件初始化可以大大减少文件增长操作的性能影响。<br />-理想情况下，支持的文件组的文件的大小应为预分配，和如果可能，请设置为静态的大小。<br /><br /> 有关详细信息，请参阅[定义数据库的自动增长设置](defining-auto-growth-settings-for-databases.md)。|  
|备份 BizTalk Server 数据库|-我们建议运行 BizTalk Server 备份作业，若要防止 BizTalk Server 数据库事务日志增长不受限制的方式。<br />-应还原整个 BizTalk Server 环境定期进行，并且应仔细记录的过程。<br />-我们建议您存档旧的备份文件。<br /><br /> 有关详细信息，请参阅[备份数据库](backing-up-databases.md)。|  
|监视 BizTalk Server SQL 代理作业。|监视这些作业的运行状况，并确保它们无错运行。 有关详细信息，请参阅[监视 SQL Server 代理作业](monitoring-sql-server-agent-jobs.md)。|  
|启用 BizTalk Server 跟踪和存档|"DTA 清除和存档"SQL 代理作业中存档和清除旧数据从 BizTalk 跟踪数据库，从而阻止增长失控。 这对于 BizTalk Server 系统正常运行至关重要。 有关详细信息，请参阅[清除和存档跟踪数据](purging-and-archiving-tracking-data.md)。|  
  
<a name="BKMK_Backup"></a>   
## <a name="backing-up-the-biztalk-server-databases"></a>备份 BizTalk Server 数据库  
  
|步骤|参考|  
|-----------|---------------|  
|验证已配置备份 BizTalk Server SQL 代理作业。|请参阅[配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|配置备份 BizTalk Server SQL 代理作业来删除早于指定天数的备份文件@DaysToKeep变量。 如果备份文件不会删除它们可以不受限制不断增长的可能填满磁盘，它包含备份文件，并且会导致有限的磁盘空间与相关的问题。|请参阅[配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|验证备份 BizTalk Server SQL 代理作业已启用并正在运行。|[监视 SQL Server 代理作业](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Disaster"></a>   
## <a name="using-sql-server-log-shipping-for-disaster-recovery"></a>使用 SQL Server 日志传送灾难恢复  
  
|步骤|参考|  
|-----------|---------------|  
|验证的灾难恢复服务器都具有容量来处理生产负载。|请参阅[使用 BizTalk Server 日志传送灾难恢复](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|请确保也记录在灾难恢复例程的详细信息。|请参阅[使用 BizTalk Server 日志传送灾难恢复](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|作为常规的测试，实际故障转移到灾难恢复站点的一部分，尤其是当新的 BizTalk 应用程序放在生产环境中。|请参阅[使用 BizTalk Server 日志传送灾难恢复](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
  
<a name="BKMK_Jobs"></a>   
## <a name="monitoring-biztalk-server-sql-agent-jobs"></a>监视 BizTalk Server SQL 代理作业  
  
|步骤|参考|  
|-----------|---------------|  
|验证 SQL Server 代理服务正在运行。|请参阅[监视 SQL Server 代理作业](monitoring-sql-server-agent-jobs.md)|  
|验证 BizTalk server 安装的 SQL Server 代理作业已启用并正在运行成功。|请参阅[监视 SQL Server 代理作业](monitoring-sql-server-agent-jobs.md)|  
|验证 BizTalk Server SQL 代理作业及时完成。|请参阅[监视 SQL Server 代理作业](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Purge"></a>   
## <a name="purging-and-archiving-tracking-data"></a>清除和存档跟踪数据  
  
|步骤|参考|  
|-----------|---------------|  
|请确保 SQL 代理作业"DTA 清除和存档"正确配置和启用，并且已成功完成。|请参阅[配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)。|  
|确保作业可以快速生成传入跟踪数据清除跟踪数据。|请参阅[测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)|  
|查看软清除和硬清除参数，以确保保持最佳的时间长度的数据。|请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。|  
|如果您只需清除旧数据，则不需要将其存档第一次，更改 SQL 代理作业来调用存储的过程"dtasp_PurgeTrackingDatabase。"|请参阅[从 BizTalk 跟踪数据库中清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)。|  
  
## <a name="next"></a>Next
  
-   [不可更改的 SQL Server 设置](sql-server-settings-that-should-not-be-changed.md)  
  
-   [监视和降低数据库 IO 争用](monitoring-and-reducing-database-i-o-contention.md)  
  
-   [查看和测试故障转移方案的 SQL Server 群集配置](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)  
  
-   [定义数据库的自动增长设置](defining-auto-growth-settings-for-databases.md)  
  
-   [备份数据库](backing-up-databases.md)  
  
-   [为灾难恢复使用 BizTalk Server 日志传送](using-biztalk-server-log-shipping-for-disaster-recovery.md)  
  
-   [监视 SQL Server 代理作业](monitoring-sql-server-agent-jobs.md)  
  
-   [清除和存档跟踪数据](purging-and-archiving-tracking-data.md)