---
title: SWIFT 接收适配器存储和转发 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11eeb335-366b-4b29-9078-de9396b258ca
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1744f86cc10bfe37b1a4c7814c31e6e2e8812507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364376"
---
# <a name="swift-receive-adapter-store-and-forward"></a><span data-ttu-id="bdd26-102">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="bdd26-102">SWIFT Receive Adapter Store and Forward</span></span>
<span data-ttu-id="bdd26-103">接收适配器接收来自 SWIFT 的存储和转发 (SnF) 队列消息。</span><span class="sxs-lookup"><span data-stu-id="bdd26-103">The receive adapter receives messages from the SWIFT store and forward (SnF) queue.</span></span> <span data-ttu-id="bdd26-104">若要从队列接收消息，适配器必须使用 SnF 队列打开会话。</span><span class="sxs-lookup"><span data-stu-id="bdd26-104">To receive messages from the queue, the adapter must open a session with the SnF queue.</span></span> <span data-ttu-id="bdd26-105">若要打开队列，必须建立与队列的会话的专用客户端进程。</span><span class="sxs-lookup"><span data-stu-id="bdd26-105">To open the queue, it must have a dedicated client process that establishes the session with the queue.</span></span> <span data-ttu-id="bdd26-106">在设计中，作为 COM plus 的进程外组件实现此过程。</span><span class="sxs-lookup"><span data-stu-id="bdd26-106">In the design, this process is implemented as a COM plus out-of-proc component.</span></span>  
  
## <a name="push-session-store-and-forward-sequence"></a><span data-ttu-id="bdd26-107">将会话存储和转发序列推送</span><span class="sxs-lookup"><span data-stu-id="bdd26-107">Push session store and forward sequence</span></span>  
 <span data-ttu-id="bdd26-108">以下列表介绍的存储和转发的序列。</span><span class="sxs-lookup"><span data-stu-id="bdd26-108">The following list describes the store and forward sequence.</span></span>  
  
1.  <span data-ttu-id="bdd26-109">开始处理消息的服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdd26-109">Start the server application that processes the messages.</span></span>  
  
2.  <span data-ttu-id="bdd26-110">服务器进程将所需的安全上下文作为输入基元期间 Sw:HandleInitRequest 与第一个 SwCallback 上打开。</span><span class="sxs-lookup"><span data-stu-id="bdd26-110">The server process opens the required security contexts during the first SwCallback with the Sw:HandleInitRequest as an input primitive.</span></span>  
  
3.  <span data-ttu-id="bdd26-111">服务器响应与一个或两个 Sw:CryptoMode 和设置为高级 Sw:FACryptoMode Sw:HandleInitRequest。</span><span class="sxs-lookup"><span data-stu-id="bdd26-111">The server responds to the Sw:HandleInitRequest with either or both Sw:CryptoMode and Sw:FACryptoMode set to Advanced.</span></span>  
  
     <span data-ttu-id="bdd26-112">服务器现已开始处理传入的请求。</span><span class="sxs-lookup"><span data-stu-id="bdd26-112">The server is now ready to start processing incoming requests.</span></span>  
  
4.  <span data-ttu-id="bdd26-113">若要启动队列的消息传递，客户端进程启动推送会话。</span><span class="sxs-lookup"><span data-stu-id="bdd26-113">To start the delivery of messages from a queue, a client process starts a push session.</span></span> <span data-ttu-id="bdd26-114">基于适配器配置 （push 模式），接收适配器生成名为 SnFQueueManager.exe 获取在推送模式下队列的客户端进程。</span><span class="sxs-lookup"><span data-stu-id="bdd26-114">Based on the adapter configuration (push mode), the receive adapter spawns a client process called SnFQueueManager.exe to acquire the queue in push mode.</span></span>  
  
5.  <span data-ttu-id="bdd26-115">SwCall() 作为输入基元运行与 Sw:AcquireSnFRequest （在 Sw:ExchangeSnFRequest)。</span><span class="sxs-lookup"><span data-stu-id="bdd26-115">An SwCall() runs with Sw:AcquireSnFRequest (within the Sw:ExchangeSnFRequest) as an input primitive.</span></span> <span data-ttu-id="bdd26-116">此请求启动与所指示的队列的会话 （如果 SwSec:AuthorisationContext 具有必需的 RBAC 角色）。</span><span class="sxs-lookup"><span data-stu-id="bdd26-116">This request starts a session with the queue indicated (if the SwSec:AuthorisationContext has the required RBAC role).</span></span>  
  
