---
title: "确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c519ec4649ee1fbcfbc51edb7e3e8fe6ba6b5871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments"></a><span data-ttu-id="70f3c-102">鸣谢</span><span class="sxs-lookup"><span data-stu-id="70f3c-102">Acknowledgments</span></span>
<span data-ttu-id="70f3c-103">在方级别使用配置 HL7 确认[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="70f3c-103">You configure HL7 acknowledgments at the party level using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Configuration Explorer.</span></span> <span data-ttu-id="70f3c-104">确认将应用于通过接收位置 （可能是 MLLP 适配器） 和 HL7 HL7 消息发送方 2.X 接收管道。</span><span class="sxs-lookup"><span data-stu-id="70f3c-104">Acknowledgments apply to parties that are sending HL7 messages through a receive location (possibly the MLLP adapter) and the HL7 2.X receive pipeline.</span></span> <span data-ttu-id="70f3c-105">当一条消息完成分析和验证，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以创建一条确认消息，其中包含验证过程的结果 （成功或错误）。</span><span class="sxs-lookup"><span data-stu-id="70f3c-105">When a message completes parsing and validation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can create an acknowledgment message that contains the result (success or error) of the validation process.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="70f3c-106">可以在两种方式之一返回确认消息。</span><span class="sxs-lookup"><span data-stu-id="70f3c-106"> can return acknowledgment messages in one of two ways.</span></span> <span data-ttu-id="70f3c-107">如果原始发送方提交通过双向原始消息接收端口配置，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]返回通过该原始端口位置的确认消息。</span><span class="sxs-lookup"><span data-stu-id="70f3c-107">If the original sending party submitted the original message through a two-way receive port configuration, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] returns the acknowledgment message through that original port location.</span></span> <span data-ttu-id="70f3c-108">如果原始发送端口提交原始消息通过单向接收端口，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将确认消息提交到 MessageBox 数据库并将其使用订阅模型路由。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f3c-108">If the original sending port submitted the original message through a one-way receive port, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] submits the acknowledgment message into the MessageBox database and routes it using the subscription model.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span></span> <span data-ttu-id="70f3c-109">用于接收消息处理根据 HL7 消息 (MSH 3.1) 发送应用程序域内的值自动执行当事方关联。</span><span class="sxs-lookup"><span data-stu-id="70f3c-109">performs party association for receive message processing automatically based on the value within the sending application field of the HL7 message (MSH 3.1).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f3c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70f3c-110">See Also</span></span>  
 [<span data-ttu-id="70f3c-111">消息流</span><span class="sxs-lookup"><span data-stu-id="70f3c-111">Message Flow</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)