---
title: 顺序保护 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- convoy sets
- correlation sets, sequential receive tasks
ms.assetid: f05ff42c-2236-42a3-8166-19700e0c3d97
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7a928650b04b7f57c29ba3abe2828990bf0a0cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393329"
---
# <a name="sequential-convoys"></a><span data-ttu-id="d862a-102">顺序保护</span><span class="sxs-lookup"><span data-stu-id="d862a-102">Sequential Convoys</span></span>
<span data-ttu-id="d862a-103">顺序保护可以使多个单独的消息以实现所需的效果。</span><span class="sxs-lookup"><span data-stu-id="d862a-103">A sequential convoy enables multiple single messages to join together to achieve a required result.</span></span> <span data-ttu-id="d862a-104">顺序保护是一组具有预定义的顺序的相关消息。</span><span class="sxs-lookup"><span data-stu-id="d862a-104">A sequential convoy is a set of related messages that have a predefined order.</span></span> <span data-ttu-id="d862a-105">尽管消息无需是完全相同，但 BizTalk Server 必须按先后顺序来接收它们。</span><span class="sxs-lookup"><span data-stu-id="d862a-105">Although the messages do not have to be exactly the same, BizTalk Server must receive them in a sequential order.</span></span>  
  
 <span data-ttu-id="d862a-106">例如，假设在线零售公司接收新订单，从直接客户和经销商处在整个一天中的课程。</span><span class="sxs-lookup"><span data-stu-id="d862a-106">For example, suppose that an online retail company receives new orders from direct clients and from dealers throughout the course of the day.</span></span> <span data-ttu-id="d862a-107">在下午 2:00 之前接收的所有订单必须都转到单个批处理中的仓库，必须保留的一系列订单的接收顺序。</span><span class="sxs-lookup"><span data-stu-id="d862a-107">All orders received before 2:00 PM must go to the warehouse in a single batch, and the sequence of the receipt of the orders must be preserved.</span></span> <span data-ttu-id="d862a-108">这样，较早的订单具有优先级，以防从仓库中的存货中转出任何项。</span><span class="sxs-lookup"><span data-stu-id="d862a-108">This enables earlier orders to have priority in case any items are out of stock in the warehouse.</span></span> <span data-ttu-id="d862a-109">通过组装具有批头部信息的单个文件中的天的所有订单生成此批顺序。</span><span class="sxs-lookup"><span data-stu-id="d862a-109">You build this batch order by assembling all orders for the day in a single file that has batch header information.</span></span> <span data-ttu-id="d862a-110">在下午 2:00，一天的所有订单都进入仓库进行处理。</span><span class="sxs-lookup"><span data-stu-id="d862a-110">At 2:00 PM, all orders for the day go to the warehouse for processing.</span></span> <span data-ttu-id="d862a-111">2:00 之后接收的所有订单被都放入新批处理的第二天的处理。</span><span class="sxs-lookup"><span data-stu-id="d862a-111">All orders received after 2:00 PM are put into a new batch for processing on the following day.</span></span>  
  
 <span data-ttu-id="d862a-112">前面的方案是需要顺序保护处理的传入消息的业务流程的示例。</span><span class="sxs-lookup"><span data-stu-id="d862a-112">The preceding scenario is an example of a business process that requires sequential convoy processing of incoming messages.</span></span> <span data-ttu-id="d862a-113">业务要求指出，所有单个订单都接收到的特定一天下午 2:00 点之前应统一批处理。</span><span class="sxs-lookup"><span data-stu-id="d862a-113">The business requirements state that all single orders received before 2:00 PM for a specific day should batch together.</span></span> <span data-ttu-id="d862a-114">这要求设置接收启动一个新的业务流程实例并初始化一个相关的第一个消息。</span><span class="sxs-lookup"><span data-stu-id="d862a-114">This requires the first message received to start a new orchestration instance and initialize a correlation set.</span></span> <span data-ttu-id="d862a-115">此时，接收的所有其他订单的消息类型路由到已在运行的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="d862a-115">At that point, all other orders received of that message type route to the already-running orchestration instance.</span></span> <span data-ttu-id="d862a-116">若要实现此目的，您定位**侦听**形状 (包含**接收**形状和一个**延迟**形状) 内**循环**形状。</span><span class="sxs-lookup"><span data-stu-id="d862a-116">To accomplish this, you position a **Listen** shape (containing a **Receive** shape and a **Delay** shape) inside a **Loop** shape.</span></span> <span data-ttu-id="d862a-117">达到延迟后, 结束循环。</span><span class="sxs-lookup"><span data-stu-id="d862a-117">After reaching the delay, the loop ends.</span></span> <span data-ttu-id="d862a-118">这允许将未知数量的同一个业务流程中的订单回执。</span><span class="sxs-lookup"><span data-stu-id="d862a-118">This allows for the receipt of an unknown number of orders in the same business process.</span></span>  
  
