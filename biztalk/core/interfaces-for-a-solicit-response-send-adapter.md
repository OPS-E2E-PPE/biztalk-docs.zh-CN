---
title: 发送适配器的接口的要求响应 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5056092886ad9d73d3db3dcc910038bc7dcd6e4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024131"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a><span data-ttu-id="6fe7b-102">用于要求响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="6fe7b-102">Interfaces for a Solicit-Response Send Adapter</span></span>
<span data-ttu-id="6fe7b-103">发送适配器与接收适配器使用相同的批处理机制将响应消息提交回服务器中。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-103">Send adapters use the same batch mechanism as receive adapters to submit response messages back into the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fe7b-104">建议让请求-响应适配器异步处理消息。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-104">It is recommended that a solicit-response adapter is process messages asynchronously.</span></span> <span data-ttu-id="6fe7b-105">如果适配器以同步方式处理消息，会有消息重复的风险。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-105">If the adapter processes message in a synchronous manner, there is a risk of message duplication.</span></span>  
  
 <span data-ttu-id="6fe7b-106">发送适配器需要实现以下接口才能在请求-响应模式中工作：</span><span class="sxs-lookup"><span data-stu-id="6fe7b-106">Send adapters need to implement the following interfaces to work in solicit-response mode:</span></span>  
  
- <span data-ttu-id="6fe7b-107">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="6fe7b-107">**IBTTransport**</span></span>  
  
- <span data-ttu-id="6fe7b-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="6fe7b-108">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="6fe7b-109">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="6fe7b-109">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="6fe7b-110">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="6fe7b-110">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="6fe7b-111">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="6fe7b-111">**IBTTransmitter**</span></span>  
  
- <span data-ttu-id="6fe7b-112">**IBTTransmitterBatch**并**IBTBatchTransmitter** （如果发送批处理是必需的）</span><span class="sxs-lookup"><span data-stu-id="6fe7b-112">**IBTTransmitterBatch** and **IBTBatchTransmitter** (if send batching is required)</span></span>  
  
- <span data-ttu-id="6fe7b-113">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="6fe7b-113">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="6fe7b-114">对象交互涉及的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="6fe7b-114">The steps involved in the object interaction are as follows:</span></span>  
  
1. <span data-ttu-id="6fe7b-115">适配器发送要求消息后，会从目标服务器收到响应消息。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-115">After the adapter sends a solicit message, it receives back a response message from that destination server.</span></span> <span data-ttu-id="6fe7b-116">然后会从传输代理获得一个批。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-116">It then obtains a batch from the transport proxy.</span></span>  
  
2. <span data-ttu-id="6fe7b-117">适配器通过调用将响应消息添加到批**ibttransportproxy:: Submitresponsemessage**。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-117">The adapter adds the response message to the batch by calling **IBTTransportProxy::SubmitResponseMessage**.</span></span>  
  
3. <span data-ttu-id="6fe7b-118">适配器通过调用提交批处理**IBTTransportProxy::Done**传入一个指向其**IBTBatchComplete**从消息引擎回调的接口。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-118">The adapter submits the batch by calling **IBTTransportProxy::Done** passing in a pointer to its **IBTBatchComplete** interface for the callback from the Messaging Engine.</span></span>  
  
4. <span data-ttu-id="6fe7b-119">消息引擎调用适配器的**ibtbatchcallback:: Batchcomplete**使用传输代理通知它提交操作的结果的回调方法。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-119">The Messaging Engine calls the adapter's **IBTBatchCallBack::BatchComplete** callback method using the transport proxy notifying it of the result of submission operation.</span></span>  
  
   <span data-ttu-id="6fe7b-120">下图显示了创建要求-响应发送适配器所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="6fe7b-120">The following figure shows the object interactions involved in creating a solicit-response send adapter.</span></span>  
  
   <span data-ttu-id="6fe7b-121">![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")</span><span class="sxs-lookup"><span data-stu-id="6fe7b-121">![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")</span></span>  
   <span data-ttu-id="6fe7b-122">要求-响应发送适配器的交互图</span><span class="sxs-lookup"><span data-stu-id="6fe7b-122">Interaction diagram for a solicit-response send adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe7b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fe7b-123">See Also</span></span>  
 <span data-ttu-id="6fe7b-124">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6fe7b-124">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="6fe7b-125">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fe7b-125">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="6fe7b-126">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fe7b-126">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="6fe7b-127">[发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fe7b-127">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="6fe7b-128">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fe7b-128">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="6fe7b-129">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fe7b-129">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="6fe7b-130">[异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fe7b-130">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="6fe7b-131">支持事务性异步批处理的发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="6fe7b-131">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)