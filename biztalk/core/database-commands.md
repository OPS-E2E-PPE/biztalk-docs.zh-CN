---
title: 数据库命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5bb9d25db876fb7d48900b1ee47f187544a4b87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389775"
---
# <a name="database-commands"></a>数据库命令
BAM 管理实用程序的数据库命令使您能够使用 BAM 数据库：  
  
-   安装程序数据库：创建特定于 BAM 的数据库。  
  
-   migrate-sql:可以迁移从 BAM 数据库：  
  
    -   与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2000  
  
    -   与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2005  
  
-   启用的引用：启用对分布式 BAM 主导入数据库的引用。  
  
-   获取引用：获取对分布式 BAM 主导入数据库的引用的列表。  
  
-   禁用参考：禁用对 BAM 主导入数据库的引用。  
  
> [!NOTE]
>  通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="setup-databases-command"></a>设置数据库命令  
 **Usage**  
  
 **bm.exe 设置-数据库-ConfigFile:\<配置文件\>[-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|ConfigFile:\<配置文件\>|从其创建数据库的 BAM 配置文件。|  
|NSUser:\<通知服务用户名\>|可选：通知服务用户有权创建数据库用户 ID。|  
|NSUserPassword|可选：指定的通知服务用户的密码。|  
  
 创建配置文件 （BAM 主导入、 BAM 星型架构、 BAM 存档、 BAM 分析和警报） 中所述如果它们尚不存在的数据库。 一旦创建了数据库，该命令将创建关联的 BAM 元数据表和存储的过程。  
  
 如果您设置了 BAM 警报，则需要 NSUser 和 NSUserPassword 参数。 如果 NSUserPassword 未指定命令行上，则 bm.exe 会提示您输入密码。  
  
> [!NOTE]
>  之后该命令完成时，你可能注意到从跟踪日志中 AlertModule 异常：  
>   
>  "指定的帐户是数据库所有者。 数据库所有者始终有权访问视图并不能添加到或从视图中删除。"  
>   
>  此外，可能会看到从 NotificationServices #19001 事件中的警告。  
>   
>  如果该命令执行期间未不报告任何错误，可以安全地忽略这些声明。  
  
> [!IMPORTANT]
>  如果使用的 BAM 配置文件不包含警报部分，执行安装程序数据库命令，并且已配置了 BAM 警报，bm.exe 将覆盖配置，以便警报将不再起作用。  
  
 若要设置 BAM 数据库必须在承载 BAMPrimaryImport、 BAMStarSchema 和 BAMArchive 数据库的 Microsoft SQL server 上具有管理员权限。 若要设置 SQL Notification Services 数据库，您必须具有管理员权限并且是本地管理员组的成员，以及是任何其他的其他管理组的已配置，如 BTS Admins 组的成员。  
  
 **示例**  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a>迁移 sql 命令  
 **Usage**  
  
 **bm.exe-从： sql2000-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<server\>] [-数据库：\<数据库\>]**  
  
 \- 或 -  
  
 **bm.exe-从： sql2005-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<server\>] [-数据库：\<数据库\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|从： sql2000|指定要将从 Microsoft SQL Server 2000 数据库转换。|  
|到： sql2008|指定要将转换为 Microsoft SQL Server 2008 数据库。|  
|从： sql2005|指定要将从 Microsoft SQL Server 2005 数据库转换。|  
|到： sql2008|指定要将转换为 Microsoft SQL Server 2008 数据库。|  
|NSUser:\<通知服务用户名\>|可选：通知服务用户有权创建数据库用户 ID。|  
|NSUserPassword|可选：指定通知服务用户的密码。|  
|服务器：\<服务器\>|可选：转换后的数据库将驻留的服务器的名称。 服务器必须与承载 Microsoft SQL Server 2008 数据库的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：然后转换后的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 将从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 的 BAM 基础结构迁移到 Microsoft SQL Server 2008。 在升级后将数据库服务器和分析服务器从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 为 Microsoft SQL Server 2008，请使用此命令。  
  
 如果配置 BAM 警报，则需要 NSUser 和 NSUserPassword 参数。 如果 NSUserPassword 未指定命令行上，则 bm.exe 会提示您输入密码。  
  
 若要迁移的 SQL Server Notification Services 数据库，您必须具有管理员权限是本地管理员组的成员，以及是任何其他的其他管理组的已配置，如 BTS 的成员管理员组。  
  
> [!NOTE]
>  如果收到错误消息"错误：无法在计算机上启动服务 NS$ BAMAlerts\<计算机名\>。 该服务未响应及时的方式。 在启动或控制请求"，请尝试手动重新启动该服务。 如果在迁移期间，SQL Server 是极其繁忙，则可能无法重新启动该服务。  
  
> [!NOTE]
>  若要安装 Notification Services 的计算机上运行迁移 sql 命令，你必须属于该计算机上的本地管理员组。  
  
 **示例**  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a>启用 reference 命令  
 **Usage**  
  
 **bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|TargetServer:\<目标服务器\>|为其启用引用的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。|  
|TargetDatabase:\<目标数据库\>|为其启用引用的数据库的名称。|  
|服务器：\<服务器\>|可选：这会启用对目标服务器和数据库的引用的服务器的名称。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：这会启用对目标服务器和数据库的引用的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 启用对另一个分布式 BAM 主导入数据库的引用。 这允许对视图和活动元数据从当前数据库订阅目标 BAM 主导入数据库上。 此位置用于启用分布式活动导航。  
  
 您可以指定目标服务器为 SQL Server，例如，mymachine2\myinstance 的实例。  
  
 **示例**  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a>get-references 命令  
 **Usage**  
  
 **bm.exe get-references [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|服务器：\<服务器\>|可选：若要获取的引用列表的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：要获取的引用列表的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出对其执行该命令在计算机上启用的引用。  
  
 **示例**  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a>disable-reference 命令  
 **Usage**  
  
 **bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|TargetServer:\<目标服务器\>|若要禁用引用的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。|  
|TargetDatabase:\<目标数据库\>|要禁用引用的数据库的名称。|  
|服务器：\<服务器\>|可选：哪些引用到目标服务器和数据库要禁用的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：要禁用的哪些引用到目标服务器上的数据库和数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 禁用对目标服务器上的其他分布式 BAM 主导入数据库的引用。  
  
 您可以指定目标服务器为 SQL Server，例如，mymachine2\myinstance 的实例。  
  
 **示例**  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)