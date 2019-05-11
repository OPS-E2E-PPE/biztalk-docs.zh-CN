---
title: 按序送达使用 MQSeries 适配器的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MQSeries adapters, ordered delivery
ms.assetid: 517ff2a4-7315-43b5-8d4b-7494adf141e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8442d5f23f7259d9f13f7f60034d0ca871537e50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262627"
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a>按序送达消息与 MQSeries 适配器
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了**按序送达**选项适用于静态发送端口。 设置**按序送达**上的发送端口选项**True**可确保 BizTalk Server 向发送端口在发布到 BizTalk MessageBox 数据库的相同顺序传送消息。 若要提供端到端按序的送达必须满足以下条件:  
  
-   必须与适配器提交给 BizTalk Server 时保留消息的顺序接收消息。 例如，接收消息时使用 MQSeries 接收适配器，接收位置应配置选项**订单并停止**或**订单并挂起**。  
  
-   您必须订阅这些消息与发送端口都**按序送达**选项设为**True**。  
  
-   如果业务流程来的处理消息，只能运行一个业务流程实例应使用，该业务流程应配置为使用顺序保护，并**按序送达**属性业务流程的接收端口应设置为 **，则返回 True**。  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a>使用用于按序送达消息的 MQSeries 适配器  
 MQSeries 接收适配器提交给 BizTalk Server 中时保留消息的顺序提供支持。 端到端地按序送达消息通过 BizTalk Server 可以使用 MQSeries 适配器中如果通过使用配置的发送端口处理消息接收消息**按序送达**选项设置为 **，则返回 true**。  
  
## <a name="see-also"></a>请参阅  
 [按序送达消息](../core/ordered-delivery-of-messages.md)   
 [如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)