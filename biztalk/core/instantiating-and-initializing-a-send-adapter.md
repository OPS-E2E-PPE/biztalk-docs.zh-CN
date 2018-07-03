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
ms.openlocfilehash: b91bb59d974d68595e53c563311c74f590d33b3d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978918"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a><span data-ttu-id="64df6-102">实例化和初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="64df6-102">Instantiating and Initializing a Send Adapter</span></span>
<span data-ttu-id="64df6-103">默认情况下，在第一个消息传送到发送适配器之前，不会实例化发送适配器，这一过程称为“懒创建”。</span><span class="sxs-lookup"><span data-stu-id="64df6-103">By default, send adapters are not instantiated until the first message is delivered to them, a process known as "lazy creation."</span></span> <span data-ttu-id="64df6-104">默认的“懒创建”方法有助于节省系统资源。</span><span class="sxs-lookup"><span data-stu-id="64df6-104">The default lazy creation approach helps to conserve system resources.</span></span> <span data-ttu-id="64df6-105">创建发送适配器之后，在停止 BizTalk Server 服务之前该发送适配器将一直被缓存并且处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="64df6-105">After the send adapter is created, it is cached and lives until the BizTalk Server service is stopped.</span></span>  
  
 <span data-ttu-id="64df6-106">**InitTransmitterOnServiceStart**的成员**功能**枚举指示消息引擎在服务启动，而不是使用默认延迟创建，创建发送适配器如果这所需。</span><span class="sxs-lookup"><span data-stu-id="64df6-106">The **InitTransmitterOnServiceStart** member of the **Capabilities** enumeration directs the Messaging Engine to create the send adapter on service startup, rather than using the default lazy creation, if this is desired.</span></span>  
  
 <span data-ttu-id="64df6-107">在消息的批处理方面，消息的发送是一个不同于消息接收的模型。</span><span class="sxs-lookup"><span data-stu-id="64df6-107">Sending a message is a different model than receiving a message with respect to batching of messages.</span></span> <span data-ttu-id="64df6-108">对于接收，适配器的传入消息将插入到从消息引擎获得的某个批。</span><span class="sxs-lookup"><span data-stu-id="64df6-108">In the receive case the adapter has incoming messages to insert into a batch obtained from the Messaging Engine.</span></span> <span data-ttu-id="64df6-109">对于发送，消息引擎从适配器获得批并将要传输的消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="64df6-109">In the send case the Messaging Engine obtains a batch from the adapter and sends messages to the adapter to be transmitted.</span></span> <span data-ttu-id="64df6-110">这两种情况都使用传输代理来获取消息批对象。</span><span class="sxs-lookup"><span data-stu-id="64df6-110">Both use the transport proxy to obtain the message batch objects.</span></span>  
  
## <a name="how-a-send-adapter-is-initialized"></a><span data-ttu-id="64df6-111">如何初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="64df6-111">How a Send Adapter Is Initialized</span></span>  
 <span data-ttu-id="64df6-112">若要启用对传输代理的配置和绑定，适配器必须实现以下配置接口：</span><span class="sxs-lookup"><span data-stu-id="64df6-112">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
- <span data-ttu-id="64df6-113">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="64df6-113">**IBTTransport**</span></span>  
  
- <span data-ttu-id="64df6-114">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="64df6-114">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="64df6-115">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="64df6-115">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="64df6-116">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="64df6-116">**IPersistPropertyBag**</span></span>  
  
  <span data-ttu-id="64df6-117">以下步骤介绍了在初始化发送适配器时所涉及事件的顺序：</span><span class="sxs-lookup"><span data-stu-id="64df6-117">The following steps describe the sequence of events involved in initializing a send adapter:</span></span>  
  
1. <span data-ttu-id="64df6-118">当消息引擎初始化发送适配器时，它首先会执行**QueryInterface**有关**IPersistPropertyBag**，这是一个可选接口。</span><span class="sxs-lookup"><span data-stu-id="64df6-118">When the Messaging Engine initializes a send adapter, it first performs a **QueryInterface** for **IPersistPropertyBag**, which is an optional interface.</span></span> <span data-ttu-id="64df6-119">如果适配器实现了接口，处理程序配置传递给适配器**负载**方法调用。</span><span class="sxs-lookup"><span data-stu-id="64df6-119">If the adapter implements the interface, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="64df6-120">适配器将使用此信息来确保它得到正确地配置。</span><span class="sxs-lookup"><span data-stu-id="64df6-120">The adapter uses this information to ensure it is configured correctly.</span></span>  
  
