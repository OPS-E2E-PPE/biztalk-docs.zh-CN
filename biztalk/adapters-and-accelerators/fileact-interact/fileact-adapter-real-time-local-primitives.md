---
title: FileAct 适配器实时本地基元 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef4da4f8-3de2-4d35-8f8a-1e12937e52a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcc0f1d093d56b8cd4580ef068007d02aab6346f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223069"
---
# <a name="fileact-adapter-real-time-local-primitives"></a><span data-ttu-id="3c6eb-102">FileAct 适配器实时本地基元</span><span class="sxs-lookup"><span data-stu-id="3c6eb-102">FileAct Adapter Real-Time Local Primitives</span></span>
<span data-ttu-id="3c6eb-103">本地基元涉及两条消息，该客户端 SWIFTNet 链接 (SNL) 和本地 FileAct 子系统之间交换。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-103">Local primitives involve two messages each, which are exchanged between the client SWIFTNet Link (SNL) and the local FileAct subsystem.</span></span>  
  
 <span data-ttu-id="3c6eb-104">下图显示 FileAct 本地基元。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-104">The following figure shows the FileAct local primitives.</span></span>  
  
 <span data-ttu-id="3c6eb-105">![FileAct 本地基元](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")</span><span class="sxs-lookup"><span data-stu-id="3c6eb-105">![FileAct local primitives](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")</span></span>  
  
## <a name="get-status-for-a-single-transfer"></a><span data-ttu-id="3c6eb-106">获得单个传输状态</span><span class="sxs-lookup"><span data-stu-id="3c6eb-106">Get Status for a Single Transfer</span></span>  
 <span data-ttu-id="3c6eb-107">获取状态基元检索有关本地的持久性上下文从一个传输的状态信息。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-107">The Get Status primitive retrieves status information concerning one transfer from the local persistent context.</span></span>  
  
## <a name="subscribe-to-transfer-events"></a><span data-ttu-id="3c6eb-108">订阅通知，以便传输事件</span><span class="sxs-lookup"><span data-stu-id="3c6eb-108">Subscribe to Transfer Events</span></span>  
 <span data-ttu-id="3c6eb-109">基于事件的事件中，通过使用订阅事件基元可能接收到渐进式传输状态信息。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-109">Progressive transfer status information may be received on an event-by-event basis by using the Subscribe Event primitive.</span></span> <span data-ttu-id="3c6eb-110">每个文件传输可能链接到已命名实体的协商期间调用的事件终结点。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-110">Each file transfer may be linked to a named entity called an event endpoint during the negotiation.</span></span> <span data-ttu-id="3c6eb-111">订阅事件基元时，将调用的事件服务器将定向为一个此类事件终结点为其自身的所有事件报告。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-111">An event server that invokes the Subscribe Event primitive directs all the event reports for one such an event endpoint to itself.</span></span>  
  
 <span data-ttu-id="3c6eb-112">事件服务器可以订阅特征 （不同级别的详细信息，以及不同的事件类型）。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-112">An event server can subscribe to characteristics (different levels of detail, as well as to different event types).</span></span>  
  
 <span data-ttu-id="3c6eb-113">事件服务器可能会调用该基元多次订阅多个事件终结点。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-113">An event server may invoke the primitive multiple times to subscribe to multiple event endpoints.</span></span> <span data-ttu-id="3c6eb-114">只能有一个事件服务器可能在给定时间订阅特定事件的任何终结点。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-114">Only one event server may subscribe to any particular event endpoint at a given time.</span></span> <span data-ttu-id="3c6eb-115">此外，事件服务器可以调用该基元的同一个事件终结点的多个时间，个更改特性。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-115">Additionally, an event server can invoke the primitive multiple times for the same event endpoint for changing the characteristics.</span></span>  
  
## <a name="receive-transfer-events"></a><span data-ttu-id="3c6eb-116">接收传输事件</span><span class="sxs-lookup"><span data-stu-id="3c6eb-116">Receive Transfer Events</span></span>  
 <span data-ttu-id="3c6eb-117">接收传输事件是处理有关传输正在进行中的事件按事件状态信息的基元。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-117">Receive Transfer Events is the primitive that handles the event-by-event status information concerning transfers-in-progress.</span></span> <span data-ttu-id="3c6eb-118">它的响应设置订阅事件基元的订阅中的条款。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-118">It responds to the terms of a subscription that is set up by the Subscribe Event primitive.</span></span> <span data-ttu-id="3c6eb-119">可以在传输发送或接收端实现此基元。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-119">This primitive can be implemented at the sending or receiving side of a transfer.</span></span>  
  
## <a name="abort-transfer"></a><span data-ttu-id="3c6eb-120">中止传输</span><span class="sxs-lookup"><span data-stu-id="3c6eb-120">Abort Transfer</span></span>  
 <span data-ttu-id="3c6eb-121">用户应用程序可能中止传输正在进行使用中止基元。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-121">A user application may abort a transfer-in-progress using the Abort primitive.</span></span> <span data-ttu-id="3c6eb-122">中止基元是可能会执行从发送方或接收方的传输正在进行的基元。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-122">The Abort primitive is a primitive that may be exercised from either the sending-side or the receiving-side of a transfer-in-progress.</span></span> <span data-ttu-id="3c6eb-123">当启动或接受传输时，每个端必须建立用作访问密钥才能从其自身保护传输的传输密钥的选项。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-123">When initiating or accepting a transfer, each side has the option of establishing a transfer key that serves as an access key to protect that transfer from its own side.</span></span> <span data-ttu-id="3c6eb-124">如果对进行传输中建立的传输密钥，则它可能未被终止从该端无需提供中止基元的练习中的传输密钥值。</span><span class="sxs-lookup"><span data-stu-id="3c6eb-124">If a transfer key is established for a transfer-in-progress, it may not be aborted from that side without supplying the transfer key value in the exercise of the Abort primitive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c6eb-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c6eb-125">See Also</span></span>  
 <span data-ttu-id="3c6eb-126">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="3c6eb-126">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="3c6eb-127">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="3c6eb-127">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="3c6eb-128">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="3c6eb-128">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="3c6eb-129">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="3c6eb-129">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="3c6eb-130">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="3c6eb-130">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="3c6eb-131">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="3c6eb-131">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="3c6eb-132">[FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="3c6eb-132">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="3c6eb-133">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="3c6eb-133">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)