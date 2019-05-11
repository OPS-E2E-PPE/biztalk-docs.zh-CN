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
# <a name="request-response-messaging"></a><span data-ttu-id="991bc-102">请求-响应消息传送</span><span class="sxs-lookup"><span data-stu-id="991bc-102">Request-Response Messaging</span></span>
<span data-ttu-id="991bc-103">在请求/响应消息传送模式中，一个参与方发送请求消息并接收方返回响应消息。</span><span class="sxs-lookup"><span data-stu-id="991bc-103">In a request/response messaging pattern, one party sends a request message and the receiving party returns a response message.</span></span> <span data-ttu-id="991bc-104">请求/响应处理的两个典型示例是浏览器具有与 Web 服务器使用 HTTP 适配器和使用简单对象访问协议 (SOAP) 适配器 Web 服务处理的交互。</span><span class="sxs-lookup"><span data-stu-id="991bc-104">Two typical examples of request/response processing are the interaction that a browser has with a Web server using the HTTP adapter, and Web service processing using the Simple Object Access Protocol (SOAP) adapter.</span></span> <span data-ttu-id="991bc-105">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，典型的发布/订阅方式处理请求和响应消息。</span><span class="sxs-lookup"><span data-stu-id="991bc-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], both the request and the response messages are handled in a typical publish/subscribe fashion.</span></span> <span data-ttu-id="991bc-106">这是了解 BizTalk 应用程序进行性能优化时，因为需要高吞吐量的系统配置可能不同比低延迟要求各个消息的一个重要考虑因素。</span><span class="sxs-lookup"><span data-stu-id="991bc-106">This is an important consideration to understand when you performance-tune a BizTalk application, because a system requiring high throughput might be configured differently than one requiring low latency for individual messages.</span></span>  
  
 <span data-ttu-id="991bc-107">![请求&#47;响应消息传送](../core/media/arch-request-response-1.gif "arch_request 响应 1")</span><span class="sxs-lookup"><span data-stu-id="991bc-107">![Request&#47;Response messaging](../core/media/arch-request-response-1.gif "arch_request-response-1")</span></span>  
  
 <span data-ttu-id="991bc-108">当收到一条消息请求/响应样式的接收适配器，BizTalk Server 首先将请求消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="991bc-108">When a message is received by a request/response style receive adapter, BizTalk Server first publishes the request message to the MessageBox database.</span></span> <span data-ttu-id="991bc-109">接下来的相应订阅服务器上，可能是绑定到接收端口的业务流程收到此消息。</span><span class="sxs-lookup"><span data-stu-id="991bc-109">Next this message is received by the appropriate subscriber, which is likely an orchestration bound to a receive port.</span></span> <span data-ttu-id="991bc-110">此订阅者表述的响应消息，并将其发布到 MessageBox，以及将导致其发回给发出请求的接收端口的属性。</span><span class="sxs-lookup"><span data-stu-id="991bc-110">This subscriber formulates a response message and publishes it to the MessageBox, along with properties that cause it to be sent back to the receive port from which the request came.</span></span> <span data-ttu-id="991bc-111">最后，响应消息被拾取请求，接收适配器提交请求，并返回到调用应用程序的发布服务器。</span><span class="sxs-lookup"><span data-stu-id="991bc-111">Finally, the response message is picked up by the publisher of the request, the receive adapter that submitted the request, and is returned to the calling application.</span></span> <span data-ttu-id="991bc-112">下图提供了这些步骤的详细图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="991bc-112">The diagram below provides a detailed graphical representation of these steps.</span></span>  
  
 <span data-ttu-id="991bc-113">![请求&#47;SOAP 适配器接收到的响应消息](../core/media/arch-request-response-2.gif "arch_request 响应 2")</span><span class="sxs-lookup"><span data-stu-id="991bc-113">![Request&#47;response message received by SOAP adapter](../core/media/arch-request-response-2.gif "arch_request-response-2")</span></span>  
  
 <span data-ttu-id="991bc-114">**SOAP 适配器接收到的请求/响应消息流**</span><span class="sxs-lookup"><span data-stu-id="991bc-114">**Flow of request/response message received by SOAP adapter**</span></span>  
  
1. <span data-ttu-id="991bc-115">SOAP 适配器将提交消息到终结点管理器。</span><span class="sxs-lookup"><span data-stu-id="991bc-115">The SOAP adapter submits messages to the Endpoint Manager.</span></span>  
  
2. <span data-ttu-id="991bc-116">终结点管理器将消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="991bc-116">The Endpoint Manager publishes the message into the MessageBox.</span></span>  
  
3. <span data-ttu-id="991bc-117">业务流程，后者已绑定到接收端口并因此具有消息订阅，接收消息，并对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="991bc-117">The orchestration, which is bound to the receive port and therefore has a subscription for the message, receives the message and processes it.</span></span>  
  
4. <span data-ttu-id="991bc-118">业务流程将发送一个响应消息，发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="991bc-118">The orchestration sends a response message that is published to the MessageBox.</span></span>  
  
5. <span data-ttu-id="991bc-119">终结点管理器接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="991bc-119">The Endpoint Manager receives the response message.</span></span>  
  
6. <span data-ttu-id="991bc-120">终结点管理器返回到 SOAP 适配器的响应</span><span class="sxs-lookup"><span data-stu-id="991bc-120">The Endpoint Manager returns the response to the SOAP adapter</span></span>  
  
   <span data-ttu-id="991bc-121">如果不了解内部实现，则可以忽略此类行为对性能的影响。</span><span class="sxs-lookup"><span data-stu-id="991bc-121">The implications of this type of behavior on performance can be overlooked if the internal implementation is not understood.</span></span> <span data-ttu-id="991bc-122">BizTalk Server 最初优化为高吞吐量的情况，但它也可以配置为具有较低的吞吐量和低滞后时间，尤其是在请求/响应方案的需求。</span><span class="sxs-lookup"><span data-stu-id="991bc-122">BizTalk Server is initially tuned for high throughput scenarios, but it can also be configured for an environment with lower throughput and a need for lower latency, especially in request/response scenarios.</span></span> <span data-ttu-id="991bc-123">您需要考虑在此方案中优化的多个组件。</span><span class="sxs-lookup"><span data-stu-id="991bc-123">You need to consider several components for tuning in this scenario.</span></span> <span data-ttu-id="991bc-124">首先，订户了解已发布的消息通过轮询机制。</span><span class="sxs-lookup"><span data-stu-id="991bc-124">First, subscribers find out about published messages through a polling mechanism.</span></span> <span data-ttu-id="991bc-125">如果轮询间隔设置得太高，这可能导致请求/响应方式具有较高的延迟高于所需的交互。</span><span class="sxs-lookup"><span data-stu-id="991bc-125">If the polling interval is set too high, this could cause request/response style interactions to have a higher latency than you would want.</span></span>  
  
   <span data-ttu-id="991bc-126">请注意，在此方案中，有两个订阅进行填充： 初始消息的订阅以及一个用于响应消息，这会增加此轮询间隔的影响。</span><span class="sxs-lookup"><span data-stu-id="991bc-126">Note that in this scenario, there are two subscriptions to be filled: the subscription for the initial message, as well as the one for the response message, and this increases the impact of this polling interval.</span></span> <span data-ttu-id="991bc-127">第二个，接收适配器配置为将消息插入到 MessageBox 中不同大小的批处理。</span><span class="sxs-lookup"><span data-stu-id="991bc-127">Second, receive adapters are configured to insert messages into the MessageBox in batches of varying sizes.</span></span> <span data-ttu-id="991bc-128">大多数适配器都允许您配置 BizTalk Server 或注册表中的批大小通过典型的适配器配置界面或通过参数。</span><span class="sxs-lookup"><span data-stu-id="991bc-128">Most adapters enable you to configure the batch size through the typical adapter configuration interface or through parameters in BizTalk Server or the registry.</span></span> <span data-ttu-id="991bc-129">如果批大小设置过高，则可能会增加各个消息的延迟。</span><span class="sxs-lookup"><span data-stu-id="991bc-129">If the batch size is set too high, the latency for individual messages may be increased.</span></span> <span data-ttu-id="991bc-130">有关详细信息有关的性能特征[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[规划可持续性能](../core/planning-for-sustained-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="991bc-130">For more information about the performance characteristics of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Planning for Sustained Performance](../core/planning-for-sustained-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991bc-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="991bc-131">See Also</span></span>  
 [<span data-ttu-id="991bc-132">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="991bc-132">Runtime Architecture</span></span>](../core/runtime-architecture.md)