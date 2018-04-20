---
title: 承载模型的适配器 |Microsoft 文档
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
ms.openlocfilehash: 645a1fcd41650c98c442549a898f7083be770842
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="adapter-hosting-model"></a><span data-ttu-id="00504-102">承载模型的适配器</span><span class="sxs-lookup"><span data-stu-id="00504-102">Adapter Hosting Model</span></span>
<span data-ttu-id="00504-103">一般情况下在 BizTalk 服务中，Btsntsvc.exe 托管 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="00504-103">In general BizTalk adapters are hosted in the BizTalk service, Btsntsvc.exe.</span></span> <span data-ttu-id="00504-104">这意味着，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理适配器的生存期。</span><span class="sxs-lookup"><span data-stu-id="00504-104">This means that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] manages the lifetime of the adapter.</span></span> <span data-ttu-id="00504-105">但也存在其他进程管理适配器的情况，如下所述。</span><span class="sxs-lookup"><span data-stu-id="00504-105">There are also situations, described below, where other processes manage the adapter.</span></span>  
  
## <a name="in-process-adapters"></a><span data-ttu-id="00504-106">进程内适配器</span><span class="sxs-lookup"><span data-stu-id="00504-106">In-Process Adapters</span></span>  
 <span data-ttu-id="00504-107">由管理的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]称为进程内适配器。</span><span class="sxs-lookup"><span data-stu-id="00504-107">Adapters that are managed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are called in-process adapters.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="00504-108"> 为执行以下这些适配器：</span><span class="sxs-lookup"><span data-stu-id="00504-108"> does the following for these adapters:</span></span>  
  
-   <span data-ttu-id="00504-109">实例化适配器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]启动</span><span class="sxs-lookup"><span data-stu-id="00504-109">Instantiate the adapter when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is started</span></span>  
  
-   <span data-ttu-id="00504-110">初始化期间，将适配器的传输代理传递给适配器</span><span class="sxs-lookup"><span data-stu-id="00504-110">Passes the adapter's transport proxy to the adapter during initialization</span></span>  
  
-   <span data-ttu-id="00504-111">处理适配器的请求</span><span class="sxs-lookup"><span data-stu-id="00504-111">Services the adapter's requests</span></span>  
  
-   <span data-ttu-id="00504-112">终止的适配器上的关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务</span><span class="sxs-lookup"><span data-stu-id="00504-112">Terminates the adapter on shutdown of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="00504-113"> 将在运行时提供给适配器处理程序配置和终结点配置信息。</span><span class="sxs-lookup"><span data-stu-id="00504-113"> delivers handler configuration and endpoint configuration information to the adapter at run time.</span></span> <span data-ttu-id="00504-114">还指定其他配置信息，例如服务时段，它定义启用适配器以处理请求的特定时间段。</span><span class="sxs-lookup"><span data-stu-id="00504-114">Other aspects of configuration are specified, such as service windows that define specific time periods during which the adapter is enabled to actively handle requests.</span></span>  
  
 <span data-ttu-id="00504-115">可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或服务控制管理器手动关闭 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="00504-115">The BizTalk service may be manually shut down by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or by using the service control manager.</span></span> <span data-ttu-id="00504-116">如果连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库丢失该服务的自动回收本身。</span><span class="sxs-lookup"><span data-stu-id="00504-116">If connectivity to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases is lost the service automatically recycles itself.</span></span>  
  
 <span data-ttu-id="00504-117">在典型的宿主模型中，接收端适配器、发送端适配器与 BizTalk 服务及消息引擎和业务流程引擎的宿主均为同一进程。</span><span class="sxs-lookup"><span data-stu-id="00504-117">In the typical hosting model, receive-side adapters and send-side adapters are hosted in the same process as the BizTalk service, along with the Messaging Engine and the Orchestration Engine.</span></span> <span data-ttu-id="00504-118">宿主模型极其灵活，既允许将接收、发送和业务流程主机分开，也允许将它们合并。</span><span class="sxs-lookup"><span data-stu-id="00504-118">The hosting model is flexible enough to allow for separation of receive, send, and orchestration hosts and combinations of these.</span></span> <span data-ttu-id="00504-119">下图中的主机在同一进程中执行这三种任务。</span><span class="sxs-lookup"><span data-stu-id="00504-119">In the following figure, the host is executing all three in the same process.</span></span>  
  
 <span data-ttu-id="00504-120">由于宿主模型富于变化，所以在开发适配器的过程中，一定要牢记发送适配器和接收适配器可能不会配置在同一主机中。</span><span class="sxs-lookup"><span data-stu-id="00504-120">Because of the rich hosting model, it is important when developing adapters to remember that the send and receive adapters may never be configured in the same host.</span></span> <span data-ttu-id="00504-121">它们甚至可能配置为运行在不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="00504-121">They may even be configured to run on different computers.</span></span>  
  
 <span data-ttu-id="00504-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span><span class="sxs-lookup"><span data-stu-id="00504-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span></span>  
