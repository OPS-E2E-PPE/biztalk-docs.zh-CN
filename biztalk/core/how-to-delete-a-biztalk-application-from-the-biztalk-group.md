---
title: 如何从 BizTalk 组中删除 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeploying, applications
- applications, deleting
- applications, groups
- undeploying, deleting
- managing [applications], deleting
- deleting, applications
- applications, undeploying
- managing [applications], groups
- groups, applications
ms.assetid: 968a6436-ae1a-4f85-bb44-e704826a0197
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3125ef9bc0f30b944c487c2edcba70e1e270dbc4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385375"
---
# <a name="how-to-delete-a-biztalk-application-from-the-biztalk-group"></a>如何从 BizTalk 组中删除 BizTalk 应用程序
您可以从 BizTalk 组中删除应用程序。 这从组中，BizTalk 数据库中删除其所有数据和应用程序将不再显示在 BizTalk Server 管理控制台。 它不会卸载该应用程序。  
  
 删除应用程序之前，请切记以下几点：  
  
-   必须先停止应用程序，可以将其删除。 您应该用于完全停止选项停止应用程序，如中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
-   仅当没有其他应用程序包含对它的引用，可以删除应用程序。 如果其他应用程序包含对要删除的应用程序的引用，您必须首先删除从其他应用程序的引用。 有关说明，请参阅[如何删除对另一个应用程序的引用](../core/how-to-remove-a-reference-to-another-application.md)。  
  
-   如果它包含发送端口组中另一个应用程序的发送端口的成员，则无法删除应用程序。 可以删除该应用程序之前，必须取消登记该成员发送端口。 有关说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)。  
  
-   如果它包含参与方引用的发送端口，则无法删除应用程序。 可以从参与方删除该引用，删除该发送端口，或将发送端口移至不同的应用程序。 有关执行这些任务的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)，[如何删除发送端口](../core/how-to-delete-a-send-port.md)，或[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。  
  
-   无法删除默认应用程序。 如果你想要将其删除，必须先将另一个应用程序默认值。 有关说明，请参阅[如何更改默认应用程序](../core/how-to-change-the-default-application.md)。  
  
-   如果应用程序中的业务流程具有挂起的实例，则无法删除应用程序。  
  
-   若要完全取消部署 BizTalk 应用程序，您必须执行中所述的步骤[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)，并且可能还需要删除其他文件和设置，如中所述[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-delete-a-biztalk-application"></a>若要删除的 BizTalk 应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。  
  
3. 右键单击应用程序文件夹中，然后依次**删除**。  
  
4. 单击**是**以确认删除。  
  
    BizTalk Server 将从 BizTalk 数据库删除所有应用程序数据，并从管理控制台删除应用程序。  
  
    如果 BizTalk Server 无法删除的任何应用程序项目，则删除操作失败。 在这种情况下，BizTalk Server 将尝试回滚删除操作。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveApp /ApplicationName:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask RemoveApp /ApplicationName:MyApplication**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|若要删除的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Server**|承载 BizTalk 管理数据库的 SQL Server 实例的名称。 如果指定的 Database 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果指定的 Server 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)