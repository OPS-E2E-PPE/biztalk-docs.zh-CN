---
title: 如何登记业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], enlisting
- orchestrations, enlisting
- enlisting, orchestrations
ms.assetid: b21a398b-8c9a-42ae-aac0-de35dbfd8176
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203f8a61c439230b692577c8674b12e35944c24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966286"
---
# <a name="how-to-enlist-an-orchestration"></a>如何登记业务流程
本主题介绍如何使用 BizTalk Server 管理控制台来登记到主机的业务流程。 必须登记业务流程，然后才能开始。  
  
 当登记业务流程，请记住以下几点：  
  
-   **必须先才能将其登记绑定业务流程。** 配置业务流程绑定的说明，请参阅[如何配置业务流程的绑定](../core/how-to-configure-bindings-for-an-orchestration.md)。  
  
-   **自动创建订阅。** 业务流程登记进程 MessageBox 数据库中创建必需的订阅。  
  
-   **必须安装该应用程序。** 必须安装包含所有业务流程将在其中运行的计算机上的业务流程的应用程序。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
-   **调用业务流程必须绑定到调用的业务流程所在的主机。** 任何其他业务流程调用的业务流程必须绑定到调用业务流程所在的主机。  
  
-   **您还应登记从属业务流程。** 如果登记业务流程，但未登记任何从属业务流程，从属业务流程将不具有任何订阅。 没有订阅的相关业务流程可能会删除或挂起消息，因为没有要匹配的消息的订阅。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来登记业务流程以测试其功能。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-enlist-an-orchestration"></a>若要登记业务流程  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含要登记的业务流程的应用程序。  
  
3. 单击**业务流程**，右键单击业务流程以登记，然后单击**登记**。  
  
   > [!NOTE]
   >  要在一次登记多个业务流程，按住 shift 键并选择要登记的每个业务流程，右键单击业务流程，然后单击**登记**。  
  
    登记业务流程并创建了相应的订阅。 业务流程处于停止状态。 若要开始处理传入消息，您必须显式启动业务流程通过右键单击它并单击**启动**。 有关详细信息，请参阅[如何启动业务流程](../core/how-to-start-an-orchestration.md)。  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)