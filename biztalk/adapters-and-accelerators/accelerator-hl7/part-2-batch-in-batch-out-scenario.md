---
title: "第 2 部分： 批处理中的批处理方案出 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56ffac38676fe6b163a39ff06be5fe0538800d2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="part-2-batch-inbatch-out-scenario"></a><span data-ttu-id="f8301-102">第 2 部分： 中的批处理 / 批处理出方案</span><span class="sxs-lookup"><span data-stu-id="f8301-102">Part 2: Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="f8301-103">在本教程的此部分中，你会收到 HL7 编码批处理文件，将其传递[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]碎片，而发送到目标的不变的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="f8301-103">In this part of the tutorial, you receive an HL7-encoded batch file, pass it through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without fragmentation, and send the intact batch file to the destination.</span></span> <span data-ttu-id="f8301-104">下图显示了此过程中，流和以下子节介绍工作流。</span><span class="sxs-lookup"><span data-stu-id="f8301-104">The following figure shows the flow of this process, and the subsection below describes the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8301-105">在开始之前在本教程的此部分，请关闭 MllpReceive 和 MllpSend 的工具，可通过关闭命令提示符的第 1 部分中使用。</span><span class="sxs-lookup"><span data-stu-id="f8301-105">Before starting this part of the tutorial, turn off the MllpReceive and MllpSend tools that you used in Part 1, by closing the command prompts.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 <span data-ttu-id="f8301-106">**消息在批处理作业中的流动方式在 / 批处理出方案**</span><span class="sxs-lookup"><span data-stu-id="f8301-106">**How messages flow in the Batch In/Batch Out scenario**</span></span>  
  
 <span data-ttu-id="f8301-107">此方案包括以下工作流：</span><span class="sxs-lookup"><span data-stu-id="f8301-107">This scenario includes the following workflow:</span></span>  
  
1.  <span data-ttu-id="f8301-108">工作流一开始时的业务线应用程序发送消息批为[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 集成引擎使用 FILE 协议。</span><span class="sxs-lookup"><span data-stu-id="f8301-108">The workflow begins when a line-of-business application sends a message batch to the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Integration Engine using the FILE protocol.</span></span> <span data-ttu-id="f8301-109">批处理包含两个版本的 ADT ^ A03 消息。</span><span class="sxs-lookup"><span data-stu-id="f8301-109">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="f8301-110">源应用程序所属 Tutorial_BatchSource 方。</span><span class="sxs-lookup"><span data-stu-id="f8301-110">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2.  <span data-ttu-id="f8301-111">集成引擎接收文件上的批处理接收端口，并验证消息批处理。</span><span class="sxs-lookup"><span data-stu-id="f8301-111">The Integration Engine receives the batch on a FILE receive port, and validates the message batch.</span></span> <span data-ttu-id="f8301-112">(的验证级别取决于为中的源方选择设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。)</span><span class="sxs-lookup"><span data-stu-id="f8301-112">(The level of validation depends on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.)</span></span>  
  
3.  <span data-ttu-id="f8301-113">基于中的设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]禁用批处理碎片当事方，接口引擎的配置资源管理器不会转换为单个消息，分析批处理，但会作为批处理批处理。</span><span class="sxs-lookup"><span data-stu-id="f8301-113">Based on a setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer that disables batch fragmentation for the party, the Interface Engine does not parse the batch into individual messages, but leaves the batch as a batch.</span></span> <span data-ttu-id="f8301-114">它会验证各条消息，根据为中的源方选择设置重新[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="f8301-114">It validates the individual messages, again based on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
4.  <span data-ttu-id="f8301-115">接口引擎生成基于中的确认定义设置批处理消息的确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]方的配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="f8301-115">The Interface Engine generates an acknowledgment for the batch message, based on the acknowledgment definition settings in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Editor for the party.</span></span> <span data-ttu-id="f8301-116">在这种情况下，选择原始确认模式，以便接口引擎生成在验证的消息标头和正文之后消息批处理的单个应用程序接受确认。</span><span class="sxs-lookup"><span data-stu-id="f8301-116">In this case, you select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for the message batch after validating both the message header and body.</span></span> <span data-ttu-id="f8301-117">引擎生成基于 ACK_024_GLO_DEF 架构该确认，该确认 MSA2 字段中输入"AA"，在 MSH3，输入目标方并在 MSH5 输入源方。</span><span class="sxs-lookup"><span data-stu-id="f8301-117">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5.  <span data-ttu-id="f8301-118">确认批处理到源方通过文件的接口引擎路由发送适配器设置来处理确认。</span><span class="sxs-lookup"><span data-stu-id="f8301-118">The Interface Engine routes the acknowledgment batch to the source party through a FILE send adapter set up to process acknowledgments.</span></span> <span data-ttu-id="f8301-119">在这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将批处理路由到 \Tutorial_BatchACKDrop 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f8301-119">In this case, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] routes the batch to the \Tutorial_BatchACKDrop folder.</span></span>  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="f8301-120">将发送到目标消息批处理为指定目标方中，在此情况下文件夹 \Tutorial_BTAHL7Drop。</span><span class="sxs-lookup"><span data-stu-id="f8301-120"> sends the message batch to the destination specified for the destination party, in this case the folder \Tutorial_BTAHL7Drop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8301-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="f8301-121">In This Section</span></span>  
  
-   [<span data-ttu-id="f8301-122">步骤 1： 配置对批次中的当事方信息/批处理出</span><span class="sxs-lookup"><span data-stu-id="f8301-122">Step 1: Configure Party Information for Batch In/Batch Out</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [<span data-ttu-id="f8301-123">步骤 2： 修改或创建发送方和接收端口</span><span class="sxs-lookup"><span data-stu-id="f8301-123">Step 2: Modify or Create the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="f8301-124">步骤 3： 测试中的批处理/批处理出方案</span><span class="sxs-lookup"><span data-stu-id="f8301-124">Step 3: Test the Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)