---
title: "与 MSMQ 适配器的消息的有序传送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MSMQ adapters, ordered delivery
ms.assetid: e8dafc76-e894-4120-9cea-d014d635850e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac842fcd1e9b386fa885844f3a797504ed7c4c3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a>与 MSMQ 适配器的消息的有序传送
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供**按序送达**选项适用于静态发送端口。 设置**按序送达**到发送端口上的选项**True**可确保 BizTalk 服务器将消息传送到发送端口与它们发布到 MessageBox 数据库相同的顺序。 为提供端对端的按序送达功能，必须满足以下条件：  
  
-   接收消息的适配器必须保持消息提交给 BizTalk Server 时的顺序。  
  
-   您必须订阅拥有的发送端口与这些消息**按序送达**选项设为**True**。  
  
-   如果业务流程用于的处理应使用的消息，仅业务流程的单个实例，应将业务流程配置为使用顺序保护和**按序送达**属性业务流程的接收端口应设置为**True**。  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a>为有序的消息传递使用 MSMQ 适配器  
 MSMQ 接收适配器可以保持消息提交给 BizTalk Server 时的顺序。 端到端顺序接收消息使用 MSMQ 适配器，如果通过使用配置发送端口处理消息时可以获得的传递消息通过 BizTalk Server**按序送达**选项设置为**True**。  
  
## <a name="see-also"></a>另请参阅  
 [有序的消息传送](../core/ordered-delivery-of-messages.md)   
 [如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)