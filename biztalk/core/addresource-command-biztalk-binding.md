---
title: "AddResource 命令： BizTalk 绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69c732d3-82c8-4615-b68f-ed29b54ebbf3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00f9a5eac7d2c6f2be72ba78ee4c538ca505151e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="addresource-command-biztalk-binding"></a>AddResource 命令： BizTalk 绑定
若要将绑定文件添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:BizTalkBinding**为**类型**参数。 添加绑定文件时，可以为其指定部署环境。 以后导入该应用程序时，可以选择此部署环境来应用这些绑定。 可以将任意数量的绑定文件添加到 BizTalk 应用程序中，每个绑定文件为不同的部署环境而定制。 通过为要添加的每个绑定文件运行此命令，可以添加多个文件。  
  
 中所述，你可以添加绑定文件的程序集、 应用程序或组中，导出[ExportBindings 命令](../core/exportbindings-command.md)，然后使用 AddResource 命令绑定文件添加到应用程序。  
  
 运行此命令可将绑定文件添加到 BizTalk 管理数据库中，该文件显示在应用程序的“资源”文件夹下。 此外，将列出该文件，当你使用[ListApp 命令](../core/listapp-command.md)。 与导入绑定文件不同，添加绑定文件并不会立即更改现有绑定。 在该应用程序导入到另一个 BizTalk 组后，才应用这些绑定。  
  
 添加绑定文件时，可以使用可选的 "TargetEnvironment" /Property 参数来指定其部署环境。 该值可以是表示要将此文件中的绑定应用到的部署环境的任何字符串，如 Test 或 Production。 如果不指定 /Property 参数，值的值**\<默认\>**自动指定，并且此绑定文件将应用导入应用程序每次。  
  
 如果要导入的应用程序中包含一个或多个以这种方式明确添加的绑定文件，则可以通过指定 /Property 参数的值，选择要应用哪个或哪些绑定文件。 在导入应用程序时应用绑定。  
  
 由于绑定在导入过程中应用，所以已应用的绑定将被同名的新绑定所覆盖。 换言之，将应用的具有特定名称的最后一个绑定生效。 使用多个绑定文件时，请注意这一情况。 如果它们包含重复项，则最后应用的绑定文件生效。 导入应用程序时，绑定按如下顺序应用：  
  
1.  由 BizTalk Server 生成的、未通过绑定文件显式添加到应用程序但用户已经显式选择导出到应用程序 .msi 文件的应用程序绑定。  
  
2.  已经显式添加但尚未指定目标部署环境的绑定文件。 本组中的绑定可以按任何顺序应用。  
  
3.  已经显式添加并且具有与为导入应用程序而选的部署环境相匹配的关联目标部署环境的绑定。 本组中的绑定可以按任何顺序应用。  
  
 有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 有关使用绑定文件的背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:"***值***"**] **/Type:System.BizTalk:BizTalkBinding/Property:TargetEnvironment ="***值***"** [**/覆盖**] **/source:***值*[**/Server:***值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|绑定文件要添加到的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。|  
|**/ 键入**(或**/T**，请参阅备注)|是|**System.BizTalk:BizTalkBinding** （此值不区分大小写。）|  
|**/ 源**(或**/So**，请参阅备注)|是|绑定文件的完整路径，包含文件名。 如果路径包含空格，必须将它括在双引号 （"）。|  
|**/Property:TargetEnvironment =** (或**/P:TargetEnvironment =**，请参阅备注)|是|指定目标部署环境的字符串。 您可以使用任何字符串，如 Production。 示例： **/Property:TargetEnvironment ="Production"**<br /><br /> 如果未指定，值为**\<默认\>**自动应用。 该值区分大小写。 如果该值包含空格，则必须将其括在双引号 (") 中。 环境值的最大长度为 128 个字符。|  
|**/ 覆盖**(或**/Ov**，请参阅备注)|是|更新现有绑定文件的选项。 如果未指定，且应用程序中已经存在与要添加的文件同名的绑定文件，则 AddResource 操作将失败。|  
|**/ 服务器**(或**/Se**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或**/Da**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkBinding /Property:TargetEnvironment = 测试 /Source:"C:\Binding Files\MyBinding.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 属性名称区分大小写。 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)