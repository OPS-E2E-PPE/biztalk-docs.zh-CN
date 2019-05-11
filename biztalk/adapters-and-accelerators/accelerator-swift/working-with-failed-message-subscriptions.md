---
title: 使用失败消息的订阅 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0244ea33744d592377261c8e532d981cc5d828aa
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529672"
---
# <a name="working-with-failed-message-subscriptions"></a><span data-ttu-id="762d7-102">使用失败的消息订阅</span><span class="sxs-lookup"><span data-stu-id="762d7-102">Working with Failed Message Subscriptions</span></span>
<span data-ttu-id="762d7-103">当 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]拆装器进程 （分析和验证） 一条消息，它将升级该消息的属性。</span><span class="sxs-lookup"><span data-stu-id="762d7-103">When the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] disassembler processes (parses and validates) a message, it promotes properties for that message.</span></span> <span data-ttu-id="762d7-104">如果 A4SWIFT 接收到消息的入站批处理的一部分，这些升级的属性提供的正确性和消息有效性的信息，以及与批处理相关的信息。</span><span class="sxs-lookup"><span data-stu-id="762d7-104">These promoted properties provide information about the correctness and validity of the message, as well as batch-related information if A4SWIFT received the message as part of an inbound batch.</span></span> <span data-ttu-id="762d7-105">有关这些属性的完整列表，请参阅[A4SWIFT_ \* 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="762d7-105">For a complete list of these properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
 <span data-ttu-id="762d7-106">与本机 BizTalk 拆装器，不同 A4SWIFT 拆装器不会挂起一条消息，处理会生成错误或失败时。</span><span class="sxs-lookup"><span data-stu-id="762d7-106">Unlike native BizTalk Disassemblers, the A4SWIFT disassembler does not suspend a message when processing produces errors or failures.</span></span> <span data-ttu-id="762d7-107">相反，它将失败的消息到 MessageBox 数据库发布，就像一样是有效的消息。</span><span class="sxs-lookup"><span data-stu-id="762d7-107">Instead, it publishes the failed message to the MessageBox database just as it would a valid message.</span></span> <span data-ttu-id="762d7-108">因此，失败的消息可以到 MessageBox 数据库中执行错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="762d7-108">As a result, failed messages can carry error details into the MessageBox database.</span></span> <span data-ttu-id="762d7-109">可以从 MessageBox 数据库中检索消息、 处理和修复消息，并甚至回 MessageBox 数据库中重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="762d7-109">You can retrieve the message from the MessageBox database, handle and repair the message, and even resubmit the message back into the MessageBox database.</span></span> <span data-ttu-id="762d7-110">你将无法再执行这些任务的大部分，如果消息已实际*挂起*。</span><span class="sxs-lookup"><span data-stu-id="762d7-110">You would not be able to perform most of these tasks if the message was actually *suspended*.</span></span>  
  
 <span data-ttu-id="762d7-111">您可以标识 A4SWIFT 已通过升级属性发布到 MessageBox 数据库作为失败或错误消息。</span><span class="sxs-lookup"><span data-stu-id="762d7-111">You can identify a message that A4SWIFT has published to the MessageBox database as failed or erroneous by its promoted properties.</span></span> <span data-ttu-id="762d7-112">在处理失败的消息时，SWIFT 反汇编程序填充，并将提升**A4SWIFT_Failed**属性，以及一个或多个其他的以下属性，将消息发布到 MessageBox 数据库之前：</span><span class="sxs-lookup"><span data-stu-id="762d7-112">When processing a failed message, the SWIFT disassembler populates and promotes the **A4SWIFT_Failed** property, and one or more of the other following properties, before publishing the message to the MessageBox database:</span></span>  
  
- <span data-ttu-id="762d7-113">**A4SWIFT_ParseErrors**指示分析错误 （如格式不正确的数据） 处理过程中遇到的数目。</span><span class="sxs-lookup"><span data-stu-id="762d7-113">**A4SWIFT_ParseErrors** indicates the number of parsing errors (such as malformed data) encountered during processing.</span></span>  
  
- <span data-ttu-id="762d7-114">**A4SWIFT_XmlValidationErrors**指示 XML 验证错误 （例如无效的数据或架构方面的类型不正确） 处理过程中遇到的数目。</span><span class="sxs-lookup"><span data-stu-id="762d7-114">**A4SWIFT_XmlValidationErrors** indicates the number of XML validation errors (such as invalid data or incorrect type with respect to the schema) encountered during processing.</span></span>  
  
- <span data-ttu-id="762d7-115">**A4SWIFT_BreValidationErrors**指示处理过程中遇到的业务规则引擎 (BRE) 验证错误 （如中断的 SWIFT 网络规则的数据） 数。</span><span class="sxs-lookup"><span data-stu-id="762d7-115">**A4SWIFT_BreValidationErrors** indicates the number of Business Rule Engine (BRE) validation errors (such as data that breaks a SWIFT network rule) encountered during processing.</span></span>  
  
- <span data-ttu-id="762d7-116">**A4SWIFT_Failed**是**true**时的任何 count 的上述属性值大于零，或者**false**当计数等于零。</span><span class="sxs-lookup"><span data-stu-id="762d7-116">**A4SWIFT_Failed** is **true** when the count of any the above properties is greater than zero, or **false** when the count is equal to zero.</span></span>  
  
  <span data-ttu-id="762d7-117">这些属性是 Microsoft 的所有部分。Solutions.A4SWIFT.Property 命名空间。</span><span class="sxs-lookup"><span data-stu-id="762d7-117">These properties are all part of the Microsoft .Solutions.A4SWIFT.Property namespace.</span></span> <span data-ttu-id="762d7-118">有关这些及其他升级的属性的详细信息，请参阅[A4SWIFT_ \* 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="762d7-118">For more information about these and other promoted properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
  <span data-ttu-id="762d7-119">若要捕获或检索失败的消息，您需要在其中创建筛选器表达式 （订阅） 发送端口或业务流程接收形状，包括一些，上面列出的属性作为**AND**表达式的子句。</span><span class="sxs-lookup"><span data-stu-id="762d7-119">To catch or retrieve failed messages, you need to create filter expressions (subscriptions) for send ports or orchestration receive shapes that include some of the properties listed above, as **AND** clauses of the expression.</span></span>  
  
  <span data-ttu-id="762d7-120">例如，若要订阅所有失败消息，您将添加以下子句 (作为**AND**子句是否存在其他子句):</span><span class="sxs-lookup"><span data-stu-id="762d7-120">For example, to subscribe to all failed messages, you add the following clause (as an **AND** clause if there are other clauses):</span></span>  
  
  <span data-ttu-id="762d7-121">Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **，则返回 true**</span><span class="sxs-lookup"><span data-stu-id="762d7-121">Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**</span></span>  
  
  <span data-ttu-id="762d7-122">若要仅分析失败的消息的订阅，同时添加以下子句：</span><span class="sxs-lookup"><span data-stu-id="762d7-122">To subscribe to messages with only parse failures, you add the following clauses together:</span></span>  
  
  <span data-ttu-id="762d7-123">**和**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **，则返回 true**，**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors = = 0，**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors = = 0;</span><span class="sxs-lookup"><span data-stu-id="762d7-123">**AND** Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**,**AND**Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors == 0,**AND**Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors == 0;</span></span>  
  
  <span data-ttu-id="762d7-124">相反，对于发送端口或业务流程设计为处理有效的消息，包括"**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **false**"作为其筛选器表达式中的子句。</span><span class="sxs-lookup"><span data-stu-id="762d7-124">Conversely, for send ports or orchestrations designed to handle only valid messages, include "**AND**Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **false**" as a clause in their filter expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="762d7-125">如果订阅重叠，A4SWIFT 将完成的所有订阅。</span><span class="sxs-lookup"><span data-stu-id="762d7-125">If subscriptions overlap, A4SWIFT will fulfill all subscriptions.</span></span> <span data-ttu-id="762d7-126">也就是说，如果 （发送端口或业务流程） 的多个服务有由某个特定消息的筛选器表达式，所有此类服务将收到同一消息。</span><span class="sxs-lookup"><span data-stu-id="762d7-126">That is, if more than one service (send port or orchestration) has filter expressions fulfilled by a particular message, all such services will receive the same message.</span></span> <span data-ttu-id="762d7-127">例如，如果发送端口订阅所有失败消息和业务流程订阅仅分析失败消息，这两个订阅将满足 A4SWIFT 处理某个消息时遇到分析错误时。</span><span class="sxs-lookup"><span data-stu-id="762d7-127">For example, if a send port subscribes to all failed messages and an orchestration subscribes to only messages with parse failures, both subscriptions will be satisfied when A4SWIFT encounters parse errors when processing a message.</span></span> <span data-ttu-id="762d7-128">请务必跨服务消除不需要的重叠的订阅中。</span><span class="sxs-lookup"><span data-stu-id="762d7-128">Be sure to eliminate unwanted overlaps in subscriptions across services.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="762d7-129">A4SWIFT A4SWIFT 接收和处理消息，并将该消息发布到 MessageBox 数据库中，但消息不满足任何订阅，如果将挂起的消息的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]错误，指出缺少的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="762d7-129">If A4SWIFT receives and processes a message, and publishes that message to the MessageBox database, but the message does not satisfy any subscription, A4SWIFT will suspend the message with a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] error indicating a lack of subscribers.</span></span> <span data-ttu-id="762d7-130">例如，如果订阅的所有消息的服务"A4SWIFT_Failed = = false"，但没有服务订阅消息的"A4SWIFT_Failed = = true"，则分析失败的消息或验证确实将挂起由于缺乏订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="762d7-130">For example, if you have a service subscribing to all messages "A4SWIFT_Failed == false", but no services subscribe to messages where "A4SWIFT_Failed == true", then messages that fail parsing or validation will indeed be suspended due to a lack of subscribers.</span></span> <span data-ttu-id="762d7-131">实际上，这种情况下，可模拟传统挂起失败的消息。</span><span class="sxs-lookup"><span data-stu-id="762d7-131">This scenario actually enables you to mimic traditional suspension of failed messages.</span></span> <span data-ttu-id="762d7-132">请确保订阅不希望具有挂起的所有消息。</span><span class="sxs-lookup"><span data-stu-id="762d7-132">Be sure to subscribe to all messages that you do not want to have suspended.</span></span> <span data-ttu-id="762d7-133">有关 MessageBox 数据库订阅的更多详情请参见 BizTalk Server 帮助、 发送端口，业务流程和筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="762d7-133">See BizTalk Server Help for additional details about MessageBox database subscriptions, send ports, orchestrations, and filter expressions.</span></span>  
  
 <span data-ttu-id="762d7-134">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="762d7-134">This section contains:</span></span>  
  
-   [<span data-ttu-id="762d7-135">失败的消息和 ErrorCollection 对象</span><span class="sxs-lookup"><span data-stu-id="762d7-135">Failed Messages and ErrorCollection Objects</span></span>](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)