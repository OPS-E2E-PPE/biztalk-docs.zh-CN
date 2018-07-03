---
title: 消息确认段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f771968e6d7c7f58ccd8d3e68b43aac0eb64e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968494"
---
# <a name="message-acknowledgment-segment"></a><span data-ttu-id="f48f6-102">消息确认段</span><span class="sxs-lookup"><span data-stu-id="f48f6-102">Message Acknowledgment Segment</span></span>
<span data-ttu-id="f48f6-103">确认 (ACK) 消息的消息确认 (MSA) 段标识确认正在确认哪种类型的系统发送，并指示哪些消息通知。</span><span class="sxs-lookup"><span data-stu-id="f48f6-103">The Message Acknowledgment (MSA) segment of an acknowledgment (ACK) message identifies what type of acknowledgment the system is sending, and indicates what message the ACK is acknowledging.</span></span> <span data-ttu-id="f48f6-104">它包含两个所需的段： 确认代码和消息，控制 id。</span><span class="sxs-lookup"><span data-stu-id="f48f6-104">It consists of two required segments: an acknowledgment code and a message control ID.</span></span>  

## <a name="acknowledgment-code-msa1"></a><span data-ttu-id="f48f6-105">确认代码： MSA1</span><span class="sxs-lookup"><span data-stu-id="f48f6-105">Acknowledgment Code: MSA1</span></span>  
 <span data-ttu-id="f48f6-106">下表列出了可用 MSA1 字段值，该值指示消息接收结果。</span><span class="sxs-lookup"><span data-stu-id="f48f6-106">The following table lists the available MSA1 field values indicating the result of the message receiving.</span></span>  

|<span data-ttu-id="f48f6-107">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="f48f6-107">Value</span></span>|<span data-ttu-id="f48f6-108">含义</span><span class="sxs-lookup"><span data-stu-id="f48f6-108">Meaning</span></span>|<span data-ttu-id="f48f6-109">Description</span><span class="sxs-lookup"><span data-stu-id="f48f6-109">Description</span></span>|  
|-----------|-------------|-----------------|  
|<span data-ttu-id="f48f6-110">AA</span><span class="sxs-lookup"><span data-stu-id="f48f6-110">AA</span></span>|<span data-ttu-id="f48f6-111">应用程序确认</span><span class="sxs-lookup"><span data-stu-id="f48f6-111">Application Acknowledgment</span></span>|<span data-ttu-id="f48f6-112">系统收到消息并处理它的任何问题。</span><span class="sxs-lookup"><span data-stu-id="f48f6-112">The system has received the message and processed it with no problem.</span></span>|  
|<span data-ttu-id="f48f6-113">AE</span><span class="sxs-lookup"><span data-stu-id="f48f6-113">AE</span></span>|<span data-ttu-id="f48f6-114">应用程序错误</span><span class="sxs-lookup"><span data-stu-id="f48f6-114">Application Error</span></span>|<span data-ttu-id="f48f6-115">与消息或其结构相关的处理问题出现在接收应用程序。</span><span class="sxs-lookup"><span data-stu-id="f48f6-115">A processing problem related to the message or its structure occurred at the receiving application.</span></span> <span data-ttu-id="f48f6-116">发送系统应诊断并更正问题，然后再尝试重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="f48f6-116">The sending system should diagnose and correct the problem before attempting to resend the message.</span></span>|  
|<span data-ttu-id="f48f6-117">AR</span><span class="sxs-lookup"><span data-stu-id="f48f6-117">AR</span></span>|<span data-ttu-id="f48f6-118">应用程序拒绝</span><span class="sxs-lookup"><span data-stu-id="f48f6-118">Application Reject</span></span>|<span data-ttu-id="f48f6-119">问题发生在接收位置与 MSH9 中的值 （消息类型）、 MSH11 （处理 ID） 或 MSH12 (版本 ID)、 发送系统应诊断并更正该问题后重新发送消息; 在这种情况下或在接收已对消息或其结构，在其中用例发送系统应重新发送该消息在适当的时间段，而无需更改到消息后不相关的系统出现问题。</span><span class="sxs-lookup"><span data-stu-id="f48f6-119">Either a problem occurred at the receiving location related to the value in MSH9 (message type), MSH11 (processing ID), or MSH12 (version ID), in which case the sending system should diagnose and correct the problem before resending the message; or a problem occurred at the receiving system that was unrelated to the message or its structure, in which case the sending system should resend the message after an appropriate period, without change to the message.</span></span>|  

