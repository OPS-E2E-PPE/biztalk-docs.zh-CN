---
title: 实例化和初始化发送适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f10e6507-3351-4173-95f5-48546ca5f5c4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3808af04a8b2bcf6f866629f254212d5b10b8d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382072"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a><span data-ttu-id="63906-102">实例化和初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="63906-102">Instantiating and Initializing a Send Adapter</span></span>
<span data-ttu-id="63906-103">默认情况下，发送适配器不会实例化，直到第一条消息传递到它们，该过程称为"懒创建。</span><span class="sxs-lookup"><span data-stu-id="63906-103">By default, send adapters are not instantiated until the first message is delivered to them, a process known as "lazy creation."</span></span> <span data-ttu-id="63906-104">默认的懒创建方法有助于节省系统资源。</span><span class="sxs-lookup"><span data-stu-id="63906-104">The default lazy creation approach helps to conserve system resources.</span></span> <span data-ttu-id="63906-105">创建发送适配器后，它将被缓存，位于直到 BizTalk Server 服务已停止。</span><span class="sxs-lookup"><span data-stu-id="63906-105">After the send adapter is created, it is cached and lives until the BizTalk Server service is stopped.</span></span>  
  
 <span data-ttu-id="63906-106">**InitTransmitterOnServiceStart**的成员**功能**枚举指示消息引擎在服务启动，而不是使用默认延迟创建，创建发送适配器如果这所需。</span><span class="sxs-lookup"><span data-stu-id="63906-106">The **InitTransmitterOnServiceStart** member of the **Capabilities** enumeration directs the Messaging Engine to create the send adapter on service startup, rather than using the default lazy creation, if this is desired.</span></span>  
  
 <span data-ttu-id="63906-107">发送一条消息是与接收消息的消息批处理方面不同的模型。</span><span class="sxs-lookup"><span data-stu-id="63906-107">Sending a message is a different model than receiving a message with respect to batching of messages.</span></span> <span data-ttu-id="63906-108">对于接收适配器的传入消息将从消息引擎获取一批中插入。</span><span class="sxs-lookup"><span data-stu-id="63906-108">In the receive case the adapter has incoming messages to insert into a batch obtained from the Messaging Engine.</span></span> <span data-ttu-id="63906-109">在发送的情况下，消息引擎从适配器获得批并将消息发送到传输的适配器。</span><span class="sxs-lookup"><span data-stu-id="63906-109">In the send case the Messaging Engine obtains a batch from the adapter and sends messages to the adapter to be transmitted.</span></span> <span data-ttu-id="63906-110">同时使用传输代理来获取消息批对象。</span><span class="sxs-lookup"><span data-stu-id="63906-110">Both use the transport proxy to obtain the message batch objects.</span></span>  
  
## <a name="how-a-send-adapter-is-initialized"></a><span data-ttu-id="63906-111">如何初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="63906-111">How a Send Adapter Is Initialized</span></span>  
 <span data-ttu-id="63906-112">若要启用配置和绑定到传输代理，适配器必须实现以下配置接口：</span><span class="sxs-lookup"><span data-stu-id="63906-112">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
- <span data-ttu-id="63906-113">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="63906-113">**IBTTransport**</span></span>  
  
- <span data-ttu-id="63906-114">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="63906-114">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="63906-115">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="63906-115">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="63906-116">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="63906-116">**IPersistPropertyBag**</span></span>  
  
  <span data-ttu-id="63906-117">以下步骤介绍在初始化发送适配器所涉及的事件序列：</span><span class="sxs-lookup"><span data-stu-id="63906-117">The following steps describe the sequence of events involved in initializing a send adapter:</span></span>  
  
1. <span data-ttu-id="63906-118">当消息引擎初始化发送适配器时，它首先会执行**QueryInterface**有关**IPersistPropertyBag**，这是一个可选接口。</span><span class="sxs-lookup"><span data-stu-id="63906-118">When the Messaging Engine initializes a send adapter, it first performs a **QueryInterface** for **IPersistPropertyBag**, which is an optional interface.</span></span> <span data-ttu-id="63906-119">如果适配器实现了接口，处理程序配置传递给适配器**负载**方法调用。</span><span class="sxs-lookup"><span data-stu-id="63906-119">If the adapter implements the interface, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="63906-120">适配器使用此信息以确保配置正确。</span><span class="sxs-lookup"><span data-stu-id="63906-120">The adapter uses this information to ensure it is configured correctly.</span></span>  
  
