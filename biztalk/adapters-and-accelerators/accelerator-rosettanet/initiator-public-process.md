---
title: 发起方公用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, initiator
- CIDX, 0A1 messages
- messages, 0A1 messages
- messages, message flow
- messages, public processes
- 0A1 messages
- public processes, message flow
ms.assetid: 371d0792-d346-405b-a8f4-2dfa64dd1566
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50506911108d21247f5da9cadc76cd505417a8d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283503"
---
# <a name="initiator-public-process"></a><span data-ttu-id="818a2-102">发起方公用流程</span><span class="sxs-lookup"><span data-stu-id="818a2-102">Initiator Public Process</span></span>
<span data-ttu-id="818a2-103">此过程将启动 RosettaNet 实现框架 (RNIF) 消息传送在发起方系统通过创建并发送初始的 RNIF 业务消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-103">This process initiates RosettaNet Implementation Framework (RNIF) messaging on the initiator system by creating and sending the initial RNIF business message.</span></span>  
  
## <a name="message-flow-in-the-initiator-public-process"></a><span data-ttu-id="818a2-104">发起方公用流程中的消息流</span><span class="sxs-lookup"><span data-stu-id="818a2-104">Message Flow in the Initiator Public Process</span></span>  
 <span data-ttu-id="818a2-105">通过发起方公用流程的消息流如下所示：</span><span class="sxs-lookup"><span data-stu-id="818a2-105">The message flow through the initiator public process is as follows:</span></span>  
  
1. <span data-ttu-id="818a2-106">发起方公用流程的专用流程通过服务内容端口从接收服务内容和附件。</span><span class="sxs-lookup"><span data-stu-id="818a2-106">The initiator public process receives the service content and attachments from the private process through the service-content port.</span></span>  
  
2. <span data-ttu-id="818a2-107">公用流程向专用流程发送响应，并不会无需进一步处理。</span><span class="sxs-lookup"><span data-stu-id="818a2-107">The public process sends the response to the private process, and does no further processing.</span></span>  
  
3. <span data-ttu-id="818a2-108">如果公用流程接收通知，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未成功发送消息，则公用流程将该状态发送回发起方专用流程，然后结束。</span><span class="sxs-lookup"><span data-stu-id="818a2-108">If the public process receives notification that Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the initiator private process, and then ends.</span></span>  
  
4. <span data-ttu-id="818a2-109">如果公用流程接收通知的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]成功发送消息，流程进入等待状态 （等待由响应方操作）。</span><span class="sxs-lookup"><span data-stu-id="818a2-109">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the responder).</span></span>  
  
