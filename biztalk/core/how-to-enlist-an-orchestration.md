---
title: "如何登记业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], enlisting
- orchestrations, enlisting
- enlisting, orchestrations
ms.assetid: b21a398b-8c9a-42ae-aac0-de35dbfd8176
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f58cb697e270052f8f42229997b1125e808816b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enlist-an-orchestration"></a>如何登记业务流程
本主题介绍如何使用 BizTalk Server 管理控制台来登记到主机业务流程。 你可以使用它之前，必须登记业务流程。  
  
 当登记业务流程，请记住以下几点：  
  
-   **必须先绑定业务流程，你可以对其进行登记。** 有关配置业务流程的绑定的说明，请参阅[如何将绑定配置为业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。  
  
-   **自动创建订阅。** 业务流程登记过程 MessageBox 数据库中创建必需的订阅。  
  
-   **你必须安装应用程序。** 你必须安装包含所有将运行业务流程的位置的计算机上的业务流程的应用程序。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
-   **调用的业务流程必须绑定到调用的业务流程的同一主机。** 所有业务流程，由另一个业务流程调用必须绑定到调用的业务流程的同一主机。  
  
-   **你还应登记依赖业务流程。** 如果你的业务流程中登记，但不是登记任何从属的业务流程，依赖业务流程将没有任何订阅。 没有订阅依赖 orchestration 可能会删除或挂起消息，因为没有要匹配的消息没有订阅。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来登记业务流程以测试其功能。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-enlist-an-orchestration"></a>若要登记业务流程  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要登记的业务流程的应用程序。  
  
3.  单击**业务流程**，右键单击业务流程，以登记，然后单击**Enlist**。  
  
    > [!NOTE]
    >  要在一次登记多个业务流程，请按住 shift 键，并选择要登记每个业务流程业务流程，右键单击，然后单击**Enlist**。  
  
     业务流程将登记，并创建相应的订阅。 业务流程处于停止状态。 若要开始处理传入消息，你必须显式启动业务流程通过右键单击它并单击**启动**。 有关详细信息，请参阅[如何启动 Orchestration](../core/how-to-start-an-orchestration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)