## <a name="implementing-sequential-convoys"></a><span data-ttu-id="d862a-119">实现顺序保护</span><span class="sxs-lookup"><span data-stu-id="d862a-119">Implementing Sequential Convoys</span></span>  
 <span data-ttu-id="d862a-120">您可以通过使用实现顺序保护"顺序关联接收"消息传送在 BizTalk Server 中的设计模式。</span><span class="sxs-lookup"><span data-stu-id="d862a-120">You can implement sequential convoys by using the "sequential correlated receives" messaging design pattern in BizTalk Server.</span></span> <span data-ttu-id="d862a-121">顺序关联接收是接收的关联到前一个接收。</span><span class="sxs-lookup"><span data-stu-id="d862a-121">Sequential correlated receives are receives that are correlated to previous receives.</span></span>  
  
 <span data-ttu-id="d862a-122">将在其中接收的相关集由其他接收初始化的情况下发生保护处理。</span><span class="sxs-lookup"><span data-stu-id="d862a-122">Convoy processing takes place for cases in which the correlation sets for a receive are initialized by another receive.</span></span>  
  
 <span data-ttu-id="d862a-123">对于接收到需要保护处理的、 具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="d862a-123">For receives that require convoy processing, the following restrictions apply:</span></span>  
  
- <span data-ttu-id="d862a-124">构成特殊接收必须初始化由前一个的顺序保护集的相关集接收。</span><span class="sxs-lookup"><span data-stu-id="d862a-124">The correlation sets that constitute a sequential convoy set for a particular receive must be initialized by one preceding receive.</span></span>  
  
- <span data-ttu-id="d862a-125">需要顺序保护处理的接收端口必须与初始化保护集的接收端口相同。</span><span class="sxs-lookup"><span data-stu-id="d862a-125">The port for a receive that requires sequential convoy processing must be the same as the port for the receive initializing the convoy set.</span></span> <span data-ttu-id="d862a-126">不支持跨端口保护。</span><span class="sxs-lookup"><span data-stu-id="d862a-126">Cross-port convoys are not supported.</span></span>  
  
- <span data-ttu-id="d862a-127">需要保护处理必须与初始化保护接收的消息类型相匹配的接收的消息类型设置，除非接收语句所操作按序的送达端口上。</span><span class="sxs-lookup"><span data-stu-id="d862a-127">Message types for a receive that requires convoy processing must match the message type for the receive initializing the convoy set, unless the receive statement is operating on an ordered delivery port.</span></span>  
  
- <span data-ttu-id="d862a-128">所有接收参与顺序保护中必须遵循所有相关集已初始化 （或后接） 由初始化接收，除非在按序的送达端口上操作。</span><span class="sxs-lookup"><span data-stu-id="d862a-128">All receives participating in a sequential convoy must follow all the correlation sets that are initialized (or followed) by the initializing receive, unless operating on an ordered delivery port.</span></span>  
  
- <span data-ttu-id="d862a-129">如果顺序保护初始化由激活接收语句，则激活接收不能具有筛选器表达式，除非在按序的送达端口上操作。</span><span class="sxs-lookup"><span data-stu-id="d862a-129">If a sequential convoy is initialized by an activate receive statement, then the activate receive cannot have a filter expression unless operating on an ordered delivery port.</span></span>  
  
- <span data-ttu-id="d862a-130">如果顺序保护初始化由激活接收，则后续接收不能为嵌套的业务流程内。</span><span class="sxs-lookup"><span data-stu-id="d862a-130">If a sequential convoy is initialized by an activate receive, the following receives cannot be inside a nested orchestration.</span></span>  
  
  <span data-ttu-id="d862a-131">有关顺序保护实现的示例，请参阅[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="d862a-131">For an example of sequential convoy implementation, see [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d862a-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="d862a-132">See Also</span></span>  
 <span data-ttu-id="d862a-133">[使用保护方案](../core/working-with-convoy-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="d862a-133">[Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md) </span></span>  
 [<span data-ttu-id="d862a-134">并行保护</span><span class="sxs-lookup"><span data-stu-id="d862a-134">Parallel Convoys</span></span>](../core/parallel-convoys.md)