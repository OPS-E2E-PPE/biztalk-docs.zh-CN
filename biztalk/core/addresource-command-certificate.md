---
title: AddResource 命令： 证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e915043-6634-4644-8d69-376d762c7cec
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e6fc335b3765299ee1b26b40d235e55240a2b53
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984942"
---
# <a name="addresource-command-certificate"></a>AddResource 命令：证书
若要添加到 BizTalk 应用程序安全证书，请使用**AddResource**命令并指定**system.biztalk: certificate**类型参数。 要使此命令能够起作用，证书必须位于本地计算机上的“其他人”证书存储中。  
  
 运行此命令可将证书添加到 BizTalk 管理数据库中。 该证书还显示在 BizTalk Server 管理控制台中，具体位置为向其添加证书的应用程序的“资源”文件夹中。 此外，列出了当你使用的证书[ListApp 命令](../core/listapp-command.md)。  
  
 安装应用程序时，该证书被导入到本地计算机上的“其他人”证书存储中。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Certificate** [**/overwrite**]**/Thumbprint:"**<em>值</em>**"** [**/Server:**<em>值</em>] [**/数据库：**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|“否”|向其添加证书的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/Ty**，请参阅备注)|是|**System.biztalk: certificate** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|“否”|更新现有证书的选项。 如果未指定，且应用程序中已存在与要添加的证书具有相同 Thumbprint 属性的证书，则 Add 操作将失败。 通过在证书管理单元中双击证书，再单击“详细信息”选项卡，可以查看它的 Thumbprint 属性。有关详细信息，请参阅证书管理单元文档中的“查看证书信息”。|  
|**/ 指纹**(或 **/Th**，请参阅备注)|是|证书的指纹属性 (*指纹*是数据的摘要)。 此值必须放在双引号 (") 中。|  
|**/ 服务器**(或 **/S**，请参阅备注)|“否”|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|“否”|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: system.biztalk: certificate 覆盖 /Thumbprint:"04 a2 8e 32 24 f9 36 b9 42 81 12 71 3a d2 ef db c7 9 c 83 dc"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Remarks  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)