---
title: AddResource 命令： 预处理脚本 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b4f66e5-1f40-4bc3-82a8-c27a0e435797
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5255bfa0bfe73941b69d8e6b95f2230a9dfbd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230869"
---
# <a name="addresource-command-preprocessing-script"></a>AddResource 命令：预处理脚本
若要将预处理脚本添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:PreProcessingScript**为类型参数。 运行此命令可将脚本文件添加到 BizTalk 管理数据库中。 该脚本文件还会显示在 BizTalk 管理控制台中，即它所添加到的应用程序的“资源”文件夹下。 此外，将列出该文件，当你使用[ListApp 命令](../core/listapp-command.md)。  
  
 在导入或安装应用程序之前，或卸载应用程序之后，预处理脚本从 .msi 文件运行。 你还可以使用 BTSTask 添加后处理的脚本，从而中所述运行应用程序导入或之后安装，或者，在卸载之前[AddResource 命令： 后处理脚本](../core/addresource-command-postprocessing-script.md)。 有关预处理和后处理脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:PreProcessingScript**[**/Overwrite**]**/Source:***值*[**/Destination:***值*] [**/Server:** *值*] [**/数据库：***值*] [**/Property:Args ="***自变量列表***"**]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|脚本要添加到的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.BizTalk:PreProcessingScript** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|是|更新现有脚本的选项。 如果未指定，和中的应用程序作为被添加，则添加操作将失败的脚本文件具有相同的名称已存在脚本文件。|  
|**/ 源**(或 **/So**，请参阅备注)|是|脚本文件的完整路径，包含文件名。 如果路径中有空格，必须将它括在双引号 （"）。|  
|**/ 目标**(或 **/De**，请参阅备注)|是|从 .msi 文件安装应用程序时，脚本文件要复制到的位置的完整路径。 如果未提供，不复制文件到本地文件系统在安装过程。 如果在卸载应用程序期间运行此脚本，则应指定 Destination，否则，此脚本将不会驻留在本地文件系统中，并且在卸载期间也无法运行。 如果路径中有空格，必须将它括在双引号 （"）。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
|**/ 属性**(或 **/P**，请参阅备注)|是|调用脚本时将作为参数传递给脚本的零个或多个资源属性。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:PreProcessingScript / 覆盖 /Source:"C:\Source Scripts\MyScript.vbs"/Destination:"C:\New Scripts\MyScript.vbs"/Server:MyDatabaseServer /Database:BizTalkMgmtDb/Property:Args ="argument1 argument2"**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
 支持脚本文件使用下列扩展名：.com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf、.wsh。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将一个预或后续处理脚本添加到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)