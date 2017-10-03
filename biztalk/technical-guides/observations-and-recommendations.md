---
title: "观察值和建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88289080-1a59-4ffc-a0b2-312ec21940c2
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fba4c82725239bb8e37d8bf611dd721d1ee1514b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="observations-and-recommendations"></a>观察值和建议
## <a name="test-results-summary"></a>测试结果摘要  
 仅限消息的方案的结果令要 ~ 每天 109,382,400 消息。 对于业务流程的方案，结果将指示运行 BizTalk Server 的单台计算机可以处理每天最多 58,752,000 消息。 在沙盒环境使用正常的企业级的硬件部署的很多 BizTalk Server 解决方案来实现这些结果。 因此，这些结果指示的一种 BizTalk 服务器性能的则可通过实现任何自定义代码。 客户解决方案通常涉及到自定义方式开发 BizTalk 项目;在许多情况下这会增加处理要求这反过来会影响性能。 按照本指南中讲述的建议特别[优化 BizTalk 服务器应用程序](../technical-guides/optimizing-biztalk-server-applications.md)部分，实现自定义方式开发 BizTalk Server 项目可以最小化的影响。  
  
 下表提供为此性能评估的测试结果摘要。  
  
|应用场景|消息传递 (BizTalk KPI-每秒处理的文档)|消息传送 (SQL KPI – SQL 处理器使用率)|消息延迟 （秒）|业务流程 (BizTalk KPI-每秒处理的文档)|业务流程 (SQL KPI – SQL 处理器使用率)|业务流程延迟 （秒）|  
|--------------|----------------------------------------------------------------|-------------------------------------------------------|-----------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------|  
|单个 MessageBox 1 BizTalk Server 计算机|每秒处理的 1266年文档|59%SQL CPU 使用率|0.06|每秒处理的 680 文档|66.5%SQL CPU 使用率|0.067|  
|单个 MessageBox 2 BizTalk Server 计算机|每秒处理的 1267年文档|59.8%SQL CPU 使用率|0.057|每秒处理的 686 文档|68.5%SQL CPU 使用率|0.067|  
|3 MessageBox 1 BizTalk Server 计算机|每秒处理的 2102年文档|41%SQL CPU 使用率|0.077|每秒处理的 974 文档|48%SQL CPU 使用率|0.11|  
|3 MessageBox 2 BizTalk Server 计算机|每秒处理的 2285年文档|58%SQL CPU 使用率|0.041|每秒处理的 1065年文档|65%SQL CPU 使用率|0..69|  
|4 MessageBoxes 1 BizTalk Server 计算机|每秒处理的 2125年文档|30%SQL CPU 使用率|0.078|每秒处理的 979 文档|37%SQL CPU 使用率|0.095|  
|4 MessageBoxes 2 BizTalk Server 计算机|每秒处理的 2790年文档|50%SQL CPU 使用率|0.052|每秒处理的 1487年文档|63%SQL CPU 使用率|0.15|  
|4 MessageBoxes 3 BizTalk Server 计算机|每秒处理的 2656年文档|58%SQL CPU 使用率|0.074|每秒处理的 1388年文档|65%SQL CPU 使用率|0.15|  
  
## <a name="comparison-of-performance-statistics-with-biztalk-server-2009"></a>与 BizTalk Server 2009 性能统计信息的比较  
 下表显示了 BizTalk Server 2009 和 BizTalk Server 2010 之间的性能统计信息的比较。 此表中列出的 BizTalk Server 2009 性能统计信息都是从 BizTalk Server 2009 性能和优化指南。  
  
