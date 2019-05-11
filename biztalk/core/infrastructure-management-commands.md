---
title: 基础结构管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a75743ae6f6b65bcab0afa42dd5536e8bfbf1c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382195"
---
# <a name="infrastructure-management-commands"></a>基础结构管理命令
BAM 管理 (BM) 实用程序命令，可以获取和更新 BAM 配置。  
  
-   获取配置：获取 BAM 配置文件。  
  
-   更新配置：更新 BAM 配置。  
  
-   get-更改：列出对 BAM 基础结构的更改。  
  
-   get-defxml:获取包含 BAM 主导入数据库中的所有项目的文件。  
  
> [!NOTE]
>  通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="get-config-command"></a>get-config 命令  
 **Usage**  
  
 **bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|文件名：\<输出文件\>|路径和要保存配置文件的名称。|  
|服务器：\<服务器\>|可选：从中获取配置服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：从中获取配置数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 检索 BAM 配置 XML 并将其保存在指定的文件。 **获取配置**命令不会覆盖现有文件。  
  
 **示例**  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a>update-config 命令  
 **Usage**  
  
 **bm.exe 更新-config-FileName:\<配置文件\>**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|文件名：\<配置文件\>|路径和从其更新 BAM 基础结构的配置文件的名称。|  
  
 更新包含 BAM 配置 XML 的文件从本地计算机上的配置。 可以在当前配置中添加服务器和数据库名称尚不存在。 更改服务器或已动态基础结构中部署的数据库名称将会失败，并且 bm.exe 会报告错误。  
  
 如果修改了送达的警报的文件的文件存放位置。 必须重新启动 SQL Notification Services。 如果不重新启动 NS 服务，警报将继续传送到原始文件存放位置。  
  
 通过修改 BAM 配置文件的以下行可以更改文件存放位置。  
  
 \<属性名称 ="FileDropUNC"\>\\\\< 计算机名\>\alerts\</Property\>  
  
 若要更新的引用的适当步骤，请参阅[备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)。  
  
> [!IMPORTANT]
>  如果执行更新数据库命令，使用 BAM 配置文件不包含警报部分，并且已配置了 BAM 警报，bm.exe 将覆盖配置，以便警报将不再起作用。  
  
 **示例**  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a>get-changes 命令  
 **Usage**  
  
 **bm.exe get-changes [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|服务器：\<服务器\>|可选：BAM 主导入数据库所在的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 获取更改应用到 BAM 主导入数据库的列表。 此命令可用于审核对 BAM 基础结构的更改。 该命令返回以下信息：  
  
 更改和从其应用更改的文件的命令类型。  
  
 谁应用了更改。  
  
 更改了哪些活动。  
  
 更改了哪些视图。  
  
 **示例**  
  
```  
bm.exe get-changes  
```  
  
 命令的输出  
  
 \#1:部署 c:\bam\ordermanagement.xml  
  
 通过在 2005 年 12 月 30 日的域 \ 用户 8:17:08 PM (v3.5.1536.0)。  
  
 活动：OrderMgmt  
  
 Views:SalesManager  
  
## <a name="get-defxml-command"></a>get-defxml 命令  
 **Usage**  
  
 **bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|文件名：\<输出文件\>|路径和要将定义保存到文件的名称。|  
|服务器：\<服务器\>|可选：从中获取定义服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：从中获取定义的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 从 BAM 主导入数据库上检索所有项目，并将其保存为 XML 文件中。 该命令不会覆盖现有文件。  
  
 **示例**  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)