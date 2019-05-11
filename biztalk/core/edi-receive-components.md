---
title: EDI 接收组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d3b82e8-1168-4c2c-bf1a-886b43ff8108
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93eb1bbb4e1a43d8cb9ff7e2a97cb2a6610c6687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389386"
---
# <a name="edi-receive-components"></a><span data-ttu-id="8dc84-102">EDI 接收组件</span><span class="sxs-lookup"><span data-stu-id="8dc84-102">EDI Receive Components</span></span>
<span data-ttu-id="8dc84-103">管道和 EDI/AS2 消息不是此主题处理 EDI 消息中所述的管道组件。</span><span class="sxs-lookup"><span data-stu-id="8dc84-103">The pipeline and pipeline components described in this topic process EDI messages that are not EDI/AS2 messages.</span></span> <span data-ttu-id="8dc84-104">有关处理收到的 EDI/AS2 或 EDI/AS2 消息的信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc84-104">For information about the processing of received EDI/AS2 or non-EDI/AS2 messages, see [AS2 Receive Components](../core/as2-receive-components.md).</span></span> <span data-ttu-id="8dc84-105">请注意 AS2 接收组件还执行 EDI 处理除 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="8dc84-105">Note that AS2 receive components perform EDI processing in addition to AS2 processing.</span></span>  
  
