---
title: 观测和建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88289080-1a59-4ffc-a0b2-312ec21940c2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf134382be6086a1a3ab96fa649fa6cbb41d9bad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980070"
---
# <a name="observations-and-recommendations"></a>观测和建议
## <a name="test-results-summary"></a>测试结果摘要  
 仅限消息传送的方案的结果所观察到为 ~ 109,382,400 消息 / 天。 对于业务流程方案中，结果表明运行 BizTalk Server 的单台计算机可以处理最多 58,752,000 消息 / 天。 在使用正常的企业级的硬件部署的很多 BizTalk Server 解决方案的沙盒环境中实现了这些结果。 因此，这些结果指示可以无自定义代码来实现的 BizTalk Server 性能的类型。 客户解决方案通常涉及到自定义开发 BizTalk 项目;在许多情况下这会增加处理要求这反过来会影响性能。 按照本指南中的建议特别[优化 BizTalk Server 应用程序](../technical-guides/optimizing-biztalk-server-applications.md)部分中，实现自定义开发 BizTalk Server 项目可以最小化的影响。  
  
 下表提供有关此性能评估的测试结果摘要。  
  
|应用场景|消息传送 (BizTalk KPI-每秒处理的文档)|消息传送 (SQL KPI – SQL 处理器使用率)|消息延迟 （秒）|业务流程 (BizTalk KPI-每秒处理的文档)|业务流程 (SQL KPI – SQL 处理器使用率)|业务流程的延迟 （秒）|  
|--------------|----------------------------------------------------------------|-------------------------------------------------------|-----------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------|  
|单个 MessageBox 1 BizTalk Server 计算机|每秒处理的 1266年文档|59%SQL CPU 利用率|0.06|每秒处理的 680 文档|66.5%SQL CPU 使用率|0.067|  
|单个 MessageBox 2 BizTalk Server 计算机|每秒处理的 1267年文档|59.8%SQL CPU 使用率|0.057|每秒处理的 686 文档|68.5%SQL CPU 使用率|0.067|  
|3 个 MessageBox 1 BizTalk Server 计算机|每秒处理的 2102年文档|41%SQL CPU 利用率|0.077|每秒处理的 974 文档|48%SQL CPU 利用率|0.11|  
|3 个 MessageBox 2 BizTalk Server 计算机|每秒处理的 2285年文档|58%SQL CPU 利用率|0.041|每秒处理的 1065年文档|65%SQL CPU 利用率|0..69|  
|4 个 Messagebox 1 BizTalk Server 计算机|每秒处理的 2125年文档|30%的 SQL CPU 利用率|0.078|每秒处理的 979 文档|37%SQL CPU 利用率|0.095|  
|4 个 Messagebox 2 BizTalk Server 计算机|每秒处理的 2790年文档|50%的 SQL CPU 利用率|0.052|每秒处理的 1487年文档|63%SQL CPU 利用率|0.15|  
|4 个 Messagebox 3 BizTalk Server 计算机|每秒处理的 2656年文档|58%SQL CPU 利用率|0.074|每秒处理的 1388年文档|65%SQL CPU 利用率|0.15|  
  
## <a name="comparison-of-performance-statistics-with-biztalk-server-2009"></a>与 BizTalk Server 2009 的性能统计信息的比较  
 下表显示了 BizTalk Server 2009 和 BizTalk Server 2010 之间的性能统计信息的比较。 此表中列出的 BizTalk Server 2009 性能统计信息是从 BizTalk Server 2009 性能和优化指南。  
  
