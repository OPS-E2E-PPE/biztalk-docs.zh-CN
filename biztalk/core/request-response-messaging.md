---
title: 请求-响应消息传送 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- request/response messaging, about request/response messaging
- SOAP adapters, message processing
- SOAP adapters, request/response messaging
- request/response messaging
- patterns, messages
- messages, request/response messaging
- request/response messaging, processing
- request/response messaging, SOAP adapters
- messages, patterns
ms.assetid: 1a2f79b5-1f44-4191-8ce1-b3c9043be4f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8d58fbcac6803adb36495f1aa9982909580e1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985070"
---
# <a name="request-response-messaging"></a>请求-响应消息传送
在请求/响应消息传送模式中，一方发送一个请求消息，接收方将返回一个响应消息。 请求/响应处理的两个典型示例是浏览器使用 HTTP 适配器与 Web 服务器进行交互，以及使用简单对象访问协议 (SOAP) 适配器进行 Web Services 处理。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，典型的发布/订阅方式处理请求和响应消息。 若要将 BizTalk 应用程序调整到最佳性能，则了解这一点十分重要，因为具有高吞吐量要求的系统配置可能与要求各个消息都具有低延迟时间的系统配置不同。  
  
 ![请求&#47;响应消息传送](../core/media/arch-request-response-1.gif "arch_request 响应 1")  
  
 当采用请求/响应方式的接收适配器收到消息后，BizTalk Server 首先会将该请求消息发布到 MessageBox 数据库。 随后，相应的订户将接收此消息，该订户可能是绑定到某个接收端口的业务流程。 此订阅者表述的响应消息，并将其发布到 MessageBox，以及将导致其发回给发出请求的接收端口的属性。 最后，该请求的发布服务器（即提交请求的接收适配器）将提取此响应消息并将其返回到调用方应用程序。 下图提供了这些步骤的详细的图形表示形式：  
  
 ![请求&#47;SOAP 适配器接收到的响应消息](../core/media/arch-request-response-2.gif "arch_request 响应 2")  
  
 **SOAP 适配器接收到的请求/响应消息流**  
  
1. SOAP 适配器将消息提交给终结点管理器。  
  
2. 终结点管理器将消息发布到 MessageBox 中。  
  
3. 绑定到接收端口并因此具有消息订阅的业务流程将接收该消息并对其进行处理。  
  
4. 该业务流程将发送一个响应消息，该消息将发布到 MessageBox。  
  
5. 终结点管理器接收该响应消息。  
  
6. 终结点管理器返回到 SOAP 适配器的响应  
  
   如果不了解内部实现，则可以忽略此类行为对性能的影响。 BizTalk Server 最初优化为适用于高吞吐量的情况，但也可以将其配置为用于具有较低吞吐量和需要较低延迟时间的环境，尤其是在请求/响应情况下。 在这种情况下进行优化时，您需要考虑若干因素。 首先，订户是通过轮询机制来查找有关发布的消息的信息。 如果轮询间隔设置过高，则可能会导致采用请求/响应方式的交互的延迟时间高于所需延迟时间。  
  
   请注意，在此方案中，有两个订阅进行填充： 初始消息的订阅以及一个用于响应消息，这会增加此轮询间隔的影响。 其次，接收适配器配置为向 MessageBox 中分批插入不同批大小的消息。 大多数适配器都允许您通过典型的适配器配置界面或通过 BizTalk Server 或注册表中的参数来配置批大小。 如果批大小设置过高，则可能会增加各个消息的延迟时间。 有关详细信息有关的性能特征[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[规划可持续性能](../core/planning-for-sustained-performance.md)。  
  
## <a name="see-also"></a>请参阅  
 [运行时体系结构](../core/runtime-architecture.md)