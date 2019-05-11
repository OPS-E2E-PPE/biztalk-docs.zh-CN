---
title: 启用发送端口上的跟踪 |Microsoft Docs
description: 打开消息正文跟踪，并在 BizTalk Server 中的发送端口上跟踪消息属性
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578d48c5eefe4866de974b11f1171cf271a24156
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385990"
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a>在 BizTalk Server 中配置发送端口跟踪
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台配置跟踪的发送端口，如选项来查看消息正文和升级属性。 这可帮助你监视 BizTalk 实施的运行状况并确定任何瓶颈。 你配置的跟踪设置适用于所有发送端口的实例。  
  
 有关消息事件和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>先决条件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="enable-tracking-on-a-send-port"></a>启用发送端口上的跟踪  
  
1.  在中**BizTalk Server 管理**，展开 BizTalk 组，然后展开 BizTalk 应用程序可以发送端口。  
  
2.  选择**发送端口**，右键单击发送端口，选择**属性**，然后选择**跟踪**。  
  
    > [!NOTE]
    >  一个发送端口可以只有一个发送管道与相关联。 如果发送管道上禁用消息正文跟踪，则不会跟踪在发送端口上。 在此类方案中，您可以禁用"跟踪"选项上的发送端口。  
  
3.  使用以下详细信息来启用的跟踪选项，然后选择**确定**以保存所做的更改。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**跟踪消息正文-端口处理前请求消息**|保存并接收消息前跟踪消息内容。 <br/><br/> **请注意**:请务必启用消息正文管道跟踪成功跟踪端口处理前的响应消息。|  
    |**跟踪消息正文-端口处理后请求消息**|保存并跟踪消息内容后接收消息。|  
    |**跟踪消息正文-端口处理前响应消息**|保存并发送消息前跟踪消息内容。 仅适用于要求响应发送端口。|    
    |**跟踪消息正文-端口处理后响应消息**|保存并跟踪消息内容后将消息发送。 仅适用于要求响应发送端口。|  
    |**跟踪消息正文-端口处理后响应消息**|跟踪入站消息的升级的属性。|  
    |**跟踪消息属性-端口处理后请求消息**|跟踪出站消息的升级的属性。|  
    |**跟踪消息属性-端口处理前响应消息**|保存并发送消息前跟踪消息属性。 仅适用于要求响应发送端口。|   
    |**跟踪消息属性-端口处理后响应消息**|保存并发送消息之后跟踪属性。 仅适用于要求响应发送端口。|   
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)
