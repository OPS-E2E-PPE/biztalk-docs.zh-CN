---
title: 如何从应用程序和 BizTalk 组中删除策略 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, policies
- managing [policies], applications
- managing [policies], deleting
- groups, policies
- managing [policies], groups
- applications, policies
ms.assetid: e9882cb3-8808-4258-a107-a24905290288
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4bb4b162d90811a4eddaa513556ecb1f6c6cd8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254509"
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a>如何从应用程序和 BizTalk 组中删除策略
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从应用程序和 BizTalk 组的规则引擎数据库中删除策略。  
  
 删除策略前，请注意以下重要事项：  
  
-   不能删除已部署的策略。 你必须首先取消部署策略中, 所述[如何部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)。 取消部署策略使它处于非活动状态，以便它不再函数中使用 BizTalk 组中任何应用程序。  
  
-   删除一个策略就是将其从规则引擎数据库中删除。 如果要再次使用此策略，应先将其导出到 .xml 文件，然后再删除它。 有关说明，请参阅[如何导出策略](../core/how-to-export-a-policy.md)。  
  
-   如果有其他应用程序使用此策略，则此策略对这些应用程序将不再有效。 请先确认您不再希望将此策略用于引用它的任何其他应用程序，然后再删除它。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-a-policy"></a>若要删除策略  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含策略的 BizTalk 组若要删除，，然后展开包含策略的应用程序  
  
3.  单击**策略**，右键单击的策略，然后单击**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask RemoveResource** [**/ApplicationName:***值*] **/Luid:***值*[**/Server:***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**/ 应用程序名称**|包含要删除的策略的 BizTalk 应用程序的名称。 如果未指定此参数，则使用默认的应用程序。|  
    |**/ Luid**|策略的本地唯一标识符 (LUID)。 你可以通过使用获取而定**ListApp**命令时中, 所述[ListApp 命令](../core/listapp-command.md)。|  
    |**/ 服务器**|承载 BizTalk 管理数据库的 SQL Server 实例的名称。 如果指定了“Database”参数，则此参数是必需的。 如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果指定了“Server”参数，则此参数是必需的。 如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理策略](../core/managing-policies.md)