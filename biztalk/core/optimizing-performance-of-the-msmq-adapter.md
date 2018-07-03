---
title: 优化 MSMQ 适配器的性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729aaddba023d854d7ecfeb5644357f2383bc6b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011582"
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a><span data-ttu-id="52bc4-102">优化 MSMQ 适配器的性能</span><span class="sxs-lookup"><span data-stu-id="52bc4-102">Optimizing Performance of the MSMQ Adapter</span></span>
<span data-ttu-id="52bc4-103">MSMQ 适配器的优化在发送端与接收端有所不同。</span><span class="sxs-lookup"><span data-stu-id="52bc4-103">Optimization of the MSMQ adapter differs between the send and receive sides.</span></span> <span data-ttu-id="52bc4-104">对于接收端，通过设置接收位置属性可控制优化。</span><span class="sxs-lookup"><span data-stu-id="52bc4-104">You control optimization on the receive side by setting a property on the receive location.</span></span> <span data-ttu-id="52bc4-105">对于发送端，则可以使用业务流程来控制优化。</span><span class="sxs-lookup"><span data-stu-id="52bc4-105">On the send side, you can control optimization by using an orchestration.</span></span>  
  
## <a name="receive-optimization"></a><span data-ttu-id="52bc4-106">接收优化</span><span class="sxs-lookup"><span data-stu-id="52bc4-106">Receive Optimization</span></span>  
 <span data-ttu-id="52bc4-107">在接收端，适配器应使用单个执行线程。</span><span class="sxs-lookup"><span data-stu-id="52bc4-107">On the receive side, you can have the adapter use a single execution thread.</span></span> <span data-ttu-id="52bc4-108">适配器使用单一线程或多个线程上的设置取决于**按序处理**属性上的接收位置，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="52bc4-108">Whether the adapter uses a single thread or multiple threads depends on the setting of the **Ordered Processing** property on the receive location, as follows:</span></span>  
  
- <span data-ttu-id="52bc4-109">当该属性是 **，则返回 True**，适配器对单个线程。</span><span class="sxs-lookup"><span data-stu-id="52bc4-109">When the property is **True**, the adapter operates on a single thread.</span></span> <span data-ttu-id="52bc4-110">这样可限制适配器一次只能处理一个消息，从而节省内存。</span><span class="sxs-lookup"><span data-stu-id="52bc4-110">This limits the adapter to one message at a time and conserves memory.</span></span> <span data-ttu-id="52bc4-111">请注意，这会有效地设置**批大小**为一 (1)，而不考虑分配给它的属性表中的值。</span><span class="sxs-lookup"><span data-stu-id="52bc4-111">Notice that this effectively sets **Batch Size** to one (1), regardless of the value assigned to it in the property sheet.</span></span>  
  
- <span data-ttu-id="52bc4-112">当**按序处理**是**False**，适配器在运行多个线程，并可以处理多条消息一次，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="52bc4-112">When **Ordered Processing** is **False**, the adapter runs multiple threads and can process multiple messages at a time, therefore increasing performance.</span></span>  
  
  <span data-ttu-id="52bc4-113">必须设置**按序处理**到**True**如果管理服务器资源，以至或的数量或大小的消息可能会耗尽可用的内存。</span><span class="sxs-lookup"><span data-stu-id="52bc4-113">You must set **Ordered Processing** to **True** if you put a premium on managing server resources, or if the number or size of messages might exhaust available memory.</span></span>  
  
  <span data-ttu-id="52bc4-114">此外可以通过减少的值控制内存使用量**批大小**接收位置上。</span><span class="sxs-lookup"><span data-stu-id="52bc4-114">You can also control memory use by reducing the value of **Batch Size** on the receive location.</span></span> <span data-ttu-id="52bc4-115">较小的批大小可使内存中保持较少的消息，从而仅使用较少内存。</span><span class="sxs-lookup"><span data-stu-id="52bc4-115">A smaller batch size keeps fewer messages in memory and therefore uses less memory.</span></span>  
  
  <span data-ttu-id="52bc4-116">通过将发送端口和接收位置分别放置在单独的计算机上，也可以降低内存使用率。</span><span class="sxs-lookup"><span data-stu-id="52bc4-116">Placing send ports and receive locations on separate computers can also reduce memory use.</span></span>  
  
## <a name="send-optimization"></a><span data-ttu-id="52bc4-117">发送优化</span><span class="sxs-lookup"><span data-stu-id="52bc4-117">Send Optimization</span></span>  
 <span data-ttu-id="52bc4-118">在发送端，可以使用示例业务流程来实现等效的单个消息处理。</span><span class="sxs-lookup"><span data-stu-id="52bc4-118">On the send side, you can achieve the equivalent single-message processing by using the sample orchestration.</span></span> <span data-ttu-id="52bc4-119">该示例将发送单个消息，然后一直等到其收到确认后才会发送下一个消息。</span><span class="sxs-lookup"><span data-stu-id="52bc4-119">The sample sends a single message and then waits to send the next message until it receives an acknowledgment.</span></span> <span data-ttu-id="52bc4-120">有关详细信息，请参阅[如何从代码创建 MSMQ 接收位置和发送端口](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)。</span><span class="sxs-lookup"><span data-stu-id="52bc4-120">For more information, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="remote-transactional-read-operations"></a><span data-ttu-id="52bc4-121">远程事务性读取操作</span><span class="sxs-lookup"><span data-stu-id="52bc4-121">Remote Transactional Read Operations</span></span>  
 <span data-ttu-id="52bc4-122">与 BizTalk Server MSMQ 适配器是能够发出从事务性 MSMQ 队列进行远程读取的操作。</span><span class="sxs-lookup"><span data-stu-id="52bc4-122">With BizTalk Server the MSMQ adapter is capable of making remote read operations from transactional MSMQ queues.</span></span>  <span data-ttu-id="52bc4-123">这是因为 MSMQ 4.0 和更高版本支持远程事务性读取操作。</span><span class="sxs-lookup"><span data-stu-id="52bc4-123">This is because MSMQ 4.0 and later versions support remote transactional read operations.</span></span>  <span data-ttu-id="52bc4-124">但是，事务性读取操作的速度通常较慢。</span><span class="sxs-lookup"><span data-stu-id="52bc4-124">However, transactional read operations are typically slow operations.</span></span> <span data-ttu-id="52bc4-125">为优化性能，应在没有其他选择时使用这些操作。</span><span class="sxs-lookup"><span data-stu-id="52bc4-125">To optimize performance they should be used only when there is no other option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bc4-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="52bc4-126">See Also</span></span>  
 <span data-ttu-id="52bc4-127">[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="52bc4-127">[How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) </span></span>  
 <span data-ttu-id="52bc4-128">[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="52bc4-128">[How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) </span></span>  
 [<span data-ttu-id="52bc4-129">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="52bc4-129">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)