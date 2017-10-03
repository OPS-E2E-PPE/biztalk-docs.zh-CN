---
title: "清单： 配置 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edd20f24-8a72-40b7-abee-81fbd3ceefda
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce0eff1dab6afe81c55f4cffa08c4839762e82ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-configuring-sql-server"></a>清单： 配置 SQL Server
本主题列出时准备应遵循的步骤[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]或[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境。  
  
-   [清单： 配置 SQL Server](../technical-guides/checklist-configuring-sql-server.md)  
  
-   [执行 SQL Server 维护过程](../technical-guides/checklist-configuring-sql-server.md#BKMK_Maintain)  
  
-   [备份 BizTalk Server 数据库](../technical-guides/checklist-configuring-sql-server.md#BKMK_Backup)  
  
-   [使用 SQL Server 日志传送以实现灾难恢复](../technical-guides/checklist-configuring-sql-server.md#BKMK_Disaster)  
  
-   [监视 BizTalk Server SQL 代理作业](../technical-guides/checklist-configuring-sql-server.md#BKMK_Jobs)  
  
-   [清除和存档跟踪数据](../technical-guides/checklist-configuring-sql-server.md#BKMK_Purge)  
  
<a name="BKMK_Config"></a>   
## <a name="configuring-sql-server"></a>配置 SQL Server  
  
|步骤|参考|  
|-----------|---------------|  
|监视和减少[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库文件磁盘 I/O 争用。|-我们建议你主动监视可存放的数据和事务日志文件的磁盘的磁盘 I/O 使用情况。<br />-我们建议，数据文件和事务日志文件的每个放置在专用的驱动器，以减少磁盘 I/O 争用成为问题的可能性。<br />-你可以减少磁盘 I/O 争用，通过将分离的 MessageBox 和跟踪 (DTA) 的数据库，并且通过将数据库文件和事务日志文件在不同的物理磁盘上分离。<br /><br /> 有关详细信息，请参阅[监视和减少数据库 IO 争用](~/technical-guides/monitoring-and-reducing-database-i-o-contention.md)|  
|确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]正确对齐的磁盘分区上配置|正确对齐的磁盘分区可能会导致显著降低延迟，从而提高[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能，这反过来提高[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。 相反，非对齐的磁盘分区可能造成负面影响输入/输出性能，从而降低[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。<br /><br /> 有关如何正确对齐的磁盘分区的详细信息会产生积极影响性能，请参阅["磁盘分区对齐最佳实践 for SQL Server"](http://go.microsoft.com/fwlink/?LinkId=154073) (http://go.microsoft.com/fwlink/?LinkId=154073)。|  
|让您使用 SQL Server 事件探查器来监视事件|使用 SQL Server 事件探查器监视感兴趣的事件。 如果跟踪变得太大，你可以筛选基于所需的信息，以便收集事件数据的一个子集。 监视过多事件会增加服务器和监视进程的开销，并且可能导致跟踪文件或跟踪表变得很大，尤其是当监视进程持续很长时间时。|  
|监视和减少 DTC 日志文件磁盘 I/O 争用。|[监视和减少 DTC 日志文件磁盘 IO 争用](~/technical-guides/monitoring-and-reducing-dtc-log-file-disk-i-o-contention.md)|  
|提供的高可用性[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。|[数据库可用性规划](~/technical-guides/planning-for-database-availability.md)|  
|查看故障转移方案的主动/主动 SQL Server 群集配置。|[查看和测试故障转移方案的 SQL Server 群集配置](~/technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|使用默认配置设置：<br /><br /> -最大值 Degree of Parallelism (MDOP)。<br />-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上的统计信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。<br />-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库索引重新生成和碎片整理。|[不应更改的 SQL Server 设置](~/technical-guides/sql-server-settings-that-should-not-be-changed.md)|  
|启用跟踪标志 1118 (TF1118) 的所有实例的启动参数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。|实现 TF1118 有助于减少争用跨[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]通过删除几乎所有单个页分配的实例。 详细信息，请参阅 Microsoft 知识库文章 328551， ["并发增强功能的 tempdb 数据库"](http://go.microsoft.com/fwlink/?LinkId=153694) (http://go.microsoft.com/fwlink/?LinkId=153694)。 **注意：** TF1118，请参阅有关详细信息["误解围绕 TF1118"](http://go.microsoft.com/fwlink/?LinkId=158271) (http://go.microsoft.com/fwlink/?LinkId=158271)。 请注意，在以下链接的内容不由 Microsoft 拥有，Microsoft 不保证内容的准确性。|  
|将 tempdb 数据库拆分为多个大小相等的每个上的数据文件[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。|确保用于 tempdb 数据文件的大小相等。 这是关键的因为按比例填充算法由[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]取决于数据文件的大小。 如果数据文件创建不相等的大小，按比例填充算法将使用全局分配映射 (GAM) 分配，而无需分配所有的文件，从而与将创建多个的目的之间分配更多的最大文件数据文件。 作为一般原则是，为每个 CPU 的服务器上创建一个数据文件，然后调整根据需要向上或向下文件数。 请注意，双核心 CPU 将被视为两个 CPU。 在任何情况下，数据文件数必须大于 8 无关多少个内核，以便在计算机上可用。 有关 tempdb 文件的详细信息，请参阅[优化 tempdb 性能](http://go.microsoft.com/fwlink/?LinkId=158272)(http://go.microsoft.com/fwlink/?LinkId=158272) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档。|  
|如果你正在运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载位于运行的计算机上的数据库和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]具有足够的物理内存配置的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用地址窗口扩展 (AWE) 内存。|X86 计算机，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应配置为使用超过 2 GB 的物理内存。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]包括对使用的 Microsoft Windows 地址窗口扩展 (AWE) 来解决最多 32 GB 的内存支持。 使用 AWE，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可以保留未被其他应用程序和操作系统使用的内存。 但是，使用此内存中，每个实例必须以静态方式分配所需的内存。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]只能使用此 AWE 分配内存，为数据缓存而不是可执行文件、 驱动程序、 Dll、 和等。 有关详细信息，请参阅：<br /><br /> Microsoft 知识库文章 274750， ["如何配置 SQL Server 以使用多个 2 GB 的物理内存"](http://go.microsoft.com/fwlink/?LinkId=153718) (http://go.microsoft.com/fwlink/?LinkId=153718)。<br />-   [使用 AWE](http://go.microsoft.com/fwlink/?LinkId=153720) (http://go.microsoft.com/fwlink/?LinkId=153720) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档。<br />-   [为 SQL Server 启用 AWE 内存](http://go.microsoft.com/fwlink/?LinkId=158273)(http://go.microsoft.com/fwlink/?LinkId=158273) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档。|  
|在上设置的相同值的最小值和最大服务器内存[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]instance(s) 该主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。|运行的计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]该主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库应将专用于运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 当运行的计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]该主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库**是**专用于运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，我们建议的 min server memory 和最大服务器内存选项卡上的每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例将设置为指定的内存分配给固定的量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 在这种情况下，应将设置为 min server memory 和最大服务器内存为相同的值 （等于最大的 SQL Server 将使用的物理内存量）。 这将减少开销，否则将由使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]动态管理这些值。 运行每台计算机上，执行以下 T-SQL 命令[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]指定的内存分配给固定的量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]:<br /><br /> sp_configure ' 最大服务器内存 (MB)，（以 mb 为单位的最大大小） sp_configure 最小服务器内存 (MB)，（以 mb 为单位的最小大小）<br /><br /> 设置的内存量之前[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，减去所需的总物理内存从 Windows Server 的内存来确定适当的内存设置。 这是最大可以为分配的内存量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 **注意：**如果运行的计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]该主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库也承载企业单一登录主密钥，如主题所述[群集主密钥服务器](~/technical-guides/clustering-the-master-secret-server.md)然后你可能需要调整此值，以确保有足够的内存可用于运行企业单一登录服务。|  
|BizTalk 跟踪数据库的大小|-当确定 BizTalk 跟踪 (DTA) 数据库中的消息的大小，将添加消息上下文的平均大小到的消息大小如果一点很重要，相比的消息大小。<br />-若要限制 BizTalk 跟踪数据库中的消息的大小，则将提升的属性数目的限制。<br />-如果启用业务流程调试器选项，考虑到每个形状中业务流程的状态保存到 BizTalk 跟踪数据库中。|  
  
<a name="BKMK_Maintain"></a>   
## <a name="performing-sql-server-maintenance-procedures"></a>执行 SQL Server 维护过程  
  
|步骤|参考|  
|-----------|---------------|  
|定义自动增长设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。|特别是对于 MessageBox 和跟踪数据库，数据库自动增长应设置为固定数量的兆字节为单位，而不是百分比。 根据你的 BizTalk Server 应用程序和吞吐量，MessageBox 和跟踪数据库可能会非常大。 如果自动增长设置为百分比，则自动增长可能是非常高。<br />-即时文件初始化可以极大地降低文件增长操作的性能影响。<br />-理想情况下，支持的文件组的文件的大小应预分配，并且如果可能，请设置为静态大小。<br /><br /> 有关详细信息，请参阅[定义数据库的自动增长设置](~/technical-guides/defining-auto-growth-settings-for-databases.md)。|  
|备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库|-我们建议运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]备份作业，以防止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库增长方式不受限制的事务日志。<br />-你应还原整个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上定期，并且你的环境应仔细记录的过程。<br />-我们建议你将旧的备份文件存档。<br /><br /> 有关详细信息，请参阅[备份数据库](~/technical-guides/backing-up-databases.md)。|  
|监视器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 代理作业。|监视这些作业的运行状况，并确保它们正在运行且未发生错误。 有关详细信息，请参阅[监视 SQL Server 代理作业](~/technical-guides/monitoring-sql-server-agent-jobs.md)。|  
|启用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪和存档|"DTA 清除和存档"SQL 代理作业存档，并从 BizTalk 跟踪数据库，从而阻止增长出控件将其清除旧数据。 这是必需的正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 有关详细信息，请参阅[清除和存档跟踪数据](~/technical-guides/purging-and-archiving-tracking-data.md)。|  
  
<a name="BKMK_Backup"></a>   
## <a name="backing-up-the-biztalk-server-databases"></a>备份 BizTalk Server 数据库  
  
|步骤|参考|  
|-----------|---------------|  
|验证备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置 SQL 代理作业。|-请参阅["如何配置备份 BizTalk Server 作业"](http://go.microsoft.com/fwlink/?LinkId=153813) (http://go.microsoft.com/fwlink/?LinkId=153813)。<br />-请参阅[备份数据库](~/technical-guides/backing-up-databases.md)。|  
|配置备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 代理作业以删除早于指定天数的备份文件@DaysToKeep变量。 如果备份文件不会删除它们可以不受限制随时间增长的可能填满磁盘，它包含备份文件，并且会导致与磁盘空间有限相关的问题。|请参阅 Microsoft 知识库文章 982546， ["备份 BizTalk Server"作业失败时备份的文件会累积随着 Microsoft BizTalk Dababase Server 中的时间的推移](http://go.microsoft.com/fwlink/?LinkId=202858)(http://go.microsoft.com/fwlink/?LinkId=202858)。|  
|验证备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 代理作业是否已启用且正在运行。|[监视 SQL Server 代理作业](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Disaster"></a>   
## <a name="using-sql-server-log-shipping-for-disaster-recovery"></a>使用 SQL Server 日志传送以实现灾难恢复  
  
|步骤|参考|  
|-----------|---------------|  
|验证灾难恢复服务器具有处理生产负载的能力。|请参阅[使用 BizTalk Server 日志传送以实现灾难恢复](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|确保你的灾难恢复日常活动期间细节很好地进行了说明。|请参阅[使用 BizTalk Server 日志传送以实现灾难恢复](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|作为正则的测试，实际故障转移到灾难恢复站点的一部分，尤其是当新的 BizTalk 应用程序都将置于生产。|请参阅[使用 BizTalk Server 日志传送以实现灾难恢复](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
  
<a name="BKMK_Jobs"></a>   
## <a name="monitoring-biztalk-server-sql-agent-jobs"></a>监视 BizTalk Server SQL 代理作业  
  
|步骤|参考|  
|-----------|---------------|  
|验证 SQL Server 代理服务正在运行。|请参阅[监视 SQL Server 代理作业](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
|验证安装的 SQL Server 代理作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已启用并且成功运行。|请参阅[监视 SQL Server 代理作业](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
|验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]及时完成 SQL 代理作业。|请参阅[监视 SQL Server 代理作业](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Purge"></a>   
## <a name="purging-and-archiving-tracking-data"></a>清除和存档跟踪数据  
  
|步骤|参考|  
|-----------|---------------|  
|确保 SQL 代理作业"DTA 清除和存档"正确配置和启用，并且已成功完成。|请参阅["如何配置 DTA 清除和存档作业"](http://go.microsoft.com/fwlink/?LinkId=153814) (http://go.microsoft.com/fwlink/?LinkId=153814)。|  
|确保作业能够快速生成传入的跟踪数据清除的跟踪数据。|请参阅["衡量最大可持续跟踪吞吐量"](http://go.microsoft.com/fwlink/?LinkId=153815) (http://go.microsoft.com/fwlink/?LinkId=153815)。|  
|查看软清除和硬清除参数，以确保你保存数据的最佳总时间。|请参阅["存档和清除跟踪数据库 BizTalk"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)。|  
|如果你只需以清除旧数据并不需要对其进行存档第一次，更改 SQL 代理作业调用存储的过程"dtasp_PurgeTrackingDatabase。"|请参阅["如何从 BizTalk 跟踪数据库清除数据"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [不应更改的 SQL Server 设置](~/technical-guides/sql-server-settings-that-should-not-be-changed.md)  
  
-   [监视和减少数据库 IO 争用](~/technical-guides/monitoring-and-reducing-database-i-o-contention.md)  
  
-   [查看和测试故障转移方案的 SQL Server 群集配置](~/technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)  
  
-   [定义数据库的自动增长设置](~/technical-guides/defining-auto-growth-settings-for-databases.md)  
  
-   [备份数据库](~/technical-guides/backing-up-databases.md)  
  
-   [使用 BizTalk Server 日志传送以实现灾难恢复](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)  
  
-   [监视 SQL Server 代理作业](~/technical-guides/monitoring-sql-server-agent-jobs.md)  
  
-   [清除和存档跟踪数据](~/technical-guides/purging-and-archiving-tracking-data.md)