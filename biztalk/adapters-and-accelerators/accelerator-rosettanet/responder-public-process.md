---
title: "响应方公用流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow
- messages, public processes
- public processes, message flow
- public processes, responder
ms.assetid: 78d83954-2998-44ac-a527-5e5858c61009
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89c246bca80fdb648df909cd4f01fca4e2691dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="responder-public-process"></a><span data-ttu-id="5c7f3-102">响应方公共过程</span><span class="sxs-lookup"><span data-stu-id="5c7f3-102">Responder Public Process</span></span>
<span data-ttu-id="5c7f3-103">响应方在此公共过程从发起方，接收 RosettaNet 实现框架 (RNIF) 消息，并相应地做出响应。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-103">This public process on the responder receives the RosettaNet Implementation Framework (RNIF) message from the initiator, and responds accordingly.</span></span>  
  
## <a name="message-flow-in-the-responder-public-process"></a><span data-ttu-id="5c7f3-104">响应方公共过程中的消息流</span><span class="sxs-lookup"><span data-stu-id="5c7f3-104">Message Flow in the Responder Public Process</span></span>  
 <span data-ttu-id="5c7f3-105">响应方公共过程通过邮件流未，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c7f3-105">The message flow through the responder public process is as follows:</span></span>  
  
1.  <span data-ttu-id="5c7f3-106">响应方公共过程从响应方 MessageBox 数据库接收 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-106">The responder public process receives the RNIF message from the responder MessageBox database.</span></span>  
  
2.  <span data-ttu-id="5c7f3-107">公共过程从操作消息提取的服务内容和标头，并将其发送到专用的流程。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-107">The public process extracts the service content and headers from the action message, and sends them to the private process.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c7f3-108">响应方公共过程对传入的消息 （和任何其他验证包含在验证适配器中，如果适用） 执行标准的验证。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-108">The responder public process performs standard validation on the incoming message (and any additional validation included in a validation adapter, if applicable).</span></span> <span data-ttu-id="5c7f3-109">如果验证成功，公用流程将启动应用程序适配器来执行特定的实现根据通知。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-109">If validation is successful, then the public process will initiate the application adapter to perform notification in accordance with the specific implementation.</span></span> <span data-ttu-id="5c7f3-110">响应方公共过程会将消息保存在 MessageBox 数据库中，并将通知响应方专用流程，因此具有消息保存到 MessageBox (使用`BeginNotify`中的方法`ApplicationAdapter`类)。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-110">The responder public process will save the message in the MessageBox database, and will notify the responder private process that it has saved the message in the MessageBox (using the `BeginNotify` method in the `ApplicationAdapter` class).</span></span> <span data-ttu-id="5c7f3-111">有关验证适配器和应用程序适配器的详细信息，请参阅[ValidationAdapter &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)和[ApplicationAdapter &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).</span><span class="sxs-lookup"><span data-stu-id="5c7f3-111">For more information about the validation adapter and application adapter, see [ValidationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md) and [ApplicationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).</span></span>  
  
3.  <span data-ttu-id="5c7f3-112">如果活动是异步的单个操作，公共过程通过包装服务内容消息部分与该前导码，服务标头，并 （在 RNIF 2.01) 来构造一条 RNIF 信号消息 （确认接受） 的传递标头。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-112">If the activity is asynchronous and single-action, the public process constructs an RNIF signal message (Acknowledgment Acceptance) by wrapping the service-content message part with the preamble, the service header, and (for RNIF 2.01 only) the delivery header.</span></span> <span data-ttu-id="5c7f3-113">公共过程构造该前导码、 服务标头和使用方之间的贸易合作伙伴协议中存储信息的传递标头： 过程配置设置、 有关源的配置信息和目标方和合作伙伴接口过程 (PIP) 变量。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-113">The public process constructs the preamble, the service header, and the delivery header using information stored in the trading partner agreement between the parties: the process configuration settings, configuration information about the source and destination parties, and the Partner Interface Process (PIP) variables.</span></span> <span data-ttu-id="5c7f3-114">然后，过程将信号消息发送到发起方。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-114">The process then sends the signal message to the initiator.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c7f3-115">如果消息是单操作消息，消息流已完成。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-115">If the message is a single-action message, the message flow is complete.</span></span>  
  
