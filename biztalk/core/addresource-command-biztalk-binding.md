---
title: AddResource 命令：BizTalk 绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69c732d3-82c8-4615-b68f-ed29b54ebbf3
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1a8d114d474e1c9033778bb7903c2d1d9e5f1ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360654"
---
# <a name="addresource-command-biztalk-binding"></a>AddResource 命令：BizTalk 绑定
若要将绑定文件添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: biztalkbinding**有关**类型**参数。 当你添加绑定文件时，可以为其指定部署环境。 更高版本导入应用程序时，可以选择此部署环境来应用这些绑定。 可以将任意数量的绑定文件添加到 BizTalk 应用程序，为不同的部署环境自定义每个。 通过运行以下命令可添加的每个文件进行添加多个绑定文件。  
  
 您可以添加程序集、 应用程序或组，为导出的绑定文件中所述[ExportBindings 命令](../core/exportbindings-command.md)，然后使用 AddResource 命令将绑定文件添加到应用程序。  
  
 运行此命令将绑定文件添加到 BizTalk 管理数据库，并显示应用程序的资源文件夹中的文件。 此外，当您使用列出该文件[ListApp 命令](../core/listapp-command.md)。 与导入绑定文件，不同上添加绑定文件不会立即更改现有绑定。 直到应用程序导入到另一个 BizTalk 组，不会应用这些绑定。  
  
 当你添加绑定文件时，可以通过使用可选的"TargetEnvironment"/Property 参数来指定其部署环境。 值可以是任何字符串，表示要在其中应用此文件，如测试或生产环境中的绑定的部署环境。 如果不指定 /Property 参数的值的值**\<默认\>** 自动指定，并且此绑定文件将应用每次导入应用程序。  
  
 导入包含一个或多个以这种方式明确添加的绑定文件的应用程序时，可以选择哪些绑定文件或文件以应用通过指定 /Property 参数的值。 在应用程序导入应用绑定。  
  
 当导入过程中应用绑定时，已应用的绑定将覆盖具有相同名称的新绑定。 换而言之，具有特定名称的最后一个绑定，应用将生效。 请注意此时使用多个绑定文件。 如果它们包含重复项，最后应用的绑定将生效。 导入应用程序时，绑定按以下顺序应用：  
  
1. 应用程序绑定由 BizTalk Server 生成的未显式添加到应用程序通过绑定文件，但已经显式选择导出到应用程序.msi 文件的用户。  
  
2. 已显式添加，并且没有指定目标部署环境的绑定文件。 在此集中的绑定可以按任何特定顺序应用。  
  
3. 绑定已显式添加的且具有相关联的目标部署环境为应用程序导入选择的部署环境相匹配。 在此集中的绑定可以按任何特定顺序应用。  
  
   有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 有关使用绑定文件的背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:"**<em>值</em>**"**] **/Type:System.BizTalk:BizTalkBinding/Property:TargetEnvironment="**<em>值</em>**"** [**/覆盖**] **/source:**<em>值</em>[**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要将绑定文件添加到 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: biztalkbinding** （此值不区分大小写。）|  
|**/Source** (或 **/So**，请参阅备注)|是|绑定文件，其中包括文件名的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/Property:TargetEnvironment =** (或 **/P:TargetEnvironment =**，请参阅备注)|否|一个字符串，指定目标部署环境。 可以使用任意字符串，例如生产。 示例： **/Property:TargetEnvironment ="生产"**<br /><br /> 如果未指定的值**\<默认\>** 自动应用。 值是区分大小写。 如果值包含空格，则必须将其括在双引号 （"）。 环境值的最大长度为 128 个字符。|  
|**/ 覆盖**(或 **/Ov**，请参阅备注)|否|若要更新现有绑定文件的选项。 如果未指定，且绑定文件已经存在与要添加的文件具有相同文件名的应用程序中，则 AddResource 操作将失败。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkBinding /Property:TargetEnvironment = 测试 /Source:"C:\Binding Files\MyBinding.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 属性名称不区分大小写。 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)