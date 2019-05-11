---
title: 警报管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 651bc1d0df943df022cf597bb7292cb3143ad327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359295"
---
# <a name="alert-management-commands"></a>警报管理命令
BAM 管理实用程序警报管理命令允许您可以使用已部署的警报。  
  
-   get-alerts:获取已部署的警报的列表。  
  
-   删除警报：删除警报。  
  
-   启用警报：对视图启用警报。  
  
-   禁用的警报：对视图禁用警报。  
  
> [!NOTE]
>  通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-alerts-command"></a>get-alerts Command  
 **Usage**  
  
 **bm.exe get-alerts [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|要从其中获取警报的列表视图的名称。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出对其执行该命令的计算机上定义的警报。  
  
 **示例**  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a>remove-alerts 命令  
 **Usage**  
  
 **bm.exe 删除警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|要从其中移除警报视图的名称。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 删除指定的视图上的所有警报。  
  
 **示例**  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a>enable-alerts 命令  
 **Usage**  
  
 **bm.exe 启用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|要启用的警报视图的名称。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 对指定视图启用警报。  
  
 **示例**  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a>disable-alerts 命令  
 **Usage**  
  
 **bm.exe 禁用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|要禁用警报的视图的名称。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 对指定视图禁用警报。  
  
 **示例**  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)