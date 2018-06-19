---
title: 在 BizTalk Server 中的 HL7 快捷键方选项卡 |Microsoft 文档
description: 使用 BTAHL7 配置资源管理器来查看现有的当事方，并在 BizTalk Server 中配置确认
ms.custom: ''
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e01052c8-25c5-4736-8403-33f16fbd3fb7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d8572da051d046d46b6e895f11f07d3f9d9771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206133"
---
# <a name="parties-in-btahl7-configuration-explorer"></a><span data-ttu-id="7c4de-103">BTAHL7 配置资源管理器中的各方</span><span class="sxs-lookup"><span data-stu-id="7c4de-103">Parties in BTAHL7 Configuration Explorer</span></span>
<span data-ttu-id="7c4de-104">你使用**方**选项卡以查看可用的当事方，并指定[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置特定的一方你选择和配置确认的属性。</span><span class="sxs-lookup"><span data-stu-id="7c4de-104">You use the **Parties** tab to view the available parties and specify [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration for a particular party that you choose, and to configure properties for acknowledgments.</span></span> 

## <a name="parties-ui-explained"></a><span data-ttu-id="7c4de-105">方用户界面说明</span><span class="sxs-lookup"><span data-stu-id="7c4de-105">Parties UI explained</span></span>
<span data-ttu-id="7c4de-106">**方**选项卡包含的左侧和右侧窗格。</span><span class="sxs-lookup"><span data-stu-id="7c4de-106">The **Parties** tab contains both a left and right pane.</span></span> <span data-ttu-id="7c4de-107">在左窗格中显示可用的当事方。</span><span class="sxs-lookup"><span data-stu-id="7c4de-107">The available parties appear in the left pane.</span></span> <span data-ttu-id="7c4de-108">右窗格中包含以下选项卡为所选的当事方：</span><span class="sxs-lookup"><span data-stu-id="7c4de-108">The right pane contains the following tabs for the selected party:</span></span>  
  
-   <span data-ttu-id="7c4de-109">**方别名**。</span><span class="sxs-lookup"><span data-stu-id="7c4de-109">**Party Aliases**.</span></span> <span data-ttu-id="7c4de-110">使用此选项卡查看已选择左窗格中的方有关的信息。</span><span class="sxs-lookup"><span data-stu-id="7c4de-110">Use this tab to view information about the party you have selected from the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c4de-111">BizTalk 资源管理器用于创建参与方。</span><span class="sxs-lookup"><span data-stu-id="7c4de-111">You use BizTalk Explorer to create parties.</span></span>  
  
-   <span data-ttu-id="7c4de-112">**批处理定义**。</span><span class="sxs-lookup"><span data-stu-id="7c4de-112">**Batch Definition**.</span></span> <span data-ttu-id="7c4de-113">使用此选项卡来配置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理。</span><span class="sxs-lookup"><span data-stu-id="7c4de-113">Use this tab to configure [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
-   <span data-ttu-id="7c4de-114">**批处理计划**。</span><span class="sxs-lookup"><span data-stu-id="7c4de-114">**Batch Schedule**.</span></span> <span data-ttu-id="7c4de-115">使用此选项卡来激活出站批处理。</span><span class="sxs-lookup"><span data-stu-id="7c4de-115">Use this tab to activate outbound batches.</span></span>  
  
-   <span data-ttu-id="7c4de-116">**确认**。</span><span class="sxs-lookup"><span data-stu-id="7c4de-116">**Acknowledgment**.</span></span> <span data-ttu-id="7c4de-117">使用此选项卡指定入站和生成的确认的属性。</span><span class="sxs-lookup"><span data-stu-id="7c4de-117">Use this tab to specify the properties for inbound and generated acknowledgments.</span></span>  
  
-   <span data-ttu-id="7c4de-118">**验证**。</span><span class="sxs-lookup"><span data-stu-id="7c4de-118">**Validation**.</span></span> <span data-ttu-id="7c4de-119">使用此选项卡选择入站和生成消息的消息验证选项。</span><span class="sxs-lookup"><span data-stu-id="7c4de-119">Use this tab to select the message validation options for inbound and generated messages.</span></span>  
  
-   <span data-ttu-id="7c4de-120">**MSH 映射**。</span><span class="sxs-lookup"><span data-stu-id="7c4de-120">**MSH Map**.</span></span> <span data-ttu-id="7c4de-121">使用此选项卡启用入站消息的消息标头转换。</span><span class="sxs-lookup"><span data-stu-id="7c4de-121">Use this tab to enable message header transformations for inbound messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c4de-122">你必须配置方别名、 批处理定义、 批处理计划和为所有贸易方的确认信息。</span><span class="sxs-lookup"><span data-stu-id="7c4de-122">You must configure party aliases, batch definitions, batch schedules, and acknowledgment information for all trading parties.</span></span>  
    > 
    >  <span data-ttu-id="7c4de-123">你可以通过按 F5，或通过右击方列表中，刷新方列表并选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="7c4de-123">You can refresh the parties list by pressing F5, or by right-clicking the parties list, and select **Refresh**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7c4de-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7c4de-124">Next steps</span></span>  
  
-   [<span data-ttu-id="7c4de-125">当事方别名选项卡</span><span class="sxs-lookup"><span data-stu-id="7c4de-125">Party Aliases Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/party-aliases-tab.md)  
  
-   [<span data-ttu-id="7c4de-126">批处理定义选项卡</span><span class="sxs-lookup"><span data-stu-id="7c4de-126">Batch Definition Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)  
  
-   [<span data-ttu-id="7c4de-127">批处理计划选项卡</span><span class="sxs-lookup"><span data-stu-id="7c4de-127">Batch Schedule Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)  
  
-   [<span data-ttu-id="7c4de-128">确认选项卡</span><span class="sxs-lookup"><span data-stu-id="7c4de-128">Acknowledgment Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-tab.md)  
  
-   [<span data-ttu-id="7c4de-129">验证选项卡</span><span class="sxs-lookup"><span data-stu-id="7c4de-129">Validation Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)  
  
-   [<span data-ttu-id="7c4de-130">MSH 映射选项卡</span><span class="sxs-lookup"><span data-stu-id="7c4de-130">MSH Map Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-map-tab.md)