|应用场景|BizTalk Server 2009<br /> 最大可持续吞吐量 (MST) 消息数/秒|BizTalk Server 2009<br />所需的 BizTalk 服务器数量|BizTalk Server 2010<br />最大可持续吞吐量 (MST) 消息数/秒|BizTalk Server 2010<br />所需的 BizTalk 服务器数量|BizTalk Server 2010%区别 BizTalk Server 2009|  
|--------------|----------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------|  
|消息传送-单一 MessageBox|1291|2|1266|1|98.06%|  
|业务流程的单个消息框|676|2|680|1|100.59%|  
|消息传送-3 MessageBoxes|2103|3|2285|2 （使用 1 BTS 2102/秒）|108.65%|  
|消息传送-4 MessageBoxes|不适用|不适用|2790|2|不适用|  
|业务流程-3 MessageBoxes|1005|4|1065|2 （使用 1 BTS 974/秒）|105.97%|  
|业务流程-4 MessageBoxes|不适用|不适用|1487|2|不适用|  
  
 在实验室环境中，使用四个 MessageBox 数据库时，最大可持续吞吐量结果如下所示：  
  
-   对于消息传递方案，每秒的 2790年文档。  
  
-   对于业务流程的方案，每秒的 1487年文档。  
  
 **消息注意事项**而 BizTalk Server 规定了对消息大小没有限制，我们运行 BizTalk Server 2010 的测试在使用 2 KB 的消息，WCF 适配器使用的类型了 WCF NetTCP 适配器。 这与 BizTalk Server 2009 性能优化指南的测试中使用的消息大小和适配器类型相匹配。  
  
 性能改善的驱动程序：  
  
