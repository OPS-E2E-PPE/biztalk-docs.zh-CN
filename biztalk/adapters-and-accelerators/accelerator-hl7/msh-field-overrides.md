---
title: "MSH 字段将覆盖 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- headers, overriding
- MSH Map tab [Configuration Explorer]
- headers, MSH Map tab
- messages, message headers
ms.assetid: f5b2c820-57e7-4a56-9d9f-713563bd7335
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7303de4a8054cfe9f7140bd6eb548c228248777c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="msh-field-overrides"></a><span data-ttu-id="dedc3-102">MSH 字段将覆盖</span><span class="sxs-lookup"><span data-stu-id="dedc3-102">MSH Field Overrides</span></span>
<span data-ttu-id="dedc3-103">每个 HL7 消息具有一个消息头。</span><span class="sxs-lookup"><span data-stu-id="dedc3-103">Every HL7 message has a message header.</span></span> <span data-ttu-id="dedc3-104">使用[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，你可以重写基于你的业务需求的任何消息标头值。</span><span class="sxs-lookup"><span data-stu-id="dedc3-104">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can override any message header value based on your business need.</span></span> <span data-ttu-id="dedc3-105">你使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**MSH 映射**选项卡以手动覆盖消息标头值而不使用任何映射或业务流程。</span><span class="sxs-lookup"><span data-stu-id="dedc3-105">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **MSH Map** tab to manually over ride message header values without using any mapping or orchestration.</span></span>  
  
## <a name="configuring-msh-field-overrides"></a><span data-ttu-id="dedc3-106">配置 MSH 字段重写</span><span class="sxs-lookup"><span data-stu-id="dedc3-106">Configuring MSH Field Overrides</span></span>  
 <span data-ttu-id="dedc3-107">你使用**MSH 映射**选项卡中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**方**选项卡) 来配置 MSH 字段重写。</span><span class="sxs-lookup"><span data-stu-id="dedc3-107">You use the **MSH Map** tab in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure MSH field overrides.</span></span> <span data-ttu-id="dedc3-108">使用此选项卡，此值替代 MSH 字段输入的值在出站 HL7 中的现有 MSH 值消息时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将发送到所选的当事方。</span><span class="sxs-lookup"><span data-stu-id="dedc3-108">When you enter a value for an MSH field using this tab, that value overrides the existing MSH value in an outbound HL7 message that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends to the selected party.</span></span> <span data-ttu-id="dedc3-109">你可以键入新值 MSH 的多个字段，或从 MSH15 和 MSH16 字段的下拉列表中选择值。</span><span class="sxs-lookup"><span data-stu-id="dedc3-109">You can type new values for many MSH fields, or select values from a drop-down list for the MSH15 and MSH16 fields.</span></span>  
  
 <span data-ttu-id="dedc3-110">下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**MSH 映射**选项卡。</span><span class="sxs-lookup"><span data-stu-id="dedc3-110">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **MSH Map** tab.</span></span>  
  
 <span data-ttu-id="dedc3-111">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")</span><span class="sxs-lookup"><span data-stu-id="dedc3-111">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")</span></span>  
  
 <span data-ttu-id="dedc3-112">使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器并配置 MSH 字段重写。</span><span class="sxs-lookup"><span data-stu-id="dedc3-112">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and configure MSH field overrides.</span></span>  
  
#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="dedc3-113">若要打开 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="dedc3-113">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="dedc3-114">单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-114">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
#### <a name="to-configure-msh-field-overrides"></a><span data-ttu-id="dedc3-115">若要配置 MSH 字段重写</span><span class="sxs-lookup"><span data-stu-id="dedc3-115">To configure MSH field overrides</span></span>  
  
