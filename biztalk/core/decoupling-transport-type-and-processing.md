---
title: 分离传输类型和处理 |Microsoft 文档
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
ms.openlocfilehash: 0b14522c6bbf9393bc22f632c4db5eeb5e4a22a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238597"
---
# <a name="decoupling-transport-type-and-processing"></a><span data-ttu-id="ae693-102">分离传输类型和处理</span><span class="sxs-lookup"><span data-stu-id="ae693-102">Decoupling Transport Type and Processing</span></span>
<span data-ttu-id="ae693-103">在面向服务的解决方案中，业务处理与传输和接收消息的具体细节之间通常存在明显的界线。</span><span class="sxs-lookup"><span data-stu-id="ae693-103">In a service oriented solution, a clear line often exists between the business processing and the specifics of transmitting and receiving messages.</span></span> <span data-ttu-id="ae693-104">这样，您可以单独更改解决方案的业务流程或消息传送部分。</span><span class="sxs-lookup"><span data-stu-id="ae693-104">This enables you to change the business process or the messaging part of the solution independently.</span></span>  
  
 <span data-ttu-id="ae693-105">但是，面向服务的解决方案在一处违反了此设计原则。</span><span class="sxs-lookup"><span data-stu-id="ae693-105">The service oriented solution violates this design principle in one place.</span></span> <span data-ttu-id="ae693-106">本部分将描述这种情况，并提供可用的替代方案以及所选的结构。</span><span class="sxs-lookup"><span data-stu-id="ae693-106">This section describes the situation, the possible alternatives, and the selected structure.</span></span>  
  
## <a name="correlation-and-the-mqseries-adapter"></a><span data-ttu-id="ae693-107">相关和 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="ae693-107">Correlation and the MQSeries Adapter</span></span>  
 <span data-ttu-id="ae693-108">若要使用 MQSeries 适配器，则不能使用标准的 BizTalk Server 相关标识符。</span><span class="sxs-lookup"><span data-stu-id="ae693-108">In order to use the MQSeries adapter, you cannot use the standard BizTalk Server correlation identifiers.</span></span> <span data-ttu-id="ae693-109">这是因为相关标识符将转到具有自己的系统相关标识符的 IBM 后端系统。</span><span class="sxs-lookup"><span data-stu-id="ae693-109">This is because the correlation identifier goes to an IBM back-end system that has its own system of correlation identifiers.</span></span> <span data-ttu-id="ae693-110">相反，你必须使用**MQSeries.MQMD_CorrelId**和**MQSeries.MQMD_MsgID**属性。</span><span class="sxs-lookup"><span data-stu-id="ae693-110">Instead, you must use the **MQSeries.MQMD_CorrelId** and **MQSeries.MQMD_MsgID** properties.</span></span> <span data-ttu-id="ae693-111">使用这些属性可能会将特定于传输的信息放入业务流程中，即，放入业务程序中。</span><span class="sxs-lookup"><span data-stu-id="ae693-111">Using these properties potentially puts transport-specific information in the orchestration and, thus, in the business process.</span></span>  
  
 <span data-ttu-id="ae693-112">处理此依存关系的一种方法是使用 BizTalk Server 相关标识符，并使用自定义管道组件翻译 MQSeries 的相关标识符。</span><span class="sxs-lookup"><span data-stu-id="ae693-112">One way to handle this dependency would be to use the BizTalk Server correlation identifier and use a custom pipeline component to translate the correlation identifier for MQSeries.</span></span> <span data-ttu-id="ae693-113">这会增加该方案的复杂性。</span><span class="sxs-lookup"><span data-stu-id="ae693-113">This adds complexity to the scenario.</span></span> <span data-ttu-id="ae693-114">此外，如果传输发生更改，则必须相应地更改两个管道组件。</span><span class="sxs-lookup"><span data-stu-id="ae693-114">In addition, if the transport changes, two pipeline components must be changed.</span></span> <span data-ttu-id="ae693-115">最终，BizTalk Server 相关标识符将重新指定依存关系（在管道组件中），而不是解析 MQSeries 标识符。</span><span class="sxs-lookup"><span data-stu-id="ae693-115">And, ultimately, it relocates the dependency (in the pipeline component) rather than resolving it.</span></span>  
  
 <span data-ttu-id="ae693-116">另一种办法是将特定于 MQSeries 的相关处理分别放置在单独的业务流程中，并调用该业务流程。</span><span class="sxs-lookup"><span data-stu-id="ae693-116">Another option would be to isolate the MQSeries-specific correlation handling to a separate orchestration and call that orchestration.</span></span> <span data-ttu-id="ae693-117">这将保持业务流程的独立性。</span><span class="sxs-lookup"><span data-stu-id="ae693-117">This would preserve the independence of the business process.</span></span> <span data-ttu-id="ae693-118">但这也将导致在业务流程之间存在编译时依存关系。</span><span class="sxs-lookup"><span data-stu-id="ae693-118">However, this introduces a compile-time dependency between the orchestrations.</span></span> <span data-ttu-id="ae693-119">若要修改传输，则两个业务流程都需要进行重新编译（例如，从解决方案的存根版本更改为解决方案的适配器版本）。</span><span class="sxs-lookup"><span data-stu-id="ae693-119">Modifying the transport requires recompiling both orchestrations (as, for example, in going from the stub to the adapter version of the solution).</span></span> <span data-ttu-id="ae693-120">同时，调用也会增加解决方案的响应时间。</span><span class="sxs-lookup"><span data-stu-id="ae693-120">The call also adds to the response time for the solution.</span></span>  
  
 <span data-ttu-id="ae693-121">在增加了复杂性和性能可能降低的情况下，直接在业务流程中使用 MQSeries 相关似乎是最简单的办法。</span><span class="sxs-lookup"><span data-stu-id="ae693-121">Given the additional complexity and possible decrease in performance, it seemed simplest to use the MQSeries correlation directly in the orchestration.</span></span>  
  
 <span data-ttu-id="ae693-122">有关适配器和在业务流程中的相关性的详细信息，请参阅[MQSCorrelationSetOrchestration （BizTalk Server 示例）](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ae693-122">For more information about the adapter and correlations in orchestrations, see [MQSCorrelationSetOrchestration (BizTalk Server Sample)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae693-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae693-123">See Also</span></span>  
 <span data-ttu-id="ae693-124">[服务实现重点介绍面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ae693-124">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="ae693-125">MQSCorrelationSetOrchestration （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="ae693-125">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)