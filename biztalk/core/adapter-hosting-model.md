---
title: "承载模型的适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf9a8e6b-8c8d-47ec-b2a3-aed58206121d
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645a1fcd41650c98c442549a898f7083be770842
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-hosting-model"></a><span data-ttu-id="da5dd-102">承载模型的适配器</span><span class="sxs-lookup"><span data-stu-id="da5dd-102">Adapter Hosting Model</span></span>
<span data-ttu-id="da5dd-103">一般情况下在 BizTalk 服务中，Btsntsvc.exe 托管 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="da5dd-103">In general BizTalk adapters are hosted in the BizTalk service, Btsntsvc.exe.</span></span> <span data-ttu-id="da5dd-104">这意味着，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理适配器的生存期。</span><span class="sxs-lookup"><span data-stu-id="da5dd-104">This means that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] manages the lifetime of the adapter.</span></span> <span data-ttu-id="da5dd-105">但也存在其他进程管理适配器的情况，如下所述。</span><span class="sxs-lookup"><span data-stu-id="da5dd-105">There are also situations, described below, where other processes manage the adapter.</span></span>  
  
## <a name="in-process-adapters"></a><span data-ttu-id="da5dd-106">进程内适配器</span><span class="sxs-lookup"><span data-stu-id="da5dd-106">In-Process Adapters</span></span>  
 <span data-ttu-id="da5dd-107">由管理的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]称为进程内适配器。</span><span class="sxs-lookup"><span data-stu-id="da5dd-107">Adapters that are managed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are called in-process adapters.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="da5dd-108">为执行以下这些适配器：</span><span class="sxs-lookup"><span data-stu-id="da5dd-108"> does the following for these adapters:</span></span>  
  
-   <span data-ttu-id="da5dd-109">实例化适配器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]启动</span><span class="sxs-lookup"><span data-stu-id="da5dd-109">Instantiate the adapter when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is started</span></span>  
  
-   <span data-ttu-id="da5dd-110">初始化期间，将适配器的传输代理传递给适配器</span><span class="sxs-lookup"><span data-stu-id="da5dd-110">Passes the adapter's transport proxy to the adapter during initialization</span></span>  
  
-   <span data-ttu-id="da5dd-111">处理适配器的请求</span><span class="sxs-lookup"><span data-stu-id="da5dd-111">Services the adapter's requests</span></span>  
  
