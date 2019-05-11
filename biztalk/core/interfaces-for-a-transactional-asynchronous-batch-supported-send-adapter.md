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
ms.openlocfilehash: e911445cd0f92bbe863f10b8335aee0bf64630bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381859"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="c1fc7-102">事务性异步的支持批的发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="c1fc7-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="c1fc7-103">发送适配器可以创建和需要事务方式传输消息时控制事务。</span><span class="sxs-lookup"><span data-stu-id="c1fc7-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="c1fc7-104">若要支持事务性发送，适配器需要实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="c1fc7-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="c1fc7-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="c1fc7-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="c1fc7-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="c1fc7-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="c1fc7-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="c1fc7-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="c1fc7-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="c1fc7-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="c1fc7-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="c1fc7-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="c1fc7-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="c1fc7-110">**IBTTransmitterBatch**</span></span>  
  
- <span data-ttu-id="c1fc7-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="c1fc7-111">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="c1fc7-112">适配器创建 MSDTC 事务，并对该对象对的调用中返回的指针**BeginBatch**方法**IBTTransmitterBatch**接口。</span><span class="sxs-lookup"><span data-stu-id="c1fc7-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="c1fc7-113">消息引擎调用此方法以获取到发送适配器用于将传出消息批。</span><span class="sxs-lookup"><span data-stu-id="c1fc7-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="c1fc7-114">当适配器完成发送操作和提交或回滚事务时，它通知事务结果的消息引擎通过使用**DTCCommitConfirm**方法的**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="c1fc7-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
  <span data-ttu-id="c1fc7-115">执行事务性发送操作时下, 图显示了传输代理和发送适配器之间的交互。</span><span class="sxs-lookup"><span data-stu-id="c1fc7-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
  <span data-ttu-id="c1fc7-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span><span class="sxs-lookup"><span data-stu-id="c1fc7-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span></span>  
  <span data-ttu-id="c1fc7-117">以异步方式发送事务性消息的工作流</span><span class="sxs-lookup"><span data-stu-id="c1fc7-117">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fc7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1fc7-118">See Also</span></span>  
 <span data-ttu-id="c1fc7-119">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="c1fc7-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="c1fc7-120">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c1fc7-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="c1fc7-121">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c1fc7-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="c1fc7-122">[发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c1fc7-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="c1fc7-123">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c1fc7-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="c1fc7-124">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c1fc7-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="c1fc7-125">[异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c1fc7-125">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="c1fc7-126">要求-响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="c1fc7-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)