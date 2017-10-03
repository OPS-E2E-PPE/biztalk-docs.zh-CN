---
title: "性能工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d26c17a-3eb9-41a5-b0dc-31b974bf3d9b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c53894ca4dcf1b1541c020e14a83542a7ce56d56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="performance-tools"></a>性能工具
本主题提供有关可用于评估 BizTalk Server 解决方案的性能的工具的信息。 本主题中所述的工具有不同的目的;一些旨在评估端到端性能，而其他专注于评估的 BizTalk Server 解决方案的特定方面的性能。  
  
## <a name="biztalk-server-orchestration-profiler"></a>BizTalk Server 业务流程事件探查器  
 BizTalk Server 业务流程事件探查器可用于查看指定时间内跟踪数据的业务流程，并可用于确定在业务流程中存在性能瓶颈。  
  
 有关 BizTalk Server 业务流程事件探查器的详细信息，请参阅[BizTalk Server 2006 Orchestration 事件探查器](http://go.microsoft.com/fwlink/?LinkId=102209)(http://go.microsoft.com/fwlink/?LinkId=102209)。  
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。 另请注意此实用程序用于 BizTalk Server 2006 处理，并因此可能无法按预期工作 BizTalk Server 2010 上。  
  
## <a name="bizunit-30-and-bizunit-designer"></a>BizUnit 3.0 和 BizUnit 设计器  
 BizUnit 是一个框架，用于自动测试的 BizTalk 解决方案。 BizUnit 是测试端到端 BizTalk Server 方案的理想工具。 时执行的与 BizUnit BizTalk 解决方案的自动测试的主要侧重点在于[实现自动化测试](../technical-guides/implementing-automated-testing.md)本指南的部分。 有关 BizUnit 3.0 的详细信息，请参阅[BizUnit-框架，用于自动分布式系统的测试](http://go.microsoft.com/fwlink/?LinkID=85168)(http://go.microsoft.com/fwlink/?LinkID=85168)。  
  
 BizUnit 设计器是一个 GUI，允许快速创建可以用于单元测试或进行系统测试分布式应用程序的 BizUnit 测试用例。 该工具位于[BizUnit 设计器](http://go.microsoft.com/fwlink/?LinkID=117917)(http://go.microsoft.com/fwlink/?LinkID=117917)。  
  
> [!IMPORTANT]  
>  本指南中，生成测试用例撰写 BizUnit 设计器才与 BizUnit 兼容 1.x 2.x。  
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter 是用于测量磁盘输入/输出性能的开放源工具。 有关 IOMeter 的详细信息，请参阅[http://www.iometer.org](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412)。  
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="log-parser"></a>日志分析程序  
 日志分析器是一个功能强大、 通用的工具，如事件日志、 注册表、 文件系统和活动 Windows® 操作系统提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及密钥的数据源的通用查询访问权限Directory®。 Log Parser 是下载[日志分析器 2.2](http://go.microsoft.com/fwlink/?LinkID=100882) (http://go.microsoft.com/fwlink/?LinkID=100882)。  
  
## <a name="microsoft-biztalk-loadgen-2007"></a>Microsoft BizTalk LoadGen 2007  
 BizTalk LoadGen 2007 是用于运行性能和压力测试针对一个负载生成工具[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。  
  
 有关 Microsoft BizTalk LoadGen 2007 工具的详细信息，请参阅[Microsoft BizTalk LoadGen 2007 工具](http://go.microsoft.com/fwlink/?LinkId=59841)(http://go.microsoft.com/fwlink/?LinkId=59841)。  
  
## <a name="pathping"></a>Pathping  
 Pathping 上某个目标主机的方式提供有关在一个或多个路由器跃点处的数据可能丢失的信息。 为此，请 pathping 将 Internet 控制消息协议 (ICMP) 数据包发送到路径中的每个路由器中。 Windows 2000 Server 以来 Pathping.exe 是适用于 Windows 的所有版本。  
  
## <a name="performance-analysis-of-logs-pal"></a>日志 (PAL) 的性能分析  
 PAL 工具用于生成包含基于 HTML 的报表，以图形方式图表重要的性能计数器，并且如果超出这些计数器的阈值，将生成警报。 PAL 是解决方案的极好工具，用于标识在 BizTalk Server 解决方案以便于相应的分配的资源时优化性能中的瓶颈。  
  
 有关性能分析的日志 (PAL) 工具的详细信息，请参阅[性能分析的日志 (PAL) 工具](http://go.microsoft.com/fwlink/?LinkID=98098)(http://go.microsoft.com/fwlink/?LinkID=98098)。  
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="performance-monitor"></a>性能监视器  
 性能监视器以实时或查看历史数据的方式显示了内置的 Windows 性能计数器。  
  
## <a name="relog"></a>Relog  
 重新记录实用程序可用于从由性能监视器创建的日志提取性能计数器，并将数据转换为其他格式，如制表符分隔的文本文件 (文本 TSV)、 以逗号分隔的文本文件 (CSV 文本)、 二进制文件和 SQL 数据库。 此数据可以再进行分析，并且查询使用诸如 Log Parser 之类的其他工具来为关键绩效指标 (Kpi) 生成统计信息。 重新记录实用程序随附[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]和后续版本。  
  
## <a name="visual-studio-2010---testing-the-application"></a>Visual Studio 2010 的测试应用程序  
 Microsoft Visual Studio 2010 旗舰版和 Visual Studio 测试的 Professional 2010 现在包含新的应用程序调用 Microsoft 测试管理器来帮助你定义和管理通过使用测试计划测试工作量。 有关使用负载测试的详细信息，请参阅[测试应用程序](http://go.microsoft.com/fwlink/?LinkID=205342)(http://go.microsoft.com/fwlink/?LinkID=205342)。  
  
## <a name="visual-studio-2010-profiling-tools"></a>Visual Studio 2010 分析工具  
 使用 Visual Studio 分析工具，可配置文件自定义.NET 组件 （自定义管道组件、 管道和/或业务流程，自定义 functoid 由调用的帮助程序组件）。 有关 Visual Studio 分析工具，请参阅详细信息[使用分析工具分析应用程序性能](http://go.microsoft.com/fwlink/?LinkID=210555)(http://go.microsoft.com/fwlink/?LinkID=210555)。  
  
## <a name="windows-performance-analysis-tools"></a>Windows 性能分析工具  
 Windows 性能工具旨在为大量的性能问题，包括应用程序开始时间，启动问题的分析延迟过程调用和中断活动 （Dpc 和 Isr） 系统的响应能力问题，应用程序资源使用情况和中断风暴。  
  
 有关 Windows 性能分析工具的详细信息，请参阅[Windows 性能分析](http://go.microsoft.com/fwlink/?LinkId=139763)(http://go.microsoft.com/fwlink/?LinkId=139763)。  
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>性能监视和优化的 SQL Server 工具  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]提供多个工具来监视中的事件[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和优化物理数据库设计。 这些工具进行了介绍[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书主题[用于性能监视和优化工具](http://go.microsoft.com/fwlink/?LinkId=146357)(http://go.microsoft.com/fwlink/?LinkId=146357)。 有关特定工具用于信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]下面提供的性能监视和优化：  
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]探查器可以用于捕获发送到的 TRANSACT-SQL 语句[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]从这些语句的结果集。 因为[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]与紧密集成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，分析[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]跟踪配置文件可以是用于分析中可能会发生的问题的有用工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]读取和写入时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。 有关如何使用信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]探查器，请参阅[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]联机丛书主题[使用 SQL Server 事件探查器](http://go.microsoft.com/fwlink/?linkid=104423)(http://go.microsoft.com/fwlink/?linkid=104423)。  
  
> [!IMPORTANT]  
>  没有与运行 SQL 事件探查器相关联的增加大量开销。 因此，SQL 事件探查器是最适合在测试或开发环境中使用。 如果使用 SQL 事件探查器解决生产环境，请留意关联的开销成本，并相应地限制 SQL 事件探查器使用。  
  
> [!NOTE]  
>  当使用 SQL 事件探查器捕获 TRANSACT-SQL 语句，配置 SQL 事件探查器以生成输出到的本地驱动器，而不是驱动器位于远程网络共享或其他慢速的设备，例如，在本地的 USB 记忆棒。  
  
### <a name="sql-trace"></a>SQL 跟踪  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]提供 TRANSACT-SQL 系统存储过程的 SQL Server 数据库引擎实例上创建跟踪。 这些系统存储过程可从自己的应用程序中手动创建跟踪，而不是使用 SQL Server 事件探查器。 这样，您就可以针对企业的特定需求编写自定义应用程序。 有关使用 SQL 跟踪的详细信息，请参阅[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]联机丛书主题[简介 SQL 跟踪](http://go.microsoft.com/fwlink/?LinkId=146354)(http://go.microsoft.com/fwlink/?LinkId=146354)。  
  
> [!NOTE]  
>  当使用 SQL 跟踪捕获 TRANSACT-SQL 语句，配置 SQL 跟踪，以生成输出到的本地驱动器，而不是位于远程网络共享或其他慢速设备上的驱动器时，例如 USB 闪存驱动器。  
  
### <a name="sql-activity-monitor"></a>SQL 活动监视器  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]活动监视器相关信息提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]进程并了解这些进程如何影响的当前实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]活动监视器，请参阅[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]联机丛书主题[活动监视器](http://go.microsoft.com/fwlink/?LinkId=146355)(http://go.microsoft.com/fwlink/?LinkId=146355)。 有关如何打开活动监视器信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio，请参阅[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]联机丛书主题[如何： 打开活动监视器 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094)。  
  
### <a name="sql-server-2008-r2-data-collection"></a>SQL Server 2008 R2 数据收集  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 提供了一个数据收集器，您可以用它来获取和保存从多个源收集的数据。 通过数据收集器，您可以使用数据收集容器，这样便可确定对运行 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 的计算机进行数据收集的范围和频率。 有关实现详细信息[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]数据收集，请参阅[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]联机丛书主题[数据收集](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356)。  
  
### <a name="sqlio"></a>SQLIO  
 由 Microsoft 评估给定配置的 I/O 容量开发 SQLIO 工具。 SQLIO 工具的名称可以看出，是用于测量上的文件系统 I/O 的影响的重要工具[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能。 可以从下载 SQLIO [SQLIO 磁盘子系统基准工具](http://go.microsoft.com/fwlink/?LinkId=115176)(http://go.microsoft.com/fwlink/?LinkId=115176)。  
  
## <a name="see-also"></a>另请参阅  
 [查找并消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)