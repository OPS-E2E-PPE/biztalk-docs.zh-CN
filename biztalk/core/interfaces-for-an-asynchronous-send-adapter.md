---
title: 发送适配器的异步接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8f87fe34d75f0e511568fa0e91088a1b7608a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331506"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a><span data-ttu-id="5a9ce-102">发送适配器的异步接口</span><span class="sxs-lookup"><span data-stu-id="5a9ce-102">Interfaces for an Asynchronous Send Adapter</span></span>
<span data-ttu-id="5a9ce-103">一次发送一个消息的适配器可以同步或异步发送消息。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-103">Adapters sending messages one at a time may send messages either synchronously or asynchronously.</span></span> <span data-ttu-id="5a9ce-104">它不会阻止传输代理线程，但执行发送操作时，而是使用单独的线程时，适配器将消息异步发送。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-104">An adapter sends messages asynchronously when it does not block the transport proxy thread but rather uses a separate thread while performing the send operations.</span></span> <span data-ttu-id="5a9ce-105">若要能够以异步方式发送消息，适配器必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="5a9ce-105">To be able to send messages asynchronously, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="5a9ce-106">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="5a9ce-106">**IBTTransport**</span></span>  
  
- <span data-ttu-id="5a9ce-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="5a9ce-107">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="5a9ce-108">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="5a9ce-108">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="5a9ce-109">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="5a9ce-109">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="5a9ce-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="5a9ce-110">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="5a9ce-111">以下步骤介绍发送适配器执行传输出 server 消息引擎的请求消息的操作的序列：</span><span class="sxs-lookup"><span data-stu-id="5a9ce-111">The following steps describe the sequence of actions that the send adapter performs to transmit messages out of the server at the request of the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="5a9ce-112">消息引擎将使用传输代理要传递给发送适配器的传出消息，通过调用**TransmitMessage**方法**IBTTransmitter**接口。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-112">The Messaging Engine uses the transport proxy to pass an outgoing message to a send adapter by calling the **TransmitMessage** method of the **IBTTransmitter** interface.</span></span>  
  
2.  <span data-ttu-id="5a9ce-113">适配器会立即返回从**TransmitMessage**后存储消息要发送到某些内部队列，并返回`False`有关**bDeleteMessage**。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-113">The adapter returns immediately from **TransmitMessage** after storing the message to be sent to some internal queue, and returns `False` for **bDeleteMessage**.</span></span> <span data-ttu-id="5a9ce-114">这将告知消息引擎会将消息传输以异步方式。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-114">This tells the Messaging Engine the message will be transmitted in an asynchronous manner.</span></span>  
  
3.  <span data-ttu-id="5a9ce-115">适配器发送的消息使用其自己的线程池。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-115">The adapter sends the message using its own thread pool.</span></span>  
  
4.  <span data-ttu-id="5a9ce-116">发送操作完成后，适配器从 MessageBox 数据库中删除原始消息。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-116">After the send operation completes, the adapter deletes the original message from the MessageBox database.</span></span> <span data-ttu-id="5a9ce-117">它从消息引擎使用获取一批**IBTTransportBatch.GetBatch**方法的传输代理，然后调用**DeleteMessage**。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-117">It obtains a batch from the Messaging Engine using the **IBTTransportBatch.GetBatch** method of the transport proxy, and then calls **DeleteMessage**.</span></span>  
  
     <span data-ttu-id="5a9ce-118">下图显示了对象交互涉及创建异步发送适配器。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-118">The following figure shows the object interactions involved in creating an asynchronous send adapter.</span></span>  
  
     <span data-ttu-id="5a9ce-119">![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")</span><span class="sxs-lookup"><span data-stu-id="5a9ce-119">![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")</span></span>  
<span data-ttu-id="5a9ce-120">以异步方式发送一条消息的工作流</span><span class="sxs-lookup"><span data-stu-id="5a9ce-120">Workflow for sending a message asynchronously</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a9ce-121">我们建议适配器对当前正在处理的消息的计数。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-121">We recommend that the adapter keep a count of the messages currently being processed.</span></span> <span data-ttu-id="5a9ce-122">适配器应该一直阻止**Terminate**方法，直到消息计数归零。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-122">The adapter should block the **Terminate** method until the message count has reached zero.</span></span> <span data-ttu-id="5a9ce-123">对于发送适配器，应适当地处理正在处理的消息。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-123">For send adapters, messages that are being processed should be handled appropriately.</span></span> <span data-ttu-id="5a9ce-124">这意味着已成功异步传送的任何消息，应删除来自适配器的专用应用程序的消息队列，以防止消息被发送两次。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-124">This means that any message that was successfully delivered asynchronously should be deleted from the adapter's private application message queue to prevent messages from being sent twice.</span></span> <span data-ttu-id="5a9ce-125">一般情况下后, **Terminate**调用由消息引擎它不接受发布新消息来自适配器的请求。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-125">In general, after **Terminate** is called by the Messaging Engine it does not accept requests to publish new messages from the adapter.</span></span> <span data-ttu-id="5a9ce-126">此规则的例外是与要求-响应对相关的响应消息。</span><span class="sxs-lookup"><span data-stu-id="5a9ce-126">The exception to this is response messages related to solicit-response pairs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a9ce-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a9ce-127">See Also</span></span>  
 <span data-ttu-id="5a9ce-128">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="5a9ce-128">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="5a9ce-129">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5a9ce-129">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="5a9ce-130">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5a9ce-130">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="5a9ce-131">[发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5a9ce-131">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="5a9ce-132">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5a9ce-132">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="5a9ce-133">[异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5a9ce-133">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="5a9ce-134">[事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5a9ce-134">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="5a9ce-135">要求-响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="5a9ce-135">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)