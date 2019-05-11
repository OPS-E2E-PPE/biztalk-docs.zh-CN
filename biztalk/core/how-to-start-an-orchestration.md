---
title: 如何启动业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], starting
- starting, orchestrations
- orchestrations, starting
ms.assetid: 83411279-ee6f-4d68-aa3b-b5cd5e106088
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49713fbaafab361faffdda7cc8b631b4fc94aed6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383844"
---
# <a name="how-to-start-an-orchestration"></a>如何启动业务流程
本主题介绍如何使用 BizTalk Server 管理控制台来启动业务流程。 启动业务流程时，将开始处理传入的消息。  
  
 当启动和业务流程，请记住以下重要事项：  
  
-   可以启动业务流程之前，它必须登记，以及所有发送端口和发送端口组与之关联。 有关说明，请参阅[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)并[如何登记发送端口或发送端口组](../core/how-to-enlist-a-send-port-or-send-port-group.md)。  
  
-   启动业务流程不会自动启动任何相关的发送端口。 您必须单独启动这些发送，如中所述[如何启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)。  
  
-   如果登记发送端口和/或发送端口组与此业务流程相关联，但没有启动它们，BizTalk Server 将放入任何消息发送到此发送端口或发送端口组的主机的挂起队列中已登记的发送端口或发送端口组p。  
  
> [!NOTE]
>  应用程序开发人员可以启动业务流程以测试其功能在开发过程中，通过使用本主题中的过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组的成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-start-an-orchestration"></a>若要启动业务流程  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含想要启动的业务流程的应用程序。  
  
3. 单击**业务流程**，右键单击该业务流程，然后单击**启动**。  
  
   > [!IMPORTANT]
   >  如果不首先未登记相关的发送端口并启动业务流程之前，发送端口组，您将看到一条错误消息。  
  
   > [!NOTE]
   >  若要同时启动多个业务流程，按住 shift 键并选择每个业务流程中，右键单击业务流程，然后单击**启动**。  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何停止业务流程](../core/how-to-stop-an-orchestration.md)   
 [如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)