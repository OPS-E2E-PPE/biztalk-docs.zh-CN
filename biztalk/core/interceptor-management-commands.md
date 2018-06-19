---
title: 拦截器管理命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2be6460-1f81-4bc3-a831-34ff24d65d34
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32392c05f47c00a6c62372acbf8d1ba0bed0da6c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974387"
---
# <a name="interceptor-management-commands"></a>侦听器管理命令
为了支持新的 BAM 侦听器功能，在 BAM 管理实用程序中添加了四个新命令。  
  
 这些命令支持侦听器的部署、检索和删除。 还提供了一个命令用于列出已配置的侦听器。  
  
-   部署侦听器： 部署的侦听器配置。  
  
-   get interceptorlist： 获取在其部署截获的活动的列表。  
  
-   get 侦听器： 获取侦听器配置。  
  
-   删除侦听器： 删除的侦听器配置。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="deploy-interceptor-command"></a>deploy-interceptor 命令  
 **用法**  
  
 **bm.exe 部署侦听器 FileName:\<配置 XML 文件名\>[-Force: True] [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|文件名：\<配置 XML 文件名\>|包含侦听器配置的 XML 文件的名称。|  
|Force:True|可选： 在检测到事件源名称冲突时强制的侦听器配置的部署。|  
|服务器：\<服务器\>|可选： 部署侦听器服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。|  
|数据库：\<数据库\>|可选： 用于配置侦听器 BAM 主导入数据库的名称。|  
  
 此命令将侦听器配置部署到指定的服务器和数据库。 在部署期间，BAM 管理实用程序执行以下验证：  
  
-   XSD 验证： 针对常见的侦听器配置架构验证的侦听器配置。  
  
-   验证活动存在（部署在主导入数据库中）且检查点有效（存在并具有匹配的数据类型）。  
  
 如果在事件源名称中检测到冲突，则发出描述冲突的警告。 对于冲突，部署将失败，除非 **– Force: True**参数标记用于。  
  
> [!NOTE]
>  **– Force: True**参数可能会删除引用具有相同名称的事件源的侦听器配置。 应使用**get 侦听器**命令以在使用之前创建的现有侦听器配置备份 **– Force: True**参数。  
  
 **示例**  
  
```  
bm.exe deploy-interceptor  -FileName:myInceptor.xml  
bm.exe deploy-interceptor  -FileName:myInceptor.xml -Force:True  
```  
  
## <a name="get-interceptorlist-command"></a>get-interceptorlist 命令  
 **用法**  
  
 **bm.exe get interceptorlist [-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|服务器：\<服务器\>|可选： 从中返回的已部署的拦截器列表服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。|  
|数据库：\<数据库\>|可选： 要从中检索已部署的拦截器 BAM 主导入数据库的名称。|  
  
 此命令返回活动的列表及为之启用侦听的关联事件源。  
  
 **示例**  
  
```  
bm.exe get-interceptorlist   
```  
  
## <a name="get-interceptor-command"></a>get-interceptor 命令  
 **用法**  
  
 **bm.exe get 拦截器 [-Server:\<服务器\>] [-数据库：\<数据库\>]-FileName:\<配置 XML 文件名\>[-活动：\<活动名称\>] [-EventSource:\<事件源名称\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|服务器：\<服务器\>|可选： 要从中检索已部署的拦截器服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。|  
|数据库：\<数据库\>|可选： 要从中检索部署的侦听器 BAM 主导入数据库的名称。|  
|文件名：\<配置 XML 文件名\>|向其写入侦听器配置的 XML 文件的名称。|  
|活动：\<活动名称\>|可选： 指定为其返回配置的侦听器的活动。 可以结合使用**EventSource**参数以进一步指定要返回的配置。|  
|EventSource:\<事件源名称\>|可选： 指定事件源为其返回配置的侦听器。 可以结合使用**活动**参数以进一步指定要返回的配置。|  
  
 如果没有提供活动名称或事件源名称，该命令将为所有事件源和活动返回包含侦听器配置的有效配置文件。  
  
 如果只提供活动名称，该命令将为该活动的所有事件源返回有效的侦听器配置文件。  
  
 如果只提供事件源名称，该命令将为所有活动中的该事件源返回有效的侦听器配置文件。  
  
 如果同时提供了活动名称和事件源名称，则该命令将为该活动的该事件源返回有效的侦听器配置文件。  
  
 **示例**  
  
```  
bm.exe get-interceptor   
bm.exe get-interceptor  -Activity:ShippingPO  
```  
  
## <a name="remove-interceptor-command"></a>remove-interceptor 命令  
 **用法**  
  
 **bm.exe 删除侦听器 [-Server:\<服务器\>] [-数据库：\<数据库\>] [-活动：\<活动名称\>] [-EventSource:\<事件源名称\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|服务器：\<服务器\>|可选： 在其上配置侦听器的服务器名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。|  
|数据库：\<数据库\>|可选： 在其上配置侦听器的数据库名称。|  
|活动：\<活动名称\>|可选： 指定要删除指定的侦听器其活动。 可以结合使用**EventSource**参数以进一步指定要返回的配置。|  
|EventSource:\<事件源名称\>|可选： 指定要删除指定的侦听器其事件源。 可以结合使用**活动**参数以进一步指定要返回的配置。|  
  
 如果只提供活动名称，该命令将为该活动的所有事件源删除侦听器。  
  
 如果只提供事件源名称，该命令只删除所有活动的该事件源部分。  
  
 **示例**  
  
```  
bm.exe remove-interceptor   
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)