---
title: "AddResource 命令： 证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e915043-6634-4644-8d69-376d762c7cec
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc2f1ca82dcd7a91f3572a4db96e9fc75f62839
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-certificate"></a>AddResource 命令：证书
若要将一个安全证书添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:Certificate**为类型参数。 要使此命令能够起作用，证书必须位于本地计算机上的“其他人”证书存储中。  
  
 运行此命令可将证书添加到 BizTalk 管理数据库中。 该证书还显示在 BizTalk Server 管理控制台中，具体位置为向其添加证书的应用程序的“资源”文件夹中。 此外，列出了当你使用的证书[ListApp 命令](../core/listapp-command.md)。  
  
 安装应用程序时，该证书被导入到本地计算机上的“其他人”证书存储中。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Certificate** [**/Overwrite**] **/Thumbprint:"***值***"** [**/Server:***值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|向其添加证书的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或**/Ty**，请参阅备注)|是|**System.BizTalk:Certificate** （此值不区分大小写。）|  
|**/ 覆盖**(或**/O**，请参阅备注)|是|更新现有证书的选项。 如果未指定，且应用程序中已存在与要添加的证书具有相同 Thumbprint 属性的证书，则 Add 操作将失败。 通过在证书管理单元中双击证书，再单击“详细信息”选项卡，可以查看它的 Thumbprint 属性。有关详细信息，请参阅证书管理单元文档中的“查看证书信息”。|  
|**/ 指纹**(或**/Th**，请参阅备注)|是|该证书指纹属性 (*指纹*是数据的摘要)。 此值必须放在双引号 (") 中。|  
|**/ 服务器**(或**/S**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或**/D**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:Certificate 覆盖 /Thumbprint:"04 a2 8e 32 24 f9 36 b9 42 81 12 71 3a d2 ef db c7 9c 83 dc"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)