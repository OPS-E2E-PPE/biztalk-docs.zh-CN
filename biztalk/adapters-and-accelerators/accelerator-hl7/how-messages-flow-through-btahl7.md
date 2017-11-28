---
title: "如何消息流经 BTAHL7 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40ac6defd3b0cf99d2f0e53b3173b32e09efa0c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-messages-flow-through-btahl7"></a><span data-ttu-id="39252-102">如何消息流经 BTAHL7</span><span class="sxs-lookup"><span data-stu-id="39252-102">How Messages Flow through BTAHL7</span></span>
<span data-ttu-id="39252-103">当你安装[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 的顶部[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]，你将添加[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]体系结构。</span><span class="sxs-lookup"><span data-stu-id="39252-103">When you install [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) on top of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], you add [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] components to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span> <span data-ttu-id="39252-104">下图显示了组合的系统提供的体系结构概述[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39252-104">The following figure shows the combined system, which provides an architectural overview of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")  
  
## <a name="message-processing-flow"></a><span data-ttu-id="39252-105">消息处理流程</span><span class="sxs-lookup"><span data-stu-id="39252-105">Message Processing Flow</span></span>  
 <span data-ttu-id="39252-106">当业务线应用程序发送一条消息给[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="39252-106">When a line-of-business application sends a message to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system, the following occurs:</span></span>  
  
1.  <span data-ttu-id="39252-107">如果消息的 HL7 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 MLLP 适配器）。</span><span class="sxs-lookup"><span data-stu-id="39252-107">If the message is an HL7 message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an MLLP adapter).</span></span> <span data-ttu-id="39252-108">如果它是一条 XML 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 HTTP 适配器）。</span><span class="sxs-lookup"><span data-stu-id="39252-108">If it is an XML message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an HTTP adapter).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39252-109">你可以通过任何适配器; 传输 2.X 和 2.XML 消息但是，你通常将传输 V2。通过 MLLP 适配器，并且你的 X 消息通常会通过 HTTP 适配器传输 2.XML 消息。</span><span class="sxs-lookup"><span data-stu-id="39252-109">You can transport both 2.X and 2.XML messages over any adapter; however, you would usually transport V2.X messages over an MLLP adapter, and you would usually transport 2.XML messages over an HTTP adapter.</span></span>  
  
2.  <span data-ttu-id="39252-110">将消息路由通过分析通过反汇编程序，并验证接收管道。</span><span class="sxs-lookup"><span data-stu-id="39252-110">The message is routed through the receive pipeline for parsing by the disassembler, and validation.</span></span>  
  
    1.  <span data-ttu-id="39252-111">如果传入消息的 HL7 消息，平面文件反汇编程序 (DASM) 会将其分解为 XML。</span><span class="sxs-lookup"><span data-stu-id="39252-111">If the incoming message is an HL7 message, the flat file disassembler (DASM) disassembles it into XML.</span></span> <span data-ttu-id="39252-112">如果传入消息是一条 XML 消息，则 XML DASM 反汇编它。</span><span class="sxs-lookup"><span data-stu-id="39252-112">If the incoming message is an XML message, the XML DASM disassembles it.</span></span>  
  
    2.  <span data-ttu-id="39252-113">如果传入消息批处理消息，拆装器将分解为单独的消息。</span><span class="sxs-lookup"><span data-stu-id="39252-113">If the incoming message is a batch message, the disassembler disassembles into the individual messages.</span></span> <span data-ttu-id="39252-114">(有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)和[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)</span><span class="sxs-lookup"><span data-stu-id="39252-114">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
    3.  <span data-ttu-id="39252-115">DASM 然后验证消息。</span><span class="sxs-lookup"><span data-stu-id="39252-115">The DASM then validates the message.</span></span>  
  
    4.  <span data-ttu-id="39252-116">如果你使用的双向 MLLP 接收适配器，并且如果拆装器已验证消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将确认 (ACK) 发送到同一个适配器接收原始消息通过消息的原始发送方。</span><span class="sxs-lookup"><span data-stu-id="39252-116">If you use a two-way MLLP receive adapter, and if the disassembler has validated the message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an acknowledgment (ACK) to the original sender of the message through the same adapter that received the original message.</span></span> <span data-ttu-id="39252-117">如果没有，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将发送否定确认 （否认）。</span><span class="sxs-lookup"><span data-stu-id="39252-117">If not, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a negative acknowledgment (NAK).</span></span> <span data-ttu-id="39252-118">（如何完成此步骤依赖于 ACK 配置。</span><span class="sxs-lookup"><span data-stu-id="39252-118">(How this step is accomplished depends on the ACK configuration.</span></span> <span data-ttu-id="39252-119">有关详细信息，请参阅[ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)</span><span class="sxs-lookup"><span data-stu-id="39252-119">For details, see [ACK Message Modes](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md).)</span></span>  
  
    5.  <span data-ttu-id="39252-120">如果未使用的双向 MLLP 接收适配器，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成 ACK 或确认 （或否认或 NAKs），并放入 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="39252-120">If you do not use a two-way MLLP receive adapter, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates an ACK or ACKs (or NAK or NAKs) and deposits it into the MessageBox database.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="39252-121">然后将它路由到相应的部门基于发送端口配置，可以使用它的任何其他适配器 （除了 MLLP)。</span><span class="sxs-lookup"><span data-stu-id="39252-121"> then routes it to the appropriate parties based on the send port configuration, which could use any of the other adapters (besides MLLP).</span></span>  
  
     <span data-ttu-id="39252-122">在平面文件和 XML 反汇编程序中执行的进程的更完整列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。</span><span class="sxs-lookup"><span data-stu-id="39252-122">For a more complete listing of the processes performed in the flat file and XML disassemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
