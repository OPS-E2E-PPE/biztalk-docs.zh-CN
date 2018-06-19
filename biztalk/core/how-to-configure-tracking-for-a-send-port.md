---
title: 启用发送端口上的跟踪 |Microsoft 文档
description: 打开跟踪的消息正文，并在 BizTalk Server 发送端口上跟踪消息属性
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
ms.openlocfilehash: 223c417769086cc71f501b044410bf2d3e4cbc74
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2017
ms.locfileid: "26686628"
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a>在 BizTalk Server 中配置发送端口跟踪
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置跟踪发送端口，如选项，以查看消息正文和升级的属性。 这有助于您监视 BizTalk 实施的运行状况并确定存在的任何瓶颈问题。 所配置的跟踪设置将应用于发送端口的所有实例。  
  
 有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>必备条件  
使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。 有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="enable-tracking-on-a-send-port"></a>启用发送端口上的跟踪  
  
1.  在**BizTalk Server 管理**，展开 BizTalk 组，然后展开你的 BizTalk 应用程序具有发送端口。  
  
2.  选择**发送端口**，右键单击发送端口，选择**属性**，然后选择**跟踪**。  
  
    > [!NOTE]
    >  一个发送端口只能与一个发送管道相关联。 如果发送管道上禁用跟踪的消息正文，然后执行任何操作会跟踪上发送端口。 在这种情况中，您可以禁用该发送端口上的“跟踪”选项。  
  
3.  使用以下详细信息来启用跟踪所需的选项，然后选择**确定**以保存所做的更改。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**跟踪消息正文-端口处理前的请求消息**|将保存并在收到消息前跟踪消息内容。 <br/><br/> **请注意**： 请务必启用消息正文管道跟踪来成功跟踪端口处理前的响应消息。|  
    |**跟踪消息正文-端口处理后的请求消息**|保存并消息后，收到的消息跟踪消息内容。|  
    |**跟踪消息正文-端口处理前的响应消息**|将保存并发送消息前跟踪消息内容。 仅适用于请求作出响应发送端口。|    
    |**跟踪消息正文-端口处理后的响应消息**|保存并消息后，将消息发送跟踪消息内容。 仅适用于请求作出响应发送端口。|  
    |**跟踪消息正文-端口处理后的响应消息**|跟踪的入站消息提升的属性。|  
    |**跟踪消息属性-端口处理后的请求消息**|跟踪的出站消息提升的属性。|  
    |**跟踪消息属性 – 端口处理前的响应消息**|将保存并发送消息前跟踪消息属性。 仅适用于请求作出响应发送端口。|   
    |**跟踪消息属性 – 端口处理后的响应消息**|保存并消息后，将消息发送跟踪属性。 仅适用于请求作出响应发送端口。|   
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)
