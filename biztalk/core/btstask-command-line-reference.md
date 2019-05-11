---
title: BTSTask 命令行参考 |Microsoft Docs
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
ms.openlocfilehash: a3df365e96c42865189a8e70aa5d1994a4b08a9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357795"
---
# <a name="btstask-command-line-reference"></a>BTSTask 命令行参考
在本部分中的主题提供附带的 BTSTask 命令行工具的参考信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 可以使用 BTSTask，如下所示从命令行执行许多应用程序部署任务：  
  
- 使用 AddApp 命令添加到 BizTalk 管理数据库的 BizTalk 应用程序。  
  
- 使用 AddResource 命令添加到应用程序的项目。  
  
- 使用 ExportApp 命令，应用程序和及其项目导出到某一.msi 文件。  
  
- 使用 ExportBindings 命令可将绑定信息导出到.xml 文件中。  
  
- 使用 ImportApp 命令导入的.msi 文件从应用程序。  
  
- 从.xml 文件使用 ImportBindings 命令导入绑定信息。  
  
- 列出了通过使用 ListApp 命令及其本地唯一标识符 (Luid) 以及应用程序中包含的项目。  
  
- 使用 ListApps 命令列出于 BizTalk 组的 BizTalk 管理数据库中的所有应用程序。  
  
- 通过使用 ListPackage 命令可列出.msi 文件中的资源。  
  
- 列出所有支持的项目类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 ListTypes 命令。  
  
- 使用 RemoveApp 命令可从 BizTalk 管理数据库和 BizTalk 管理控制台中删除应用程序。  
  
- 使用 RemoveResource 命令从应用程序中删除项目。  
  
- 使用 UninstallApp 命令从本地计算机中卸载应用程序。  
  
> [!IMPORTANT]
>  不能在将应用程序导入过程中运行的预处理或后处理脚本中使用 BTSTask 命令。 如果这样做，导入可能会失败。 这是因为导入过程中所做的更改看不到脚本。  
  
 此外，您可以了解如何为 BTSTask 编辑控制台前景色。 如果控制台背景色为白色，您将难以查看 BTSTask 控制台的输出，并将需要修改控制台前景色。  
  
> [!NOTE]
>  完成脚本后，它返回零 (0) 以指示成功完成后或一个非零数字来指示失败。  
  
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
  
-   [ListTypes 命令](../core/listtypes-command.md)  
  
-   [RemoveApp 命令](../core/removeapp-command.md)  
  
-   [RemoveResource 命令](../core/removeresource-command.md)  
  
-   [UninstallApp 命令](../core/uninstallapp-command.md)  
  
-   [如何为 BTSTask 编辑控制台颜色](../core/how-to-edit-the-console-colors-for-btstask.md)