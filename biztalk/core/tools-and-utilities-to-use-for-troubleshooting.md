---
title: 工具和实用程序用于故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c817384f-e328-439d-9c41-a94ed75670ce
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b13d6d57ff393fd5ec1336ec1639ba58fd8cda23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379829"
---
# <a name="tools-and-utilities-to-use-for-troubleshooting"></a>工具和实用程序用于故障排除
本部分介绍几个工具和实用程序，也可用于诊断 Microsoft BizTalk Server 组件或依存关系中的问题的根本原因。  
  
## <a name="event-viewer"></a>事件查看器  
 BizTalk Server 日志的信息，警告和错误记录到 BizTalk Server 事件日志基于计算机。 故障排除时 BizTalk Server 组件或依存关系中的问题，事件日志应查找信息以帮助诊断问题的第一个位置。 
  
## <a name="network-monitor"></a>网络监视器  
 使用网络监视器实用工具捕获 BizTalk Server 与远程客户端或服务器之间的网络流量。 然后可以分析捕获的网络流量来诊断网络相关的问题。  
  
 网络监视器是 Windows 服务器上可用。  
  
 网络监视器功能用于 Windows XP 通过使用 NETCAP.exe 实用程序随 Windows XP CD 上提供的 Windows 支持工具一起安装。 有关 NETCAP.exe 实用程序，请参阅详细信息[网络监视器捕获实用程序的说明](http://go.microsoft.com/fwlink/?LinkId=66227)。  
  
 有关如何捕获网络流量使用网络监视器的信息，请参阅[如何捕获网络流量使用网络监视器](http://go.microsoft.com/fwlink/?LinkId=66230)。  
  
## <a name="fiddler-tool"></a>Fiddler 工具  
 使用 Fiddler 来记录 BizTalk Server 与远程客户端或服务器之间的所有 HTTP 流量。 Fiddler 与 Visual Studio Team Edition for Testers 兼容，并允许您记录另存为可以添加到 Visual Studio Team Edition for Testers 项目的 Web 测试文件。  
  
 Fiddler 的缺点是，它目前不支持 SSL，不会自动跟踪隐藏的字段，如视图状态，并不筛选依存请求。  
  
 Fiddler，请参阅[ http://www.fiddlertool.com ](http://go.microsoft.com/fwlink/?LinkId=119605)。 
  
## <a name="sql-server-profiler"></a>SQL Server Profiler  
 Microsoft SQL Server Profiler 可用于捕获发送到 SQL Server 的 TRANSACT-SQL 语句和 SQL Server 结果集从这些语句。 由于 BizTalk Server 与 SQL Server 紧密集成，SQL Server 配置文件跟踪分析可以是用于分析在 BizTalk Server 中读取和写入到 SQL Server 数据库时可能发生的问题的有用工具。 
  
## <a name="sql-server-query-editor"></a>SQL Server 查询编辑器  
 SQL Server 查询编辑器可以用于直接对 SQL Server 数据库执行 SQL 语句。 此功能可能对于查询 BizTalk Server 数据库，或者在某些情况下 BizTalk Server 数据库更新。 
  
## <a name="dtctester"></a>DTCTester  
 大多数 BizTalk Server 运行时操作都需要 Microsoft 分布式事务处理协调器 (MSDTC) 支持，以确保操作事务性一致。 如果没有 MSDTC 事务支持，则相关联的 BizTalk Server 运行时操作将无法进行。 使用 DTCTester 工具可跨防火墙或针对网络验证分布式的事务支持。 由于 DTCTester 实用程序使用 ODBC 验证对 SQL Server 数据库的事务支持，并因此需要一个所测试的计算机上安装了 SQL Server。 有关 DTCTester 的详细信息请参阅[如何使用 DTCTester 工具](http://support.microsoft.com/kb/293799)。  
  
## <a name="dtcping"></a>DTCPing  
 使用 DTCPing 工具可跨防火墙或针对网络验证分布式的事务支持。 DTCPing 工具必须在客户端和服务器计算机上安装在任何一台计算机上未安装 SQL Server 时，由于 DTCTester 实用程序的良好替代方法。 有关使用 DTCPing 验证分布式的事务支持的详细信息请参阅[如何对 MS DTC 防火墙问题进行故障排除](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)。  
  
## <a name="performance-console"></a>性能控制台  
 使用性能控制台捕获性能监视 BizTalk Server 环境中的数据。 请参阅[性能计数器](../core/performance-counters.md)有关 BizTalk Server 附带的性能计数器的完整列表。 
  
## <a name="regmon-filemon-and-debugview"></a>RegMon、 FileMon 和 DebugView  
 列出对注册表的应用程序进行，每次调用并记录结果，RegMon 实时显示注册表访问活动。 此工具可以识别应用程序无法访问注册表项时。 同样，FileMon 显示文件系统活动在真实时间中列出的应用程序每次系统调用并注册结果。 Debugview 可让你监视可通过 TCP/IP 访问的网络上的任何计算机或在本地系统上的调试结果。  
  
 RegMon 和 FileMon 使管理员能够测试应用程序，并以确定应用程序对注册表或文件系统的任何调用失败。 管理员可以缓解该错误，例如，通过更改文件系统或注册表项的权限。  
  
 DebugView 使管理员能够测试应用程序并监视可通过 TCP/IP 访问的网络上的任何计算机或在本地系统上的调试结果。  
  
 有关这些实用工具的详细信息，请参阅[Windows Sysinternals](https://docs.microsoft.com/sysinternals/)。 
  
## <a name="debug-diagnostics-tool-of-the-iis-diagnostics-toolkit"></a>IIS 诊断工具包的调试诊断工具  
 IIS 诊断工具包的调试诊断工具可以生成对失败的进程的内存转储，并执行生成的转储文件的基本分析。 有关使用 IIS 诊断工具包的调试诊断工具捕获内存转储的详细信息请参阅[如何捕获 BizTalk 进程的内存转储](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)。