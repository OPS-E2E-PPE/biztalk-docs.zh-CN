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
ms.openlocfilehash: e2fe3d2b217757d9d06b1954a5d950f4ea88bd91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004062"
---
# <a name="how-to-add-a-policy-to-an-application"></a>如何向应用程序添加策略
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加策略。 使用管理控制台时，可以一次添加多个策略。 将策略添加到应用程序后，该策略可供该应用程序以及引用它的任何其他应用程序使用。  
  
 向应用程序中添加策略时，请切记以下几点：  
  
-   之前可以将策略添加到应用程序，该策略必须存在于 BizTalk 组中，规则引擎数据库中并且必须发布它，如中所述[如何导入策略](../core/how-to-import-a-policy.md)。  
  
    > [!NOTE]
    >  当使用规则引擎部署向导从规则引擎数据库中删除某个策略时，该策略仍将显示在管理控制台中，但您将无法发布该策略。 有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
-   该策略不能存在于 BizTalk 组的其他应用程序中。  
  
    > [!IMPORTANT]
    >  如果有两个或更多应用程序共享一个策略，应创建一个单独的应用程序以包含此策略，然后创建从使用该策略的应用程序到包含该策略的应用程序的引用。 这是因为，如果您停止一个包含策略的应用程序，该策略将自动取消部署，并且不能再为使用它的任何应用程序发挥作用。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
-   若要使策略生效并发挥作用，还必须部署此策略。 策略自动部署应用程序启动时，或者你可以手动将它们部署中所述[如何部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-policy-to-an-application"></a>向应用程序添加策略  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”和“BizTalk 组”。  
  
3. 展开应用程序中，展开你想要添加的策略，然后右键单击该应用的程序**策略**。  
  
4. 指向**外**然后单击**策略**。  
  
5. 选择的每个策略和版本，以添加，然后单击复选框**确定**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Rules** [**覆盖**] **/Name:**<em>值</em>**/Version:**<em>值</em>[**/Server:**<em>值</em>] [**/Database:**<em>值</em>]  
  
   > [!NOTE]
   >  参数值是区分大小写的。 参数名称不区分大小写。 此外，当使用此命令向应用程序添加策略时，还将自动添加该策略使用的所有词汇。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules / 覆盖 /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 应用程序名称**|向其添加策略的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。 包含空格的名称必须括在双引号 （"）。|  
   |**/ 类型**|**System.biztalk: rules**|  
   |**/ 覆盖**|更新现有策略的选项。 如果未指定，且应用程序中已经存在与要添加的策略名称相同的策略，则 AddResource 操作将失败。|  
   |**/ 名称**|策略的名称。|  
   |**/ 版本**|策略的版本号。|  
   |**/ 服务器**|承载 BizTalk 管理数据库的 SQL Server 实例的名称。 如果指定了“Database”参数，则此参数是必需的。 如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果指定了“Server”参数，则此参数是必需的。 如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理策略](../core/managing-policies.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [AddResource 命令：策略](../core/addresource-command-policy.md)