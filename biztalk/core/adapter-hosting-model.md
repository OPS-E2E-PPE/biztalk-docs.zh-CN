---
title: 适配器宿主模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf9a8e6b-8c8d-47ec-b2a3-aed58206121d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f6603c07bc74cb904ad3eb88f50a3c7d2c60d09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361430"
---
# <a name="adapter-hosting-model"></a><span data-ttu-id="c2385-102">适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="c2385-102">Adapter Hosting Model</span></span>
<span data-ttu-id="c2385-103">一般情况下 BizTalk 适配器的宿主 BizTalk 服务 Btsntsvc.exe。</span><span class="sxs-lookup"><span data-stu-id="c2385-103">In general BizTalk adapters are hosted in the BizTalk service, Btsntsvc.exe.</span></span> <span data-ttu-id="c2385-104">这意味着，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理适配器的生存期。</span><span class="sxs-lookup"><span data-stu-id="c2385-104">This means that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] manages the lifetime of the adapter.</span></span> <span data-ttu-id="c2385-105">还有一些情况下，如下所述，其他进程管理适配器。</span><span class="sxs-lookup"><span data-stu-id="c2385-105">There are also situations, described below, where other processes manage the adapter.</span></span>  
  
## <a name="in-process-adapters"></a><span data-ttu-id="c2385-106">进程内适配器</span><span class="sxs-lookup"><span data-stu-id="c2385-106">In-Process Adapters</span></span>  
 <span data-ttu-id="c2385-107">由适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]称为进程内适配器。</span><span class="sxs-lookup"><span data-stu-id="c2385-107">Adapters that are managed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are called in-process adapters.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c2385-108">执行以下操作适用于这些适配器：</span><span class="sxs-lookup"><span data-stu-id="c2385-108">does the following for these adapters:</span></span>  
  
- <span data-ttu-id="c2385-109">实例化适配器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已启动</span><span class="sxs-lookup"><span data-stu-id="c2385-109">Instantiate the adapter when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is started</span></span>  
  
- <span data-ttu-id="c2385-110">在初始化期间传递到适配器的适配器的传输代理</span><span class="sxs-lookup"><span data-stu-id="c2385-110">Passes the adapter's transport proxy to the adapter during initialization</span></span>  
  
- <span data-ttu-id="c2385-111">适配器的请求提供服务</span><span class="sxs-lookup"><span data-stu-id="c2385-111">Services the adapter's requests</span></span>  
  
- <span data-ttu-id="c2385-112">终止在关闭的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务</span><span class="sxs-lookup"><span data-stu-id="c2385-112">Terminates the adapter on shutdown of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service</span></span>  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c2385-113">在运行时将处理程序配置和终结点配置信息传递给适配器。</span><span class="sxs-lookup"><span data-stu-id="c2385-113">delivers handler configuration and endpoint configuration information to the adapter at run time.</span></span> <span data-ttu-id="c2385-114">指定配置的其他方面，例如服务时段，用于定义在此期间启用适配器以处理请求的特定时间段。</span><span class="sxs-lookup"><span data-stu-id="c2385-114">Other aspects of configuration are specified, such as service windows that define specific time periods during which the adapter is enabled to actively handle requests.</span></span>  
  
  <span data-ttu-id="c2385-115">BizTalk 服务可能会被手动关闭使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或通过使用服务控制管理器。</span><span class="sxs-lookup"><span data-stu-id="c2385-115">The BizTalk service may be manually shut down by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or by using the service control manager.</span></span> <span data-ttu-id="c2385-116">如果连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库会自动丢失该服务将回收其自身。</span><span class="sxs-lookup"><span data-stu-id="c2385-116">If connectivity to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases is lost the service automatically recycles itself.</span></span>  
  
  <span data-ttu-id="c2385-117">在典型的宿主模型中，接收端适配器和发送端适配器与 BizTalk 服务，以及消息引擎和业务流程引擎在同一进程中托管。</span><span class="sxs-lookup"><span data-stu-id="c2385-117">In the typical hosting model, receive-side adapters and send-side adapters are hosted in the same process as the BizTalk service, along with the Messaging Engine and the Orchestration Engine.</span></span> <span data-ttu-id="c2385-118">托管模型非常灵活，以便接收、 发送和业务流程的主机和的这些组合的分离。</span><span class="sxs-lookup"><span data-stu-id="c2385-118">The hosting model is flexible enough to allow for separation of receive, send, and orchestration hosts and combinations of these.</span></span> <span data-ttu-id="c2385-119">在下图中，主机在同一进程中的所有三个执行。</span><span class="sxs-lookup"><span data-stu-id="c2385-119">In the following figure, the host is executing all three in the same process.</span></span>  
  
  <span data-ttu-id="c2385-120">由于宿主模型富于它重要开发适配器要记住发送时，接收适配器可能不会配置在同一主机中。</span><span class="sxs-lookup"><span data-stu-id="c2385-120">Because of the rich hosting model, it is important when developing adapters to remember that the send and receive adapters may never be configured in the same host.</span></span> <span data-ttu-id="c2385-121">它们甚至可能配置为在不同计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="c2385-121">They may even be configured to run on different computers.</span></span>  
  
  <span data-ttu-id="c2385-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span><span class="sxs-lookup"><span data-stu-id="c2385-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span></span>  
  <span data-ttu-id="c2385-123">进程内适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="c2385-123">The in-process adapter hosting model</span></span>  
  
