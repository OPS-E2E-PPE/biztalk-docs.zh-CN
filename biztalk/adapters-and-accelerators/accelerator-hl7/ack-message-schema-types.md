---
title: ACK 消息架构类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923cd9122f1b0d322f5a12d3be38f660a67d054e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247568"
---
# <a name="ack-message-schema-types"></a><span data-ttu-id="d9523-102">ACK 消息架构类型</span><span class="sxs-lookup"><span data-stu-id="d9523-102">ACK Message Schema Types</span></span>
<span data-ttu-id="d9523-103">确认消息架构有两种形式：</span><span class="sxs-lookup"><span data-stu-id="d9523-103">Acknowledgment message schemas come in two forms:</span></span>  

- <span data-ttu-id="d9523-104">**常规确认 (ACK)**。</span><span class="sxs-lookup"><span data-stu-id="d9523-104">**General acknowledgment (ACK)**.</span></span> <span data-ttu-id="d9523-105">如果应用程序未定义的特殊业务线应用程序级别的确认消息，或者如果发生了使该列不能应用程序处理的错误，可以使用常规确认 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="d9523-105">You can use a general acknowledgment (ACK) where the application does not define a special line-of-business application level acknowledgment message or where an error occurred that precludes application processing.</span></span> <span data-ttu-id="d9523-106">此外可以使用它对于接受级别的确认。</span><span class="sxs-lookup"><span data-stu-id="d9523-106">You can also use it for accept level acknowledgments.</span></span> <span data-ttu-id="d9523-107">下表列出了 ACK 消息结构。</span><span class="sxs-lookup"><span data-stu-id="d9523-107">The following table lists the ACK message structure.</span></span>  


  | <span data-ttu-id="d9523-108">ACK ^ 各不相同 ^ ACK</span><span class="sxs-lookup"><span data-stu-id="d9523-108">ACK^varies^ACK</span></span> | <span data-ttu-id="d9523-109">常规确认</span><span class="sxs-lookup"><span data-stu-id="d9523-109">General acknowledgment</span></span> | <span data-ttu-id="d9523-110">一章</span><span class="sxs-lookup"><span data-stu-id="d9523-110">Chapter</span></span> |
  |----------------|------------------------|---------|
  |      <span data-ttu-id="d9523-111">MSH</span><span class="sxs-lookup"><span data-stu-id="d9523-111">MSH</span></span>       |     <span data-ttu-id="d9523-112">消息标头</span><span class="sxs-lookup"><span data-stu-id="d9523-112">Message Header</span></span>     |    <span data-ttu-id="d9523-113">2</span><span class="sxs-lookup"><span data-stu-id="d9523-113">2</span></span>    |
  |      <span data-ttu-id="d9523-114">MSA</span><span class="sxs-lookup"><span data-stu-id="d9523-114">MSA</span></span>       | <span data-ttu-id="d9523-115">消息确认</span><span class="sxs-lookup"><span data-stu-id="d9523-115">Message Acknowledgment</span></span> |    <span data-ttu-id="d9523-116">2</span><span class="sxs-lookup"><span data-stu-id="d9523-116">2</span></span>    |
  |    <span data-ttu-id="d9523-117">[ ERR ]</span><span class="sxs-lookup"><span data-stu-id="d9523-117">[ ERR ]</span></span>     |         <span data-ttu-id="d9523-118">错误</span><span class="sxs-lookup"><span data-stu-id="d9523-118">Error</span></span>          |    <span data-ttu-id="d9523-119">2</span><span class="sxs-lookup"><span data-stu-id="d9523-119">2</span></span>    |


