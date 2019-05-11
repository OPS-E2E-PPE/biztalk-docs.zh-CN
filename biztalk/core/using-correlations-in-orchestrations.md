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
ms.openlocfilehash: 4b16c54f4c49a1a81ea412c5b980ba23e60e8290
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401620"
---
# <a name="using-correlations-in-orchestrations"></a><span data-ttu-id="17147-102">业务流程中使用的相关性</span><span class="sxs-lookup"><span data-stu-id="17147-102">Using Correlations in Orchestrations</span></span>
<span data-ttu-id="17147-103">相关是将传入消息与业务流程的相应实例相匹配的过程。</span><span class="sxs-lookup"><span data-stu-id="17147-103">Correlation is the process of matching an incoming message with the appropriate instance of an orchestration.</span></span> <span data-ttu-id="17147-104">例如，业务流程发出一条消息并接收响应或响应回同一业务流程。</span><span class="sxs-lookup"><span data-stu-id="17147-104">For example, orchestration sends out of a message and receives the response or responses back into the same orchestration.</span></span> <span data-ttu-id="17147-105">有三种相关的消息交换模式：</span><span class="sxs-lookup"><span data-stu-id="17147-105">There are three correlated messages exchange patterns:</span></span>  
  
- <span data-ttu-id="17147-106">传统握手</span><span class="sxs-lookup"><span data-stu-id="17147-106">Traditional handshake</span></span>  
  
- <span data-ttu-id="17147-107">顺序保护</span><span class="sxs-lookup"><span data-stu-id="17147-107">Sequential convoy</span></span>  
  
- <span data-ttu-id="17147-108">并行保护</span><span class="sxs-lookup"><span data-stu-id="17147-108">Parallel convoy</span></span>  
  
  <span data-ttu-id="17147-109">在传统握手模式中，握手出现在业务流程或业务流程之间的消息交换，并可以通过在其中相关集是一系列业务流程中定义相关集来实现握手升级具有将消息路由到特定的业务流程实例使用的特定值的属性。</span><span class="sxs-lookup"><span data-stu-id="17147-109">In the traditional handshake pattern, handshakes exist between the exchanges of the messages among the orchestrations or business processes, and you can achieve the handshakes by defining correlation sets in the orchestrations where a correlation set is a list of promoted properties with specific values that you use to route messages to a specific orchestration instance.</span></span>  
  
  <span data-ttu-id="17147-110">如果您的业务流程，用于发出采购订单、 接收发票和付款，则需要以确保通过从发送相应的采购订单的业务流程实例接收的发票消息由于可能会同时处理的采购订单号。</span><span class="sxs-lookup"><span data-stu-id="17147-110">If, for example, your orchestration is designed to issue a purchase order, receive an invoice, and send out the payment, you need to be sure that the invoice message is received by the same orchestration instance that the corresponding purchase order was sent from since numbers of purchase orders may be processed at the time.</span></span> <span data-ttu-id="17147-111">在此示例中，采购订单标识号可用作相关集进行关联的采购订单消息和发票消息中的参数。</span><span class="sxs-lookup"><span data-stu-id="17147-111">In this example, the purchase order identification number can be used as a parameter in the correlation set for correlating the purchase order message and the invoice message.</span></span> <span data-ttu-id="17147-112">下面是此示例中的方案流</span><span class="sxs-lookup"><span data-stu-id="17147-112">The following is the scenario flow for this example,</span></span>  
  
1. <span data-ttu-id="17147-113">业务流程 A 采购订单消息发送到业务流程 b。在发送前查看采购订单消息，初始化相关集。</span><span class="sxs-lookup"><span data-stu-id="17147-113">The Orchestration A sends out the purchase order message to the Orchestration B. Before sending out the purchase order message, the correlation set is initialized.</span></span>  
  
2. <span data-ttu-id="17147-114">在业务流程 B，在其中处理采购订单，生成并发回发票，第一个的接收形状将沿用同一相关集，以接收采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="17147-114">In the Orchestration B, in which processes the purchase order, generates and sends back the invoice, the first Receive shape follows the same correlation set to receive the purchase order message.</span></span>  
  
3. <span data-ttu-id="17147-115">处理后的采购订单消息，将发票消息发送回业务流程 A 时，也将沿用同一相关集。</span><span class="sxs-lookup"><span data-stu-id="17147-115">After processing the purchase order message, when sending back the invoice message to the Orchestration A, the same correlation set is also followed.</span></span>  
  
