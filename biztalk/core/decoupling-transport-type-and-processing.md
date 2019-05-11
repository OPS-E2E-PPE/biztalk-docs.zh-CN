---
title: 分离传输类型和处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transport types, decoupling processing
- processing, decoupling transport types
- transport types
- transport types, service solutions
- service solution tutorial, MQSeries adapters
- processing, service solutions
- service solution tutorial, decoupling transport type and processing
- correlations, MQSeries adapters
- MQSeries adapters, correlations
- MQSeries adapters, service solutions
ms.assetid: 0b2c733a-e2c7-42ff-a733-f712fde38f7e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23a65f525664d44a53760e5cb905e4db10f0f8a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352469"
---
# <a name="decoupling-transport-type-and-processing"></a><span data-ttu-id="99bd8-102">分离传输类型和处理</span><span class="sxs-lookup"><span data-stu-id="99bd8-102">Decoupling Transport Type and Processing</span></span>
<span data-ttu-id="99bd8-103">在面向服务解决方案中，清除行通常存在业务处理和传输和接收消息的具体情况之间。</span><span class="sxs-lookup"><span data-stu-id="99bd8-103">In a service oriented solution, a clear line often exists between the business processing and the specifics of transmitting and receiving messages.</span></span> <span data-ttu-id="99bd8-104">这使您可以独立地更改业务流程或消息传送解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="99bd8-104">This enables you to change the business process or the messaging part of the solution independently.</span></span>  
  
 <span data-ttu-id="99bd8-105">面向服务的解决方案违反了此设计原则在一个位置。</span><span class="sxs-lookup"><span data-stu-id="99bd8-105">The service oriented solution violates this design principle in one place.</span></span> <span data-ttu-id="99bd8-106">本部分介绍这种情况，可能替代方案，并将所选的结构。</span><span class="sxs-lookup"><span data-stu-id="99bd8-106">This section describes the situation, the possible alternatives, and the selected structure.</span></span>  
  
## <a name="correlation-and-the-mqseries-adapter"></a><span data-ttu-id="99bd8-107">相关和 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="99bd8-107">Correlation and the MQSeries Adapter</span></span>  
 <span data-ttu-id="99bd8-108">若要使用 MQSeries 适配器，不能使用标准 BizTalk Server 相关标识符。</span><span class="sxs-lookup"><span data-stu-id="99bd8-108">In order to use the MQSeries adapter, you cannot use the standard BizTalk Server correlation identifiers.</span></span> <span data-ttu-id="99bd8-109">这是因为相关标识符将转到具有其自己系统相关标识符的 IBM 后端系统。</span><span class="sxs-lookup"><span data-stu-id="99bd8-109">This is because the correlation identifier goes to an IBM back-end system that has its own system of correlation identifiers.</span></span> <span data-ttu-id="99bd8-110">相反，必须使用**MQSeries.MQMD_CorrelId**并**MQSeries.MQMD_MsgID**属性。</span><span class="sxs-lookup"><span data-stu-id="99bd8-110">Instead, you must use the **MQSeries.MQMD_CorrelId** and **MQSeries.MQMD_MsgID** properties.</span></span> <span data-ttu-id="99bd8-111">在业务流程和，因此，业务流程中，可能会使用这些属性将特定于传输的信息。</span><span class="sxs-lookup"><span data-stu-id="99bd8-111">Using these properties potentially puts transport-specific information in the orchestration and, thus, in the business process.</span></span>  
  
 <span data-ttu-id="99bd8-112">处理此依存关系的一种方法是使用 BizTalk Server 相关标识符并使用自定义管道组件翻译 mqseries 相关标识符。</span><span class="sxs-lookup"><span data-stu-id="99bd8-112">One way to handle this dependency would be to use the BizTalk Server correlation identifier and use a custom pipeline component to translate the correlation identifier for MQSeries.</span></span> <span data-ttu-id="99bd8-113">这会增加复杂性的方案。</span><span class="sxs-lookup"><span data-stu-id="99bd8-113">This adds complexity to the scenario.</span></span> <span data-ttu-id="99bd8-114">此外，如果传输发生更改，则必须更改两个管道组件。</span><span class="sxs-lookup"><span data-stu-id="99bd8-114">In addition, if the transport changes, two pipeline components must be changed.</span></span> <span data-ttu-id="99bd8-115">而且，从根本上讲，它重新定位到的依赖关系 （在管道组件中） 而不是解析它。</span><span class="sxs-lookup"><span data-stu-id="99bd8-115">And, ultimately, it relocates the dependency (in the pipeline component) rather than resolving it.</span></span>  
  
 <span data-ttu-id="99bd8-116">另一个选项是隔离到单独的业务流程处理的特定于 MQSeries 的相关并调用该业务流程。</span><span class="sxs-lookup"><span data-stu-id="99bd8-116">Another option would be to isolate the MQSeries-specific correlation handling to a separate orchestration and call that orchestration.</span></span> <span data-ttu-id="99bd8-117">这样可以保持业务流程的独立性。</span><span class="sxs-lookup"><span data-stu-id="99bd8-117">This would preserve the independence of the business process.</span></span> <span data-ttu-id="99bd8-118">但是，它引入了在业务流程之间的编译时依赖项。</span><span class="sxs-lookup"><span data-stu-id="99bd8-118">However, this introduces a compile-time dependency between the orchestrations.</span></span> <span data-ttu-id="99bd8-119">若要修改传输需要进行重新编译这两个业务流程 （为，例如，在从转存根 （stub） 到解决方案的适配器版本）。</span><span class="sxs-lookup"><span data-stu-id="99bd8-119">Modifying the transport requires recompiling both orchestrations (as, for example, in going from the stub to the adapter version of the solution).</span></span> <span data-ttu-id="99bd8-120">调用也会增加解决方案的响应时间。</span><span class="sxs-lookup"><span data-stu-id="99bd8-120">The call also adds to the response time for the solution.</span></span>  
  
 <span data-ttu-id="99bd8-121">给定增加了复杂性和性能可能降低的它看起来最简单的方法直接在业务流程中使用 MQSeries 相关。</span><span class="sxs-lookup"><span data-stu-id="99bd8-121">Given the additional complexity and possible decrease in performance, it seemed simplest to use the MQSeries correlation directly in the orchestration.</span></span>  
  
 <span data-ttu-id="99bd8-122">有关适配器和业务流程中的相关详细信息，请参阅[MQSCorrelationSetOrchestration （BizTalk Server 示例）](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="99bd8-122">For more information about the adapter and correlations in orchestrations, see [MQSCorrelationSetOrchestration (BizTalk Server Sample)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bd8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="99bd8-123">See Also</span></span>  
 <span data-ttu-id="99bd8-124">[面向服务的实现重点推荐的解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="99bd8-124">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="99bd8-125">MQSCorrelationSetOrchestration（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="99bd8-125">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)