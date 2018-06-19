---
title: 消息确认段 |Microsoft 文档
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
ms.openlocfilehash: 9547b6d8ddf3013facd94930b5d91ec42db0e5d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204933"
---
# <a name="message-acknowledgment-segment"></a><span data-ttu-id="f0191-102">消息确认段</span><span class="sxs-lookup"><span data-stu-id="f0191-102">Message Acknowledgment Segment</span></span>
<span data-ttu-id="f0191-103">确认 (ACK) 消息的消息确认 (MSA) 段标识 ACK 正在确认哪种类型的系统发送，并指示哪些消息的确认。</span><span class="sxs-lookup"><span data-stu-id="f0191-103">The Message Acknowledgment (MSA) segment of an acknowledgment (ACK) message identifies what type of acknowledgment the system is sending, and indicates what message the ACK is acknowledging.</span></span> <span data-ttu-id="f0191-104">它由两个所需的段组成： 一个确认代码和消息控制 id。</span><span class="sxs-lookup"><span data-stu-id="f0191-104">It consists of two required segments: an acknowledgment code and a message control ID.</span></span>  
  
## <a name="acknowledgment-code-msa1"></a><span data-ttu-id="f0191-105">确认代码： MSA1</span><span class="sxs-lookup"><span data-stu-id="f0191-105">Acknowledgment Code: MSA1</span></span>  
 <span data-ttu-id="f0191-106">下表列出可用 MSA1 字段值，该值指示消息接收的结果。</span><span class="sxs-lookup"><span data-stu-id="f0191-106">The following table lists the available MSA1 field values indicating the result of the message receiving.</span></span>  
  
|<span data-ttu-id="f0191-107">值</span><span class="sxs-lookup"><span data-stu-id="f0191-107">Value</span></span>|<span data-ttu-id="f0191-108">含义</span><span class="sxs-lookup"><span data-stu-id="f0191-108">Meaning</span></span>|<span data-ttu-id="f0191-109">Description</span><span class="sxs-lookup"><span data-stu-id="f0191-109">Description</span></span>|  
|-----------|-------------|-----------------|  
|<span data-ttu-id="f0191-110">AA</span><span class="sxs-lookup"><span data-stu-id="f0191-110">AA</span></span>|<span data-ttu-id="f0191-111">应用程序确认</span><span class="sxs-lookup"><span data-stu-id="f0191-111">Application Acknowledgment</span></span>|<span data-ttu-id="f0191-112">系统收到消息并处理它与任何问题。</span><span class="sxs-lookup"><span data-stu-id="f0191-112">The system has received the message and processed it with no problem.</span></span>|  
|<span data-ttu-id="f0191-113">要从中</span><span class="sxs-lookup"><span data-stu-id="f0191-113">AE</span></span>|<span data-ttu-id="f0191-114">应用程序错误</span><span class="sxs-lookup"><span data-stu-id="f0191-114">Application Error</span></span>|<span data-ttu-id="f0191-115">处理问题相关的消息或其结构发生了接收应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0191-115">A processing problem related to the message or its structure occurred at the receiving application.</span></span> <span data-ttu-id="f0191-116">发送系统应诊断并更正该问题后尝试重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="f0191-116">The sending system should diagnose and correct the problem before attempting to resend the message.</span></span>|  
|<span data-ttu-id="f0191-117">AR</span><span class="sxs-lookup"><span data-stu-id="f0191-117">AR</span></span>|<span data-ttu-id="f0191-118">应用程序拒绝</span><span class="sxs-lookup"><span data-stu-id="f0191-118">Application Reject</span></span>|<span data-ttu-id="f0191-119">问题发生在与 MSH9 中的值相关的接收位置 （消息类型），MSH11 （处理 ID），或 MSH12 (版本 ID)，在这种情况下发送系统应诊断并更正该问题后重新发送消息;或接收已与消息或其结构，在其中情况下，发送系统应重新发送消息在适当的段，且不会更改消息后不相关的系统出现问题。</span><span class="sxs-lookup"><span data-stu-id="f0191-119">Either a problem occurred at the receiving location related to the value in MSH9 (message type), MSH11 (processing ID), or MSH12 (version ID), in which case the sending system should diagnose and correct the problem before resending the message; or a problem occurred at the receiving system that was unrelated to the message or its structure, in which case the sending system should resend the message after an appropriate period, without change to the message.</span></span>|  
  
## <a name="message-control-id-msa2"></a><span data-ttu-id="f0191-120">消息控件 ID (MSA2)</span><span class="sxs-lookup"><span data-stu-id="f0191-120">Message Control ID (MSA2)</span></span>  
 <span data-ttu-id="f0191-121">MSA2 字段标识 ACK 正在确认的消息。</span><span class="sxs-lookup"><span data-stu-id="f0191-121">The MSA2 field identifies the message that the ACK is acknowledging.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="f0191-122">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 会在 MSA2 基于确认模式生成值。</span><span class="sxs-lookup"><span data-stu-id="f0191-122"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the value in MSA2 based upon the acknowledgment mode.</span></span> <span data-ttu-id="f0191-123">此值使发送和接收应用程序在以保证消息并且该确认同步。</span><span class="sxs-lookup"><span data-stu-id="f0191-123">This value enables the sending and receiving applications to keep the message and the acknowledgment synchronized.</span></span> <span data-ttu-id="f0191-124">下表列出 MSA2 字段的可用值。</span><span class="sxs-lookup"><span data-stu-id="f0191-124">The following table lists the available values for the MSA2 field.</span></span>  
  
|<span data-ttu-id="f0191-125">确认模式</span><span class="sxs-lookup"><span data-stu-id="f0191-125">Acknowledgment Mode</span></span>|<span data-ttu-id="f0191-126">MSA2 中的值</span><span class="sxs-lookup"><span data-stu-id="f0191-126">Value in MSA2</span></span>|  
|-------------------------|-------------------|  
|<span data-ttu-id="f0191-127">原始模式</span><span class="sxs-lookup"><span data-stu-id="f0191-127">Original mode</span></span>|<span data-ttu-id="f0191-128">转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息</span><span class="sxs-lookup"><span data-stu-id="f0191-128">A transposed value of the value in the MSH10 (message control ID) field of the original message</span></span>|  
|<span data-ttu-id="f0191-129">增强的模式： 提交确认</span><span class="sxs-lookup"><span data-stu-id="f0191-129">Enhanced Mode: Commit Acknowledgment</span></span>|<span data-ttu-id="f0191-130">转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息</span><span class="sxs-lookup"><span data-stu-id="f0191-130">A transposed value of the value in the MSH10 (message control ID) field of the original message</span></span>|  
|<span data-ttu-id="f0191-131">增强的模式： 应用程序确认</span><span class="sxs-lookup"><span data-stu-id="f0191-131">Enhanced Mode: Application Acknowledgment</span></span>|<span data-ttu-id="f0191-132">生成的 GUID[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]的确认</span><span class="sxs-lookup"><span data-stu-id="f0191-132">A GUID generated by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] for the acknowledgment</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0191-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0191-133">See Also</span></span>  
 <span data-ttu-id="f0191-134">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="f0191-134">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="f0191-135">[ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="f0191-135">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="f0191-136">[设置发送端口用于接收确认](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span><span class="sxs-lookup"><span data-stu-id="f0191-136">[Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span></span>  
 [<span data-ttu-id="f0191-137">确认错误条件</span><span class="sxs-lookup"><span data-stu-id="f0191-137">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)