---
title: 消息响应方 BTARN 中的流 |Microsoft Docs
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
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1d797b4f2722f5a686a087c81a661df556de20e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283004"
---
# <a name="message-flow-in-the-responder-btarn"></a><span data-ttu-id="0938b-102">响应方 BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="0938b-102">Message Flow in the Responder BTARN</span></span>
<span data-ttu-id="0938b-103">响应方计算机上的消息流开始，通过 Internet 从发起方计算机接收消息。</span><span class="sxs-lookup"><span data-stu-id="0938b-103">Message flow on a responder computer starts with receiving a message over the Internet from the initiator computer.</span></span> <span data-ttu-id="0938b-104">它涉及到将该消息转换从 RosettaNet 实现框架 (RNIF) 的消息中的后端应用程序，然后将消息路由到业务线应用程序的专有格式兼容的消息。</span><span class="sxs-lookup"><span data-stu-id="0938b-104">It involves converting that message from a RosettaNet Implementation Framework (RNIF)-compliant message to a message in the proprietary format of the back-end application, and then routing the message to the line-of-business application.</span></span>  
  
 <span data-ttu-id="0938b-105">如果合作伙伴接口流程 (PIP) 是单操作，则唯一的响应是确认信号消息。</span><span class="sxs-lookup"><span data-stu-id="0938b-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="0938b-106">如果 PIP 是双操作，该响应程序将处理和发送响应消息，并随后接收确认时响应。</span><span class="sxs-lookup"><span data-stu-id="0938b-106">If the PIP is double-action, the responder will process and send a response message, and subsequently receive an acknowledgment for that response.</span></span>  
  
 <span data-ttu-id="0938b-107">如果 PIP 是异步的通过 Internet 每次消息传输会在不同的 HTTP 连接上发生。</span><span class="sxs-lookup"><span data-stu-id="0938b-107">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="0938b-108">如果 PIP 是同步的每次消息传输会发生在同一连接上的 HTTP 适配器的进程之前保存已完成。</span><span class="sxs-lookup"><span data-stu-id="0938b-108">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="0938b-109">在双操作同步方案中，响应方计算机不会发送到发起方计算机以响应初始请求消息的确认。</span><span class="sxs-lookup"><span data-stu-id="0938b-109">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="0938b-110">响应消息作为确认。</span><span class="sxs-lookup"><span data-stu-id="0938b-110">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-responder-computer"></a><span data-ttu-id="0938b-111">响应方计算机上的 BTARN 组件</span><span class="sxs-lookup"><span data-stu-id="0938b-111">BTARN Components on the Responder Computer</span></span>  
 <span data-ttu-id="0938b-112">当消息流通过 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]响应方计算机上的以下组件将处理该消息：</span><span class="sxs-lookup"><span data-stu-id="0938b-112">As a message flows through Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the responder computer, the following components will process the message:</span></span>  
  
- <span data-ttu-id="0938b-113">RNIFReceive.aspx 页</span><span class="sxs-lookup"><span data-stu-id="0938b-113">RNIFReceive.aspx page</span></span>  
  
- <span data-ttu-id="0938b-114">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="0938b-114">HTTP adapter</span></span>  
  
- <span data-ttu-id="0938b-115">接收管道</span><span class="sxs-lookup"><span data-stu-id="0938b-115">Receive pipeline</span></span>  
  
- <span data-ttu-id="0938b-116">响应方公用流程</span><span class="sxs-lookup"><span data-stu-id="0938b-116">Responder public process</span></span>  
  
- <span data-ttu-id="0938b-117">响应方专用流程</span><span class="sxs-lookup"><span data-stu-id="0938b-117">Responder private process</span></span>  
  
- <span data-ttu-id="0938b-118">SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="0938b-118">SQL adapter</span></span>  
  
- <span data-ttu-id="0938b-119">发送管道</span><span class="sxs-lookup"><span data-stu-id="0938b-119">Send pipeline</span></span>  
  
  <span data-ttu-id="0938b-120">有关这些组件，以及它们如何处理消息的详细信息，请参阅[BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。</span><span class="sxs-lookup"><span data-stu-id="0938b-120">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="message-flow-on-the-responder-computer"></a><span data-ttu-id="0938b-121">响应方计算机上的消息流</span><span class="sxs-lookup"><span data-stu-id="0938b-121">Message Flow on the Responder Computer</span></span>  
 <span data-ttu-id="0938b-122">通过响应方接收的消息的消息流[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]计算机是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="0938b-122">The message flow of a received message through the responder [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer is as follows:</span></span>  
  
 <span data-ttu-id="0938b-123">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")</span><span class="sxs-lookup"><span data-stu-id="0938b-123">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")</span></span>  
  
1. <span data-ttu-id="0938b-124">RNIFReceive aspx 页从发起方接收的传入消息。</span><span class="sxs-lookup"><span data-stu-id="0938b-124">The RNIFReceive aspx page receives the incoming message from the initiator.</span></span>  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0938b-125">将消息提交到 HTTP 适配器，将其提交给接收管道。</span><span class="sxs-lookup"><span data-stu-id="0938b-125">submits the message to the HTTP adapter, which submits it to the receive pipeline.</span></span>  
  
3. <span data-ttu-id="0938b-126">接收管道进行解码、 拆装，并对消息执行参与方解析，然后会将消息转换成后端业务线应用程序的专有格式。</span><span class="sxs-lookup"><span data-stu-id="0938b-126">The receive pipeline decodes, disassembles, and performs party resolution on the message, and then converts the message into the proprietary format of the back-end line-of-business application.</span></span>  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0938b-127">将消息路由到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="0938b-127">routes the message to the MessageBox database.</span></span>  
  
5. <span data-ttu-id="0938b-128">公用流程处理消息的 RNIF 头。</span><span class="sxs-lookup"><span data-stu-id="0938b-128">The public process processes the RNIF headers of the message.</span></span>  
  
6. <span data-ttu-id="0938b-129">专用流程处理消息的服务内容。</span><span class="sxs-lookup"><span data-stu-id="0938b-129">The private process processes the service content of the message.</span></span> <span data-ttu-id="0938b-130">它会生成，会返回到公用流程、 到 MessageBox 数据库、 到发送管道中，然后对返回的 HTTP 适配器通过 Internet 到发起方的确认。</span><span class="sxs-lookup"><span data-stu-id="0938b-130">It generates an acknowledgement that is returned to the public process, to the MessageBox database, to the send pipeline, and then to the HTTP adapter for return over the Internet to the initiator.</span></span>  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0938b-131">将消息路由到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="0938b-131">routes the message to the MessageBox database.</span></span>  
  
8. <span data-ttu-id="0938b-132">发送管道的组装，然后签名/加密 / 对消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="0938b-132">The send pipeline assembles, and then signs/encrypts/encodes the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0938b-133">将消息路由到 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="0938b-133">routes the message to the SQL adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0938b-134">将消息提交到[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，和后端上的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="0938b-134">submits the message to [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and to the line-of-business application on the back end.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0938b-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="0938b-135">See Also</span></span>  
 <span data-ttu-id="0938b-136">[BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="0938b-136">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 [<span data-ttu-id="0938b-137">发起程序 BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="0938b-137">Message Flow in the Initiator BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)