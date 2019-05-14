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
ms.openlocfilehash: 88d5dd42d26fd3c5ca899059beb87f72beff8dd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340167"
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a>如何为业务流程配置跟踪
本主题介绍如何使用 BizTalk Server 管理控制台为业务流程配置跟踪。  
  
 有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。 有关跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-an-orchestration"></a>若要为业务流程配置跟踪  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含您要为其配置跟踪的业务流程的应用程序。  
  
3. 单击**业务流程**，右键单击您要为其配置跟踪，然后单击该业务的流程**属性**。  
  
4. 单击**跟踪**选项卡上，选择所需的跟踪选项下, 表中所述，然后单击**确定**。  
  
   |Option|Description|  
   |------------|-----------------|  
   |**跟踪事件-业务流程开始和结束**|选中此复选框以跟踪业务流程实例之前和之后的整个业务流程处理。 业务流程跟踪，您可以查看跟踪中的实例查询结果视图。|  
   |**跟踪事件-消息发送和接收**|选择此复选框可跟踪消息发送和接收事件。 此复选框才可用 匡 **业务流程开始和结束**复选框。|  
   |**跟踪事件-形状开始和结束**|当您需要调试业务流程调试器中的业务流程实例时，请选中此复选框。 选中此复选框后，业务流程调试器中的事件列表填充。 此复选框才可用 匡 **业务流程开始和结束**复选框。|  
   |**跟踪消息正文-业务流程处理前**|选中此复选框可以保存和跟踪业务流程实例在处理之前的实际消息内容。 此复选框才可用 匡 **消息发送和接收**复选框。|  
   |**跟踪消息正文-业务流程处理之后**|选中此复选框可以保存和跟踪业务流程实例在处理后的实际消息内容。 此复选框才可用 匡 **消息发送和接收**复选框。|  
   |**跟踪消息属性-传入的消息**|选择此复选框可跟踪入站消息的升级的属性。|  
   |**跟踪消息属性-传出消息**|选择此复选框可跟踪出站消息的升级的属性。|  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)