4. <span data-ttu-id="17147-116">在从业务流程 B，接收发票消息的接收形状在业务流程 A，沿用同一相关集是还以确保接收相关的发票消息基于预定义的相关集。</span><span class="sxs-lookup"><span data-stu-id="17147-116">In the Orchestration A, at the Receive shape which receives the invoice message back from the orchestration B, the same correlation set is also followed to ensure that receiving the correlated invoice message based on the predefined correlation set.</span></span>  
  
   <span data-ttu-id="17147-117">顺序保护和并行保护模式中存在全球多个单一项必须为关联在一起才能实现类似无法完成的单个项本身的任何时间。</span><span class="sxs-lookup"><span data-stu-id="17147-117">The sequential convoy and parallel convoy patterns exist in the world any time multiple single items must be related together in order to achieve something that the individual item cannot accomplish by itself.</span></span> <span data-ttu-id="17147-118">有关详细信息，请参阅[使用保护方案](../core/working-with-convoy-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="17147-118">For more information, see [Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md).</span></span>  
  
   <span data-ttu-id="17147-119">除了相关的消息交换模式，有两种类型的业务流程中的相关性：</span><span class="sxs-lookup"><span data-stu-id="17147-119">In addition to the correlated message exchange patterns, there are two types of correlations in orchestration:</span></span>  
  
- <span data-ttu-id="17147-120">手动相关</span><span class="sxs-lookup"><span data-stu-id="17147-120">Manual correlation</span></span>  
  
- <span data-ttu-id="17147-121">自动关联</span><span class="sxs-lookup"><span data-stu-id="17147-121">Automatic correlation</span></span>  
  
  <span data-ttu-id="17147-122">在手动相关方案中，手动配置业务流程来初始化并沿用相关集，以将消息与正确的实例相关联。</span><span class="sxs-lookup"><span data-stu-id="17147-122">In the manual correlation scenario, you manually configure the orchestrations to initialize and follow the correlation set to associate the messages with proper instances.</span></span> <span data-ttu-id="17147-123">在自动相关方案中，消息引擎将关联消息与实例，例如，如果您的业务流程中设置了请求-响应端口或自相关端口。</span><span class="sxs-lookup"><span data-stu-id="17147-123">In the automatic correlation scenario, the messaging engine will correlate the messages with the instances for you, for example, when you set up Request-Response port or Self-Correlating port in your orchestrations.</span></span>  
  
  <span data-ttu-id="17147-124">每当您的业务流程不具有将消息与实例相关联的一种显式方法，例如激活接收，请求-响应端口或自相关端口时，必须使用相关。</span><span class="sxs-lookup"><span data-stu-id="17147-124">You must use correlation whenever your orchestration does not have an explicit way of associating a message with an instance, such as an activate receive, a request-response, or a self-correlating port.</span></span>  
  
## <a name="examples-of-using-correlations"></a><span data-ttu-id="17147-125">使用相关示例</span><span class="sxs-lookup"><span data-stu-id="17147-125">Examples of Using Correlations</span></span>  
  
-   [<span data-ttu-id="17147-126">PartyResolution（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="17147-126">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="17147-127">从下载 SDK 示例"关联消息与业务流程实例" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="17147-127">Download the SDK sample "Correlating Messages with Orchestration Instances" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="17147-128">从下载 SDK 示例"并行保护" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="17147-128">Download the SDK sample "Parallel Convoy" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17147-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="17147-129">In This Section</span></span>  
  
-   [<span data-ttu-id="17147-130">相关集</span><span class="sxs-lookup"><span data-stu-id="17147-130">Correlation Sets</span></span>](../core/correlation-sets.md) 
  
-   [<span data-ttu-id="17147-131">相关类型</span><span class="sxs-lookup"><span data-stu-id="17147-131">Correlation Types</span></span>](../core/correlation-types.md) 
  
-   [<span data-ttu-id="17147-132">如何添加和删除相关集</span><span class="sxs-lookup"><span data-stu-id="17147-132">How to Add and Remove Correlation Sets</span></span>](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [<span data-ttu-id="17147-133">如何配置相关集</span><span class="sxs-lookup"><span data-stu-id="17147-133">How to Configure Correlation Sets</span></span>](../core/how-to-configure-correlation-sets.md)  
  
-   [<span data-ttu-id="17147-134">如何配置相关类型</span><span class="sxs-lookup"><span data-stu-id="17147-134">How to Configure Correlation Types</span></span>](../core/how-to-configure-correlation-types.md)  
  
-   [<span data-ttu-id="17147-135">使用保护方案</span><span class="sxs-lookup"><span data-stu-id="17147-135">Working with Convoy Scenarios</span></span>](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="17147-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="17147-136">See Also</span></span>  
 [<span data-ttu-id="17147-137">如何使用自相关直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="17147-137">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)