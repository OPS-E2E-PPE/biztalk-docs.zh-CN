---
title: 接收适配器的接口的同步请求-响应 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c60832-52b5-4d2c-81ec-94c46c375b15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78be6c80937367b9ae3572125331d6c7e1b20bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981430"
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a><span data-ttu-id="633e8-102">同步请求-响应接收适配器的接口</span><span class="sxs-lookup"><span data-stu-id="633e8-102">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>
<span data-ttu-id="633e8-103">所有接收适配器都需要实现以下接口，然后才可以在请求-响应模式中工作：</span><span class="sxs-lookup"><span data-stu-id="633e8-103">All receive adapters need to implement the following interfaces to work in request-response mode:</span></span>  
  
- <span data-ttu-id="633e8-104">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="633e8-104">**IBTTransport**</span></span>  
  
- <span data-ttu-id="633e8-105">**IBTTransportControl** （仅适用于常规适配器）</span><span class="sxs-lookup"><span data-stu-id="633e8-105">**IBTTransportControl** (regular adapters only)</span></span>  
  
- <span data-ttu-id="633e8-106">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="633e8-106">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="633e8-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="633e8-107">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="633e8-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="633e8-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="633e8-109">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="633e8-109">**IBTBatchCallBack**</span></span>  
  
- <span data-ttu-id="633e8-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="633e8-110">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="633e8-111">支持请求-响应协议的接收适配器（例如，HTTP 接收适配器）在提交请求消息时执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="633e8-111">Receive adapters that support request-response protocols (for example, the HTTP receive adapter) perform the following actions when submitting request messages:</span></span>  
  
1. <span data-ttu-id="633e8-112">接收适配器接收传入的请求消息。</span><span class="sxs-lookup"><span data-stu-id="633e8-112">The receive adapter receives incoming request messages.</span></span> <span data-ttu-id="633e8-113">通过调用从传输代理上获取一批**GetBatch**方法**IBTTransportProxy**接口。</span><span class="sxs-lookup"><span data-stu-id="633e8-113">It obtains a batch from the transport proxy by calling the **GetBatch** method of the **IBTTransportProxy** interface.</span></span> <span data-ttu-id="633e8-114">此调用中，适配器将中的传递回调指针到其实现**IBTBatchCallBack.BatchComplete**方法。</span><span class="sxs-lookup"><span data-stu-id="633e8-114">In this call the adapter passes in a callback pointer to its implementation of the **IBTBatchCallBack.BatchComplete** method.</span></span>  
  
2. <span data-ttu-id="633e8-115">适配器通过调用将请求消息添加到批处理**SubmitRequestMessage**方法**IBTTransportBatch**接口，一次为每个请求消息。</span><span class="sxs-lookup"><span data-stu-id="633e8-115">The adapter adds request messages into the batch by calling the **SubmitRequestMessage** method of the **IBTTransportBatch** interface, once for each request message.</span></span>  
  
3. <span data-ttu-id="633e8-116">当所有消息都已都添加时，适配器调用**完成**方法**IBTTransportBatch**接口，它将提交到消息引擎通过传输代理批。</span><span class="sxs-lookup"><span data-stu-id="633e8-116">When all the messages have been added, the adapter calls the **Done**method of the **IBTTransportBatch** interface, which submits the batch to the Messaging Engine through the transport proxy.</span></span>  
  
4. <span data-ttu-id="633e8-117">处理批后，消息引擎调用适配器的**IBTBatchCallBack.BatchComplete**通过传输代理的回调方法。</span><span class="sxs-lookup"><span data-stu-id="633e8-117">After the batch has been processed, the Messaging Engine invokes the adapter's **IBTBatchCallBack.BatchComplete** callback method through the transport proxy.</span></span> <span data-ttu-id="633e8-118">提交状态作为 HRESULT 值的数组（与批处理中每个消息相对应）传递给适配器。</span><span class="sxs-lookup"><span data-stu-id="633e8-118">The status of the submission is passed to the adapter as an array of HRESULT values corresponding to each message in the batch.</span></span> <span data-ttu-id="633e8-119">如果批处理在管道中或业务流程中失败，则 SOAP 错误消息将作为响应返回给适配器。</span><span class="sxs-lookup"><span data-stu-id="633e8-119">If the batch fails, either in the pipeline or in the orchestration, the SOAP fault message is returned to the adapter as a response.</span></span>  
  
5. <span data-ttu-id="633e8-120">传入的请求消息可以有业务流程订户。</span><span class="sxs-lookup"><span data-stu-id="633e8-120">The incoming request messages may have orchestration subscribers.</span></span> <span data-ttu-id="633e8-121">在业务流程完成并已处理的请求消息后，消息引擎通过调用适配器的适配器发送响应消息通过传输代理**TransmitMessage** 方法**IBTTransmitter**接口。</span><span class="sxs-lookup"><span data-stu-id="633e8-121">After the orchestration completes and the request message has been processed, the Messaging Engine sends the response message through the transport proxy to the adapter by calling the adapter's **TransmitMessage** method from the **IBTTransmitter** interface.</span></span>  
  
6. <span data-ttu-id="633e8-122">适配器发送响应消息，然后从 MessageBox 数据库中删除原始消息。</span><span class="sxs-lookup"><span data-stu-id="633e8-122">The adapter sends a response message and deletes the original message from the MessageBox database.</span></span>  
  
   <span data-ttu-id="633e8-123">下图显示在创建同步的请求-响应接收适配器时涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="633e8-123">The following figure shows the object interactions involved in creating a synchronous request-response receive adapter.</span></span>  
  
   <span data-ttu-id="633e8-124">![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")</span><span class="sxs-lookup"><span data-stu-id="633e8-124">![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")</span></span>  
   <span data-ttu-id="633e8-125">接收适配器提交同步消息的工作流</span><span class="sxs-lookup"><span data-stu-id="633e8-125">Workflow for a receive adapter submitting a synchronous message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633e8-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="633e8-126">See Also</span></span>  
 <span data-ttu-id="633e8-127">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="633e8-127">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="633e8-128">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="633e8-128">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="633e8-129">[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="633e8-129">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="633e8-130">[接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="633e8-130">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="633e8-131">[接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="633e8-131">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="633e8-132">[接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="633e8-132">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="633e8-133">支持批处理的事务性接收适配器的接口</span><span class="sxs-lookup"><span data-stu-id="633e8-133">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)