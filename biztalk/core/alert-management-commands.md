---
title: 警报管理命令 |Microsoft 文档
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
ms.openlocfilehash: f419e7a0019287383080c319961b8a3831d27bb4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967683"
---
# <a name="alert-management-commands"></a>警报管理命令
您可借助 BAM 管理实用程序的警报管理命令来处理已部署的警报。  
  
-   get 警报： 获取已部署的警报的列表。  
  
-   删除警报： 删除警报。  
  
-   启用警报： 启用对视图的警报。  
  
-   禁用警报： 禁用对视图的警报。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-alerts-command"></a>get-alerts 命令  
 **用法**  
  
 **bm.exe get 警报 [的视图：\<视图名称\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|从中获取警报列表的视图的名称。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出在执行此命令的计算机上定义的警报。  
  
 **示例**  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a>remove-alerts 命令  
 **用法**  
  
 **bm.exe 删除警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|从中删除警报的视图的名称。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 删除指定视图中的所有警报。  
  
 **示例**  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a>enable-alerts 命令  
 **用法**  
  
 **bm.exe 启用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|启用警报的视图的名称。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 对指定视图启用警报。  
  
 **示例**  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a>disable-alerts 命令  
 **用法**  
  
 **bm.exe 禁用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|禁用警报的视图的名称。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 对指定视图禁用警报。  
  
 **示例**  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)