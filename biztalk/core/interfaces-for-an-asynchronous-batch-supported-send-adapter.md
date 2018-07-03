---
title: 发送适配器的异步接口的支持批的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc579995821a97dc588b2221f8a7dd2e9cd1e136
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993014"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="cae1f-102">异步的支持批的发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="cae1f-102">Interfaces for an Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="cae1f-103">可识别批的适配器可以同步或异步发送消息，并且可以执行事务性发送。</span><span class="sxs-lookup"><span data-stu-id="cae1f-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted sends.</span></span> <span data-ttu-id="cae1f-104">若要发送消息批，发送适配器必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="cae1f-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="cae1f-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="cae1f-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="cae1f-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="cae1f-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="cae1f-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="cae1f-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="cae1f-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="cae1f-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="cae1f-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="cae1f-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="cae1f-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="cae1f-110">**IBTTransmitterBatch**</span></span>  
  
  <span data-ttu-id="cae1f-111">对于异步批发送，消息引擎将从适配器获取一个批，并且将要传输的消息添加到该批。</span><span class="sxs-lookup"><span data-stu-id="cae1f-111">For the asynchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="cae1f-112">消息引擎调用时，仅发送消息**完成**批上的方法。</span><span class="sxs-lookup"><span data-stu-id="cae1f-112">The messages are only sent when the Messaging Engine calls the **Done** method on the batch.</span></span> <span data-ttu-id="cae1f-113">适配器返回`False`为打算以异步方式传输每个消息。</span><span class="sxs-lookup"><span data-stu-id="cae1f-113">The adapter returns `False` for each message that it intends to transmit asynchronously.</span></span> <span data-ttu-id="cae1f-114">然后，适配器从适配器代理获取一个批，并删除它已成功传输的那些消息。</span><span class="sxs-lookup"><span data-stu-id="cae1f-114">The adapter then gets a batch from the adapter proxy and deletes those messages that it successfully transmitted.</span></span>  
  
  <span data-ttu-id="cae1f-115">下图显示在创建异步的支持批的发送适配器时涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="cae1f-115">The following figure shows the object interactions involved in creating an asynchronous batch-supported send adapter.</span></span>  
  
  <span data-ttu-id="cae1f-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span><span class="sxs-lookup"><span data-stu-id="cae1f-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span></span>  
  <span data-ttu-id="cae1f-117">异步发送消息的工作流</span><span class="sxs-lookup"><span data-stu-id="cae1f-117">Workflow for sending a message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae1f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cae1f-118">See Also</span></span>  
 <span data-ttu-id="cae1f-119">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="cae1f-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="cae1f-120">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cae1f-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="cae1f-121">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cae1f-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="cae1f-122">[发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cae1f-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="cae1f-123">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cae1f-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="cae1f-124">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cae1f-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="cae1f-125">[事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cae1f-125">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="cae1f-126">要求-响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="cae1f-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)