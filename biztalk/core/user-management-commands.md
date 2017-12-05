---
title: "用户管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16527acda7432b2eea35f0c87bb9d89fff632430
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="user-management-commands"></a>用户管理命令
BAM 管理实用程序的警报用户管理命令允许您获取、添加和删除用户。  
  
-   get 帐户： 获取所有用户和组可以访问指定的视图的列表。  
  
-   添加帐户： 授予访问权限指定的用户或组指定的视图。  
  
-   删除帐户： 删除从指定的视图的访问权限的用户或组。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-accounts-command"></a>get-accounts 命令  
 **用法**  
  
 **bm.exe get 帐户的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|列出其帐户的视图的名称。|  
|服务器：\<服务器\>|可选： 用于检索帐户的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 要从中检索帐户数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出可访问指定视图的所有用户和组。  
  
 **示例**  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a>add-account 命令  
 **用法**  
  
 **bm.exe 添加帐户 AccountName:\<帐户名称\>的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|AccountName: < 帐户名称|向其授予权限的帐户的名称。|  
|视图：\<视图名称\>|向其授予权限的视图的名称。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 授予指定的用户或组对指定视图的访问权限。  
  
> [!IMPORTANT]
>  如果你使用的实时聚合 (Rta)，与添加用户**添加帐户**命令都不会自动授予 SQL Server 登录权限。 如果你使用的 Rta，考虑建立包含所有需要查看的 Rta 视图的用户的 Windows 用户组。 授予该组对 BAM 主导入数据库的宿主 SQL Server 的显式登录权限。  
  
 **示例**  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a>remove-account 命令  
 **用法**  
  
 **bm.exe 删除帐户 AccountName:\<帐户名称\>的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|AccountName:\<帐户名称\>|删除其视图权限的帐户的名称。|  
|视图：\<视图名称\>|删除权限的视图的名称。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从指定的视图中删除用户或用户组的访问权限。 从视图中删除帐户将从为指定视图定义的警报中删除该帐户及其所有成员。 如果该帐户是警报的唯一所有者，则当前用户 (admin) 将成为警报的新所有者。  
  
 **示例**  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)