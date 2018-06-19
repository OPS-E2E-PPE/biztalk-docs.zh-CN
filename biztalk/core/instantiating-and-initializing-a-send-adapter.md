---
title: 实例化和初始化发送适配器 |Microsoft 文档
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
ms.openlocfilehash: 07ed590b73d31a03a4b3316a4d84edfc1e39eb0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257661"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a><span data-ttu-id="d6037-102">实例化和初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="d6037-102">Instantiating and Initializing a Send Adapter</span></span>
<span data-ttu-id="d6037-103">默认情况下，在第一个消息传送到发送适配器之前，不会实例化发送适配器，这一过程称为“懒创建”。</span><span class="sxs-lookup"><span data-stu-id="d6037-103">By default, send adapters are not instantiated until the first message is delivered to them, a process known as "lazy creation."</span></span> <span data-ttu-id="d6037-104">默认的“懒创建”方法有助于节省系统资源。</span><span class="sxs-lookup"><span data-stu-id="d6037-104">The default lazy creation approach helps to conserve system resources.</span></span> <span data-ttu-id="d6037-105">创建发送适配器之后，在停止 BizTalk Server 服务之前该发送适配器将一直被缓存并且处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="d6037-105">After the send adapter is created, it is cached and lives until the BizTalk Server service is stopped.</span></span>  
  
 <span data-ttu-id="d6037-106">**InitTransmitterOnServiceStart**的成员**功能**枚举指示消息传递引擎服务启动后，而不使用默认延迟创建，创建发送适配器如果这所需。</span><span class="sxs-lookup"><span data-stu-id="d6037-106">The **InitTransmitterOnServiceStart** member of the **Capabilities** enumeration directs the Messaging Engine to create the send adapter on service startup, rather than using the default lazy creation, if this is desired.</span></span>  
  
 <span data-ttu-id="d6037-107">在消息的批处理方面，消息的发送是一个不同于消息接收的模型。</span><span class="sxs-lookup"><span data-stu-id="d6037-107">Sending a message is a different model than receiving a message with respect to batching of messages.</span></span> <span data-ttu-id="d6037-108">对于接收，适配器的传入消息将插入到从消息引擎获得的某个批。</span><span class="sxs-lookup"><span data-stu-id="d6037-108">In the receive case the adapter has incoming messages to insert into a batch obtained from the Messaging Engine.</span></span> <span data-ttu-id="d6037-109">对于发送，消息引擎从适配器获得批并将要传输的消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="d6037-109">In the send case the Messaging Engine obtains a batch from the adapter and sends messages to the adapter to be transmitted.</span></span> <span data-ttu-id="d6037-110">这两种情况都使用传输代理来获取消息批对象。</span><span class="sxs-lookup"><span data-stu-id="d6037-110">Both use the transport proxy to obtain the message batch objects.</span></span>  
  
## <a name="how-a-send-adapter-is-initialized"></a><span data-ttu-id="d6037-111">如何初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="d6037-111">How a Send Adapter Is Initialized</span></span>  
 <span data-ttu-id="d6037-112">若要启用对传输代理的配置和绑定，适配器必须实现以下配置接口：</span><span class="sxs-lookup"><span data-stu-id="d6037-112">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
-   <span data-ttu-id="d6037-113">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="d6037-113">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="d6037-114">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="d6037-114">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="d6037-115">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="d6037-115">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="d6037-116">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="d6037-116">**IPersistPropertyBag**</span></span>  
  
 <span data-ttu-id="d6037-117">以下步骤介绍了在初始化发送适配器时所涉及事件的顺序：</span><span class="sxs-lookup"><span data-stu-id="d6037-117">The following steps describe the sequence of events involved in initializing a send adapter:</span></span>  
  
1.  <span data-ttu-id="d6037-118">当消息引擎初始化发送适配器时，它首先会执行**QueryInterface**为**IPersistPropertyBag**，这是可选的接口。</span><span class="sxs-lookup"><span data-stu-id="d6037-118">When the Messaging Engine initializes a send adapter, it first performs a **QueryInterface** for **IPersistPropertyBag**, which is an optional interface.</span></span> <span data-ttu-id="d6037-119">如果适配器实现接口时，将处理程序配置传递给的适配器**负载**方法调用。</span><span class="sxs-lookup"><span data-stu-id="d6037-119">If the adapter implements the interface, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="d6037-120">适配器将使用此信息来确保它得到正确地配置。</span><span class="sxs-lookup"><span data-stu-id="d6037-120">The adapter uses this information to ensure it is configured correctly.</span></span>  
  
