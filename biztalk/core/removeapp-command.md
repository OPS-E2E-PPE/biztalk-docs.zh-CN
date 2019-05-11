---
title: RemoveApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 323290ae-8498-4ad6-9b06-a1d54640250e
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a670116f01343df2131835dfc225d93bb64a399d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397927"
---
# <a name="removeapp-command"></a>RemoveApp 命令
从 BizTalk 管理数据库中移除 （删除） BizTalk 应用程序以及所有包含的项目。 这不会卸载该应用程序。 有关执行此操作的说明，请参阅[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)。  
  
 在以下情况下，删除操作将失败：  
  
- **应用程序不会停止。** 有关停止应用程序的说明，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。 **ApplicationManager** SDK 示例安装在该示例<em>\<示例路径\>\\</em>Admin\ExplorerOM\ 目录说明了如何以编程方式启动或停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
- **其他应用程序包含对应用程序的引用。** 如果其他应用程序包含对要删除的应用程序的引用，您必须首先删除从其他应用程序的引用。 有关说明，请参阅[如何删除对另一个应用程序的引用](../core/how-to-remove-a-reference-to-another-application.md)。  
  
- **该应用程序包含发送端口组中另一个应用程序的发送端口的成员。** 可以删除该应用程序之前，必须取消登记该成员发送端口。 有关说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)。  
  
- **应用程序包含参与方引用的发送端口。** 可以从参与方删除该引用，或将发送端口移至不同的应用程序。 有关执行这些任务的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)或[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。  
  
- **应用程序是默认应用程序。** 如果你想要将其删除，必须先将另一个应用程序默认值。 有关说明，请参阅[如何更改默认应用程序](../core/how-to-change-the-default-application.md)。  
  
- **在应用程序中的业务流程登记、 启动或具有挂起的实例。** 有关业务流程的详细信息，请参阅[管理业务流程](../core/managing-orchestrations.md)。  
  
> [!NOTE]
>  如果应用程序包含处于已部署状态的策略，该策略不会从规则引擎数据库中删除，并继续下的策略文件夹中显示\<的所有项目\>BizTalk 应用程序节点管理控制台。 如果策略添加到另一个应用程序时，策略将保持已部署的状态。  
  
## <a name="usage"></a>用法  
 **BTSTask RemoveApp /ApplicationName:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|若要删除的 BizTalk 应用程序的名称。 如果名称包含空格，必须将其用双引号 （"）。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask RemoveApp /ApplicationName:MyApplication**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)