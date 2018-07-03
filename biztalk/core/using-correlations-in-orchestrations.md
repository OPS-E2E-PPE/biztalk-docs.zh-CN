---
title: 业务流程中使用相关性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, orchestrations
- messages, correlation sets
- correlation sets
- orchestrations, messages
- messages, validating
ms.assetid: d919afa9-bada-406a-bf4b-7b46c831c6d5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbd81b40006842bc17344b4b39aced80fec4e602
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973902"
---
# <a name="using-correlations-in-orchestrations"></a><span data-ttu-id="5746b-102">业务流程中使用的相关性</span><span class="sxs-lookup"><span data-stu-id="5746b-102">Using Correlations in Orchestrations</span></span>
<span data-ttu-id="5746b-103">相关是将传入消息与业务流程的相应实例相匹配的过程。</span><span class="sxs-lookup"><span data-stu-id="5746b-103">Correlation is the process of matching an incoming message with the appropriate instance of an orchestration.</span></span> <span data-ttu-id="5746b-104">例如，业务流程发出一条消息，然后接收到返回该业务流程的一个或多个响应。</span><span class="sxs-lookup"><span data-stu-id="5746b-104">For example, orchestration sends out of a message and receives the response or responses back into the same orchestration.</span></span> <span data-ttu-id="5746b-105">有三种相关消息交换模式：</span><span class="sxs-lookup"><span data-stu-id="5746b-105">There are three correlated messages exchange patterns:</span></span>  
  
- <span data-ttu-id="5746b-106">传统握手</span><span class="sxs-lookup"><span data-stu-id="5746b-106">Traditional handshake</span></span>  
  
- <span data-ttu-id="5746b-107">顺序保护</span><span class="sxs-lookup"><span data-stu-id="5746b-107">Sequential convoy</span></span>  
  
- <span data-ttu-id="5746b-108">并行保护</span><span class="sxs-lookup"><span data-stu-id="5746b-108">Parallel convoy</span></span>  
  
  <span data-ttu-id="5746b-109">在传统握手模式中，握手出现在业务流程内的消息交换之中，您可以通过在业务流程中定义相关集来实现握手，其中相关集是一个升级属性列表，这些属性具有特定的值，用来将消息路由到特定的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="5746b-109">In the traditional handshake pattern, handshakes exist between the exchanges of the messages among the orchestrations or business processes, and you can achieve the handshakes by defining correlation sets in the orchestrations where a correlation set is a list of promoted properties with specific values that you use to route messages to a specific orchestration instance.</span></span>  
  
  <span data-ttu-id="5746b-110">例如，如果您的业务流程用于发出采购订单，接收发票以及付款，则您需要确保由发送采购订单的业务流程实例接收相应发票消息，因为系统可能同时处理多个采购订单。</span><span class="sxs-lookup"><span data-stu-id="5746b-110">If, for example, your orchestration is designed to issue a purchase order, receive an invoice, and send out the payment, you need to be sure that the invoice message is received by the same orchestration instance that the corresponding purchase order was sent from since numbers of purchase orders may be processed at the time.</span></span> <span data-ttu-id="5746b-111">在下例中，采购订单标识号可用作将采购订单消息与发票消息相关联的相关集中的参数。</span><span class="sxs-lookup"><span data-stu-id="5746b-111">In this example, the purchase order identification number can be used as a parameter in the correlation set for correlating the purchase order message and the invoice message.</span></span> <span data-ttu-id="5746b-112">下面是此示例的流程。</span><span class="sxs-lookup"><span data-stu-id="5746b-112">The following is the scenario flow for this example,</span></span>  
  
1. <span data-ttu-id="5746b-113">业务流程 A 向业务流程 B 发出采购订单消息。在发出采购订单消息之前，初始化相关集。</span><span class="sxs-lookup"><span data-stu-id="5746b-113">The Orchestration A sends out the purchase order message to the Orchestration B. Before sending out the purchase order message, the correlation set is initialized.</span></span>  
  
2. <span data-ttu-id="5746b-114">在业务流程 B 中处理采购订单，生成并发回发票，第一个接收形状将沿用同一相关集来接收采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="5746b-114">In the Orchestration B, in which processes the purchase order, generates and sends back the invoice, the first Receive shape follows the same correlation set to receive the purchase order message.</span></span>  
  
3. <span data-ttu-id="5746b-115">处理完采购订单消息后，在将发票消息发回业务流程 A 时，也将沿用同一相关集。</span><span class="sxs-lookup"><span data-stu-id="5746b-115">After processing the purchase order message, when sending back the invoice message to the Orchestration A, the same correlation set is also followed.</span></span>  
  
