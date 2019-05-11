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
ms.openlocfilehash: 38652fdb7b1b5484c4c01510416489c4437b629e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398889"
---
# <a name="request-response-messaging"></a>请求-响应消息传送
在请求/响应消息传送模式中，一个参与方发送请求消息并接收方返回响应消息。 请求/响应处理的两个典型示例是浏览器具有与 Web 服务器使用 HTTP 适配器和使用简单对象访问协议 (SOAP) 适配器 Web 服务处理的交互。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，典型的发布/订阅方式处理请求和响应消息。 这是了解 BizTalk 应用程序进行性能优化时，因为需要高吞吐量的系统配置可能不同比低延迟要求各个消息的一个重要考虑因素。  
  
 ![请求&#47;响应消息传送](../core/media/arch-request-response-1.gif "arch_request 响应 1")  
  
 当收到一条消息请求/响应样式的接收适配器，BizTalk Server 首先将请求消息发布到 MessageBox 数据库。 接下来的相应订阅服务器上，可能是绑定到接收端口的业务流程收到此消息。 此订阅者表述的响应消息，并将其发布到 MessageBox，以及将导致其发回给发出请求的接收端口的属性。 最后，响应消息被拾取请求，接收适配器提交请求，并返回到调用应用程序的发布服务器。 下图提供了这些步骤的详细图形表示形式。  
  
 ![请求&#47;SOAP 适配器接收到的响应消息](../core/media/arch-request-response-2.gif "arch_request 响应 2")  
  
 **SOAP 适配器接收到的请求/响应消息流**  
  
1. SOAP 适配器将提交消息到终结点管理器。  
  
2. 终结点管理器将消息发布到 MessageBox。  
  
3. 业务流程，后者已绑定到接收端口并因此具有消息订阅，接收消息，并对其进行处理。  
  
4. 业务流程将发送一个响应消息，发布到 MessageBox。  
  
5. 终结点管理器接收响应消息。  
  
6. 终结点管理器返回到 SOAP 适配器的响应  
  
   如果不了解内部实现，则可以忽略此类行为对性能的影响。 BizTalk Server 最初优化为高吞吐量的情况，但它也可以配置为具有较低的吞吐量和低滞后时间，尤其是在请求/响应方案的需求。 您需要考虑在此方案中优化的多个组件。 首先，订户了解已发布的消息通过轮询机制。 如果轮询间隔设置得太高，这可能导致请求/响应方式具有较高的延迟高于所需的交互。  
  
   请注意，在此方案中，有两个订阅进行填充： 初始消息的订阅以及一个用于响应消息，这会增加此轮询间隔的影响。 第二个，接收适配器配置为将消息插入到 MessageBox 中不同大小的批处理。 大多数适配器都允许您配置 BizTalk Server 或注册表中的批大小通过典型的适配器配置界面或通过参数。 如果批大小设置过高，则可能会增加各个消息的延迟。 有关详细信息有关的性能特征[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[规划可持续性能](../core/planning-for-sustained-performance.md)。  
  
## <a name="see-also"></a>请参阅  
 [运行时体系结构](../core/runtime-architecture.md)