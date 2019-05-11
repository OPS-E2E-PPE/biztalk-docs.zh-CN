---
title: 警报订阅管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ffcfea22ac63f3a8f4eb22aaeeae3513705ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359278"
---
# <a name="alert-subscription-management-commands"></a>警报订阅管理命令
BAM 管理实用程序订阅管理命令允许您处理警报订阅。  
  
-   get-subscription:获取警报的订户的列表。  
  
-   添加订阅：向警报添加订户。  
  
-   删除订阅：从警报删除订户。  
  
> [!NOTE]
>  通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-subscription-command"></a>get-subscription 命令  
 **Usage**  
  
 **bm.exe get-subscriptions -View:\<view name\> -Alert:\<alert name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|此警报是指定的视图的名称。|  
|警报：\<警报名称\>|获取订阅的警报的名称。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 列出指定警报的所有订阅服务器。  
  
 **示例**  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a>添加订阅命令  
 **Usage**  
  
 **bm.exe 添加订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>-类型: [文件&#124;电子邮件] [-电子邮件：\<电子邮件地址\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|对其指定警报的视图的名称。|  
|警报：\<警报名称\>|警报的订阅的名称。|  
|AccountName:\<帐户名称\>|域 \ 用户格式，以订阅警报中的帐户。|  
|类型: [文件&#124;电子邮件]|警报的传递类型。 如果指定传递类型为电子邮件，必须包括在命令行上的电子邮件参数。|  
|电子邮件：\<电子邮件地址\>|可选：将向其传递警报通知电子邮件地址。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 将指定的帐户的订阅添加到指定的警报。  
  
 **示例**  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a>remove-subscription 命令  
 **Usage**  
  
 **bm.exe remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|视图：\<视图名称\>|对其指定警报的视图的名称。|  
|警报：\<警报名称\>|警报的名称。|  
|AccountName:\<帐户名称\>|以 domain\user 格式，若要从警报中删除帐户。|  
|服务器：\<服务器\>|可选：该视图所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：视图所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从指定的警报中删除指定的帐户的订阅。 删除指定的帐户的所有订阅。  
  
 **示例**  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)