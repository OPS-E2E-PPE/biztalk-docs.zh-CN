---
title: 批处理消息处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f954de27e2e18adbb38a2eeed86557b4752aaa8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65248254"
---
# <a name="batch-message-processing"></a><span data-ttu-id="686a4-102">批处理消息处理</span><span class="sxs-lookup"><span data-stu-id="686a4-102">Batch Message Processing</span></span>
<span data-ttu-id="686a4-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理三种类型的 HL7 2.X 批处理方案：</span><span class="sxs-lookup"><span data-stu-id="686a4-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) handles three types of HL7 2.X batch scenarios:</span></span>  
  
- <span data-ttu-id="686a4-104">零碎的入站的批处理方案。</span><span class="sxs-lookup"><span data-stu-id="686a4-104">Fragmented inbound batch scenario.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="686a4-105">将这些批次分析为单独的输出消息。</span><span class="sxs-lookup"><span data-stu-id="686a4-105">parses these batches into separate output messages.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="686a4-106">零碎的批处理中，将发送确认 (Ack) 为每个消息。</span><span class="sxs-lookup"><span data-stu-id="686a4-106">sends acknowledgments (ACKs) for each message in a fragmented batch.</span></span>  
  
- <span data-ttu-id="686a4-107">在批处理 / 批处理方案。</span><span class="sxs-lookup"><span data-stu-id="686a4-107">Batch in/batch out scenario.</span></span> <span data-ttu-id="686a4-108">这些是入站批处理的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不进行分段，但通过，并且将保持不变的批作为发送。</span><span class="sxs-lookup"><span data-stu-id="686a4-108">These are in-bound batches that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fragment, but passes through and sends as an intact batch.</span></span> <span data-ttu-id="686a4-109">如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送确认的批处理，确认包括版本 id。</span><span class="sxs-lookup"><span data-stu-id="686a4-109">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK for the batch, the ACK includes a version ID.</span></span>  
  
- <span data-ttu-id="686a4-110">创建批处理方案。</span><span class="sxs-lookup"><span data-stu-id="686a4-110">Create-batch scenario.</span></span> <span data-ttu-id="686a4-111">在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]合并输出批处理到不同的输入的消息。</span><span class="sxs-lookup"><span data-stu-id="686a4-111">In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combines separate input messages into an output batch.</span></span>  
  
  <span data-ttu-id="686a4-112">可以设置两种方式之一中的批的格式：</span><span class="sxs-lookup"><span data-stu-id="686a4-112">You can format batches in either of two ways:</span></span>  
  
- <span data-ttu-id="686a4-113">使用文件标头和尾部 (FHS/FTS) 和批头部和尾部 (BHS/BTS)。</span><span class="sxs-lookup"><span data-stu-id="686a4-113">With a file header and trailer (FHS/FTS) and a batch header and trailer (BHS/BTS).</span></span>  
  
- <span data-ttu-id="686a4-114">与任何文件或批处理标头/尾部。</span><span class="sxs-lookup"><span data-stu-id="686a4-114">With no file or batch headers/trailers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="686a4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="686a4-115">See Also</span></span>  
 <span data-ttu-id="686a4-116">[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="686a4-116">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 <span data-ttu-id="686a4-117">[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="686a4-117">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="686a4-118">[第 1 部分：零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="686a4-118">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 <span data-ttu-id="686a4-119">[第 2 部分：在批处理 / 批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="686a4-119">[Part 2: Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span></span>  
 <span data-ttu-id="686a4-120">[第 3 部分：创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="686a4-120">[Part 3: Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span></span>  
 [<span data-ttu-id="686a4-121">消息处理</span><span class="sxs-lookup"><span data-stu-id="686a4-121">Message Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)