---
title: ExportApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6217d0f1-cf39-4520-87c8-8d25b21865af
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93d613f3e32c3dd592fc84bb05121f7256e6faa5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388299"
---
# <a name="exportapp-command"></a>ExportApp 命令
将导出到.msi 文件的 BizTalk 应用程序。 如果已具有相同的文件名和路径的.msi 文件存在，将覆盖该现有.msi 文件。  
  
 可以使用 ResourceSpec 参数有选择地导出到.msi 文件的应用程序中的项目。 指定要导出的 XML 文件的项目创建在运行时**ListApp**命令具有 ResourceSpec 参数，如中所述[ListApp 命令](../core/listapp-command.md)。 您然后使用此 XML 文件的位置用作 ResourceSpec 的值在运行时**ExportApp**命令。 在执行此操作时，仅在指定的 XML 文件中所列的项目将导出到.msi 文件。  
  
> [!NOTE]
>  出于安全原因，在应用程序导出过程中不会保留密码从应用程序绑定。 它们不会删除任何已添加到应用程序的绑定文件中。 从.msi 文件安装应用程序之后, 必须重新配置密码，以便对函数应用程序。  
>   
>  此外，从证书文件删除私有密钥。  
  
## <a name="usage"></a>用法  
 **BTSTask ExportApp** [**/ApplicationName:**<em>值</em>] **/包：**<em>值</em>[**/ResourceSpec:**<em>值</em>] [**/GlobalParties**] [**/Server:**<em>值</em>] [**/database:** <em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|若要导出的 BizTalk 应用程序的名称。 如果名称包含空格，必须将其用双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。|  
|**/ 打包**(或 **/P**，请参阅备注)|是|将.msi 文件的完整路径。 如果路径包含空格，则必须将其括在引号 （"）。 例如：Package:"C:\My MSI Files\My.msi"|  
|**/ ResourceSpec** (或 **/R**，请参阅备注)|否|资源规范文件的完整路径。 如果路径包含空格，则必须将其括在引号 （"）。 例如：ResourceSpec:"C:\My Files\MyResourceSpec.xml"|  
|**/ GlobalParties** (或 **/G**，请参阅备注)|否|如果指定，组的全局参与方信息将导出的.msi 文件中。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **ExportApp /ApplicationName:MyApplication /Package:C:\MSI\MyApplication.msi**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)