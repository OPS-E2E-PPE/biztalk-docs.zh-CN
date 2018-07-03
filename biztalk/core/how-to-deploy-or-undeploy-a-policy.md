---
title: 如何部署或取消部署策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], undeploying
- deploying, policies
- policies, deploying
- managing [policies], deploying
- policies, undeploying
- undeploying, policies
ms.assetid: 9d26d4fe-9673-4baa-9927-02efda56b7a4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad8aa910982ddb63a9f8b9602dbb1bfa843895fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022891"
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a>如何部署或取消部署策略
本主题介绍如何使用 BizTalk Server 管理控制台来部署或手动取消部署策略。 此外，自动启动应用程序部署它所包含的任何策略，并停止应用程序会自动取消部署其策略。 部署策略会将其放在使用它的应用程序中生效。 取消部署策略使它处于非活动状态，以便它不再使用 BizTalk 组中的任何应用程序中的函数。  
  
 当部署或取消部署策略时，请记住以下重要事项：  
  
-   可以部署策略之前，它必须存在于 BizTalk 组的规则引擎数据库中。 如果导入包含策略的应用程序，该策略将自动导入到规则引擎数据库中，也可以显式导入策略到规则引擎数据库中通过使用管理控制台或 BTSTask，中所述[如何导入策略](../core/how-to-import-a-policy.md)。 或者，您可以将策略添加到规则引擎数据库中使用规则引擎部署向导，如中所述[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
-   你可以部署策略之前，必须发布它，如中所述[如何发布策略](../core/how-to-publish-a-policy.md)。  
  
-   不能修改已部署的策略。 如果你想要修改已部署的策略，您必须先取消部署它。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-deploy-or-undeploy-a-policy"></a>部署或取消部署策略  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开包含你想要部署或取消部署，然后展开该策略的 BizTalk 组**\<的所有项目\>**.  
  
3. 单击**策略**，右键单击该策略，然后单击**部署**或**Undeploy**。  
  
## <a name="see-also"></a>请参阅  
 [管理策略](../core/managing-policies.md)   
 [如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)