5. <span data-ttu-id="818a2-110">以下操作可以结束等待状态：</span><span class="sxs-lookup"><span data-stu-id="818a2-110">The following actions can end the wait state:</span></span>  
  
   1.  <span data-ttu-id="818a2-111">公用流程从响应方接收的确认信号。</span><span class="sxs-lookup"><span data-stu-id="818a2-111">The public process receives an acknowledgement signal from the responder.</span></span>  
  
        <span data-ttu-id="818a2-112">如果信号的不可否认 （按照流程配置设置中），所需进程读取摘要、 关联信号中的摘要与原始操作消息中的摘要，然后持久保留该信号。</span><span class="sxs-lookup"><span data-stu-id="818a2-112">If non-repudiation for the signal is required (as set in the process configuration settings), the process reads the digest, correlates the digest in the signal with the digest in the original action message, and then persists the signal.</span></span>  
  
        <span data-ttu-id="818a2-113">公用流程向专用流程发送标头和服务内容的信号。</span><span class="sxs-lookup"><span data-stu-id="818a2-113">The public process sends the headers and service content of the signal to the private process.</span></span>  
  
   2.  <span data-ttu-id="818a2-114">公用流程从响应方接收双操作响应消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-114">The public process receives a double-action response message from the responder.</span></span>  
  
        <span data-ttu-id="818a2-115">该过程从响应消息中提取的服务内容和标头，并将其发送到专用流程。</span><span class="sxs-lookup"><span data-stu-id="818a2-115">The process extracts the service content and headers from the response message, and sends them to the private process.</span></span>  
  
        <span data-ttu-id="818a2-116">如果活动是同步的该过程通过将服务内容消息部分使用前导头、 服务头和传递头包装 （对于 RNIF 2.01) 构造 RNIF 信号消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-116">If the activity is synchronous, the process constructs an RNIF signal message by wrapping the service-content message part with the preamble, service header, and delivery header (for RNIF 2.01).</span></span> <span data-ttu-id="818a2-117">进程创建的前导码和标头使用源和目标参与方和参与方之间的贸易合作伙伴协议中存储的 PIP 变量的配置信息。</span><span class="sxs-lookup"><span data-stu-id="818a2-117">The process creates the preamble and headers using configuration information about the source and destination parties, and the PIP variables stored in the trading partner agreement between the parties.</span></span> <span data-ttu-id="818a2-118">然后，过程将信号消息发送到响应方。</span><span class="sxs-lookup"><span data-stu-id="818a2-118">The process then sends the signal message to the responder.</span></span>  
  
        <span data-ttu-id="818a2-119">如果活动是异步的则在进程结束。</span><span class="sxs-lookup"><span data-stu-id="818a2-119">If the activity is asynchronous, the process ends.</span></span>  
  
   3.  <span data-ttu-id="818a2-120">公用流程从响应方接收失败通知 (NoF) 消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-120">The public process receives a Notification of Failure (NoF) message from the responder.</span></span> <span data-ttu-id="818a2-121">公用流程将相应的状态消息发送到发起方专用流程。</span><span class="sxs-lookup"><span data-stu-id="818a2-121">The public process sends a corresponding status message to the initiator private process.</span></span> <span data-ttu-id="818a2-122">专用流程然后处理该错误并结束这两个进程。</span><span class="sxs-lookup"><span data-stu-id="818a2-122">The private process then handles the error and ends both processes.</span></span>  
  
   4.  <span data-ttu-id="818a2-123">公用流程未收到的确认信号响应方的时间内到确认期 （按照流程配置设置中设置）。</span><span class="sxs-lookup"><span data-stu-id="818a2-123">The public process does not receive an acknowledgement signal from the responder within the Time to Acknowledge period (as set in the process configuration settings).</span></span> <span data-ttu-id="818a2-124">如果是这样，会发生下列情况之一：</span><span class="sxs-lookup"><span data-stu-id="818a2-124">If so, one of the following occurs:</span></span>  
  
        <span data-ttu-id="818a2-125">如果重试的次数 （按照流程配置设置中） 还没有到零，并且活动是异步，则公用流程将再次发送消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-125">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is asynchronous, the public process sends the message again.</span></span>  
  
        <span data-ttu-id="818a2-126">如果重试的次数 （按照流程配置设置中） 还没有到零，并且活动是同步，则公用流程将启动一个 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-126">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is synchronous, the public process initiates a 0A1 message.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="818a2-127">CIDX 不支持 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-127">CIDX does not support 0A1 messages.</span></span>  
  
        <span data-ttu-id="818a2-128">如果重试次数达到零，而无需成功发送，则公用流程将发布错误消息，并且如果这不是 CIDX，则公用流程将发送 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-128">If the number of retries reaches zero without a successful send, the public process posts an error message, and if this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
        <span data-ttu-id="818a2-129">如果活动是同步的并且不是 CIDX，则公用流程将启动一个 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-129">If the activity is synchronous, and this is not CIDX, the public process initiates a 0A1 message.</span></span>  
  
   5.  <span data-ttu-id="818a2-130">如果与执行持续时间的时间内发生任何操作并不是 CIDX，则公用流程将发送 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="818a2-130">If no action occurs within the Time to Perform period, and this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818a2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="818a2-131">See Also</span></span>  
 <span data-ttu-id="818a2-132">[公用流程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="818a2-132">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 [<span data-ttu-id="818a2-133">响应方公用流程</span><span class="sxs-lookup"><span data-stu-id="818a2-133">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)