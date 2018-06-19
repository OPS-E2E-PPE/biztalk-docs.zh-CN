---
title: 消息流中对响应方 BTARN |Microsoft 文档
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
ms.openlocfilehash: f3ad33db4f67336f41ac868a7a14e1266a85dd45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207381"
---
# <a name="message-flow-in-the-responder-btarn"></a><span data-ttu-id="5061c-102">响应方 BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="5061c-102">Message Flow in the Responder BTARN</span></span>
<span data-ttu-id="5061c-103">通过 Internet 从发起程序计算机中接收消息开头响应方计算机上的消息流。</span><span class="sxs-lookup"><span data-stu-id="5061c-103">Message flow on a responder computer starts with receiving a message over the Internet from the initiator computer.</span></span> <span data-ttu-id="5061c-104">它包括将该消息转换从 RosettaNet 实现框架 (RNIF)-符合到为后端的应用程序，然后将消息路由到业务线应用程序专有格式的消息的消息。</span><span class="sxs-lookup"><span data-stu-id="5061c-104">It involves converting that message from a RosettaNet Implementation Framework (RNIF)-compliant message to a message in the proprietary format of the back-end application, and then routing the message to the line-of-business application.</span></span>  
  
 <span data-ttu-id="5061c-105">如果合作伙伴接口流程 (PIP) 是单操作的，则唯一的响应是确认信号消息。</span><span class="sxs-lookup"><span data-stu-id="5061c-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="5061c-106">如果 PIP，双操作响应方将处理和发送响应消息，和随后接收确认时该响应。</span><span class="sxs-lookup"><span data-stu-id="5061c-106">If the PIP is double-action, the responder will process and send a response message, and subsequently receive an acknowledgment for that response.</span></span>  
  
 <span data-ttu-id="5061c-107">如果 PIP 是异步的，则通过 Internet 的每次消息传输将在不同的 HTTP 连接上进行；</span><span class="sxs-lookup"><span data-stu-id="5061c-107">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="5061c-108">如果 PIP 是同步的，则每次消息传输将在同一连接上进行，HTTP 适配器将一直保持该连接，直到相应流程完成为止。</span><span class="sxs-lookup"><span data-stu-id="5061c-108">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="5061c-109">在双操作同步方案中，响应方计算机不会向发起方计算机发送确认消息以响应初始请求消息，</span><span class="sxs-lookup"><span data-stu-id="5061c-109">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="5061c-110">而是以响应消息作为确认消息。</span><span class="sxs-lookup"><span data-stu-id="5061c-110">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-responder-computer"></a><span data-ttu-id="5061c-111">响应方计算机上的 BTARN 组件</span><span class="sxs-lookup"><span data-stu-id="5061c-111">BTARN Components on the Responder Computer</span></span>  
 <span data-ttu-id="5061c-112">因为消息流经[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]响应方在计算机上，以下组件将处理该消息：</span><span class="sxs-lookup"><span data-stu-id="5061c-112">As a message flows through [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the responder computer, the following components will process the message:</span></span>  
  
-   <span data-ttu-id="5061c-113">RNIFReceive.aspx 页</span><span class="sxs-lookup"><span data-stu-id="5061c-113">RNIFReceive.aspx page</span></span>  
  
-   <span data-ttu-id="5061c-114">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="5061c-114">HTTP adapter</span></span>  
  
-   <span data-ttu-id="5061c-115">接收管道</span><span class="sxs-lookup"><span data-stu-id="5061c-115">Receive pipeline</span></span>  
  
-   <span data-ttu-id="5061c-116">响应方公共过程</span><span class="sxs-lookup"><span data-stu-id="5061c-116">Responder public process</span></span>  
  
-   <span data-ttu-id="5061c-117">响应方专用流程</span><span class="sxs-lookup"><span data-stu-id="5061c-117">Responder private process</span></span>  
  
-   <span data-ttu-id="5061c-118">SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="5061c-118">SQL adapter</span></span>  
  
-   <span data-ttu-id="5061c-119">发送管道</span><span class="sxs-lookup"><span data-stu-id="5061c-119">Send pipeline</span></span>  
  
 <span data-ttu-id="5061c-120">有关这些组件，以及它们如何处理消息的详细信息，请参阅[消息处理中 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。</span><span class="sxs-lookup"><span data-stu-id="5061c-120">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="message-flow-on-the-responder-computer"></a><span data-ttu-id="5061c-121">响应方计算机上的消息流</span><span class="sxs-lookup"><span data-stu-id="5061c-121">Message Flow on the Responder Computer</span></span>  
 <span data-ttu-id="5061c-122">已收到消息的消息流通过响应方 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 计算机的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="5061c-122">The message flow of a received message through the responder [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer is as follows:</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")  
  
1.  <span data-ttu-id="5061c-123">RNIFReceive aspx 页从发起方接收传入的消息。</span><span class="sxs-lookup"><span data-stu-id="5061c-123">The RNIFReceive aspx page receives the incoming message from the initiator.</span></span>  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5061c-124"> 将消息提交给 HTTP 适配器，HTTP 适配器再将其提交给接收管道。</span><span class="sxs-lookup"><span data-stu-id="5061c-124"> submits the message to the HTTP adapter, which submits it to the receive pipeline.</span></span>  
  
3.  <span data-ttu-id="5061c-125">接收管道将解码、 进行反汇编，并在消息中，执行方解析，并且然后将消息转换为后端业务线应用程序的专有格式。</span><span class="sxs-lookup"><span data-stu-id="5061c-125">The receive pipeline decodes, disassembles, and performs party resolution on the message, and then converts the message into the proprietary format of the back-end line-of-business application.</span></span>  
  
4.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5061c-126"> 将消息路由至 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="5061c-126"> routes the message to the MessageBox database.</span></span>  
  
5.  <span data-ttu-id="5061c-127">公用流程处理消息的 RNIF 头。</span><span class="sxs-lookup"><span data-stu-id="5061c-127">The public process processes the RNIF headers of the message.</span></span>  
  
6.  <span data-ttu-id="5061c-128">专用流程处理消息的服务内容。</span><span class="sxs-lookup"><span data-stu-id="5061c-128">The private process processes the service content of the message.</span></span> <span data-ttu-id="5061c-129">它会生成都会返回到公共进程、 MessageBox 数据库、 向发送管道，然后返回的 HTTP 适配器通过 Internet 发起程序的确认。</span><span class="sxs-lookup"><span data-stu-id="5061c-129">It generates an acknowledgement that is returned to the public process, to the MessageBox database, to the send pipeline, and then to the HTTP adapter for return over the Internet to the initiator.</span></span>  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5061c-130"> 将消息路由至 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="5061c-130"> routes the message to the MessageBox database.</span></span>  
  
8.  <span data-ttu-id="5061c-131">发送管道将汇编; 而然后符号/加密/编码消息。</span><span class="sxs-lookup"><span data-stu-id="5061c-131">The send pipeline assembles, and then signs/encrypts/encodes the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5061c-132">将消息路由到的 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="5061c-132"> routes the message to the SQL adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5061c-133">将消息提交至[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，而在后端业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="5061c-133"> submits the message to [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and to the line-of-business application on the back end.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5061c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5061c-134">See Also</span></span>  
 <span data-ttu-id="5061c-135">[BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="5061c-135">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 [<span data-ttu-id="5061c-136">发起方 BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="5061c-136">Message Flow in the Initiator BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)