|应用场景|BizTalk Server 2009<br /> 最大可承受吞吐量 (MST) 消息数/秒|BizTalk Server 2009<br />BizTalk Server 所需的数目|BizTalk Server 2010<br />最大可承受吞吐量 (MST) 消息数/秒|BizTalk Server 2010<br />BizTalk Server 所需的数目|从 BizTalk Server 2009 的 BizTalk Server 2010%差异|  
|--------------|----------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------|  
|消息传送的单个 MessageBox|1291|2|1266|@shouldalert|98.06%|  
|业务流程的单个 MessageBox|676|2|680|@shouldalert|100.59%|  
|消息传送的 3 个 Messagebox|2103|3|2285|2 （具有 1 BTS 2102/秒）|108.65%|  
|消息传送的 4 个 Messagebox|不适用|不适用|2790|2|不适用|  
|业务流程-3 个 Messagebox|1005|4|1065|2 （具有 1 BTS 974/秒）|105.97%|  
|业务流程-4 个 Messagebox|不适用|不适用|1487|2|不适用|  
  
 在实验室环境中，使用四个 MessageBox 数据库时，最大可承受吞吐量结果如下所示：  
  
- 对于消息传送方案，每秒 2790年文档。  
  
- 对于业务流程的方案，每秒 1487年文档。  
  
  **消息注意事项**时 BizTalk Server 规定了对消息大小没有限制，我们运行 BizTalk Server 2010 的测试使用 2 KB 的消息，使用 WCF 适配器的类型了 Wcf-nettcp 适配器。 此匹配在 BizTalk Server 2009 性能优化指南的测试中使用的消息大小和适配器类型。  
  
  性能改进的驱动程序：  
  