3.  <span data-ttu-id="39252-123">消息传递和接收管道中，该适配器后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将该消息传递到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="39252-123">After the message passes through the adapter and the receive pipeline, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes the message into the MessageBox database.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="39252-124">然后，确定下一步将消息发送到何处。</span><span class="sxs-lookup"><span data-stu-id="39252-124"> then determines where to send the message next.</span></span> <span data-ttu-id="39252-125">如果消息是业务流程的一部分，它会将消息发送到业务流程引擎。</span><span class="sxs-lookup"><span data-stu-id="39252-125">If the message is part of an orchestration, it sends the message to the Orchestration Engine.</span></span>  
  
4.  <span data-ttu-id="39252-126">业务流程引擎处理的消息。</span><span class="sxs-lookup"><span data-stu-id="39252-126">The Orchestration Engine processes the message.</span></span>  
  
    1.  <span data-ttu-id="39252-127">如果地图会影响消息，该映射将根据其规则消息转换。</span><span class="sxs-lookup"><span data-stu-id="39252-127">If a map affects the message, the map transforms the message according to its rules.</span></span>  
  
    2.  <span data-ttu-id="39252-128">如果已经设置了业务规则，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用外部管道，可能在业务流程引擎业务规则引擎 (BRE)。</span><span class="sxs-lookup"><span data-stu-id="39252-128">If you have set up a business rule, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] invokes the Business Rule Engine (BRE) outside of the pipelines, potentially in the Orchestration Engine.</span></span>  
  
    3.  <span data-ttu-id="39252-129">业务流程引擎将消息发送回 MessageBox 数据库，然后继续处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="39252-129">The Orchestration Engine sends the message back to the MessageBox database, and then continues processing the orchestration.</span></span>  
  
5.  <span data-ttu-id="39252-130">根据订阅，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到发送端口。</span><span class="sxs-lookup"><span data-stu-id="39252-130">Based on the subscription, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the send port.</span></span>  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="39252-131">将以下的处理，（如果适用） 发送管道通过消息路由： 程序集和验证。</span><span class="sxs-lookup"><span data-stu-id="39252-131"> routes the message through the send pipeline for the following processing (if applicable): assembly and validation.</span></span>  
  
    1.  <span data-ttu-id="39252-132">如果该消息将是 HL7 2.X 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将消息从 XML 组合到 HL7 通过平面文件汇编器 (ASM)。</span><span class="sxs-lookup"><span data-stu-id="39252-132">If the message will be an HL7 2.X message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles the message from XML into HL7 by the flat file assembler (ASM).</span></span> <span data-ttu-id="39252-133">如果传入的消息将一条 XML 消息，则 XML DASM 汇编它。</span><span class="sxs-lookup"><span data-stu-id="39252-133">If the incoming message will be an XML message, the XML DASM assembles it.</span></span>  
  
    2.  <span data-ttu-id="39252-134">如果该消息将作为一部分的批处理消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组合成批处理消息的每条消息。</span><span class="sxs-lookup"><span data-stu-id="39252-134">If the message will be part of a batch message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles each message into the batch message.</span></span> <span data-ttu-id="39252-135">(有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)和[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)</span><span class="sxs-lookup"><span data-stu-id="39252-135">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
    3.  <span data-ttu-id="39252-136">ASM 验证消息 （如果启用通过发送方配置设置）。</span><span class="sxs-lookup"><span data-stu-id="39252-136">The ASM validates the message (if enabled through send-party configuration settings).</span></span>  
  
     <span data-ttu-id="39252-137">平面文件和 XML 汇编程序中执行的进程的更完整列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。</span><span class="sxs-lookup"><span data-stu-id="39252-137">For a more complete listing of the processes performed in the flat file and XML assemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
7.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="39252-138">将通过适配器消息发送。</span><span class="sxs-lookup"><span data-stu-id="39252-138"> sends the message through an adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39252-139">你可以在大量的适配器; 传输 2.X 消息和 2.XML 消息但是，大多数系统传输 MLLP 适配器，通过的 2.X 消息和 2.通过 HTTP 适配器的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="39252-139">You can transport 2.X messages and 2.XML messages over a number of adapters; however, most systems transport 2.X messages over an MLLP adapter, and 2.XML messages over an HTTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39252-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39252-140">See Also</span></span>  
 [<span data-ttu-id="39252-141">BTAHL7 将消息的路由</span><span class="sxs-lookup"><span data-stu-id="39252-141">How BTAHL7 Routes Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)