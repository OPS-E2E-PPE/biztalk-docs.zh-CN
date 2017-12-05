---
title: "活动管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18caccaf5207b5a63d0272c5d9e0277270c3e04c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="activity-management-commands"></a>活动管理命令
你可借助 BAM 管理实用程序的活动管理命令来处理已部署的活动。  
  
-   获取活动： 获取已部署的活动的列表。  
  
-   删除活动： 中移除该活动。  
  
-   get activitywindow： 获取活动的持续时间。  
  
-   集 activitywindow： 设置为活动的活动持续时间。  
  
-   获取索引： 获取索引的列表。  
  
-   创建索引： 创建新的索引。  
  
-   删除索引： 删除索引。  
  
-   get 存档： 获取已存档的活动的行为。  
  
-   集存档： 设置已存档的活动的行为。  
  
> [!NOTE]
>  您可以通过包括启用 BAM 实用程序的任何命令上跟踪**-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BAM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-activities-command"></a>get-activities 命令  
 **用法**  
  
 **bm.exe get 活动 [的视图：\<视图名称\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<活动名称\>|要删除的活动的名称。|  
|服务器：\<服务器\>|可选： 从其获取活动列表的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 若要获取的活动列表的数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出在执行此命令的计算机上部署的活动。  
  
 **示例**  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a>remove-activity 命令  
 **用法**  
  
 **bm.exe 删除活动的名称：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<活动名称\>|要删除的活动的名称。|  
|服务器：\<服务器\>|可选： 要从中移除活动服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 要从中移除活动数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从 BAM 主导入数据库中删除指定的活动。 如果该活动具有相关视图，则此命令将失败并报告错误。 使用 remove-view 命令删除所有相关视图后，即可再次执行 remove-activity 命令。  
  
 **示例**  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a>get-activitywindow 命令  
 **用法**  
  
 **bm.exe get activitywindow 的活动：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|.Activity 的名称。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 显示指定活动的持续时间。 该命令返回持续时间的长度和度量单位。  
  
 **示例**  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a>set-activitywindow 命令  
 **用法**  
  
 **bm.exe 集 activitywindow 的活动：\<活动名称\>-TimeLength:\<整数\>-时间单位： 月 &#124; 天 &#124;小时 &#124;分钟 [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|活动的名称。|  
|TimeLength:\<整数\>|活动的持续时间。|  
|TimeUnit:Month &#124; 天 &#124;小时 &#124;分钟|持续时间的度量单位。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 设置指定活动的持续时间。  
  
 **示例**  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a>get-index 命令  
 **用法**  
  
 **bm.exe get 索引的活动：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|活动的名称。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出已为指定活动创建的所有索引。  
  
 **示例**  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a>create-index 命令  
 **用法**  
  
 **bm.exe 创建索引 IndexName:\<索引名称\>的活动：\<活动名称\>的检查点：\<checkpoint1\>[，\<checkpoint2\>...][-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|IndexName:\<索引名称\>|新索引的名称。|  
|活动：\<活动名称\>|创建索引的活动的名称。|  
|检查点：\<checkpoint1\>[，\<checkpoint2\>...]|以逗号分隔的索引检查点列表。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 使用指定检查点为指定的活动创建索引。  
  
 **示例**  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a>delete-index 命令  
 **用法**  
  
 **bm.exe 删除索引 IndexName:\<索引名称\>的活动：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|IndexName:\<索引名称\>|要删除的索引的名称。|  
|活动：\<活动名称\>|删除索引的活动的名称。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从指定活动中删除具有给定名称的指定索引。  
  
 **示例**  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a>set-archive 命令  
 **用法**  
  
 **bm.exe get 存档的活动：\<活动\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|要显示其行为的活动的名称。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 获取指定活动的存档程序包的行为，无论存档程序包是存档还是清除活动数据。  
  
 **示例**  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a>set-archive 命令  
 **用法**  
  
 **bm.exe 集的存档的活动：\<活动\>-ShouldArchive: True [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|要显示其行为的活动的名称。|  
|ShouldArchive: True|如果设置为 True，则将活动移至存档数据库。 如果设置为 False，则清除活动。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 设置指定活动的存档程序包的行为，以便将活动数据移至存档数据库。 默认情况下，会为部署的新活动设置此行为。  
  
 **示例**  
  
 若要清除 BAM 活动数据，请执行以下操作：  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 若要将 BAM 活动数据移至 BAMArchive 数据库，请执行以下操作：  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)