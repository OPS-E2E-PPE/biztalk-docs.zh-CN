---
title: AddResource 命令：虚拟目录 |Microsoft Docs
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
ms.openlocfilehash: de084d8ca925985373da2cb2606f6d016a20cdba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360279"
---
# <a name="addresource-command-virtual-directory"></a>AddResource 命令：虚拟目录
若要将网站或 Web services 的虚拟目录添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: webdirectory**类型参数。 运行此命令将虚拟目录添加到 BizTalk 管理数据库。 虚拟目录还会显示在 BizTalk Server 管理控制台中，添加到应用程序的资源文件夹中。 此外，使用时列出的虚拟目录[ListApp 命令](../core/listapp-command.md)。  
  
> [!IMPORTANT]
>  当添加包含 https 的 URL 与虚拟目录时，必须指定而不是 https 的 URL 中使用 http。 如果使用 https 时，要添加虚拟目录的操作将失败。 即使使用 http URL 中将其添加，Internet Information Services 元数据库中的 URL 的 https 设置将生效，和虚拟目录将正常工作。  
  
> [!NOTE]
>  如果从 64 位版本的 Web 服务中，添加虚拟目录，并尝试安装包括 32 位计算机上的虚拟目录的应用程序，将不安装的虚拟目录。 它将只能在 64 位计算机上安装。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [/**应用程序名称：**<em>值</em>] **/Type:System.BizTalk:WebDirectory**[**/overwrite**]**/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|                   参数                   | Required |                                                                                                                                                                                                                                                         ReplTest1                                                                                                                                                                                                                                                          |
|-----------------------------------------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **/ ApplicationName** (或 **/A**，请参阅备注) |    否    |                                                                                                                                要将虚拟目录添加到 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。                                                                                                                                 |
|      **/ 键入**(或 **/T**，请参阅备注)       |   是    |                                                                                                                                                                                                                          **System.biztalk: webdirectory** （此值不区分大小写。）                                                                                                                                                                                                                           |
|    **/ 覆盖**(或 **/O**，请参阅备注)    |    否    |                                                                                                                                               若要更新现有虚拟目录的选项。 如果未指定，且虚拟目录已存在具有相同的名称与要添加虚拟目录则 AddResource 操作将失败的应用程序中。                                                                                                                                                |
|     **/Source** (或 **/S**，请参阅备注)      |   是    |                                                                                                                                                                                                 源虚拟目录的完整 URI。<br /><br /> 示例：<br /><br /> http://MyHost:80/MyPath/MyVirtualDirectory                                                                                                                                                                                                 |
|  **/ 目标**(或 **/De**，请参阅备注)   |    否    |                                                                                                                                                    从.msi 文件安装应用程序时要分配给虚拟目录的 URI。 如果未指定此参数，然后源参数的值用于 localhost 作为主机。                                                                                                                                                    |
|     **/ 服务器**(或 **/S**，请参阅备注)      |    否    | 承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。 |
|    **/ 数据库**(或 **/Da**，请参阅备注)    |    否    |                                                                                                                                                                                     BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。                                                                                                                                                                                     |
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:WebDirectory /Overwrite /Source:<http://Host1:90/MyVirtualDirectory> /Destination:<http://Host2:90/MyVirtualDirectory> /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)