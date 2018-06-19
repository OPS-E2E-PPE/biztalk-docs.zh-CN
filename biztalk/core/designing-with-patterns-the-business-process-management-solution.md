---
title: 设计用于模式： 业务流程管理解决方案 |Microsoft 文档
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
ms.openlocfilehash: 91da8c63fc46ee90696e257bfd6142b5088af305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239661"
---
# <a name="designing-with-patterns-the-business-process-management-solution"></a><span data-ttu-id="bd33d-102">设计用于模式： 业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bd33d-102">Designing with Patterns: the Business Process Management Solution</span></span>
<span data-ttu-id="bd33d-103">业务流程管理解决方案为您展示了一种在 BizTalk 应用程序中构造流程管理器的方法。</span><span class="sxs-lookup"><span data-stu-id="bd33d-103">The business process management solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="bd33d-104">该解决方案使用组件来选择和控制订单处理中的阶段序列。</span><span class="sxs-lookup"><span data-stu-id="bd33d-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="bd33d-105">该解决方案首先获取订单（该订单可能是申请新的服务、申请变化或申请取消服务），然后记录该订单，并在传递订单以进行处理之前对该订单进行确认。</span><span class="sxs-lookup"><span data-stu-id="bd33d-105">The solution takes an order—which may be for new service, a change, or cancellation of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="bd33d-106">处理过程由一个或多个订单处理阶段组成。</span><span class="sxs-lookup"><span data-stu-id="bd33d-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="bd33d-107">最后，该解决方案向原始订单请求返回最终响应。</span><span class="sxs-lookup"><span data-stu-id="bd33d-107">Finally, the solution returns a final response to the original order request.</span></span>  
  
 <span data-ttu-id="bd33d-108">通过设计完善的流程管理解决方案，您可以增减流程中的各个阶段，而无需重新构造其余的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd33d-108">A well-designed process management solution enables you to add or subtract stages from the process without having to reconstruct the rest of the application.</span></span> <span data-ttu-id="bd33d-109">在此解决方案中采用的方法正是这样。</span><span class="sxs-lookup"><span data-stu-id="bd33d-109">The approach taken in this solution allows for exactly that.</span></span> <span data-ttu-id="bd33d-110">将订单处理拆分为分散、独立的阶段。</span><span class="sxs-lookup"><span data-stu-id="bd33d-110">The order process is broken into discrete, independent stages.</span></span> <span data-ttu-id="bd33d-111">所有阶段都从同一端口进行读取，并使用筛选器确定要供其处理的消息。</span><span class="sxs-lookup"><span data-stu-id="bd33d-111">All stages read from the same port and use a filter to determine which messages are theirs to process.</span></span> <span data-ttu-id="bd33d-112">在下一部分“模式”中将对此予以详细介绍。</span><span class="sxs-lookup"><span data-stu-id="bd33d-112">This is explained further in the following section, "Patterns."</span></span>  
  
 <span data-ttu-id="bd33d-113">尽管您可以通过 FTP 连接将非服务接口用于此解决方案。但此解决方案还可通过 Web Services 接受输入，</span><span class="sxs-lookup"><span data-stu-id="bd33d-113">This solution also accepts input through a Web service, although you can also use a non-service interface with this solution through an FTP connection.</span></span> <span data-ttu-id="bd33d-114">此工具将模拟应用程序在批处理系统中的可能用法。</span><span class="sxs-lookup"><span data-stu-id="bd33d-114">This facility simulates how the application might be used in a batch system.</span></span>  
  
