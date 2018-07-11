---
title: 如何为业务流程配置跟踪 |Microsoft Docs
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
ms.openlocfilehash: 3c64d7521bf6d65458f66bb0ef06d08421edf1b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013190"
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a>如何为业务流程配置跟踪
本主题将介绍如何使用 BizTalk Server 管理控制台为业务流程配置跟踪。  
  
 有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。 有关跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-an-orchestration"></a>为业务流程配置跟踪  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含您要为其配置跟踪的业务流程的应用程序。  
  
3. 单击**业务流程**，右键单击您要为其配置跟踪，然后单击该业务的流程**属性**。  
  
4. 单击**跟踪**选项卡上，选择所需的跟踪选项下, 表中所述，然后单击**确定**。  
  
   |选项|Description|  
   |------------|-----------------|  
   |**跟踪事件-业务流程开始和结束**|选中此复选框可在处理整个业务流程之前和之后跟踪业务流程实例。 使用业务流程跟踪可以在跟踪查询结果视图中查看实例。|  
   |**跟踪事件-消息发送和接收**|选中此复选框可跟踪消息发送和接收事件。 此复选框才可用**业务流程开始和结束**复选框。|  
   |**跟踪事件-形状开始和结束**|当需要在业务流程调试器中调试业务流程实例时，请选中此复选框。 选中此复选框之后，将会填充业务流程调试器中的事件列表。 此复选框才可用**业务流程开始和结束**复选框。|  
   |**跟踪消息正文-业务流程处理前**|选中此复选框可以保存和跟踪业务流程实例处理之前的实际消息内容。 此复选框才可用**消息发送和接收**复选框。|  
   |**跟踪消息正文-业务流程处理之后**|选中此复选框可以保存和跟踪业务流程实例处理之后的实际消息内容。 此复选框才可用**消息发送和接收**复选框。|  
   |**跟踪消息属性-传入的消息**|选中此复选框可跟踪入站消息的升级属性。|  
   |**跟踪消息属性-传出消息**|选中此复选框可跟踪出站消息的升级属性。|  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)