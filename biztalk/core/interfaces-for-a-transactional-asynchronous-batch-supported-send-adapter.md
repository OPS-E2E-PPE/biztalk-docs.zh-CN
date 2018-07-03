---
title: 事务性异步的支持批的发送适配器的接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c3ad79f09563b3e65ccfab64da5b9ec6ea3033c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982894"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="c8350-102">事务性异步的支持批的发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="c8350-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="c8350-103">在必须以事务方式传输消息时，发送适配器可以创建和控制事务。</span><span class="sxs-lookup"><span data-stu-id="c8350-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="c8350-104">为了支持事务性发送，适配器需要实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="c8350-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="c8350-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="c8350-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="c8350-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="c8350-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="c8350-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="c8350-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="c8350-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="c8350-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="c8350-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="c8350-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="c8350-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="c8350-110">**IBTTransmitterBatch**</span></span>  
  
- <span data-ttu-id="c8350-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="c8350-111">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="c8350-112">适配器创建 MSDTC 事务，并对该对象对的调用中返回的指针**BeginBatch**方法**IBTTransmitterBatch**接口。</span><span class="sxs-lookup"><span data-stu-id="c8350-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="c8350-113">消息引擎调用此方法来获得一个批，并通过此批将传出消息发送到发送适配器。</span><span class="sxs-lookup"><span data-stu-id="c8350-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="c8350-114">当适配器完成发送操作和提交或回滚事务时，它通知事务结果的消息引擎通过使用**DTCCommitConfirm**方法的**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="c8350-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
  <span data-ttu-id="c8350-115">下图显示了执行事务性发送操作时，传输代理和发送适配器之间的交互过程。</span><span class="sxs-lookup"><span data-stu-id="c8350-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
  <span data-ttu-id="c8350-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span><span class="sxs-lookup"><span data-stu-id="c8350-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span></span>  
  <span data-ttu-id="c8350-117">异步发送事务性消息的工作流</span><span class="sxs-lookup"><span data-stu-id="c8350-117">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8350-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8350-118">See Also</span></span>  
 <span data-ttu-id="c8350-119">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="c8350-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="c8350-120">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c8350-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="c8350-121">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c8350-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="c8350-122">[发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c8350-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="c8350-123">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c8350-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="c8350-124">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c8350-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="c8350-125">[异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c8350-125">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="c8350-126">要求-响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="c8350-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)