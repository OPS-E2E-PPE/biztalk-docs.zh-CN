---
title: "警报订阅管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02234637e38bb59e71c0f435ee24feef39e09e91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="alert-subscription-management-commands"></a>警报订阅管理命令
BAM 管理实用程序订阅管理命令可用于处理警报订阅。  
  
-   获取订阅： 获取对警报的订阅服务器的列表。  
  
-   添加订阅： 将订阅服务器添加到警报。  
  
-   删除订阅： 订阅服务器，则删除警报。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-subscription-command"></a>get-subscription 命令  
 **用法**  
  
 **bm.exe 获取订阅的视图：\<视图名称\>-警报：\<警报名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|要对其指定警报的视图的名称。|  
|警报：\<警报名称\>|从中获取订阅的警报的名称。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出指定警报的所有订户。  
  
 **示例**  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a>add-subscription 命令  
 **用法**  
  
 **bm.exe 添加订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>-类型: [文件 &#124;电子邮件] [-电子邮件：\<电子邮件地址\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|对其指定警报的视图的名称。|  
|警报：\<警报名称\>|订阅的警报的名称。|  
|AccountName:\<帐户名称\>|订阅警报的帐户（格式为“域\用户”）。|  
|类型: [文件 &#124;电子邮件]|警报的传递类型。 如果指定传递类型为电子邮件，则必须在命令行中包含电子邮件参数。|  
|电子邮件：\<电子邮件地址\>|可选： 将向其传递警报通知电子邮件地址。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 为指定帐户向指定警报添加订阅。  
  
 **示例**  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a>remove-subscription 命令  
 **用法**  
  
 **bm.exe 删除订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|对其指定警报的视图的名称。|  
|警报：\<警报名称\>|警报的名称。|  
|AccountName:\<帐户名称\>|从警报中删除的帐户（格式为“域\用户”）。|  
|服务器：\<服务器\>|可选： 视图所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上视图所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从指定警报中删除指定帐户的订阅。 指定帐户的所有订阅都将被删除。  
  
 **示例**  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)