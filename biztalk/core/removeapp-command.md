---
title: RemoveApp 命令 |Microsoft 文档
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
ms.openlocfilehash: 05269411c81aeccdaf1c30e36e47c02787bf044a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972155"
---
# <a name="removeapp-command"></a>RemoveApp 命令
从 BizTalk 管理数据库中删除 BizTalk 应用程序及其包含的所有项目。 这不会卸载该应用程序。 有关执行此操作的说明，请参阅[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)。  
  
 在以下情况下，删除操作会失败：  
  
-   **应用程序不会停止。** 有关停止应用程序的说明，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。 **ApplicationManager** SDK 示例中会安装*\<示例路径\>\\*Admin\ExplorerOM\ 目录说明了如何以编程方式启动或停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
-   **其他应用程序包含对应用程序的引用。** 如果其他应用程序包含对要删除的应用程序的引用，则必须先从其他应用程序中删除这类引用。 有关说明，请参阅[如何移除对另一个应用程序的引用](../core/how-to-remove-a-reference-to-another-application.md)。  
  
-   **应用程序包含在另一个应用程序中的发送端口是其成员的发送端口组。** 要删除该应用程序，必须先取消登记该成员发送端口。 有关说明，请参阅[如何发送端口或发送端口组中取消](../core/how-to-unenlist-a-send-port-or-send-port-group.md)。  
  
-   **应用程序包含引用的参与方发送端口。** 您可以删除参与方的该引用，或将该发送端口移至另一个应用程序。 有关执行这些任务的说明，请参阅[如何查看或编辑方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)或[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。  
  
-   **应用程序是默认应用程序。** 如果要删除这种应用程序，必须先将其他应用程序设置为默认应用程序。 有关说明，请参阅[如何更改默认的应用程序](../core/how-to-change-the-default-application.md)。  
  
-   **应用程序中的业务流程程序登记之后，启动，或具有挂起的实例。** 有关业务流程的详细信息，请参阅[管理业务流程](../core/managing-orchestrations.md)。  
  
> [!NOTE]
>  如果应用程序包含在已部署状态的策略，策略不从规则引擎数据库中删除，并且继续在下的策略文件夹中显示\<所有项目\>的 BizTalk 应用程序节点管理控制台。 如果将该策略添加到另一个应用程序，则该策略仍处于已部署状态。  
  
## <a name="usage"></a>用法  
 **BTSTask RemoveApp /ApplicationName:** *值*[**/Server:***值*] [**/数据库：** *值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|要删除的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将它用双引号 （"）。|  
|**/ 服务器**(或 **/S**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask RemoveApp /ApplicationName:MyApplication**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)