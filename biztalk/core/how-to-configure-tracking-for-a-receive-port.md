---
title: 如何配置跟踪的接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6f45158939210c3b084aa29234bee1b4a032b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385897"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a>如何配置跟踪的接收端口
本主题介绍如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台配置跟踪的接收端口，如选项来查看消息正文和升级属性... 这可帮助你监视的运行状况在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现并识别任何瓶颈。 你配置的跟踪设置适用于所有的接收端口的实例。  
  
 有关消息事件和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[核对清单：消息和实例数据跟踪](../core/checklist-message-and-instance-data-tracking.md)  
  
 你配置的跟踪设置适用于所有的接收端口的实例。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-a-receive-port"></a>若要配置跟踪的接收端口  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置跟踪的接收端口。  
  
3. 单击**接收端口**，右键单击该接收端口，然后单击**跟踪**。  
  
   > [!NOTE]
   >  启用消息正文跟踪，接收端口之前, 请确保你想要在所有; 跟踪接收端口这可能是一项开销。 例如，接收管道 RcvPipe 在不同的接收端口中的多个接收位置使用。 如果启用消息正文跟踪在 RcvPipe 上的选项，它会导致对所有接收位置，而您可能不想要执行跟踪消息正文。 因此，设置消息正文跟踪在接收端口根据你的要求。  
  
4. 下表中所述配置所需的跟踪选项，然后单击**确定**。  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**跟踪消息正文-端口处理前请求消息**|选中此复选框可保存并跟踪消息内容之前接收消息。|  
   |**跟踪消息正文-端口处理后请求消息**|选中此复选框可保存并跟踪消息内容后接收消息。|  
   |||  
   |||  
   |**跟踪消息属性-端口处理前请求消息**|选择此复选框可跟踪入站消息的升级的属性。|  
   |**跟踪消息属性-端口处理后请求消息**|如果你想要跟踪出站消息的升级的属性，请选中此复选框。|  
   |||  
   |||  
  
## <a name="see-also"></a>请参阅  
 [管理接收端口](../core/managing-receive-ports.md)