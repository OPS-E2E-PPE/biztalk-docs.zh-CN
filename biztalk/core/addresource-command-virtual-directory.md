---
title: AddResource 命令： 虚拟目录 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 446be3b3-31da-4f03-81b5-3a75c8da6558
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f28605a4bac678cefaafcb853d3dcdc55994831
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230653"
---
# <a name="addresource-command-virtual-directory"></a>AddResource 命令： 虚拟目录
若要将网站或 Web 服务的虚拟目录添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:WebDirectory**为类型参数。 运行此命令可将该虚拟目录添加到 BizTalk 管理数据库中。 该虚拟目录还会显示在 BizTalk Server 管理控制台中，即它所添加到的应用程序的“资源”文件夹下。 此外，当你使用列出的虚拟目录[ListApp 命令](../core/listapp-command.md)。  
  
> [!IMPORTANT]
>  使用包含 https 的 URL 添加虚拟目录时，必须在指定的 URL 中使用 http，而不是 https。 如果使用 https，则添加虚拟目录的操作将失败。 即使添加时在 URL 中使用 http，Internet 信息服务元数据库中 URL 的 https 设置仍将有效，而且虚拟目录将正常工作。  
  
> [!NOTE]
>  如果添加的是 64 位版本 Web Services 的虚拟目录，而尝试在 32 位计算机上安装包含该虚拟目录的应用程序，则无法安装该虚拟目录。 它只能安装在 64 位计算机上。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [/**ApplicationName:***值*] **/Type:System.BizTalk:WebDirectory**[**/Overwrite**] **/Source:***值*[**/Destination:***值*] [**/Server:** *值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|虚拟目录要添加到的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.BizTalk:WebDirectory** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|是|更新现有虚拟目录的选项。 如果未指定，且应用程序中已经存在与要添加的虚拟目录同名的虚拟目录，则 AddResource 操作将失败。|  
|**/ 源**(或 **/S**，请参阅备注)|是|源虚拟目录的完整 URI。<br /><br /> 示例：<br /><br /> http://MyHost:80/MyPath/MyVirtualDirectory|  
|**/ 目标**(或 **/De**，请参阅备注)|是|从 .msi 文件安装应用程序时要分配给该虚拟目录的 URI。 如果未指定此参数，则使用 Source 参数的值，localhost 作为主机。|  
|**/ 服务器**(或 **/S**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:WebDirectory / 覆盖 /Source:http://Host1:90 / MyVirtualDirectory /Destination:http://Host2:90 / MyVirtualDirectory /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)