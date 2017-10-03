---
title: "确认错误条件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15b481f4cdb60822841021f7f708a6caea021b8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-error-conditions"></a><span data-ttu-id="df8df-102">确认错误条件</span><span class="sxs-lookup"><span data-stu-id="df8df-102">Acknowledgment Error Conditions</span></span>
<span data-ttu-id="df8df-103">以下条件将导致严重的错误条件时[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 是处理确认 (ACK) 消息：</span><span class="sxs-lookup"><span data-stu-id="df8df-103">The following conditions will result in a fatal error condition when [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) is processing acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="df8df-104">缺少必填的字段以 MSH9</span><span class="sxs-lookup"><span data-stu-id="df8df-104">Missing required fields in MSH9</span></span>  
  
-   <span data-ttu-id="df8df-105">缺少必填的字段以 MSH12</span><span class="sxs-lookup"><span data-stu-id="df8df-105">Missing required fields in MSH12</span></span>  
  
 <span data-ttu-id="df8df-106">以下条件会导致出现非致命错误条件。</span><span class="sxs-lookup"><span data-stu-id="df8df-106">The following conditions result in a non-fatal error condition.</span></span> <span data-ttu-id="df8df-107">在此情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成 ACK，但也将挂起的确认：</span><span class="sxs-lookup"><span data-stu-id="df8df-107">In this situation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates the ACK, but also suspends the ACK:</span></span>  
  
-   <span data-ttu-id="df8df-108">缺少必填的字段在 MSH11</span><span class="sxs-lookup"><span data-stu-id="df8df-108">Missing a required field in MSH11</span></span>  
  
-   <span data-ttu-id="df8df-109">缺少 MSH10 值</span><span class="sxs-lookup"><span data-stu-id="df8df-109">Missing a MSH10 value</span></span>  
  
-   <span data-ttu-id="df8df-110">标头中的可选字段的枚举类型错误。</span><span class="sxs-lookup"><span data-stu-id="df8df-110">Enumeration type errors for optional fields in the header.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df8df-111">枚举类型错误时 MSH 15 设置为 AL 或 ER，在标头中找到[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成的状态一起提交 ACK **MSA_1 = CR**。</span><span class="sxs-lookup"><span data-stu-id="df8df-111">For enumeration type errors found in the header when MSH 15 is set to AL or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a commit ACK with the status **MSA_1=CR**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df8df-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df8df-112">See Also</span></span>  
 <span data-ttu-id="df8df-113">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="df8df-113">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="df8df-114">[ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="df8df-114">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="df8df-115">[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="df8df-115">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="df8df-116">设置发送端口用于接收确认</span><span class="sxs-lookup"><span data-stu-id="df8df-116">Setting Up a Send Port for Receiving ACKs</span></span>](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)