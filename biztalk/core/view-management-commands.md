---
title: 查看管理命令 |Microsoft Docs
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
ms.openlocfilehash: fbd91cf632b655fe3c2cb535f2ee4db3c889688d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243247"
---
# <a name="view-management-commands"></a>视图管理命令
BAM 管理实用程序视图管理命令允许您可以使用已部署的视图。  
  
-   获取视图：列出所有已部署的视图。  
  
-   删除视图：删除已部署的视图。  
  
-   get-rtawindow:获取视图的持续时间。  
  
-   集 rtawindow:在视图上设置的持续时间。  
  
> [!NOTE]
>  通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-views-command"></a>get-views Command  
 **Usage**  
  
 **bm.exe get-views [ -Activity:\<activity name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|活动：\<活动名称\>|若要列出其视图的活动的名称。|  
|服务器：\<服务器\>|可选：从中获取视图的列表的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：从中获取视图的列表的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出对其执行该命令的计算机上部署的视图。  
  
 **示例**  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a>remove-view 命令  
 **Usage**  
  
 **bm.exe remove-view -Name:\<view name\> [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<视图名称\>|要删除的视图的名称。|  
|服务器：\<服务器\>|可选：要从其中移除该视图的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：要从其中移除该视图的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从 BAM 主导入数据库中删除指定的视图。 如果此视图具有相关警报，则会删除在同一时间。  
  
 **示例**  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a>get-rtawindow 命令  
 **Usage**  
  
 **bm.exe get-rtawindow -View:\<view name\> -Activity:\<activity name\> -Rta:\<RTA name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|视图名称。|  
|活动：\<活动名称\>|活动名称。|  
|Rta:\<RTA 名称\>|实时聚合的名称。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 显示指定实时聚合的持续时间。 该命令返回持续时间和持续时间单位所依据的单位的长度。  
  
 **示例**  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a>set-rtawindow 命令  
 **Usage**  
  
 **bm.exe 集 rtawindow 的视图：\<视图名称\>-活动：\<活动名称\>-名称：\<RTA 名称\>-TimeLength:\<整数\>-时间单位： Day&#124;小时&#124;分钟 [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|视图名称。|  
|活动：\<活动名称\>|活动名称。|  
|名称：\<RTA 名称\>|实时聚合的名称。|  
|TimeLength:\<整数\>|实时聚合的持续时间。|  
|TimeUnit:Month&#124;Day&#124;Hour&#124;Minute|窗口持续时间度量单位。|  
|服务器：\<服务器\>|可选：该活动所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：活动所处的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 设置指定实时聚合的持续时间。  
  
 **示例**  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)