<span data-ttu-id="00504-123">进程内适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="00504-123">The in-process adapter hosting model</span></span>  
  
## <a name="isolated-adapters"></a><span data-ttu-id="00504-124">独立的适配器</span><span class="sxs-lookup"><span data-stu-id="00504-124">Isolated Adapters</span></span>  
 <span data-ttu-id="00504-125">有时接收适配器不可能驻留在 BizTalk 服务中。</span><span class="sxs-lookup"><span data-stu-id="00504-125">There are scenarios when hosting receive adapters in the BizTalk service is not possible.</span></span> <span data-ttu-id="00504-126">例如，在某些 Internet 信息服务 (IIS) 进程模型中，ASP.NET 应用程序和 ISAPI 扩展的生存期是由 IIS 管理的。</span><span class="sxs-lookup"><span data-stu-id="00504-126">For example, the Internet Information Services (IIS) process model is such that IIS manages the lifetime of ASP.NET applications and ISAPI extensions.</span></span> <span data-ttu-id="00504-127">BizTalk SOAP 适配器必须运行在相同的进程空间 IIS，从而使其不可能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来控制 SOAP 适配器的任何实例的生存期。</span><span class="sxs-lookup"><span data-stu-id="00504-127">The BizTalk SOAP adapter must run within the same process space as IIS, thus making it impossible for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to control the lifetime of any instances of the SOAP adapter.</span></span>  
  
 <span data-ttu-id="00504-128">对于这些类型的适配器，有另一种宿主模型可供使用，即独立接收适配器，简称独立适配器。</span><span class="sxs-lookup"><span data-stu-id="00504-128">For these types of adapters there is another hosting model referred to as isolated receive adapters, or simply isolated adapters.</span></span> <span data-ttu-id="00504-129">没有独立发送适配器这一概念。</span><span class="sxs-lookup"><span data-stu-id="00504-129">There is no concept of an isolated send adapter.</span></span>  
  
 <span data-ttu-id="00504-130">因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法创建独立的适配器，适配器必须获取其自己的传输代理并使用该传输代理注册自身。</span><span class="sxs-lookup"><span data-stu-id="00504-130">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot create an isolated adapter, the adapter must acquire its own transport proxy and register itself with that transport proxy.</span></span>  
  
 <span data-ttu-id="00504-131">下图说明了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载体系结构。</span><span class="sxs-lookup"><span data-stu-id="00504-131">The following figure illustrates the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosting architecture.</span></span> <span data-ttu-id="00504-132">为了提升性能，独立主机结构尽量免除一切不必要的进程间通信。</span><span class="sxs-lookup"><span data-stu-id="00504-132">For the sake of performance, the isolated host architecture tries to eliminate any unnecessary interprocess communication.</span></span> <span data-ttu-id="00504-133">由于独立适配器和 BizTalk 消息引擎堆栈位于同一进程中，因此该适配器调用消息引擎时没有进程间通信。</span><span class="sxs-lookup"><span data-stu-id="00504-133">Because the isolated adapter and the BizTalk Messaging Engine stack are in the same process, there is no interprocess communication when the adapter is calling the Messaging Engine.</span></span> <span data-ttu-id="00504-134">在此情况下，唯一的进程间通信发生在消息引擎和数据库之间，这是不可避免的。</span><span class="sxs-lookup"><span data-stu-id="00504-134">In that scenario the only interprocess communication is between the Messaging Engine and the database, which is unavoidable.</span></span>  
  
 <span data-ttu-id="00504-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span><span class="sxs-lookup"><span data-stu-id="00504-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span></span>  
<span data-ttu-id="00504-136">独立适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="00504-136">The isolated adapter hosting model</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00504-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00504-137">See Also</span></span>  
 [<span data-ttu-id="00504-138">适配器框架概述</span><span class="sxs-lookup"><span data-stu-id="00504-138">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)