---
title: 如何从应用程序中删除业务流程 |Microsoft Docs
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
ms.openlocfilehash: 0a3dbca1d838ca2691dcbfd1174debe49cbf0362
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335035"
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a>如何从应用程序中删除业务流程
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序中删除业务流程。 从应用程序中删除业务流程还将其从删除的 BizTalk 组的 BizTalk 管理数据库。  
  
 在删除某个业务流程，将发生以下情况：  
  
- 从 BizTalk 管理数据库中删除该业务流程。  
  
- 包含该业务流程的 BizTalk 程序集从 BizTalk 管理数据库中删除，但不是会从本地文件系统或全局程序集缓存 (GAC) 中，如果两个位置存在。  
  
- 正在删除 BizTalk 程序集，因此从 BizTalk 管理数据库中删除包含在程序集中的所有项目。  
  
  从应用程序中删除业务流程前, 请记住以下重要事项：  
  
- 如果其他项目在此业务流程或中也将被删除的程序集中包含的项目上的依赖项，它们将无法再正常运行时删除该业务流程。 有关依赖项的背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
- 不能删除有正在运行的实例的业务流程。 必须终止任何正在运行的实例。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-an-orchestration-from-an-application"></a>若要从应用程序中删除业务流程  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的业务流程的应用程序。  
  
3. 单击**业务流程**，右键单击该业务流程，然后单击**取消登记**。  
  
4. 选择业务流程，指向**视图**，然后单击**实例信息**。  
  
5. 在查询结果窗格中，右键单击业务流程实例，然后单击**Terminate**。  
  
   > [!NOTE]
   >  可以取消登记、 终止正在运行的实例，并停止所有的应用程序中的业务流程立即通过应用程序，使用完全停止选项中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
6. 单击**业务流程**，右键单击该业务流程，然后单击**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**  
  
   |参数|Description|  
   |---------------|-----------------|  
   |**/ApplicationName**|包含该业务流程的 BizTalk 应用程序若要删除的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定此参数，则使用默认应用程序。|  
   |**/Luid**|业务流程的本地唯一标识符 (LUID)。 可通过获得 LUID [ListApp 命令](../core/listapp-command.md)。|  
   |**/Server**|承载 BizTalk 管理数据库的 SQL Server 实例的名称。 如果指定的 Database 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果指定的 Server 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [RemoveResource 命令](../core/removeresource-command.md)