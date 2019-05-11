---
title: ImportApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8ee5a78-1e8f-4290-b70a-36f2f888a1d6
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fba2557e502420024403b1666946443ec99ca567
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382515"
---
# <a name="importapp-command"></a>ImportApp 命令
导入到 BizTalk 应用程序的.msi 文件中包含的项目。 如果应用程序不存在，则创建它。  
  
 时导入应用程序，您可以使用 /Environment 参数来指定目标部署环境的应用程序，如果绑定文件添加到此应用程序为特定部署环境自定义的。 有关背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。 有关添加绑定文件的说明，请参阅[AddResource 命令：BizTalk 绑定](../core/addresource-command-biztalk-binding.md)。  
  
> [!NOTE]
>  导入操作将超时，如果超过 3600 秒的持续时间。 如果你尝试导入.msi 文件，并在操作超时，应通过重新导出该应用程序，并选择要导出项目的一个子集来划分到多个.msi 文件的应用程序的内容。 有关详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
 如果导入失败，BTSTask 返回显示的错误数。 在操作期间所执行的操作的大多数都将回滚，除以下：  
  
- 自定义脚本执行的操作不回滚。 您可以编写脚本，以便它们回滚使用 Delete 环境变量。  
  
- 如果程序集安装在全局程序集缓存 (GAC) 中，它们不会删除。  
  
- 在 Windows 不会删除注册表中进行的条目。  
  
  如果导入成功，BTSTask 返回"0"。  
  
## <a name="usage"></a>用法  
 **BTSTask 的 ImportApp /Package:** *值*[**/Environment:**<em>值</em>] [**/ApplicationName:** <em>值</em>] [**/overwrite**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ 打包**(或 **/P**，请参阅备注)|是|将.msi 文件的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。 例如："C:\My MSI Files\MyApplication.msi"|  
|**/ 环境**(或 **/E**，请参阅备注)|否|要将应用，例如测试的绑定文件的目标部署环境。 这是绑定文件添加到应用程序时为目标部署环境指定的值。 未指定时，应用不具有指定的环境的所有绑定。|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|.Msi 文件中的项目导入到 BizTalk 应用程序的名称。 如果名称包含空格，必须将其用双引号 （"）。 如果未指定，则使用默认应用程序。 如果指定的应用程序不存在，创建应用程序。|  
|**/ 覆盖**(或 **/O**，请参阅备注)|否|若要使用具有相同的本地唯一标识符 (LUID) 与.msi 文件中的项目覆盖应用程序中的项目的选项。 可以通过使用应用程序中查看的项目的 Luid [ListApp 命令](../core/listapp-command.md)。 如果未指定此选项，并且有一个或多个项目中具有相同 LUID 的应用程序.msi 文件，导入中的项目将失败。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask ImportApp /Package:C:\MSI\MyApplication.msi /Environment:Test /ApplicationName:MyApplication /Overwrite**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)