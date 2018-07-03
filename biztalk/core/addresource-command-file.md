---
title: AddResource 命令： 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9635e43-af26-48d3-af0e-df245a8955e7
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4878e74d1c45e5d75280a5ce9daf5447ed1e905
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982438"
---
# <a name="addresource-command-file"></a>AddResource 命令： 文件
若要将文件添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: file**类型参数。 运行此命令可将文件添加到 BizTalk 管理数据库中。 文件还会显示在 BizTalk 管理控制台中，即它所添加到的应用程序的“资源”文件夹中。 此外，当您使用列出该文件[ListApp 命令](../core/listapp-command.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:File** [**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|“否”|要将文件添加到 BizTalk 应用程序的名称。 如果路径包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: file** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|“否”|若要更新现有文件的选项。 如果未指定，且文件与要添加的文件具有相同名称的应用程序中已经存在，则 AddResource 操作将失败。|  
|**/Source** (或 **/So**，请参阅备注)|是|该文件，其中包括文件名的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ 目标**(或**De**，请参阅备注)|“否”|将文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。 如果未提供，该文件是期间不会复制到本地文件系统安装。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|“否”|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|“否”|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: system.biztalk: file / 覆盖 /Source:"C:\Source Files\File.txt"/Destination:"C:\New Files\File.txt"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Remarks  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)