---
title: 批处理消息 |Microsoft 文档
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
ms.openlocfilehash: aad80bb8fe9a59163ee17e7862bece728fdc52b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204757"
---
# <a name="batch-message-processing"></a><span data-ttu-id="decd7-102">批处理消息处理</span><span class="sxs-lookup"><span data-stu-id="decd7-102">Batch Message Processing</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="decd7-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理三种类型的 HL7 2.X 批处理方案：</span><span class="sxs-lookup"><span data-stu-id="decd7-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) handles three types of HL7 2.X batch scenarios:</span></span>  
  
-   <span data-ttu-id="decd7-104">零碎的入站的批处理方案。</span><span class="sxs-lookup"><span data-stu-id="decd7-104">Fragmented inbound batch scenario.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="decd7-105">将这些批分析为单独的输出消息。</span><span class="sxs-lookup"><span data-stu-id="decd7-105"> parses these batches into separate output messages.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="decd7-106">零碎的批次中发送确认 (Ack) 中的为每条消息。</span><span class="sxs-lookup"><span data-stu-id="decd7-106"> sends acknowledgments (ACKs) for each message in a fragmented batch.</span></span>  
  
-   <span data-ttu-id="decd7-107">在批处理 / 批处理出方案。</span><span class="sxs-lookup"><span data-stu-id="decd7-107">Batch in/batch out scenario.</span></span> <span data-ttu-id="decd7-108">这些是入站批处理，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]并非片段，但传递并以保持不变的批处理形式发送。</span><span class="sxs-lookup"><span data-stu-id="decd7-108">These are in-bound batches that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fragment, but passes through and sends as an intact batch.</span></span> <span data-ttu-id="decd7-109">如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送的批处理，ACK 的 ACK 包括版本 id。</span><span class="sxs-lookup"><span data-stu-id="decd7-109">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK for the batch, the ACK includes a version ID.</span></span>  
  
-   <span data-ttu-id="decd7-110">创建批处理方案。</span><span class="sxs-lookup"><span data-stu-id="decd7-110">Create-batch scenario.</span></span> <span data-ttu-id="decd7-111">在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]合并到输出批处理多个单独输入的消息。</span><span class="sxs-lookup"><span data-stu-id="decd7-111">In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combines separate input messages into an output batch.</span></span>  
  
 <span data-ttu-id="decd7-112">可以设置两种方式之一中的批的格式：</span><span class="sxs-lookup"><span data-stu-id="decd7-112">You can format batches in either of two ways:</span></span>  
  
-   <span data-ttu-id="decd7-113">使用文件标头和尾部 (FHS/FT) 和批处理标头和尾部 (BHS/BTS)。</span><span class="sxs-lookup"><span data-stu-id="decd7-113">With a file header and trailer (FHS/FTS) and a batch header and trailer (BHS/BTS).</span></span>  
  
-   <span data-ttu-id="decd7-114">与任何文件或批处理标头/拖车安排。</span><span class="sxs-lookup"><span data-stu-id="decd7-114">With no file or batch headers/trailers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="decd7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="decd7-115">See Also</span></span>  
 <span data-ttu-id="decd7-116">[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="decd7-116">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 <span data-ttu-id="decd7-117">[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="decd7-117">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="decd7-118">[第 1 部分： 零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="decd7-118">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 <span data-ttu-id="decd7-119">[第 2 部分： 中的批处理 / 批处理出方案](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="decd7-119">[Part 2: Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span></span>  
 <span data-ttu-id="decd7-120">[第 3 部分： 创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="decd7-120">[Part 3: Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span></span>  
 [<span data-ttu-id="decd7-121">消息处理</span><span class="sxs-lookup"><span data-stu-id="decd7-121">Message Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)