2. <span data-ttu-id="64df6-121">消息引擎执行**QueryInterface**有关**IBTTransportControl**，这是必需的接口。</span><span class="sxs-lookup"><span data-stu-id="64df6-121">The Messaging Engine performs a **QueryInterface** for **IBTTransportControl**, which is a mandatory interface.</span></span>  
  
3. <span data-ttu-id="64df6-122">引擎将调用**IBTTransportControl.Initialize**、 传入适配器的传输代理。</span><span class="sxs-lookup"><span data-stu-id="64df6-122">The engine calls **IBTTransportControl.Initialize**, passing in the transport proxy for the adapter.</span></span>  
  
4. <span data-ttu-id="64df6-123">消息引擎执行**QueryInterface**有关**IBTTransmitter**。</span><span class="sxs-lookup"><span data-stu-id="64df6-123">The Messaging Engine performs a **QueryInterface** for **IBTTransmitter**.</span></span>  
  
    <span data-ttu-id="64df6-124">如果消息引擎找到该接口，则适配器将被视为不支持批的发送器。</span><span class="sxs-lookup"><span data-stu-id="64df6-124">If the Messaging Engine discovers this interface, the adapter is treated as a batch-unaware transmitter.</span></span>  
  
    <span data-ttu-id="64df6-125">如果消息引擎不会发现此接口，消息引擎将执行**QueryInterface**有关**IBTBatchTransmitter**，发现其中表示适配器是可识别批发送器。</span><span class="sxs-lookup"><span data-stu-id="64df6-125">If the Messaging Engine does not discover this interface, the Messaging Engine performs a **QueryInterface** for **IBTBatchTransmitter**, discovery of which indicates that the adapter is a batch-aware transmitter.</span></span>  
  
    <span data-ttu-id="64df6-126">如果消息引擎找不到这两个接口中的任何一个，则会出现错误，从而导致初始化失败。</span><span class="sxs-lookup"><span data-stu-id="64df6-126">If the Messaging Engine discovers neither of these interfaces, an error condition results, causing the initialization to fail.</span></span> <span data-ttu-id="64df6-127">如果未找到任何必需接口，则初始化将失败。</span><span class="sxs-lookup"><span data-stu-id="64df6-127">The initialization fails if any mandatory interfaces are not discovered.</span></span>  
  
   <span data-ttu-id="64df6-128">下图说明了 API 调用的顺序；蓝色的接口由适配器实现。</span><span class="sxs-lookup"><span data-stu-id="64df6-128">The following diagram illustrates this sequence of API calls; the interfaces in blue are implemented by the adapter.</span></span>  
  
   <span data-ttu-id="64df6-129">![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")</span><span class="sxs-lookup"><span data-stu-id="64df6-129">![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")</span></span>  
  
   <span data-ttu-id="64df6-130">适配器在初始化和配置完毕后就可发送消息。</span><span class="sxs-lookup"><span data-stu-id="64df6-130">The adapter can send messages as soon as it is initialized and configured.</span></span>  
  
   <span data-ttu-id="64df6-131">下图显示了初始化发送适配器时所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="64df6-131">The following figure shows the object interactions involved in initializing a send adapter.</span></span>  
  
   <span data-ttu-id="64df6-132">![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")</span><span class="sxs-lookup"><span data-stu-id="64df6-132">![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")</span></span>  
   <span data-ttu-id="64df6-133">初始化发送适配器的工作流</span><span class="sxs-lookup"><span data-stu-id="64df6-133">Workflow for initializing a send adapter</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64df6-134">适配器不应阻止消息引擎在调用如**IBTTransportControl.Initialize**并**ipersistpropertybag.load 这样**。</span><span class="sxs-lookup"><span data-stu-id="64df6-134">Adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize** and **IPersistPropertyBag.Load**.</span></span> <span data-ttu-id="64df6-135">在这些调用中执行过多的处理会影响服务启动时间。</span><span class="sxs-lookup"><span data-stu-id="64df6-135">Performing excessive processing in these calls affects service startup time.</span></span>