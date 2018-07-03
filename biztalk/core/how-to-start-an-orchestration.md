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
ms.openlocfilehash: d2593c68d642debcfcd8b49fa0ee67f806adc7c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993054"
---
# <a name="how-to-start-an-orchestration"></a>如何启动业务流程
本主题将介绍如何使用 BizTalk Server 管理控制台启动业务流程。 启动业务流程后，业务流程将开始处理传入的消息。  
  
 启动业务流程时，请切记以下几点：  
  
-   必须先登记业务流程以及与该业务流程相关联的所有发送端口和发送端口组，然后才可以启动业务流程。 有关说明，请参阅[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)并[如何登记发送端口或发送端口组](../core/how-to-enlist-a-send-port-or-send-port-group.md)。  
  
-   启动业务流程并不会自动启动任何相关的发送端口。 您必须单独启动这些发送，如中所述[如何启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)。  
  
-   如果登记了与此业务流程相关联的发送端口和/或发送端口组，但没有启动它们，则 BizTalk Server 会将发送到此发送端口或发送端口组的任何消息放入已登记发送端口或发送端口组的主机的挂起队列中。  
  
> [!NOTE]
>  应用程序开发人员可以启动业务流程以测试其功能在开发过程中，通过使用本主题中的过程。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，则必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-start-an-orchestration"></a>若要启动业务流程  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含想要启动的业务流程的应用程序。  
  
3. 单击**业务流程**，右键单击该业务流程，然后单击**启动**。  
  
   > [!IMPORTANT]
   >  如果在启动业务流程前没有先登记相关的发送端口和发送端口组，则将看到错误消息。  
  
   > [!NOTE]
   >  若要同时启动多个业务流程，按住 shift 键并选择每个业务流程中，右键单击业务流程，然后单击**启动**。  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何停止业务流程](../core/how-to-stop-an-orchestration.md)   
 [如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)