## <a name="edi-receive-pipeline"></a><span data-ttu-id="8dc84-106">EDI 接收管道</span><span class="sxs-lookup"><span data-stu-id="8dc84-106">EDI Receive Pipeline</span></span>  
 <span data-ttu-id="8dc84-107">EDI 接收 EDI 接收管道中执行处理。</span><span class="sxs-lookup"><span data-stu-id="8dc84-107">EDI receive processing is performed in the EDI Receive pipeline.</span></span> <span data-ttu-id="8dc84-108">此管道安装在中的 microsoft.biztalk.edi.edipipelines.dll 内[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8dc84-108">This pipeline is installed in Microsoft.BizTalk.Edi.EdiPipelines.dll in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span> <span data-ttu-id="8dc84-109">此管道处理通过任何传输接收的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="8dc84-109">This pipeline processes EDI messages received over any transport.</span></span> <span data-ttu-id="8dc84-110">它不会处理通过 HTTP 接收 AS2 编码的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="8dc84-110">It does not process AS2-encoded EDI messages received over HTTP.</span></span> <span data-ttu-id="8dc84-111">由 AS2 管道执行 AS2 编码的 EDI 消息的处理。</span><span class="sxs-lookup"><span data-stu-id="8dc84-111">Processing of AS2-encoded EDI messages is performed by the AS2 pipelines.</span></span> <span data-ttu-id="8dc84-112">AS2 接收管道都使用相同的组件来处理和 EDI 管道使用 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="8dc84-112">The AS2 receive pipelines use the same components to process EDI messages as the EDI pipeline uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8dc84-113">如果您创建的接收位置使用 EDIReceive 管道，并且具有 HTTP 传输类型，则可能出现安全问题。</span><span class="sxs-lookup"><span data-stu-id="8dc84-113">A security issue could occur if you create a receive location that uses the EDIReceive pipeline and has a transport type of HTTP.</span></span> <span data-ttu-id="8dc84-114">EdiReceive 管道将不会生成 HTTP"200 确定"确认。</span><span class="sxs-lookup"><span data-stu-id="8dc84-114">The EdiReceive pipeline will not generate an HTTP "200 OK" acknowledgment.</span></span> <span data-ttu-id="8dc84-115">如果不返回任何 EDI 确认，则连接将不正常终止，但将保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="8dc84-115">If no EDI acknowledgment is returned, the connection will not be terminated gracefully, but will remain open.</span></span> <span data-ttu-id="8dc84-116">超时期限已过期时，该连接将超时时间。</span><span class="sxs-lookup"><span data-stu-id="8dc84-116">The connection will time out when the time-out period has expired.</span></span>  
  
 <span data-ttu-id="8dc84-117">EDIReceive 管道包括以下管道组件：</span><span class="sxs-lookup"><span data-stu-id="8dc84-117">The EDIReceive pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="8dc84-118">EDI 拆装器</span><span class="sxs-lookup"><span data-stu-id="8dc84-118">EDI Disassembler</span></span>  
  
-   <span data-ttu-id="8dc84-119">BatchMarker。</span><span class="sxs-lookup"><span data-stu-id="8dc84-119">BatchMarker.</span></span>  
  
## <a name="edi-receive-pipeline-components"></a><span data-ttu-id="8dc84-120">EDI 接收管道组件</span><span class="sxs-lookup"><span data-stu-id="8dc84-120">EDI Receive Pipeline Components</span></span>  
 <span data-ttu-id="8dc84-121">EDIReceive 管道使用以下管道组件。</span><span class="sxs-lookup"><span data-stu-id="8dc84-121">The EDIReceive pipeline use the following pipeline components.</span></span> <span data-ttu-id="8dc84-122">这些组件安装在中的 Microsoft.BizTalk.Edi.PipelineComponents.dll[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。</span><span class="sxs-lookup"><span data-stu-id="8dc84-122">These components are installed in Microsoft.BizTalk.Edi.PipelineComponents.dll in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components\\.</span></span>  
  
### <a name="edi-disassembler"></a><span data-ttu-id="8dc84-123">EDI 拆装器</span><span class="sxs-lookup"><span data-stu-id="8dc84-123">EDI Disassembler</span></span>  
 <span data-ttu-id="8dc84-124">EDI 拆装器 EDIReceive 管道中执行大多数处理收到的 EDI 编码交换。</span><span class="sxs-lookup"><span data-stu-id="8dc84-124">The EDI Disassembler performs most processing of received EDI-encoded interchanges in the EDIReceive Pipeline.</span></span> <span data-ttu-id="8dc84-125">有关 EDI 拆装器如何处理 EDI 消息的信息，请参阅[EDI 拆装器的工作原理](../core/how-the-edi-disassembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc84-125">For information about how the EDI Disassembler processes EDI messages, see [How the EDI Disassembler Works](../core/how-the-edi-disassembler-works.md).</span></span>  
  
### <a name="batchmarker"></a><span data-ttu-id="8dc84-126">BatchMarker</span><span class="sxs-lookup"><span data-stu-id="8dc84-126">BatchMarker</span></span>  
 <span data-ttu-id="8dc84-127">BatchMarker 管道组件准备的交换进行批处理的提升的 BatchId、 ToBeBatched 和 ToBeRouted 上下文属性所需的批处理的交换处理。</span><span class="sxs-lookup"><span data-stu-id="8dc84-127">The BatchMarker pipeline component prepares an interchange for batching by promoting the BatchId, ToBeBatched, and ToBeRouted context properties that are required for processing a batched interchange.</span></span> <span data-ttu-id="8dc84-128">BatchMarker 组件设置这些属性的方式取决于多少贸易合作伙伴协议订阅批元素。</span><span class="sxs-lookup"><span data-stu-id="8dc84-128">How the BatchMarker component sets these properties depends upon how many trading partner agreements subscribes to the batch element.</span></span>  
  
- <span data-ttu-id="8dc84-129">如果只有一个协议订阅相应批元素，BatchMarker 组件设置为 True，将 ToBeBatched 上下文属性，以便批处理业务流程提取批元素。</span><span class="sxs-lookup"><span data-stu-id="8dc84-129">If only one agreement subscribes to the batch element, the BatchMarker component sets the ToBeBatched context property to True, so that the batching orchestration picks up the batch element.</span></span>  
  
- <span data-ttu-id="8dc84-130">如果多个协议订阅批元素，BatchMarker 组件设置为 True，将 ToBeRouted 上下文属性，以便路由业务流程提取批元素。</span><span class="sxs-lookup"><span data-stu-id="8dc84-130">If more than one agreement subscribes to a batch element, the BatchMarker component sets the ToBeRouted context property to True, so that the routing orchestration picks up the batch element.</span></span> <span data-ttu-id="8dc84-131">它还 BatchIds 上下文属性设置为批处理 Id 的空格分隔列表。</span><span class="sxs-lookup"><span data-stu-id="8dc84-131">It also sets the BatchIds context property to a space delimited list of batch IDs.</span></span> <span data-ttu-id="8dc84-132">路由业务流程将为每个批 ID，制作一份批元素，然后将 ToBeBatched 属性设置为 True 的批元素，每个副本上，以便批处理业务流程将提取所有副本。</span><span class="sxs-lookup"><span data-stu-id="8dc84-132">The routing orchestration will then make one copy of the batch element for each batch ID, and set the ToBeBatched property to True on each copy of the batch element, so that the batching orchestration will pick up all copies.</span></span>  
  
  <span data-ttu-id="8dc84-133">BatchMarker 组件包含在 EDIReceive 管道的最后一个阶段 （贸易合作伙伴协议解析）。</span><span class="sxs-lookup"><span data-stu-id="8dc84-133">The BatchMarker component is included in the last stage (trading partner agreement resolution) of the EDIReceive pipeline.</span></span> <span data-ttu-id="8dc84-134">将处理 EDI 消息的所有管道应都包含 BatchMarker 管道组件。</span><span class="sxs-lookup"><span data-stu-id="8dc84-134">All pipelines that will process EDI messages should include the BatchMarker pipeline component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8dc84-135">可以不包含 EDI 拆装器，以便执行贸易合作伙伴协议解析，而不解析 EDI 消息的接收管道中包含 BatchMarker 组件。</span><span class="sxs-lookup"><span data-stu-id="8dc84-135">The BatchMarker component can be included in a receive pipeline that does not include the EDI Dissassembler, in order to perform trading partner agreement resolution without parsing the EDI message.</span></span>  
  
 <span data-ttu-id="8dc84-136">可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BatchMarker 组件来对非 EDI 消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="8dc84-136">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BatchMarker component to batch non-EDI messages.</span></span> <span data-ttu-id="8dc84-137">有关详细信息，请参阅的"处理非 EDI 消息在 BatchMarker 组件"部分[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc84-137">For more information, see the "Processing Non-EDI Messages in the BatchMarker Component" section of [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc84-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="8dc84-138">See Also</span></span>  
 [<span data-ttu-id="8dc84-139">BizTalk Server 如何接收 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="8dc84-139">How BizTalk Server Receives EDI Messages</span></span>](../core/how-biztalk-server-receives-edi-messages.md)