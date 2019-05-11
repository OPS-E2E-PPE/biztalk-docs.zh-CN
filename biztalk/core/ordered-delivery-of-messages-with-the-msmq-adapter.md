---
title: 按序送达使用 MSMQ 适配器的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MSMQ adapters, ordered delivery
ms.assetid: e8dafc76-e894-4120-9cea-d014d635850e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54395febdadb62584d0a8d6422b9fd05ab3821d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322274"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a>按序送达消息使用 MSMQ 适配器
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了**按序送达**选项适用于静态发送端口。 设置**按序送达**上的发送端口选项**True**可确保 BizTalk Server 向发送端口在发布到 MessageBox 数据库的相同顺序传送消息。 若要提供端到端按序的送达必须满足以下条件:  
  
-   必须与适配器提交给 BizTalk Server 时保留消息的顺序接收消息。  
  
-   您必须订阅这些消息与发送端口都**按序送达**选项设为**True**。  
  
-   如果业务流程来的处理消息，只能运行一个业务流程实例应使用，该业务流程应配置为使用顺序保护，并**按序送达**属性业务流程的接收端口应设置为 **，则返回 True**。  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a>使用 MSMQ 适配器按序送达消息  
 MSMQ 接收适配器提交给 BizTalk Server 中时保留消息的顺序提供支持。 端到端地按序送达消息通过 BizTalk Server 可以使用 MSMQ 适配器中如果通过使用配置的发送端口处理消息接收消息**按序送达**选项设置为**True**。  
  
## <a name="see-also"></a>请参阅  
 [按序送达消息](../core/ordered-delivery-of-messages.md)   
 [如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)