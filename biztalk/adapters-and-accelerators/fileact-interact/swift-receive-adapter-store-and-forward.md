---
title: SWIFT 接收适配器存储和转发 |Microsoft 文档
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
ms.openlocfilehash: 315b9bbe6985bbce5ccb44d8d4846b18730f292b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224469"
---
# <a name="swift-receive-adapter-store-and-forward"></a><span data-ttu-id="9fea6-102">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="9fea6-102">SWIFT Receive Adapter Store and Forward</span></span>
<span data-ttu-id="9fea6-103">接收适配器从 SWIFT 存储和转发 (SnF) 队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="9fea6-103">The receive adapter receives messages from the SWIFT store and forward (SnF) queue.</span></span> <span data-ttu-id="9fea6-104">若要从队列接收消息，适配器必须使用 SnF 队列打开会话。</span><span class="sxs-lookup"><span data-stu-id="9fea6-104">To receive messages from the queue, the adapter must open a session with the SnF queue.</span></span> <span data-ttu-id="9fea6-105">若要打开队列，则必须建立与队列的会话的专用客户端进程。</span><span class="sxs-lookup"><span data-stu-id="9fea6-105">To open the queue, it must have a dedicated client process that establishes the session with the queue.</span></span> <span data-ttu-id="9fea6-106">在设计中，作为 COM plus 进程外的组件来实现此过程。</span><span class="sxs-lookup"><span data-stu-id="9fea6-106">In the design, this process is implemented as a COM plus out-of-proc component.</span></span>  
  
## <a name="push-session-store-and-forward-sequence"></a><span data-ttu-id="9fea6-107">将会话存储和转发序列推送</span><span class="sxs-lookup"><span data-stu-id="9fea6-107">Push session store and forward sequence</span></span>  
 <span data-ttu-id="9fea6-108">以下列表介绍的存储和转发的序列。</span><span class="sxs-lookup"><span data-stu-id="9fea6-108">The following list describes the store and forward sequence.</span></span>  
  
1.  <span data-ttu-id="9fea6-109">启动服务器应用程序处理消息。</span><span class="sxs-lookup"><span data-stu-id="9fea6-109">Start the server application that processes the messages.</span></span>  
  
2.  <span data-ttu-id="9fea6-110">服务器进程将所需的安全上下文作为输入基元期间 Sw:HandleInitRequest 与第一个 SwCallback 上打开。</span><span class="sxs-lookup"><span data-stu-id="9fea6-110">The server process opens the required security contexts during the first SwCallback with the Sw:HandleInitRequest as an input primitive.</span></span>  
  
3.  <span data-ttu-id="9fea6-111">服务器响应的其中一种或两个 Sw:CryptoMode 和设置为高级 Sw:FACryptoMode Sw:HandleInitRequest。</span><span class="sxs-lookup"><span data-stu-id="9fea6-111">The server responds to the Sw:HandleInitRequest with either or both Sw:CryptoMode and Sw:FACryptoMode set to Advanced.</span></span>  
  
     <span data-ttu-id="9fea6-112">服务器现已开始处理传入请求。</span><span class="sxs-lookup"><span data-stu-id="9fea6-112">The server is now ready to start processing incoming requests.</span></span>  
  
4.  <span data-ttu-id="9fea6-113">若要启动队列消息的传递，客户端进程启动推送会话。</span><span class="sxs-lookup"><span data-stu-id="9fea6-113">To start the delivery of messages from a queue, a client process starts a push session.</span></span> <span data-ttu-id="9fea6-114">接收适配器根据适配器配置 （推送模式下），生成一个称为 SnFQueueManager.exe 获取在推送模式下队列的客户端进程。</span><span class="sxs-lookup"><span data-stu-id="9fea6-114">Based on the adapter configuration (push mode), the receive adapter spawns a client process called SnFQueueManager.exe to acquire the queue in push mode.</span></span>  
  
5.  <span data-ttu-id="9fea6-115">SwCall() 运行 Sw:AcquireSnFRequest （在 Sw:ExchangeSnFRequest) 作为输入基元。</span><span class="sxs-lookup"><span data-stu-id="9fea6-115">An SwCall() runs with Sw:AcquireSnFRequest (within the Sw:ExchangeSnFRequest) as an input primitive.</span></span> <span data-ttu-id="9fea6-116">此请求启动与指示队列的会话 （如果 SwSec:AuthorisationContext 具有所需的 RBAC 角色）。</span><span class="sxs-lookup"><span data-stu-id="9fea6-116">This request starts a session with the queue indicated (if the SwSec:AuthorisationContext has the required RBAC role).</span></span>  
  
