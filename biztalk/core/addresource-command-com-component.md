---
title: "AddResource 命令： COM 组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86a4f2fc-bbbe-4b4a-8008-2c79b3ebb6a1
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 757c6f334d5f3bc694b7db201467be80a3a0bc87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-com-component"></a>AddResource 命令： COM 组件
若要将非托管的 COM 组件添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:Com**为类型参数。 运行此命令可将 COM 组件添加到 BizTalk 管理数据库中。 该 COM 组件还会显示在 BizTalk 管理控制台中，即它所添加到的应用程序的“资源”文件夹下。 此外，列出了该组件使用时[ListApp 命令](../core/listapp-command.md)。  
  
> [!NOTE]
>  如果添加 64 位的非托管 COM 或 COM+ 组件，并尝试在 32 位的计算机上安装包含 COM 或 COM+ 组件的应用程序，则不会安装该组件。 它将仅在 64 位计算机上安装。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Com** [**/覆盖**] **/Source:***值*[**/Destination:***值*] [**/Options:Regsvr32OnInstall**] [**/Server:***值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|向其添加 COM 组件的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或**/T**，请参阅备注)|是|**System.BizTalk:Com** （此值不区分大小写。）|  
|**/ 覆盖**(或**/Ov**，请参阅备注)|是|更新现有 COM 组件的选项。 如果未指定，且应用程序中已经存在与要添加的 COM 组件文件名相同的 COM 组件，则 AddResource 操作将失败。|  
|**/ 源**(或**/So**，请参阅备注)|是|COM 组件 .dll 文件的完整路径，包含文件名。 如果路径包含空格，必须将它括在双引号 （"）。|  
|**/ 目标**(或**/De**，请参阅备注)|是|从 .msi 文件安装应用程序时，COM 组件 .dll 文件要复制到的位置的完整路径。 如果未提供，则安装期间该文件将不会复制到本地文件系统；因此，在安装期间该组件不会添加到 Windows 注册表中。 如果路径包含空格，必须将它括在双引号 （"）。 如果指定 Regsvr32OnInstallOption，则还必须指定 Destination。|  
|**/ 选项**(或**/Op**，请参阅备注)|是|**Regsvr32OnInstall。** 指定从 .msi 文件安装应用程序时将 COM 组件添加到 Windows 注册表中。 如果指定此选项，则还必须指定 Destination。|  
|**/ 服务器**(或**/Se**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或**/Da**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:Com / 覆盖 /Source:"C:\Source Components\COM.dll"/Destination:"C:\New Components\COM.dll"/Options:Regsvr32OnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)