- <span data-ttu-id="d9523-120">**延迟确认 (MCF)**。</span><span class="sxs-lookup"><span data-stu-id="d9523-120">**Delayed acknowledgment (MCF)**.</span></span> <span data-ttu-id="d9523-121">此消息仅存在与 HL7 2.1 版的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="d9523-121">This message exists only for backward compatibility with HL7 Version 2.1.</span></span> <span data-ttu-id="d9523-122">您将其用作创建泛型窗体，异步应用程序级别确认，MCF 消息的协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9523-122">You use it as part of the protocol that creates a generic form of an asynchronous application level acknowledgment, the MCF message.</span></span> <span data-ttu-id="d9523-123">下表列出了 MCF 消息结构。</span><span class="sxs-lookup"><span data-stu-id="d9523-123">The following table lists the MCF message structure.</span></span>  

  |<span data-ttu-id="d9523-124">MCF ^ 各不相同 ^ ACK</span><span class="sxs-lookup"><span data-stu-id="d9523-124">MCF^varies^ACK</span></span>|<span data-ttu-id="d9523-125">延迟的确认</span><span class="sxs-lookup"><span data-stu-id="d9523-125">Delayed Acknowledgment</span></span>|<span data-ttu-id="d9523-126">一章</span><span class="sxs-lookup"><span data-stu-id="d9523-126">Chapter</span></span>|  
  |--------------------|----------------------------|-------------|  
  |<span data-ttu-id="d9523-127">MSH</span><span class="sxs-lookup"><span data-stu-id="d9523-127">MSH</span></span>|<span data-ttu-id="d9523-128">消息标头</span><span class="sxs-lookup"><span data-stu-id="d9523-128">Message Header</span></span>|<span data-ttu-id="d9523-129">2</span><span class="sxs-lookup"><span data-stu-id="d9523-129">2</span></span>|  
  |<span data-ttu-id="d9523-130">MSA</span><span class="sxs-lookup"><span data-stu-id="d9523-130">MSA</span></span>|<span data-ttu-id="d9523-131">消息确认</span><span class="sxs-lookup"><span data-stu-id="d9523-131">Message Acknowledgment</span></span>|<span data-ttu-id="d9523-132">2</span><span class="sxs-lookup"><span data-stu-id="d9523-132">2</span></span>|  
  |<span data-ttu-id="d9523-133">[ ERR ]</span><span class="sxs-lookup"><span data-stu-id="d9523-133">[ ERR ]</span></span>|<span data-ttu-id="d9523-134">错误</span><span class="sxs-lookup"><span data-stu-id="d9523-134">Error</span></span>|<span data-ttu-id="d9523-135">2</span><span class="sxs-lookup"><span data-stu-id="d9523-135">2</span></span>|  

  <span data-ttu-id="d9523-136">确认的消息具有 MSH9 字段设置为**ACK ^\<**<em>触发器事件</em>**\>^ ACK**或**MCF ^\<** <em>触发器事件</em>**\>^ ACK**。</span><span class="sxs-lookup"><span data-stu-id="d9523-136">Acknowledgment messages have the MSH9 field set as either **ACK^\<**<em>trigger event</em>**\>^ACK** or **MCF^\<**<em>trigger event</em>**\>^ACK**.</span></span> <span data-ttu-id="d9523-137">因此，MSH9 的第一个组件就足以确定确认架构。</span><span class="sxs-lookup"><span data-stu-id="d9523-137">As a result, the first component of MSH9 is sufficient to determine the ACK schema.</span></span> <span data-ttu-id="d9523-138">文档名称的 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 管道使用始终包含 HL7 作为命名空间。</span><span class="sxs-lookup"><span data-stu-id="d9523-138">The document name that the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) pipeline uses always contains HL7 as the namespace.</span></span> <span data-ttu-id="d9523-139">类型名称是 ACK 或 MCF 的 MSH9_1 字段的内容。</span><span class="sxs-lookup"><span data-stu-id="d9523-139">The type name is the contents of the MSH9_1 field, which is ACK or MCF.</span></span> <span data-ttu-id="d9523-140">因此，如以上示例中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]管道查找与名称 HL7 的架构。ACK 或 HL7。MCF，具体取决于 MSH9_1 字段的值。</span><span class="sxs-lookup"><span data-stu-id="d9523-140">As a result, as in the example above, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pipeline looks for a schema with the names HL7.ACK or HL7.MCF, depending on the value of the MSH9_1 field.</span></span> <span data-ttu-id="d9523-141">消息正文的架构是相同的 2.X 版本的所有消息。</span><span class="sxs-lookup"><span data-stu-id="d9523-141">The schema for the message body is the same for all 2.X version messages.</span></span>  

> [!NOTE]
>  <span data-ttu-id="d9523-142">在中的批处理 / 出 ACK 方案中，确认标头的内容的批处理，则按如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9523-142">In a batch in/batch out ACK scenario, the contents of the ACK header is as follows:</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d9523-143">设置 MSH1，2、 8 和 15 到用户界面中配置。</span><span class="sxs-lookup"><span data-stu-id="d9523-143">sets MSH1, 2, 8 and 15 to what you configure in the user interface.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d9523-144">将 MSH7 设置为系统时间。</span><span class="sxs-lookup"><span data-stu-id="d9523-144">sets MSH7 to the system time.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d9523-145">将 MSH9 设置为确认。</span><span class="sxs-lookup"><span data-stu-id="d9523-145">sets MSH9 to ACK.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d9523-146">设置为 2.4 或 2.5 MSH12。</span><span class="sxs-lookup"><span data-stu-id="d9523-146">sets MSH12 to 2.4 or 2.5.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d9523-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9523-147">See Also</span></span>  
 <span data-ttu-id="d9523-148">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="d9523-148">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="d9523-149">[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="d9523-149">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 <span data-ttu-id="d9523-150">[设置用于接收 Ack 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span><span class="sxs-lookup"><span data-stu-id="d9523-150">[Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span></span>  
 [<span data-ttu-id="d9523-151">错误条件确认</span><span class="sxs-lookup"><span data-stu-id="d9523-151">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)