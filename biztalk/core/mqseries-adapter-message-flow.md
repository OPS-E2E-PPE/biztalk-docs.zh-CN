---
title: MQSeries 适配器消息流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, message flow
ms.assetid: aa5c8523-afd6-4181-9c11-a150857a7790
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37208bc0d1b9d1abf28f223a678168cdf15d1d16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263861"
---
# <a name="mqseries-adapter-message-flow"></a>MQSeries 适配器消息流
消息源自[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机首先会传递到 MQSeries 服务器在 Windows 上运行。 在 Windows 上运行的 MQSeries 服务器可以位于与运行 BizTalk Server 在同一台计算机上。 消息通过 MQSeries Server for Windows 计算机添加到如 UNIX 的操作系统上的 MQSeries 服务器主机路由。 随后，应用程序从 MQSeries 队列中检索消息。  

 从应用程序的消息发起首先将进入 MQSeries 队列 MQSeries 服务器上。 MQSeries 服务器将消息转发到 MQSeries Server for Windows 计算机。 BizTalk Server 从 MQSeries Server for Windows 计算机接收消息，并将其转发到相应的应用程序。  

 MQSeries 适配器支持以下消息传送方案。  


|        **应用场景**        |                                                                                                                                                                                                                 **说明**                                                                                                                                                                                                                 |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          Receive           |                                                                                                                                           适配器从 MQSeries 服务器、 传递给接收一条消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。                                                                                                                                           |
| 发送 （静态单向端口） |                                                                                                                                                      适配器路由来自消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。                                                                                                                                                      |
|        动态发送        |                                                                                                                                                                                   使程序能够在运行时选择目标地址 (URI)。                                                                                                                                                                                    |
|      动态接收       |                                                                                                                             使应用程序能够在运行时选择源地址 (URI)，通过设置**MQSeries.DynamicReceive**上下文属性设置为**是**并指定动态接收地址。                                                                                                                             |
|        Correlation         | 来自适配器的消息是与可以处理多个类型的消息的业务流程的特定实例相关联。<br /><br /> MQSeries 服务器可以使用要求响应创建相关标识符或 BizTalk Server 可以创建相关标识符。<br /><br /> 有关关联集的详细信息，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 |

 有关使用端口和管道、 业务流程和基于内容的路由中的适配器的详细信息，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 在适配器中使用相关标识符的详细信息，请参阅[关联的消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。  

 有关可用于在适配器中进行筛选的标头属性的信息，请参阅[与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md)并[MQSeries 上下文属性](../core/mqseries-context-properties.md)。  

## <a name="see-also"></a>请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)