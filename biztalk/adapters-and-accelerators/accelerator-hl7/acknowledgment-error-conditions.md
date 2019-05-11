---
title: 错误条件确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae28a26d62ec18f6cfb81db55442b8e440b5a93c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247715"
---
# <a name="acknowledgment-error-conditions"></a><span data-ttu-id="97177-102">错误条件确认</span><span class="sxs-lookup"><span data-stu-id="97177-102">Acknowledgment Error Conditions</span></span>
<span data-ttu-id="97177-103">以下条件将导致严重的错误条件时 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 是处理确认 (ACK) 消息：</span><span class="sxs-lookup"><span data-stu-id="97177-103">The following conditions will result in a fatal error condition when Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) is processing acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="97177-104">缺少必填的字段以 MSH9</span><span class="sxs-lookup"><span data-stu-id="97177-104">Missing required fields in MSH9</span></span>  
  
- <span data-ttu-id="97177-105">缺少必填的字段以 MSH12</span><span class="sxs-lookup"><span data-stu-id="97177-105">Missing required fields in MSH12</span></span>  
  
  <span data-ttu-id="97177-106">以下条件会导致出现非致命错误条件。</span><span class="sxs-lookup"><span data-stu-id="97177-106">The following conditions result in a non-fatal error condition.</span></span> <span data-ttu-id="97177-107">在此情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成确认，但也将挂起的确认：</span><span class="sxs-lookup"><span data-stu-id="97177-107">In this situation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates the ACK, but also suspends the ACK:</span></span>  
  
- <span data-ttu-id="97177-108">MSH11 中的所需的字段丢失</span><span class="sxs-lookup"><span data-stu-id="97177-108">Missing a required field in MSH11</span></span>  
  
- <span data-ttu-id="97177-109">缺少 MSH10 值</span><span class="sxs-lookup"><span data-stu-id="97177-109">Missing a MSH10 value</span></span>  
  
- <span data-ttu-id="97177-110">标头中的可选字段的枚举类型错误。</span><span class="sxs-lookup"><span data-stu-id="97177-110">Enumeration type errors for optional fields in the header.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97177-111">当 MSH 15 设置为 AL 或 ER，标头中找到的枚举类型错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成的状态的提交确认**MSA_1 = CR**。</span><span class="sxs-lookup"><span data-stu-id="97177-111">For enumeration type errors found in the header when MSH 15 is set to AL or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a commit ACK with the status **MSA_1=CR**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97177-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="97177-112">See Also</span></span>  
 <span data-ttu-id="97177-113">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="97177-113">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="97177-114">[ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="97177-114">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="97177-115">[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="97177-115">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="97177-116">设置用于接收 ACK 的发送端口</span><span class="sxs-lookup"><span data-stu-id="97177-116">Setting Up a Send Port for Receiving ACKs</span></span>](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)