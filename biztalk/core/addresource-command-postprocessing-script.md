---
title: AddResource 命令：后续处理脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d6d1622-1c90-4059-903e-68dcab829744
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f83660b1088796d126fe0c36c56ebd025aa7eb19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360502"
---
# <a name="addresource-command-postprocessing-script"></a>AddResource 命令：后续处理脚本
若要将后续处理脚本添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: postprocessingscript**类型参数。 运行此命令将脚本文件添加到 BizTalk 管理数据库。 脚本文件也显示在 BizTalk 管理控制台中，添加到应用程序的资源文件夹中。 此外，当您使用列出该文件[ListApp 命令](../core/listapp-command.md)。  
  
 应用程序导入或安装之后或在卸载之前，后续处理脚本从.msi 文件运行。 您也可以使用 BTSTask 添加预处理脚本，运行应用程序导入或安装之前或之后卸载，如中所述[AddResource 命令：预处理脚本](../core/addresource-command-preprocessing-script.md)。 有关预处理脚本和后续处理脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:PostProcessingScript**[**/Overwrite**]**/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>] [**/property: args ="**<em>参数列表</em>**"**]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要将脚本添加到 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: postprocessingscript** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|否|若要更新现有脚本的选项。 如果未指定，且脚本文件已存在与要添加，则添加操作将失败的脚本文件具有相同名称的应用程序中。|  
|**/Source** (或 **/So**，请参阅备注)|是|脚本文件，其中包括文件名的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ 目标**(或 **/De**，请参阅备注)|否|当从.msi 文件安装应用程序时将复制的脚本文件所在的位置的完整路径。 如果未提供，该文件是期间不会复制到本地文件系统安装。 如果此脚本应在应用程序卸载期间运行，则应指定 Destination;否则为该脚本将不会驻留在本地文件系统上，并且将不能在卸载期间运行。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
|**/ 属性**(或 **/P**，请参阅备注)|否|将传递给脚本作为自变量时调用脚本的零个或多个资源属性。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.biztalk: postprocessingscript / 覆盖 /Source:"C:\Source Scripts\MyScript.vbs"/Destination:"C:\New Scripts\MyScript.vbs"/Server:MyDatabaseServer /Database:BizTalkMgmtDb /property: args ="argument1 参数 2"**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
 为脚本文件支持下列扩展名：.com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf、.wsh。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何向应用程序添加预处理或后处理脚本](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)