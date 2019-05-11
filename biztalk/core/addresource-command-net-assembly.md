---
title: AddResource 命令：.NET 程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef6ec298-35fe-4845-9549-685993d2c659
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1be8a6f2d6d4dc54c1c17e3c592acc50ce99e8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360541"
---
# <a name="addresource-command-net-assembly"></a>AddResource 命令：.NET 程序集
若要将.NET 程序集 （其中包括托管的 COM 或 COM + 组件） 添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: assembly**类型参数。 运行此命令将程序集添加到 BizTalk 管理数据库。 程序集还会显示在 BizTalk 管理控制台中，添加到应用程序的资源文件夹中。 此外，该程序集列出使用时[ListApp 命令](../core/listapp-command.md)。  
  
 如果程序集具有相同全名的程序集的应用程序中已存在，可以指定 Overwrite 参数。 全名包括名称、 公钥标记、 区域性和版本。 在这种情况下，现有程序集将被覆盖。 有关依赖关系的详细信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Assembly**[**/overwrite**]**/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Options:GacOnAdd**<em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**&#124;**RegasmOnInstall** &#124; **RegsvcsOnInstall**] [**/Server:**<em>值</em>] [**/database:** <em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要将程序集添加到 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: assembly** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/Ov**，请参阅备注)|否|若要更新的现有程序集的选项。 如果未指定，且程序集已经存在具有相同的全名作为要添加的程序集则 AddResource 操作将失败的应用程序中。 全名包括程序集名称、 版本、 区域性和公钥标记。 在 BizTalk Server 管理控制台中的应用程序的资源文件夹的名称字段中显示此信息。|  
|**/Source** (或 **/So**，请参阅备注)|是|包括文件名称的程序集文件的完整路径。 如果路径包含空格，必须将其用双引号 （"）。|  
|**/ 目标**(或 **/De**，请参阅备注)|否|程序集文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供，该程序集文件不复制到本地文件系统在安装过程。 如果路径包含空格，必须将其用双引号 （"）。 如果指定 RegasmOnInstall 或 RegsvcsOnInstall 选项，则还必须指定 Destination。 **注意：** 可以使用 %btad_installdir%环境变量来指定应用程序安装文件夹。 这将创建其他目标计算机上的应用程序的文件的一致位置。 示例:"BTAD_InstallDir%\MyAssemblies\Orchestrations.dll"|  
|**/ 选项**(或 **/Op**，请参阅备注)|否|-   **GacOnAdd**:在 AddResource 操作过程，在本地计算机上安装到全局程序集缓存 (GAC) 程序集。<br />-   **GacOnInstall**:从.msi 文件安装应用程序时，将程序集安装到 GAC。<br />-   **GacOnImport**:导入应用程序.msi 文件时，将程序集安装到 GAC。<br />-   **RegasmOnInstall**:从.msi 文件安装应用程序时，将托管的 COM 程序集添加到 Windows 注册表。 如果指定此选项，则还必须指定 Destination。<br />-   **RegsvcsOnInstall**： 将托管的 COM + 程序集添加到 Windows 注册表中，从.msi 文件安装应用程序。 如果指定此选项，则还必须指定 Destination。<br /><br /> 必须用逗号分隔多个选项。 可以使用逗号和值之间没有空格。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.biztalk: assembly / 覆盖 /Source:"%BTAD_InstallDir%\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd、 RegasmOnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)