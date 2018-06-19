---
title: BTSTask 命令行参考 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c350695-13e9-441a-9f1e-03cdc3e41328
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2de1e2e616b57d0cc8eda0cb9de9eae5c72d26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231917"
---
# <a name="btstask-command-line-reference"></a>BTSTask 命令行参考
本部分中的主题提供有关包含的 BTSTask 命令行工具参考信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在命令行中使用 BTSTask 可执行许多应用程序部署任务，具体如下：  
  
-   使用 AddApp 命令可向 BizTalk 管理数据库添加 BizTalk 应用程序。  
  
-   使用 AddResource 命令可向应用程序添加项目。  
  
-   使用 ExportApp 命令可将应用程序及其项目导出到 .msi 文件。  
  
-   使用 ExportBindings 命令可将绑定信息导出到 .xml 文件。  
  
-   使用 ImportApp 命令可从 .msi 文件导入应用程序。  
  
-   使用 ImportBindings 命令可从 .xml 文件导入绑定信息。  
  
-   使用 ListApp 命令可列出包含在应用程序中的项目及其本地唯一标识符 (LUID)。  
  
-   使用 ListApps 命令可列出 BizTalk 组在 BizTalk 管理数据库中的所有应用程序。  
  
-   使用 ListPackage 命令可列出 .msi 文件中的资源。  
  
-   列出所有支持的项目类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用默认应用命令。  
  
-   使用 RemoveApp 命令可从 BizTalk 管理数据库和 BizTalk 管理控制台删除应用程序。  
  
-   使用 RemoveResource 命令可从应用程序中删除项目。  
  
-   使用 UninstallApp 命令可从本地计算机中卸载应用程序。  
  
> [!IMPORTANT]
>  在将于应用程序导入期间运行的预处理脚本或后续处理脚本中不能使用 BTSTask 命令。 如果使用该命令，导入可能会失败。 这是因为在导入期间所做的更改对脚本来说是不可见的。  
  
 此外，您可能要掌握如何为 BTSTask 编辑控制台前景色。 如果控制台背景色为白色，则难以查看 BTSTask 控制台的输出，您就需要修改控制台的前景色。  
  
> [!NOTE]
>  脚本完成时，它若返回零 (0) 则表示成功完成，若返回非零数则表示失败。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [AddApp 命令](../core/addapp-command.md)  
  
-   [AddResource 命令](../core/addresource-command.md)  
  
-   [ExportApp 命令](../core/exportapp-command.md)  
  
-   [ExportBindings 命令](../core/exportbindings-command.md)  

- [ExportParties 命令](../core/exportparties-command.md)

- [ExportSettings 命令](../core/exportsettings-command.md)
  
-   [ImportApp 命令](../core/importapp-command.md)  
  
-   [ImportBindings 命令](../core/importbindings-command.md)  

- [ImportParties 命令](../core/importparties-command.md)

- [ImportSettings 命令](../core/importsettings-command.md)
  
-   [ListApp 命令](../core/listapp-command.md)  
  
-   [ListApps 命令](../core/listapps-command.md)  
  
-   [ListPackage 命令](../core/listpackage-command.md)  
  
-   [默认应用命令](../core/listtypes-command.md)  
  
-   [RemoveApp 命令](../core/removeapp-command.md)  
  
-   [RemoveResource 命令](../core/removeresource-command.md)  
  
-   [UninstallApp 命令](../core/uninstallapp-command.md)  
  
-   [如何编辑 BTSTask 的控制台颜色](../core/how-to-edit-the-console-colors-for-btstask.md)