1.  **硬件改进**-我们实验室中使用的 SQL Server 计算机已 4 个 CPU，四核 （16 个核心） 和 @ 2.40 GHz Intel Xeon E7330。 在 2009年测试中，4 个 CPU，个四核 （16 个核心） 和 Intel Xeon 2.4 GHz 已使用。  
  
     我们实验室中使用的 BizTalk Server 计算机已 2 个 CPU，四核 （8 核），Nehalem 超线程 (16 个逻辑核心） 和 Intel Xeon X 5570 @ 2.93 GHz。 在 2009年测试中，2 个 CPU，个四核 （8 核），Intel Xeon 2.33 GHz 已使用。  
  
2.  **SQL Server 引擎的改进**-在 2009年测试针对 SQL Server 2008 中，而与作为基础数据库平台的 SQL Server 2008 R2 执行我们的测试执行。  
  
## <a name="recommendations-for-scaling-the-biztalk-server-and-sql-server-tiers"></a>缩放 BizTalk Server 和 SQL Server 层的建议  
 与这些结果中，BizTalk Server 产品团队已能够演示，单个 BizTalk Server 计算机和一台 SQL Server 计算机可以支持 109 亿万条消息在消息传递方案中并且 58 万个业务流程的 24 小时期间。 通过缩放到我们的环境中可用的最佳配置 BizTalk Server 和 SQL 层，我们都能处理 over241 100 万次消息每天和 128 多万业务流程。 通过使用在许多企业中部署的硬件类在沙盒环境中执行结果。 如上文所述，这些数字表示实际的性能，可以使用任何自定义代码和优化的环境中实现的 BizTalk server。  使用其他硬件，则可能甚至更高的性能可能已达到。 客户解决方案通常涉及到自定义方式开发 BizTalk 项目，会产生额外的处理要求，因此提高资源利用率、 反过来降低整体性能。 但是，按照所述在指南中，尤其是中的建议的建议[优化 BizTalk 服务器应用程序](../technical-guides/optimizing-biztalk-server-applications.md)，此方法的影响最小化。  
  
 结果演示，是否 MessageBox SQL Server 计算机不是瓶颈，向外扩展的 BizTalk Server 计算机的数量是有效的向外扩展策略。 在我们的结果指示，因为我们观察到一个争用点发生 MessageBox 数据库内共享的表格上，添加 BizTalk Server 计算机成为低效的横向扩展方法的某些点之后, 导致到的性能降低。 若要最大化可以从具有单个 MessageBox 数据库的 BizTalk Server 组中获取的结果，你应该应用中所述的优化[优化数据库性能](../technical-guides/optimizing-database-performance.md)。 具体而言，应确保快速存储子系统用于 SQL Server 存储和 SQL Server 用于存储 MessageBox 数据库文件的逻辑磁盘响应时间尽可能短。 可接受的读/写性能测量的常用的阈值为 15 毫秒;通常这被测量得出 avg.Disk sec/Read 和 avg.可在逻辑磁盘性能对象下找到的磁盘 sec/Write 计数器。 一旦所有可用优化已应用于承载 MessageBox 数据库的 SQL Server 计算机，可以添加其他 MessageBox 数据库。 同样的优化技术应用于主 MessageBox 数据库也应该将应用到辅助数据库。 我们建议你遵循中的准则[缩放出 SQL Server 层](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075) BizTalk Server 文档中。  
  
 若要获得最佳结果，整个的硬件和软件堆栈需要的适当的质量，并正确配置。 首先，较高的质量硬件应购买包括，但不是限于千兆网络连接、 快速存储 （SAN 或 15-K 本地 SQL 磁盘） 和现代具有多个 Cpu，具有多个内核，每个 CPU 的计算机。 SQL Server 计算机应将专用于 BizTalk Server 仅处理。 当运行单个 SQL Server 计算机时，我们建议，可创建的 SQL 的两个实例，一个用于 BizTalk MessageBox，所有其他数据库的一个。 这使实例范围的设置配置为获得最佳性能的 MessageBox。 中的优化建议[优化性能](../technical-guides/optimizing-performance.md)应该应用按以下顺序分步：[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)，[优化网络性能](../technical-guides/optimizing-network-performance.md)，[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)，[后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)和[常规 BizTalk ServerOptimizations1](../technical-guides/general-biztalk-server-optimizations1.md)。 创建专用的 MessageBox 数据库文件组和分配这些跨 SAN Lun 中, 所述[Databases2 优化文件组](../technical-guides/optimizing-filegroups-for-the-databases2.md)，可提供很大的性能改进，具体取决于你SAN 配置和 LUN 布局。  
  
 若要有效地确定如何缩放 BizTalk Server 或 SQL 层，我们建议，负载测试是使用近似实际生产数据的消息执行。 在缩放 BizTalk Server 层前, 确保 SQL Server 不是已是瓶颈，根据中的建议[监视 SQL Server 性能](../technical-guides/monitoring-sql-server-performance.md)。 如果 SQL Server 不成为瓶颈，并且没有任何 BizTalk Server 计算机上的 CPU 预留空间，你可能能够通过修改您的主机实例布局提高吞吐量。 请务必建立四个或五个关键绩效指标 (Kpi)，用于为所有测试运行作为粗略比较点。 以下建议，你将能够快速仪表是否特定更改的解决方案的总体性能下降。  
  
 在横向扩展 SQL Server 层之前, 应用所有中优化[优化数据库性能](../technical-guides/optimizing-database-performance.md)。 在客户性能实验室的过程中，观察已 MessageBox 该磁盘存储配置，TempDb 数据库尤其是可以提供超过 30%吞吐量改进。 缩小到 MessageBox 的多个数据库，因为没有什么的性能好处时从单个 MessageBox 数据库扩展到两个 MessageBox 数据库已使用三个和第四个 MessageBox 数据库。 有关横向扩展 BizTalk Server MessageBox 的详细信息，请参阅[缩放出 SQL Server 层](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075) BizTalk Server 文档中。  
  
## <a name="implemented-optimizations"></a>实现的优化  
 本部分提供已应用于实验室测试方案的所有优化的清单。  
  
> [!NOTE]  
>  这些前应进行测试根据你更改管理过程应用这些安全更新生产环境中。  
  
 将优化应用系统、 受控方式 — 通过应用优化的一组，然后测试影响-将导致的最大性能优势。 定期测试优化的影响的情况下应用优化实际上可能会导致性能降低的解决方案。  
  
### <a name="checklists-of-optimizations-applied"></a>优化应用的核对清单  
 **平台和网络优化**  
  
|Optimization|参考|  
|------------------|---------------|  
|BIOS： 配置性能设置。|[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)|  
|禁用对 SQL Server 文件的实时扫描。|[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)|  
|启用"高性能"BizTalk Server 和 SQL Server 的所有计算机上的电源计划。|[一般性的指导原则，用于提高操作系统性能](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
|在所有 BizTalk Server 和 SQL Server 计算机上禁用防病毒软件。|[一般性的指导原则，用于提高操作系统性能](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
  
 **SQL Server 优化： 常规**  
  
|Optimization|参考|  
|------------------|---------------|  
|设置为 64 KB 的 NTFS 文件分配单元。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|安装 SQL Server 2008 R2。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|配置 SQL Server 2008 R2 数据收集器/仓库。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|确保适当的 Windows 特权具有已扩展到的 SQL Server 服务帐户。|SQL Server 2008 R2:[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkID=132144)(http://go.microsoft.com/fwlink/?LinkID=132144)|  
|设置 SQL Server 的最小和最大服务器内存。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|授予到用于针对 SQL Server 的帐户的 Windows 锁定内存页特权。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|预先大小 BizTalk Server 数据库迁移到具有多个数据文件的适当大小...|[后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|配置 SQL Server 客户端协议。|[故障排除 SQL Server](http://go.microsoft.com/fwlink/?LinkID=154250) (http://go.microsoft.com/fwlink/?LinkID=154250)|  
|将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|手动设置 SQL Server 进程关联|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|配置 MSDTC 和禁用 DTC 跟踪|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|启用跟踪标志 T1118 作为引导参数的 SQL Server 的所有实例|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
  
 **SQL Server 优化： BizTalk 数据库**  
  
|Optimization|参考|  
|------------------|---------------|  
|将自动增长的 BizTalk 数据库都设置为固定的值，并不是百分比值。|[后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|移动/拆分 BizTalk 数据库数据和日志文件，以单独的 LUN。|[后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|请考虑设置特定的 MessageBox 数据库表上的 text in row 表选项|[后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
  
 **BizTalk 优化**  
  
|Optimization|参考|  
|------------------|---------------|  
|单独接收端口、 发送端口、 业务流程，以及在单独、 专用的主机上的跟踪。|[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|配置轮询间隔。|[低延迟方案 Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|调整 BizTalk 配置文件的最大连接属性。|"增加允许的更改 maxconnection 参数的值的 SOAP 和 HTTP 并发连接数"部分[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|在 BizTalk Server 中的每个节点上定义的 CLR 承载每个主机实例的参数：<br /><br /> 最大 IO 线程： 250<br /><br /> 最大工作线程： 100<br /><br /> 最小的 IO 线程： 25<br /><br /> 最小工作线程： 25|"定义的 CLR 承载 BizTalk 主机实例的线程值"部分[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|增加到 10000 的进程内消息和内部消息队列大小。|[低延迟方案 Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|禁用 BizTalk 服务器组级别跟踪。|[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|管理并发执行的 ASP.NET 4 Web 应用程序可以承载独立接收到的位置后, 端 Web 服务和在 IIS 7.5 和 IIS 7.0 在集成模式下运行的 WCF 服务的请求的数量|[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|禁用限制的 BizTalk Server 主机|[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|配置 MSDTC 和禁用 DTC 跟踪|[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
  
 **WCF 配置优化**  
  
|Optimization|参考|  
|------------------|---------------|  
|对于每个 WCF 服务，应用 serviceThrottling 服务行为，并将设置**maxConcurrentCalls**和**maxConcurrentSessions**为 200。|[优化 BizTalk Server WCF 适配器性能](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)|  
|在后端 WCF 服务配置文件中配置 serviceThrottling 行为的使用情况。|[优化 WCF Web 服务性能](../technical-guides/optimizing-wcf-web-service-performance.md)|  
  
## <a name="see-also"></a>另请参阅  
 [缩放生产 BizTalk Server 环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)