---
title: 使用 BizTalk 消息引擎 |Microsoft Docs
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
ms.openlocfilehash: 598a7030b885057dc7781336c2925f0cb99b17fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395179"
---
# <a name="using-the-biztalk-messaging-engine"></a><span data-ttu-id="107fe-102">使用 BizTalk 消息引擎</span><span class="sxs-lookup"><span data-stu-id="107fe-102">Using the BizTalk Messaging Engine</span></span>
<span data-ttu-id="107fe-103">下图演示了消息引擎的体系结构。</span><span class="sxs-lookup"><span data-stu-id="107fe-103">The following diagram illustrates the architecture of the Messaging Engine.</span></span> <span data-ttu-id="107fe-104">它显示了其中一条消息是由适配器接收，提交到 BizTalk Server 的方案。</span><span class="sxs-lookup"><span data-stu-id="107fe-104">It shows a scenario in which a message is received by an adapter and submitted into BizTalk Server.</span></span>  
  
 <span data-ttu-id="107fe-105">![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")</span><span class="sxs-lookup"><span data-stu-id="107fe-105">![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")</span></span>  
<span data-ttu-id="107fe-106">消息引擎的体系结构</span><span class="sxs-lookup"><span data-stu-id="107fe-106">Architecture of the Messaging Engine</span></span>  
  
 <span data-ttu-id="107fe-107">每个适配器具有其自己的实例**TransportProxy**它使用与消息引擎进行交互的对象。</span><span class="sxs-lookup"><span data-stu-id="107fe-107">Each adapter has its own instance of a **TransportProxy** object that it uses to interact with the Messaging Engine.</span></span> <span data-ttu-id="107fe-108">适配器在以原子方式处理的批处理中执行对消息引擎的工作。</span><span class="sxs-lookup"><span data-stu-id="107fe-108">Adapters perform work against the Messaging Engine in batches, which are processed atomically.</span></span> <span data-ttu-id="107fe-109">一批是诸如 SubmitMessage、 SuspendMessage 或 DeleteMessage 的集合。</span><span class="sxs-lookup"><span data-stu-id="107fe-109">A batch is a collection of operations such as SubmitMessage, SuspendMessage, or DeleteMessage.</span></span>  
  
 <span data-ttu-id="107fe-110">以下是的适配器将提交到消息引擎的消息的方案的事件序列：</span><span class="sxs-lookup"><span data-stu-id="107fe-110">The following is the sequence of events for the scenario where an adapter submits a message to the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="107fe-111">适配器创建新的消息，并将数据流连接到该消息。</span><span class="sxs-lookup"><span data-stu-id="107fe-111">The adapter creates a new message and connects the data stream to the message.</span></span>  
  
2.  <span data-ttu-id="107fe-112">适配器从消息引擎获取新批。</span><span class="sxs-lookup"><span data-stu-id="107fe-112">The adapter gets a new batch from the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="107fe-113">该适配器将消息添加到提交的批。</span><span class="sxs-lookup"><span data-stu-id="107fe-113">The adapter adds the message to the batch to be submitted.</span></span>  
  
4.  <span data-ttu-id="107fe-114">该批提交并在消息引擎线程池上排队等候。</span><span class="sxs-lookup"><span data-stu-id="107fe-114">The batch is committed and queued up on the Messaging Engine thread pool.</span></span>  
  
5.  <span data-ttu-id="107fe-115">消息引擎线程池开始处理新的批。</span><span class="sxs-lookup"><span data-stu-id="107fe-115">The Messaging Engine thread pool starts processing the new batch.</span></span>  
  
6.  <span data-ttu-id="107fe-116">在接收管道中处理该消息。</span><span class="sxs-lookup"><span data-stu-id="107fe-116">The message is processed in the receive pipeline.</span></span>  
  
7.  <span data-ttu-id="107fe-117">接收管道将生成零个或多个消息。</span><span class="sxs-lookup"><span data-stu-id="107fe-117">The receive pipeline produces zero or more messages.</span></span> <span data-ttu-id="107fe-118">管道可以使用提供它们不会返回任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="107fe-118">Pipelines can consume messages providing they do not return any errors.</span></span> <span data-ttu-id="107fe-119">接收管道可以生成多条消息;这通常会拆装器组件拆装成多个消息的单个交换。</span><span class="sxs-lookup"><span data-stu-id="107fe-119">Receive pipelines can produce more than one message; typically this happens when the dissassembler component disassembles a single interchange into many messages.</span></span> <span data-ttu-id="107fe-120">通常接收管道将已提交的消息规范化为 XML。</span><span class="sxs-lookup"><span data-stu-id="107fe-120">Typically the receive pipeline normalizes the submitted message into XML.</span></span>  
  
8.  <span data-ttu-id="107fe-121">如果配置映射，将在映射器中处理由管道生成的消息。</span><span class="sxs-lookup"><span data-stu-id="107fe-121">The message(s) produced by the pipeline will be processed in the mapper if mapping is configured.</span></span>  
  
9. <span data-ttu-id="107fe-122">消息将发布到消息代理或 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="107fe-122">The message(s) are published to the Message Agent or to the MessageBox database.</span></span>  
  
10. <span data-ttu-id="107fe-123">消息引擎回调适配器，以通知它的工作批的结果。</span><span class="sxs-lookup"><span data-stu-id="107fe-123">The Messaging Engine calls back the adapter to notify it of the outcome of the batch of work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="107fe-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="107fe-124">In This Section</span></span>  
  
-   [<span data-ttu-id="107fe-125">可恢复的交换处理</span><span class="sxs-lookup"><span data-stu-id="107fe-125">Recoverable Interchange Processing</span></span>](../core/recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="107fe-126">按序送达消息</span><span class="sxs-lookup"><span data-stu-id="107fe-126">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
  
-   [<span data-ttu-id="107fe-127">错误处理</span><span class="sxs-lookup"><span data-stu-id="107fe-127">Error Handling</span></span>](../core/error-handling.md)  
  
## <a name="see-also"></a><span data-ttu-id="107fe-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="107fe-128">See Also</span></span>  
 <span data-ttu-id="107fe-129">[BizTalk Server 如何处理大消息](../core/how-biztalk-server-processes-large-messages.md) </span><span class="sxs-lookup"><span data-stu-id="107fe-129">[How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) </span></span>  
 <span data-ttu-id="107fe-130">[引擎性能特征](../core/engine-performance-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="107fe-130">[Engine Performance Characteristics](../core/engine-performance-characteristics.md) </span></span>  
 <span data-ttu-id="107fe-131">[测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="107fe-131">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="107fe-132">[测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="107fe-132">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="107fe-133">使用 Microsoft BizTalk LoadGen 2007 工具</span><span class="sxs-lookup"><span data-stu-id="107fe-133">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)