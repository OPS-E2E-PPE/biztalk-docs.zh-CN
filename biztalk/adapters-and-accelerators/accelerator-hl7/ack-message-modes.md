---
title: ACK 消息模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66636704ccbe63be2a47fb56dd43f797174fc89a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247472"
---
# <a name="ack-message-modes"></a><span data-ttu-id="d1174-102">ACK 消息模式</span><span class="sxs-lookup"><span data-stu-id="d1174-102">ACK Message Modes</span></span>
<span data-ttu-id="d1174-103">对于确认 (ACK) 消息，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 确定的确认模式和要用于填充你想要生成的确认 MSH15 和 MSH16 字段值。</span><span class="sxs-lookup"><span data-stu-id="d1174-103">For acknowledgment (ACK) messages, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determines the acknowledgment mode and values to use for populating MSH15 and MSH16 fields of the ACK you want to generate.</span></span> <span data-ttu-id="d1174-104">这些值是在贸易合作伙伴管理 (TPM) 配置中存在。</span><span class="sxs-lookup"><span data-stu-id="d1174-104">These values are present in the Trading Partner Management (TPM) configuration.</span></span> <span data-ttu-id="d1174-105">下面是可能值为 ACK 模式：</span><span class="sxs-lookup"><span data-stu-id="d1174-105">The following values are possible for ACK mode:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1174-106">在以下列表中，HL7 规范强制项 1 至 3，并且它们包含 MSH15 和 MSH16 值。</span><span class="sxs-lookup"><span data-stu-id="d1174-106">In the following list, the HL7 specification mandates items 1 through 3 and that they contain MSH15 and MSH16 values.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d1174-107">定义项 4，以表示不应生成确认。</span><span class="sxs-lookup"><span data-stu-id="d1174-107">defines item 4 to signify that an acknowledgment should not be generated.</span></span>  
  
1. <span data-ttu-id="d1174-108">原始-一个 ACK 验证标头和正文后发送。</span><span class="sxs-lookup"><span data-stu-id="d1174-108">Original - One ACK sent after validating the header and body.</span></span> <span data-ttu-id="d1174-109">此模式都涉及到架构验证。</span><span class="sxs-lookup"><span data-stu-id="d1174-109">This mode involves schema validation.</span></span>  
  
2. <span data-ttu-id="d1174-110">增强的两个发送的确认消息：</span><span class="sxs-lookup"><span data-stu-id="d1174-110">Enhanced - Two ACK messages sent:</span></span>  
  
   -   <span data-ttu-id="d1174-111">接受确认 – 接收系统标头的验证后会发送此类型的确认。</span><span class="sxs-lookup"><span data-stu-id="d1174-111">Accept ACK – The receiving system sends this type of ACK after validation of the header.</span></span> <span data-ttu-id="d1174-112">此确认向发出信号，起始应用程序的消息是提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="d1174-112">This ACK signals to the initiating application that the message is committed to the database.</span></span>  
  
   -   <span data-ttu-id="d1174-113">应用程序确认接收系统完成消息验证，包括标头和正文后会发送此类型的确认。</span><span class="sxs-lookup"><span data-stu-id="d1174-113">Application ACK- The receiving system sends this type of ACK after complete message validation, including the header and the body.</span></span>  
  
3. <span data-ttu-id="d1174-114">延迟-发送两条确认消息。</span><span class="sxs-lookup"><span data-stu-id="d1174-114">Deferred - Two ACK messages sent.</span></span>  
  
   - <span data-ttu-id="d1174-115">原始模式：接收系统验证标头和正文后会发送此类型的确认。</span><span class="sxs-lookup"><span data-stu-id="d1174-115">Original Mode: The receiving system sends this type of ACK after validation of the header and body.</span></span> <span data-ttu-id="d1174-116">此模式都涉及到架构验证。</span><span class="sxs-lookup"><span data-stu-id="d1174-116">This mode involves schema validation.</span></span>  
  
   - <span data-ttu-id="d1174-117">延迟模式下：业务线应用程序在处理它之后确认消息。</span><span class="sxs-lookup"><span data-stu-id="d1174-117">Deferred Mode: The line-of-business application acknowledges the message after processing it.</span></span> <span data-ttu-id="d1174-118">应用程序提供对延迟的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，它将它作为独立的消息处理，并将其传送到目标。</span><span class="sxs-lookup"><span data-stu-id="d1174-118">The application delivers the deferred message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], which process it as a stand-alone message and delivers it to the destination.</span></span>  
  
4. <span data-ttu-id="d1174-119">静态-在成功或失败时发送的确认。</span><span class="sxs-lookup"><span data-stu-id="d1174-119">Static - An on success or on failure ACK sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1174-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1174-120">See Also</span></span>  
 <span data-ttu-id="d1174-121">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="d1174-121">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="d1174-122">[编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="d1174-122">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 <span data-ttu-id="d1174-123">[ACK 进程模型](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span><span class="sxs-lookup"><span data-stu-id="d1174-123">[ACK Process Model](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span></span>  
 [<span data-ttu-id="d1174-124">静态确认</span><span class="sxs-lookup"><span data-stu-id="d1174-124">Static Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)