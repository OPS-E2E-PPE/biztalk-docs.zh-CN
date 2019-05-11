---
title: 消息类型和事件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message events
- HL7, message types
- message types
- messages, message types
ms.assetid: d53d51d0-216d-472b-97b7-8a96b8013510
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 143223d0ed0f03d6eaa66141ea052ed701638e56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303651"
---
# <a name="message-types-and-events"></a><span data-ttu-id="584bf-102">消息类型和事件</span><span class="sxs-lookup"><span data-stu-id="584bf-102">Message Types and Events</span></span>
<span data-ttu-id="584bf-103">HL7 标准已分组到一起作为实际事件的特定分组相关的消息*消息类型*ADT。</span><span class="sxs-lookup"><span data-stu-id="584bf-103">The HL7 standard has grouped messages that relate to a particular grouping of real-world events together as *message type* ADT.</span></span> <span data-ttu-id="584bf-104">这些消息涉及到触发器事件，如患者的管理。</span><span class="sxs-lookup"><span data-stu-id="584bf-104">These messages involve trigger events, such as patient administration.</span></span> <span data-ttu-id="584bf-105">版本 2.4 的 HL7 标准定义了超过 100 个消息类型，其中每个 HL7 组织分配有唯一的三个字符消息类型代码。</span><span class="sxs-lookup"><span data-stu-id="584bf-105">Version 2.4 of the HL7 standard defines more than 100 message types, each of which the HL7 organization has assigned a unique three-character message type code.</span></span> <span data-ttu-id="584bf-106">HL7 标准的版本不断演进，如 HL7 组织已添加新的消息类型来提供新的功能。</span><span class="sxs-lookup"><span data-stu-id="584bf-106">As versions of the HL7 standard have evolved, the HL7 organization has added new message types to provide new capabilities.</span></span>  
  
 <span data-ttu-id="584bf-107">所有消息类型都包含的消息事件，也称为*事件*。</span><span class="sxs-lookup"><span data-stu-id="584bf-107">All message types contain message events, also called *events*.</span></span> <span data-ttu-id="584bf-108">您可以看作是将事件消息中的特定消息类型分组的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="584bf-108">You can think of an event as a unique type of message grouped within a particular message type.</span></span> <span data-ttu-id="584bf-109">例如，管理员/访问通知 （消息事件 A01） 和放电装置/结束访问 （消息事件 A03） 是唯一患者管理消息类型 (ADT) 包含的消息。</span><span class="sxs-lookup"><span data-stu-id="584bf-109">For example, the Admin/Visit Notification (message event A01) and Discharge/End Visit (message event A03) are unique messages contained by the Patient Administration message type (ADT).</span></span> <span data-ttu-id="584bf-110">HL7 组织分配的每个消息事件的三个字符的唯一事件代码。</span><span class="sxs-lookup"><span data-stu-id="584bf-110">The HL7 organization has assigned each message event a unique three-character event code.</span></span>  
  
 <span data-ttu-id="584bf-111">只有一个消息类型可以包含特定的消息事件。</span><span class="sxs-lookup"><span data-stu-id="584bf-111">Only one message type can contain a particular message event.</span></span> <span data-ttu-id="584bf-112">消息类型可以包含多个消息事件。</span><span class="sxs-lookup"><span data-stu-id="584bf-112">Message types can contain multiple message events.</span></span> <span data-ttu-id="584bf-113">但是，特定的消息事件的结构而异的 HL7 标准版本之间。</span><span class="sxs-lookup"><span data-stu-id="584bf-113">However, the structure of a particular message event can vary between versions of the HL7 standard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584bf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="584bf-114">See Also</span></span>  
 <span data-ttu-id="584bf-115">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="584bf-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="584bf-116">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="584bf-116">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="584bf-117">[使用 HL7 2.xml 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="584bf-117">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="584bf-118">[触发器事件和消息](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span><span class="sxs-lookup"><span data-stu-id="584bf-118">[Trigger Events and Messages](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span></span>  
 [<span data-ttu-id="584bf-119">HL7 消息传送</span><span class="sxs-lookup"><span data-stu-id="584bf-119">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)