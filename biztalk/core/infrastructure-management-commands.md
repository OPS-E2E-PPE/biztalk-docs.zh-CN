---
title: "基础结构管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae58ea03f394b0fe8b7223bdd810dbc72ccb2472
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="infrastructure-management-commands"></a>基础结构管理命令
通过 BAM 管理 (BM) 实用程序命令，可以获取和更新 BAM 配置。  
  
-   get-config： 获取 BAM 配置文件。  
  
-   更新-config： 更新 BAM 配置。  
  
-   获取变更： 列出对 BAM 基础结构的更改。  
  
-   get defxml： 获取包含 BAM 主导入数据库中的所有项目的文件。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-config-command"></a>get-config 命令  
 **用法**  
  
 **bm.exe get-config FileName:\<输出文件 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|文件名：\<输出文件 >|保存配置的文件的路径和名称。|  
|服务器：\<服务器 >|可选： 从其获取配置服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库 >|可选： 若要获取的配置的数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 检索 BAM 配置 XML，并将其保存到指定的文件中。 **Get-config**命令将不会覆盖现有文件。  
  
 **示例**  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a>update-config 命令  
 **用法**  
  
 **bm.exe 更新-config FileName:\<配置文件 >**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|文件名：\<配置文件 >|更新 BAM 基础结构所用配置文件的路径和名称。|  
  
 更新本地计算机上包含 BAM 配置 XML 文件中的配置。 可以添加当前配置中尚不存在的服务器名和数据库名。 如果已在服务器或数据库中部署了动态基础结构，则更改服务器名或数据库名将失败，并且 bm.exe 会报告错误。  
  
 如果修改了送达的警报的文件存放位置， 则必须重新启动 SQL Notification Services。 如果没有重新启动 NS 服务，则警报将继续传送到原始的文件存放位置。  
  
 修改 BAM 配置文件的以下行，可以更改文件存放位置。  
  
 \<属性名称 ="FileDropUNC">\\\\< 计算机名\>\alerts\</Property >  
  
 适当的步骤来更新的引用，请参阅[备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)。  
  
> [!IMPORTANT]
>  如果执行 update-database 命令时使用不包含警报部分的 BAM 配置文件，但是已经配置了 BAM 警报，则 bm.exe 将覆盖该配置，因而这些警报就不再起作用。  
  
 **示例**  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a>get-changes 命令  
 **用法**  
  
 **bm.exe 获取变更 [-Server:\<服务器 >] [-数据库：\<数据库 >]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|服务器：\<服务器 >|可选： BAM 主导入数据库所在的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库 >|可选： 如果未指定的名称，bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 获取应用于 BAM 主导入数据库的一系列更改。 使用此命令可以审核对 BAM 基础结构所做的更改。 该命令将返回以下信息：  
  
 更改的命令类型以及应用更改所依据的文件。  
  
 谁应用了更改。  
  
 更改了哪些活动。  
  
 更改了哪些视图。  
  
 **示例**  
  
```  
bm.exe get-changes  
```  
  
 命令输出  
  
 \#1： 部署 c:\bam\ordermanagement.xml  
  
 By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).  
  
 活动： OrderMgmt  
  
 视图： SalesManager  
  
## <a name="get-defxml-command"></a>get-defxml 命令  
 **用法**  
  
 **bm.exe get defxml FileName:\<输出文件 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|文件名：\<输出文件 >|保存定义的文件的路径和名称。|  
|服务器：\<服务器 >|可选： 从其获取定义服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库 >|可选： 从其获取定义数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从 BAM 主导入数据库检索所有项目，并将这些项目保存到一个 XML 格式的文件中。 此命令不会覆盖现有文件。  
  
 **示例**  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)