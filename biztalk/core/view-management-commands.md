---
title: 查看管理命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ced7a9ac58fa0375e3eaefa49832e6c23ba1a73
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975171"
---
# <a name="view-management-commands"></a>视图管理命令
您可借助 BAM 管理实用程序的视图管理命令来处理已部署的视图。  
  
-   get 视图： 列出所有已部署的视图。  
  
-   删除视图： 删除已部署的视图。  
  
-   get rtawindow： 对视图中获取的持续时间。  
  
-   集 rtawindow： 在视图上设置的持续时间。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-views-command"></a>get-views 命令  
 **用法**  
  
 **bm.exe get 视图 [-活动：\<活动名称\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|列出其视图的活动的名称。|  
|服务器：\<服务器\>|可选： 用于获取视图的列表的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 若要获取的视图列表的数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出在执行此命令的计算机上部署的视图。  
  
 **示例**  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a>remove-view 命令  
 **用法**  
  
 **bm.exe 删除视图的名称：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<视图名称\>|要删除的视图的名称。|  
|服务器：\<服务器\>|可选： 要从中删除视图服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 要从中删除该视图的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从 BAM 主导入数据库中删除所指定的视图。 如果该视图具有相关警报，则这些警报也将被一同删除。  
  
 **示例**  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a>get-rtawindow 命令  
 **用法**  
  
 **bm.exe get rtawindow 的视图：\<视图名称\>的活动：\<活动名称\>-Rta:\<RTA 名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|视图名称。|  
|活动：\<活动名称\>|活动名称。|  
|Rta:\<RTA 名称\>|实时聚合的名称。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 显示指定实时聚合的持续时间。 该命令返回持续时间的长度和度量单位。  
  
 **示例**  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a>set-rtawindow 命令  
 **用法**  
  
 **bm.exe 集 rtawindow 的视图：\<视图名称\>的活动：\<活动名称\>-名称：\<RTA 名称\>-TimeLength:\<整数\>-TimeUnit:Day &#124;小时 &#124;分钟 [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|视图名称。|  
|活动：\<活动名称\>|活动名称。|  
|名称：\<RTA 名称\>|实时聚合的名称。|  
|TimeLength:\<整数\>|实时聚合的持续时间。|  
|TimeUnit:Month &#124; 天 &#124;小时 &#124;分钟|时段的度量单位。|  
|服务器：\<服务器\>|可选： 活动所在的服务器的名称。 服务器必须与从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上活动所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 设置指定实时聚合的持续时间。  
  
 **示例**  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)