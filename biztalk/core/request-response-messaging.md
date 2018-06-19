---
title: 请求-响应消息传送 |Microsoft 文档
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
ms.openlocfilehash: cd612d5f41e4648625a2a28398f20ecf74e0a4e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268517"
---
# <a name="request-response-messaging"></a><span data-ttu-id="a8b71-102">请求-响应消息传送</span><span class="sxs-lookup"><span data-stu-id="a8b71-102">Request-Response Messaging</span></span>
<span data-ttu-id="a8b71-103">在请求/响应消息传送模式中，一方发送一个请求消息，接收方将返回一个响应消息。</span><span class="sxs-lookup"><span data-stu-id="a8b71-103">In a request/response messaging pattern, one party sends a request message and the receiving party returns a response message.</span></span> <span data-ttu-id="a8b71-104">请求/响应处理的两个典型示例是浏览器使用 HTTP 适配器与 Web 服务器进行交互，以及使用简单对象访问协议 (SOAP) 适配器进行 Web Services 处理。</span><span class="sxs-lookup"><span data-stu-id="a8b71-104">Two typical examples of request/response processing are the interaction that a browser has with a Web server using the HTTP adapter, and Web service processing using the Simple Object Access Protocol (SOAP) adapter.</span></span> <span data-ttu-id="a8b71-105">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，典型发布/订阅的方式处理请求和响应消息。</span><span class="sxs-lookup"><span data-stu-id="a8b71-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], both the request and the response messages are handled in a typical publish/subscribe fashion.</span></span> <span data-ttu-id="a8b71-106">若要将 BizTalk 应用程序调整到最佳性能，则了解这一点十分重要，因为具有高吞吐量要求的系统配置可能与要求各个消息都具有低延迟时间的系统配置不同。</span><span class="sxs-lookup"><span data-stu-id="a8b71-106">This is an important consideration to understand when you performance-tune a BizTalk application, because a system requiring high throughput might be configured differently than one requiring low latency for individual messages.</span></span>  
  
 <span data-ttu-id="a8b71-107">![请求和 #47;响应消息传送](../core/media/arch-request-response-1.gif "arch_request-响应-1")</span><span class="sxs-lookup"><span data-stu-id="a8b71-107">![Request&#47;Response messaging](../core/media/arch-request-response-1.gif "arch_request-response-1")</span></span>  
  
 <span data-ttu-id="a8b71-108">当采用请求/响应方式的接收适配器收到消息后，BizTalk Server 首先会将该请求消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="a8b71-108">When a message is received by a request/response style receive adapter, BizTalk Server first publishes the request message to the MessageBox database.</span></span> <span data-ttu-id="a8b71-109">随后，相应的订户将接收此消息，该订户可能是绑定到某个接收端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a8b71-109">Next this message is received by the appropriate subscriber, which is likely an orchestration bound to a receive port.</span></span> <span data-ttu-id="a8b71-110">此订阅服务器依照响应消息，并将其发布到 MessageBox，以及将导致其发送回请求所来自的接收端口的属性。</span><span class="sxs-lookup"><span data-stu-id="a8b71-110">This subscriber formulates a response message and publishes it to the MessageBox, along with properties that cause it to be sent back to the receive port from which the request came.</span></span> <span data-ttu-id="a8b71-111">最后，该请求的发布服务器（即提交请求的接收适配器）将提取此响应消息并将其返回到调用方应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8b71-111">Finally, the response message is picked up by the publisher of the request, the receive adapter that submitted the request, and is returned to the calling application.</span></span> <span data-ttu-id="a8b71-112">下图提供了这些步骤的详细的图形表示形式：</span><span class="sxs-lookup"><span data-stu-id="a8b71-112">The diagram below provides a detailed graphical representation of these steps.</span></span>  
  
 <span data-ttu-id="a8b71-113">![请求 &#47; SOAP 适配器接收到响应消息](../core/media/arch-request-response-2.gif "arch_request-响应-2")</span><span class="sxs-lookup"><span data-stu-id="a8b71-113">![Request&#47;response message received by SOAP adapter](../core/media/arch-request-response-2.gif "arch_request-response-2")</span></span>  
  
 <span data-ttu-id="a8b71-114">**SOAP 适配器接收到的请求/响应消息的流**</span><span class="sxs-lookup"><span data-stu-id="a8b71-114">**Flow of request/response message received by SOAP adapter**</span></span>  
  
1.  <span data-ttu-id="a8b71-115">SOAP 适配器将消息提交给终结点管理器。</span><span class="sxs-lookup"><span data-stu-id="a8b71-115">The SOAP adapter submits messages to the Endpoint Manager.</span></span>  
  
2.  <span data-ttu-id="a8b71-116">终结点管理器将消息发布到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="a8b71-116">The Endpoint Manager publishes the message into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="a8b71-117">绑定到接收端口并因此具有消息订阅的业务流程将接收该消息并对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="a8b71-117">The orchestration, which is bound to the receive port and therefore has a subscription for the message, receives the message and processes it.</span></span>  
  
4.  <span data-ttu-id="a8b71-118">该业务流程将发送一个响应消息，该消息将发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="a8b71-118">The orchestration sends a response message that is published to the MessageBox.</span></span>  
  
5.  <span data-ttu-id="a8b71-119">终结点管理器接收该响应消息。</span><span class="sxs-lookup"><span data-stu-id="a8b71-119">The Endpoint Manager receives the response message.</span></span>  
  
6.  <span data-ttu-id="a8b71-120">终结点管理器将响应返回给 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="a8b71-120">The Endpoint Manager returns the response to the SOAP adapter</span></span>  
  
 <span data-ttu-id="a8b71-121">如果不了解内部实现，则可以忽略此类行为对性能的影响。</span><span class="sxs-lookup"><span data-stu-id="a8b71-121">The implications of this type of behavior on performance can be overlooked if the internal implementation is not understood.</span></span> <span data-ttu-id="a8b71-122">BizTalk Server 最初优化为适用于高吞吐量的情况，但也可以将其配置为用于具有较低吞吐量和需要较低延迟时间的环境，尤其是在请求/响应情况下。</span><span class="sxs-lookup"><span data-stu-id="a8b71-122">BizTalk Server is initially tuned for high throughput scenarios, but it can also be configured for an environment with lower throughput and a need for lower latency, especially in request/response scenarios.</span></span> <span data-ttu-id="a8b71-123">在这种情况下进行优化时，您需要考虑若干因素。</span><span class="sxs-lookup"><span data-stu-id="a8b71-123">You need to consider several components for tuning in this scenario.</span></span> <span data-ttu-id="a8b71-124">首先，订户是通过轮询机制来查找有关发布的消息的信息。</span><span class="sxs-lookup"><span data-stu-id="a8b71-124">First, subscribers find out about published messages through a polling mechanism.</span></span> <span data-ttu-id="a8b71-125">如果轮询间隔设置过高，则可能会导致采用请求/响应方式的交互的延迟时间高于所需延迟时间。</span><span class="sxs-lookup"><span data-stu-id="a8b71-125">If the polling interval is set too high, this could cause request/response style interactions to have a higher latency than you would want.</span></span>  
  
 <span data-ttu-id="a8b71-126">请注意，在此方案中，有两个订阅要填充： 对于初始消息，订阅以及一个用于响应消息，这会增加此轮询间隔的影响。</span><span class="sxs-lookup"><span data-stu-id="a8b71-126">Note that in this scenario, there are two subscriptions to be filled: the subscription for the initial message, as well as the one for the response message, and this increases the impact of this polling interval.</span></span> <span data-ttu-id="a8b71-127">其次，接收适配器配置为向 MessageBox 中分批插入不同批大小的消息。</span><span class="sxs-lookup"><span data-stu-id="a8b71-127">Second, receive adapters are configured to insert messages into the MessageBox in batches of varying sizes.</span></span> <span data-ttu-id="a8b71-128">大多数适配器都允许您通过典型的适配器配置界面或通过 BizTalk Server 或注册表中的参数来配置批大小。</span><span class="sxs-lookup"><span data-stu-id="a8b71-128">Most adapters enable you to configure the batch size through the typical adapter configuration interface or through parameters in BizTalk Server or the registry.</span></span> <span data-ttu-id="a8b71-129">如果批大小设置过高，则可能会增加各个消息的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="a8b71-129">If the batch size is set too high, the latency for individual messages may be increased.</span></span> <span data-ttu-id="a8b71-130">有关详细信息有关的性能特征[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[持续性能规划](../core/planning-for-sustained-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="a8b71-130">For more information about the performance characteristics of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Planning for Sustained Performance](../core/planning-for-sustained-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b71-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b71-131">See Also</span></span>  
 [<span data-ttu-id="a8b71-132">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="a8b71-132">Runtime Architecture</span></span>](../core/runtime-architecture.md)