---
title: 消息如何流经 BTAHL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6bddae0d685d63772b5fd76f70ba19e0628cab5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000102"
---
# <a name="how-messages-flow-through-btahl7"></a><span data-ttu-id="df25d-102">如何将消息流通过 BTAHL7</span><span class="sxs-lookup"><span data-stu-id="df25d-102">How Messages Flow through BTAHL7</span></span>
<span data-ttu-id="df25d-103">安装 Microsoft BizTalk Accelerator for HL7 时 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 添加 MicrosoftBizTalk Server 之上[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]体系结构。</span><span class="sxs-lookup"><span data-stu-id="df25d-103">When you install Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) on top of MicrosoftBizTalk Server, you add [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] components to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span> <span data-ttu-id="df25d-104">下图显示了组合的系统提供的体系结构概述[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="df25d-104">The following figure shows the combined system, which provides an architectural overview of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="df25d-105">![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")</span><span class="sxs-lookup"><span data-stu-id="df25d-105">![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")</span></span>  
  
## <a name="message-processing-flow"></a><span data-ttu-id="df25d-106">消息处理流</span><span class="sxs-lookup"><span data-stu-id="df25d-106">Message Processing Flow</span></span>  
 <span data-ttu-id="df25d-107">当业务线应用程序发送一条消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统中，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="df25d-107">When a line-of-business application sends a message to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system, the following occurs:</span></span>  
  
1. <span data-ttu-id="df25d-108">如果消息是 HL7 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 MLLP 适配器）。</span><span class="sxs-lookup"><span data-stu-id="df25d-108">If the message is an HL7 message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an MLLP adapter).</span></span> <span data-ttu-id="df25d-109">如果它是一条 XML 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 HTTP 适配器）。</span><span class="sxs-lookup"><span data-stu-id="df25d-109">If it is an XML message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an HTTP adapter).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="df25d-110">可以通过任何适配器; 传输 2.X 和 2.xml XML 消息但是，通常会传输 V2。X 消息通过 MLLP 适配器，并且您通常会通过 HTTP 适配器传输 2.XML 消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-110">You can transport both 2.X and 2.XML messages over any adapter; however, you would usually transport V2.X messages over an MLLP adapter, and you would usually transport 2.XML messages over an HTTP adapter.</span></span>  
  
2. <span data-ttu-id="df25d-111">通过分析由拆装器和验证的接收管道路由消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-111">The message is routed through the receive pipeline for parsing by the disassembler, and validation.</span></span>  
  
   1. <span data-ttu-id="df25d-112">如果传入消息的 HL7 消息，平面文件拆装器 (DASM) 会将其分解为 XML。</span><span class="sxs-lookup"><span data-stu-id="df25d-112">If the incoming message is an HL7 message, the flat file disassembler (DASM) disassembles it into XML.</span></span> <span data-ttu-id="df25d-113">如果传入消息是一条 XML 消息，XML DASM 分解它。</span><span class="sxs-lookup"><span data-stu-id="df25d-113">If the incoming message is an XML message, the XML DASM disassembles it.</span></span>  
  
   2. <span data-ttu-id="df25d-114">如果传入消息批消息，拆装器将分解为各个消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-114">If the incoming message is a batch message, the disassembler disassembles into the individual messages.</span></span> <span data-ttu-id="df25d-115">(有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)并[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)</span><span class="sxs-lookup"><span data-stu-id="df25d-115">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
   3. <span data-ttu-id="df25d-116">DASM 然后验证消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-116">The DASM then validates the message.</span></span>  
  
   4. <span data-ttu-id="df25d-117">如果您使用的双向 MLLP 接收适配器，并且如果拆装器已验证消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]向通过相同的适配器接收原始消息的消息的原始发件人发送确认 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="df25d-117">If you use a two-way MLLP receive adapter, and if the disassembler has validated the message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an acknowledgment (ACK) to the original sender of the message through the same adapter that received the original message.</span></span> <span data-ttu-id="df25d-118">如果没有，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送否定确认 (NAK)。</span><span class="sxs-lookup"><span data-stu-id="df25d-118">If not, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a negative acknowledgment (NAK).</span></span> <span data-ttu-id="df25d-119">（如何完成此步骤取决于确认配置。</span><span class="sxs-lookup"><span data-stu-id="df25d-119">(How this step is accomplished depends on the ACK configuration.</span></span> <span data-ttu-id="df25d-120">有关详细信息，请参阅[ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)</span><span class="sxs-lookup"><span data-stu-id="df25d-120">For details, see [ACK Message Modes](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md).)</span></span>  
  
   5. <span data-ttu-id="df25d-121">如果不使用双向 MLLP 接收适配器，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成确认或确认 （NAK 或 NAKs），并放到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="df25d-121">If you do not use a two-way MLLP receive adapter, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates an ACK or ACKs (or NAK or NAKs) and deposits it into the MessageBox database.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="df25d-122"> 然后将它路由到相应的部门根据发送端口配置可使用任何其他适配器 （除了 MLLP)。</span><span class="sxs-lookup"><span data-stu-id="df25d-122"> then routes it to the appropriate parties based on the send port configuration, which could use any of the other adapters (besides MLLP).</span></span>  
  
      <span data-ttu-id="df25d-123">在平面文件和 XML 拆装器中执行的进程的完整的列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。</span><span class="sxs-lookup"><span data-stu-id="df25d-123">For a more complete listing of the processes performed in the flat file and XML disassemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
