---
title: AddResource 命令：COM 组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86a4f2fc-bbbe-4b4a-8008-2c79b3ebb6a1
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aabd3968c416b97b7a8f9dc89548313d97156b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360686"
---
# <a name="addresource-command-com-component"></a>AddResource 命令：COM 组件
若要将非托管的 COM 组件添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: com**类型参数。 运行此命令将 COM 组件添加到 BizTalk 管理数据库。 COM 组件还会显示在 BizTalk 管理控制台中，添加到应用程序的资源文件夹中。 此外，列出了该组件使用时[ListApp 命令](../core/listapp-command.md)。  
  
> [!NOTE]
>  如果添加 64 位非托管的 COM 或 COM + 组件，并尝试安装包括 32 位计算机上的 COM 或 COM + 组件的应用程序，将不会安装该组件。 它将只能在 64 位计算机上安装。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Com** [**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Options:Regsvr32OnInstall**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要向其中添加 COM 组件的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: com** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/Ov**，请参阅备注)|否|若要更新现有 COM 组件的选项。 如果未指定，且 COM 组件已存在具有相同的文件名作为 COM 组件添加，则 AddResource 操作将失败的应用程序中。|  
|**/Source** (或 **/So**，请参阅备注)|是|包括文件名称的 COM 组件.dll 文件的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ 目标**(或 **/De**，请参阅备注)|否|COM 组件.dll 文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供，该文件是期间不会复制到本地文件系统安装;因此，该组件无法添加到 Windows 注册表在安装过程。 如果路径包含空格，则必须将其括在双引号 （"）。 如果指定 Regsvr32OnInstallOption，则还必须指定 Destination。|  
|**/ 选项**(或 **/Op**，请参阅备注)|否|**Regsvr32OnInstall.** 指定要将 COM 组件添加到 Windows 注册表中，从.msi 文件安装应用程序。 如果指定此选项，则还必须指定 Destination。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Com  /Overwrite /Source:"C:\Source Components\COM.dll" /Destination:"C:\New Components\COM.dll" /Options:Regsvr32OnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)