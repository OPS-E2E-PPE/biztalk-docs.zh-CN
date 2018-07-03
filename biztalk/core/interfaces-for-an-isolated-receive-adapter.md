---
title: 接收适配器的接口独立 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c6b195e-76bf-4c3e-a324-5513bc24fed1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 129a0d16100ed7f38f49d0cfa5cc329446c3e72e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997182"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a><span data-ttu-id="04458-102">接口独立接收适配器</span><span class="sxs-lookup"><span data-stu-id="04458-102">Interfaces for an Isolated Receive Adapter</span></span>
<span data-ttu-id="04458-103">独立接收适配器不是托管在进程空间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程。</span><span class="sxs-lookup"><span data-stu-id="04458-103">Isolated receive adapters are hosted in a process space other than the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process.</span></span> <span data-ttu-id="04458-104">独立接收适配器若要与消息引擎进行交互，需要在启动时注册自身，以便引擎可以配置和控制它。</span><span class="sxs-lookup"><span data-stu-id="04458-104">To interact with the Messaging Engine, an isolated receive adapter registers itself on startup so that the engine can configure and control it.</span></span> <span data-ttu-id="04458-105">适配器创建传输代理，将查询的接口**IBTTransportProxy**，并调用**IBTTransportProxy.RegisterIsolatedReceiver**注册其**IBTTransportConfig**与消息引擎回调接口。</span><span class="sxs-lookup"><span data-stu-id="04458-105">The adapter creates the transport proxy, queries for the interface **IBTTransportProxy**, and calls **IBTTransportProxy.RegisterIsolatedReceiver** to register its **IBTTransportConfig** callback interface with the Messaging Engine.</span></span> <span data-ttu-id="04458-106">适配器将提交到其第一条消息之前，会发生此同步调用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04458-106">This synchronous call occurs before the adapter submits its first message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="04458-107">这使消息引擎可以通过回调进入适配器，通知适配器哪些终结点是活动的，因而应该侦听上面的传入消息。</span><span class="sxs-lookup"><span data-stu-id="04458-107">This allows the Messaging Engine to call back into the adapter and tell it which of its endpoints are active and should be listened on for incoming messages.</span></span> <span data-ttu-id="04458-108">独立适配器必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="04458-108">Isolated adapters must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="04458-109">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="04458-109">**IBTTransport**</span></span>  
  
- <span data-ttu-id="04458-110">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="04458-110">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="04458-111">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="04458-111">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="04458-112">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="04458-112">**IPersistPropertyBag**</span></span>  
  
  <span data-ttu-id="04458-113">注册适配器需要适配器传递一个已配置并已启用的接收位置。</span><span class="sxs-lookup"><span data-stu-id="04458-113">Registering the adapter requires the adapter to pass a configured and enabled receive location.</span></span> <span data-ttu-id="04458-114">适配器的主机进程必须是 BizTalk Isolated Host Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="04458-114">The adapter's host process must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="04458-115">此外，还需查询该适配器以确保它具有正确的类 ID，并且运行在之前为该主机实例配置的计算机上。</span><span class="sxs-lookup"><span data-stu-id="04458-115">In addition, the adapter is queried to ensure that it has the correct class ID and is running on the computer that was configured for that host instance.</span></span>  
  
  <span data-ttu-id="04458-116">适配器已成功注册了传输代理后，消息引擎将传递的配置信息和其他接收位置回适配器通过调用**负载**方法的**IPersistPropertyBag**接口和**AddReceiveEndpoint**方法**IBTTransportConfig**分别接口。</span><span class="sxs-lookup"><span data-stu-id="04458-116">After the adapter has successfully registered with the transport proxy, the Messaging Engine passes the configuration information and the other receive locations back to the adapter by calling the **Load** method of the **IPersistPropertyBag** interface and the **AddReceiveEndpoint** method of the **IBTTransportConfig** interface respectively.</span></span>  
  
  <span data-ttu-id="04458-117">当独立接收适配器结束消息的处理并即将终止，它必须调用**TerminateIsolatedReceiver**方法**IBTTransportProxy**接口。</span><span class="sxs-lookup"><span data-stu-id="04458-117">When an isolated receive adapter ends the processing of messages and is going to be terminated, it must call the **TerminateIsolatedReceiver** method of the **IBTTransportProxy** interface.</span></span>  
  
  <span data-ttu-id="04458-118">下图显示创建独立接收适配器时涉及到的对象交互。</span><span class="sxs-lookup"><span data-stu-id="04458-118">The following illustration shows the object interactions involved in creating an isolated receive adapter.</span></span>  
  
  <span data-ttu-id="04458-119">![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")</span><span class="sxs-lookup"><span data-stu-id="04458-119">![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")</span></span>  
  <span data-ttu-id="04458-120">初始化独立接收适配器的工作流。</span><span class="sxs-lookup"><span data-stu-id="04458-120">Workflow for initializing an isolated receive adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04458-121">我们建议适配器保持跟踪当前执行的请求的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04458-121">We recommend that the adapter keep track of currently executing requests to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="04458-122">适配器应该一直阻止**Terminate**方法，直到工作计数归零。</span><span class="sxs-lookup"><span data-stu-id="04458-122">The adapter should block the **Terminate** method until the work count has reached zero.</span></span> <span data-ttu-id="04458-123">这项工作在接收端，包括尚未发布到所有未完成请求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04458-123">On the receive side, this work includes any outstanding requests that have not been published to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="04458-124">请注意响应消息通常不传送给接收适配器后**Terminate**调用。</span><span class="sxs-lookup"><span data-stu-id="04458-124">Note that response messages are typically not delivered to a receive adapter after **Terminate** is called.</span></span> <span data-ttu-id="04458-125">一般情况下，适配器调用后**Terminate**方法中，消息引擎不接受请求发布新消息，但要求-响应对的响应消息除外。</span><span class="sxs-lookup"><span data-stu-id="04458-125">In general, after the adapter calls the **Terminate** method, the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="04458-126">一个进程可以作为多个独立适配器实例的宿主，但是只能作为一个适配器的宿主。</span><span class="sxs-lookup"><span data-stu-id="04458-126">One process may host several instances of isolated adapters, while only one process may host one adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04458-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="04458-127">See Also</span></span>  
 <span data-ttu-id="04458-128">[适配器变量](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="04458-128">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="04458-129">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="04458-129">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="04458-130">[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="04458-130">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="04458-131">[接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="04458-131">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="04458-132">[接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="04458-132">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="04458-133">[接收适配器的接口的事务性批处理支持](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="04458-133">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="04458-134">同步请求-响应接收适配器的接口</span><span class="sxs-lookup"><span data-stu-id="04458-134">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)