## <a name="isolated-adapters"></a><span data-ttu-id="c2385-124">独立的适配器</span><span class="sxs-lookup"><span data-stu-id="c2385-124">Isolated Adapters</span></span>  
 <span data-ttu-id="c2385-125">有托管 BizTalk 服务中接收适配器时的情况下不可能。</span><span class="sxs-lookup"><span data-stu-id="c2385-125">There are scenarios when hosting receive adapters in the BizTalk service is not possible.</span></span> <span data-ttu-id="c2385-126">例如，Internet 信息服务 (IIS) 进程模型是由 IIS 管理 ASP.NET 应用程序和 ISAPI 扩展的生存期。</span><span class="sxs-lookup"><span data-stu-id="c2385-126">For example, the Internet Information Services (IIS) process model is such that IIS manages the lifetime of ASP.NET applications and ISAPI extensions.</span></span> <span data-ttu-id="c2385-127">BizTalk SOAP 适配器必须运行在同一进程空间中作为 IIS 中，从而使其不可能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来控制 SOAP 适配器的任何实例的生存期。</span><span class="sxs-lookup"><span data-stu-id="c2385-127">The BizTalk SOAP adapter must run within the same process space as IIS, thus making it impossible for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to control the lifetime of any instances of the SOAP adapter.</span></span>  
  
 <span data-ttu-id="c2385-128">对于这些类型的适配器没有另一个宿主模型可供即独立接收适配器或简称独立的适配器。</span><span class="sxs-lookup"><span data-stu-id="c2385-128">For these types of adapters there is another hosting model referred to as isolated receive adapters, or simply isolated adapters.</span></span> <span data-ttu-id="c2385-129">没有独立的发送适配器的概念。</span><span class="sxs-lookup"><span data-stu-id="c2385-129">There is no concept of an isolated send adapter.</span></span>  
  
 <span data-ttu-id="c2385-130">因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能创建一个独立的适配器，适配器必须获取其自己的传输代理并传输代理注册自身。</span><span class="sxs-lookup"><span data-stu-id="c2385-130">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot create an isolated adapter, the adapter must acquire its own transport proxy and register itself with that transport proxy.</span></span>  
  
 <span data-ttu-id="c2385-131">下图说明了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]托管体系结构。</span><span class="sxs-lookup"><span data-stu-id="c2385-131">The following figure illustrates the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosting architecture.</span></span> <span data-ttu-id="c2385-132">为了提升性能，独立主机结构尽量免除任何不必要的进程间通信。</span><span class="sxs-lookup"><span data-stu-id="c2385-132">For the sake of performance, the isolated host architecture tries to eliminate any unnecessary interprocess communication.</span></span> <span data-ttu-id="c2385-133">由于独立的适配器和 BizTalk 消息引擎堆栈位于相同的过程中，没有任何进程间通信时该适配器调用消息引擎。</span><span class="sxs-lookup"><span data-stu-id="c2385-133">Because the isolated adapter and the BizTalk Messaging Engine stack are in the same process, there is no interprocess communication when the adapter is calling the Messaging Engine.</span></span> <span data-ttu-id="c2385-134">在该方案中，消息引擎和数据库之间是唯一的进程间通信，这是不可避免的。</span><span class="sxs-lookup"><span data-stu-id="c2385-134">In that scenario the only interprocess communication is between the Messaging Engine and the database, which is unavoidable.</span></span>  
  
 <span data-ttu-id="c2385-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span><span class="sxs-lookup"><span data-stu-id="c2385-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span></span>  
<span data-ttu-id="c2385-136">独立的适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="c2385-136">The isolated adapter hosting model</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2385-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2385-137">See Also</span></span>  
 [<span data-ttu-id="c2385-138">适配器框架概述</span><span class="sxs-lookup"><span data-stu-id="c2385-138">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)