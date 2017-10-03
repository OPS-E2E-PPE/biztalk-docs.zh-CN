---
title: "如何配置发送端口的跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- configuring, tracking
- tracking, send ports
- configuring [HAT tracking], send ports
- send ports, tracking
- managing [send ports], configuring
- tracking, configuring
- send ports, configuring
- managing [send ports], tracking
- HAT, send ports
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60ba83b7d3451599a0422ec370fed41eeba94407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-send-port"></a>如何为发送端口配置跟踪
本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置发送端口的跟踪，例如用于查看消息正文和升级属性的选项。 这有助于您监视 BizTalk 实施的运行状况并确定存在的任何瓶颈问题。 所配置的跟踪设置将应用于发送端口的所有实例。  
  
 有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。 有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-a-send-port"></a>为发送端口配置跟踪  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置跟踪的发送端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  单击**发送端口**，右键单击发送端口，请单击**属性**，然后单击**跟踪**。  
  
    > [!NOTE]
    >  一个发送端口只能与一个发送管道相关联。 如果在发送管道上禁用消息正文跟踪，则在发送端口上也无法跟踪任何东西。 在这种情况中，您可以禁用该发送端口上的“跟踪”选项。  
  
4.  下表中所述配置所需的跟踪选项，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**跟踪消息正文-端口处理前的请求消息**|选中此复选框，以便你能够保存和跟踪消息内容之前收到的消息。 **注意：**必须启用邮件正文管道跟踪成功跟踪端口处理前的响应消息。|  
    |**跟踪消息正文-端口处理后的请求消息**|选中此复选框，以便你能够保存和跟踪消息内容后收到的消息。|  
    |||  
    |||  
    |**跟踪消息属性-端口处理前的请求消息**|选中此复选框可跟踪入站消息的升级属性。|  
    |**跟踪消息属性-端口处理后的请求消息**|如果需要，选中此复选框可跟踪出站消息已升级的属性。|  
    |||  
    |||  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)