---
title: 如何向应用程序添加策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], adding to applications
- policies, applications
- applications, policies
- policies, adding to applications
ms.assetid: 93b3ce5e-8c63-4c64-9bdc-1747541ba9a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c67abd388f91e18072599e1697bde4acacaee8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387232"
---
# <a name="how-to-add-a-policy-to-an-application"></a>如何向应用程序添加策略
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加策略。 使用管理控制台时，可以一次添加多个策略。 将策略添加到应用程序使其可用于使用由该应用程序，以及对其进行引用的任何其他应用程序中。  
  
 当应用程序中添加一个策略，请记住以下重要事项：  
  
-   之前可以将策略添加到应用程序，该策略必须存在于 BizTalk 组中，规则引擎数据库中并且必须发布它，如中所述[如何导入策略](../core/how-to-import-a-policy.md)。  
  
    > [!NOTE]
    >  当使用规则引擎部署向导从规则引擎数据库中删除策略时，它仍将显示在管理控制台中，但您将无法再将其发布。 有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
-   该策略不能已存在于 BizTalk 组中的另一个应用程序。  
  
    > [!IMPORTANT]
    >  如果在两个或多个应用程序之间共享一个策略，则应创建单独的应用程序以包含此策略，然后创建从使用策略来包含该策略的应用程序的应用程序引用。 这是因为如果停止包含策略的应用程序，该策略将自动取消部署并不再为任何应用程序使用它的函数。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
-   对于策略才会生效并开始正常运行，它还必须部署。 策略自动部署应用程序启动时，或者你可以手动将它们部署中所述[如何部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-policy-to-an-application"></a>若要将策略添加到应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]和 BizTalk 组。  
  
3. 展开应用程序中，展开你想要添加的策略，然后右键单击该应用的程序**策略**。  
  
4. 指向**外**然后单击**策略**。  
  
5. 选择的每个策略和版本，以添加，然后单击复选框**确定**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Rules** [**覆盖**] **/Name:**<em>值</em>**/Version:**<em>值</em>[**/Server:**<em>值</em>] [**/Database:**<em>值</em>]  
  
   > [!NOTE]
   >  参数值都区分大小写。 参数名称不区分大小写。 此外，当通过使用此命令可将策略添加到应用程序中，该策略使用的任何词汇自动还将添加。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules /Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要将策略添加到 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。 包含空格的名称必须括在双引号 （"）。|  
   |**/Type**|**System.BizTalk:Rules**|  
   |**/Overwrite**|若要更新现有策略的选项。 如果未指定，且策略已存在具有相同的名称作为要添加的策略的应用程序中，则 AddResource 操作将失败。|  
   |**/Name**|策略的名称。|  
   |**/ 版本**|策略的版本号。|  
   |**/Server**|承载 BizTalk 管理数据库的 SQL Server 实例的名称。 如果指定的 Database 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果指定的 Server 参数被必需。 如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理策略](../core/managing-policies.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [AddResource 命令：策略](../core/addresource-command-policy.md)