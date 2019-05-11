---
title: 解决 SQL Server 权限问题的准则 |Microsoft Docs
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
ms.openlocfilehash: 54d7a26d4c781ea27c2cefa19540025b0688e9b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344856"
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a>解决 SQL Server 权限问题的准则
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 广泛使用的 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库的运行时操作和这种情况下，它是重要的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]正确设置权限。 本主题提供一些通用准则来最小化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]权限问题，您可以执行进行故障排除步骤[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]权限问题的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="general-guidelines"></a>通用指导原则  
  
- **使用 BizTalk Server 的多计算机安装的域用户和组**  
  
   配置时，必须使用域用户组和帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要在多计算机方案中运行其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]单独的计算机上安装。 不要尝试配置或运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中*直通*，由此避免使用域组和帐户的每台计算机创建配对的用户名和密码的身份验证方案。 虽然此类直通方案可能看起来正常工作，在某些情况下，这将导致[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法在其他情况下，不受支持的配置。  
  
   有关安装和配置详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多计算机配置中，下载安装指南，网址[相关的安装指南与 BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582)。  
  
- **请确保在相应的 SQL Server 角色中定义的相应的 Windows 用户和组**  
  
   请验证正确[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]主题中的表中列出的角色成员身份[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
- **用户 SQL Server Profiler 诊断权限问题**  
  
   设置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Profiler 跟踪来监视**审核登录失败事件**来收集有关权限错误的详细的信息。 有关如何使用信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Profiler，请参阅[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a>随 BizTalk Server 一起安装的 SQL Server 作业无法执行  
  
##### <a name="problem"></a>问题  
 使用安装的 SQL Server 作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中生成失败，错误如下所示[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用程序日志：  
  
 事件类型：警告  
  
 事件源：SQLSERVERAGENT  
  
 事件类别：作业引擎  
  
 事件 ID：208  
  
 日期:6/29/2008  
  
 时间：下午 4:45:01  
  
 用户：不可用  
  
 计算机：*SQLServer*  
  
 说明:  
  
 SQL Server 计划的作业备份 BizTalk Server  
  
 (0x4AC7C44A48541443927A56C5C6699ECF)-状态：失败-调用时间：2008-6-29 13:45:01-消息：作业失败。  Schedule 305 (MarkAndBackupLogSched) 调用了该作业。 若要运行的最后一步是步骤 1 (BackupFull)。  
  
 **-和-**  
  
 事件类型：信息  
  
 事件源：MSSQLSERVER  
  
 事件类别：(4)  
  
 事件 ID：17055  
  
 日期:6/29/2008  
  
 时间：下午 4:45:01  
  
 用户：不可用  
  
 计算机：*SQLServer*  
  
 说明:  
  
 18456:用户 NT AUTHORITY\SYSTEM 登录失败。  
  
##### <a name="cause"></a>原因  
 如果已从删除了 BUILTIN\Administrators 登录名，可能出现此错误[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 如果删除了 BUILTIN\Administrators 登录名，则 sqlmaint.exe 将无法登录到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]这将阻止 SQL 作业运行。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，重新创建 BUILTIN\Administrators 登录名，并将其添加到 db_owner 角色[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和 Master 数据库。  
  
## <a name="see-also"></a>请参阅  
 [故障排除 SQL Server](../core/troubleshooting-sql-server.md)   
 [故障排除的 BizTalk Server 权限](../core/troubleshooting-biztalk-server-permissions.md)