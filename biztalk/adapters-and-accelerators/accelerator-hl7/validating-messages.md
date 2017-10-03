---
title: "验证消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, acknowledgements
- messages, acknowledgements
- acknowledgements, validating
- validating, messages
- acknowledgements, messages
- messages, validating
ms.assetid: 7dba0f40-5e19-4598-82cb-22c71e9536c6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1edaffcab50d6a8af508cb16c9eede39c5ddb952
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-messages"></a><span data-ttu-id="bb434-102">验证消息</span><span class="sxs-lookup"><span data-stu-id="bb434-102">Validating Messages</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="bb434-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持从应用程序的入站消息发送确认 (ACK) 或贸易合作伙伴可能需要转换为 HL7 HL7 XML 回执形式 ACK 消息编码。</span><span class="sxs-lookup"><span data-stu-id="bb434-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports sending acknowledgments (ACK) for inbound messages from an application or trading partner in the form of an HL7 XML receipt that might need conversion to an HL7 encoded ACK message.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bb434-104">它签入相关入站 （贸易合作伙伴格式） 文档规范针对入站的消息后，通常会生成回执。</span><span class="sxs-lookup"><span data-stu-id="bb434-104"> typically generates a receipt after it checks the inbound message against the relevant inbound (trading-partner format) document specification.</span></span> <span data-ttu-id="bb434-105">当所有段都通过验证，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]返回回执，该值指示对应用程序接受。</span><span class="sxs-lookup"><span data-stu-id="bb434-105">When all the segments pass validation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] returns a receipt that indicates acceptance to the application.</span></span> <span data-ttu-id="bb434-106">否则为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成，该值指示错误或失败/拒绝回执。</span><span class="sxs-lookup"><span data-stu-id="bb434-106">Otherwise, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a receipt indicating error or failure/reject.</span></span>  
  
 <span data-ttu-id="bb434-107">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK 传输报告针对 HL7 标准的语法和示意性错误。</span><span class="sxs-lookup"><span data-stu-id="bb434-107">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK transmission reports syntactical and schematic errors against the HL7 standard.</span></span> <span data-ttu-id="bb434-108">如果验证失败，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将挂起的消息队列中的文档并返回详细说明拒绝回执。</span><span class="sxs-lookup"><span data-stu-id="bb434-108">If the validation fails, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] places the document in the suspended message queue and returns a receipt detailing the rejection.</span></span> <span data-ttu-id="bb434-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器执行包括检查数据类型、 语法和架构验证的验证。</span><span class="sxs-lookup"><span data-stu-id="bb434-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser performs validation that involves checking data types, syntax, and the schema validation.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bb434-110">在分析中的位置的详细信息以及回执记录出现的任何示意性错误。</span><span class="sxs-lookup"><span data-stu-id="bb434-110"> records any schematic errors that occur in parsing in the receipt along with the location details.</span></span>  
  
 <span data-ttu-id="bb434-111">在配置时，你需要创建[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用确认进行响应所需项目</span><span class="sxs-lookup"><span data-stu-id="bb434-111">At configure time, you need to create the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artifacts required for responding with an ACK.</span></span> <span data-ttu-id="bb434-112">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器将创建 HL7 规范 ACK XML 实例。</span><span class="sxs-lookup"><span data-stu-id="bb434-112">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser creates the HL7 canonical ACK XML instance.</span></span> <span data-ttu-id="bb434-113">BizTalk 将此转换为适当的 BizTalk 映射中的所需的版本格式，并验证目标格式。</span><span class="sxs-lookup"><span data-stu-id="bb434-113">BizTalk converts this to the required version format in an appropriate BizTalk map and validates the destination format.</span></span> <span data-ttu-id="bb434-114">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序然后将消息转换为 HL7 编码实例。</span><span class="sxs-lookup"><span data-stu-id="bb434-114">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer then converts the message into an HL7-encoded instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb434-115">如果的入站消息分隔符之间存在冲突，并且在指定的那些[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成一条确认消息，使用相同的分隔符的入站消息和替代的配置设置。</span><span class="sxs-lookup"><span data-stu-id="bb434-115">If there is a conflict between the delimiters of an inbound message and those specified in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will generate an ACK message that uses the same delimiters of the inbound message and overrides the configuration settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb434-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb434-116">See Also</span></span>  
 <span data-ttu-id="bb434-117">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="bb434-117">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="bb434-118">[编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="bb434-118">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 [<span data-ttu-id="bb434-119">ACK 消息模式</span><span class="sxs-lookup"><span data-stu-id="bb434-119">ACK Message Modes</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)