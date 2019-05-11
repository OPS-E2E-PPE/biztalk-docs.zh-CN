---
title: 附录 D：性能度量工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 024f4a08-f3fd-4786-8549-0da5463c0bb9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55e4eb3132bd953ff5cf2d525442f61b4c635582
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401391"
---
# <a name="appendix-d-tools-for-measuring-performance"></a>附录 D：性能度量工具
本主题介绍可用于监视和评估 BizTalk Server 环境的性能的几个工具。  
  
## <a name="performance-analysis-of-logs-pal-tool"></a>性能日志分析 (PAL) 工具  
 [PAL 工具](https://github.com/clinthuffman/PAL)用于生成基于 HTML 的报告以图形方式绘制图表重要性能监视器计数器和超出这些计数器的阈值时，将生成警报。 PAL 是解决方案的用于标识 BizTalk Server 解决方案，以便相应分配资源时优化性能中的瓶颈的理想工具。 
  
> [!NOTE]  
>  使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。  
  
## <a name="performance-monitor"></a>性能监视器  
 性能监视器提供了内置 Windows 性能计数器、 实时或作为一种方法来查看历史数据的可视化显示。  
  
## <a name="log-parser"></a>日志分析程序  
 Log parser 是 Windows® 操作系统 （如事件日志、 注册表、 文件系统和活动提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及关键的数据源的通用查询访问的功能全面的强大工具Directory®。 下载[日志分析程序](https://www.microsoft.com/download/details.aspx?id=24659)。
  
## <a name="relog"></a>重新记录  
 重新记录实用工具用于从性能监视器创建的日志提取性能计数器，并将数据转换成其他格式，如制表符分隔的文本文件 (文本 TSV)、 逗号分隔的文本文件 (文本 CSV)、 二进制文件和 SQL 数据库。 此数据可以再进行分析，使用诸如 Log Parser 之类的其他工具来生成关键绩效指标 (Kpi) 的统计信息查询。 
  
## <a name="loadgen"></a>LoadGen  
 BizTalk LoadGen 2007 是用来对 BizTalk Server 运行性能和压力测试的负载生成工具。 下载[BizTalk LoadGen 2007 工具](https://www.microsoft.com/download/details.aspx?id=14925)。
  
## <a name="visual-studio-team-system-load-testing"></a>Visual Studio Team System 负载测试  
 Visual Studio Team System (VSTS) 提供了用于创建和运行负载测试工具。 请参阅[测试应用程序](https://docs.microsoft.com/vsts/manual-test/overview)。
  
## <a name="bizunit"></a>BizUnit  
 BizUnit 是一个框架，专为 BizTalk Server 解决方案的自动测试。 BizUnit 是测试端到端 BizTalk Server 方案的理想工具。 请参阅[BizUnit](https://github.com/BizUnit/BizUnit)。
  
> [!NOTE]  
>  使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter 是用于测量磁盘 I/O 性能的开放源代码工具。 请参阅[ http://www.iometer.org ](http://www.iometer.org/)。
  
> [!NOTE]  
>  使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。  
  

## <a name="pathping"></a>pathping  
 Pathping 上某个目标主机的方式提供有关在一个或多个路由器跃点处的数据可能丢失的信息。 为此，请 pathping 将 Internet 控制消息协议 (ICMP) 数据包发送到路径中每个路由器中。 
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>性能监视和优化的 SQL Server 工具  
SQL Server 提供了几个工具，用于监视 SQL Server 中的事件和优化物理数据库设计。 请参阅[性能监视和优化工具](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)。 
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft SQL Server Profiler 可用于捕获发送到 SQL Server 的 TRANSACT-SQL 语句和 SQL Server 结果集从这些语句。 SQL Server 与 SQL Server 紧密集成，因为 SQL Server 配置文件跟踪分析可以是用于分析在 BizTalk Server 中读取和写入到 SQL Server 数据库时可能发生的问题的有用工具。 请参阅[使用 SQL Server Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler-templates-and-permissions)。
  
> [!IMPORTANT]  
>  没有与运行 SQL Profiler 相关联的增加大量开销。 因此 SQL Profiler 是最适合在测试或开发环境中使用。 如果使用 SQL Profiler 来解决生产环境中，了解关联的开销成本，并相应地限制 SQL Profiler 的使用。  
> 
>  当使用 SQL Profiler 来捕获 TRANSACT-SQL 语句，配置 SQL Profiler，以生成输出到的本地驱动器，而不是驱动器位于远程网络共享或其他慢速设备，例如，在本地的 USB 记忆棒。  
  
### <a name="sql-trace"></a>SQL 跟踪  
 SQL Server 提供 TRANSACT-SQL 系统存储过程的 SQL Server 数据库引擎实例上创建跟踪。 这些系统存储过程可以用于从您自己的应用程序中手动，而不是使用 SQL Server Profiler 创建跟踪。 这样，您就可以针对企业的特定需求编写自定义应用程序。 请参阅[SQL 跟踪](https://docs.microsoft.com/sql/relational-databases/sql-trace/sql-trace)。 
  
> [!NOTE]  
>  当使用 SQL 跟踪捕获 TRANSACT-SQL 语句配置 SQL 跟踪，以生成输出到本地驱动器而不是位于远程网络共享或其他慢速设备上的驱动器时，如 USB 闪存驱动器。  
  
### <a name="sql-activity-monitor"></a>SQL 活动监视器  
SQL Server 活动监视器提供了有关 SQL Server 进程以及这些进程如何影响 SQL Server 的当前实例的信息。 请参阅[活动监视器](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)，和[如何：打开活动监视器 (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)。 
  
### <a name="sql-server-data-collection"></a>SQL Server 数据收集  
SQL Server 提供了一个数据收集器，可用于获取和保存从多个源收集的数据。 数据收集器，可使用数据收集容器，使您能够确定作用域和运行 SQL Server 的计算机上的数据收集的频率。 请参阅[数据收集](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)。
  
### <a name="sqlio"></a>SQLIO  
 Microsoft 评估给定配置的 I/O 容量开发 SQLIO 工具。 该工具的名称可以看出，SQLIO 是一个重要的工具，用于测量上的 SQL Server 性能的文件系统 I/O 的影响。 下载[SQLIO](https://www.microsoft.com/download/details.aspx?id=20163)。