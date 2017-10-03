---
title: "AddResource 命令： BAM 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9de7a82-9b06-4d50-9678-73140e80d0af
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2753be55fa8cf71b04bbf34d2fdfd8d1190e65e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-bam-artifact"></a>AddResource 命令：BAM 项目
若要将一个 BAM 项目添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:Bam**为类型参数。 运行此命令可将 BAM 项目文件添加到 BizTalk 管理数据库中。 该 BAM 项目还会显示在 BizTalk Server 管理控制台中，即它所添加到的应用程序的“资源”文件夹下。 此外，将列出该文件，当你使用[ListApp 命令](../core/listapp-command.md)。  
  
 使用 AddResource 命令添加 BAM 定义不会部署 BAM 定义。 而是在使用导入向导将包含 BAM 定义的 .msi 文件导入应用程序中时，BAM 定义才会部署到本地计算机。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Bam**[**/覆盖**] **/Source:***值*[**/Destination:***值*] [**/Server:** *值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|向其添加 BAM 项目的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或**/T**，请参阅备注)|是|**System.BizTalk:Bam** （此值不区分大小写。）|  
|**/ 覆盖**(或**/O**，请参阅备注)|是|更新现有 BAM 项目的选项。 如果未指定，且应用程序中已经存在与要添加的 BAM 项目名称相同的项目，则 AddResource 操作将失败。|  
|**/ 源**(或**/So**，请参阅备注)|是|BAM 项目文件的完整路径，包含文件名。 如果路径包含空格，必须将它括在双引号 （"）。|  
|**/ 目标**(或**De**，请参阅备注)|是|从 .msi 文件安装应用程序时，BAM 项目文件要复制到的位置的完整路径。 如果未提供，不复制文件到本地文件系统在安装过程。 如果路径包含空格，必须将它括在双引号 （"）。|  
|**/ 服务器**(或**/Se**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或**/Da**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:Bam / 覆盖 /Source:"C:\Source BAMfiles\MyBAMfile.xml"/Destination:"C:\New BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将一个 BAM 项目添加到应用程序](../core/how-to-add-a-bam-artifact-to-an-application.md)