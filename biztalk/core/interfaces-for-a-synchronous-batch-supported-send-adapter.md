---
title: "批处理支持异步接口发送适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ab61fd6624468e0464cfe0c648fcc868bd20005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a><span data-ttu-id="0a10e-102">同步的支持批的发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="0a10e-102">Interfaces for a Synchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="0a10e-103">可识别批的适配器可以同步或异步发送消息，并且可以执行事务性发送操作。</span><span class="sxs-lookup"><span data-stu-id="0a10e-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted send operations.</span></span> <span data-ttu-id="0a10e-104">若要发送消息批，发送适配器必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="0a10e-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="0a10e-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="0a10e-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="0a10e-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="0a10e-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="0a10e-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="0a10e-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="0a10e-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="0a10e-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="0a10e-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="0a10e-109">**IBTBatchTransmitter**</span></span>  
  
-   <span data-ttu-id="0a10e-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="0a10e-110">**IBTTransmitterBatch**</span></span>  
  
 <span data-ttu-id="0a10e-111">对于同步批发送，消息引擎将从适配器获取一个批，并且将要传输的消息添加到该批。</span><span class="sxs-lookup"><span data-stu-id="0a10e-111">For the synchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="0a10e-112">The Messaging Engine 将每条消息添加到批处理，并仅在它调用时才发送消息**完成**批次的方法。</span><span class="sxs-lookup"><span data-stu-id="0a10e-112">The Messaging Engine adds each message to the batch and sends the messages only when it calls the **Done** method on the batch.</span></span> <span data-ttu-id="0a10e-113">适配器返回`True`为**bDeleteMessage**它想要以同步方式传输每条消息。</span><span class="sxs-lookup"><span data-stu-id="0a10e-113">The adapter returns `True` for **bDeleteMessage** for each message that it intends to transmit synchronously.</span></span> <span data-ttu-id="0a10e-114">适配器应将消息数据，而不是消息指针，保存在其**TransmitMessage**实现。</span><span class="sxs-lookup"><span data-stu-id="0a10e-114">The adapter should save message data, as opposed to a message pointer, in its **TransmitMessage** implementation.</span></span> <span data-ttu-id="0a10e-115">这是因为消息指针将不再有效之后`True`返回，并且不应使用或缓存供以后使用。</span><span class="sxs-lookup"><span data-stu-id="0a10e-115">This is because the message pointer is no longer valid after `True` is returned, and should not be used or cached for later use.</span></span>  
  
 <span data-ttu-id="0a10e-116">下图显示在创建同步的支持批的发送适配器时涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="0a10e-116">The following figure shows the object interactions involved in creating a synchronous batch-supported send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
<span data-ttu-id="0a10e-117">同步提交消息的工作流</span><span class="sxs-lookup"><span data-stu-id="0a10e-117">Workflow for submitting a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a10e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a10e-118">See Also</span></span>  
 <span data-ttu-id="0a10e-119">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="0a10e-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="0a10e-120">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a10e-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="0a10e-121">[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a10e-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="0a10e-122">[发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a10e-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="0a10e-123">[异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a10e-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="0a10e-124">[异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a10e-124">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="0a10e-125">[事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a10e-125">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="0a10e-126">适配器发送的请求作出响应的接口</span><span class="sxs-lookup"><span data-stu-id="0a10e-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)