6.  <span data-ttu-id="bdd26-117">Sw:AcquireStatus 中响应与"已接受"后立即, SWIFTNet SnF 开始将消息发送到中获取指定的服务器。</span><span class="sxs-lookup"><span data-stu-id="bdd26-117">Immediately after responding with “Accepted” in the Sw:AcquireStatus, SWIFTNet SnF starts sending messages to the server as specified in the acquire.</span></span> <span data-ttu-id="bdd26-118">如果未尚未启动接收适配器，消息将收到异常。</span><span class="sxs-lookup"><span data-stu-id="bdd26-118">If the receive adapter was not yet started, messages get exceptions.</span></span> <span data-ttu-id="bdd26-119">（这是就是必须已启动的接收适配器的原因）。</span><span class="sxs-lookup"><span data-stu-id="bdd26-119">(That is why it is important to have the receive adapters already started).</span></span>  
  
7.  <span data-ttu-id="bdd26-120">SWIFTNet SnF 启动推送数 （最大窗口大小） 的消息。</span><span class="sxs-lookup"><span data-stu-id="bdd26-120">SWIFTNet SnF starts pushing a number of messages (up to the window size).</span></span>  
  
8.  <span data-ttu-id="bdd26-121">为确认每条消息，推送新消息 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="bdd26-121">For every message acknowledged, a new message (if any) is pushed.</span></span>  
  
9. <span data-ttu-id="bdd26-122">客户端进程 (SnFQueueManager.exe) 完成其工作后，可以立即终止。</span><span class="sxs-lookup"><span data-stu-id="bdd26-122">The client process (SnFQueueManager.exe) has done its job and can now terminate.</span></span> <span data-ttu-id="bdd26-123">该过程会发出 SwSec:DestroyContextRequest，清理打开安全上下文。</span><span class="sxs-lookup"><span data-stu-id="bdd26-123">The process issues SwSec:DestroyContextRequest, which cleans up the open security contexts.</span></span> <span data-ttu-id="bdd26-124">Sw:TermRequest 之后, 在进程退出。</span><span class="sxs-lookup"><span data-stu-id="bdd26-124">After the Sw:TermRequest, the process exits.</span></span>  
  
### <a name="message-correlation"></a><span data-ttu-id="bdd26-125">消息相关性</span><span class="sxs-lookup"><span data-stu-id="bdd26-125">Message Correlation</span></span>  
 <span data-ttu-id="bdd26-126">RequestRef 字段是将保留并替换为返回响应消息中接收适配器。</span><span class="sxs-lookup"><span data-stu-id="bdd26-126">The RequestRef field is preserved and substituted back in the response messages by the receive adapter.</span></span> <span data-ttu-id="bdd26-127">这可确保传入消息和响应消息之间的端到端相关性</span><span class="sxs-lookup"><span data-stu-id="bdd26-127">This ensures end to end correlation between the incoming message and the response message</span></span>  
  
### <a name="duplicate-processing"></a><span data-ttu-id="bdd26-128">重复处理</span><span class="sxs-lookup"><span data-stu-id="bdd26-128">Duplicate processing</span></span>  
 <span data-ttu-id="bdd26-129">如果 FileAct 请求和适配器实例接收，则接收的消息可能重复的指示符节点，然后，它必须检查以查看引用的传输已成功完成，或者如果它出现故障，并采取相应的措施。</span><span class="sxs-lookup"><span data-stu-id="bdd26-129">If receiving a FileAct request, and the adapter instance receives a message with a Possible Duplicate Indicator node, then it must check to see if the referenced transfer has already completed successfully or if it has failed, and take the appropriate action.</span></span> <span data-ttu-id="bdd26-130">如果文件传输适配器更新为"重复"传输状态已执行，否则它将更新其为"已接受"。</span><span class="sxs-lookup"><span data-stu-id="bdd26-130">If the file transfer has already taken place then the adapter updates the transfer status as “Duplicate” otherwise it updates it as “Accepted.”</span></span>  
  
### <a name="acknowledgments"></a><span data-ttu-id="bdd26-131">确认</span><span class="sxs-lookup"><span data-stu-id="bdd26-131">Acknowledgments</span></span>  
 <span data-ttu-id="bdd26-132">如果发件人请求 FileAct 请求确认，适配器将检查文件传输完成事件，并生成验证文件摘要值后的确认。</span><span class="sxs-lookup"><span data-stu-id="bdd26-132">If the sender requests an acknowledgement for a FileAct request, the adapter checks for the file transfer completion event and generates the acknowledgement after verifying the file digest value.</span></span> <span data-ttu-id="bdd26-133">适配器向 BizTalk 发送适配器以选择它并将其发送给发件人发送确认消息。</span><span class="sxs-lookup"><span data-stu-id="bdd26-133">The adapter sends the acknowledgement message to BizTalk for the send adapter to pick it up and send it to the sender.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd26-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdd26-134">See Also</span></span>  
 <span data-ttu-id="bdd26-135">[SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="bdd26-135">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="bdd26-136">[SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="bdd26-136">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="bdd26-137">[SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="bdd26-137">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="bdd26-138">[SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="bdd26-138">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 [<span data-ttu-id="bdd26-139">SWIFT 接收适配器同步和延迟模式</span><span class="sxs-lookup"><span data-stu-id="bdd26-139">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)