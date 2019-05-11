---
title: MSH 字段替代 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- headers, overriding
- MSH Map tab [Configuration Explorer]
- headers, MSH Map tab
- messages, message headers
ms.assetid: f5b2c820-57e7-4a56-9d9f-713563bd7335
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d0168aff76d5c0f7f408840a79b8311f2061cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290185"
---
# <a name="msh-field-overrides"></a><span data-ttu-id="82291-102">MSH 字段替代</span><span class="sxs-lookup"><span data-stu-id="82291-102">MSH Field Overrides</span></span>
<span data-ttu-id="82291-103">每个 HL7 消息具有一个消息头。</span><span class="sxs-lookup"><span data-stu-id="82291-103">Every HL7 message has a message header.</span></span> <span data-ttu-id="82291-104">使用[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，可以重写基于你的业务需求的任何消息标头值。</span><span class="sxs-lookup"><span data-stu-id="82291-104">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can override any message header value based on your business need.</span></span> <span data-ttu-id="82291-105">您使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**MSH 映射**选项卡可以手动写消息标头值而不使用任何映射或业务流程。</span><span class="sxs-lookup"><span data-stu-id="82291-105">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **MSH Map** tab to manually over ride message header values without using any mapping or orchestration.</span></span>  
  
## <a name="configuring-msh-field-overrides"></a><span data-ttu-id="82291-106">配置 MSH 字段替代</span><span class="sxs-lookup"><span data-stu-id="82291-106">Configuring MSH Field Overrides</span></span>  
 <span data-ttu-id="82291-107">您使用**MSH 映射**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**参与方**选项卡) 配置 MSH 字段替代。</span><span class="sxs-lookup"><span data-stu-id="82291-107">You use the **MSH Map** tab in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure MSH field overrides.</span></span> <span data-ttu-id="82291-108">出站 HL7 中的现有 MSH 值消息时使用此选项卡中的值重写的 MSH 字段输入的值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将发送到所选的参与方。</span><span class="sxs-lookup"><span data-stu-id="82291-108">When you enter a value for an MSH field using this tab, that value overrides the existing MSH value in an outbound HL7 message that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends to the selected party.</span></span> <span data-ttu-id="82291-109">您可以键入新许多 MSH 字段值，或从 MSH15 和 MSH16 字段的下拉列表中选择值。</span><span class="sxs-lookup"><span data-stu-id="82291-109">You can type new values for many MSH fields, or select values from a drop-down list for the MSH15 and MSH16 fields.</span></span>  
  
 <span data-ttu-id="82291-110">下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**MSH 映射**选项卡。</span><span class="sxs-lookup"><span data-stu-id="82291-110">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **MSH Map** tab.</span></span>  
  
 <span data-ttu-id="82291-111">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")</span><span class="sxs-lookup"><span data-stu-id="82291-111">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")</span></span>  
  
 <span data-ttu-id="82291-112">使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和配置 MSH 字段替代。</span><span class="sxs-lookup"><span data-stu-id="82291-112">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and configure MSH field overrides.</span></span>  
  
#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="82291-113">若要打开 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="82291-113">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="82291-114">单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="82291-114">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
#### <a name="to-configure-msh-field-overrides"></a><span data-ttu-id="82291-115">若要配置 MSH 字段替代</span><span class="sxs-lookup"><span data-stu-id="82291-115">To configure MSH field overrides</span></span>  
  
