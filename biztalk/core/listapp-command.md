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
ms.openlocfilehash: e397fe9ad768ffa367c6699ec2f3abb4006e4a26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328723"
---
# <a name="listapp-command"></a>ListApp 命令
所有 BizTalk 应用程序，以及本地唯一标识符 (LUID) 和类型的每个项目中的资源项目的列表输出到控制台。 资源项目是可以通过使用添加到 BizTalk 应用程序[AddResource 命令](../core/addresource-command.md)，如程序集、 脚本、 文件、 策略、 COM 组件、 虚拟目录、 BAM 项目或证书。 这些资源项目还会显示在 BizTalk Server 管理控制台的资源节点中。  
  
 如果指定此命令的 ResourceSpec 参数，则相同的信息写入一个.xml 文件。 可以使用此.xml 文件，其**ExportApp**命令，将导出到.msi 文件，应用程序中的项目的子集，如中所述[ExportApp 命令](../core/exportapp-command.md)。  
  
 对于虚拟目录，此命令将替换为 Web 服务器主机名"localhost"。 如果使用 ExportApp 命令的 ResourceSpec 参数生成的文件，则手动编辑要替换的主机名为"localhost"和端口号，如果 Web 服务器存在于远程计算机上的文件。 如果不这样做，虚拟目录及其内容将不会添加到应用程序.msi 文件。  
  
 示例： http://MyWebServer:80/MyVirtualDirectory。  
  
## <a name="usage"></a>用法  
 **BTSTask ListApp** [**/ApplicationName:**<em>value</em>] [**/ResourceSpec:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|向 BizTalk 应用程序的项目列表的名称。 如果名称包含空格，必须将其用双引号 （"）。  如果未指定此参数，则使用默认应用程序。|  
|**/ ResourceSpec** (或 **/R**，请参阅备注)|否|若要使用此命令生成的.xml 文件的完整路径。 此文件将列出应用程序，以及的 LUID 和类型的每个中的项目。 例如：C:\Artifacts\MyArtifacts.xml. 如果路径包含空格，则必须用双引号 （"）。 如果已具有相同的路径和文件名称的文件存在，则将覆盖。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask ListApp /ApplicationName:MyApplication /ResourceSpec:C:\Artifacts\MyArtifacts.xml**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)