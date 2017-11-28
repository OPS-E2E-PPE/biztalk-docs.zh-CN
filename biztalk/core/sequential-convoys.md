---
title: "顺序保护 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- convoy sets
- correlation sets, sequential receive tasks
ms.assetid: f05ff42c-2236-42a3-8166-19700e0c3d97
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329d0f56d9f092cd146a900c42ed48d5206a6393
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sequential-convoys"></a><span data-ttu-id="b347e-102">顺序保护</span><span class="sxs-lookup"><span data-stu-id="b347e-102">Sequential Convoys</span></span>
<span data-ttu-id="b347e-103">顺序保护可以使多个单独的消息结合在一起，以取得所需的效果。</span><span class="sxs-lookup"><span data-stu-id="b347e-103">A sequential convoy enables multiple single messages to join together to achieve a required result.</span></span> <span data-ttu-id="b347e-104">顺序保护是一组具有预定义顺序的相关消息。</span><span class="sxs-lookup"><span data-stu-id="b347e-104">A sequential convoy is a set of related messages that have a predefined order.</span></span> <span data-ttu-id="b347e-105">虽然这些消息不必完全相同，但 BizTalk Server 必须按顺序接收它们。</span><span class="sxs-lookup"><span data-stu-id="b347e-105">Although the messages do not have to be exactly the same, BizTalk Server must receive them in a sequential order.</span></span>  
  
 <span data-ttu-id="b347e-106">例如，假设一家在线零售公司一整天都从直接客户和经销商处接收新订单。</span><span class="sxs-lookup"><span data-stu-id="b347e-106">For example, suppose that an online retail company receives new orders from direct clients and from dealers throughout the course of the day.</span></span> <span data-ttu-id="b347e-107">在下午 2:00 之前接收的所有订单都必须作为单独一批进入仓库，并且订单的接收顺序必须保留。</span><span class="sxs-lookup"><span data-stu-id="b347e-107">All orders received before 2:00 PM must go to the warehouse in a single batch, and the sequence of the receipt of the orders must be preserved.</span></span> <span data-ttu-id="b347e-108">这就使得在仓库中的任何商品脱销的情况下，较早的订单具有优先权。</span><span class="sxs-lookup"><span data-stu-id="b347e-108">This enables earlier orders to have priority in case any items are out of stock in the warehouse.</span></span> <span data-ttu-id="b347e-109">通过将一天的所有订单整理到一个具有批头部信息的文件中，您可以生成此批顺序。</span><span class="sxs-lookup"><span data-stu-id="b347e-109">You build this batch order by assembling all orders for the day in a single file that has batch header information.</span></span> <span data-ttu-id="b347e-110">在下午 2:00，一天的所有订单都进入仓库进行处理。</span><span class="sxs-lookup"><span data-stu-id="b347e-110">At 2:00 PM, all orders for the day go to the warehouse for processing.</span></span> <span data-ttu-id="b347e-111">在下午 2:00 以后接收的所有订单将放到一个新批中，以备第二天进行处理。</span><span class="sxs-lookup"><span data-stu-id="b347e-111">All orders received after 2:00 PM are put into a new batch for processing on the following day.</span></span>  
  
 <span data-ttu-id="b347e-112">上述方案举例说明了需要对传入消息进行顺序保护处理的业务流程。</span><span class="sxs-lookup"><span data-stu-id="b347e-112">The preceding scenario is an example of a business process that requires sequential convoy processing of incoming messages.</span></span> <span data-ttu-id="b347e-113">业务要求指出，在特定一天的下午 2:00 之前接收的所有单个订单都应共同组成一批。</span><span class="sxs-lookup"><span data-stu-id="b347e-113">The business requirements state that all single orders received before 2:00 PM for a specific day should batch together.</span></span> <span data-ttu-id="b347e-114">这就需要接收的第一条消息启动新的业务流程实例并初始化相关集。</span><span class="sxs-lookup"><span data-stu-id="b347e-114">This requires the first message received to start a new orchestration instance and initialize a correlation set.</span></span> <span data-ttu-id="b347e-115">同时，接收的该消息类型的所有其他订单都路由到已经运行的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="b347e-115">At that point, all other orders received of that message type route to the already-running orchestration instance.</span></span> <span data-ttu-id="b347e-116">若要实现此目的，您可以定位**侦听**形状 (包含**接收**形状和**延迟**形状) 内**循环**形状。</span><span class="sxs-lookup"><span data-stu-id="b347e-116">To accomplish this, you position a **Listen** shape (containing a **Receive** shape and a **Delay** shape) inside a **Loop** shape.</span></span> <span data-ttu-id="b347e-117">达到延迟后，循环将结束。</span><span class="sxs-lookup"><span data-stu-id="b347e-117">After reaching the delay, the loop ends.</span></span> <span data-ttu-id="b347e-118">这就允许在同一业务流程中接收无数个订单。</span><span class="sxs-lookup"><span data-stu-id="b347e-118">This allows for the receipt of an unknown number of orders in the same business process.</span></span>  
  