1.  **硬件改进**-在我们的实验室中使用的 SQL Server 计算机是 4 的 CPU、 四核 （16 个内核），@ 2.40 GHz Intel Xeon E7330。 在 2009年测试中，4 个 CPU，四核 （16 个内核），Intel Xeon 2.4 GHz 使用了。  
  
     在我们的实验室中使用的 BizTalk Server 计算机的 2 个 CPU，四核 （8 个内核），Nehalem 超线程 (16 个逻辑核心），Intel Xeon X 5570 @ 2.93 g h z。 在 2009年测试中，2 个 CPU，四核 （8 个内核），Intel Xeon 2.33 GHz 使用了。  
  
2.  **SQL Server 引擎的改进**-2009年中的测试执行针对 SQL Server 2008 中，而我们的测试执行的 SQL Server 2008 R2 作为基础数据库平台。  
  
## <a name="recommendations-for-scaling-the-biztalk-server-and-sql-server-tiers"></a>有关缩放 BizTalk Server 和 SQL Server 层的建议  
 与这些结果，BizTalk Server 产品团队已能够演示，一台 BizTalk Server 计算机和一台 SQL Server 计算机可以支持 109 传输万条消息中的消息传送的方案和 5800 万美元业务流程在 24 时制期间。 通过缩放到我们的环境中提供的最佳配置的 BizTalk Server 和 SQL 层，我们能够处理 over241 100 万条消息 / 天和亿 128 业务流程。 结果在沙盒环境中使用的许多企业中部署的硬件的类执行。 如前面所述，这些数字表示 BizTalk Server 可以使用任何自定义代码和一个优化的环境来实现的实际的性能。  与其他硬件，就可以更大的性能可能已实现。 客户解决方案通常涉及到会产生额外的处理要求，因此提高资源利用率、 又降低整体性能的自定义开发 BizTalk 项目。 但是，按照本指南，尤其是中的建议所述的建议[优化 BizTalk Server 应用程序](../technical-guides/optimizing-biztalk-server-applications.md)，这种影响可以降到最低。  
  
 结果证明，是否 MessageBox SQL Server 计算机不是瓶颈，增加 BizTalk Server 计算机的数目是有效的扩展策略。 特定时间点后我们的结果指示，因为我们观察到 MessageBox 数据库中的共享表上发生的争用点，添加 BizTalk Server 计算机变为无效的向外缩放技术，这会导致性能降低。 若要最大化可以从 BizTalk Server 组与单个 MessageBox 数据库中获取的结果，应该应用中所述的优化[优化数据库性能](../technical-guides/optimizing-database-performance.md)。 具体而言，应确保快速存储子系统，用于 SQL Server 存储和 SQL Server 用于存储的 MessageBox 数据库文件的逻辑磁盘在尽可能短的时间内响应。 测量可接受的读/写性能的常用的阈值为 15 毫秒;通常这被度量的 avg.Disk sec/Read 和 avg.可在逻辑磁盘性能对象下找到 disk sec/Write 计数器。 一旦所有可用优化已应用于承载 MessageBox 数据库的 SQL Server 计算机，可以添加其他 MessageBox 数据库。 同样的优化技术应用于主 MessageBox 数据库还应应用于辅助数据库。 我们建议你遵循中的准则[缩放出 SQL Server 层](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075) BizTalk Server 文档中。  
  
 若要获得最佳结果，在整个硬件和软件堆栈应属于适当的质量和正确配置。 首先，很好的高质量的硬件应购买包括，但不是限于千兆网络连接、 快速存储 （SAN 或 15-K 本地 SQL 磁盘） 和现代具有与每个 CPU 的多个核心的多个 Cpu 的计算机。 应将 SQL Server 计算机专用于 BizTalk Server 仅处理。 在运行单个 SQL Server 计算机，我们建议创建两个实例的 SQL，分别为 BizTalk MessageBox 和所有其他数据库。 这使实例范围的设置进行配置以获得最佳性能的 MessageBox。 中的优化建议[优化性能](../technical-guides/optimizing-performance.md)应该应用执行步骤的顺序如下：[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)，[优化网络性能](../technical-guides/optimizing-network-performance.md)，[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)，[后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)和[一般 BizTalk ServerOptimizations1](../technical-guides/general-biztalk-server-optimizations1.md)。 创建为 MessageBox 数据库的专用文件组，然后在分配这些跨 SAN Lun，如中所述[优化文件组的数据库 2](../technical-guides/optimizing-filegroups-for-the-databases2.md)，可以提供很大的性能改进，具体取决于你SAN 配置和 LUN 布局。  
  
 若要有效地确定如何缩放 BizTalk Server 或 SQL 层，我们建议，负载测试是使用近似实际的生产数据的消息执行。 BizTalk Server 层之前，确保 SQL Server 不是已是瓶颈中的建议[监视 SQL Server 性能](../technical-guides/monitoring-sql-server-performance.md)。 如果 SQL Server 不是瓶颈，并且没有任何 BizTalk Server 计算机上的 CPU 余量，您可以通过修改主机实例布局提高吞吐量。 请务必建立四或五个关键性能指标 (Kpi)，作为高级比较点使用的所有测试运行。 以下这一建议，您将能够快速测量是否特定更改解决方案的总体性能下降。  
  
 向外扩展 SQL Server 层之前, 应用所有中优化[优化数据库性能](../technical-guides/optimizing-database-performance.md)。 在客户性能实验室的课程中，发现就是该磁盘的存储配置，MessageBox 和 TempDb 数据库特别是可以提供超过 30%吞吐量改进。 缩放到多个 MessageBox 数据库，因为没有什么性能好处时向外扩展的单个 MessageBox 数据库中，到两个 MessageBox 数据库使用三个和四个 MessageBox 数据库。 有关向外扩展 BizTalk Server MessageBox 的详细信息，请参阅[缩放出 SQL Server 层](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075) BizTalk Server 文档中。  
  
## <a name="implemented-optimizations"></a>实现的优化  
 本部分提供所有已应用于实验室测试方案的优化的清单。  
  
> [!NOTE]  
>  这些应测试根据您的更改管理过程之前将其在生产环境中应用。  
  
 以系统化、 可控制的方式应用优化-通过应用一系列优化，然后测试影响 — 将导致最大性能优势。 定期测试优化的影响的情况下应用优化实际上可能会导致性能下降的解决方案。  
  
### <a name="checklists-of-optimizations-applied"></a>应用了优化的检查表  
 **平台和网络优化**  
  
|Optimization|参考|  
|------------------|---------------|  
|BIOS： 配置性能设置。|[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)|  
|禁用 SQL Server 文件上的实时扫描。|[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)|  
|启用"高性能"电源计划在所有 BizTalk Server 和 SQL Server 计算机上。|[优化操作系统性能的通用指南](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
|所有 BizTalk Server 和 SQL Server 计算机上禁用防病毒软件。|[优化操作系统性能的通用指南](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
  
 **SQL Server 优化： 常规**  
  
|Optimization|参考|  
|------------------|---------------|  
|设置为 64 KB NTFS 文件分配单元。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|安装 SQL Server 2008 R2。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|配置 SQL Server 2008 R2 数据收集器/仓库。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|请确保已将相应的 Windows 权限扩展到 SQL Server 服务帐户。|SQL Server 2008 R2:[服务帐户设置 Windows](http://go.microsoft.com/fwlink/?LinkID=132144) (http://go.microsoft.com/fwlink/?LinkID=132144)|  
|设置 SQL Server 的最小值和最大服务器内存。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|授予到用于 SQL Server 的帐户的 Windows 锁定内存页特权。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|预调整到适当大小的 BizTalk Server 数据库的大小与多个数据文件...|[配置后数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|配置 SQL Server 客户端协议。|[故障排除 SQL Server](http://go.microsoft.com/fwlink/?LinkID=154250) (http://go.microsoft.com/fwlink/?LinkID=154250)|  
|将 tempdb 数据库拆分为多个大小相等的 BizTalk Server 使用的每个 SQL Server 实例上的数据文件|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|手动设置 SQL Server 进程关联|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|配置 MSDTC 和禁用 DTC 跟踪|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|启用跟踪标志 T1118 作为引导参数的所有实例的 SQL Server|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
  
 **SQL Server 优化： BizTalk 数据库**  
  
|Optimization|参考|  
|------------------|---------------|  
|将自动增长的 BizTalk 数据库设置为固定的值并不是百分比值。|[配置后数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|移动/拆分 BizTalk 数据库数据和日志文件，以单独的 LUN。|[配置后数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|请考虑设置上特定 MessageBox 数据库表的 'text in row 表选项|[配置后数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
  
 **BizTalk 优化**  
  
|Optimization|参考|  
|------------------|---------------|  
|单独的接收端口、 发送端口、 业务流程和单独的专用主机上的跟踪。|[一般 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|配置轮询间隔。|[低延迟方案 Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|调整 BizTalk 配置文件最大连接属性。|"Increase SOAP 和 HTTP 更改 maxconnection 参数的值所允许的并发连接数"部分中的[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|在 BizTalk Server 的每个节点上定义每个主机实例的 CLR Hosting 参数：<br /><br /> 最大 IO 线程数： 250<br /><br /> 最大工作线程数： 100<br /><br /> 最小 IO 线程数： 25<br /><br /> 最小工作线程数： 25|"定义的 CLR 承载 BizTalk 主机实例的线程值"部分中的[常规 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|进程内消息和内部消息队列大小限制提高为 10000。|[低延迟方案 Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|禁用 BizTalk Server 组级别跟踪。|[一般 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|管理并发执行隔离的接收的位置、 后端 Web 服务和 IIS 7.5 和 IIS 7.0 集成模式下运行的 WCF 服务可以托管的 ASP.NET 4 Web 应用程序请求数|[一般 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|禁用 BizTalk Server 主机阻止|[一般 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|配置 MSDTC 和禁用 DTC 跟踪|[一般 BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
  
 **WCF 配置优化**  
  
|Optimization|参考|  
|------------------|---------------|  
|对于每个 WCF 服务，应用 serviceThrottling 服务行为，并将设置**maxConcurrentCalls**并**maxConcurrentSessions**为 200。|[优化 BizTalk Server WCF 适配器性能](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)|  
|后端 WCF 服务配置文件中配置 serviceThrottling 行为的使用情况。|[优化 WCF Web 服务性能](../technical-guides/optimizing-wcf-web-service-performance.md)|  
  
## <a name="see-also"></a>请参阅  
 [缩放 BizTalk Server 生产环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)