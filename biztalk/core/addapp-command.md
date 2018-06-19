---
title: AddApp 命令 |Microsoft 文档
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
ms.openlocfilehash: 2a6b91faa406181db3e4195bf57baeb086a0b69e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229997"
---
# <a name="addapp-command"></a>AddApp 命令
在 BizTalk 管理数据库中创建新的 BizTalk 应用程序。 在 BizTalk Server 管理控制台的“应用程序”节点中可查看该应用程序。 你可以添加项目到应用程序使用 AddResource 命令中所述[AddResource 命令](../core/addresource-command.md)。  
  
## <a name="usage"></a>用法  
 **BTSTask AddApp /ApplicationName:** *值*[**/Description:***值*] [**/默认**] [**/服务器：***值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|要添加的 BizTalk 应用程序的名称。 如果应用程序名称包含空格，它必须括在双引号 （"） 中。|  
|**/ 默认**(或 **/Def**，请参阅备注)|是|如果指定，使新的应用程序的默认应用程序的 BizTalk 组。|  
|**/ 说明**(或 **/Des**，请参阅备注)|是|应用程序的说明。 必须将其放在双引号 (") 中。|  
|**/ 服务器**(或 **/S**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **AddApp /ApplicationName:MyApplication /Description:"我 BizTalk 应用程序"**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何创建应用程序](../core/how-to-create-an-application.md)