1.  <span data-ttu-id="82291-116">BTAHL7 配置资源管理器中上**MSH 映射**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="82291-116">In BTAHL7 Configuration Explorer, on the **MSH Map** tab, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82291-117">若要覆盖现有值设置为 null，请键入**\\**。</span><span class="sxs-lookup"><span data-stu-id="82291-117">To override the existing value to null, type **\\**.</span></span>  
  
    |<span data-ttu-id="82291-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="82291-118">Use this</span></span>|<span data-ttu-id="82291-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="82291-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="82291-120">**MSH.3**</span><span class="sxs-lookup"><span data-stu-id="82291-120">**MSH.3**</span></span>|<span data-ttu-id="82291-121">为此消息标头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="82291-121">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="82291-122">**MSH.4**</span><span class="sxs-lookup"><span data-stu-id="82291-122">**MSH.4**</span></span>|<span data-ttu-id="82291-123">为此消息标头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="82291-123">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="82291-124">**MSH.5**</span><span class="sxs-lookup"><span data-stu-id="82291-124">**MSH.5**</span></span>|<span data-ttu-id="82291-125">为此消息标头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="82291-125">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="82291-126">**MSH.6**</span><span class="sxs-lookup"><span data-stu-id="82291-126">**MSH.6**</span></span>|<span data-ttu-id="82291-127">为此消息标头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="82291-127">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="82291-128">**MSH.8**</span><span class="sxs-lookup"><span data-stu-id="82291-128">**MSH.8**</span></span>|<span data-ttu-id="82291-129">为此消息标头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="82291-129">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="82291-130">**MSH.9**</span><span class="sxs-lookup"><span data-stu-id="82291-130">**MSH.9**</span></span>|<span data-ttu-id="82291-131">此消息标头的替代类型消息字段</span><span class="sxs-lookup"><span data-stu-id="82291-131">Type message field overrides for this message header</span></span>|  
    |<span data-ttu-id="82291-132">**MSH.12**</span><span class="sxs-lookup"><span data-stu-id="82291-132">**MSH.12**</span></span>|<span data-ttu-id="82291-133">为此消息标头替代类型消息字段。</span><span class="sxs-lookup"><span data-stu-id="82291-133">Type message field overrides for this message header.</span></span>|  
    |<span data-ttu-id="82291-134">**MSH.15**</span><span class="sxs-lookup"><span data-stu-id="82291-134">**MSH.15**</span></span>|<span data-ttu-id="82291-135">从接受确认类型为确认替代以下选项中选择：</span><span class="sxs-lookup"><span data-stu-id="82291-135">Select from the following options for an acknowledgment override for the accept acknowledgment type:</span></span><br /><br /> <span data-ttu-id="82291-136">-   **AL**。</span><span class="sxs-lookup"><span data-stu-id="82291-136">-   **AL**.</span></span> <span data-ttu-id="82291-137">如果始终想要发送，请选择此选项接受确认。</span><span class="sxs-lookup"><span data-stu-id="82291-137">Select this option if you always want to send accept acknowledgments.</span></span><br /><span data-ttu-id="82291-138">-   **NE**。</span><span class="sxs-lookup"><span data-stu-id="82291-138">-   **NE**.</span></span> <span data-ttu-id="82291-139">选择此选项，如果永远不会想要发送接受确认。</span><span class="sxs-lookup"><span data-stu-id="82291-139">Select this option if you never want to send accept acknowledgments.</span></span><br /><span data-ttu-id="82291-140">-   **SU**。</span><span class="sxs-lookup"><span data-stu-id="82291-140">-   **SU**.</span></span> <span data-ttu-id="82291-141">如果你想要发送，请选择此选项后的消息传输成功接受确认。</span><span class="sxs-lookup"><span data-stu-id="82291-141">Select this option if you want to send accept acknowledgments after successful transmission of a message.</span></span><br /><span data-ttu-id="82291-142">-   **ER**。</span><span class="sxs-lookup"><span data-stu-id="82291-142">-   **ER**.</span></span> <span data-ttu-id="82291-143">如果你想要发送，请选择此选项仅当出现错误时，接受确认。</span><span class="sxs-lookup"><span data-stu-id="82291-143">Select this option if you want to send accept acknowledgments only in the event of an error.</span></span>|  
    |<span data-ttu-id="82291-144">**MSH.16**</span><span class="sxs-lookup"><span data-stu-id="82291-144">**MSH.16**</span></span>|<span data-ttu-id="82291-145">从应用程序确认类型为确认替代以下选项中选择：</span><span class="sxs-lookup"><span data-stu-id="82291-145">Select from the following options for an acknowledgment override for the application acknowledgment type:</span></span><br /><br /> <span data-ttu-id="82291-146">-   **AL**。</span><span class="sxs-lookup"><span data-stu-id="82291-146">-   **AL**.</span></span> <span data-ttu-id="82291-147">如果始终想要发送应用程序确认，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="82291-147">Select this option if you always want to send application acknowledgments.</span></span><br /><span data-ttu-id="82291-148">-   **NE**。</span><span class="sxs-lookup"><span data-stu-id="82291-148">-   **NE**.</span></span> <span data-ttu-id="82291-149">如果你永远不会想要发送应用程序确认，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="82291-149">Select this option if you never want to send application acknowledgments.</span></span><br /><span data-ttu-id="82291-150">-   **SU**。</span><span class="sxs-lookup"><span data-stu-id="82291-150">-   **SU**.</span></span> <span data-ttu-id="82291-151">如果你想要将应用程序确认发送成功传输消息后，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="82291-151">Select this option if you want to send application acknowledgments after successful transmission of a message.</span></span><br /><span data-ttu-id="82291-152">-   **ER**。</span><span class="sxs-lookup"><span data-stu-id="82291-152">-   **ER**.</span></span> <span data-ttu-id="82291-153">如果你想要发送应用程序确认仅发生错误时，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="82291-153">Select this option if you want to send application acknowledgments only in the event of an error.</span></span>|  
  
2.  <span data-ttu-id="82291-154">单击“保存” 。</span><span class="sxs-lookup"><span data-stu-id="82291-154">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82291-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="82291-155">See Also</span></span>  
 <span data-ttu-id="82291-156">[日志记录配置](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="82291-156">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="82291-157">[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="82291-157">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
[<span data-ttu-id="82291-158">运行日志记录、消息批处理、验证和确认设置</span><span class="sxs-lookup"><span data-stu-id="82291-158">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)