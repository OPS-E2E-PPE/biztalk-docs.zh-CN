---
title: 用户管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b79ff5a6bc94faab130de5d7d793612f2130d732
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399962"
---
# <a name="user-management-commands"></a>用户管理命令
BAM 管理实用程序警报用户管理命令可以获取、 添加和删除用户。  
  
-   get-accounts:获取所有用户和组可以访问指定的视图的列表。  
  
-   添加帐户：授予访问权限指定的用户或组对指定视图的权限。  
  
-   删除帐户：删除访问权限的用户或组从指定的视图。  
  
> [!NOTE]
>  通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-accounts-command"></a>get-accounts 命令  
 **Usage**  
  
 **bm.exe 获取帐户的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|列出帐户到为其视图的名称。|  
|服务器：\<服务器\>|可选：要从中检索帐户的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：要从中检索帐户的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出所有用户和组可以访问指定的视图。  
  
 **示例**  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a>添加帐户命令  
 **Usage**  
  
 **bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|AccountName: < 帐户名称|要向其授予权限的帐户的名称。|  
|视图：\<视图名称\>|要向其授予权限的视图的名称。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 授予指定的用户或组对指定视图的访问权限。  
  
> [!IMPORTANT]
>  如果使用的实时聚合 (Rta)，使用添加用户**添加帐户**命令不会自动授予 SQL Server 登录权限。 如果使用 Rta，请考虑建立一个包含的所有用户需要查看的 Rta 视图的 Windows 用户组。 授予该组对 BAM 主导入数据库的宿主 SQL 服务器上的显式 SQL Server 登录权限。  
  
 **示例**  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a>remove-account 命令  
 **Usage**  
  
 **bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|AccountName:\<帐户名称\>|要从其中移除对视图的权限的帐户的名称。|  
|视图：\<视图名称\>|删除权限的视图的名称。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 删除访问权限的用户或组从指定的视图。 从视图中删除帐户从为指定的视图定义的警报中删除该帐户及其所有成员。 如果该帐户是警报的唯一所有者，当前用户 (admin) 将成为新所有者的警报。  
  
 **示例**  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)