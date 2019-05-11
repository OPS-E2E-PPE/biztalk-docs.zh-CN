---
title: WCF LOB 适配器 SDK 适配器通道和服务之间的差异 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24d41d96-0ea1-4a97-bd45-b65afdbbd923
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7ec63ce59139d0a34aa66969bde1898c0981e94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363678"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="99daa-102">WCF LOB 适配器 SDK 适配器通道和服务之间的差异</span><span class="sxs-lookup"><span data-stu-id="99daa-102">Difference between adapter channel and service in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="99daa-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]每个提供了一组可用于将应用程序功能提供给使用方应用程序在同一计算机上或在网络上的 Api。</span><span class="sxs-lookup"><span data-stu-id="99daa-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] each provide a set of APIs that can be used to expose application functionality to consuming applications on the same computer or across a network.</span></span> <span data-ttu-id="99daa-104">若要选择最合适的框架，您必须考虑将公开提供的功能的业务需求以及目标系统应用程序的属性。</span><span class="sxs-lookup"><span data-stu-id="99daa-104">To choose the most appropriate framework, you must consider the properties of the target system application you are exposing as well as the business requirements for the exposed functionality.</span></span> <span data-ttu-id="99daa-105">本主题提供了可用于选择合适的框架的准则。</span><span class="sxs-lookup"><span data-stu-id="99daa-105">This topic provides guidelines that you can use to choose the appropriate framework.</span></span>  
  
## <a name="when-to-write-an-adapter"></a><span data-ttu-id="99daa-106">何时编写一个适配器</span><span class="sxs-lookup"><span data-stu-id="99daa-106">When to Write an Adapter</span></span>  
 <span data-ttu-id="99daa-107">请考虑编写适配器使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]时：</span><span class="sxs-lookup"><span data-stu-id="99daa-107">Consider writing an adapter using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] when:</span></span>  
  
- <span data-ttu-id="99daa-108">在目标系统是现有的、 非*Web 服务启用*系统</span><span class="sxs-lookup"><span data-stu-id="99daa-108">The target system is an existing, non-*Web services-enabled* system</span></span>  
  
- <span data-ttu-id="99daa-109">在目标系统是动态的可以使用新的操作增强</span><span class="sxs-lookup"><span data-stu-id="99daa-109">The target system is dynamic and can be enhanced with new operations</span></span>  
  
- <span data-ttu-id="99daa-110">目标系统具有大量的元数据</span><span class="sxs-lookup"><span data-stu-id="99daa-110">The target system has a large amount of metadata</span></span>  
  
- <span data-ttu-id="99daa-111">大型、 不同的目标系统的数据的用户数</span><span class="sxs-lookup"><span data-stu-id="99daa-111">There is a large, diverse number of users for the target system's data</span></span>  
  
- <span data-ttu-id="99daa-112">消费应用程序需要丰富的应用程序元数据发现功能</span><span class="sxs-lookup"><span data-stu-id="99daa-112">Consuming applications need rich application metadata discovery functionality</span></span>  
  
  <span data-ttu-id="99daa-113">例如，如果目标系统包含数百个用于管理卫生保健声明的操作和操作都是动态 （这意味着用户可以添加执行其他任务的新操作），则最好公开此功能使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99daa-113">For example, if the target system contains hundreds of operations for managing health care claims, and the operations are dynamic (meaning users can add new operations that perform additional tasks), it makes sense to expose this functionality using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="99daa-114">这将确保新的操作是使用适配器的应用程序可发现。</span><span class="sxs-lookup"><span data-stu-id="99daa-114">This will ensure that new operations are discoverable by applications using the adapter.</span></span> <span data-ttu-id="99daa-115">使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，必须修改服务协定，因为它是静态的。</span><span class="sxs-lookup"><span data-stu-id="99daa-115">With [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], you would have to modify the service contract because it is static.</span></span>  
  
## <a name="when-to-write-a-service"></a><span data-ttu-id="99daa-116">何时编写的服务</span><span class="sxs-lookup"><span data-stu-id="99daa-116">When to Write a Service</span></span>  
 <span data-ttu-id="99daa-117">使用*WCF 服务模型*创建服务时：</span><span class="sxs-lookup"><span data-stu-id="99daa-117">Use the *WCF Service Model* to create a service when:</span></span>  
  
