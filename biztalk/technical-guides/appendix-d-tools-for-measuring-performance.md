---
title: "附录 d： 工具以衡量性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 024f4a08-f3fd-4786-8549-0da5463c0bb9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19953e021a2416f777d9b28c14b1eb8516c70c81
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="appendix-d-tools-for-measuring-performance"></a>附录 d： 以衡量性能的工具
本主题介绍几种工具可用来监视和评估 BizTalk Server 环境的性能。  
  
## <a name="performance-analysis-of-logs-pal-tool"></a>性能日志分析 (PAL) 工具  
 [PAL 工具](https://github.com/clinthuffman/PAL)用于生成包含基于 HTML 的报表以图形方式绘制图表重要性能监视器计数器和超出这些计数器的阈值时，将生成警报。 PAL 是解决方案的极好工具，用于标识在 BizTalk Server 解决方案以便于相应的分配的资源时优化性能中的瓶颈。 
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="performance-monitor"></a>性能监视器  
 性能监视器以实时或查看历史数据的方式显示了内置的 Windows 性能计数器。  
  
## <a name="log-parser"></a>日志分析程序  
 日志分析器是一个功能强大、 通用的工具，如事件日志、 注册表、 文件系统和活动 Windows® 操作系统提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及密钥的数据源的通用查询访问权限Directory®。 下载[日志分析程序](https://www.microsoft.com/download/details.aspx?id=24659)。
  
## <a name="relog"></a>Relog  
 重新记录实用程序可用于从由性能监视器创建的日志提取性能计数器，并将数据转换为其他格式，如制表符分隔的文本文件 (文本 TSV)、 以逗号分隔的文本文件 (CSV 文本)、 二进制文件和 SQL 数据库。 此数据可以再进行分析，并且查询使用诸如 Log Parser 之类的其他工具来为关键绩效指标 (Kpi) 生成统计信息。 
  
## <a name="loadgen"></a>LoadGen  
 BizTalk LoadGen 2007 是用于对 BizTalk Server 中运行性能和压力测试的负载生成工具。 下载[BizTalk LoadGen 2007 工具](https://www.microsoft.com/download/details.aspx?id=14925)。
  
## <a name="visual-studio-team-system-load-testing"></a>Visual Studio Team System 负载测试  
 Visual Studio Team System (VSTS) 提供一个用于创建和运行负载测试工具。 请参阅[测试应用程序](https://docs.microsoft.com/vsts/manual-test/overview)。
  
## <a name="bizunit"></a>BizUnit  
 BizUnit 是一个框架，用于自动测试的 BizTalk Server 解决方案。 BizUnit 是测试端到端 BizTalk Server 方案的理想工具。 请参阅[BizUnit](https://github.com/BizUnit/BizUnit)。
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter 是用于测量磁盘输入/输出性能的开放源工具。 请参阅[http://www.iometer.org](http://www.iometer.org/)。
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  

## <a name="pathping"></a>Pathping  
 Pathping 上某个目标主机的方式提供有关在一个或多个路由器跃点处的数据可能丢失的信息。 为此，请 pathping 将 Internet 控制消息协议 (ICMP) 数据包发送到路径中的每个路由器中。 
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>性能监视和优化的 SQL Server 工具  
SQL Server 提供几种工具，用于监视 SQL Server 中的事件和优化物理数据库设计。 请参阅[性能监视和优化工具](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)。 
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft SQL Server 事件探查器可以用于捕获发送到 SQL Server 的 TRANSACT-SQL 语句和 SQL Server 结果设置从这些语句。 由于 SQL Server 与 SQL Server 紧密集成，SQL Server 配置文件跟踪的分析可能用于分析在 BizTalk Server 中读取和写入 SQL Server 数据库时可能发生的问题的有用工具。 请参阅[使用 SQL Server 事件探查器](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler-templates-and-permissions)。
  
> [!IMPORTANT]  
>  没有与运行 SQL 事件探查器相关联的增加大量开销。 因此，SQL 事件探查器是最适合在测试或开发环境中使用。 如果使用 SQL 事件探查器解决生产环境，请留意关联的开销成本，并相应地限制 SQL 事件探查器使用。  
> 
>  当使用 SQL 事件探查器捕获 TRANSACT-SQL 语句，配置 SQL 事件探查器以生成输出到的本地驱动器，而不是驱动器位于远程网络共享或其他慢速的设备，例如，在本地的 USB 记忆棒。  
  
### <a name="sql-trace"></a>SQL 跟踪  
 SQL Server 提供 TRANSACT-SQL 系统存储过程的 SQL Server 数据库引擎实例上创建跟踪。 这些系统存储过程可从自己的应用程序中手动创建跟踪，而不是使用 SQL Server 事件探查器。 这样，您就可以针对企业的特定需求编写自定义应用程序。 请参阅[SQL 跟踪](https://docs.microsoft.com/sql/relational-databases/sql-trace/sql-trace)。 
  
> [!NOTE]  
>  当使用 SQL 跟踪捕获 TRANSACT-SQL 语句，配置 SQL 跟踪，以生成输出到的本地驱动器，而不是位于远程网络共享或其他慢速设备上的驱动器时，例如 USB 闪存驱动器。  
  
### <a name="sql-activity-monitor"></a>SQL 活动监视器  
SQL Server 活动监视器提供有关 SQL Server 过程和了解这些进程如何影响当前的 SQL Server 实例的信息。 请参阅[活动监视器](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)，和[如何： 打开活动监视器 (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)。 
  
### <a name="sql-server-data-collection"></a>SQL Server 数据收集  
SQL Server 提供了可用于获取和保存数据，则通过多个来源收集的数据收集器。 数据收集器，可使用使你可以确定的范围和频率的运行 SQL Server 的计算机上的数据收集的数据集合容器。 请参阅[数据收集](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)。
  
### <a name="sqlio"></a>SQLIO  
 由 Microsoft 评估给定配置的 I/O 容量开发 SQLIO 工具。 该工具的名称可以看出，SQLIO 是用于测量的文件系统 I/O 对 SQL Server 性能的影响的重要工具。 下载[SQLIO](https://www.microsoft.com/download/details.aspx?id=20163)。