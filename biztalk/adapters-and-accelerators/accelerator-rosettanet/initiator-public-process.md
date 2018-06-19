---
title: 发起方公共流程 |Microsoft 文档
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
ms.openlocfilehash: df1565915d36f3036543ff69c5da680d5949dc74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210701"
---
# <a name="initiator-public-process"></a><span data-ttu-id="17aa5-102">发起方公共流程</span><span class="sxs-lookup"><span data-stu-id="17aa5-102">Initiator Public Process</span></span>
<span data-ttu-id="17aa5-103">本流程通过创建并发送初始的 RNIF 业务消息，在发起方系统中启动 RosettaNet 实现框架 (RNIF) 消息传送。</span><span class="sxs-lookup"><span data-stu-id="17aa5-103">This process initiates RosettaNet Implementation Framework (RNIF) messaging on the initiator system by creating and sending the initial RNIF business message.</span></span>  
  
## <a name="message-flow-in-the-initiator-public-process"></a><span data-ttu-id="17aa5-104">发起方公用流程中的消息流</span><span class="sxs-lookup"><span data-stu-id="17aa5-104">Message Flow in the Initiator Public Process</span></span>  
 <span data-ttu-id="17aa5-105">通过发起方公用流程的消息流如下：</span><span class="sxs-lookup"><span data-stu-id="17aa5-105">The message flow through the initiator public process is as follows:</span></span>  
  
1.  <span data-ttu-id="17aa5-106">发起方公用流程通过服务内容端口从专用流程接收服务内容和附件。</span><span class="sxs-lookup"><span data-stu-id="17aa5-106">The initiator public process receives the service content and attachments from the private process through the service-content port.</span></span>  
  
2.  <span data-ttu-id="17aa5-107">然后，该公用流程向专用流程发送响应，而不进行进一步的处理。</span><span class="sxs-lookup"><span data-stu-id="17aa5-107">The public process sends the response to the private process, and does no further processing.</span></span>  
  
3.  <span data-ttu-id="17aa5-108">如果公共进程接收通知， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未未成功发送消息、 公共过程将状态发送回发起程序专用过程中，连接，然后结束。</span><span class="sxs-lookup"><span data-stu-id="17aa5-108">If the public process receives notification that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the initiator private process, and then ends.</span></span>  
  
4.  <span data-ttu-id="17aa5-109">如果公用流程接收到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 成功发送消息的通知，则公用流程进入等待状态（等待响应方的操作）。</span><span class="sxs-lookup"><span data-stu-id="17aa5-109">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the responder).</span></span>  
  