## <a name="message-control-id-msa2"></a><span data-ttu-id="f48f6-120">消息控件 ID (MSA2)</span><span class="sxs-lookup"><span data-stu-id="f48f6-120">Message Control ID (MSA2)</span></span>  
 <span data-ttu-id="f48f6-121">MSA2 字段用于标识确认正在确认的消息。</span><span class="sxs-lookup"><span data-stu-id="f48f6-121">The MSA2 field identifies the message that the ACK is acknowledging.</span></span> <span data-ttu-id="f48f6-122">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 中 MSA2 基于确认模式生成值。</span><span class="sxs-lookup"><span data-stu-id="f48f6-122">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the value in MSA2 based upon the acknowledgment mode.</span></span> <span data-ttu-id="f48f6-123">此值允许发送和接收应用程序，以保证消息并且确认同步。</span><span class="sxs-lookup"><span data-stu-id="f48f6-123">This value enables the sending and receiving applications to keep the message and the acknowledgment synchronized.</span></span> <span data-ttu-id="f48f6-124">下表列出了 MSA2 字段的可用值。</span><span class="sxs-lookup"><span data-stu-id="f48f6-124">The following table lists the available values for the MSA2 field.</span></span>  


|            <span data-ttu-id="f48f6-125">确认模式</span><span class="sxs-lookup"><span data-stu-id="f48f6-125">Acknowledgment Mode</span></span>            |                                                           <span data-ttu-id="f48f6-126">MSA2 中的值</span><span class="sxs-lookup"><span data-stu-id="f48f6-126">Value in MSA2</span></span>                                                            |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|               <span data-ttu-id="f48f6-127">原始模式</span><span class="sxs-lookup"><span data-stu-id="f48f6-127">Original mode</span></span>               |                  <span data-ttu-id="f48f6-128">转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息</span><span class="sxs-lookup"><span data-stu-id="f48f6-128">A transposed value of the value in the MSH10 (message control ID) field of the original message</span></span>                   |
|   <span data-ttu-id="f48f6-129">增强模式： 提交确认</span><span class="sxs-lookup"><span data-stu-id="f48f6-129">Enhanced Mode: Commit Acknowledgment</span></span>    |                  <span data-ttu-id="f48f6-130">转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息</span><span class="sxs-lookup"><span data-stu-id="f48f6-130">A transposed value of the value in the MSH10 (message control ID) field of the original message</span></span>                   |
| <span data-ttu-id="f48f6-131">增强模式： 应用程序确认</span><span class="sxs-lookup"><span data-stu-id="f48f6-131">Enhanced Mode: Application Acknowledgment</span></span> | <span data-ttu-id="f48f6-132">通过生成的 GUID[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认</span><span class="sxs-lookup"><span data-stu-id="f48f6-132">A GUID generated by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] for the acknowledgment</span></span> |

## <a name="see-also"></a><span data-ttu-id="f48f6-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="f48f6-133">See Also</span></span>  
 <span data-ttu-id="f48f6-134">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="f48f6-134">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="f48f6-135">[ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="f48f6-135">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="f48f6-136">[设置用于接收 Ack 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span><span class="sxs-lookup"><span data-stu-id="f48f6-136">[Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span></span>  
 [<span data-ttu-id="f48f6-137">错误条件确认</span><span class="sxs-lookup"><span data-stu-id="f48f6-137">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)