- <span data-ttu-id="99daa-118">在目标系统是静态的且具有一组固定的操作</span><span class="sxs-lookup"><span data-stu-id="99daa-118">The target system is static and has a fixed set of operations</span></span>  
  
- <span data-ttu-id="99daa-119">目标系统具有很少或没有元数据</span><span class="sxs-lookup"><span data-stu-id="99daa-119">The target system has little or no metadata</span></span>  
  
- <span data-ttu-id="99daa-120">服务开发人员都有详细的应用程序公开的了解</span><span class="sxs-lookup"><span data-stu-id="99daa-120">Service developers have detailed knowledge of the application to be exposed</span></span>  
  
- <span data-ttu-id="99daa-121">公开的全新应用程序</span><span class="sxs-lookup"><span data-stu-id="99daa-121">A brand new application is being exposed</span></span>  
  
- <span data-ttu-id="99daa-122">要创建泛型传输适配器</span><span class="sxs-lookup"><span data-stu-id="99daa-122">You are creating generic transport adapters</span></span>  
  
  <span data-ttu-id="99daa-123">例如，如果目标系统包含用于管理的体育团队 20 操作，您可以公开操作作为静态协定使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="99daa-123">For example, if the target system contains 20 operations for managing sports teams, you can expose the operations as a static contract using [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="99daa-124">通过此操作，避免实现不必要的元数据功能并有可能可以最大程度减少开发时间。</span><span class="sxs-lookup"><span data-stu-id="99daa-124">By doing so, you avoid implementing unnecessary metadata features and you can potentially minimize development time.</span></span>  
  
## <a name="when-to-write-a-channel"></a><span data-ttu-id="99daa-125">当编写一个通道</span><span class="sxs-lookup"><span data-stu-id="99daa-125">When to Write a Channel</span></span>  
 <span data-ttu-id="99daa-126">使用*WCF 通道模型*创建通道时：</span><span class="sxs-lookup"><span data-stu-id="99daa-126">Use the *WCF Channel Model* to create a channel when:</span></span>  
  
-   <span data-ttu-id="99daa-127">创建网络协议。</span><span class="sxs-lookup"><span data-stu-id="99daa-127">Creating a wire protocol.</span></span> <span data-ttu-id="99daa-128">网络协议的示例包括 WS-ReliableMessaging 协议。</span><span class="sxs-lookup"><span data-stu-id="99daa-128">Examples of wire protocols include WS-ReliableMessaging Protocol.</span></span>  
  
-   <span data-ttu-id="99daa-129">发送/接收 WCF 消息而不是 WCF （TCP、 HTTP、 命名管道、 MSMQ 和对等通道） 中包含的传输。</span><span class="sxs-lookup"><span data-stu-id="99daa-129">Send/receive WCF messages over a transport other than ones that are included in WCF (TCP, HTTP, Named Pipes, MSMQ and PeerChannel).</span></span> <span data-ttu-id="99daa-130">例如，可以编写 UDP 传输、 TIBCO 或 Java 消息服务 (JMS) 传输。</span><span class="sxs-lookup"><span data-stu-id="99daa-130">For example, you can write a UDP transport, TIBCO, or a Java Messaging Service (JMS) transport.</span></span>  
  
-   <span data-ttu-id="99daa-131">与不作为 Web 服务公开的系统集成。</span><span class="sxs-lookup"><span data-stu-id="99daa-131">Integrating with a system that is not exposed as a Web service.</span></span>  <span data-ttu-id="99daa-132">在这种情况下你传输充当调整现有系统的消息格式或 API 允许 WCF 客户端的 WCF 消息以直接与现有系统进行通信的适配器。</span><span class="sxs-lookup"><span data-stu-id="99daa-132">In this case your transport acts as an adapter adapting WCF messages to the existing system's message format or API allowing a WCF client to talk directly to the existing system.</span></span> <span data-ttu-id="99daa-133">此示例是 Web 服务增强 (WSE) 3.0 TCP 传输。</span><span class="sxs-lookup"><span data-stu-id="99daa-133">An example of this is the Web Services Enhancement (WSE) 3.0 TCP transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99daa-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="99daa-134">See Also</span></span>  
 <span data-ttu-id="99daa-135">[规划和设计适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="99daa-135">[Plan and design an adapter using the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="99daa-136">了解 LOB 系统与 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="99daa-136">Understand the LOB system with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)