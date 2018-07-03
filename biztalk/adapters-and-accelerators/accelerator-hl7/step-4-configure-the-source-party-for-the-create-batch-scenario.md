---
title: 步骤 4： 配置源参与方创建批处理方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b06b6545-4c2e-4a56-9feb-bd3f9574d4d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbb4e172c88c179ea53f1e48d1e08dcb63458607
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999822"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="566f5-102">步骤 4： 配置源参与方创建批处理方案</span><span class="sxs-lookup"><span data-stu-id="566f5-102">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>
<span data-ttu-id="566f5-103">在此步骤中，可以配置创建 Batch 方案的源参与方。</span><span class="sxs-lookup"><span data-stu-id="566f5-103">In this step, you configure the source party for the Create-Batch scenario.</span></span> <span data-ttu-id="566f5-104">您还选择确认该 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将进行批处理，为此参与方定义的一样。</span><span class="sxs-lookup"><span data-stu-id="566f5-104">You also select the acknowledgments that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will batch, as defined for this party.</span></span> <span data-ttu-id="566f5-105">设置为确认批处理计划以便[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]后的消息计数达到 2 将创建批。</span><span class="sxs-lookup"><span data-stu-id="566f5-105">You set the scheduling for the acknowledgment batch such that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will create the batch after the message count reaches 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="566f5-106">在此方案中，你可以使用你在中创建的同一个源参与方[步骤 7： 创建和配置源参与方](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)的 （零碎的入站批处理方案） 本教程的第 1 部分。</span><span class="sxs-lookup"><span data-stu-id="566f5-106">In this scenario, you use the same source party that you created in [Step 7: Create and Configure a Source Party](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md) of Part 1 of this tutorial (the Fragmented Inbound Batch Scenario).</span></span>  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="566f5-107">若要配置源参与方创建批处理方案</span><span class="sxs-lookup"><span data-stu-id="566f5-107">To configure the source party for the Create-Batch scenario</span></span>  
  
1. <span data-ttu-id="566f5-108">BTAHL7 配置资源管理器中上**参与方**选项卡上的控制台树中，单击**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="566f5-108">In BTAHL7 Configuration Explorer, on the **Parties** tab in the console tree, click **Tutorial_BatchSource**.</span></span>  
  
2. <span data-ttu-id="566f5-109">单击**确认**详细信息窗格中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="566f5-109">Click the **Acknowledgment** tab in the Details pane.</span></span> <span data-ttu-id="566f5-110">确认**确认类型**是**OriginalMode**。</span><span class="sxs-lookup"><span data-stu-id="566f5-110">Verify that the **Acknowledgment type** is **OriginalMode**.</span></span>  
  
3. <span data-ttu-id="566f5-111">单击**批定义**选项卡。下**可用的消息确认**，单击**BTAHL7Schemas.ADT_A03_231_GLO_DEF**，单击向右箭头 (**>>**) 若要将此架构添加到**选择消息的 Ack**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="566f5-111">Click the **Batch Definition** tab. Under **Available Message Acks**, click **BTAHL7Schemas.ADT_A03_231_GLO_DEF**, click the Move to the right arrow (**>>**) to add this schema to **Selected Message Acks**, and then click **Save**.</span></span>  
  
4. <span data-ttu-id="566f5-112">单击**批处理计划**选项卡。在中**重复执行批处理后**部分中，选择**消息**，然后键入**2**中**消息**框。</span><span class="sxs-lookup"><span data-stu-id="566f5-112">Click the **Batch Schedule** tab. In the **Repeat Batch After** section, select **Messages**, and then type **2** in the **Messages** box.</span></span>  
  
5. <span data-ttu-id="566f5-113">单击**启动计划**。</span><span class="sxs-lookup"><span data-stu-id="566f5-113">Click **Start Schedule**.</span></span>  
  
   <span data-ttu-id="566f5-114">请继续执行[步骤 5： 为消息批处理创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="566f5-114">Proceed to [Step 5: Create the Send Port for the Message Batch](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md).</span></span>