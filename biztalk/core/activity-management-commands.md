---
title: 活动管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dc32b005d0a6492fbdce87a1149c23c5a13442e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361677"
---
# <a name="activity-management-commands"></a>活动管理命令
BAM 管理实用程序活动管理命令允许您可以使用已部署的活动。  
  
-   获取活动：获取已部署的活动的列表。  
  
-   删除活动：删除活动。  
  
-   get-activitywindow:获取活动的持续时间。  
  
-   set-activitywindow:设置活动的活动的持续时间。  
  
-   获取索引：获取索引的列表。  
  
-   创建索引：创建新的索引。  
  
-   删除索引：删除索引。  
  
-   get-存档：获取已存档活动的行为。  
  
-   设置存档：设置已存档活动的行为。  
  
> [!NOTE]
>  通过将可以启用任何 BAM 实用程序命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BAM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-activities-command"></a>get-activities 命令  
 **Usage**  
  
 **bm.exe get-activities [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<活动名称\>|要删除的活动的名称。|  
|服务器：\<服务器\>|可选：从中获取活动的列表服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：从中获取活动的列表的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出了在其执行此命令的计算机上部署的活动。  
  
 **示例**  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a>remove-activity 命令  
 **Usage**  
  
 **bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<活动名称\>|要删除的活动的名称。|  
|服务器：\<服务器\>|可选：要从中移除活动的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：要从中移除活动的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从 BAM 主导入数据库中删除指定的活动。 如果该活动具有相关的视图，该命令将失败并报告错误。 使用 remove-view 命令删除所有相关的视图，然后再次执行 remove-activity 命令。  
  
 **示例**  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a>get-activitywindow 命令  
 **Usage**  
  
 **bm.exe get-activitywindow -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|.Activity 的名称。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 显示指定活动的持续时间。 该命令返回持续时间和持续时间单位所依据的单位的长度。  
  
 **示例**  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a>set-activitywindow 命令  
 **Usage**  
  
 **bm.exe set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|活动的名称。|  
|TimeLength:\<整数\>|活动的持续时间。|  
|TimeUnit:Month&#124;Day&#124;Hour&#124;Minute|持续时间度量单位。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 设置指定活动的持续时间。  
  
 **示例**  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a>get-index 命令  
 **Usage**  
  
 **bm.exe get-index -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|活动的名称。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出已为指定的活动创建的所有索引。  
  
 **示例**  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a>create index 命令  
 **Usage**  
  
 **bm.exe create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...][ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|IndexName:\<索引名称\>|新的索引的名称。|  
|活动：\<活动名称\>|为其创建索引的活动的名称。|  
|Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...]|以逗号分隔的索引检查点的列表。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 创建使用指定的检查点的指定活动的索引。  
  
 **示例**  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a>delete-index 命令  
 **Usage**  
  
 **bm.exe delete-index -IndexName:\<index name\> -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|IndexName:\<索引名称\>|要删除的索引的名称。|  
|活动：\<活动名称\>|会删除该索引的活动的名称。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从指定的活动中删除具有给定名称的指定的索引。  
  
 **示例**  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a>set-archive 命令  
 **Usage**  
  
 **bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|为其行为是要显示的活动的名称。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 获取指定活动的存档程序包行为，是否存档程序包是存档还是清除活动数据。  
  
 **示例**  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a>set-archive 命令  
 **Usage**  
  
 **bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|为其行为是要显示的活动的名称。|  
|ShouldArchive:True|如果设置为 True，则将活动移至存档数据库。 如果设置为 False，该活动将清除。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 设置指定，以便活动数据移至存档数据库的活动的存档程序包行为。 默认情况下部署的新活动设置此行为。  
  
 **示例**  
  
 若要清除 BAM 活动数据，执行以下操作：  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 将 BAM 活动数据移至 BAMArchive 数据库，执行以下操作：  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)