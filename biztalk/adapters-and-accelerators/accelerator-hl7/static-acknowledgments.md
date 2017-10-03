---
title: "静态确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- static acknowledgements
- acknowledgements, static acknowledgements
ms.assetid: 1cdd01fc-1dae-4851-917f-4f13a0f9595a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8081dc0f3c37c40cb1103567ae06f80037a12730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="static-acknowledgments"></a><span data-ttu-id="e432e-102">静态确认</span><span class="sxs-lookup"><span data-stu-id="e432e-102">Static Acknowledgments</span></span>
<span data-ttu-id="e432e-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持原始、 增强、 延迟，和静态确认 (ACK) 模式。</span><span class="sxs-lookup"><span data-stu-id="e432e-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports original, enhanced, deferred, and static acknowledgment (ACK) modes.</span></span> <span data-ttu-id="e432e-104">如果你选择静态 ACK 模式中的一方[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成包含仅相对值的指示成功或失败的静态确认。</span><span class="sxs-lookup"><span data-stu-id="e432e-104">If you select static ACK mode for a party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will generate static ACKs that contain only an indication of success or failure.</span></span> <span data-ttu-id="e432e-105">是否接收系统接收和处理消息，在成功和失败值配置中，该值指示静态 ACK[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="e432e-105">The static ACK indicates whether the receiving system received and processed the message, in success and failure values configured in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
 <span data-ttu-id="e432e-106">在原始，增强，和延迟模式，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成动态确认。</span><span class="sxs-lookup"><span data-stu-id="e432e-106">In original, enhanced, and deferred modes, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates dynamic ACKs.</span></span> <span data-ttu-id="e432e-107">它们 HL7 编码，并且包含 MSA.1 确认代码字段和 ERR 段等字段。</span><span class="sxs-lookup"><span data-stu-id="e432e-107">They are HL7-encoded, and contain fields such as the MSA.1 Acknowledgment Code field and the ERR segment.</span></span> <span data-ttu-id="e432e-108">动态 ACK MSA.1 字段将指示失败条件是拒绝还是出现错误，导致不同的处理 (请参阅[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md))。</span><span class="sxs-lookup"><span data-stu-id="e432e-108">The MSA.1 field of a dynamic ACK will indicate whether a failure condition is a Reject or an Error, which result in different processing (see [Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)).</span></span> <span data-ttu-id="e432e-109">ERR 段提供有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="e432e-109">The ERR segment provides detailed information about the error.</span></span> <span data-ttu-id="e432e-110">静态 Ack 提供任何此类信息。</span><span class="sxs-lookup"><span data-stu-id="e432e-110">Static ACKs provide no such information.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e432e-111">处理不同于动态确认静态 ACK</span><span class="sxs-lookup"><span data-stu-id="e432e-111"> processes a static ACK differently from a dynamic ACK.</span></span> <span data-ttu-id="e432e-112">如果双向发送端口 （这就只会发送下一条消息后接收 ACK） 收到静态 ACK，并确认指示失败 （或不是有效的 ACK），[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将将转移到辅助传输或挂起消息。</span><span class="sxs-lookup"><span data-stu-id="e432e-112">If a two-way send port (which will only send the next message after receiving the ACK) receives the static ACK, and the ACK indicates failure (or is not a valid ACK), [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will move to the secondary transport or suspend the message.</span></span> <span data-ttu-id="e432e-113">它不会重试消息，就像如果它收到动态 ACK，取决于在故障条件。</span><span class="sxs-lookup"><span data-stu-id="e432e-113">It will not retry the message, as it would if it received a dynamic ACK, depending upon the failure condition.</span></span>  
  
 <span data-ttu-id="e432e-114">当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器处理静态 ACK，它将写入**IsStaticAck**为消息上下文的布尔属性。</span><span class="sxs-lookup"><span data-stu-id="e432e-114">When the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser processes a static ACK, it writes the **IsStaticAck** Boolean property to the message context.</span></span> <span data-ttu-id="e432e-115">序列化程序使用此值以确定它是否应处理为静态的确认消息</span><span class="sxs-lookup"><span data-stu-id="e432e-115">The serializer uses this value to determine whether it should process the message as a static ACK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e432e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e432e-116">See Also</span></span>  
 <span data-ttu-id="e432e-117">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="e432e-117">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="e432e-118">消息确认段</span><span class="sxs-lookup"><span data-stu-id="e432e-118">Message Acknowledgment Segment</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)