---
title: "触发事件和消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- health care organizations, HL7 messages
- trigger events
- messages, trigger events
- messages, about messages
ms.assetid: e93b397c-8cbe-4589-aa88-e474d7722174
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 188d7f1e09ae3f96c953c6a83bbad42ccdce3643
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="trigger-events-and-messages"></a><span data-ttu-id="9ed8f-102">触发事件和消息</span><span class="sxs-lookup"><span data-stu-id="9ed8f-102">Trigger Events and Messages</span></span>
<span data-ttu-id="9ed8f-103">在数字卫生保健系统中，应用程序由于实际事件，如放置实验室顺序或药品顺序创建 HL7 消息。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-103">In a digital health care system, applications create HL7 messages because of a real-world event, such as the placing of a laboratory order or drug order.</span></span> <span data-ttu-id="9ed8f-104">HL7 组织已写 HL7 标准基于卫生保健将现实生活中的事件创建对数据应用程序，之间流动，即使这些应用程序跨异类系统的需求的假设。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-104">The HL7 organization has written the HL7 standard based on the assumption that an event in the real world of health care creates the need for data to flow among applications, even when these applications span heterogeneous systems.</span></span> <span data-ttu-id="9ed8f-105">HL7 标准调用此实际事件*触发器事件*。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-105">The HL7 standard calls this real-world event a *trigger event*.</span></span> <span data-ttu-id="9ed8f-106">自动的系统必须系统地识别触发器事件。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-106">An automated system must systematically recognize the trigger event.</span></span>  
  
 <span data-ttu-id="9ed8f-107">若要展开此概念，请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-107">To expand this concept, consider the following scenario.</span></span> <span data-ttu-id="9ed8f-108">在一家医院到达时，一个患者在医院使用患者管理软件应用程序中注册。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-108">On arrival at a hospital, a patient registers in a hospital using a patient administration software application.</span></span> <span data-ttu-id="9ed8f-109">上提交的患者的记录，该应用程序需要通知其他医院应用程序 （例如会计、 实验室中，依次类推） 有关的患者的注册。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-109">On committing the patient records, the application needs to inform other hospital applications (such as accounting, labs, and so on) about the registration of the patient.</span></span> <span data-ttu-id="9ed8f-110">在应用程序之间共享此信息是必需的以便使用这些应用程序的实体可以提供与所需的服务将患者。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-110">Sharing this information across applications is necessary so that the entities that use those applications can provide the patient with the required services.</span></span> <span data-ttu-id="9ed8f-111">注册一个患者的行为是一种触发器事件。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-111">The act of registering a patient is a type of trigger event.</span></span> <span data-ttu-id="9ed8f-112">Web 应用程序通常通过创建包含患者记录的数据的 HL7 消息来创建此触发器事件。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-112">A Web application typically creates this trigger event by creating an HL7 message containing the data for the patient record.</span></span>  
  
 <span data-ttu-id="9ed8f-113">在创建一个或多个消息触发操作的应用程序处理的消息中的操作会导致触发事件。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-113">Trigger events always result in the creation of one or more messages that trigger an action in the application that processes the message.</span></span> <span data-ttu-id="9ed8f-114">触发事件时，才在 IT 人员有嵌入其中的部署方案中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 医院业务线应用程序中。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-114">Trigger events are relevant in deployment scenarios where IT personnel have embedded [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) within the hospital line-of-business application.</span></span> <span data-ttu-id="9ed8f-115">即使在这种部署方案，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不需要注意的触发器事件，仅触发器事件生成的消息。</span><span class="sxs-lookup"><span data-stu-id="9ed8f-115">Even in such deployment scenarios, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not need to be aware of the trigger event, only the messages that the trigger event generates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed8f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ed8f-116">See Also</span></span>  
 <span data-ttu-id="9ed8f-117">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9ed8f-117">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="9ed8f-118">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="9ed8f-118">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="9ed8f-119">[使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="9ed8f-119">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 [<span data-ttu-id="9ed8f-120">HL7 消息传送</span><span class="sxs-lookup"><span data-stu-id="9ed8f-120">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)