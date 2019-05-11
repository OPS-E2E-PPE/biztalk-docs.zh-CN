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
ms.openlocfilehash: 3958629596a11bbfcb6ae109c36ab0237a780542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381873"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a><span data-ttu-id="f7077-102">发送适配器的接口的要求响应</span><span class="sxs-lookup"><span data-stu-id="f7077-102">Interfaces for a Solicit-Response Send Adapter</span></span>
<span data-ttu-id="f7077-103">发送适配器使用相同的批处理机制与接收适配器将响应消息提交回服务器。</span><span class="sxs-lookup"><span data-stu-id="f7077-103">Send adapters use the same batch mechanism as receive adapters to submit response messages back into the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7077-104">建议要求-响应适配器异步是处理消息。</span><span class="sxs-lookup"><span data-stu-id="f7077-104">It is recommended that a solicit-response adapter is process messages asynchronously.</span></span> <span data-ttu-id="f7077-105">如果适配器处理消息以同步方式，则消息重复的风险。</span><span class="sxs-lookup"><span data-stu-id="f7077-105">If the adapter processes message in a synchronous manner, there is a risk of message duplication.</span></span>  
  
 <span data-ttu-id="f7077-106">发送适配器需要实现以下接口，在要求-响应模式下工作：</span><span class="sxs-lookup"><span data-stu-id="f7077-106">Send adapters need to implement the following interfaces to work in solicit-response mode:</span></span>  
  
- <span data-ttu-id="f7077-107">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="f7077-107">**IBTTransport**</span></span>  
  
- <span data-ttu-id="f7077-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="f7077-108">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="f7077-109">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="f7077-109">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="f7077-110">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="f7077-110">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="f7077-111">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="f7077-111">**IBTTransmitter**</span></span>  
  
- <span data-ttu-id="f7077-112">**IBTTransmitterBatch**并**IBTBatchTransmitter** （如果发送批处理是必需的）</span><span class="sxs-lookup"><span data-stu-id="f7077-112">**IBTTransmitterBatch** and **IBTBatchTransmitter** (if send batching is required)</span></span>  
  
- <span data-ttu-id="f7077-113">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="f7077-113">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="f7077-114">中的对象交互涉及的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7077-114">The steps involved in the object interaction are as follows:</span></span>  
  
1. <span data-ttu-id="f7077-115">适配器发送要求消息后，它将接收返回的响应消息从目标服务器。</span><span class="sxs-lookup"><span data-stu-id="f7077-115">After the adapter sends a solicit message, it receives back a response message from that destination server.</span></span> <span data-ttu-id="f7077-116">然后，它获取一批从传输代理。</span><span class="sxs-lookup"><span data-stu-id="f7077-116">It then obtains a batch from the transport proxy.</span></span>  
  
2. <span data-ttu-id="f7077-117">适配器通过调用将响应消息添加到批**ibttransportproxy:: Submitresponsemessage**。</span><span class="sxs-lookup"><span data-stu-id="f7077-117">The adapter adds the response message to the batch by calling **IBTTransportProxy::SubmitResponseMessage**.</span></span>  
  
3. <span data-ttu-id="f7077-118">适配器通过调用提交批处理**IBTTransportProxy::Done**传入一个指向其**IBTBatchComplete**从消息引擎回调的接口。</span><span class="sxs-lookup"><span data-stu-id="f7077-118">The adapter submits the batch by calling **IBTTransportProxy::Done** passing in a pointer to its **IBTBatchComplete** interface for the callback from the Messaging Engine.</span></span>  
  
4. <span data-ttu-id="f7077-119">消息引擎调用适配器的**ibtbatchcallback:: Batchcomplete**使用传输代理通知它提交操作的结果的回调方法。</span><span class="sxs-lookup"><span data-stu-id="f7077-119">The Messaging Engine calls the adapter's **IBTBatchCallBack::BatchComplete** callback method using the transport proxy notifying it of the result of submission operation.</span></span>  
  
   <span data-ttu-id="f7077-120">下图显示了发送适配器中创建要求响应所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="f7077-120">The following figure shows the object interactions involved in creating a solicit-response send adapter.</span></span>  
  
   <span data-ttu-id="f7077-121">![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")</span><span class="sxs-lookup"><span data-stu-id="f7077-121">![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")</span></span>  
   <span data-ttu-id="f7077-122">要求响应发送适配器的交互图</span><span class="sxs-lookup"><span data-stu-id="f7077-122">Interaction diagram for a solicit-response send adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7077-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7077-123">See Also</span></span>  
 <span data-ttu-id="f7077-124">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f7077-124">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="f7077-125">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f7077-125">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="f7077-126">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f7077-126">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="f7077-127">[发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f7077-127">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="f7077-128">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f7077-128">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="f7077-129">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f7077-129">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="f7077-130">[异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f7077-130">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="f7077-131">支持事务性异步批处理的发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="f7077-131">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)