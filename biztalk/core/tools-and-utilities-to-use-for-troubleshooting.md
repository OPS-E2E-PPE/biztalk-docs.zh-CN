---
title: "工具和实用程序用于故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c817384f-e328-439d-9c41-a94ed75670ce
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86eab8504ab3dff93370783cca6c8fce1a0b9388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tools-and-utilities-to-use-for-troubleshooting"></a>用于故障排除的工具和实用程序
本部分介绍的若干工具和实用程序可用于诊断 Microsoft 中的问题的根本原因[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件或依赖项。  
  
## <a name="event-viewer"></a>事件查看器  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将信息、 警告和错误记录到事件日志的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基于计算机。 中的问题进行故障排除时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事件日志组件或依赖关系，应为第一个要查找信息以帮助诊断问题的位置。 有关事件查看器的详细信息，请参阅 Windows 文档。  
  
## <a name="network-monitor"></a>网络监视器  
 使用网络监视器实用工具来捕获之间的网络流量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与远程客户端或服务器。 然后，分析捕获的网络流量可以诊断网络相关问题。  
  
 网络监视器位于[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]通过**添加/删除 Windows 组件**中可用的选项**添加/删除程序**。  
  
 Windows XP 通过使用 NETCAP.exe 实用程序（随 Windows XP CD 上的 Windows 支持工具一起安装）来提供网络监视器功能。 有关更多信息 NETCAP.exe 实用程序，请参阅[网络监视器捕获实用程序的说明](http://go.microsoft.com/fwlink/?LinkId=66227)。  
  
 有关如何捕获网络流量的网络监视器信息请参阅[如何捕获网络流量的网络监视器](http://go.microsoft.com/fwlink/?LinkId=66230)。  
  
## <a name="fiddler-tool"></a>Fiddler 工具  
 使用 Fiddler 来记录之间的所有 HTTP 流量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与远程客户端或服务器。 Fiddler 与 Visual Studio Team Edition for Testers 兼容，允许您将记录另存为可以添加到 Visual Studio Team Edition for Testers 项目的 Web 测试文件。  
  
 Fiddler 的缺点是目前不支持 SSL，不自动跟踪隐藏字段，如 ViewState，以及不筛选依存请求。  
  
 Fiddler 位于[http://www.fiddlertool.com](http://go.microsoft.com/fwlink/?LinkId=119605)。有关如何使用 Fiddler 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=84814](http://go.microsoft.com/fwlink/?LinkId=84814)。  
  
## <a name="sql-server-profiler"></a>SQL Server 事件探查器  
 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]探查器可以用于捕获发送到的 TRANSACT-SQL 语句[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]从这些语句的结果集。 由于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与紧密集成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，分析[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]跟踪配置文件可以是用于分析在 BizTalk Server 中读取和写入时可能发生的问题的有用工具[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。 有关如何使用 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler 的信息，请参阅 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 文档。  
  
## <a name="sql-server-query-editor"></a>SQL Server 查询编辑器  
 SQL Server 查询编辑器可用于直接对 SQL Server 数据库执行 SQL 语句。 在某些情况下，此功能对于查询 BizTalk Server 数据库或更新 BizTalk Server 数据库很有用。 有关查询编辑器的详细信息，请参阅 [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] 或 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] 文档。  
  
## <a name="dtctester"></a>DTCTester  
 大多数 BizTalk Server 运行时操作都需要 Microsoft 分布式事务处理协调器 (MSDTC) 支持，以确保操作事务性一致。 如果没有 MSDTC 事务支持，则相关联的 BizTalk Server 运行时操作将无法进行。 使用 DTCTester 工具可跨防火墙或针对网络验证分布式事务支持。 由于 DTCTester 实用程序使用 ODBC 验证对 SQL Server 数据库的事务支持，因此要求将 SQL Server 安装在要测试的一台计算机上。 有关 DTCTester 的详细信息请参阅[如何使用 DTCTester 工具](http://support.microsoft.com/kb/293799)。  
  
## <a name="dtcping"></a>DTCPing  
 使用 DTCPing 工具可跨防火墙或针对网络验证分布式事务支持。 DTCPing 工具必须同时安装在客户端和服务器计算机上，当这两台计算机中的任一计算机上没有安装 SQL Server 时，使用 DTCPing 来代替 DTCTester 实用程序将是一个非常好的选择。 有关使用 DTCPing 验证分布式的事务支持的详细信息请参阅[如何 MS DTC 防火墙问题进行疑难解答](http://go.microsoft.com/fwlink/?LinkId=61915)。  
  
## <a name="performance-console"></a>性能控制台  
 使用性能控制台可捕获 BizTalk Server 环境中的性能监视数据。 请参阅[性能计数器](../core/performance-counters.md)有关附带的性能计数器的完整列表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关如何使用性能控制台的详细信息，请参阅 Windows 文档。  
  
## <a name="regmon-filemon-and-debugview"></a>RegMon、FileMon 和 DebugView  
 RegMon 以实时方式显示注册表访问活动，列出应用程序对注册表的每次调用并记录结果。 此工具可以识别应用程序何时无法访问某个注册表项。 同样，FileMon 以实时方式显示文件系统活动，列出应用程序对注册表的每次调用并记录结果。 使用 Debugview 可以监视本地系统或可通过 TCP/IP 访问的网络计算机的调试结果。  
  
 RegMon 和 FileMon 使管理员能够测试应用程序并识别应用程序调用注册表或文件系统时出现的错误。 例如，通过更改文件系统或注册项权限，管理员可以缓解该错误。  
  
 DebugView 使管理员能够测试应用程序并监视本地系统或可通过 TCP/IP 访问的网络计算机的调试结果。  
  
 有关这些实用工具的详细信息，请参阅 Windows Sysinternals 网站在[http://www.microsoft.com/technet/sysinternals/default.mspx](http://go.microsoft.com/fwlink/?LinkId=66235)。  
  
## <a name="debug-diagnostics-tool-of-the-iis-diagnostics-toolkit"></a>IIS 诊断工具包的调试诊断工具  
 IIS 诊断工具包的调试诊断工具可以对失败的进程生成内存转储并对生成的转储文件进行基本分析。 有关使用 IIS 诊断工具包的调试诊断工具捕获的内存转储的详细信息请参阅[如何捕获 BizTalk 进程的内存转储](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)。