1.  <span data-ttu-id="dedc3-116">在 BTAHL7 配置资源管理器，在**MSH 映射**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dedc3-116">In BTAHL7 Configuration Explorer, on the **MSH Map** tab, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dedc3-117">若要覆盖现有值为 null，请键入 **\\** 。</span><span class="sxs-lookup"><span data-stu-id="dedc3-117">To override the existing value to null, type **\\**.</span></span>  
  
    |<span data-ttu-id="dedc3-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="dedc3-118">Use this</span></span>|<span data-ttu-id="dedc3-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="dedc3-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="dedc3-120">**MSH.3**</span><span class="sxs-lookup"><span data-stu-id="dedc3-120">**MSH.3**</span></span>|<span data-ttu-id="dedc3-121">为此消息头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="dedc3-121">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="dedc3-122">**MSH.4**</span><span class="sxs-lookup"><span data-stu-id="dedc3-122">**MSH.4**</span></span>|<span data-ttu-id="dedc3-123">为此消息头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="dedc3-123">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="dedc3-124">**MSH.5**</span><span class="sxs-lookup"><span data-stu-id="dedc3-124">**MSH.5**</span></span>|<span data-ttu-id="dedc3-125">为此消息头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="dedc3-125">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="dedc3-126">**MSH.6**</span><span class="sxs-lookup"><span data-stu-id="dedc3-126">**MSH.6**</span></span>|<span data-ttu-id="dedc3-127">为此消息头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="dedc3-127">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="dedc3-128">**MSH.8**</span><span class="sxs-lookup"><span data-stu-id="dedc3-128">**MSH.8**</span></span>|<span data-ttu-id="dedc3-129">为此消息头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="dedc3-129">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="dedc3-130">**MSH.9**</span><span class="sxs-lookup"><span data-stu-id="dedc3-130">**MSH.9**</span></span>|<span data-ttu-id="dedc3-131">此消息头的替代类型消息字段</span><span class="sxs-lookup"><span data-stu-id="dedc3-131">Type message field overrides for this message header</span></span>|  
    |<span data-ttu-id="dedc3-132">**MSH.12**</span><span class="sxs-lookup"><span data-stu-id="dedc3-132">**MSH.12**</span></span>|<span data-ttu-id="dedc3-133">为此消息头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="dedc3-133">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="dedc3-134">**MSH.15**</span><span class="sxs-lookup"><span data-stu-id="dedc3-134">**MSH.15**</span></span>|<span data-ttu-id="dedc3-135">选择接受确认类型的确认替代的以下选项：</span><span class="sxs-lookup"><span data-stu-id="dedc3-135">Select from the following options for an acknowledgment override for the accept acknowledgment type:</span></span><br /><br /> <span data-ttu-id="dedc3-136">-   **AL**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-136">-   **AL**.</span></span> <span data-ttu-id="dedc3-137">如果你始终希望能够发送，请选择此选项接受确认。</span><span class="sxs-lookup"><span data-stu-id="dedc3-137">Select this option if you always want to send accept acknowledgments.</span></span><br /><span data-ttu-id="dedc3-138">-   **NE**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-138">-   **NE**.</span></span> <span data-ttu-id="dedc3-139">如果你永远不会想要发送，请选择此选项接受确认。</span><span class="sxs-lookup"><span data-stu-id="dedc3-139">Select this option if you never want to send accept acknowledgments.</span></span><br /><span data-ttu-id="dedc3-140">-   **SU**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-140">-   **SU**.</span></span> <span data-ttu-id="dedc3-141">如果你想要发送，请选择此选项接受后成功的消息传输的确认。</span><span class="sxs-lookup"><span data-stu-id="dedc3-141">Select this option if you want to send accept acknowledgments after successful transmission of a message.</span></span><br /><span data-ttu-id="dedc3-142">-   **ER**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-142">-   **ER**.</span></span> <span data-ttu-id="dedc3-143">如果你想要发送，请选择此选项仅发生错误时接受确认。</span><span class="sxs-lookup"><span data-stu-id="dedc3-143">Select this option if you want to send accept acknowledgments only in the event of an error.</span></span>|  
    |<span data-ttu-id="dedc3-144">**MSH.16**</span><span class="sxs-lookup"><span data-stu-id="dedc3-144">**MSH.16**</span></span>|<span data-ttu-id="dedc3-145">选择从以下选项中进行的应用程序的确认类型的确认替代：</span><span class="sxs-lookup"><span data-stu-id="dedc3-145">Select from the following options for an acknowledgment override for the application acknowledgment type:</span></span><br /><br /> <span data-ttu-id="dedc3-146">-   **AL**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-146">-   **AL**.</span></span> <span data-ttu-id="dedc3-147">如果你始终希望能够发送应用程序确认，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="dedc3-147">Select this option if you always want to send application acknowledgments.</span></span><br /><span data-ttu-id="dedc3-148">-   **NE**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-148">-   **NE**.</span></span> <span data-ttu-id="dedc3-149">如果你永远不会想要发送应用程序确认，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="dedc3-149">Select this option if you never want to send application acknowledgments.</span></span><br /><span data-ttu-id="dedc3-150">-   **SU**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-150">-   **SU**.</span></span> <span data-ttu-id="dedc3-151">如果你想要将应用程序确认发送成功的消息传输后，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="dedc3-151">Select this option if you want to send application acknowledgments after successful transmission of a message.</span></span><br /><span data-ttu-id="dedc3-152">-   **ER**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-152">-   **ER**.</span></span> <span data-ttu-id="dedc3-153">如果你想要仅发生错误时发送应用程序确认，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="dedc3-153">Select this option if you want to send application acknowledgments only in the event of an error.</span></span>|  
  
2.  <span data-ttu-id="dedc3-154">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="dedc3-154">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dedc3-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dedc3-155">See Also</span></span>  
 <span data-ttu-id="dedc3-156">[日志记录配置](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="dedc3-156">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="dedc3-157">[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="dedc3-157">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
[<span data-ttu-id="dedc3-158">运行日志记录、消息批处理、验证和确认设置</span><span class="sxs-lookup"><span data-stu-id="dedc3-158">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)