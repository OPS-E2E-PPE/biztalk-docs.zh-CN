---
title: 如何发布策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- managing [policies], publishing
- publishing, policies
ms.assetid: 730c57a7-526f-40ca-8610-88216558e375
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8a3591c6f904db07f51610e0bcff7afae7b8e31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335745"
---
# <a name="how-to-publish-a-policy"></a>如何发布策略
本主题介绍如何使用 BizTalk Server 管理控制台来发布 BizTalk 组中的策略。 发布某一策略，可将它添加到 BizTalk 应用程序，如中所述[如何向应用程序添加策略](../core/how-to-add-a-policy-to-an-application.md)。  
  
 可以发布策略之前，它必须存在于 BizTalk 组的规则引擎数据库中。 有三种方法可以将策略导入规则引擎数据库：  
  
-   您可以导入包含策略的应用程序。 当执行此操作时，该策略将自动导入到规则引擎数据库。  
  
-   您可以显式将策略导入规则引擎数据库通过使用管理控制台或 BTSTask，如中所述[如何导入策略](../core/how-to-import-a-policy.md)。  
  
-   您可以将策略添加到规则引擎数据库中使用规则引擎部署向导，如中所述[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
> [!NOTE]
>  尽管已发布的策略可以覆盖由另一个策略导入，您应指定此选项，可以永远不会覆盖已发布的词汇。 若要更新已发布的词汇，必须从规则引擎数据库中删除它，然后导入新版本。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-publish-a-policy"></a>若要发布策略  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开包含该策略的 BizTalk 组将发布，则展开**应用程序**，然后展开**\<的所有项目\>**。  
  
3. 单击**策略**，右键单击该策略，然后单击**发布**。  
  
   > [!NOTE]
   >  若要发布策略，，引用该策略的任何程序集必须安装在全局程序集缓存 (GAC) 的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机在打开之前**BizTalk Server 管理**。 当**BizTalk Server 管理**是打开，维护安装到 GAC 的程序集的缓存。 直到会更新此缓存**BizTalk Server 管理**关闭并重新打开。 如果成功发布策略时，发布失败，因为引用的程序集未安装在 gac 中必须关闭**BizTalk Server 管理**，将被引用程序集安装到 GAC 中，打开**BizTalk Server 管理**，并发布策略。  
  
## <a name="see-also"></a>请参阅  
 [管理策略](../core/managing-policies.md)