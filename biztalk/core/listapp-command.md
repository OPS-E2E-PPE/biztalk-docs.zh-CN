---
title: ListApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5329dd55-4ce7-46d2-8983-90ac33725055
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51299b6f3488e1088fac2b903c9146bee93885e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987302"
---
# <a name="listapp-command"></a>ListApp 命令
将 BizTalk 应用程序中所有资源项目的列表以及每个项目的本地唯一标识符 (LUID) 和类型输出到控制台。 资源项目是可以通过使用添加到 BizTalk 应用程序[AddResource 命令](../core/addresource-command.md)，如程序集、 脚本、 文件、 策略、 COM 组件、 虚拟目录、 BAM 项目或证书。 这些资源项目还会显示在 BizTalk Server 管理控制台的“资源”节点下。  
  
 如果为此命令指定 ResourceSpec 参数，则相同的信息将被写入 .xml 文件中。 可以使用此.xml 文件，其**ExportApp**命令，将导出到.msi 文件，应用程序中的项目的子集，如中所述[ExportApp 命令](../core/exportapp-command.md)。  
  
 对于虚拟目录，此命令将“localhost”替换为 Web 服务器主机名。 如果使用 ExportApp 命令的 ResourceSpec 参数所生成的文件，则在 Web 服务器存在于远程计算机时，需要手动编辑该文件，将“localhost”替换为主机名和端口号。 如果不这样做，虚拟目录及其内容将不添加到应用程序的 .msi 文件中。  
  
 示例： http://MyWebServer:80/MyVirtualDirectory。  
  
## <a name="usage"></a>用法  
 **BTSTask ListApp** [**/ApplicationName:**<em>值</em>] [**/ResourceSpec:**<em>值</em>] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|“否”|要列出其项目的 BizTalk 应用程序的名称。 如果名称包含空格，必须将其用双引号 （"）。  如果未指定此参数，则使用默认的应用程序。|  
|**/ ResourceSpec** (或 **/R**，请参阅备注)|“否”|要用此命令生成的 .xml 文件的完整路径。 此文件将列出应用程序中的各个项目，以及每个项目的 LUID 和类型。 示例： C:\Artifacts\MyArtifacts.xml。 如果路径包含空格，则必须用双引号 （"）。 如果已存在具有相同路径和文件名的文件，则该文件将被覆盖。|  
|**/ 服务器**(或 **/S**，请参阅备注)|“否”|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|“否”|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask ListApp /ApplicationName:MyApplication /ResourceSpec:C:\Artifacts\MyArtifacts.xml**  
  
## <a name="remarks"></a>Remarks  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)