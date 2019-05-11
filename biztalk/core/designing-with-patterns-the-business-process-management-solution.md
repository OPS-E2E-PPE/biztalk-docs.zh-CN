---
title: 使用模式进行设计： 业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [process management solutions], examples
- patterns [process management solutions], designing
- examples, programming patterns
- designing, programming patterns
ms.assetid: 0583f4a4-01db-4d5b-a1f5-1694c1ddbd30
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3477ff868c6a5f07d6a600e35c1dea4b3d6cf9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530932"
---
# <a name="designing-with-patterns-the-business-process-management-solution"></a><span data-ttu-id="e7a1e-102">使用模式进行设计： 业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="e7a1e-102">Designing with Patterns: the Business Process Management Solution</span></span>
<span data-ttu-id="e7a1e-103">业务流程管理解决方案显示了一种方法来构造流程管理器中的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-103">The business process management solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="e7a1e-104">该解决方案使用一个组件来选择和控制订单处理中的阶段序列。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="e7a1e-105">该解决方案首先获取订单-这可能会为新的服务、 更改或取消服务 — 记录，并处理在传递之前该订单进行确认。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-105">The solution takes an order—which may be for new service, a change, or cancellation of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="e7a1e-106">处理由处理订单的一个或多个阶段组成。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="e7a1e-107">最后，该解决方案返回最终响应向原始订单请求。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-107">Finally, the solution returns a final response to the original order request.</span></span>  
  
 <span data-ttu-id="e7a1e-108">设计完善的流程管理解决方案，可增加或减少而无需重新构造的应用程序的其余部分的过程中的各个阶段。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-108">A well-designed process management solution enables you to add or subtract stages from the process without having to reconstruct the rest of the application.</span></span> <span data-ttu-id="e7a1e-109">此解决方案中采用的方法允许这一点。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-109">The approach taken in this solution allows for exactly that.</span></span> <span data-ttu-id="e7a1e-110">订单处理拆分为分散、 独立的阶段。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-110">The order process is broken into discrete, independent stages.</span></span> <span data-ttu-id="e7a1e-111">所有阶段都从同一个端口读取和使用筛选器来确定哪些消息要供其处理。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-111">All stages read from the same port and use a filter to determine which messages are theirs to process.</span></span> <span data-ttu-id="e7a1e-112">此予以详细介绍在以下部分中，"模式。"</span><span class="sxs-lookup"><span data-stu-id="e7a1e-112">This is explained further in the following section, "Patterns."</span></span>  
  
 <span data-ttu-id="e7a1e-113">此解决方案还通过接受输入 Web 服务，尽管也可以使用此解决方案通过 FTP 连接使用非服务接口。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-113">This solution also accepts input through a Web service, although you can also use a non-service interface with this solution through an FTP connection.</span></span> <span data-ttu-id="e7a1e-114">此工具将模拟应用程序可能会使用批处理系统中的方式。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-114">This facility simulates how the application might be used in a batch system.</span></span>  
  
## <a name="patterns"></a><span data-ttu-id="e7a1e-115">模式</span><span class="sxs-lookup"><span data-stu-id="e7a1e-115">Patterns</span></span>  
 <span data-ttu-id="e7a1e-116">下图显示在业务流程管理解决方案中的前面部分所述的模式的简化的版本。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-116">The following diagram shows a simplified version of the patterns in the business process management solution as described in the preceding section.</span></span>  
  
 <span data-ttu-id="e7a1e-117">![业务流程管理解决方案模式](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")</span><span class="sxs-lookup"><span data-stu-id="e7a1e-117">![Business Process Management Solution Patterns](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")</span></span>  
  
 <span data-ttu-id="e7a1e-118">该解决方案包含以下部分： 服务接口、 FTP 通道、 各种转换器、 流程管理器和两个处理阶段。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-118">The solution consists of the following parts: the service interface, the FTP channel, various translators, the process manager, and the two processing stages.</span></span> <span data-ttu-id="e7a1e-119">预处理部分中的四个转换器创建回服务接口中，将生成一个项历史记录或跟踪数据库中并在服务系统中生成一个条目的确认消息。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-119">The four translators in the preprocessing section create an acknowledgement message that goes back to the service interface, generate an entry in a history or tracking database, and make an entry in the service system.</span></span> <span data-ttu-id="e7a1e-120">第四个转换器可创建流程管理器所需的消息。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-120">The fourth translator creates the message needed by the process manager.</span></span> <span data-ttu-id="e7a1e-121">进程管理器又控制处理阶段。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-121">The process manager in turn controls the processing stages.</span></span>  
  
 <span data-ttu-id="e7a1e-122">在多个进程管理器实现中，管理器会跟踪处理状态。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-122">In many process manager implementations, the manager tracks the processing state.</span></span> <span data-ttu-id="e7a1e-123">此实现中，如图所示，此进行了修改。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-123">This implementation, as the diagram shows, modifies this.</span></span> <span data-ttu-id="e7a1e-124">在此解决方案中，进程管理器消息以指示应接着处理消息的处理阶段中设置的标志。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-124">In this solution, the process manager sets a flag in the message to indicate the processing stage that should next handle the message.</span></span> <span data-ttu-id="e7a1e-125">然后，每个阶段都使用筛选器以确定是否应处理特定消息。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-125">Each stage then uses a filter to determine whether it should handle a particular message.</span></span>  
  
 <span data-ttu-id="e7a1e-126">使用此方法，流程管理器无需维护任何路由信息。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-126">Using this approach, the process manager does not have to maintain any routing information.</span></span> <span data-ttu-id="e7a1e-127">该管理器和各个阶段之间的所有消息都使用相同的端口。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-127">All messages between the manager and the various stages use the same ports.</span></span> <span data-ttu-id="e7a1e-128">若要添加某一阶段，只需添加发送和接收正确的端口和正确的阶段编号的筛选器上的组件。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-128">To add a stage, you only have to add a component that sends and receives on the proper ports and filters for the correct stage number.</span></span> <span data-ttu-id="e7a1e-129">你不必更改任何流程管理器本身。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-129">You don't need to change anything in the process manager itself.</span></span>  
  
 <span data-ttu-id="e7a1e-130">请注意还有许多未表达出关系图。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-130">Note that a lot is left out of the diagram.</span></span> <span data-ttu-id="e7a1e-131">处理阶段可能 — 和，实际上，做 — 与后端进程进行通信。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-131">The processing stages may—and, in fact, do—communicate with backend processes.</span></span> <span data-ttu-id="e7a1e-132">解决方案还可以收集进程中的多个点的历史信息。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-132">The solution could also collect historical information at more than one point in the process.</span></span> <span data-ttu-id="e7a1e-133">这样一来，最重要的是，进程管理器的逻辑未指定。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-133">Perhaps, most significantly, the logic of the process manager isn't specified.</span></span> <span data-ttu-id="e7a1e-134">此外，未指定使用同步或异步连接。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-134">In addition, the use of synchronous or asynchronous connections is not specified.</span></span> <span data-ttu-id="e7a1e-135">将以下各节中讨论这些内容。</span><span class="sxs-lookup"><span data-stu-id="e7a1e-135">These will be considered in following sections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a1e-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7a1e-136">See Also</span></span>  
 <span data-ttu-id="e7a1e-137">[业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="e7a1e-137">[Patterns in the Business Process Management Solution](../core/patterns-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="e7a1e-138">转换业务流程管理解决方案的模式</span><span class="sxs-lookup"><span data-stu-id="e7a1e-138">Translating the Patterns of the Business Process Management Solution</span></span>](../core/translating-the-patterns-of-the-business-process-management-solution.md)