4. <span data-ttu-id="5746b-116">在业务流程 A 的接收从业务流程 B 发回的发票消息的接收形状中，也将沿用同一相关集，以确保根据预定义相关集接收相关发票消息。</span><span class="sxs-lookup"><span data-stu-id="5746b-116">In the Orchestration A, at the Receive shape which receives the invoice message back from the orchestration B, the same correlation set is also followed to ensure that receiving the correlated invoice message based on the predefined correlation set.</span></span>  
  
   <span data-ttu-id="5746b-117">在必须将多个单一项关联在一起才能得出所需结果，而单个项目自身不能完成的情况下，就需要使用顺序保护和并行保护模式。</span><span class="sxs-lookup"><span data-stu-id="5746b-117">The sequential convoy and parallel convoy patterns exist in the world any time multiple single items must be related together in order to achieve something that the individual item cannot accomplish by itself.</span></span> <span data-ttu-id="5746b-118">有关详细信息，请参阅[使用保护方案](../core/working-with-convoy-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="5746b-118">For more information, see [Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md).</span></span>  
  
   <span data-ttu-id="5746b-119">除了相关消息交换模式以外，业务流程中还有两种类型的相关：</span><span class="sxs-lookup"><span data-stu-id="5746b-119">In addition to the correlated message exchange patterns, there are two types of correlations in orchestration:</span></span>  
  
- <span data-ttu-id="5746b-120">手动相关</span><span class="sxs-lookup"><span data-stu-id="5746b-120">Manual correlation</span></span>  
  
- <span data-ttu-id="5746b-121">自动相关</span><span class="sxs-lookup"><span data-stu-id="5746b-121">Automatic correlation</span></span>  
  
  <span data-ttu-id="5746b-122">在手动相关方案中，您手动配置业务流程来初始化并沿用相关集，以将消息与正确的实例相关联。</span><span class="sxs-lookup"><span data-stu-id="5746b-122">In the manual correlation scenario, you manually configure the orchestrations to initialize and follow the correlation set to associate the messages with proper instances.</span></span> <span data-ttu-id="5746b-123">在自动相关方案中，消息引擎将为您关联消息与实例，例如，在业务流程中设置请求-响应端口或自相关端口时。</span><span class="sxs-lookup"><span data-stu-id="5746b-123">In the automatic correlation scenario, the messaging engine will correlate the messages with the instances for you, for example, when you set up Request-Response port or Self-Correlating port in your orchestrations.</span></span>  
  
  <span data-ttu-id="5746b-124">在业务流程不能显式将消息与实例相关联时，必须使用相关，例如，活动接收端口、请求-响应端口或自相关端口。</span><span class="sxs-lookup"><span data-stu-id="5746b-124">You must use correlation whenever your orchestration does not have an explicit way of associating a message with an instance, such as an activate receive, a request-response, or a self-correlating port.</span></span>  
  
## <a name="examples-of-using-correlations"></a><span data-ttu-id="5746b-125">使用相关示例</span><span class="sxs-lookup"><span data-stu-id="5746b-125">Examples of Using Correlations</span></span>  
  
-   [<span data-ttu-id="5746b-126">PartyResolution（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="5746b-126">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="5746b-127">从下载 SDK 示例"关联消息与业务流程实例" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="5746b-127">Download the SDK sample "Correlating Messages with Orchestration Instances" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="5746b-128">从下载 SDK 示例"并行保护" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="5746b-128">Download the SDK sample "Parallel Convoy" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5746b-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="5746b-129">In This Section</span></span>  
  
-   [<span data-ttu-id="5746b-130">相关集</span><span class="sxs-lookup"><span data-stu-id="5746b-130">Correlation Sets</span></span>](../core/correlation-sets.md) 
  
-   [<span data-ttu-id="5746b-131">相关类型</span><span class="sxs-lookup"><span data-stu-id="5746b-131">Correlation Types</span></span>](../core/correlation-types.md) 
  
-   [<span data-ttu-id="5746b-132">如何添加和删除相关集</span><span class="sxs-lookup"><span data-stu-id="5746b-132">How to Add and Remove Correlation Sets</span></span>](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [<span data-ttu-id="5746b-133">如何配置相关集</span><span class="sxs-lookup"><span data-stu-id="5746b-133">How to Configure Correlation Sets</span></span>](../core/how-to-configure-correlation-sets.md)  
  
-   [<span data-ttu-id="5746b-134">如何配置相关类型</span><span class="sxs-lookup"><span data-stu-id="5746b-134">How to Configure Correlation Types</span></span>](../core/how-to-configure-correlation-types.md)  
  
-   [<span data-ttu-id="5746b-135">使用保护方案</span><span class="sxs-lookup"><span data-stu-id="5746b-135">Working with Convoy Scenarios</span></span>](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="5746b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="5746b-136">See Also</span></span>  
 [<span data-ttu-id="5746b-137">如何使用自相关直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="5746b-137">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)