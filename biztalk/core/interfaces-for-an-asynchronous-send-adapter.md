---
title: "异步接口发送适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db156f5a95a088ae706bb2b1c801d8dee89cdece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a><span data-ttu-id="a5337-102">异步接口发送适配器</span><span class="sxs-lookup"><span data-stu-id="a5337-102">Interfaces for an Asynchronous Send Adapter</span></span>
<span data-ttu-id="a5337-103">一次发送一条消息的适配器可以同步或异步发送消息。</span><span class="sxs-lookup"><span data-stu-id="a5337-103">Adapters sending messages one at a time may send messages either synchronously or asynchronously.</span></span> <span data-ttu-id="a5337-104">如果适配器在执行发送操作时不阻止传输代理线程而是使用单独的线程，则异步发送消息。</span><span class="sxs-lookup"><span data-stu-id="a5337-104">An adapter sends messages asynchronously when it does not block the transport proxy thread but rather uses a separate thread while performing the send operations.</span></span> <span data-ttu-id="a5337-105">为了能够异步发送消息，适配器需要实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="a5337-105">To be able to send messages asynchronously, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="a5337-106">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="a5337-106">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="a5337-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="a5337-107">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="a5337-108">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="a5337-108">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="a5337-109">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="a5337-109">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="a5337-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="a5337-110">**IBTTransmitter**</span></span>  
  
 <span data-ttu-id="a5337-111">以下步骤说明了发送适配器应消息引擎的请求从服务器传输消息时执行的一系列操作：</span><span class="sxs-lookup"><span data-stu-id="a5337-111">The following steps describe the sequence of actions that the send adapter performs to transmit messages out of the server at the request of the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="a5337-112">The Messaging Engine 使用传输代理将传出的消息传递给发送适配器，通过调用**TransmitMessage**方法**IBTTransmitter**接口。</span><span class="sxs-lookup"><span data-stu-id="a5337-112">The Messaging Engine uses the transport proxy to pass an outgoing message to a send adapter by calling the **TransmitMessage** method of the **IBTTransmitter** interface.</span></span>  
  
2.  <span data-ttu-id="a5337-113">适配器将立即返回从**TransmitMessage**后存储消息发送到某些内部队列，并返回`False`为**bDeleteMessage**。</span><span class="sxs-lookup"><span data-stu-id="a5337-113">The adapter returns immediately from **TransmitMessage** after storing the message to be sent to some internal queue, and returns `False` for **bDeleteMessage**.</span></span> <span data-ttu-id="a5337-114">这样可以通知消息引擎消息将在异步模式下传输。</span><span class="sxs-lookup"><span data-stu-id="a5337-114">This tells the Messaging Engine the message will be transmitted in an asynchronous manner.</span></span>  
  
3.  <span data-ttu-id="a5337-115">适配器使用自己的线程池发送消息。</span><span class="sxs-lookup"><span data-stu-id="a5337-115">The adapter sends the message using its own thread pool.</span></span>  
  
4.  <span data-ttu-id="a5337-116">发送操作完成后，适配器从 MessageBox 数据库删除原始消息。</span><span class="sxs-lookup"><span data-stu-id="a5337-116">After the send operation completes, the adapter deletes the original message from the MessageBox database.</span></span> <span data-ttu-id="a5337-117">从消息引擎使用，它获取一批**IBTTransportBatch.GetBatch**传输代理，然后调用的方法**DeleteMessage**。</span><span class="sxs-lookup"><span data-stu-id="a5337-117">It obtains a batch from the Messaging Engine using the **IBTTransportBatch.GetBatch** method of the transport proxy, and then calls **DeleteMessage**.</span></span>  
  
     <span data-ttu-id="a5337-118">下图显示了创建异步发送适配器所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="a5337-118">The following figure shows the object interactions involved in creating an asynchronous send adapter.</span></span>  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
<span data-ttu-id="a5337-119">异步发送消息的工作流</span><span class="sxs-lookup"><span data-stu-id="a5337-119">Workflow for sending a message asynchronously</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5337-120">我们建议适配器对当前正处理的消息进行计数。</span><span class="sxs-lookup"><span data-stu-id="a5337-120">We recommend that the adapter keep a count of the messages currently being processed.</span></span> <span data-ttu-id="a5337-121">适配器应阻止**终止**方法，直到消息计数已达到零。</span><span class="sxs-lookup"><span data-stu-id="a5337-121">The adapter should block the **Terminate** method until the message count has reached zero.</span></span> <span data-ttu-id="a5337-122">对于发送适配器，正处理的消息应被适当处理。</span><span class="sxs-lookup"><span data-stu-id="a5337-122">For send adapters, messages that are being processed should be handled appropriately.</span></span> <span data-ttu-id="a5337-123">这意味着，已成功异步传送的任何消息应该从适配器的专用应用程序消息队列中删除，以防止消息被发送两次。</span><span class="sxs-lookup"><span data-stu-id="a5337-123">This means that any message that was successfully delivered asynchronously should be deleted from the adapter's private application message queue to prevent messages from being sent twice.</span></span> <span data-ttu-id="a5337-124">一般情况下之后,**终止**调用由消息传送引擎它不接受请求将从适配器的新消息发布。</span><span class="sxs-lookup"><span data-stu-id="a5337-124">In general, after **Terminate** is called by the Messaging Engine it does not accept requests to publish new messages from the adapter.</span></span> <span data-ttu-id="a5337-125">这种情况的一个例外是与要求-响应对相关的消息。</span><span class="sxs-lookup"><span data-stu-id="a5337-125">The exception to this is response messages related to solicit-response pairs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5337-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5337-126">See Also</span></span>  
 <span data-ttu-id="a5337-127">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a5337-127">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="a5337-128">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a5337-128">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="a5337-129">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a5337-129">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="a5337-130">[发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a5337-130">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="a5337-131">[同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a5337-131">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="a5337-132">[异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a5337-132">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="a5337-133">[事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a5337-133">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="a5337-134">适配器发送的请求作出响应的接口</span><span class="sxs-lookup"><span data-stu-id="a5337-134">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)