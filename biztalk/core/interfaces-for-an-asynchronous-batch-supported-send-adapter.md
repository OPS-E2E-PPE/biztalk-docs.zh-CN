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
ms.openlocfilehash: 07890cb81bb76a665f98d7f489b4775c01f436b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381792"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="1fa5c-102">异步的支持批的发送适配器的的接口</span><span class="sxs-lookup"><span data-stu-id="1fa5c-102">Interfaces for an Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="1fa5c-103">可识别批的适配器以同步方式还是以异步方式，可以发送消息，并且可以执行事务性的发送。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted sends.</span></span> <span data-ttu-id="1fa5c-104">若要发送消息批，发送适配器必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="1fa5c-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="1fa5c-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="1fa5c-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="1fa5c-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="1fa5c-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="1fa5c-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="1fa5c-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="1fa5c-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="1fa5c-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="1fa5c-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="1fa5c-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="1fa5c-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="1fa5c-110">**IBTTransmitterBatch**</span></span>  
  
  <span data-ttu-id="1fa5c-111">对于异步批发送，消息引擎从适配器获取批，并将添加到该批传输的消息。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-111">For the asynchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="1fa5c-112">消息引擎调用时，仅发送消息**完成**批上的方法。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-112">The messages are only sent when the Messaging Engine calls the **Done** method on the batch.</span></span> <span data-ttu-id="1fa5c-113">适配器返回`False`为打算以异步方式传输每个消息。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-113">The adapter returns `False` for each message that it intends to transmit asynchronously.</span></span> <span data-ttu-id="1fa5c-114">然后，适配器从适配器代理获取一个批，并删除它已成功传输这些消息。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-114">The adapter then gets a batch from the adapter proxy and deletes those messages that it successfully transmitted.</span></span>  
  
  <span data-ttu-id="1fa5c-115">下图显示了发送适配器中创建异步的支持批的涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-115">The following figure shows the object interactions involved in creating an asynchronous batch-supported send adapter.</span></span>  
  
  <span data-ttu-id="1fa5c-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span><span class="sxs-lookup"><span data-stu-id="1fa5c-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span></span>  
  <span data-ttu-id="1fa5c-117">以异步方式发送一条消息的工作流</span><span class="sxs-lookup"><span data-stu-id="1fa5c-117">Workflow for sending a message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa5c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fa5c-118">See Also</span></span>  
 <span data-ttu-id="1fa5c-119">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="1fa5c-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="1fa5c-120">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1fa5c-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="1fa5c-121">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1fa5c-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="1fa5c-122">[发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1fa5c-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="1fa5c-123">[发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1fa5c-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="1fa5c-124">[同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1fa5c-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="1fa5c-125">[事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1fa5c-125">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="1fa5c-126">要求-响应发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="1fa5c-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)