## <a name="patterns"></a><span data-ttu-id="bd33d-115">模式</span><span class="sxs-lookup"><span data-stu-id="bd33d-115">Patterns</span></span>  
 <span data-ttu-id="bd33d-116">下图显示了业务流程管理解决方案（如前一部分中所示）中简化版本的模式。</span><span class="sxs-lookup"><span data-stu-id="bd33d-116">The following diagram shows a simplified version of the patterns in the business process management solution as described in the preceding section.</span></span>  
  
 <span data-ttu-id="bd33d-117">![业务流程管理解决方案模式](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")</span><span class="sxs-lookup"><span data-stu-id="bd33d-117">![Business Process Management Solution Patterns](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")</span></span>  
  
 <span data-ttu-id="bd33d-118">解决方案包含以下部分： 服务接口、 FTP 通道、 各种转换器、 进程管理器中，和两个处理阶段。</span><span class="sxs-lookup"><span data-stu-id="bd33d-118">The solution consists of the following parts: the service interface, the FTP channel, various translators, the process manager, and the two processing stages.</span></span> <span data-ttu-id="bd33d-119">预处理部分中的四个转换器可创建返回服务接口的确认消息，在历史记录或跟踪数据库中生成条目，并在服务系统中生成条目。</span><span class="sxs-lookup"><span data-stu-id="bd33d-119">The four translators in the preprocessing section create an acknowledgement message that goes back to the service interface, generate an entry in a history or tracking database, and make an entry in the service system.</span></span> <span data-ttu-id="bd33d-120">第四个转换器可创建流程管理器所需的消息。</span><span class="sxs-lookup"><span data-stu-id="bd33d-120">The fourth translator creates the message needed by the process manager.</span></span> <span data-ttu-id="bd33d-121">而该流程管理器又控制处理阶段。</span><span class="sxs-lookup"><span data-stu-id="bd33d-121">The process manager in turn controls the processing stages.</span></span>  
  
 <span data-ttu-id="bd33d-122">在许多流程管理器实施方式中，该管理器可跟踪处理状态。</span><span class="sxs-lookup"><span data-stu-id="bd33d-122">In many process manager implementations, the manager tracks the processing state.</span></span> <span data-ttu-id="bd33d-123">如图所示，该实施方式对此进行了修改。</span><span class="sxs-lookup"><span data-stu-id="bd33d-123">This implementation, as the diagram shows, modifies this.</span></span> <span data-ttu-id="bd33d-124">在此解决方案中，流程管理器在消息中设置了一个标志，以指示应接着处理消息的处理阶段。</span><span class="sxs-lookup"><span data-stu-id="bd33d-124">In this solution, the process manager sets a flag in the message to indicate the processing stage that should next handle the message.</span></span> <span data-ttu-id="bd33d-125">然后，每个阶段都使用筛选器确定是否应处理特定消息。</span><span class="sxs-lookup"><span data-stu-id="bd33d-125">Each stage then uses a filter to determine whether it should handle a particular message.</span></span>  
  
 <span data-ttu-id="bd33d-126">使用此方法，流程管理器将无需维护任何路由信息。</span><span class="sxs-lookup"><span data-stu-id="bd33d-126">Using this approach, the process manager does not have to maintain any routing information.</span></span> <span data-ttu-id="bd33d-127">管理器和各个阶段之间的所有消息都使用同一端口。</span><span class="sxs-lookup"><span data-stu-id="bd33d-127">All messages between the manager and the various stages use the same ports.</span></span> <span data-ttu-id="bd33d-128">若要添加阶段，则只需添加一个组件，该组件在恰当的端口上进行发送和接收操作并筛选正确的阶段编号。</span><span class="sxs-lookup"><span data-stu-id="bd33d-128">To add a stage, you only have to add a component that sends and receives on the proper ports and filters for the correct stage number.</span></span> <span data-ttu-id="bd33d-129">而无需更改任何流程管理器本身的项。</span><span class="sxs-lookup"><span data-stu-id="bd33d-129">You don't need to change anything in the process manager itself.</span></span>  
  
 <span data-ttu-id="bd33d-130">请注意，在图表中还有许多未表达出来的内容。</span><span class="sxs-lookup"><span data-stu-id="bd33d-130">Note that a lot is left out of the diagram.</span></span> <span data-ttu-id="bd33d-131">实际上，处理阶段可能与后台进程进行通信。</span><span class="sxs-lookup"><span data-stu-id="bd33d-131">The processing stages may—and, in fact, do—communicate with backend processes.</span></span> <span data-ttu-id="bd33d-132">该解决方案还可以收集进程中多个点的历史信息。</span><span class="sxs-lookup"><span data-stu-id="bd33d-132">The solution could also collect historical information at more than one point in the process.</span></span> <span data-ttu-id="bd33d-133">可能最重要的是，未指定流程管理器的逻辑。</span><span class="sxs-lookup"><span data-stu-id="bd33d-133">Perhaps, most significantly, the logic of the process manager isn't specified.</span></span> <span data-ttu-id="bd33d-134">此外，未指定使用同步连接还是异步连接。</span><span class="sxs-lookup"><span data-stu-id="bd33d-134">In addition, the use of synchronous or asynchronous connections is not specified.</span></span> <span data-ttu-id="bd33d-135">在后面几部分中将讨论这些内容。</span><span class="sxs-lookup"><span data-stu-id="bd33d-135">These will be considered in following sections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd33d-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd33d-136">See Also</span></span>  
 <span data-ttu-id="bd33d-137">[业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="bd33d-137">[Patterns in the Business Process Management Solution](../core/patterns-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="bd33d-138">翻译模式的业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bd33d-138">Translating the Patterns of the Business Process Management Solution</span></span>](../core/translating-the-patterns-of-the-business-process-management-solution.md)