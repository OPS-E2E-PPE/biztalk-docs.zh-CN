---
title: 消息批处理 |Microsoft 文档
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
ms.openlocfilehash: 849f14113d5a5e4776c303ef7a5ea4e1e50a552b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204645"
---
# <a name="message-batching"></a><span data-ttu-id="a08c0-102">消息批处理</span><span class="sxs-lookup"><span data-stu-id="a08c0-102">Message Batching</span></span>
<span data-ttu-id="a08c0-103">协议标准、 计划问题或消息大小限制可能会促使对消息进行批处理的需求。</span><span class="sxs-lookup"><span data-stu-id="a08c0-103">Protocol standards, scheduling issues, or message size limitations may motivate the need to batch messages.</span></span> <span data-ttu-id="a08c0-104">运行状况级别七 (HL7) 批处理包含包围在 HL7 批处理标头和批处理尾的消息。</span><span class="sxs-lookup"><span data-stu-id="a08c0-104">A Health Level Seven (HL7) batch consists of messages enclosed by an HL7 batch header and batch trailer.</span></span> <span data-ttu-id="a08c0-105">消息分隔符分隔批处理中的单个消息。</span><span class="sxs-lookup"><span data-stu-id="a08c0-105">Message separators separate the individual messages within the batch.</span></span>  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="a08c0-106">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]支持下列三个消息批处理方案：</span><span class="sxs-lookup"><span data-stu-id="a08c0-106"> [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] supports the following three message batching scenarios:</span></span>  
  
-   <span data-ttu-id="a08c0-107">**零碎的入站的批处理**。</span><span class="sxs-lookup"><span data-stu-id="a08c0-107">**Fragmented inbound batch**.</span></span> <span data-ttu-id="a08c0-108">在此方案中，BTAHL7 接收的 HL7 消息批次，并随后将各条消息路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="a08c0-108">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
-   <span data-ttu-id="a08c0-109">**在批处理 / 批处理出**。在此方案中，BTAHL7 接收 HL7 消息批、 验证批处理中的单个消息和将消息批然后路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="a08c0-109">**Batch in/batch out**. In this scenario, BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
-   <span data-ttu-id="a08c0-110">**创建批处理或出站批处理**。</span><span class="sxs-lookup"><span data-stu-id="a08c0-110">**Create batch or outbound batching**.</span></span> <span data-ttu-id="a08c0-111">在此方案中，BTAHL7 接收单个消息，并将它们路由到目标系统之前对它们进行批处理。</span><span class="sxs-lookup"><span data-stu-id="a08c0-111">In this scenario, BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a08c0-112">BTAHL7 不会启用默认情况下的出站批处理消息批处理。</span><span class="sxs-lookup"><span data-stu-id="a08c0-112">BTAHL7 does not enable message batching for outbound batching by default.</span></span> <span data-ttu-id="a08c0-113">你必须使用 BizTalk 资源管理器首先登记 BTAHL7 批处理业务流程，，然后启动批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="a08c0-113">You must use BizTalk Explorer to first enlist the BTAHL7 batch orchestration, and then start the batch orchestration.</span></span> <span data-ttu-id="a08c0-114">有关启用消息批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。</span><span class="sxs-lookup"><span data-stu-id="a08c0-114">For more information about enabling message batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a08c0-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="a08c0-115">In This Section</span></span>  
  
-   [<span data-ttu-id="a08c0-116">零碎的入站的批处理</span><span class="sxs-lookup"><span data-stu-id="a08c0-116">Fragmented Inbound Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [<span data-ttu-id="a08c0-117">配置批处理</span><span class="sxs-lookup"><span data-stu-id="a08c0-117">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [<span data-ttu-id="a08c0-118">计划批处理</span><span class="sxs-lookup"><span data-stu-id="a08c0-118">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [<span data-ttu-id="a08c0-119">配置批处理确认</span><span class="sxs-lookup"><span data-stu-id="a08c0-119">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)