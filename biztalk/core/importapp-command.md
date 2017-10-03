---
title: "ImportApp 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8ee5a78-1e8f-4290-b70a-36f2f888a1d6
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4200b5559ddfc12597c95d0e924a0159665f5f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importapp-command"></a>ImportApp 命令
用于将 .msi 文件中包含的项目导入到 BizTalk 应用程序中。 如果尚不存在相应的应用程序，系统将创建它。  
  
 当导入应用程序时，如果已将为特定部署环境自定义的绑定文件添加到应用程序中，则可以使用 /Environment 参数来指定该应用程序的目标部署环境。 有关背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。 有关添加绑定文件的说明，请参阅[AddResource 命令： BizTalk 绑定](../core/addresource-command-biztalk-binding.md)。  
  
> [!NOTE]
>  如果导入操作的持续时间超过 3600 秒，则该操作超时。 如果在尝试导入 .msi 文件时操作超时，则应通过重新导出该应用程序，并选择要导出的部分项目，将该应用程序的内容分成多个 .msi 文件。 有关详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
 如果导入失败，BTSTask 返回显示错误数。 在此操作期间执行的大多数操作都将被回滚，但以下操作除外：  
  
-   不回滚自定义脚本执行的操作。 您可以编写脚本，使用 Delete 环境变量回滚自定义脚本。  
  
-   如果程序集安装在全局程序集缓存 (GAC) 中，则导入失败后不删除这些程序集。  
  
-   不删除 Windows 注册表中生成的项。  
  
 如果导入成功，BTSTask 将返回“0”。  
  
## <a name="usage"></a>用法  
 **BTSTask ImportApp /Package:** *值*[**/Environment:***值*] [**/ApplicationName:** *值*] [**/覆盖**] [**/Server:***值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ 包**(或**/P**，请参阅备注)|是|.msi 文件的完整路径。 如果路径包含空格，必须将它括在双引号 （"）。 示例："C:\My MSI Files\MyApplication.msi"|  
|**/ 环境**(或**/E**，请参阅备注)|是|绑定文件适用的目标部署环境，如 Test。 此值是将绑定文件添加到应用程序时，指定的目标部署环境的值。 如果未指定此值，则应用所有未指定环境的绑定。|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|.msi 文件中的项目将导入到的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将它用双引号 （"）。 如果未指定，则使用默认应用程序。 如果指定的应用程序不存在，则系统将创建该应用程序。|  
|**/ 覆盖**(或**/O**，请参阅备注)|是|该选项的功能是，如果应用程序中的项目的本地唯一标识符 (LUID) 与 .msi 文件中的项目的本地唯一标识符 (LUID) 相同，则使用后者覆盖前者。 可以通过使用应用程序中查看的项目的 Luid [ListApp 命令](../core/listapp-command.md)。 如果未指定此选项，并且应用程序中存在一个或多个项目与 .msi 文件中的项目具有相同的 LUID，则导入失败。|  
|**/ 服务器**(或**/S**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或**/D**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask ImportApp /Package:C:\MSI\MyApplication.msi /Environment:Test /ApplicationName:MyApplication / 覆盖**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)