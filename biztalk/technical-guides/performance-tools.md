---
title: 性能工具 |Microsoft 文档
description: 调查 BizTalk Server 使用 BizUnit、 IOMeter、 业务流程探查器、 Log Parser、 LoadGen 和 SQL 工具的性能问题
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d26c17a-3eb9-41a5-b0dc-31b974bf3d9b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5cff86a15aed9a131ed16086d1aebb33739f5f2
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848933"
---
# <a name="performance-tools"></a>性能工具
本主题提供有关可用于评估 BizTalk Server 解决方案的性能的工具的信息。 本主题中所述的工具有不同的目的;一些旨在评估端到端性能，而其他专注于评估的 BizTalk Server 解决方案的特定方面的性能。  
 
## <a name="bizunit-and-bizunit-designer"></a>BizUnit 和 BizUnit 设计器  
 BizUnit 是一个框架，用于自动测试的 BizTalk 解决方案。 BizUnit 是测试端到端 BizTalk Server 方案的理想工具。 时执行的与 BizUnit BizTalk 解决方案的自动测试的主要侧重点在于[实现自动化测试](../technical-guides/implementing-automated-testing.md)本指南的部分。 请参阅[BizUnit](https://github.com/BizUnit/BizUnit)。
  
 BizUnit 设计器是一个 GUI，允许快速创建可以用于单元测试或进行系统测试分布式应用程序的 BizUnit 测试用例。 该工具位于[BizUnit 设计器](http://go.microsoft.com/fwlink/?LinkID=117917)。  
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter 是用于测量磁盘输入/输出性能的开放源工具。 请参阅[ http://www.iometer.org ](http://www.iometer.org/)。
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="log-parser"></a>日志分析程序  
 日志分析器是一个功能强大、 通用的工具，如事件日志、 注册表、 文件系统和活动 Windows® 操作系统提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及密钥的数据源的通用查询访问权限Directory®。 下载[日志分析程序](https://www.microsoft.com/download/details.aspx?id=24659)。
  
## <a name="microsoft-biztalk-loadgen"></a>Microsoft BizTalk LoadGen  
 BizTalk LoadGen 是用于对 BizTalk Server 中运行性能和压力测试的负载生成工具。 下载[BizTalk LoadGen 2007 工具](https://www.microsoft.com/download/details.aspx?id=14925)。
  
## <a name="pathping"></a>Pathping  
 Pathping 上某个目标主机的方式提供有关在一个或多个路由器跃点处的数据可能丢失的信息。 为此，请 pathping 将 Internet 控制消息协议 (ICMP) 数据包发送到路径中的每个路由器中。 Windows 2000 Server 以来 Pathping.exe 是适用于 Windows 的所有版本。  
  
## <a name="performance-analysis-of-logs-pal"></a>日志 (PAL) 的性能分析  
 PAL 工具用于生成包含基于 HTML 的报表，以图形方式图表重要的性能计数器，并且如果超出这些计数器的阈值，将生成警报。 PAL 是解决方案的极好工具，用于标识在 BizTalk Server 解决方案以便于相应的分配的资源时优化性能中的瓶颈。  
  
 有关性能分析的日志 (PAL) 工具的详细信息，请参阅[性能分析的日志 (PAL) 工具](https://github.com/clinthuffman/PAL)。
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="performance-monitor"></a>性能监视器  
 性能监视器以实时或查看历史数据的方式显示了内置的 Windows 性能计数器。  
  
## <a name="relog"></a>Relog  
 重新记录实用程序可用于从由性能监视器创建的日志提取性能计数器，并将数据转换为其他格式，如制表符分隔的文本文件 (文本 TSV)、 以逗号分隔的文本文件 (CSV 文本)、 二进制文件和 SQL 数据库。 此数据可以再进行分析，并且查询使用诸如 Log Parser 之类的其他工具来为关键绩效指标 (Kpi) 生成统计信息。 
  
## <a name="visual-studio---testing-the-application"></a>Visual Studio 的测试应用程序  
 Microsoft Visual Studio 旗舰版和专业版包括测试，以帮助你定义和管理通过使用测试计划测试工作量。 请参阅[测试应用程序](https://docs.microsoft.com/vsts/manual-test/overview)。
  
## <a name="visual-studio-profiling-tools"></a>Visual Studio 分析工具  
 使用 Visual Studio 分析工具，可配置文件自定义.NET 组件 （自定义管道组件、 管道和/或业务流程，自定义 functoid 由调用的帮助程序组件）。 请参阅，[使用分析工具来分析应用程序性能](https://docs.microsoft.com/visualstudio/profiling/performance-explorer)。
  
## <a name="windows-performance-analysis-tools"></a>Windows 性能分析工具  
Windows 性能工具旨在为大量的性能问题，包括应用程序开始时间，启动问题的分析延迟过程调用和中断活动 （Dpc 和 Isr） 系统的响应能力问题，应用程序资源使用情况和中断风暴。  
  
请参阅[Windows 性能分析](https://docs.microsoft.com/windows-hardware/test/weg/performance-tools)。
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>性能监视和优化的 SQL Server 工具  
 SQL Server 提供几种工具，用于监视 SQL Server 中的事件和优化物理数据库设计。 请参阅[性能监视和优化工具](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)。 
  
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
  
## <a name="see-also"></a>请参阅  
 [查找并消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)