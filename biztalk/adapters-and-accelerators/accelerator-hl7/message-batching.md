---
title: 消息批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f487d479036f9946dbd32ff9444d8cd714a0a1f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303827"
---
# <a name="message-batching"></a><span data-ttu-id="cf23d-102">消息批处理</span><span class="sxs-lookup"><span data-stu-id="cf23d-102">Message Batching</span></span>
<span data-ttu-id="cf23d-103">协议标准、 计划问题或消息大小限制可能会促使对消息进行批处理的需求。</span><span class="sxs-lookup"><span data-stu-id="cf23d-103">Protocol standards, scheduling issues, or message size limitations may motivate the need to batch messages.</span></span> <span data-ttu-id="cf23d-104">运行状况级别 7 (HL7) 批处理包含包围在 HL7 批处理标头和尾部批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="cf23d-104">A Health Level Seven (HL7) batch consists of messages enclosed by an HL7 batch header and batch trailer.</span></span> <span data-ttu-id="cf23d-105">消息分隔符分隔各条消息的批处理中。</span><span class="sxs-lookup"><span data-stu-id="cf23d-105">Message separators separate the individual messages within the batch.</span></span>  
  
 <span data-ttu-id="cf23d-106">Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]批处理方案支持以下三个消息：</span><span class="sxs-lookup"><span data-stu-id="cf23d-106">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] supports the following three message batching scenarios:</span></span>  
  
-   <span data-ttu-id="cf23d-107">**零碎的入站的批处理**。</span><span class="sxs-lookup"><span data-stu-id="cf23d-107">**Fragmented inbound batch**.</span></span> <span data-ttu-id="cf23d-108">在此方案中，BTAHL7 接收 HL7 消息批，，然后将各个消息路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="cf23d-108">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
-   <span data-ttu-id="cf23d-109">**在批处理 / 出站批处理**。在此方案中，BTAHL7 接收 HL7 消息批、 验证在批处理中的单个消息并将消息批然后路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="cf23d-109">**Batch in/batch out**. In this scenario, BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
-   <span data-ttu-id="cf23d-110">**创建批处理或出站批处理**。</span><span class="sxs-lookup"><span data-stu-id="cf23d-110">**Create batch or outbound batching**.</span></span> <span data-ttu-id="cf23d-111">在此方案中，BTAHL7 接收单个消息，并将它们路由到目标系统之前对其进行批量。</span><span class="sxs-lookup"><span data-stu-id="cf23d-111">In this scenario, BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf23d-112">BTAHL7 不会启用默认情况下的出站批处理的消息批处理。</span><span class="sxs-lookup"><span data-stu-id="cf23d-112">BTAHL7 does not enable message batching for outbound batching by default.</span></span> <span data-ttu-id="cf23d-113">您必须使用 BizTalk 浏览器第一次登记 BTAHL7 批处理业务流程，并启动批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="cf23d-113">You must use BizTalk Explorer to first enlist the BTAHL7 batch orchestration, and then start the batch orchestration.</span></span> <span data-ttu-id="cf23d-114">有关启用消息批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。</span><span class="sxs-lookup"><span data-stu-id="cf23d-114">For more information about enabling message batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf23d-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf23d-115">In This Section</span></span>  
  
-   [<span data-ttu-id="cf23d-116">零碎的入站批处理</span><span class="sxs-lookup"><span data-stu-id="cf23d-116">Fragmented Inbound Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [<span data-ttu-id="cf23d-117">配置批处理</span><span class="sxs-lookup"><span data-stu-id="cf23d-117">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [<span data-ttu-id="cf23d-118">计划批处理</span><span class="sxs-lookup"><span data-stu-id="cf23d-118">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [<span data-ttu-id="cf23d-119">配置批处理确认</span><span class="sxs-lookup"><span data-stu-id="cf23d-119">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)