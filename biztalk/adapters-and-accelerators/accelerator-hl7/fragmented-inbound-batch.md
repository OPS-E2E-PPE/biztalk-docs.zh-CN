---
title: "分片入站的批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0807bbe83ea2f477a7e1625488ebbecf578f3adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fragmented-inbound-batch"></a><span data-ttu-id="6bbb2-102">零碎的入站的批处理</span><span class="sxs-lookup"><span data-stu-id="6bbb2-102">Fragmented Inbound Batch</span></span>
<span data-ttu-id="6bbb2-103">你可以配置[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]若要接收消息批，从该批处理，提取消息，然后单个消息路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-103">You can configure [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive a message batch, extract the messages from the batch, and then route the individual messages to the destination system.</span></span> <span data-ttu-id="6bbb2-104">如果启用碎片，到单个消息的入站的批处理片段否则为批处理得到处理，并作为单个 'batch' 或交换路由。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-104">If you enable fragmentation, the inbound batch fragments into individual messages; otherwise, the batch is processed and routed as a single 'batch' or interchange.</span></span> <span data-ttu-id="6bbb2-105">BTAHL7 配置资源管理器用于启用批处理。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-105">You use BTAHL7 Configuration Explorer to enable batching.</span></span> <span data-ttu-id="6bbb2-106">有关启用批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-106">For more information about enabling batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
 <span data-ttu-id="6bbb2-107">下面介绍典型零碎的入站的批处理方案：</span><span class="sxs-lookup"><span data-stu-id="6bbb2-107">The following describes a typical fragmented inbound batch scenario:</span></span>  
  
1.  <span data-ttu-id="6bbb2-108">运行系统 A 的业务线应用程序将消息批发送到 BTAHL7。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-108">A line-of-business application, running on System A, sends a message batch to BTAHL7.</span></span>  
  
     <span data-ttu-id="6bbb2-109">批处理消息可以在两个不同的格式。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-109">Batch messages can be in two different formats.</span></span> <span data-ttu-id="6bbb2-110">BTAHL7 可以处理以下格式：</span><span class="sxs-lookup"><span data-stu-id="6bbb2-110">BTAHL7 can process the following formats:</span></span>  
  
    -   <span data-ttu-id="6bbb2-111">格式 1： 包含一个文件标头和尾部 (FHS/FT) 对一个或多个批处理标头和尾部 (BHS/BTS)。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-111">Format 1: Includes one file header and trailer (FHS/FTS) pair and one or more batch header and trailers (BHS/BTS).</span></span>  
  
        ```  
        FHS  
        BHS  
        MSH  
        .............  
        MSH  
        ...........  
        BTS  
        BHS  
        MSH  
        ..............  
        MSH  
        ...............  
        BTS  
        FTS  
        ```  
  
    -   <span data-ttu-id="6bbb2-112">格式 2： 不包含 HL7 定义文件和批处理包装器，并挂起一系列流中的消息。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-112">Format 2: Does not contain HL7 defined file and batch wrappers, and suspends a series are messages in a stream.</span></span>  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  <span data-ttu-id="6bbb2-113">BTAHL7 批次中创建单个消息，然后验证针对相应架构的单个消息。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-113">BTAHL7 creates individual messages from the batch and then verifies the individual messages against the appropriate schemas.</span></span>  
  
3.  <span data-ttu-id="6bbb2-114">BTAHL7 批次中提取每条消息将单独的确认消息发送到系统 A。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-114">BTAHL7 sends a separate acknowledgment message to System A for each message extracted from the batch.</span></span>  
  
4.  <span data-ttu-id="6bbb2-115">BTAHL7 将各条消息路由到目标系统基于各条消息，而不是消息批处理标头中的路由信息。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-115">BTAHL7 routes the individual messages to the destination system based on the routing information in the individual messages, rather than the message batch header.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6bbb2-116">BTAHL7 不会验证批处理和文件标头/拖车安排时**FHS3**字段 （发送方） 包含已启用的碎片的贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="6bbb2-116">BTAHL7 does not validate batch and file headers/trailers when the **FHS3** field (sending party) contains a trading partner that has fragmentation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bbb2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bbb2-117">See Also</span></span>  
 [<span data-ttu-id="6bbb2-118">配置批处理</span><span class="sxs-lookup"><span data-stu-id="6bbb2-118">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)