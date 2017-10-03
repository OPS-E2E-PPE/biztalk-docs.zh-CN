---
title: "第 1 部分： 零碎的入站的批处理方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8891bd09c803c77e1878b304f5db5b71a26ab9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a><span data-ttu-id="59e86-102">第 1 部分： 零碎的入站的批处理方案</span><span class="sxs-lookup"><span data-stu-id="59e86-102">Part 1: Fragmented Inbound Batch Scenario</span></span>
<span data-ttu-id="59e86-103">在本教程的此部分中，你将接收 HL7 编码批、 片段转换为单个消息，和各条消息发送到目标。</span><span class="sxs-lookup"><span data-stu-id="59e86-103">In this part of the tutorial, you receive an HL7-encoded batch, fragment it into individual messages, and send the individual messages to a destination.</span></span> <span data-ttu-id="59e86-104">下图显示在此过程中的流。</span><span class="sxs-lookup"><span data-stu-id="59e86-104">The following figure shows the flow of this process.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 <span data-ttu-id="59e86-105">此方案包括以下工作流：</span><span class="sxs-lookup"><span data-stu-id="59e86-105">This scenario includes the following workflow:</span></span>  
  
1.  <span data-ttu-id="59e86-106">工作流一开始时的业务线应用程序发送消息批为[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]集成引擎使用的最小较低层协议 (MLLP) 协议。</span><span class="sxs-lookup"><span data-stu-id="59e86-106">The workflow begins when a line-of-business application sends a message batch to the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Integration Engine using the Minimal Lower Layer Protocol (MLLP) protocol.</span></span> <span data-ttu-id="59e86-107">批处理包含两个版本的 ADT ^ A03 消息。</span><span class="sxs-lookup"><span data-stu-id="59e86-107">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="59e86-108">源应用程序所属 Tutorial_BatchSource 方。</span><span class="sxs-lookup"><span data-stu-id="59e86-108">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2.  <span data-ttu-id="59e86-109">接口引擎接收上 MLLP 批处理接收端口，并验证消息批处理。</span><span class="sxs-lookup"><span data-stu-id="59e86-109">The Interface Engine receives the batch on an MLLP receive port, and validates the message batch.</span></span> <span data-ttu-id="59e86-110">（的验证级别取决于为源方 BTAHL7 配置资源管理器中选择的设置。）</span><span class="sxs-lookup"><span data-stu-id="59e86-110">(The level of validation depends on settings selected for the source party in BTAHL7 Configuration Explorer.)</span></span>  
  
3.  <span data-ttu-id="59e86-111">根据 BTAHL7 配置资源管理器，使批处理碎片中的设置，接口引擎将分析批处理为两个单独 ADT ^ A03 消息。</span><span class="sxs-lookup"><span data-stu-id="59e86-111">Based on a setting in BTAHL7 Configuration Explorer that enables batch fragmentation, the Interface Engine parses the batch into two individual ADT^A03 messages.</span></span> <span data-ttu-id="59e86-112">它会验证各条消息，根据为 BTAHL7 配置资源管理器中的源方选择设置。</span><span class="sxs-lookup"><span data-stu-id="59e86-112">It validates the individual messages, again based on settings selected for the source party in BTAHL7 Configuration Explorer.</span></span>  
  
4.  <span data-ttu-id="59e86-113">接口引擎生成基于 BTAHL7 配置资源管理器中的确认定义设置的每个消息的确认。</span><span class="sxs-lookup"><span data-stu-id="59e86-113">The Interface Engine generates an acknowledgment for each message, based on the acknowledgment definition settings in BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="59e86-114">在本教程中，将选择原始确认模式，因此接口引擎在验证的消息标头和正文之后生成每条消息将单个应用程序接受确认。</span><span class="sxs-lookup"><span data-stu-id="59e86-114">In this tutorial, you will select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for each message after validating both the message header and body.</span></span> <span data-ttu-id="59e86-115">引擎生成基于 ACK_024_GLO_DEF 架构该确认，该确认 MSA2 字段中输入"AA"，在 MSH3，输入目标方并在 MSH5 输入源方。</span><span class="sxs-lookup"><span data-stu-id="59e86-115">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5.  <span data-ttu-id="59e86-116">接口引擎将放 MLLP 包装每个确认并路由到源确认方通过 MLLP 发送适配器将设置为处理确认。</span><span class="sxs-lookup"><span data-stu-id="59e86-116">The Interface Engine places MLLP wrappers around each acknowledgment, and routes the acknowledgments to the source party through an MLLP send adapter set up to process acknowledgments.</span></span>  
  
6.  <span data-ttu-id="59e86-117">接口引擎将放 MLLP 包装每个消息，并单独到 MLLP 每条消息发送端口设置来处理非确认消息的路由。</span><span class="sxs-lookup"><span data-stu-id="59e86-117">The Interface Engine places MLLP wrappers around each message, and routes each message individually to an MLLP send port set up to process non-acknowledgment messages.</span></span>  
  
7.  <span data-ttu-id="59e86-118">BTAHL7 将通过另一个 MLLP 发送端口的每条消息发送到其 MSH5 字段中指定的目标。</span><span class="sxs-lookup"><span data-stu-id="59e86-118">BTAHL7 sends each message through another MLLP send port to the destination specified in its MSH5 field.</span></span>  
  
8.  <span data-ttu-id="59e86-119">目标方将发送到 BTAHL7 应用程序接受它接收每条消息的确认。</span><span class="sxs-lookup"><span data-stu-id="59e86-119">The destination party sends to BTAHL7 an application-accept acknowledgment for each message that it received.</span></span>  
  
9. <span data-ttu-id="59e86-120">接口引擎接收每个确认。</span><span class="sxs-lookup"><span data-stu-id="59e86-120">The Interface Engine receives each acknowledgment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59e86-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="59e86-121">In This Section</span></span>  
  
-   [<span data-ttu-id="59e86-122">步骤 1： 添加标头和确认架构</span><span class="sxs-lookup"><span data-stu-id="59e86-122">Step 1: Add Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="59e86-123">步骤 2： 添加常见 v2.3.1 架构</span><span class="sxs-lookup"><span data-stu-id="59e86-123">Step 2: Add Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="59e86-124">步骤 3： 添加触发器事件 （消息） 架构</span><span class="sxs-lookup"><span data-stu-id="59e86-124">Step 3: Add a Trigger Event (Message) Schema</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [<span data-ttu-id="59e86-125">步骤 4： 创建用于接受批处理消息接收端口</span><span class="sxs-lookup"><span data-stu-id="59e86-125">Step 4: Create a Receive Port for Accepting the Batch Message</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [<span data-ttu-id="59e86-126">步骤 5： 创建发送端口将消息传递</span><span class="sxs-lookup"><span data-stu-id="59e86-126">Step 5: Create a Send Port to Deliver Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [<span data-ttu-id="59e86-127">步骤 6： 创建发送端口，以提供确认</span><span class="sxs-lookup"><span data-stu-id="59e86-127">Step 6: Create a Send Port to Deliver Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [<span data-ttu-id="59e86-128">步骤 7： 创建并配置源方</span><span class="sxs-lookup"><span data-stu-id="59e86-128">Step 7: Create and Configure a Source Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [<span data-ttu-id="59e86-129">步骤 8： 重新启动 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="59e86-129">Step 8: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="59e86-130">步骤 9： 验证零碎的入站的批处理方案</span><span class="sxs-lookup"><span data-stu-id="59e86-130">Step 9: Verify the Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)