6.  <span data-ttu-id="9fea6-117">在响应中 Sw:AcquireStatus"已接受"之后立即, SWIFTNet SnF 启动将消息发送到中获取指定的服务器。</span><span class="sxs-lookup"><span data-stu-id="9fea6-117">Immediately after responding with “Accepted” in the Sw:AcquireStatus, SWIFTNet SnF starts sending messages to the server as specified in the acquire.</span></span> <span data-ttu-id="9fea6-118">如果接收适配器未尚未启动，消息将获得异常。</span><span class="sxs-lookup"><span data-stu-id="9fea6-118">If the receive adapter was not yet started, messages get exceptions.</span></span> <span data-ttu-id="9fea6-119">（这是非常重要具有已开始接收适配器的原因）。</span><span class="sxs-lookup"><span data-stu-id="9fea6-119">(That is why it is important to have the receive adapters already started).</span></span>  
  
7.  <span data-ttu-id="9fea6-120">SWIFTNet SnF 开始推送数消息 （最多的窗口大小）。</span><span class="sxs-lookup"><span data-stu-id="9fea6-120">SWIFTNet SnF starts pushing a number of messages (up to the window size).</span></span>  
  
8.  <span data-ttu-id="9fea6-121">确认每个消息，推送一条新消息 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="9fea6-121">For every message acknowledged, a new message (if any) is pushed.</span></span>  
  
9. <span data-ttu-id="9fea6-122">客户端进程 (SnFQueueManager.exe) 完成其工作时，并可以立即终止。</span><span class="sxs-lookup"><span data-stu-id="9fea6-122">The client process (SnFQueueManager.exe) has done its job and can now terminate.</span></span> <span data-ttu-id="9fea6-123">进程发出 SwSec:DestroyContextRequest，清理打开的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="9fea6-123">The process issues SwSec:DestroyContextRequest, which cleans up the open security contexts.</span></span> <span data-ttu-id="9fea6-124">后 Sw:TermRequest，在进程退出。</span><span class="sxs-lookup"><span data-stu-id="9fea6-124">After the Sw:TermRequest, the process exits.</span></span>  
  
### <a name="message-correlation"></a><span data-ttu-id="9fea6-125">消息相关性</span><span class="sxs-lookup"><span data-stu-id="9fea6-125">Message Correlation</span></span>  
 <span data-ttu-id="9fea6-126">RequestRef 字段是将保留并在响应消息中返回替换由接收适配器。</span><span class="sxs-lookup"><span data-stu-id="9fea6-126">The RequestRef field is preserved and substituted back in the response messages by the receive adapter.</span></span> <span data-ttu-id="9fea6-127">这可确保传入的消息和响应消息之间的端到端相关性</span><span class="sxs-lookup"><span data-stu-id="9fea6-127">This ensures end to end correlation between the incoming message and the response message</span></span>  
  
### <a name="duplicate-processing"></a><span data-ttu-id="9fea6-128">重复处理</span><span class="sxs-lookup"><span data-stu-id="9fea6-128">Duplicate processing</span></span>  
 <span data-ttu-id="9fea6-129">如果接收 FileAct 请求和适配器实例接收可能重复的指示器节点下，消息，则它必须检查以查看是否引用的传输已成功完成或已失败，并采取相应的措施。</span><span class="sxs-lookup"><span data-stu-id="9fea6-129">If receiving a FileAct request, and the adapter instance receives a message with a Possible Duplicate Indicator node, then it must check to see if the referenced transfer has already completed successfully or if it has failed, and take the appropriate action.</span></span> <span data-ttu-id="9fea6-130">如果文件传输已经完成，然后适配器更新工作项作为"副本"传输状态否则它将更新其为"已接受。"</span><span class="sxs-lookup"><span data-stu-id="9fea6-130">If the file transfer has already taken place then the adapter updates the transfer status as “Duplicate” otherwise it updates it as “Accepted.”</span></span>  
  
### <a name="acknowledgments"></a><span data-ttu-id="9fea6-131">鸣谢</span><span class="sxs-lookup"><span data-stu-id="9fea6-131">Acknowledgments</span></span>  
 <span data-ttu-id="9fea6-132">如果发件人请求 FileAct 请求确认，该适配器将检查文件传输完成事件，并生成验证文件摘要值后的确认。</span><span class="sxs-lookup"><span data-stu-id="9fea6-132">If the sender requests an acknowledgement for a FileAct request, the adapter checks for the file transfer completion event and generates the acknowledgement after verifying the file digest value.</span></span> <span data-ttu-id="9fea6-133">适配器将确认消息发送到 BizTalk 发送适配器选取它，并将其发送到发送方。</span><span class="sxs-lookup"><span data-stu-id="9fea6-133">The adapter sends the acknowledgement message to BizTalk for the send adapter to pick it up and send it to the sender.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fea6-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fea6-134">See Also</span></span>  
 <span data-ttu-id="9fea6-135">[SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="9fea6-135">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="9fea6-136">[SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="9fea6-136">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="9fea6-137">[SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="9fea6-137">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="9fea6-138">[SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="9fea6-138">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 [<span data-ttu-id="9fea6-139">SWIFT 接收适配器同步和延迟模式</span><span class="sxs-lookup"><span data-stu-id="9fea6-139">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)