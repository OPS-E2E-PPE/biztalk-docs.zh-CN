---
title: 第 3 部分：创建批处理方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 439e285ddc432a57add0a9a719553eb532f12bbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290020"
---
# <a name="part-3-create-batch-scenario"></a><span data-ttu-id="7993a-102">第 3 部分：创建批处理方案</span><span class="sxs-lookup"><span data-stu-id="7993a-102">Part 3: Create-Batch Scenario</span></span>
<span data-ttu-id="7993a-103">在此方案的一部分，您收到两条传入消息、 将它们合并到批处理消息，和向目标发送一批。</span><span class="sxs-lookup"><span data-stu-id="7993a-103">In this part of the scenario, you receive two incoming messages, combine them into a batched message, and send the batch to a destination.</span></span> <span data-ttu-id="7993a-104">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 返回包含两个确认从目标到源的消息生成确认批处理。</span><span class="sxs-lookup"><span data-stu-id="7993a-104">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) returns an acknowledgment batch containing the two acknowledgments generated for the messages from the destination to the source.</span></span> <span data-ttu-id="7993a-105">下图显示了本教程的此部分的处理流程。</span><span class="sxs-lookup"><span data-stu-id="7993a-105">The following figure shows the process flow of this part of the tutorial.</span></span>  
  
 <span data-ttu-id="7993a-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")</span><span class="sxs-lookup"><span data-stu-id="7993a-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")</span></span>  
  
 <span data-ttu-id="7993a-107">**消息在创建 Batch 方案中的流动**</span><span class="sxs-lookup"><span data-stu-id="7993a-107">**How messages flow in the Create-Batch scenario**</span></span>  
  
 <span data-ttu-id="7993a-108">此方案包括以下工作流：</span><span class="sxs-lookup"><span data-stu-id="7993a-108">This scenario includes the following workflow:</span></span>  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="7993a-109">捕获与 MessageBox 数据库中的批次定义的所有消息。</span><span class="sxs-lookup"><span data-stu-id="7993a-109">traps all messages conforming to the batch definition in the MessageBox database.</span></span> <span data-ttu-id="7993a-110">输入此定义中的**批定义**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="7993a-110">You enter this definition in the **Batch Definition** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="7993a-111">在本教程中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将捕获和批处理所有消息和 ADT 架构一起发送到 Tutorial_BatchDest ^ A03，和所有确认发送到由于 ADT Tutorial_BatchSource ^ A03 消息。</span><span class="sxs-lookup"><span data-stu-id="7993a-111">In this tutorial, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will trap and batch all messages to be sent to Tutorial_BatchDest with a schema of ADT^A03, and all acknowledgments to be sent to Tutorial_BatchSource as a result of ADT^A03 messages.</span></span>  
  
- <span data-ttu-id="7993a-112">计划的批发送时间时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送批处理控制消息触发出站批处理事务。</span><span class="sxs-lookup"><span data-stu-id="7993a-112">When the scheduled batch send time occurs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a batch control message that triggers the outbound batch transaction.</span></span> <span data-ttu-id="7993a-113">在定义的计划**批处理计划**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="7993a-113">You define the schedule on the **Batch Schedule** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="7993a-114">此外可以通过单击来触发进程**立即发送**同一选项卡。</span><span class="sxs-lookup"><span data-stu-id="7993a-114">You can also trigger the process by clicking **Send Now** on the same tab.</span></span>  
  
- <span data-ttu-id="7993a-115">批处理业务流程窗体从 MessageBox 数据库中捕获的消息的消息批处理。</span><span class="sxs-lookup"><span data-stu-id="7993a-115">The batch orchestration forms the message batch out of the messages trapped in the MessageBox database.</span></span> <span data-ttu-id="7993a-116">业务流程也会将文件标头和尾部和批处理标头和尾部中的批处理。</span><span class="sxs-lookup"><span data-stu-id="7993a-116">The orchestration also wraps the batch in a file header and trailer, and a batch header and trailer.</span></span> <span data-ttu-id="7993a-117">此业务流程是一个本机[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]业务流程添加[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到集的 BizTalk 业务流程，因此它列在 BizTalk 浏览器或 BizTalk Server 管理控制台中的业务流程节点下的安装程序。</span><span class="sxs-lookup"><span data-stu-id="7993a-117">This orchestration is a native [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orchestration added by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup to your set of BizTalk orchestrations, so it is listed under the Orchestrations node in BizTalk Explorer or the BizTalk Server Administration Console.</span></span>  
  
- <span data-ttu-id="7993a-118">如果确认都定义为源参与方 （因为在这种情况下，它们是用于 Tutorial_BatchSource），BizTalk 对确认进行批处理，并将它们在批处理中返回 （到 \Tutorial_BatchACKDrop 文件夹中）。</span><span class="sxs-lookup"><span data-stu-id="7993a-118">If acknowledgments are defined for the source party (as they are in this case for Tutorial_BatchSource), BizTalk batches the acknowledgments and returns them in a batch (to the \Tutorial_BatchACKDrop folder).</span></span> <span data-ttu-id="7993a-119">在本教程中，批处理的确认一小段延迟后发送。</span><span class="sxs-lookup"><span data-stu-id="7993a-119">In this tutorial, the batched acknowledgments are sent after a short delay.</span></span>  
  
- <span data-ttu-id="7993a-120">业务流程将消息路由到发送端口 (Tutorial_BatchDest)，可将批处理的消息发送到目标 （在此情况下，您的硬盘上的 \Tutorial_BatchMsgDrop 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="7993a-120">The orchestration routes the message to the send port (Tutorial_BatchDest), which sends the batched message to the destination (in this case, the \Tutorial_BatchMsgDrop folder on your hard drive).</span></span> <span data-ttu-id="7993a-121">在本教程中，在一小时后发送批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="7993a-121">In this tutorial, the batched messages are sent after one hour.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7993a-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="7993a-122">In This Section</span></span>  
  
-   [<span data-ttu-id="7993a-123">步骤 1：配置和启用 BatchControlPort 接收端口</span><span class="sxs-lookup"><span data-stu-id="7993a-123">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [<span data-ttu-id="7993a-124">步骤 2：启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="7993a-124">Step 2: Enable the Batch Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [<span data-ttu-id="7993a-125">步骤 3：创建和配置目标参与方</span><span class="sxs-lookup"><span data-stu-id="7993a-125">Step 3: Create and Configure a Destination Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [<span data-ttu-id="7993a-126">步骤 4：为 Create-Batch 方案配置源参与方</span><span class="sxs-lookup"><span data-stu-id="7993a-126">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [<span data-ttu-id="7993a-127">步骤 5：为消息批处理创建发送端口</span><span class="sxs-lookup"><span data-stu-id="7993a-127">Step 5: Create the Send Port for the Message Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [<span data-ttu-id="7993a-128">步骤 6：为确认批处理创建发送端口</span><span class="sxs-lookup"><span data-stu-id="7993a-128">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [<span data-ttu-id="7993a-129">步骤 7：启动业务流程并重启 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7993a-129">Step 7: Start the Orchestration and Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="7993a-130">步骤 8：测试 Create-Batch 方案</span><span class="sxs-lookup"><span data-stu-id="7993a-130">Step 8: Test the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)