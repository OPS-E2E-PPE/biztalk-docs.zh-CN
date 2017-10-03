---
title: "消息流中发起程序 BTARN |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- initiator BTARN
ms.assetid: 315f3d4c-5e40-4b8e-b135-9da98dc2db1e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85fed6404627fd8abfa9d50e7d56d98ff7306f09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-flow-in-the-initiator-btarn"></a><span data-ttu-id="f9ec0-102">发起方 BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="f9ec0-102">Message Flow in the Initiator BTARN</span></span>
<span data-ttu-id="f9ec0-103">发起方计算机的消息流开始于以其专用格式接收来自后端业务线应用程序的消息。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-103">Message flow on an initiator computer starts with receiving a message from the back-end line-of-business application, in its proprietary format.</span></span> <span data-ttu-id="f9ec0-104">该消息流包括将收到的消息转换为与 RosettaNet 实现框架 (RNIF) 兼容的消息，然后通过 Internet 将经过转换的消息发送到响应方计算机。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-104">It involves converting that message to a RosettaNet Implementation Framework (RNIF)-compliant message, and then sending the message over the Internet to the responder computer.</span></span>  
  
 <span data-ttu-id="f9ec0-105">如果合作伙伴接口流程 (PIP) 是单操作的，则唯一的响应是确认信号消息。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="f9ec0-106">有关单操作消息流的信息，请参阅本主题后面的“初始消息的消息流”。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-106">For information about single-action message flow, see "Flow of an Initiated Message" later in this topic.</span></span> <span data-ttu-id="f9ec0-107">如果 PIP 是双操作的，则除了单操作消息流以外，发起方还将收到响应消息以及确认答复。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-107">If the PIP is double-action, the initiator will receive a response message, and reply with an acknowledgement, in addition to the single-action message flow.</span></span>  
  
 <span data-ttu-id="f9ec0-108">如果 PIP 是异步的，则通过 Internet 的每次消息传输将在不同的 HTTP 连接上进行；</span><span class="sxs-lookup"><span data-stu-id="f9ec0-108">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="f9ec0-109">如果 PIP 是同步的，则每次消息传输将在同一连接上进行，HTTP 适配器将一直保持该连接，直到相应流程完成为止。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-109">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="f9ec0-110">在双操作同步方案中，响应方计算机不会向发起方计算机发送确认消息以响应初始请求消息，</span><span class="sxs-lookup"><span data-stu-id="f9ec0-110">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="f9ec0-111">而是以响应消息作为确认消息。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-111">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-initiator-computer"></a><span data-ttu-id="f9ec0-112">发起方计算机上的 BTARN 组件</span><span class="sxs-lookup"><span data-stu-id="f9ec0-112">BTARN Components on the Initiator Computer</span></span>  
 <span data-ttu-id="f9ec0-113">当消息流通过发起方计算机上的 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 时，下列组件将对消息进行处理：</span><span class="sxs-lookup"><span data-stu-id="f9ec0-113">As a message flows through [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the initiator computer, the following components will process the message:</span></span>  
  
-   <span data-ttu-id="f9ec0-114">SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="f9ec0-114">SQL adapter</span></span>  
  
-   <span data-ttu-id="f9ec0-115">XML 接收管道</span><span class="sxs-lookup"><span data-stu-id="f9ec0-115">XML receive pipeline</span></span>  
  
-   <span data-ttu-id="f9ec0-116">发起方专用流程</span><span class="sxs-lookup"><span data-stu-id="f9ec0-116">Initiator private process</span></span>  
  
-   <span data-ttu-id="f9ec0-117">发起方公用流程</span><span class="sxs-lookup"><span data-stu-id="f9ec0-117">Initiator public process</span></span>  
  
-   <span data-ttu-id="f9ec0-118">XML 发送管道</span><span class="sxs-lookup"><span data-stu-id="f9ec0-118">XML send pipeline</span></span>  
  
-   <span data-ttu-id="f9ec0-119">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="f9ec0-119">HTTP adapter</span></span>  
  
-   <span data-ttu-id="f9ec0-120">RNIFSend.aspx 页</span><span class="sxs-lookup"><span data-stu-id="f9ec0-120">RNIFSend.aspx page</span></span>  
  
 <span data-ttu-id="f9ec0-121">有关这些组件，以及它们如何处理消息的详细信息，请参阅[消息处理中 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-121">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="flow-of-an-initiated-message"></a><span data-ttu-id="f9ec0-122">初始消息的消息流</span><span class="sxs-lookup"><span data-stu-id="f9ec0-122">Flow of an Initiated Message</span></span>  
 <span data-ttu-id="f9ec0-123">下列步骤说明通过发起方 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 计算机的初始消息的消息流。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-123">The following steps describe the message flow of an initiated message through the initiator [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer.</span></span> <span data-ttu-id="f9ec0-124">下图显示了这一过程：</span><span class="sxs-lookup"><span data-stu-id="f9ec0-124">The following figure shows this process.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")  
  
1.  <span data-ttu-id="f9ec0-125">业务线应用程序发送到消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-125">The line-of-business application sends the message to [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f9ec0-126"> 将该消息从 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库发送到 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-126"> sends the message from the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database to the SQL adapter.</span></span>  
  
3.  <span data-ttu-id="f9ec0-127">XML 接收管道对该消息执行简单 XML 验证。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-127">The XML receive pipeline does simple XML validation of the message.</span></span>  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f9ec0-128"> 将消息路由至 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-128"> routes the message to the MessageBox database.</span></span>  
  
5.  <span data-ttu-id="f9ec0-129">专用流程处理消息的服务内容。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-129">The private process processes the service content of the message.</span></span>  
  
6.  <span data-ttu-id="f9ec0-130">公用流程处理消息的 RNIF 头。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-130">The public process processes the RNIF headers of the message.</span></span>  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f9ec0-131"> 将该消息路由回 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-131"> routes the message back to the MessageBox database.</span></span>  
  
8.  <span data-ttu-id="f9ec0-132">接收管道对消息进行组装并签名/加密/编码。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-132">The send pipeline performs assembly and signing/encryption/encoding of the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f9ec0-133"> 将该消息路由到 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-133"> routes the message to the HTTP adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f9ec0-134">将消息路由至 RNIFSend.aspx 页，该页将其通过 Internet 发送到其目标。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-134"> routes the message to the RNIFSend.aspx page, which sends it over the Internet to its destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ec0-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9ec0-135">See Also</span></span>  
 <span data-ttu-id="f9ec0-136">[BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="f9ec0-136">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 <span data-ttu-id="f9ec0-137">[响应方 BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="f9ec0-137">[Message Flow in the Responder BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span></span>  
 [<span data-ttu-id="f9ec0-138">消息处理在 BTARN</span><span class="sxs-lookup"><span data-stu-id="f9ec0-138">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)