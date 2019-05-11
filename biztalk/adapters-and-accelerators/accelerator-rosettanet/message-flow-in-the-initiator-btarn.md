---
title: 消息发起方 BTARN 中的流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- initiator BTARN
ms.assetid: 315f3d4c-5e40-4b8e-b135-9da98dc2db1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02a1e9832a633c1b638b7a6b527e607654e75870
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283031"
---
# <a name="message-flow-in-the-initiator-btarn"></a><span data-ttu-id="9b136-102">发起方 BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="9b136-102">Message Flow in the Initiator BTARN</span></span>
<span data-ttu-id="9b136-103">发起方计算机上的消息流开始，从后端业务线应用程序，以其专用格式接收一条消息。</span><span class="sxs-lookup"><span data-stu-id="9b136-103">Message flow on an initiator computer starts with receiving a message from the back-end line-of-business application, in its proprietary format.</span></span> <span data-ttu-id="9b136-104">它涉及到将该消息转换为 RosettaNet 实现框架 (RNIF) 的兼容的消息，并向响应方计算机通过 Internet 发送消息。</span><span class="sxs-lookup"><span data-stu-id="9b136-104">It involves converting that message to a RosettaNet Implementation Framework (RNIF)-compliant message, and then sending the message over the Internet to the responder computer.</span></span>  
  
 <span data-ttu-id="9b136-105">如果合作伙伴接口流程 (PIP) 是单操作，则唯一的响应是确认信号消息。</span><span class="sxs-lookup"><span data-stu-id="9b136-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="9b136-106">有关单操作消息流的信息，请参阅本主题后面的"流的"初始消息。</span><span class="sxs-lookup"><span data-stu-id="9b136-106">For information about single-action message flow, see "Flow of an Initiated Message" later in this topic.</span></span> <span data-ttu-id="9b136-107">如果 PIP 是双操作，发起方将收到响应消息，并确认，除了单操作消息流答复。</span><span class="sxs-lookup"><span data-stu-id="9b136-107">If the PIP is double-action, the initiator will receive a response message, and reply with an acknowledgement, in addition to the single-action message flow.</span></span>  
  
 <span data-ttu-id="9b136-108">如果 PIP 是异步的通过 Internet 每次消息传输会在不同的 HTTP 连接上发生。</span><span class="sxs-lookup"><span data-stu-id="9b136-108">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="9b136-109">如果 PIP 是同步的每次消息传输会发生在同一连接上的 HTTP 适配器的进程之前保存已完成。</span><span class="sxs-lookup"><span data-stu-id="9b136-109">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="9b136-110">在双操作同步方案中，响应方计算机不会发送到发起方计算机以响应初始请求消息的确认。</span><span class="sxs-lookup"><span data-stu-id="9b136-110">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="9b136-111">响应消息作为确认。</span><span class="sxs-lookup"><span data-stu-id="9b136-111">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-initiator-computer"></a><span data-ttu-id="9b136-112">发起方计算机上的 BTARN 组件</span><span class="sxs-lookup"><span data-stu-id="9b136-112">BTARN Components on the Initiator Computer</span></span>  
 <span data-ttu-id="9b136-113">当消息流通过[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]在发起方计算机上的以下组件将处理该消息：</span><span class="sxs-lookup"><span data-stu-id="9b136-113">As a message flows through [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the initiator computer, the following components will process the message:</span></span>  
  
- <span data-ttu-id="9b136-114">SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="9b136-114">SQL adapter</span></span>  
  
- <span data-ttu-id="9b136-115">XML 接收管道</span><span class="sxs-lookup"><span data-stu-id="9b136-115">XML receive pipeline</span></span>  
  
- <span data-ttu-id="9b136-116">发起方专用流程</span><span class="sxs-lookup"><span data-stu-id="9b136-116">Initiator private process</span></span>  
  
- <span data-ttu-id="9b136-117">发起方公用流程</span><span class="sxs-lookup"><span data-stu-id="9b136-117">Initiator public process</span></span>  
  
- <span data-ttu-id="9b136-118">XML 发送管道</span><span class="sxs-lookup"><span data-stu-id="9b136-118">XML send pipeline</span></span>  
  
- <span data-ttu-id="9b136-119">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="9b136-119">HTTP adapter</span></span>  
  
- <span data-ttu-id="9b136-120">RNIFSend.aspx 页</span><span class="sxs-lookup"><span data-stu-id="9b136-120">RNIFSend.aspx page</span></span>  
  
  <span data-ttu-id="9b136-121">有关这些组件，以及它们如何处理消息的详细信息，请参阅[BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。</span><span class="sxs-lookup"><span data-stu-id="9b136-121">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="flow-of-an-initiated-message"></a><span data-ttu-id="9b136-122">启动消息流</span><span class="sxs-lookup"><span data-stu-id="9b136-122">Flow of an Initiated Message</span></span>  
 <span data-ttu-id="9b136-123">以下步骤说明通过发起方的初始消息的消息流[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="9b136-123">The following steps describe the message flow of an initiated message through the initiator [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer.</span></span> <span data-ttu-id="9b136-124">下图显示了此过程。</span><span class="sxs-lookup"><span data-stu-id="9b136-124">The following figure shows this process.</span></span>  
  
 <span data-ttu-id="9b136-125">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")</span><span class="sxs-lookup"><span data-stu-id="9b136-125">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")</span></span>  
  
1. <span data-ttu-id="9b136-126">业务线应用程序将消息发送给 Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9b136-126">The line-of-business application sends the message to Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="9b136-127">将消息从发送[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库添加到 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="9b136-127">sends the message from the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database to the SQL adapter.</span></span>  
  
3. <span data-ttu-id="9b136-128">XML 接收管道执行简单 XML 验证，消息。</span><span class="sxs-lookup"><span data-stu-id="9b136-128">The XML receive pipeline does simple XML validation of the message.</span></span>  
  
4. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9b136-129">将消息路由到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9b136-129">routes the message to the MessageBox database.</span></span>  
  
5. <span data-ttu-id="9b136-130">专用流程处理消息的服务内容。</span><span class="sxs-lookup"><span data-stu-id="9b136-130">The private process processes the service content of the message.</span></span>  
  
6. <span data-ttu-id="9b136-131">公用流程处理消息的 RNIF 头。</span><span class="sxs-lookup"><span data-stu-id="9b136-131">The public process processes the RNIF headers of the message.</span></span>  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="9b136-132">将消息路由回 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9b136-132">routes the message back to the MessageBox database.</span></span>  
  
8. <span data-ttu-id="9b136-133">发送管道执行的程序集和签名/加密/编码的消息。</span><span class="sxs-lookup"><span data-stu-id="9b136-133">The send pipeline performs assembly and signing/encryption/encoding of the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="9b136-134">将消息路由到 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="9b136-134">routes the message to the HTTP adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="9b136-135">将消息路由到 RNIFSend.aspx 页，将其通过 Internet 发送到其目标。</span><span class="sxs-lookup"><span data-stu-id="9b136-135">routes the message to the RNIFSend.aspx page, which sends it over the Internet to its destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b136-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b136-136">See Also</span></span>  
 <span data-ttu-id="9b136-137">[BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="9b136-137">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 <span data-ttu-id="9b136-138">[响应方 BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="9b136-138">[Message Flow in the Responder BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span></span>  
 [<span data-ttu-id="9b136-139">BTARN 中的消息处理</span><span class="sxs-lookup"><span data-stu-id="9b136-139">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)