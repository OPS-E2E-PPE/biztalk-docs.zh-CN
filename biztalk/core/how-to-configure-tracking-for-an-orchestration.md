---
title: 如何配置适用于业务流程的跟踪 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, tracking
- orchestrations, HAT
- managing [orchestrations], tracking
- configuring [HAT tracking], orchestrations
- tracking, orchestrations
- HAT, orchestrations
ms.assetid: 8f5ed525-11f8-4bef-95c4-cfe9c971b663
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ebae70ec70fb58a4a935be6b2c46f39cfafba59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249133"
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a>如何配置适用于业务流程的跟踪
本主题将介绍如何使用 BizTalk Server 管理控制台为业务流程配置跟踪。  
  
 有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。 有关详细信息的跟踪功能的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-an-orchestration"></a>为业务流程配置跟踪  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要配置跟踪业务的流程的应用程序。  
  
3.  单击**业务流程**，右键单击你想要配置跟踪，然后单击业务的流程**属性**。  
  
4.  单击**跟踪**选项卡上，选择跟踪所需的选项下, 表中所述，然后单击**确定**。  
  
    |选项|Description|  
    |------------|-----------------|  
    |**跟踪事件的业务流程开始和结束**|选中此复选框可在处理整个业务流程之前和之后跟踪业务流程实例。 使用业务流程跟踪可以在跟踪查询结果视图中查看实例。|  
    |**跟踪事件的发送和接收消息**|选中此复选框可跟踪消息发送和接收事件。 此复选框可仅当你选择**业务流程开始和结束**复选框。|  
    |**跟踪事件数-形状开始和结束**|当需要在业务流程调试器中调试业务流程实例时，请选中此复选框。 选中此复选框之后，将会填充业务流程调试器中的事件列表。 此复选框可仅当你选择**业务流程开始和结束**复选框。|  
    |**跟踪消息正文的业务流程处理前**|选中此复选框可以保存和跟踪业务流程实例处理之前的实际消息内容。 此复选框可仅当你选择**消息发送和接收**复选框。|  
    |**在业务流程处理跟踪消息正文-**|选中此复选框可以保存和跟踪业务流程实例处理之后的实际消息内容。 此复选框可仅当你选择**消息发送和接收**复选框。|  
    |**跟踪消息属性的传入消息**|选中此复选框可跟踪入站消息的升级属性。|  
    |**跟踪消息属性的传出消息**|选中此复选框可跟踪出站消息的升级属性。|  
  
## <a name="see-also"></a>另请参阅  
 [管理业务流程](../core/managing-orchestrations.md)