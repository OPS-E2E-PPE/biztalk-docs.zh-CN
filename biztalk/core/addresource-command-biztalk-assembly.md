---
title: AddResource 命令：BizTalk 程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c18607b5-d929-48c9-9fa3-f728a7a80d04
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74237bdbcc5298ad4f5895922599aefd32f932e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360750"
---
# <a name="addresource-command-biztalk-assembly"></a>AddResource 命令：BizTalk 程序集
若要将 BizTalk 程序集添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: biztalkassembly**类型参数。 运行此命令将程序集添加到 BizTalk 管理数据库。 程序集还会显示在 BizTalk Server 管理控制台中，添加到应用程序的资源文件夹中。 在程序集中包含的项目也会显示在相应的文件夹。 此外，当您使用列出这些项目[ListApp 命令](../core/listapp-command.md)。  
  
 使用此命令时，请记住以下几点：  
  
- 如果程序集具有相同全名的程序集的应用程序中已存在，则必须指定 Overwrite 参数或 AddResource 操作将失败。 全名包括名称、 公钥标记、 区域性和版本。 如果另一个应用程序依赖于此程序集，但是，即使您指定 Overwrite 参数时，则 AddResource 操作将失败。  
  
- 如果组中存在具有相同的完整名称的另一个程序集，则 AddResource 操作将失败，即使您指定 Overwrite 参数。  
  
- 如果要覆盖包含业务流程的程序集，必须停止并在运行此命令之前已取消登记业务流程。 此外，必须停止并取消登记，业务流程绑定到的端口的发送和接收位置被禁用。  
  
- 如果要添加的程序集不包含在应用程序中的另一个项目上具有依赖项，则 AddResource 操作将失败。  
  
  有关依赖关系的详细信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:BizTalkAssembly** [**/Overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Options:GacOnAdd** <em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要将程序集添加到 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: biztalkassembly** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/Ov**，请参阅备注)|否|若要更新的现有程序集的选项。 如果未指定，且程序集已经存在具有相同的全名作为要添加的程序集则 AddResource 操作将失败的应用程序中。 完整名称为程序集对应的本地唯一标识符 (LUID)。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。 如果另一个应用程序依赖于被覆盖的程序集，则 AddResource 操作将失败，即使指定了此参数。|  
|**/Source** (或 **/So**，请参阅备注)|是|包括文件名称的程序集文件的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ 目标**(或 **/De**，请参阅备注)|否|程序集文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供，该程序集文件不复制到本地文件系统在安装过程。 如果路径包含空格，则必须将其括在双引号 （"）。 **注意：** 环境变量 %btad_installdir%，在 BizTalk Server 安装过程中设置，可用于指定应用程序安装文件夹。 这将创建其他目标计算机上的应用程序的文件的一致位置。 示例:"BTAD_InstallDir%\MyFiles\Orchestrations.dll"|  
|**/ 选项**(或 **/Op**，请参阅备注)|否|-   **GacOnAdd**:指定将程序集安装到全局程序集缓存 (GAC) 在本地计算机上在 AddResource 操作过程。<br />-   **GacOnInstall**:指定从.msi 文件安装应用程序时，将程序集安装到 GAC。<br />-   **GacOnImport**:指定要导入应用程序.msi 文件时，将程序集安装到 GAC。<br /><br /> 必须用逗号分隔多个选项。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkAssembly /Overwrite**  
  
 **/Source:"%BTAD_InstallDir%\Source Assemblies\Orchestrations.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\Orchestrations.dll"/Options:GacOnInstall，GacOnImport /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)