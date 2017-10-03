---
title: "EDI 接收组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d3b82e8-1168-4c2c-bf1a-886b43ff8108
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc53f4c592b767c8061fb1ed8134636322b35b9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-receive-components"></a><span data-ttu-id="a9fce-102">EDI 接收组件</span><span class="sxs-lookup"><span data-stu-id="a9fce-102">EDI Receive Components</span></span>
<span data-ttu-id="a9fce-103">本主题中介绍的管道和管道组件用于处理不是 EDI/AS2 消息的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="a9fce-103">The pipeline and pipeline components described in this topic process EDI messages that are not EDI/AS2 messages.</span></span> <span data-ttu-id="a9fce-104">有关处理收到的 EDI/AS2 或非 EDI/AS2 消息的信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。</span><span class="sxs-lookup"><span data-stu-id="a9fce-104">For information about the processing of received EDI/AS2 or non-EDI/AS2 messages, see [AS2 Receive Components](../core/as2-receive-components.md).</span></span> <span data-ttu-id="a9fce-105">请注意，除 AS2 处理以外，AS2 接收组件还执行 EDI 处理。</span><span class="sxs-lookup"><span data-stu-id="a9fce-105">Note that AS2 receive components perform EDI processing in addition to AS2 processing.</span></span>  
  
## <a name="edi-receive-pipeline"></a><span data-ttu-id="a9fce-106">EDI 接收管道</span><span class="sxs-lookup"><span data-stu-id="a9fce-106">EDI Receive Pipeline</span></span>  
 <span data-ttu-id="a9fce-107">EDI 接收处理在 EDI 接收管道中执行。</span><span class="sxs-lookup"><span data-stu-id="a9fce-107">EDI receive processing is performed in the EDI Receive pipeline.</span></span> <span data-ttu-id="a9fce-108">此管道安装在 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 中的 Microsoft.BizTalk.Edi.EdiPipelines.dll 内。</span><span class="sxs-lookup"><span data-stu-id="a9fce-108">This pipeline is installed in Microsoft.BizTalk.Edi.EdiPipelines.dll in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span> <span data-ttu-id="a9fce-109">该管道用于处理通过任何传输接收的 EDI 消息，</span><span class="sxs-lookup"><span data-stu-id="a9fce-109">This pipeline processes EDI messages received over any transport.</span></span> <span data-ttu-id="a9fce-110">但不会处理通过 HTTP 接收的 AS2 编码的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="a9fce-110">It does not process AS2-encoded EDI messages received over HTTP.</span></span> <span data-ttu-id="a9fce-111">由 AS2 管道执行 AS2 编码 EDI 消息的处理。</span><span class="sxs-lookup"><span data-stu-id="a9fce-111">Processing of AS2-encoded EDI messages is performed by the AS2 pipelines.</span></span> <span data-ttu-id="a9fce-112">AS2 接收管道和 EDI 管道使用相同的组件来处理 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="a9fce-112">The AS2 receive pipelines use the same components to process EDI messages as the EDI pipeline uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9fce-113">如果创建的接收位置使用 EDIReceive 管道，但采用 HTTP 传输类型，则可能会导致安全问题。</span><span class="sxs-lookup"><span data-stu-id="a9fce-113">A security issue could occur if you create a receive location that uses the EDIReceive pipeline and has a transport type of HTTP.</span></span> <span data-ttu-id="a9fce-114">EdiReceive 管道将不生成 HTTP“200 OK”确认。</span><span class="sxs-lookup"><span data-stu-id="a9fce-114">The EdiReceive pipeline will not generate an HTTP "200 OK" acknowledgment.</span></span> <span data-ttu-id="a9fce-115">如果未返回 EDI 确认，连接将以非正常方式终止，但仍保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="a9fce-115">If no EDI acknowledgment is returned, the connection will not be terminated gracefully, but will remain open.</span></span> <span data-ttu-id="a9fce-116">当超时期过后，该连接将超时。</span><span class="sxs-lookup"><span data-stu-id="a9fce-116">The connection will time out when the time-out period has expired.</span></span>  
  
 <span data-ttu-id="a9fce-117">EDIReceive 管道包括以下管道组件：</span><span class="sxs-lookup"><span data-stu-id="a9fce-117">The EDIReceive pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="a9fce-118">EDI 拆装器</span><span class="sxs-lookup"><span data-stu-id="a9fce-118">EDI Disassembler</span></span>  
  
-   <span data-ttu-id="a9fce-119">BatchMarker。</span><span class="sxs-lookup"><span data-stu-id="a9fce-119">BatchMarker.</span></span>  
  
## <a name="edi-receive-pipeline-components"></a><span data-ttu-id="a9fce-120">EDI 接收管道组件</span><span class="sxs-lookup"><span data-stu-id="a9fce-120">EDI Receive Pipeline Components</span></span>  
 <span data-ttu-id="a9fce-121">EDIReceive 管道使用以下管道组件。</span><span class="sxs-lookup"><span data-stu-id="a9fce-121">The EDIReceive pipeline use the following pipeline components.</span></span> <span data-ttu-id="a9fce-122">这些组件安装在 Microsoft.BizTalk.Edi.PipelineComponents.dll 中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。</span><span class="sxs-lookup"><span data-stu-id="a9fce-122">These components are installed in Microsoft.BizTalk.Edi.PipelineComponents.dll in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components\\.</span></span>  
  