4.  <span data-ttu-id="5c7f3-116">在公共进程进入等待状态 （等待操作由响应方私有进程）。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-116">The public process enters a wait state (waiting for action by the responder private process).</span></span>  
  
5.  <span data-ttu-id="5c7f3-117">以下操作可以结束等待状态 （等待操作由响应方私有进程）：</span><span class="sxs-lookup"><span data-stu-id="5c7f3-117">The following actions can end the wait state (waiting for action by the responder private process):</span></span>  
  
    1.  <span data-ttu-id="5c7f3-118">响应方专用流程返回响应服务内容消息和标头，以响应的原始操作消息 （是双操作消息）。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-118">The responder private process returns a response service-content message and headers, in response to the original action message (that was a double-action message).</span></span>  
  
         <span data-ttu-id="5c7f3-119">如果公共过程从专用流程收到响应服务内容，公共过程构造包含服务内容的 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-119">If the public process receives response service content from the private process, the public process constructs an RNIF message that contains the service content.</span></span> <span data-ttu-id="5c7f3-120">它会通过包装了服务内容消息部分和标头包含有关源和目标方和 PIP 变量存储在双方之间的协议的配置信息。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-120">It does so by wrapping the service-content message part with headers that contain the configuration information about the source and destination parties, and the PIP variables stored in the agreement between the parties.</span></span>  
  
         <span data-ttu-id="5c7f3-121">公共过程将 RNIF 消息发送到发起方使用的操作/信号角色链接端口。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-121">The public process sends the RNIF message to the initiator using the Action/Signal Role link port.</span></span>  
  
         <span data-ttu-id="5c7f3-122">如果公共进程接收通知， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未未成功发送消息、 公共过程将状态发送回专用的过程中，连接，然后结束。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-122">If the public process receives notification that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the private process, and then ends.</span></span>  
  
         <span data-ttu-id="5c7f3-123">如果公用流程接收到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 成功发送消息的通知，则公用流程进入等待状态（等待发起方的操作）。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-123">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the initiator).</span></span> <span data-ttu-id="5c7f3-124">该等待状态是类似于时它正在等待由响应方的操作进入发起方等待状态。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-124">This wait state is similar to the wait state that the initiator enters when it is waiting for action by the responder.</span></span>  
  
    2.  <span data-ttu-id="5c7f3-125">公共过程从发起方接收故障通知消息 （起）。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-125">The public process receives a Notification of Failure message (NoF) from the initiator.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c7f3-126">它已成功处理传入的消息后，响应方专用流程将通知响应方公共过程。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-126">The responder private process will notify the responder public process after it has successfully processed the incoming message.</span></span> <span data-ttu-id="5c7f3-127">仅在对响应方后公用流程已收到此通知 (从`EndNotify`中的方法`ApplicationAdapter`类) 将成功完成的响应方公共过程。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-127">Only after the responder public process has received this notification (from the `EndNotify` method in the `ApplicationAdapter` class) will the responder public process be successfully completed.</span></span>  
  
6.  <span data-ttu-id="5c7f3-128">响应方公共进程进入等待状态 （正在等待从发起方到响应方公共过程发送响应消息的响应中收到信号）。</span><span class="sxs-lookup"><span data-stu-id="5c7f3-128">The responder public process enters a wait state (waiting to receive a signal from the initiator in response to the response message that the responder public process sent).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7f3-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c7f3-129">See Also</span></span>  
 <span data-ttu-id="5c7f3-130">[公共进程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="5c7f3-130">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 <span data-ttu-id="5c7f3-131">[发起方公共流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md) </span><span class="sxs-lookup"><span data-stu-id="5c7f3-131">[Initiator Public Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md) </span></span>  
 <span data-ttu-id="5c7f3-132">[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md) </span><span class="sxs-lookup"><span data-stu-id="5c7f3-132">[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md) </span></span>  
 [<span data-ttu-id="5c7f3-133">ValidationAdapter</span><span class="sxs-lookup"><span data-stu-id="5c7f3-133">ValidationAdapter</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)