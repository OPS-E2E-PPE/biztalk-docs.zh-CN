---
title: HL7 accelerator 中 BizTalk Server 中的参与方选项卡 |Microsoft Docs
description: BTAHL7 配置资源管理器用于查看现有参与方，并在 BizTalk Server 中配置确认
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
ms.openlocfilehash: 513ee55c2c934c30944916dd4342a82873208215
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290003"
---
# <a name="parties-in-btahl7-configuration-explorer"></a><span data-ttu-id="3701c-103">BTAHL7 配置资源管理器中的参与方</span><span class="sxs-lookup"><span data-stu-id="3701c-103">Parties in BTAHL7 Configuration Explorer</span></span>
<span data-ttu-id="3701c-104">您使用**参与方**选项卡以查看可用的参与方和指定[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置选择，为特定参与方，并配置确认的属性。</span><span class="sxs-lookup"><span data-stu-id="3701c-104">You use the **Parties** tab to view the available parties and specify [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration for a particular party that you choose, and to configure properties for acknowledgments.</span></span> 

## <a name="parties-ui-explained"></a><span data-ttu-id="3701c-105">UI 的参与方所述</span><span class="sxs-lookup"><span data-stu-id="3701c-105">Parties UI explained</span></span>
<span data-ttu-id="3701c-106">**参与方**选项卡包含一个左侧和右侧窗格。</span><span class="sxs-lookup"><span data-stu-id="3701c-106">The **Parties** tab contains both a left and right pane.</span></span> <span data-ttu-id="3701c-107">在左窗格中显示可用的参与方。</span><span class="sxs-lookup"><span data-stu-id="3701c-107">The available parties appear in the left pane.</span></span> <span data-ttu-id="3701c-108">右窗格包含以下选项卡的所选的参与方：</span><span class="sxs-lookup"><span data-stu-id="3701c-108">The right pane contains the following tabs for the selected party:</span></span>  
  
- <span data-ttu-id="3701c-109">**参与方别名**。</span><span class="sxs-lookup"><span data-stu-id="3701c-109">**Party Aliases**.</span></span> <span data-ttu-id="3701c-110">使用此选项卡以查看有关在左窗格中选择的参与方信息。</span><span class="sxs-lookup"><span data-stu-id="3701c-110">Use this tab to view information about the party you have selected from the left pane.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3701c-111">使用 BizTalk 浏览器中创建参与方。</span><span class="sxs-lookup"><span data-stu-id="3701c-111">You use BizTalk Explorer to create parties.</span></span>  
  
- <span data-ttu-id="3701c-112">**批处理定义**。</span><span class="sxs-lookup"><span data-stu-id="3701c-112">**Batch Definition**.</span></span> <span data-ttu-id="3701c-113">使用此选项卡来配置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理。</span><span class="sxs-lookup"><span data-stu-id="3701c-113">Use this tab to configure [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
- <span data-ttu-id="3701c-114">**批处理计划**。</span><span class="sxs-lookup"><span data-stu-id="3701c-114">**Batch Schedule**.</span></span> <span data-ttu-id="3701c-115">使用此选项卡来激活出站批。</span><span class="sxs-lookup"><span data-stu-id="3701c-115">Use this tab to activate outbound batches.</span></span>  
  
- <span data-ttu-id="3701c-116">**确认**。</span><span class="sxs-lookup"><span data-stu-id="3701c-116">**Acknowledgment**.</span></span> <span data-ttu-id="3701c-117">使用此选项卡来指定入站和生成确认的属性。</span><span class="sxs-lookup"><span data-stu-id="3701c-117">Use this tab to specify the properties for inbound and generated acknowledgments.</span></span>  
  
- <span data-ttu-id="3701c-118">**验证**。</span><span class="sxs-lookup"><span data-stu-id="3701c-118">**Validation**.</span></span> <span data-ttu-id="3701c-119">使用此选项卡选择入站和生成消息的消息验证选项。</span><span class="sxs-lookup"><span data-stu-id="3701c-119">Use this tab to select the message validation options for inbound and generated messages.</span></span>  
  
- <span data-ttu-id="3701c-120">**MSH 映射**。</span><span class="sxs-lookup"><span data-stu-id="3701c-120">**MSH Map**.</span></span> <span data-ttu-id="3701c-121">使用此选项卡上启用入站消息的消息标头转换。</span><span class="sxs-lookup"><span data-stu-id="3701c-121">Use this tab to enable message header transformations for inbound messages.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3701c-122">必须配置参与方别名、 批次定义、 批处理计划和为所有贸易参与方的确认信息。</span><span class="sxs-lookup"><span data-stu-id="3701c-122">You must configure party aliases, batch definitions, batch schedules, and acknowledgment information for all trading parties.</span></span>  
  > 
  >  <span data-ttu-id="3701c-123">您可以通过按 F5，或通过右键单击参与方列表中，刷新的参与方列表并选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="3701c-123">You can refresh the parties list by pressing F5, or by right-clicking the parties list, and select **Refresh**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3701c-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3701c-124">Next steps</span></span>  
  
-   [<span data-ttu-id="3701c-125">参与方别名选项卡</span><span class="sxs-lookup"><span data-stu-id="3701c-125">Party Aliases Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/party-aliases-tab.md)  
  
-   [<span data-ttu-id="3701c-126">批处理定义选项卡</span><span class="sxs-lookup"><span data-stu-id="3701c-126">Batch Definition Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)  
  
-   [<span data-ttu-id="3701c-127">批处理计划选项卡</span><span class="sxs-lookup"><span data-stu-id="3701c-127">Batch Schedule Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)  
  
-   [<span data-ttu-id="3701c-128">确认选项卡</span><span class="sxs-lookup"><span data-stu-id="3701c-128">Acknowledgment Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-tab.md)  
  
-   [<span data-ttu-id="3701c-129">验证选项卡</span><span class="sxs-lookup"><span data-stu-id="3701c-129">Validation Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)  
  
-   [<span data-ttu-id="3701c-130">MSH 映射选项卡</span><span class="sxs-lookup"><span data-stu-id="3701c-130">MSH Map Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-map-tab.md)