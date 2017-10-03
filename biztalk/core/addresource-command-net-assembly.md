---
title: "AddResource 命令：.NET 程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef6ec298-35fe-4845-9549-685993d2c659
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f20e259611d312429c3bd909a85a3162f1dd64
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-net-assembly"></a>AddResource 命令：.NET 程序集
若要将.NET 程序集 （其中包括托管的 COM 或 COM + 组件） 添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:Assembly**为类型参数。 运行此命令可将程序集添加到 BizTalk 管理数据库中。 程序集还会显示在 BizTalk 管理控制台中，即它所添加到的应用程序的“资源”文件夹中。 此外，当使用时，该程序集列出[ListApp 命令](../core/listapp-command.md)。  
  
 如果要添加的程序集的全名与应用程序中已经存在的程序集的全名相同，可以指定 Overwrite 参数。 全名包括名称、公钥标记、区域性和版本。 在这种情况下，现有程序集将被覆盖。 有关依赖关系的详细信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Assembly**[**/覆盖**]**/Source:***值*[**/Destination:***值*] [**/Options:GacOnAdd***&#124;* **GacOnInstall***&#124;***GacOnImport**&#124;**RegasmOnInstall**&#124;**RegsvcsOnInstall**] [**/Server:***值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|向其添加程序集的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或**/T**，请参阅备注)|是|**System.BizTalk:Assembly** （此值不区分大小写。）|  
|**/ 覆盖**(或**/Ov**，请参阅备注)|是|更新现有程序集的选项。 如果未指定，且应用程序中已存在与要添加的程序集具有相同全名的程序集，则 AddResource 操作将失败。 全名包括程序集名称、版本、区域性和公钥标记。 此信息显示在 BizTalk Server 管理控制台中，即该应用程序的“资源”文件夹的“名称”字段中。|  
|**/ 源**(或**/So**，请参阅备注)|是|程序集文件的完整路径，包含文件名。 如果路径包含空格，则必须将它用双引号 （"）。|  
|**/ 目标**(或**/De**，请参阅备注)|是|从 .msi 文件安装应用程序时，程序集文件要复制到的位置的完整路径。 如果未提供，则安装期间该程序集文件将不会复制到本地文件系统。 如果路径包含空格，则必须将它用双引号 （"）。 如果指定 RegasmOnInstall 或 RegsvcsOnInstall 选项，则还必须指定 Destination。 **注意：**可用 %btad_installdir%环境变量来指定应用程序安装文件夹。 这将创建在其他目标计算机上的应用程序的文件的一致位置。 例如：“%BTAD_InstallDir%\MyAssemblies\Orchestrations.dll”|  
|**/ 选项**(或**/Op**，请参阅备注)|是|-   **GacOnAdd**： 在 AddResource 操作过程中在本地计算机上安装到全局程序集缓存 (GAC) 的程序集。<br />-   **GacOnInstall**： 从.msi 文件安装应用程序时，将程序集安装到 GAC。<br />-   **GacOnImport**： 导入应用程序.msi 文件时，将程序集安装到 GAC。<br />-   **RegasmOnInstall**： 将托管的 COM 程序集添加到 Windows 注册表中，从.msi 文件安装应用程序时。 如果指定此选项，则还必须指定 Destination。<br />-   **RegsvcsOnInstall**： 将托管的 COM + 程序集添加到 Windows 注册表中，从.msi 文件安装应用程序时。 如果指定此选项，则还必须指定 Destination。<br /><br /> 多个选项之间必须用逗号分开。 逗号和值之间不能有空格。|  
|**/ 服务器**(或**/Se**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或**/Da**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:Assembly / 覆盖 /Source:"%BTAD_InstallDir%\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd，RegasmOnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)