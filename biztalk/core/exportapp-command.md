---
title: "ExportApp 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6217d0f1-cf39-4520-87c8-8d25b21865af
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966e53a7c74ce687724a77ea57888a4c61bb2773
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exportapp-command"></a>ExportApp 命令
用于将 BizTalk 应用程序导出到 .msi 文件。 如果已存在具有相同文件名和路径的 .msi 文件，则覆盖该现有 .msi 文件。  
  
 可以使用 ResourceSpec 参数，将应用程序中的项目有选择地导出到 .msi 文件。 指定要导出通过编辑 XML 文件的项目运行时创建**ListApp**命令与资源规格参数中所述[ListApp 命令](../core/listapp-command.md)。 您然后使用此 XML 文件的位置作为资源规格的值时运行**ExportApp**命令。 执行此操作时，只有指定的 XML 文件中所列的项目才导出到 .msi 文件。  
  
> [!NOTE]
>  为安全起见，在导出应用程序的过程中，密码从应用程序绑定中删除。 但这些密码并未从已添加到应用程序的绑定文件中删除。 从 .msi 文件安装应用程序后，您必须重新配置密码，以便应用程序可以正常运行。  
>   
>  此外，私钥也被从证书文件中删除。  
  
## <a name="usage"></a>用法  
 **BTSTask ExportApp** [**/ApplicationName:***值*] **/包：***值*[**/资源规格：***值*] [**/GlobalParties**] [**/Server:***值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|要导出的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将它用双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 包**(或**/P**，请参阅备注)|是|.msi 文件的完整路径。 如果该路径包含空格，则必须将其括在引号 (") 中。 示例：Package:"C:\My MSI Files\My.msi"|  
|**/ 资源规格**(或**/R**，请参阅备注)|是|资源规范文件的完整路径。 如果该路径包含空格，则必须将其括在引号 (") 中。 示例：ResourceSpec:"C:\My Files\MyResourceSpec.xml"|  
|**/ GlobalParties** (或**/G**，请参阅备注)|是|如果已指定，组的全局参与方信息将导出到 .msi 文件中。|  
|**/ 服务器**(或**/S**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或**/D**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **ExportApp /ApplicationName:MyApplication /Package:C:\MSI\MyApplication.msi**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)