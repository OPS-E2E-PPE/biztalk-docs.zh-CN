---
title: 故障排除 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6707c5-7c6e-4375-bfa6-9b1a86ec5e81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6418194021678080da3166c359e2b9e14072f221
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004462"
---
# <a name="troubleshooting-sql-server"></a>故障排除 SQL Server
影响 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的大多数 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 问题主要分为以下几类：  
  
- 与连接相关的问题  
  
- 与权限相关的问题  
  
- 数据库大小的问题  
  
  本主题分别介绍这些类别以及可采取的解决这些相关问题的步骤。  
  
## <a name="connectivity-related-problems"></a>与连接相关的问题  
 以下是与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机和包含 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机之间的连接问题相关的最普遍的问题。   
  
#### <a name="errors-related-to-failed-transactions-or-communication-with-the-underlying-transaction-manager-errors-are-written-to-the-biztalk-server-application-log"></a>与失败事务相关的错误或“与底层事务管理器通信”错误被写入到 BizTalk Server 应用程序日志  
  
##### <a name="problem"></a>问题  
 指示 MSDTC 事务失败或与底层事务管理器进行通信失败的错误将写入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志。  
  
##### <a name="cause"></a>原因  
 之间的 MSDTC 连接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]已失败。  
  
##### <a name="resolution"></a>解决方法  
 有关故障排除之间的 MSDTC 连接信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。  
  
#### <a name="error-a-connection-was-successfully-established-with-the-server-but-then-an-error-occurred-during-the-pre-login-handshake-occurs-when-connecting-to-remote-sql-server-databases-on-sql-server-2008"></a>连接到 SQL Server 2008 上的远程 SQL Server 数据库时发生以下错误：“已与服务器成功建立连接，但是在预登录握手时发生错误”  
  
##### <a name="problem"></a>问题  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 断开与远程连接[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成数据库和一条错误消息：  
  
##### <a name="cause"></a>原因  
 如果出现以下条件中的一个或多个，就可能出现此问题：  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 未配置为接受远程连接。  
  
- 所需的协议[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]未启用任一[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]正在运行的客户端计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
##### <a name="resolution"></a>解决方法  
 请遵循以下步骤来解决此问题：  
  
- **SQL Server 外围应用配置**工具不可用 SQL Server 2008 上。 若要远程连接 SQL Server 2008 计算机上的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，请按照 SQL Server 2008 联机帮助中的说明执行操作。  
  
- 使用**SQL Server 配置管理器**工具来启用**TCP/IP**和/或**Named Pipes**协议上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
  1.  单击**启动**，依次指向**所有程序**，然后单击**SQL Server 配置管理器**。  
  
  2.  单击此项可展开**SQL Server 网络配置**，然后单击**MSSQLSERVER 的协议**。  
  
  3.  右键单击**TCP/IP**协议，然后单击**启用**。  
  
  4.  右键单击**Named Pipes**协议，然后单击**启用**。  
  
  5.  关闭**SQL Server 配置管理器**工具。  
  
- 使用**SQL Server 配置管理器**工具来启用**TCP/IP**和/或**Named Pipes**协议上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]运行的客户端计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
  1.  单击**启动**，依次指向**所有程序**，然后单击**SQL Server 配置管理器**。  
  
  2.  单击此项可展开**SQL Server 网络配置**，然后单击**ClientProtocols**。  
  
  3.  右键单击**TCP/IP**协议，然后单击**启用**。  
  
  4.  右键单击**Named Pipes**协议，然后单击**启用**。  
  
  5.  关闭**SQL Server 配置管理器**工具。  
  
  > [!NOTE]
  >  确保至少一个协议上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]正在运行的客户端计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]匹配启用的协议[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
#### <a name="a-biztalk-host-instance-fails-and-a-general-network-error-is-written-to-the-application-log-when-the-biztalk-server-based-server-processes-a-high-volume-of-documents"></a>BizTalk 主机实例失败并且当基于 BizTalk Server 的服务器处理大量文档时，"常规网络"错误被写入到应用程序日志  
  
##### <a name="problem"></a>问题  
 处理大量文档时，BizTalk 主机实例失败，并且一个“常规网络”错误被写入应用程序日志。  
  
##### <a name="cause"></a>原因  
 出现此问题的原因是 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 实现了一个安全功能，该功能可以减小与服务器的并发 TCP/IP 连接队列的大小。 此功能有助于防止拒绝服务攻击。  
  
##### <a name="resolution"></a>解决方法  
 有关解决此问题的详细信息，请参阅[避免出现 DBNETLIB 异常](../core/avoiding-dbnetlib-exceptions.md)。  
  
## <a name="permissions-related-problems"></a>与权限相关的问题  
  
#### <a name="biztalk-server-run-time-or-design-time-operations-fail-and-a-cannot-open-database-requested-in-login-database-error-is-written-to-the-application-log-of-the-biztalk-server-or-sql-server-computer"></a>BizTalk Server 运行时或设计时操作将失败，和一个"无法打开登录中所请求的数据库\<数据库\>"错误写入到 BizTalk Server 或 SQL Server 计算机的应用程序日志  
  
##### <a name="problem"></a>问题  
 运行时或设计时操作失败，并且类似于以下的错误写入到的应用程序日志[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机：  
  
 无法打开登录中所请求的数据库\<*数据库*\>。 登录失败。   
用户登录失败\<*用户名*\>。  
  
##### <a name="cause"></a>原因  
 如果指定的帐户不属于相应的 Windows 组，可能出现此错误或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]角色。  
  
##### <a name="resolution"></a>解决方法  
 确保指定的帐户是相应的 Windows 组的成员或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]角色。 有关适当成员身份的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
## <a name="database-sizing-problems"></a>关于数据库大小的问题  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库增长取消选中然后的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境将受到负面影响。 请遵循以下步骤来管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库的增长。  
  
#### <a name="the-biztalk-server-messagebox-database-is-growing-unchecked-and-impacting-overall-performance"></a>BizTalk Server MessageBox 数据库不断无限增长，会影响到整体性能。  
  
##### <a name="problem"></a>问题  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库的增长会对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境的性能产生不利影响。  
  
##### <a name="cause"></a>原因  
 如果 SQL 代理作业的维护，会出现此问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库未运行。  
  
##### <a name="resolution"></a>解决方法  
 确保 SQL 代理作业维护的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库正在运行。 请参阅[数据库结构和作业](../core/database-structure-and-jobs.md)有关随一起安装的 SQL 代理作业的完整列表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
#### <a name="the-biztalk-server-tracking-database-is-growing-unchecked-and-impacting-overall-performance"></a>BizTalk Server 跟踪数据库不断无限增长，会影响到整体性能。  
  
##### <a name="problem"></a>问题  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪数据库不断无限增长和产生负面影响的整体性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
##### <a name="cause"></a>原因  
 如果不采取的步骤来清除和存档，会出现此问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪数据库。  
  
##### <a name="resolution"></a>解决方法  
 应采取步骤来清除和存档[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪数据库。 请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)有关详细信息。  
  
## <a name="see-also"></a>请参阅  
 [解决 SQL Server 权限问题的准则](../core/guidelines-for-resolving-sql-server-permissions-problems.md)