-   <span data-ttu-id="da5dd-112">终止的适配器上的关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务</span><span class="sxs-lookup"><span data-stu-id="da5dd-112">Terminates the adapter on shutdown of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="da5dd-113">将在运行时提供给适配器处理程序配置和终结点配置信息。</span><span class="sxs-lookup"><span data-stu-id="da5dd-113"> delivers handler configuration and endpoint configuration information to the adapter at run time.</span></span> <span data-ttu-id="da5dd-114">还指定其他配置信息，例如服务时段，它定义启用适配器以处理请求的特定时间段。</span><span class="sxs-lookup"><span data-stu-id="da5dd-114">Other aspects of configuration are specified, such as service windows that define specific time periods during which the adapter is enabled to actively handle requests.</span></span>  
  
 <span data-ttu-id="da5dd-115">可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或服务控制管理器手动关闭 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="da5dd-115">The BizTalk service may be manually shut down by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or by using the service control manager.</span></span> <span data-ttu-id="da5dd-116">如果连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库丢失该服务的自动回收本身。</span><span class="sxs-lookup"><span data-stu-id="da5dd-116">If connectivity to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases is lost the service automatically recycles itself.</span></span>  
  
 <span data-ttu-id="da5dd-117">在典型的宿主模型中，接收端适配器、发送端适配器与 BizTalk 服务及消息引擎和业务流程引擎的宿主均为同一进程。</span><span class="sxs-lookup"><span data-stu-id="da5dd-117">In the typical hosting model, receive-side adapters and send-side adapters are hosted in the same process as the BizTalk service, along with the Messaging Engine and the Orchestration Engine.</span></span> <span data-ttu-id="da5dd-118">宿主模型极其灵活，既允许将接收、发送和业务流程主机分开，也允许将它们合并。</span><span class="sxs-lookup"><span data-stu-id="da5dd-118">The hosting model is flexible enough to allow for separation of receive, send, and orchestration hosts and combinations of these.</span></span> <span data-ttu-id="da5dd-119">下图中的主机在同一进程中执行这三种任务。</span><span class="sxs-lookup"><span data-stu-id="da5dd-119">In the following figure, the host is executing all three in the same process.</span></span>  
  
 <span data-ttu-id="da5dd-120">由于宿主模型富于变化，所以在开发适配器的过程中，一定要牢记发送适配器和接收适配器可能不会配置在同一主机中。</span><span class="sxs-lookup"><span data-stu-id="da5dd-120">Because of the rich hosting model, it is important when developing adapters to remember that the send and receive adapters may never be configured in the same host.</span></span> <span data-ttu-id="da5dd-121">它们甚至可能配置为运行在不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="da5dd-121">They may even be configured to run on different computers.</span></span>  
  
 ![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")  
<span data-ttu-id="da5dd-122">进程内适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="da5dd-122">The in-process adapter hosting model</span></span>  
  
## <a name="isolated-adapters"></a><span data-ttu-id="da5dd-123">独立的适配器</span><span class="sxs-lookup"><span data-stu-id="da5dd-123">Isolated Adapters</span></span>  
 <span data-ttu-id="da5dd-124">有时接收适配器不可能驻留在 BizTalk 服务中。</span><span class="sxs-lookup"><span data-stu-id="da5dd-124">There are scenarios when hosting receive adapters in the BizTalk service is not possible.</span></span> <span data-ttu-id="da5dd-125">例如，在某些 Internet 信息服务 (IIS) 进程模型中，ASP.NET 应用程序和 ISAPI 扩展的生存期是由 IIS 管理的。</span><span class="sxs-lookup"><span data-stu-id="da5dd-125">For example, the Internet Information Services (IIS) process model is such that IIS manages the lifetime of ASP.NET applications and ISAPI extensions.</span></span> <span data-ttu-id="da5dd-126">BizTalk SOAP 适配器必须运行在相同的进程空间 IIS，从而使其不可能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来控制 SOAP 适配器的任何实例的生存期。</span><span class="sxs-lookup"><span data-stu-id="da5dd-126">The BizTalk SOAP adapter must run within the same process space as IIS, thus making it impossible for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to control the lifetime of any instances of the SOAP adapter.</span></span>  
  
 <span data-ttu-id="da5dd-127">对于这些类型的适配器，有另一种宿主模型可供使用，即独立接收适配器，简称独立适配器。</span><span class="sxs-lookup"><span data-stu-id="da5dd-127">For these types of adapters there is another hosting model referred to as isolated receive adapters, or simply isolated adapters.</span></span> <span data-ttu-id="da5dd-128">没有独立发送适配器这一概念。</span><span class="sxs-lookup"><span data-stu-id="da5dd-128">There is no concept of an isolated send adapter.</span></span>  
  
 <span data-ttu-id="da5dd-129">因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法创建独立的适配器，适配器必须获取其自己的传输代理并使用该传输代理注册自身。</span><span class="sxs-lookup"><span data-stu-id="da5dd-129">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot create an isolated adapter, the adapter must acquire its own transport proxy and register itself with that transport proxy.</span></span>  
  
 <span data-ttu-id="da5dd-130">下图说明了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载体系结构。</span><span class="sxs-lookup"><span data-stu-id="da5dd-130">The following figure illustrates the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosting architecture.</span></span> <span data-ttu-id="da5dd-131">为了提升性能，独立主机结构尽量免除一切不必要的进程间通信。</span><span class="sxs-lookup"><span data-stu-id="da5dd-131">For the sake of performance, the isolated host architecture tries to eliminate any unnecessary interprocess communication.</span></span> <span data-ttu-id="da5dd-132">由于独立适配器和 BizTalk 消息引擎堆栈位于同一进程中，因此该适配器调用消息引擎时没有进程间通信。</span><span class="sxs-lookup"><span data-stu-id="da5dd-132">Because the isolated adapter and the BizTalk Messaging Engine stack are in the same process, there is no interprocess communication when the adapter is calling the Messaging Engine.</span></span> <span data-ttu-id="da5dd-133">在此情况下，唯一的进程间通信发生在消息引擎和数据库之间，这是不可避免的。</span><span class="sxs-lookup"><span data-stu-id="da5dd-133">In that scenario the only interprocess communication is between the Messaging Engine and the database, which is unavoidable.</span></span>  
  
 ![](../core/media/isolatedadapters.gif "IsolatedAdapters")  
<span data-ttu-id="da5dd-134">独立适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="da5dd-134">The isolated adapter hosting model</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5dd-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da5dd-135">See Also</span></span>  
 [<span data-ttu-id="da5dd-136">什么是适配器 Framework？</span><span class="sxs-lookup"><span data-stu-id="da5dd-136">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)