2. <span data-ttu-id="63906-121">消息引擎执行**QueryInterface**有关**IBTTransportControl**，这是必需的接口。</span><span class="sxs-lookup"><span data-stu-id="63906-121">The Messaging Engine performs a **QueryInterface** for **IBTTransportControl**, which is a mandatory interface.</span></span>  
  
3. <span data-ttu-id="63906-122">引擎将调用**IBTTransportControl.Initialize**、 传入适配器的传输代理。</span><span class="sxs-lookup"><span data-stu-id="63906-122">The engine calls **IBTTransportControl.Initialize**, passing in the transport proxy for the adapter.</span></span>  
  
4. <span data-ttu-id="63906-123">消息引擎执行**QueryInterface**有关**IBTTransmitter**。</span><span class="sxs-lookup"><span data-stu-id="63906-123">The Messaging Engine performs a **QueryInterface** for **IBTTransmitter**.</span></span>  
  
    <span data-ttu-id="63906-124">如果消息引擎找到该接口，适配器将被视为不支持批的发送器。</span><span class="sxs-lookup"><span data-stu-id="63906-124">If the Messaging Engine discovers this interface, the adapter is treated as a batch-unaware transmitter.</span></span>  
  
    <span data-ttu-id="63906-125">如果消息引擎不会发现此接口，消息引擎将执行**QueryInterface**有关**IBTBatchTransmitter**，发现其中表示适配器是可识别批发送器。</span><span class="sxs-lookup"><span data-stu-id="63906-125">If the Messaging Engine does not discover this interface, the Messaging Engine performs a **QueryInterface** for **IBTBatchTransmitter**, discovery of which indicates that the adapter is a batch-aware transmitter.</span></span>  
  
    <span data-ttu-id="63906-126">如果消息引擎发现任一这些接口，产生的错误条件，从而导致初始化失败。</span><span class="sxs-lookup"><span data-stu-id="63906-126">If the Messaging Engine discovers neither of these interfaces, an error condition results, causing the initialization to fail.</span></span> <span data-ttu-id="63906-127">初始化失败，则如果未发现任何必需接口。</span><span class="sxs-lookup"><span data-stu-id="63906-127">The initialization fails if any mandatory interfaces are not discovered.</span></span>  
  
   <span data-ttu-id="63906-128">下图说明了这一序列的 API 调用异步方法。蓝色的接口由适配器实现。</span><span class="sxs-lookup"><span data-stu-id="63906-128">The following diagram illustrates this sequence of API calls; the interfaces in blue are implemented by the adapter.</span></span>  
  
   <span data-ttu-id="63906-129">![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")</span><span class="sxs-lookup"><span data-stu-id="63906-129">![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")</span></span>  
  
   <span data-ttu-id="63906-130">一旦初始化和配置，适配器可以发送消息。</span><span class="sxs-lookup"><span data-stu-id="63906-130">The adapter can send messages as soon as it is initialized and configured.</span></span>  
  
   <span data-ttu-id="63906-131">下图显示了在初始化发送适配器所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="63906-131">The following figure shows the object interactions involved in initializing a send adapter.</span></span>  
  
   <span data-ttu-id="63906-132">![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")</span><span class="sxs-lookup"><span data-stu-id="63906-132">![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")</span></span>  
   <span data-ttu-id="63906-133">用于初始化发送适配器的工作流</span><span class="sxs-lookup"><span data-stu-id="63906-133">Workflow for initializing a send adapter</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63906-134">适配器不应阻止消息引擎在调用如**IBTTransportControl.Initialize**并**ipersistpropertybag.load 这样**。</span><span class="sxs-lookup"><span data-stu-id="63906-134">Adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize** and **IPersistPropertyBag.Load**.</span></span> <span data-ttu-id="63906-135">执行过多的处理中这些调用会影响服务启动时间。</span><span class="sxs-lookup"><span data-stu-id="63906-135">Performing excessive processing in these calls affects service startup time.</span></span>