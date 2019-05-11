---
title: 零碎的入站的批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac8e0d99bfa9ea8696a7cd9f6eeed8a6be16006d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267815"
---
# <a name="fragmented-inbound-batch"></a><span data-ttu-id="9e9b2-102">零碎的入站的批处理</span><span class="sxs-lookup"><span data-stu-id="9e9b2-102">Fragmented Inbound Batch</span></span>
<span data-ttu-id="9e9b2-103">你可以配置[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]若要接收消息批，从批处理中提取消息，然后将各个消息路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-103">You can configure [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive a message batch, extract the messages from the batch, and then route the individual messages to the destination system.</span></span> <span data-ttu-id="9e9b2-104">如果启用碎片，为单个消息; 的入站的批处理片段否则为批处理是处理，并作为单个 'batch' 或交换路由。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-104">If you enable fragmentation, the inbound batch fragments into individual messages; otherwise, the batch is processed and routed as a single 'batch' or interchange.</span></span> <span data-ttu-id="9e9b2-105">BTAHL7 配置资源管理器用于启用批处理。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-105">You use BTAHL7 Configuration Explorer to enable batching.</span></span> <span data-ttu-id="9e9b2-106">有关启用批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-106">For more information about enabling batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
 <span data-ttu-id="9e9b2-107">下面介绍典型零碎的入站的批处理方案：</span><span class="sxs-lookup"><span data-stu-id="9e9b2-107">The following describes a typical fragmented inbound batch scenario:</span></span>  
  
1.  <span data-ttu-id="9e9b2-108">在系统 A 上运行的业务线应用程序将消息批发送到 BTAHL7。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-108">A line-of-business application, running on System A, sends a message batch to BTAHL7.</span></span>  
  
     <span data-ttu-id="9e9b2-109">批处理消息，可以在两个不同的格式。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-109">Batch messages can be in two different formats.</span></span> <span data-ttu-id="9e9b2-110">BTAHL7 可以处理以下格式：</span><span class="sxs-lookup"><span data-stu-id="9e9b2-110">BTAHL7 can process the following formats:</span></span>  
  
    -   <span data-ttu-id="9e9b2-111">格式 1:包括一个文件标头和尾部 (FHS/FTS) 对一个或多个批处理标头和尾部 (BHS/BTS)。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-111">Format 1: Includes one file header and trailer (FHS/FTS) pair and one or more batch header and trailers (BHS/BTS).</span></span>  
  
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
  
    -   <span data-ttu-id="9e9b2-112">格式 2:不包含 HL7 定义文件和批处理包装器，并挂起一系列是流中的消息。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-112">Format 2: Does not contain HL7 defined file and batch wrappers, and suspends a series are messages in a stream.</span></span>  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  <span data-ttu-id="9e9b2-113">BTAHL7 批中创建各条消息，然后验证对相应架构的单个消息。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-113">BTAHL7 creates individual messages from the batch and then verifies the individual messages against the appropriate schemas.</span></span>  
  
3.  <span data-ttu-id="9e9b2-114">BTAHL7 将单独的确认消息发送到系统 A，从批处理中提取每条消息。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-114">BTAHL7 sends a separate acknowledgment message to System A for each message extracted from the batch.</span></span>  
  
4.  <span data-ttu-id="9e9b2-115">BTAHL7 将单个消息路由到目标系统基于各条消息，而不是消息批处理标头中的路由信息。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-115">BTAHL7 routes the individual messages to the destination system based on the routing information in the individual messages, rather than the message batch header.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e9b2-116">BTAHL7 不会验证 batch 和文件的标头/尾部时**FHS3**字段 （发送方） 包含贸易合作伙伴的已启用的碎片。</span><span class="sxs-lookup"><span data-stu-id="9e9b2-116">BTAHL7 does not validate batch and file headers/trailers when the **FHS3** field (sending party) contains a trading partner that has fragmentation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e9b2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e9b2-117">See Also</span></span>  
 [<span data-ttu-id="9e9b2-118">配置批处理</span><span class="sxs-lookup"><span data-stu-id="9e9b2-118">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)