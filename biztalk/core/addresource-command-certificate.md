---
title: AddResource 命令：证书 |Microsoft Docs
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
ms.openlocfilehash: 5ef8ea4f43107683eda7ef7fc7d128b3f42c1a6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360714"
---
# <a name="addresource-command-certificate"></a>AddResource 命令：证书
若要添加到 BizTalk 应用程序安全证书，请使用**AddResource**命令并指定**system.biztalk: certificate**类型参数。 若要运行此命令，该证书必须是本地计算机上的其他人证书存储中存在。  
  
 运行此命令将证书添加到 BizTalk 管理数据库。 在 BizTalk Server 管理控制台中，添加到应用程序的资源文件夹中还显示了证书。 此外，列出了当你使用的证书[ListApp 命令](../core/listapp-command.md)。  
  
 在安装应用程序时，证书将导入本地计算机上的其他人证书存储中。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Certificate** [**/overwrite**]**/Thumbprint:"**<em>值</em>**"** [**/Server:**<em>值</em>] [**/数据库：**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要将证书添加到 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。|  
|**/ 键入**(或 **/Ty**，请参阅备注)|是|**System.biztalk: certificate** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|否|若要更新现有证书的选项。 如果未指定，且证书已存在具有相同 Thumbprint 属性为要添加，则添加操作将失败的证书的应用程序中。 可以通过双击证书管理单元中的证书，然后单击详细信息选项卡查看指纹属性。有关详细信息，请参阅"查看证书信息"文档中的证书管理单元中。|  
|**/ 指纹**(或 **/Th**，请参阅备注)|是|证书的指纹属性 (*指纹*是数据的摘要)。 此值必须括在双引号 （"）。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Certificate  /Overwrite /Thumbprint:"04 a2 8e 32 24 f9 36 b9 42 81 12 71 3a d2 ef db c7 9c 83 dc" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)