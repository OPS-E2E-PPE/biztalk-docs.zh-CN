---
title: 如何从应用程序删除业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, orchestrations
- deleting, orchestrations
- managing [orchestrations], deleting
- orchestrations, applications
- orchestrations, deleting
ms.assetid: e6d635ea-3513-42de-a667-b56c536e5328
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4909f5430ae2d0435d519823abe9735cbc1cc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255189"
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a>如何从应用程序删除业务流程
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序中删除业务流程。 从应用程序中删除业务流程，也会将该业务流程从 BizTalk 组的 BizTalk 管理数据库中删除。  
  
 删除业务流程时，将执行以下操作：  
  
-   将从 BizTalk 管理数据库中删除该业务流程。  
  
-   将删除 BizTalk 管理数据库中包含该业务流程的 BizTalk 程序集，如果该程序集还存在于本地文件系统或全局程序集缓存 (GAC) 中，则不会将这两个位置中的该程序集删除。  
  
-   由于删除了 BizTalk 程序集，因此也将从 BizTalk 管理数据库中删除该程序集所包含的所有项目。  
  
 从应用程序中删除业务流程前，请切记以下几点：  
  
-   如果有其他项目依赖于此业务流程或依赖于将连带删除的程序集中包含的项目，则删除此业务流程后这些项目将无法正常工作。 有关依赖关系的背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
-   不能删除有正在运行的实例的业务流程。 必须终止任何正在运行的实例。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-an-orchestration-from-an-application"></a>从应用程序中删除业务流程  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的业务流程的应用程序。  
  
3.  单击**业务流程**，业务流程中，右键单击，然后单击**Unenlist**。  
  
4.  选择的业务流程，指向**视图**，然后单击**实例信息**。  
  
5.  在查询结果窗格中，业务流程实例中，右键单击，然后单击**终止**。  
  
    > [!NOTE]
    >  可以取消登记、 终止正在运行的实例，并停止所有的应用程序中的业务流程一次通过使用应用程序，完全停止选项中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
6.  单击**业务流程**，业务流程中，右键单击，然后单击**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask RemoveResource** [**/ApplicationName:***值*] **/Luid:***值*[**/Server:***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations，版本 = 1.0.0.0，Culture = neutral，PublicKeyToken = 0123456789ABCDEF"**  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**/ 应用程序名称**|包含要删除的业务流程的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定此参数，则使用默认的应用程序。|  
    |**/ Luid**|业务流程的本地唯一标识符 (LUID)。 你可以通过使用获取而定[ListApp 命令](../core/listapp-command.md)。|  
    |**/ 服务器**|承载 BizTalk 管理数据库的 SQL Server 实例的名称。 如果指定了“Database”参数，则此参数是必需的。 如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果指定了“Server”参数，则此参数是必需的。 如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [RemoveResource 命令](../core/removeresource-command.md)