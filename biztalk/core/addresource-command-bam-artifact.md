---
title: AddResource 命令：BAM 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9de7a82-9b06-4d50-9678-73140e80d0af
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc71e95bf1b78f6598c584031e0ab5dc10aaa614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360724"
---
# <a name="addresource-command-bam-artifact"></a>AddResource 命令：BAM 项目
若要将 BAM 项目添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: bam**类型参数。 运行此命令将 BAM 项目文件添加到 BizTalk 管理数据库。 BAM 项目还会显示在 BizTalk Server 管理控制台中，添加到应用程序的资源文件夹中。 此外，当您使用列出该文件[ListApp 命令](../core/listapp-command.md)。  
  
 使用 AddResource 命令添加 BAM 定义不会部署 BAM 定义。 一个包含 BAM 定义的.msi 文件导入应用程序使用导入向导，但是，BAM 定义部署到本地计算机。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Bam**[**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要向其中添加 BAM 项目的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: bam** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|否|若要更新现有 BAM 项目的选项。 如果未指定，且项目已存在具有相同的名称与要添加的 BAM 项目则 AddResource 操作将失败的应用程序中。|  
|**/Source** (或 **/So**，请参阅备注)|是|BAM 项目文件，其中包括文件名的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ 目标**(或**De**，请参阅备注)|否|BAM 项目文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供，该文件是期间不会复制到本地文件系统安装。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ 服务器**(或 **/Se**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam   /Overwrite /Source:"C:\Source BAMfiles\MyBAMfile.xml" /Destination:"C:\New BAMfiles\MyBAMfile.xml" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何向应用程序添加 BAM 项目](../core/how-to-add-a-bam-artifact-to-an-application.md)