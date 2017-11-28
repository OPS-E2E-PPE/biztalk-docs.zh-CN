---
title: "发送的请求作出响应的接口适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb8ce9b625bfea144f9a4a615a604efdbe2a3cb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a><span data-ttu-id="aee4b-102">用于要求响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="aee4b-102">Interfaces for a Solicit-Response Send Adapter</span></span>
<span data-ttu-id="aee4b-103">发送适配器与接收适配器使用相同的批处理机制将响应消息提交回服务器中。</span><span class="sxs-lookup"><span data-stu-id="aee4b-103">Send adapters use the same batch mechanism as receive adapters to submit response messages back into the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aee4b-104">建议让请求-响应适配器异步处理消息。</span><span class="sxs-lookup"><span data-stu-id="aee4b-104">It is recommended that a solicit-response adapter is process messages asynchronously.</span></span> <span data-ttu-id="aee4b-105">如果适配器以同步方式处理消息，会有消息重复的风险。</span><span class="sxs-lookup"><span data-stu-id="aee4b-105">If the adapter processes message in a synchronous manner, there is a risk of message duplication.</span></span>  
  
 <span data-ttu-id="aee4b-106">发送适配器需要实现以下接口才能在请求-响应模式中工作：</span><span class="sxs-lookup"><span data-stu-id="aee4b-106">Send adapters need to implement the following interfaces to work in solicit-response mode:</span></span>  
  
-   <span data-ttu-id="aee4b-107">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="aee4b-107">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="aee4b-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="aee4b-108">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="aee4b-109">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="aee4b-109">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="aee4b-110">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="aee4b-110">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="aee4b-111">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="aee4b-111">**IBTTransmitter**</span></span>  
  
-   <span data-ttu-id="aee4b-112">**IBTTransmitterBatch**和**IBTBatchTransmitter** （如果发送批处理，则需要）</span><span class="sxs-lookup"><span data-stu-id="aee4b-112">**IBTTransmitterBatch** and **IBTBatchTransmitter** (if send batching is required)</span></span>  
  
-   <span data-ttu-id="aee4b-113">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="aee4b-113">**IBTBatchCallBack**</span></span>  
  
 <span data-ttu-id="aee4b-114">对象交互涉及的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="aee4b-114">The steps involved in the object interaction are as follows:</span></span>  
  
1.  <span data-ttu-id="aee4b-115">适配器发送要求消息后，会从目标服务器收到响应消息。</span><span class="sxs-lookup"><span data-stu-id="aee4b-115">After the adapter sends a solicit message, it receives back a response message from that destination server.</span></span> <span data-ttu-id="aee4b-116">然后会从传输代理获得一个批。</span><span class="sxs-lookup"><span data-stu-id="aee4b-116">It then obtains a batch from the transport proxy.</span></span>  
  
2.  <span data-ttu-id="aee4b-117">适配器将响应消息添加到批处理，通过调用**IBTTransportProxy::SubmitResponseMessage**。</span><span class="sxs-lookup"><span data-stu-id="aee4b-117">The adapter adds the response message to the batch by calling **IBTTransportProxy::SubmitResponseMessage**.</span></span>  
  
3.  <span data-ttu-id="aee4b-118">适配器通过调用提交批**IBTTransportProxy::Done**传递中指向的指针的其**IBTBatchComplete**从消息引擎回调的接口。</span><span class="sxs-lookup"><span data-stu-id="aee4b-118">The adapter submits the batch by calling **IBTTransportProxy::Done** passing in a pointer to its **IBTBatchComplete** interface for the callback from the Messaging Engine.</span></span>  
  
4.  <span data-ttu-id="aee4b-119">消息引擎调用该适配器**IBTBatchCallBack::BatchComplete**使用传输代理通知它提交操作的结果的回调方法。</span><span class="sxs-lookup"><span data-stu-id="aee4b-119">The Messaging Engine calls the adapter's **IBTBatchCallBack::BatchComplete** callback method using the transport proxy notifying it of the result of submission operation.</span></span>  
  
 <span data-ttu-id="aee4b-120">下图显示了创建要求-响应发送适配器所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="aee4b-120">The following figure shows the object interactions involved in creating a solicit-response send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
<span data-ttu-id="aee4b-121">要求-响应发送适配器的交互图</span><span class="sxs-lookup"><span data-stu-id="aee4b-121">Interaction diagram for a solicit-response send adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee4b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aee4b-122">See Also</span></span>  
 <span data-ttu-id="aee4b-123">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="aee4b-123">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="aee4b-124">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="aee4b-124">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="aee4b-125">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="aee4b-125">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="aee4b-126">[发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="aee4b-126">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="aee4b-127">[异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="aee4b-127">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="aee4b-128">[同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="aee4b-128">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="aee4b-129">[异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="aee4b-129">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="aee4b-130">事务异步批处理支持发送适配器的的接口</span><span class="sxs-lookup"><span data-stu-id="aee4b-130">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)