---
title: "为事务异步批处理支持发送适配器接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 948000883c092c8e247b1d4f41fb2bc7e2280e40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="6ff6d-102">事务异步批处理支持发送适配器的的接口</span><span class="sxs-lookup"><span data-stu-id="6ff6d-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="6ff6d-103">在必须以事务方式传输消息时，发送适配器可以创建和控制事务。</span><span class="sxs-lookup"><span data-stu-id="6ff6d-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="6ff6d-104">为了支持事务性发送，适配器需要实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="6ff6d-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="6ff6d-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="6ff6d-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="6ff6d-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="6ff6d-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="6ff6d-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="6ff6d-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="6ff6d-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="6ff6d-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="6ff6d-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="6ff6d-109">**IBTBatchTransmitter**</span></span>  
  
-   <span data-ttu-id="6ff6d-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="6ff6d-110">**IBTTransmitterBatch**</span></span>  
  
-   <span data-ttu-id="6ff6d-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="6ff6d-111">**IBTBatchCallBack**</span></span>  
  
 <span data-ttu-id="6ff6d-112">适配器创建的 MSDTC 事务并对该对象的调用中返回的指针**BeginBatch**方法**IBTTransmitterBatch**接口。</span><span class="sxs-lookup"><span data-stu-id="6ff6d-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="6ff6d-113">消息引擎调用此方法来获得一个批，并通过此批将传出消息发送到发送适配器。</span><span class="sxs-lookup"><span data-stu-id="6ff6d-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="6ff6d-114">当适配器完成发送操作和提交或回滚事务时，它将通知消息的事务结果引擎使用**DTCCommitConfirm**方法**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="6ff6d-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
 <span data-ttu-id="6ff6d-115">下图显示了执行事务性发送操作时，传输代理和发送适配器之间的交互过程。</span><span class="sxs-lookup"><span data-stu-id="6ff6d-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
<span data-ttu-id="6ff6d-116">异步发送事务性消息的工作流</span><span class="sxs-lookup"><span data-stu-id="6ff6d-116">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff6d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ff6d-117">See Also</span></span>  
 <span data-ttu-id="6ff6d-118">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6ff6d-118">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="6ff6d-119">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6ff6d-119">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="6ff6d-120">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6ff6d-120">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="6ff6d-121">[发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6ff6d-121">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="6ff6d-122">[异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6ff6d-122">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="6ff6d-123">[同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6ff6d-123">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="6ff6d-124">[异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6ff6d-124">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="6ff6d-125">适配器发送的请求作出响应的接口</span><span class="sxs-lookup"><span data-stu-id="6ff6d-125">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)