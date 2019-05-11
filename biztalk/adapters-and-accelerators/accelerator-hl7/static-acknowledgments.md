---
title: 静态确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- static acknowledgements
- acknowledgements, static acknowledgements
ms.assetid: 1cdd01fc-1dae-4851-917f-4f13a0f9595a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c9c310dde71d50dcf49fe4d54e2e5679f899de6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291598"
---
# <a name="static-acknowledgments"></a><span data-ttu-id="87fe4-102">静态确认</span><span class="sxs-lookup"><span data-stu-id="87fe4-102">Static Acknowledgments</span></span>
<span data-ttu-id="87fe4-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持原始、 增强、 延迟和静态确认 (ACK) 模式。</span><span class="sxs-lookup"><span data-stu-id="87fe4-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports original, enhanced, deferred, and static acknowledgment (ACK) modes.</span></span> <span data-ttu-id="87fe4-104">如果您选择静态 ACK 模式中的参与方[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成包含仅相对值的指示成功或失败的静态确认。</span><span class="sxs-lookup"><span data-stu-id="87fe4-104">If you select static ACK mode for a party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will generate static ACKs that contain only an indication of success or failure.</span></span> <span data-ttu-id="87fe4-105">静态确认指示是否接收系统接收和处理消息，在成功和失败的值中配置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="87fe4-105">The static ACK indicates whether the receiving system received and processed the message, in success and failure values configured in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
 <span data-ttu-id="87fe4-106">在原始，增强，和延迟模式，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成动态 Ack。</span><span class="sxs-lookup"><span data-stu-id="87fe4-106">In original, enhanced, and deferred modes, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates dynamic ACKs.</span></span> <span data-ttu-id="87fe4-107">进行 HL7 编码，且包含字段，如 MSA.1 确认代码字段和 ERR 段。</span><span class="sxs-lookup"><span data-stu-id="87fe4-107">They are HL7-encoded, and contain fields such as the MSA.1 Acknowledgment Code field and the ERR segment.</span></span> <span data-ttu-id="87fe4-108">动态 ACK MSA.1 字段将指示失败条件是拒绝还是错误，这会导致不同的处理 (请参阅[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md))。</span><span class="sxs-lookup"><span data-stu-id="87fe4-108">The MSA.1 field of a dynamic ACK will indicate whether a failure condition is a Reject or an Error, which result in different processing (see [Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)).</span></span> <span data-ttu-id="87fe4-109">ERR 段提供了有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="87fe4-109">The ERR segment provides detailed information about the error.</span></span> <span data-ttu-id="87fe4-110">静态确认提供没有此类信息。</span><span class="sxs-lookup"><span data-stu-id="87fe4-110">Static ACKs provide no such information.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="87fe4-111">处理了静态确认以不同的方式从动态确认。</span><span class="sxs-lookup"><span data-stu-id="87fe4-111">processes a static ACK differently from a dynamic ACK.</span></span> <span data-ttu-id="87fe4-112">如果一个双向发送端口 （这将收到确认后才发送下一条消息） 接收静态确认，并确认指示失败 （或不是有效的确认），[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将移动到的辅助传输或挂起消息。</span><span class="sxs-lookup"><span data-stu-id="87fe4-112">If a two-way send port (which will only send the next message after receiving the ACK) receives the static ACK, and the ACK indicates failure (or is not a valid ACK), [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will move to the secondary transport or suspend the message.</span></span> <span data-ttu-id="87fe4-113">它不会重试消息，就像它收到了动态的确认，根据失败条件。</span><span class="sxs-lookup"><span data-stu-id="87fe4-113">It will not retry the message, as it would if it received a dynamic ACK, depending upon the failure condition.</span></span>  
  
 <span data-ttu-id="87fe4-114">当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器处理静态 ACK，则它写入**IsStaticAck**到消息上下文的布尔属性。</span><span class="sxs-lookup"><span data-stu-id="87fe4-114">When the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser processes a static ACK, it writes the **IsStaticAck** Boolean property to the message context.</span></span> <span data-ttu-id="87fe4-115">序列化程序使用此值以确定它是否应处理消息作为静态的确认。</span><span class="sxs-lookup"><span data-stu-id="87fe4-115">The serializer uses this value to determine whether it should process the message as a static ACK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87fe4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="87fe4-116">See Also</span></span>  
 <span data-ttu-id="87fe4-117">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="87fe4-117">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="87fe4-118">消息确认段</span><span class="sxs-lookup"><span data-stu-id="87fe4-118">Message Acknowledgment Segment</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)