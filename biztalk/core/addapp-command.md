---
title: AddApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 445784f1-505b-4259-a3f4-6f0d61578b1c
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adefbfa2e2f9e92b606c9d46bd881b64ddd0864
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360988"
---
# <a name="addapp-command"></a>AddApp 命令
在 BizTalk 管理数据库中创建新的 BizTalk 应用程序。 您可以在 BizTalk Server 管理控制台的应用程序节点中查看应用程序。 您可以将项目添加到应用程序使用 AddResource 命令，如中所述[AddResource 命令](../core/addresource-command.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddApp /ApplicationName:** *value* [**/Description:**<em>value</em>] [**/Default**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|若要添加的 BizTalk 应用程序的名称。 如果应用程序名称包含空格，则必须放在双引号 （"） 中。|  
|**/ 默认**(或 **/Def**，请参阅备注)|否|如果指定，使新的应用程序的 BizTalk 组的默认应用程序。|  
|**/ 描述**(或 **/Des**，请参阅备注)|否|应用程序的说明。 必须括在双引号 （"）。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **AddApp /ApplicationName:MyApplication /Description:"My BizTalk application"**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何创建应用程序](../core/how-to-create-an-application.md)