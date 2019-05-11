---
title: 验证消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, acknowledgements
- messages, acknowledgements
- acknowledgements, validating
- validating, messages
- acknowledgements, messages
- messages, validating
ms.assetid: 7dba0f40-5e19-4598-82cb-22c71e9536c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fde2a092499f3e5c4c90d16af4043b532131de47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286335"
---
# <a name="validating-messages"></a><span data-ttu-id="5f33c-102">验证消息</span><span class="sxs-lookup"><span data-stu-id="5f33c-102">Validating Messages</span></span>
<span data-ttu-id="5f33c-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持从应用程序的入站消息发送确认 (ACK) 或贸易合作伙伴可能需要转换为 HL7 HL7 XML 回执的窗体中编码的确认消息。</span><span class="sxs-lookup"><span data-stu-id="5f33c-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports sending acknowledgments (ACK) for inbound messages from an application or trading partner in the form of an HL7 XML receipt that might need conversion to an HL7 encoded ACK message.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="5f33c-104">通常将生成回执后它会检查根据相关入站 （贸易合作伙伴格式） 文档规范对入站的消息。</span><span class="sxs-lookup"><span data-stu-id="5f33c-104">typically generates a receipt after it checks the inbound message against the relevant inbound (trading-partner format) document specification.</span></span> <span data-ttu-id="5f33c-105">当所有段都通过验证，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]返回回执，表明对应用程序接受。</span><span class="sxs-lookup"><span data-stu-id="5f33c-105">When all the segments pass validation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] returns a receipt that indicates acceptance to the application.</span></span> <span data-ttu-id="5f33c-106">否则为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成回执，该值指示错误或失败/拒绝。</span><span class="sxs-lookup"><span data-stu-id="5f33c-106">Otherwise, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a receipt indicating error or failure/reject.</span></span>  
  
 <span data-ttu-id="5f33c-107">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认传输报告针对 HL7 标准语法和示意性错误。</span><span class="sxs-lookup"><span data-stu-id="5f33c-107">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK transmission reports syntactical and schematic errors against the HL7 standard.</span></span> <span data-ttu-id="5f33c-108">如果验证失败，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将文档放在挂起的消息队列，并返回详细说明，拒绝的回执。</span><span class="sxs-lookup"><span data-stu-id="5f33c-108">If the validation fails, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] places the document in the suspended message queue and returns a receipt detailing the rejection.</span></span> <span data-ttu-id="5f33c-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器执行涉及到检查数据类型、 语法和架构验证的验证。</span><span class="sxs-lookup"><span data-stu-id="5f33c-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser performs validation that involves checking data types, syntax, and the schema validation.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="5f33c-110">在分析中的位置详细信息以及回执记录出现的任何示意性错误。</span><span class="sxs-lookup"><span data-stu-id="5f33c-110">records any schematic errors that occur in parsing in the receipt along with the location details.</span></span>  
  
 <span data-ttu-id="5f33c-111">在配置时，您需要创建[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用确认进行响应所需项目</span><span class="sxs-lookup"><span data-stu-id="5f33c-111">At configure time, you need to create the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artifacts required for responding with an ACK.</span></span> <span data-ttu-id="5f33c-112">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器创建 HL7 规范确认 XML 实例。</span><span class="sxs-lookup"><span data-stu-id="5f33c-112">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser creates the HL7 canonical ACK XML instance.</span></span> <span data-ttu-id="5f33c-113">BizTalk 将此转换为相应的 BizTalk 映射中的所需的版本格式，并验证目标格式。</span><span class="sxs-lookup"><span data-stu-id="5f33c-113">BizTalk converts this to the required version format in an appropriate BizTalk map and validates the destination format.</span></span> <span data-ttu-id="5f33c-114">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序然后将该消息转换为 HL7 编码实例。</span><span class="sxs-lookup"><span data-stu-id="5f33c-114">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer then converts the message into an HL7-encoded instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f33c-115">如果入站消息的分隔符之间没有冲突并且中指定的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成确认消息，它使用相同的入站消息的分隔符并替代的配置设置。</span><span class="sxs-lookup"><span data-stu-id="5f33c-115">If there is a conflict between the delimiters of an inbound message and those specified in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will generate an ACK message that uses the same delimiters of the inbound message and overrides the configuration settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f33c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f33c-116">See Also</span></span>  
 <span data-ttu-id="5f33c-117">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="5f33c-117">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="5f33c-118">[编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="5f33c-118">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 [<span data-ttu-id="5f33c-119">ACK 消息模式</span><span class="sxs-lookup"><span data-stu-id="5f33c-119">ACK Message Modes</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)