5.  <span data-ttu-id="17aa5-110">以下操作可以结束等待状态：</span><span class="sxs-lookup"><span data-stu-id="17aa5-110">The following actions can end the wait state:</span></span>  
  
    1.  <span data-ttu-id="17aa5-111">公用流程收到响应方的确认信号。</span><span class="sxs-lookup"><span data-stu-id="17aa5-111">The public process receives an acknowledgement signal from the responder.</span></span>  
  
         <span data-ttu-id="17aa5-112">如果要求信号的不可否认性（按照流程配置中的设置），则该流程将读取摘要，使信号中的摘要与原始操作消息中的摘要相关联，然后持久保留该信号。</span><span class="sxs-lookup"><span data-stu-id="17aa5-112">If non-repudiation for the signal is required (as set in the process configuration settings), the process reads the digest, correlates the digest in the signal with the digest in the original action message, and then persists the signal.</span></span>  
  
         <span data-ttu-id="17aa5-113">公用流程将信号的头和服务内容发送到专用流程。</span><span class="sxs-lookup"><span data-stu-id="17aa5-113">The public process sends the headers and service content of the signal to the private process.</span></span>  
  
    2.  <span data-ttu-id="17aa5-114">公用流程从响应方接收双操作响应消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-114">The public process receives a double-action response message from the responder.</span></span>  
  
         <span data-ttu-id="17aa5-115">该流程提取响应消息中的服务内容和头，然后将其发送到专用流程。</span><span class="sxs-lookup"><span data-stu-id="17aa5-115">The process extracts the service content and headers from the response message, and sends them to the private process.</span></span>  
  
         <span data-ttu-id="17aa5-116">如果活动是同步的，则该流程将使用前导头、服务头和（限于 RNIF 2.01）传递头对服务内容消息部分进行包装，从而构造 RNIF 信号消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-116">If the activity is synchronous, the process constructs an RNIF signal message by wrapping the service-content message part with the preamble, service header, and delivery header (for RNIF 2.01).</span></span> <span data-ttu-id="17aa5-117">该流程使用参与方之间的贸易合作伙伴协议中存储的以下信息来创建前导头和头：一是源参与方和目标参与方的配置信息，二是 PIP 变量；</span><span class="sxs-lookup"><span data-stu-id="17aa5-117">The process creates the preamble and headers using configuration information about the source and destination parties, and the PIP variables stored in the trading partner agreement between the parties.</span></span> <span data-ttu-id="17aa5-118">然后，将信号消息发送到响应方。</span><span class="sxs-lookup"><span data-stu-id="17aa5-118">The process then sends the signal message to the responder.</span></span>  
  
         <span data-ttu-id="17aa5-119">如果活动是异步的，则该流程结束。</span><span class="sxs-lookup"><span data-stu-id="17aa5-119">If the activity is asynchronous, the process ends.</span></span>  
  
    3.  <span data-ttu-id="17aa5-120">公用流程从响应方接收失败通知 (NoF) 消息，</span><span class="sxs-lookup"><span data-stu-id="17aa5-120">The public process receives a Notification of Failure (NoF) message from the responder.</span></span> <span data-ttu-id="17aa5-121">并将相应的状态消息发送到发起方专用流程。</span><span class="sxs-lookup"><span data-stu-id="17aa5-121">The public process sends a corresponding status message to the initiator private process.</span></span> <span data-ttu-id="17aa5-122">然后，发起方专用流程对错误进行处理，并结束公用和专用流程。</span><span class="sxs-lookup"><span data-stu-id="17aa5-122">The private process then handles the error and ends both processes.</span></span>  
  
    4.  <span data-ttu-id="17aa5-123">在确认时间期（按照在流程配置中的设置）内，公用流程未收到响应方的确认信号。</span><span class="sxs-lookup"><span data-stu-id="17aa5-123">The public process does not receive an acknowledgement signal from the responder within the Time to Acknowledge period (as set in the process configuration settings).</span></span> <span data-ttu-id="17aa5-124">如果这样的话，会出现下列情况之一：</span><span class="sxs-lookup"><span data-stu-id="17aa5-124">If so, one of the following occurs:</span></span>  
  
         <span data-ttu-id="17aa5-125">如果重试次数（按照流程配置中的设置）还没有到零，并且活动是异步的，则公用流程将再次发送消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-125">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is asynchronous, the public process sends the message again.</span></span>  
  
         <span data-ttu-id="17aa5-126">如果重试次数（按照流程配置中的设置）还没有到零，并且活动是同步的，则公用流程将启动一个 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-126">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is synchronous, the public process initiates a 0A1 message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="17aa5-127">CIDX 不支持 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-127">CIDX does not support 0A1 messages.</span></span>  
  
         <span data-ttu-id="17aa5-128">如果重试次数已经为零，发送还是不成功，则公用流程将发布错误消息；如果消息不是 CIDX，还要发送 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-128">If the number of retries reaches zero without a successful send, the public process posts an error message, and if this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
         <span data-ttu-id="17aa5-129">如果活动是同步的，并且消息不是 CIDX，则公用流程将启动一个 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-129">If the activity is synchronous, and this is not CIDX, the public process initiates a 0A1 message.</span></span>  
  
    5.  <span data-ttu-id="17aa5-130">如果在“执行时间”期间内未发生任何操作，并且消息不是 CIDX，则公用流程将发送一个 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="17aa5-130">If no action occurs within the Time to Perform period, and this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17aa5-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17aa5-131">See Also</span></span>  
 <span data-ttu-id="17aa5-132">[公共进程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="17aa5-132">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 [<span data-ttu-id="17aa5-133">响应方公共过程</span><span class="sxs-lookup"><span data-stu-id="17aa5-133">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)