### <a name="edi-disassembler"></a><span data-ttu-id="a9fce-123">EDI 拆装器</span><span class="sxs-lookup"><span data-stu-id="a9fce-123">EDI Disassembler</span></span>  
 <span data-ttu-id="a9fce-124">对 EDIReceive 管道中收到的 EDI 编码交换的处理大部分是由 EDI 拆装器执行的。</span><span class="sxs-lookup"><span data-stu-id="a9fce-124">The EDI Disassembler performs most processing of received EDI-encoded interchanges in the EDIReceive Pipeline.</span></span> <span data-ttu-id="a9fce-125">EDI 反汇编程序如何处理 EDI 消息的信息，请参阅[EDI 反汇编程序的工作原理](../core/how-the-edi-disassembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="a9fce-125">For information about how the EDI Disassembler processes EDI messages, see [How the EDI Disassembler Works](../core/how-the-edi-disassembler-works.md).</span></span>  
  
### <a name="batchmarker"></a><span data-ttu-id="a9fce-126">BatchMarker</span><span class="sxs-lookup"><span data-stu-id="a9fce-126">BatchMarker</span></span>  
 <span data-ttu-id="a9fce-127">BatchMarker 管道组件通过以下方法来准备要进行批处理的交换：升级处理批交换所需的 BatchId、ToBeBatched 和 ToBeRouted 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a9fce-127">The BatchMarker pipeline component prepares an interchange for batching by promoting the BatchId, ToBeBatched, and ToBeRouted context properties that are required for processing a batched interchange.</span></span> <span data-ttu-id="a9fce-128">BatchMarker 组件设置这些属性的方式取决于有多少贸易合作伙伴协议订阅相应批元素。</span><span class="sxs-lookup"><span data-stu-id="a9fce-128">How the BatchMarker component sets these properties depends upon how many trading partner agreements subscribes to the batch element.</span></span>  
  
-   <span data-ttu-id="a9fce-129">如果只有一个协议订阅此批元素，BatchMarker 组件会将 ToBeBatched 上下文属性设置为 True，以便批处理业务流程提取批元素。</span><span class="sxs-lookup"><span data-stu-id="a9fce-129">If only one agreement subscribes to the batch element, the BatchMarker component sets the ToBeBatched context property to True, so that the batching orchestration picks up the batch element.</span></span>  
  
-   <span data-ttu-id="a9fce-130">如果有多个协议订阅批元素，BatchMarker 组件会将 ToBeRouted 上下文属性设置为 True，以便路由业务流程提取批元素。</span><span class="sxs-lookup"><span data-stu-id="a9fce-130">If more than one agreement subscribes to a batch element, the BatchMarker component sets the ToBeRouted context property to True, so that the routing orchestration picks up the batch element.</span></span> <span data-ttu-id="a9fce-131">它还将 BatchIds 上下文属性设置为一个以空格分隔的批处理 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="a9fce-131">It also sets the BatchIds context property to a space delimited list of batch IDs.</span></span> <span data-ttu-id="a9fce-132">然后，路由业务流程将为每一个批处理 ID 创建一个批元素副本，并将每个批元素副本的 ToBeBatched 属性设置为 True，以便批处理业务流程提取所有副本。</span><span class="sxs-lookup"><span data-stu-id="a9fce-132">The routing orchestration will then make one copy of the batch element for each batch ID, and set the ToBeBatched property to True on each copy of the batch element, so that the batching orchestration will pick up all copies.</span></span>  
  
 <span data-ttu-id="a9fce-133">BatchMarker 组件包含在 EDIReceive 管道的最后一个阶段（贸易合作伙伴协议解析）中。</span><span class="sxs-lookup"><span data-stu-id="a9fce-133">The BatchMarker component is included in the last stage (trading partner agreement resolution) of the EDIReceive pipeline.</span></span> <span data-ttu-id="a9fce-134">将要处理 EDI 消息的所有管道都应包含 BatchMarker 管道组件。</span><span class="sxs-lookup"><span data-stu-id="a9fce-134">All pipelines that will process EDI messages should include the BatchMarker pipeline component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9fce-135">BatchMarker 组件所在的接收管道可以不包含 EDI 拆装器，以便在不解析 EDI 消息的情况下就可以执行贸易合作伙伴协议解析。</span><span class="sxs-lookup"><span data-stu-id="a9fce-135">The BatchMarker component can be included in a receive pipeline that does not include the EDI Dissassembler, in order to perform trading partner agreement resolution without parsing the EDI message.</span></span>  
  
 <span data-ttu-id="a9fce-136">可使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 BatchMarker 组件来对非 EDI 消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="a9fce-136">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BatchMarker component to batch non-EDI messages.</span></span> <span data-ttu-id="a9fce-137">有关详细信息，请参阅的"处理非 EDI 消息中 BatchMarker 组件"部分[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="a9fce-137">For more information, see the "Processing Non-EDI Messages in the BatchMarker Component" section of [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fce-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9fce-138">See Also</span></span>  
 [<span data-ttu-id="a9fce-139">BizTalk Server 接收 EDI 消息的方式</span><span class="sxs-lookup"><span data-stu-id="a9fce-139">How BizTalk Server Receives EDI Messages</span></span>](../core/how-biztalk-server-receives-edi-messages.md)