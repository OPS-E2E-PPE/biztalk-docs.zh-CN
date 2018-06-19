---
title: 解决 SQL Server 的权限问题的准则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c24512-5f65-4363-b806-8dd52b22f179
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db02fd2a981d3f1dc34924e680caf5926f67871a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246901"
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a>解决 SQL Server 权限问题的准则
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在运行时操作中大量使用了 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库，因此，正确设置 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 权限非常重要。 本主题提供了最大限度地减少 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 权限问题的一些通用准则以及操作步骤，您可依照这些步骤来解决影响 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 权限问题。  
  
## <a name="general-guidelines"></a>通用指导原则  
  
-   **使用 BizTalk Server 的多计算机安装的域用户和组**  
  
     如果要配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使其在多计算机方案中运行（例如 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 安装在不同的计算机上），则必须使用域用户组和帐户。 请不要尝试配置或运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中*传递*凭此可以避免使用域组和帐户的每台计算机创建配对的用户名和密码的身份验证方案。 虽然在某些情况下，此类直通方案可能运行正常；但在其他情况下，这将导致 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 失败并且不是支持的配置。  
  
     有关安装和配置详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多计算机配置中，下载安装指南，网址[相关到 BizTalk Server 2013 的指南安装](http://go.microsoft.com/fwlink/p/?LinkID=269582)。  
  
-   **确保在相应的 SQL Server 角色中定义的相应的 Windows 用户和组**  
  
     请验证正确[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]主题中的表中列出的角色成员身份[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
-   **用户 SQL Server 事件探查器诊断权限问题**  
  
     设置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]探查器跟踪来监视**审核登录失败事件**来收集有关权限失败的详细的信息。 有关如何使用信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]探查器，请参阅[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a>随 BizTalk Server 一起安装的 SQL Server 作业无法执行  
  
##### <a name="problem"></a>问题  
 随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装的 SQL Server 作业失败，并在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 应用程序日志中生成类似于以下内容的错误：  
  
 事件类型: 警告  
  
 事件源： SQLSERVERAGENT  
  
 事件类别： 作业引擎  
  
 事件 ID: 208  
  
 2008-6 月 29 日日期：  
  
 时间： 下午 4:45:01  
  
 用户：无  
  
 计算机： *sql Server*  
  
 说明:  
  
 SQL Server 计划作业“备份 BizTalk Server”  
  
 (0x4AC7C44A48541443927A56C5C6699ECF) 的状态： 失败-调用： 2008年-6-29 13:45:01-消息： 作业失败。  Schedule 305 (MarkAndBackupLogSched) 调用了该作业。 最后运行的是步骤 1 (BackupFull)。  
  
 **-和-**  
  
 事件类型： 信息  
  
 事件源： MSSQLSERVER  
  
 事件类别: (4)  
  
 事件 ID: 17055  
  
 2008-6 月 29 日日期：  
  
 时间： 下午 4:45:01  
  
 用户：无  
  
 计算机： *sql Server*  
  
 说明:  
  
 18456： 用户 NT AUTHORITY\SYSTEM 登录失败。  
  
##### <a name="cause"></a>原因  
 如果从 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 中删除了 BUILTIN\Administrators 登录名，则会产生此错误。 如果 BUILTIN\Administrators 登录名被删除，则 sqlmaint.exe 将无法登录到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，这将阻止 SQL 作业运行。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请重新创建 BUILTIN\Administrators 登录名，并将其添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库和 Master 数据库的 db_owner 角色。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除 SQL Server](../core/troubleshooting-sql-server.md)   
 [BizTalk Server 权限的疑难解答](../core/troubleshooting-biztalk-server-permissions.md)