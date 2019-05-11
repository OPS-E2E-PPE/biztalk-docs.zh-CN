---
title: 如何从应用程序和 BizTalk 组中删除策略 |Microsoft Docs
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
ms.openlocfilehash: beca719538949bd82b1d9ea442fb12c61c607e14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335068"
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a>如何从应用程序和 BizTalk 组中删除策略
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从应用程序和 BizTalk 组的规则引擎数据库中删除策略。  
  
 然后再删除策略，请记住以下重要事项：  
  
-   无法删除已部署的策略。 您必须首先取消部署策略，如中所述[如何部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)。 取消部署策略使它处于非活动状态，以便它不再使用 BizTalk 组中的任何应用程序中的函数。  
  
-   删除一个策略，将其删除从规则引擎数据库中。 如果你想要再次使用此策略，您应将其导出到一个.xml 文件，然后再删除它。 有关说明，请参阅[如何导出策略](../core/how-to-export-a-policy.md)。  
  
-   如果策略由其他应用程序，它将不再有效的其他应用程序。 验证不再想要为其删除之前对其进行引用的任何其他应用程序使用策略。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-a-policy"></a>若要删除策略  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开包含该策略的 BizTalk 组删除，，然后展开包含该策略的应用程序  
  
3. 单击**策略**，右键单击该策略，然后单击**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**  
  
   |参数|Description|  
   |---------------|-----------------|  
   |**/ApplicationName**|包含策略的 BizTalk 应用程序若要删除的名称。 如果未指定此参数，则使用默认应用程序。|  
   |**/Luid**|策略的本地唯一标识符 (LUID)。 可通过获得 LUID **ListApp**命令，如中所述[ListApp 命令](../core/listapp-command.md)。|  
   |**/Server**|承载 BizTalk 管理数据库的 SQL Server 实例的名称。 如果指定的 Database 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果指定的 Server 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理策略](../core/managing-policies.md)