---
title: 第 2 部分：批处理批处理方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d950a326aae07db4763210f67118ae272785444d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290374"
---
# <a name="part-2-batch-inbatch-out-scenario"></a><span data-ttu-id="c12d4-102">第 2 部分：在批处理 / 批处理方案</span><span class="sxs-lookup"><span data-stu-id="c12d4-102">Part 2: Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="c12d4-103">在本教程的此部分中，接收 HL7 编码的批文件，将通过其传递[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]而无需碎片，并发送到目标不变的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="c12d4-103">In this part of the tutorial, you receive an HL7-encoded batch file, pass it through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without fragmentation, and send the intact batch file to the destination.</span></span> <span data-ttu-id="c12d4-104">下图显示了此过程中，流和以下子节介绍了工作流。</span><span class="sxs-lookup"><span data-stu-id="c12d4-104">The following figure shows the flow of this process, and the subsection below describes the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c12d4-105">开始本教程的此部分之前，请关闭您的关闭该命令会提示使用第 1 部分，MllpReceive 和 MllpSend 工具。</span><span class="sxs-lookup"><span data-stu-id="c12d4-105">Before starting this part of the tutorial, turn off the MllpReceive and MllpSend tools that you used in Part 1, by closing the command prompts.</span></span>  
  
 <span data-ttu-id="c12d4-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")</span><span class="sxs-lookup"><span data-stu-id="c12d4-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")</span></span>  
  
 <span data-ttu-id="c12d4-107">**在 Batch 中的消息流的方式在 / 出站批处理方案**</span><span class="sxs-lookup"><span data-stu-id="c12d4-107">**How messages flow in the Batch In/Batch Out scenario**</span></span>  
  
 <span data-ttu-id="c12d4-108">此方案包括以下工作流：</span><span class="sxs-lookup"><span data-stu-id="c12d4-108">This scenario includes the following workflow:</span></span>  
  
1. <span data-ttu-id="c12d4-109">在工作流开始时的业务线应用程序中将消息批发送到 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 集成引擎使用 FILE 协议。</span><span class="sxs-lookup"><span data-stu-id="c12d4-109">The workflow begins when a line-of-business application sends a message batch to the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Integration Engine using the FILE protocol.</span></span> <span data-ttu-id="c12d4-110">批处理包含两个版本的 ADT ^ A03 消息。</span><span class="sxs-lookup"><span data-stu-id="c12d4-110">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="c12d4-111">源应用程序属于 Tutorial_BatchSource 参与方。</span><span class="sxs-lookup"><span data-stu-id="c12d4-111">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2. <span data-ttu-id="c12d4-112">集成引擎接收的批处理文件中的接收端口，并验证消息批。</span><span class="sxs-lookup"><span data-stu-id="c12d4-112">The Integration Engine receives the batch on a FILE receive port, and validates the message batch.</span></span> <span data-ttu-id="c12d4-113">(的验证级别取决于选择中的源参与方设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。)</span><span class="sxs-lookup"><span data-stu-id="c12d4-113">(The level of validation depends on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.)</span></span>  
  
3. <span data-ttu-id="c12d4-114">根据中的设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，以禁用批处理碎片的参与方，接口引擎未分析为单个消息批，但保留作为批处理的批处理。</span><span class="sxs-lookup"><span data-stu-id="c12d4-114">Based on a setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer that disables batch fragmentation for the party, the Interface Engine does not parse the batch into individual messages, but leaves the batch as a batch.</span></span> <span data-ttu-id="c12d4-115">它会验证各条消息，根据在源参与方选择的设置重新[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="c12d4-115">It validates the individual messages, again based on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
4. <span data-ttu-id="c12d4-116">接口引擎生成批消息，根据中的确认定义设置确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]的参与方的配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="c12d4-116">The Interface Engine generates an acknowledgment for the batch message, based on the acknowledgment definition settings in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Editor for the party.</span></span> <span data-ttu-id="c12d4-117">在这种情况下，选择原始确认模式，因此接口引擎在验证消息标头和正文后会生成消息批的单个应用程序接受确认。</span><span class="sxs-lookup"><span data-stu-id="c12d4-117">In this case, you select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for the message batch after validating both the message header and body.</span></span> <span data-ttu-id="c12d4-118">引擎生成确认基于 ACK_024_GLO_DEF 架构、 在确认 MSA2 字段中输入"AA"、 在 MSH3，输入目标参与方和 MSH5 中输入的源参与方。</span><span class="sxs-lookup"><span data-stu-id="c12d4-118">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5. <span data-ttu-id="c12d4-119">确认批处理到源参与方通过文件的接口引擎路由发送适配器设置来处理确认。</span><span class="sxs-lookup"><span data-stu-id="c12d4-119">The Interface Engine routes the acknowledgment batch to the source party through a FILE send adapter set up to process acknowledgments.</span></span> <span data-ttu-id="c12d4-120">在这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将批处理路由到 \Tutorial_BatchACKDrop 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c12d4-120">In this case, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] routes the batch to the \Tutorial_BatchACKDrop folder.</span></span>  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="c12d4-121">将发送到目标消息批次为指定目标参与方，在此情况下文件夹 \Tutorial_BTAHL7Drop。</span><span class="sxs-lookup"><span data-stu-id="c12d4-121">sends the message batch to the destination specified for the destination party, in this case the folder \Tutorial_BTAHL7Drop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c12d4-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="c12d4-122">In This Section</span></span>  
  
-   [<span data-ttu-id="c12d4-123">步骤 1：为入站批处理/出站批处理配置参与方信息</span><span class="sxs-lookup"><span data-stu-id="c12d4-123">Step 1: Configure Party Information for Batch In/Batch Out</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [<span data-ttu-id="c12d4-124">步骤 2：修改或创建发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="c12d4-124">Step 2: Modify or Create the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="c12d4-125">步骤 3：测试入站批处理/出站批处理方案</span><span class="sxs-lookup"><span data-stu-id="c12d4-125">Step 3: Test the Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)