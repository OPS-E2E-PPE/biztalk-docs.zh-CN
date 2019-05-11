---
title: 批处理教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9576d8406aa7bc0988fe961ce9b6750791fa77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251664"
---
# <a name="batching-tutorial"></a><span data-ttu-id="d8110-102">批处理教程</span><span class="sxs-lookup"><span data-stu-id="d8110-102">Batching Tutorial</span></span>
<span data-ttu-id="d8110-103">本教程提供了分步过程使用 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]来接收和发送批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="d8110-103">This tutorial provides step-by-step procedures for using Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive and send batched messages.</span></span> <span data-ttu-id="d8110-104">批处理为单个复合消息包括接收和/或发送的一组各个消息 （或确认）。</span><span class="sxs-lookup"><span data-stu-id="d8110-104">Batching involves receiving and/or sending a group of individual messages (or acknowledgments) as a single composite message.</span></span>  
  
 <span data-ttu-id="d8110-105">BTAHL7 支持以下三种消息批处理方案：</span><span class="sxs-lookup"><span data-stu-id="d8110-105">BTAHL7 supports the following three message batching scenarios:</span></span>  
  
- <span data-ttu-id="d8110-106">**零碎的入站的批处理**。</span><span class="sxs-lookup"><span data-stu-id="d8110-106">**Fragmented inbound batch**.</span></span> <span data-ttu-id="d8110-107">在此方案中，BTAHL7 接收 HL7 消息批，，然后将各个消息路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="d8110-107">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
- <span data-ttu-id="d8110-108">**在批处理 / 出站批处理**。BTAHL7 接收 HL7 消息批、 验证在批处理中的单个消息并将消息批然后路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="d8110-108">**Batch in/batch out**. BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
- <span data-ttu-id="d8110-109">**创建批次 （或出站批处理）**。</span><span class="sxs-lookup"><span data-stu-id="d8110-109">**Create batch (or outbound batching)**.</span></span> <span data-ttu-id="d8110-110">BTAHL7 接收单个消息，并将它们路由到目标系统之前对其进行批量。</span><span class="sxs-lookup"><span data-stu-id="d8110-110">BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
  <span data-ttu-id="d8110-111">本教程包括三个批处理方案的每个部分。</span><span class="sxs-lookup"><span data-stu-id="d8110-111">This tutorial includes parts for each of the three batching scenarios.</span></span> <span data-ttu-id="d8110-112">使用本教程中提供; 的顺序的三个部分第 1 部分包含有关第 2 部分和第 3 部分的先决条件步骤。</span><span class="sxs-lookup"><span data-stu-id="d8110-112">Use the three parts of the tutorial in the order provided; part 1 contains prerequisite steps for part 2 and part 3.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8110-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="d8110-113">In This Section</span></span>  
  
-   [<span data-ttu-id="d8110-114">为使用批处理教程做准备</span><span class="sxs-lookup"><span data-stu-id="d8110-114">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [<span data-ttu-id="d8110-115">第 1 部分：零碎的入站批处理方案</span><span class="sxs-lookup"><span data-stu-id="d8110-115">Part 1: Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [<span data-ttu-id="d8110-116">第 2 部分：入站批处理/出站批处理方案</span><span class="sxs-lookup"><span data-stu-id="d8110-116">Part 2: Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [<span data-ttu-id="d8110-117">第 3 部分：Create-Batch 方案</span><span class="sxs-lookup"><span data-stu-id="d8110-117">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)