---
title: 如何部署或取消部署策略 |Microsoft 文档
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
ms.openlocfilehash: 9d6e7f9f70e6f1f0f09ae1d006172fdc00dc1bc0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970099"
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a>如何部署或取消部署策略
本主题介绍如何使用 BizTalk Server 管理控制台来部署或手动取消部署策略。 此外，自动启动应用程序部署包含，任何策略，并自动停止应用程序取消部署其策略。 部署策略可将其放到中使用它的应用程序的效果。 取消部署策略使它处于非活动状态，以便它不再函数中使用 BizTalk 组中任何应用程序。  
  
 当部署或取消部署策略时，请记住以下重要事项：  
  
-   你可以部署策略之前，它必须存在于 BizTalk 组的规则引擎数据库中。 如果导入的应用程序包含策略、 策略会自动导入到规则引擎数据库中，你可以显式使用或导入策略到规则引擎数据库的管理控制台或 BTSTask，中所述[如何导入策略](../core/how-to-import-a-policy.md)。 或者，你可以将策略添加到规则引擎数据库通过使用规则引擎部署向导中中, 所述[如何部署和取消部署策略和词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
-   你可以部署策略之前，它必须发布中, 所述[如何发布策略](../core/how-to-publish-a-policy.md)。  
  
-   无法修改已部署的策略。 如果你想要修改已部署的策略，你必须首先取消部署它。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-deploy-or-undeploy-a-policy"></a>部署或取消部署策略  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含你想要部署或取消部署，然后展开该策略的 BizTalk 组**\<所有项目\>**.  
  
3.  单击**策略**，右键单击的策略，然后单击**部署**或**取消部署后再次**。  
  
## <a name="see-also"></a>另请参阅  
 [管理策略](../core/managing-policies.md)   
 [如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)