---
title: 第 3 部分： 创建批处理方案 |Microsoft 文档
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
ms.openlocfilehash: 0949d45fc70ead14338e30b554e0cb4b9694b5d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206197"
---
# <a name="part-3-create-batch-scenario"></a><span data-ttu-id="c77ec-102">第 3 部分： 创建批处理方案</span><span class="sxs-lookup"><span data-stu-id="c77ec-102">Part 3: Create-Batch Scenario</span></span>
<span data-ttu-id="c77ec-103">在此方案的一部分，你将接收两个传入消息、 将它们合并到消息的批处理，和批处理发送到目标。</span><span class="sxs-lookup"><span data-stu-id="c77ec-103">In this part of the scenario, you receive two incoming messages, combine them into a batched message, and send the batch to a destination.</span></span> <span data-ttu-id="c77ec-104">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 返回包含生成从目标到源的消息的两个确认的确认批次。</span><span class="sxs-lookup"><span data-stu-id="c77ec-104">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) returns an acknowledgment batch containing the two acknowledgments generated for the messages from the destination to the source.</span></span> <span data-ttu-id="c77ec-105">下图显示在本教程的此部分的处理流程。</span><span class="sxs-lookup"><span data-stu-id="c77ec-105">The following figure shows the process flow of this part of the tutorial.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")  
  
 <span data-ttu-id="c77ec-106">**如何将消息流中创建批处理方案**</span><span class="sxs-lookup"><span data-stu-id="c77ec-106">**How messages flow in the Create-Batch scenario**</span></span>  
  
 <span data-ttu-id="c77ec-107">此方案包括以下工作流：</span><span class="sxs-lookup"><span data-stu-id="c77ec-107">This scenario includes the following workflow:</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="c77ec-108">捕获符合 MessageBox 数据库中的批处理定义的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c77ec-108"> traps all messages conforming to the batch definition in the MessageBox database.</span></span> <span data-ttu-id="c77ec-109">输入在此定义**批定义**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="c77ec-109">You enter this definition in the **Batch Definition** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="c77ec-110">在本教程中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将捕获和批处理所有消息的架构的 ADT 与发送到 Tutorial_BatchDest ^ A03，和所有确认发送到由于 ADT Tutorial_BatchSource ^ A03 消息。</span><span class="sxs-lookup"><span data-stu-id="c77ec-110">In this tutorial, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will trap and batch all messages to be sent to Tutorial_BatchDest with a schema of ADT^A03, and all acknowledgments to be sent to Tutorial_BatchSource as a result of ADT^A03 messages.</span></span>  
  
-   <span data-ttu-id="c77ec-111">当计划的批发送时间发生时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送批处理控件消息触发的出站批处理事务。</span><span class="sxs-lookup"><span data-stu-id="c77ec-111">When the scheduled batch send time occurs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a batch control message that triggers the outbound batch transaction.</span></span> <span data-ttu-id="c77ec-112">在定义计划**批处理计划**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="c77ec-112">You define the schedule on the **Batch Schedule** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="c77ec-113">你也可以通过单击来触发进程**立即发送**同一选项卡上。</span><span class="sxs-lookup"><span data-stu-id="c77ec-113">You can also trigger the process by clicking **Send Now** on the same tab.</span></span>  
  
-   <span data-ttu-id="c77ec-114">批处理业务流程窗体消息批处理外困在 MessageBox 数据库的消息。</span><span class="sxs-lookup"><span data-stu-id="c77ec-114">The batch orchestration forms the message batch out of the messages trapped in the MessageBox database.</span></span> <span data-ttu-id="c77ec-115">业务流程也会将在文件标头和尾部，以及批处理标头和预告片批处理。</span><span class="sxs-lookup"><span data-stu-id="c77ec-115">The orchestration also wraps the batch in a file header and trailer, and a batch header and trailer.</span></span> <span data-ttu-id="c77ec-116">此业务流程是一个本机[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]业务流程通过添加[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到您的 BizTalk 业务流程，以便该设备将在 BizTalk 资源管理器或 BizTalk Server 管理控制台中的业务流程节点集的安装程序。</span><span class="sxs-lookup"><span data-stu-id="c77ec-116">This orchestration is a native [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orchestration added by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup to your set of BizTalk orchestrations, so it is listed under the Orchestrations node in BizTalk Explorer or the BizTalk Server Administration Console.</span></span>  
  
-   <span data-ttu-id="c77ec-117">如果确认为源方 （如在这种情况下，它们是为 Tutorial_BatchSource） 定义，BizTalk 批处理确认并将它们返回批处理中 （到 \Tutorial_BatchACKDrop 文件夹中）。</span><span class="sxs-lookup"><span data-stu-id="c77ec-117">If acknowledgments are defined for the source party (as they are in this case for Tutorial_BatchSource), BizTalk batches the acknowledgments and returns them in a batch (to the \Tutorial_BatchACKDrop folder).</span></span> <span data-ttu-id="c77ec-118">在本教程中，批处理的确认会发送一小段延迟后。</span><span class="sxs-lookup"><span data-stu-id="c77ec-118">In this tutorial, the batched acknowledgments are sent after a short delay.</span></span>  
  
-   <span data-ttu-id="c77ec-119">业务流程将消息路由到发送端口 (Tutorial_BatchDest)，它将批处理的消息发送到目标 （在此情况下，在硬盘上的 \Tutorial_BatchMsgDrop 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="c77ec-119">The orchestration routes the message to the send port (Tutorial_BatchDest), which sends the batched message to the destination (in this case, the \Tutorial_BatchMsgDrop folder on your hard drive).</span></span> <span data-ttu-id="c77ec-120">在本教程中，批处理的消息会发送一小时之后。</span><span class="sxs-lookup"><span data-stu-id="c77ec-120">In this tutorial, the batched messages are sent after one hour.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c77ec-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="c77ec-121">In This Section</span></span>  
  
-   [<span data-ttu-id="c77ec-122">步骤 1： 配置和启用 BatchControlPort 接收端口</span><span class="sxs-lookup"><span data-stu-id="c77ec-122">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [<span data-ttu-id="c77ec-123">步骤 2： 启用批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="c77ec-123">Step 2: Enable the Batch Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [<span data-ttu-id="c77ec-124">步骤 3： 创建并配置目标方</span><span class="sxs-lookup"><span data-stu-id="c77ec-124">Step 3: Create and Configure a Destination Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [<span data-ttu-id="c77ec-125">步骤 4： 配置创建批处理方案的源方</span><span class="sxs-lookup"><span data-stu-id="c77ec-125">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [<span data-ttu-id="c77ec-126">步骤 5： 为消息批创建发送端口</span><span class="sxs-lookup"><span data-stu-id="c77ec-126">Step 5: Create the Send Port for the Message Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [<span data-ttu-id="c77ec-127">步骤 6： 为确认批处理创建发送端口</span><span class="sxs-lookup"><span data-stu-id="c77ec-127">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [<span data-ttu-id="c77ec-128">步骤 7： 启动业务流程和重新启动 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c77ec-128">Step 7: Start the Orchestration and Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="c77ec-129">步骤 8： 测试创建批处理方案</span><span class="sxs-lookup"><span data-stu-id="c77ec-129">Step 8: Test the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)