2.  <span data-ttu-id="d6037-121">消息传送引擎都会执行**QueryInterface**为**IBTTransportControl**，这是必需的接口。</span><span class="sxs-lookup"><span data-stu-id="d6037-121">The Messaging Engine performs a **QueryInterface** for **IBTTransportControl**, which is a mandatory interface.</span></span>  
  
3.  <span data-ttu-id="d6037-122">引擎调用**IBTTransportControl.Initialize**，并用于适配器的传输代理传入。</span><span class="sxs-lookup"><span data-stu-id="d6037-122">The engine calls **IBTTransportControl.Initialize**, passing in the transport proxy for the adapter.</span></span>  
  
4.  <span data-ttu-id="d6037-123">消息传送引擎都会执行**QueryInterface**为**IBTTransmitter**。</span><span class="sxs-lookup"><span data-stu-id="d6037-123">The Messaging Engine performs a **QueryInterface** for **IBTTransmitter**.</span></span>  
  
     <span data-ttu-id="d6037-124">如果消息引擎找到该接口，则适配器将被视为不支持批的发送器。</span><span class="sxs-lookup"><span data-stu-id="d6037-124">If the Messaging Engine discovers this interface, the adapter is treated as a batch-unaware transmitter.</span></span>  
  
     <span data-ttu-id="d6037-125">如果消息引擎不会发现此接口，则消息传递引擎执行**QueryInterface**为**IBTBatchTransmitter**，发现其中表示适配器是批处理感知发送器。</span><span class="sxs-lookup"><span data-stu-id="d6037-125">If the Messaging Engine does not discover this interface, the Messaging Engine performs a **QueryInterface** for **IBTBatchTransmitter**, discovery of which indicates that the adapter is a batch-aware transmitter.</span></span>  
  
     <span data-ttu-id="d6037-126">如果消息引擎找不到这两个接口中的任何一个，则会出现错误，从而导致初始化失败。</span><span class="sxs-lookup"><span data-stu-id="d6037-126">If the Messaging Engine discovers neither of these interfaces, an error condition results, causing the initialization to fail.</span></span> <span data-ttu-id="d6037-127">如果未找到任何必需接口，则初始化将失败。</span><span class="sxs-lookup"><span data-stu-id="d6037-127">The initialization fails if any mandatory interfaces are not discovered.</span></span>  
  
 <span data-ttu-id="d6037-128">下图说明了 API 调用的顺序；蓝色的接口由适配器实现。</span><span class="sxs-lookup"><span data-stu-id="d6037-128">The following diagram illustrates this sequence of API calls; the interfaces in blue are implemented by the adapter.</span></span>  
  
 ![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")  
  
 <span data-ttu-id="d6037-129">适配器在初始化和配置完毕后就可发送消息。</span><span class="sxs-lookup"><span data-stu-id="d6037-129">The adapter can send messages as soon as it is initialized and configured.</span></span>  
  
 <span data-ttu-id="d6037-130">下图显示了初始化发送适配器时所涉及的对象交互。</span><span class="sxs-lookup"><span data-stu-id="d6037-130">The following figure shows the object interactions involved in initializing a send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")  
<span data-ttu-id="d6037-131">初始化发送适配器的工作流</span><span class="sxs-lookup"><span data-stu-id="d6037-131">Workflow for initializing a send adapter</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6037-132">适配器不应阻止调用中的消息传递引擎如**IBTTransportControl.Initialize**和**IPersistPropertyBag.Load**。</span><span class="sxs-lookup"><span data-stu-id="d6037-132">Adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize** and **IPersistPropertyBag.Load**.</span></span> <span data-ttu-id="d6037-133">在这些调用中执行过多的处理会影响服务启动时间。</span><span class="sxs-lookup"><span data-stu-id="d6037-133">Performing excessive processing in these calls affects service startup time.</span></span>