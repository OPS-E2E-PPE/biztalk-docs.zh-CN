---
title: "如何配置跟踪接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring [HAT tracking], receive ports
- tracking, receive ports
- receive ports, tracking
- configuring, tracking
- receive ports, configuring
- tracking, configuring
- HAT, receive ports
- configuring, receive ports
- managing [receive ports], tracking
ms.assetid: dd569e84-cb1c-4191-912a-0c2eb2781a85
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e18748a5d9ff8088d09dfe28bf23c7b729b6afc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a>如何配置跟踪接收端口
本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为接收端口配置跟踪，如查看消息正文和升级属性的选项。 这可帮助你监视的运行状况你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现，并确定任何瓶颈。 所配置的跟踪设置将应用于接收端口的所有实例。  
  
 有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[清单： 消息和实例数据跟踪](../core/checklist-message-and-instance-data-tracking.md)  
  
 所配置的跟踪设置将应用于接收端口的所有实例。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。 有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-a-receive-port"></a>为接收端口配置跟踪  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置跟踪的接收端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  单击**接收端口**，右键单击接收端口，然后单击**跟踪**。  
  
    > [!NOTE]
    >  启用之前接收端口上跟踪消息正文，请确保你想要在所有; 跟踪接收端口这可能是开销。 例如，接收管道 RcvPipe 在不同接收端口中的多个接收位置上使用。 如果启用跟踪 RcvPipe 上的选项的消息正文时，它会导致对上所有接收位置，而你可能希望执行跟踪的消息正文。 因此，设置该消息正文上跟踪接收端口根据你的要求。  
  
4.  下表中所述配置所需的跟踪选项，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**跟踪消息正文-端口处理前的请求消息**|选中此复选框可在接收消息之前保存并跟踪消息内容。|  
    |**跟踪消息正文-端口处理后的请求消息**|选中此复选框可在接收消息之后保存并跟踪消息内容。|  
    |||  
    |||  
    |**跟踪消息属性-端口处理前的请求消息**|选中此复选框可跟踪入站消息的升级属性。|  
    |**跟踪消息属性-端口处理后的请求消息**|如果需要，选中此复选框可跟踪出站消息已升级的属性。|  
    |||  
    |||  
  
## <a name="see-also"></a>另请参阅  
 [管理接收端口](../core/managing-receive-ports.md)