## <a name="implementing-sequential-convoys"></a><span data-ttu-id="b347e-119">实现顺序保护</span><span class="sxs-lookup"><span data-stu-id="b347e-119">Implementing Sequential Convoys</span></span>  
 <span data-ttu-id="b347e-120">您可以使用 BizTalk Server 中的“顺序关联接收”消息传送设计模式来实现顺序保护。</span><span class="sxs-lookup"><span data-stu-id="b347e-120">You can implement sequential convoys by using the "sequential correlated receives" messaging design pattern in BizTalk Server.</span></span> <span data-ttu-id="b347e-121">顺序关联接收是与以前的接收相关联的接收。</span><span class="sxs-lookup"><span data-stu-id="b347e-121">Sequential correlated receives are receives that are correlated to previous receives.</span></span>  
  
 <span data-ttu-id="b347e-122">某个接收的相关集由其他接收初始化时将发生保护处理。</span><span class="sxs-lookup"><span data-stu-id="b347e-122">Convoy processing takes place for cases in which the correlation sets for a receive are initialized by another receive.</span></span>  
  
 <span data-ttu-id="b347e-123">对于需要保护处理的接收，有下列限制：</span><span class="sxs-lookup"><span data-stu-id="b347e-123">For receives that require convoy processing, the following restrictions apply:</span></span>  
  
-   <span data-ttu-id="b347e-124">构成特殊接收的顺序保护集的相关集必须由前一个接收初始化。</span><span class="sxs-lookup"><span data-stu-id="b347e-124">The correlation sets that constitute a sequential convoy set for a particular receive must be initialized by one preceding receive.</span></span>  
  
-   <span data-ttu-id="b347e-125">需要顺序保护处理的接收的端口必须与初始化保护集的接收的端口相同。</span><span class="sxs-lookup"><span data-stu-id="b347e-125">The port for a receive that requires sequential convoy processing must be the same as the port for the receive initializing the convoy set.</span></span> <span data-ttu-id="b347e-126">不支持跨端口保护。</span><span class="sxs-lookup"><span data-stu-id="b347e-126">Cross-port convoys are not supported.</span></span>  
  
-   <span data-ttu-id="b347e-127">需要保护处理的接收的消息类型必须与初始化保护集的接收的消息类型匹配，除非接收语句所操作的是按序送达端口。</span><span class="sxs-lookup"><span data-stu-id="b347e-127">Message types for a receive that requires convoy processing must match the message type for the receive initializing the convoy set, unless the receive statement is operating on an ordered delivery port.</span></span>  
  
-   <span data-ttu-id="b347e-128">参与顺序保护的所有接收都必须沿用由初始化接收所初始化（或跟随）的所有相关集，除非在按序送达端口上操作。</span><span class="sxs-lookup"><span data-stu-id="b347e-128">All receives participating in a sequential convoy must follow all the correlation sets that are initialized (or followed) by the initializing receive, unless operating on an ordered delivery port.</span></span>  
  
-   <span data-ttu-id="b347e-129">如果顺序保护由激活接收语句初始化，则激活接收不能具有筛选器表达式，除非在按序送达端口上操作。</span><span class="sxs-lookup"><span data-stu-id="b347e-129">If a sequential convoy is initialized by an activate receive statement, then the activate receive cannot have a filter expression unless operating on an ordered delivery port.</span></span>  
  
-   <span data-ttu-id="b347e-130">如果顺序保护由激活接收初始化，则后续接收不能位于嵌套的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="b347e-130">If a sequential convoy is initialized by an activate receive, the following receives cannot be inside a nested orchestration.</span></span>  
  
 <span data-ttu-id="b347e-131">有关顺序保护实现的示例，请参阅[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="b347e-131">For an example of sequential convoy implementation, see [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b347e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b347e-132">See Also</span></span>  
 <span data-ttu-id="b347e-133">[使用队列方案](../core/working-with-convoy-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="b347e-133">[Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md) </span></span>  
 [<span data-ttu-id="b347e-134">并行的保护</span><span class="sxs-lookup"><span data-stu-id="b347e-134">Parallel Convoys</span></span>](../core/parallel-convoys.md)