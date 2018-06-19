---
title: 使用 BizTalk 消息引擎 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, Messaging Engine
- adapters, TransportProxy object
- Messaging Engine, adapters
- Messaging Engine, architecture
- TransportProxy object
- Messaging Engine, how to
- architecture, Messaging Engine
- messages, Messaging Engine
ms.assetid: e6b6d1ec-38cd-4721-9673-ae40da003dec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701ed3e82eb75b98a948313a99bb4debc65a8cce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288037"
---
# <a name="using-the-biztalk-messaging-engine"></a><span data-ttu-id="e2390-102">使用 BizTalk 消息传送引擎</span><span class="sxs-lookup"><span data-stu-id="e2390-102">Using the BizTalk Messaging Engine</span></span>
<span data-ttu-id="e2390-103">下图显示了消息引擎的结构。</span><span class="sxs-lookup"><span data-stu-id="e2390-103">The following diagram illustrates the architecture of the Messaging Engine.</span></span> <span data-ttu-id="e2390-104">它显示了一个方案，在该方案中消息由适配器接收，然后提交到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="e2390-104">It shows a scenario in which a message is received by an adapter and submitted into BizTalk Server.</span></span>  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
<span data-ttu-id="e2390-105">消息引擎的结构</span><span class="sxs-lookup"><span data-stu-id="e2390-105">Architecture of the Messaging Engine</span></span>  
  
 <span data-ttu-id="e2390-106">每个适配器具有自己的实例**TransportProxy**它使用与消息引擎进行交互的对象。</span><span class="sxs-lookup"><span data-stu-id="e2390-106">Each adapter has its own instance of a **TransportProxy** object that it uses to interact with the Messaging Engine.</span></span> <span data-ttu-id="e2390-107">适配器对消息引擎成批执行操作，这是以原子方式处理的。</span><span class="sxs-lookup"><span data-stu-id="e2390-107">Adapters perform work against the Messaging Engine in batches, which are processed atomically.</span></span> <span data-ttu-id="e2390-108">批是诸如 SubmitMessage、SuspendMessage 或 DeleteMessage 之类的操作的集合。</span><span class="sxs-lookup"><span data-stu-id="e2390-108">A batch is a collection of operations such as SubmitMessage, SuspendMessage, or DeleteMessage.</span></span>  
  
 <span data-ttu-id="e2390-109">下面是适配器将消息提交到消息引擎的方案的一系列事件：</span><span class="sxs-lookup"><span data-stu-id="e2390-109">The following is the sequence of events for the scenario where an adapter submits a message to the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="e2390-110">适配器创建新消息并将数据流连接到该消息。</span><span class="sxs-lookup"><span data-stu-id="e2390-110">The adapter creates a new message and connects the data stream to the message.</span></span>  
  
2.  <span data-ttu-id="e2390-111">适配器从消息引擎中获取新批。</span><span class="sxs-lookup"><span data-stu-id="e2390-111">The adapter gets a new batch from the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="e2390-112">适配器将该消息添加到要提交的批中。</span><span class="sxs-lookup"><span data-stu-id="e2390-112">The adapter adds the message to the batch to be submitted.</span></span>  
  
4.  <span data-ttu-id="e2390-113">该批提交并在消息引擎线程池中排队。</span><span class="sxs-lookup"><span data-stu-id="e2390-113">The batch is committed and queued up on the Messaging Engine thread pool.</span></span>  
  
5.  <span data-ttu-id="e2390-114">消息引擎线程池开始处理该新批。</span><span class="sxs-lookup"><span data-stu-id="e2390-114">The Messaging Engine thread pool starts processing the new batch.</span></span>  
  
6.  <span data-ttu-id="e2390-115">在接收管道中处理该消息。</span><span class="sxs-lookup"><span data-stu-id="e2390-115">The message is processed in the receive pipeline.</span></span>  
  
7.  <span data-ttu-id="e2390-116">接收管道将生成零个或更多个消息。</span><span class="sxs-lookup"><span data-stu-id="e2390-116">The receive pipeline produces zero or more messages.</span></span> <span data-ttu-id="e2390-117">只要管道没有返回任何错误，它们就可以使用消息。</span><span class="sxs-lookup"><span data-stu-id="e2390-117">Pipelines can consume messages providing they do not return any errors.</span></span> <span data-ttu-id="e2390-118">接收管道可以生成多个消息；这通常会在拆装器组件将单个交换拆装到多个消息时发生。</span><span class="sxs-lookup"><span data-stu-id="e2390-118">Receive pipelines can produce more than one message; typically this happens when the dissassembler component disassembles a single interchange into many messages.</span></span> <span data-ttu-id="e2390-119">接收管道通常会将提交的消息规范化为 XML。</span><span class="sxs-lookup"><span data-stu-id="e2390-119">Typically the receive pipeline normalizes the submitted message into XML.</span></span>  
  
8.  <span data-ttu-id="e2390-120">如果配置了映射，则管道生成的消息将在映射器中进行处理。</span><span class="sxs-lookup"><span data-stu-id="e2390-120">The message(s) produced by the pipeline will be processed in the mapper if mapping is configured.</span></span>  
  
9. <span data-ttu-id="e2390-121">消息将发布到消息代理或 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="e2390-121">The message(s) are published to the Message Agent or to the MessageBox database.</span></span>  
  
10. <span data-ttu-id="e2390-122">消息引擎回调适配器，以通知它该批操作的结果。</span><span class="sxs-lookup"><span data-stu-id="e2390-122">The Messaging Engine calls back the adapter to notify it of the outcome of the batch of work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2390-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="e2390-123">In This Section</span></span>  
  
-   [<span data-ttu-id="e2390-124">可恢复的交换处理</span><span class="sxs-lookup"><span data-stu-id="e2390-124">Recoverable Interchange Processing</span></span>](../core/recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="e2390-125">消息按序送达</span><span class="sxs-lookup"><span data-stu-id="e2390-125">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
  
-   [<span data-ttu-id="e2390-126">错误处理</span><span class="sxs-lookup"><span data-stu-id="e2390-126">Error Handling</span></span>](../core/error-handling.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2390-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2390-127">See Also</span></span>  
 <span data-ttu-id="e2390-128">[BizTalk Server 如何处理大消息](../core/how-biztalk-server-processes-large-messages.md) </span><span class="sxs-lookup"><span data-stu-id="e2390-128">[How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) </span></span>  
 <span data-ttu-id="e2390-129">[引擎性能特征](../core/engine-performance-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="e2390-129">[Engine Performance Characteristics](../core/engine-performance-characteristics.md) </span></span>  
 <span data-ttu-id="e2390-130">[测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="e2390-130">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="e2390-131">[用于测量引擎 MST 测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e2390-131">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="e2390-132">使用 Microsoft BizTalk LoadGen 2007 工具</span><span class="sxs-lookup"><span data-stu-id="e2390-132">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)