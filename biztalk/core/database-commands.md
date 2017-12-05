---
title: "数据库命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2232602ec5a91768f4b9dbde5f6c63a79de0c332
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="database-commands"></a>数据库命令
BAM 管理实用程序数据库命令允许你使用 BAM 数据库：  
  
-   安装程序数据库： 将创建所 BAM 特定数据库。  
  
-   迁移 sql： 迁移 BAM 数据库：  
  
    -   与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2000  
  
    -   与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2005  
  
-   启用引用： 启用对分布式 BAM 主导入数据库的引用。  
  
-   获取引用： 获取对分布式 BAM 主导入数据库的引用的列表。  
  
-   禁用参考： 禁用对 BAM 主导入数据库的引用。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="setup-databases-command"></a>安装程序数据库命令  
 **用法**  
  
 **bm.exe 安装程序数据库 ConfigFile:\<配置文件\>[-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\> ]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|ConfigFile:\<配置文件\>|BAM 配置文件从其创建数据库。|  
|NSUser:\<通知服务用户名\>|可选： 通知服务用户有权创建数据库用户 ID。|  
|NSUserPassword|可选： 指定的通知服务用户的密码。|  
  
 创建如果不存在配置文件 （BAM 主导入、 BAM 星型架构、 BAM 存档、 BAM 分析和警报） 中描述的数据库。 数据库创建后，命令将创建关联的 BAM 元数据的表和存储的过程。  
  
 如果你要设置 BAM 警报，则需要的 NSUser 和 NSUserPassword 参数。 如果未在命令行上指定 NSUserPassword，bm.exe 将提示你输入密码。  
  
> [!NOTE]
>  后该命令完成时，你可能注意到在跟踪日志中 AlertModule 中的发生异常：  
>   
>  “指定的帐户是数据库所有者。 数据库所有者始终拥有对视图的访问权限，并且不能添加到视图中或从视图中删除。”  
>   
>  此外，你可能会看到来自 NotificationServices #19001 的事件中的警告。  
>   
>  如果执行命令期间没有报告任何错误，你可以放心地忽略这些注意事项。  
  
> [!IMPORTANT]
>  如果使用 BAM 配置文件不包含警报部分中，执行安装程序数据库命令，并且你已配置 BAM 警报，bm.exe 将覆盖配置，以便警报将不再起作用。  
  
 若要设置的 BAM 数据库必须承载 BAMPrimaryImport、 BAMStarSchema 和 BAMArchive 数据库的 Microsoft SQL 服务器上具有管理员权限。 若要设置 SQL Notification Services 数据库，你必须具有管理员权限和是本地管理员组的成员，以及是任何其他附加管理组已配置，如 BTS 管理员组的成员。  
  
 **示例**  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a>迁移 sql 命令  
 **用法**  
  
 **bm.exe 迁移 sql-从： sql2000-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<服务器\> ][-数据库：\<数据库\>]**  
  
 \- 或 -  
  
 **bm.exe 迁移 sql-从： sql2005-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<服务器\> ][-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|从： sql2000|指定要从 Microsoft SQL Server 2000 数据库进行转换。|  
|到： sql2008|指定要将转换为 Microsoft SQL Server 2008 数据库。|  
|从： sql2005|指定你要从 Microsoft SQL Server 2005 数据库转换。|  
|到： sql2008|指定要将转换为 Microsoft SQL Server 2008 数据库。|  
|NSUser:\<通知服务用户名\>|可选： 通知服务用户有权创建数据库用户 ID。|  
|NSUserPassword|可选： 指定的通知服务用户的密码。|  
|服务器：\<服务器\>|可选： 转换后的数据库将驻留的服务器的名称。 服务器必须是与承载 Microsoft SQL Server 2008 数据库的计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 将其命名为的已转换的数据库。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 可以从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 的 BAM 基础结构迁移到 Microsoft SQL Server 2008。 你将数据库服务器和升级 Analysis server 从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 到 Microsoft SQL Server 2008 后，请使用此命令。  
  
 如果配置 BAM 警报，则需要的 NSUser 和 NSUserPassword 参数。 如果未在命令行上指定 NSUserPassword，bm.exe 将提示你输入密码。  
  
 若要迁移的 SQL Server Notification Services 数据库，你必须具有管理员权限和是本地管理员组的成员，以及是其他任何其他管理组的已配置，如 BTS 成员管理员组。  
  
> [!NOTE]
>  如果你收到错误消息"错误： 无法在计算机上启动服务 NS$ BAMAlerts\<计算机名称\>。 该服务未及时响应启动请求或控制请求。”，请手动重新启动该服务。 如果在迁移期间，SQL Server 是极其繁忙，服务可能无法重新启动。  
  
> [!NOTE]
>  Notification Services 的安装位置在计算机上运行迁移 sql 命令，你必须属于该计算机上的本地管理员组。  
  
 **示例**  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a>启用引用命令  
 **用法**  
  
 **bm.exe 启用引用 TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>[-Server:\<服务器\>] [-数据库：\<数据库\> ]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|TargetServer:\<目标服务器\>|引用已启用到服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。|  
|TargetDatabase:\<目标数据库\>|引用已启用到数据库的名称。|  
|服务器：\<服务器\>|可选： 将具有启用的引用的目标服务器和数据库服务器的名称。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 将具有对目标服务器和数据库启用的引用的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 启用对其他分布式 BAM 主导入数据库的引用。 这样可从当前数据库订阅目标 BAM 主导入数据库上的视图和活动元数据。 此功能可用于启用对分布式活动的导航。  
  
 可以指定目标服务器为一个 SQL Server 实例，例如“mymachine2\myinstance”。  
  
 **示例**  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a>get-references 命令  
 **用法**  
  
 **bm.exe get 引用 [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|服务器：\<服务器\>|可选： 若要获取的引用列表的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 用于获取的引用列表上的数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出执行此命令的计算机上所启用的引用。  
  
 **示例**  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a>disable-reference 命令  
 **用法**  
  
 **bm.exe 禁用引用 TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>[-Server:\<服务器\>] [-数据库：\<数据库\> ]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|TargetServer:\<目标服务器\>|要禁用引用的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。|  
|TargetDatabase:\<目标数据库\>|要禁用引用的数据库的名称。|  
|服务器：\<服务器\>|可选： 哪些引用到目标服务器和数据库位于要禁用服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 将哪些引用到目标服务器上的数据库和数据库的名称要禁用。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 禁用对目标服务器上其他分布式 BAM 主导入数据库的引用。  
  
 可以指定目标服务器为一个 SQL Server 实例，例如“mymachine2\myinstance”。  
  
 **示例**  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)