3. <span data-ttu-id="df25d-124">通过在适配器和接收管道中，该消息会传递后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将消息传递到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="df25d-124">After the message passes through the adapter and the receive pipeline, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes the message into the MessageBox database.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="df25d-125"> 然后确定接下来发送消息的位置。</span><span class="sxs-lookup"><span data-stu-id="df25d-125"> then determines where to send the message next.</span></span> <span data-ttu-id="df25d-126">如果消息是业务流程的一部分，它将消息发送到业务流程引擎。</span><span class="sxs-lookup"><span data-stu-id="df25d-126">If the message is part of an orchestration, it sends the message to the Orchestration Engine.</span></span>  
  
4. <span data-ttu-id="df25d-127">业务流程引擎处理的消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-127">The Orchestration Engine processes the message.</span></span>  
  
   1. <span data-ttu-id="df25d-128">如果映射会影响该消息，该映射将转换根据其规则的消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-128">If a map affects the message, the map transforms the message according to its rules.</span></span>  
  
   2. <span data-ttu-id="df25d-129">如果已经设置了业务规则，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用管道中，可能会以业务流程引擎外部业务规则引擎 (BRE)。</span><span class="sxs-lookup"><span data-stu-id="df25d-129">If you have set up a business rule, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] invokes the Business Rule Engine (BRE) outside of the pipelines, potentially in the Orchestration Engine.</span></span>  
  
   3. <span data-ttu-id="df25d-130">业务流程引擎将消息发送回 MessageBox 数据库，然后继续处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="df25d-130">The Orchestration Engine sends the message back to the MessageBox database, and then continues processing the orchestration.</span></span>  
  
5. <span data-ttu-id="df25d-131">根据该订阅，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到发送端口。</span><span class="sxs-lookup"><span data-stu-id="df25d-131">Based on the subscription, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the send port.</span></span>  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="df25d-132"> 通过以下处理 （如果适用） 的发送管道将消息路由： 程序集和验证。</span><span class="sxs-lookup"><span data-stu-id="df25d-132"> routes the message through the send pipeline for the following processing (if applicable): assembly and validation.</span></span>  
  
   1. <span data-ttu-id="df25d-133">如果该消息将 HL7 2.X 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将消息从 XML 组合到 HL7 的平面文件组装器 (ASM)。</span><span class="sxs-lookup"><span data-stu-id="df25d-133">If the message will be an HL7 2.X message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles the message from XML into HL7 by the flat file assembler (ASM).</span></span> <span data-ttu-id="df25d-134">如果传入消息将是一条 XML 消息，XML DASM 组合它们。</span><span class="sxs-lookup"><span data-stu-id="df25d-134">If the incoming message will be an XML message, the XML DASM assembles it.</span></span>  
  
   2. <span data-ttu-id="df25d-135">如果该消息将属于批处理消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将每个消息组装为批处理消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-135">If the message will be part of a batch message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles each message into the batch message.</span></span> <span data-ttu-id="df25d-136">(有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)并[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)</span><span class="sxs-lookup"><span data-stu-id="df25d-136">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
   3. <span data-ttu-id="df25d-137">ASM 验证消息 （如果启用通过发送参与方配置设置）。</span><span class="sxs-lookup"><span data-stu-id="df25d-137">The ASM validates the message (if enabled through send-party configuration settings).</span></span>  
  
      <span data-ttu-id="df25d-138">在平面文件和 XML 组装器中执行的进程的完整的列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。</span><span class="sxs-lookup"><span data-stu-id="df25d-138">For a more complete listing of the processes performed in the flat file and XML assemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="df25d-139"> 通过适配器将消息发送。</span><span class="sxs-lookup"><span data-stu-id="df25d-139"> sends the message through an adapter.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="df25d-140">您可以在的适配器; 内传输 2.X 消息和 2.XML 消息但是，大多数系统传输 MLLP 适配器，通过 2.X 消息和 2.通过 HTTP 适配器的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="df25d-140">You can transport 2.X messages and 2.XML messages over a number of adapters; however, most systems transport 2.X messages over an MLLP adapter, and 2.XML messages over an HTTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df25d-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="df25d-141">See Also</span></span>  
 [<span data-ttu-id="df25d-142">BTAHL7 如何路由消息</span><span class="sxs-lookup"><span data-stu-id="df25d-142">How BTAHL7 Routes Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)