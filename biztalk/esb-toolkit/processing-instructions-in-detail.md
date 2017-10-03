---
title: "处理详细信息中的说明 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532721c347189f2e3d4db9e57b2afc3aa45b76db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-instructions-in-detail"></a><span data-ttu-id="ece24-102">在详细信息中的处理指令</span><span class="sxs-lookup"><span data-stu-id="ece24-102">Processing Instructions in Detail</span></span>
<span data-ttu-id="ece24-103">本主题介绍的格式和定义所需的路线处理的多个上下文属性的系统 Properties.xsd 属性架构结构。</span><span class="sxs-lookup"><span data-stu-id="ece24-103">This topic describes the format and structure of the System-Properties.xsd property schema, which defines several context properties required for itinerary processing.</span></span> <span data-ttu-id="ece24-104">这些属性提升接收和处理通过一条消息时[!INCLUDE[prague](../includes/prague-md.md)]管道; 因为它们是提升的属性，它们都 BizTalk Server 组件访问。</span><span class="sxs-lookup"><span data-stu-id="ece24-104">These properties are promoted when a message is received and processed through [!INCLUDE[prague](../includes/prague-md.md)] pipelines; because they are promoted properties, they are accessible to BizTalk Server components.</span></span> <span data-ttu-id="ece24-105">系统 Properties.xsd 属性架构中定义以下属性：</span><span class="sxs-lookup"><span data-stu-id="ece24-105">The following properties are defined in the System-Properties.xsd property schema:</span></span>  
  
-   <span data-ttu-id="ece24-106">**ItineraryHeader。**</span><span class="sxs-lookup"><span data-stu-id="ece24-106">**ItineraryHeader.**</span></span> <span data-ttu-id="ece24-107">此属性包含所有路线的信息和通过一系列路线步骤要调用的路线服务的列表。</span><span class="sxs-lookup"><span data-stu-id="ece24-107">This property contains all the itinerary information and a list of itinerary services to be invoked through a sequence of itinerary steps.</span></span> <span data-ttu-id="ece24-108">路线 API 内部使用此属性。</span><span class="sxs-lookup"><span data-stu-id="ece24-108">The Itinerary API uses this property internally.</span></span>  
  
-   <span data-ttu-id="ece24-109">**ServiceName。**</span><span class="sxs-lookup"><span data-stu-id="ece24-109">**ServiceName.**</span></span> <span data-ttu-id="ece24-110">此属性包含要处理的当前路线服务的名称。</span><span class="sxs-lookup"><span data-stu-id="ece24-110">This property contains the name of the current itinerary service to process.</span></span>  
  
-   <span data-ttu-id="ece24-111">**ServiceState。**</span><span class="sxs-lookup"><span data-stu-id="ece24-111">**ServiceState.**</span></span> <span data-ttu-id="ece24-112">此属性包含当前路线服务的状态：**挂起**，**完成**，或**Active**。</span><span class="sxs-lookup"><span data-stu-id="ece24-112">This property contains the state of the current itinerary service: **Pending**, **Complete**, or **Active**.</span></span> <span data-ttu-id="ece24-113">所有服务都订阅包含一个路线步骤**ServiceState**值**挂起**。</span><span class="sxs-lookup"><span data-stu-id="ece24-113">All services subscribe to an itinerary step that contains a **ServiceState** value of **Pending**.</span></span>  
  
-   <span data-ttu-id="ece24-114">**ServiceType。**</span><span class="sxs-lookup"><span data-stu-id="ece24-114">**ServiceType.**</span></span> <span data-ttu-id="ece24-115">此属性定义的路线步骤的类型 (**消息**或**Orchestration**)。</span><span class="sxs-lookup"><span data-stu-id="ece24-115">This property defines the type of the itinerary step (**Messaging** or **Orchestration**).</span></span>  
  
-   <span data-ttu-id="ece24-116">**IsRequestResponse。**</span><span class="sxs-lookup"><span data-stu-id="ece24-116">**IsRequestResponse.**</span></span> <span data-ttu-id="ece24-117">此属性定义的消息传递的类型 (单向或请求-响应)。</span><span class="sxs-lookup"><span data-stu-id="ece24-117">This property defines the messaging type (one-way or request-response).</span></span>  
  
 <span data-ttu-id="ece24-118">路线服务中通过两种方式，具体取决于的值执行路线步骤**ServiceType**属性：</span><span class="sxs-lookup"><span data-stu-id="ece24-118">The Itinerary service executes itinerary steps in one of two ways, depending on the value of the **ServiceType** property:</span></span>  
  
-   <span data-ttu-id="ece24-119">路线管道组件执行所有路线步骤**ServiceType**属性**消息**。</span><span class="sxs-lookup"><span data-stu-id="ece24-119">Itinerary pipeline components execute all itinerary steps with a **ServiceType** property of **Messaging**.</span></span> <span data-ttu-id="ece24-120">开发人员可以扩展此过程，使用自定义管道和路线 API。</span><span class="sxs-lookup"><span data-stu-id="ece24-120">Developers can extend this process using a custom pipeline and the Itinerary API.</span></span>  
  
-   <span data-ttu-id="ece24-121">当**ServiceType**属性是**Orchestration**，业务流程，通过路线上下文属性的订阅激活执行路线的步骤。</span><span class="sxs-lookup"><span data-stu-id="ece24-121">When the **ServiceType** property is **Orchestration**, an orchestration, activated by a subscription to itinerary context properties, executes the itinerary step.</span></span>  
  
 <span data-ttu-id="ece24-122">当路线服务处理路线步骤时，此服务负责前移路线和使用发布的进一步处理的新路线上下文将消息调度的订阅的 BizTalk Server 的功能。</span><span class="sxs-lookup"><span data-stu-id="ece24-122">When an Itinerary service processes an itinerary step, the service is responsible for advancing the itinerary and dispatching the message with a new itinerary context for further processing using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="ece24-123">路线服务的消息上下文中路线的完全控制，因此可以转到相应的步骤基于其内部的逻辑和消息内容。</span><span class="sxs-lookup"><span data-stu-id="ece24-123">An itinerary service has full control of the itinerary in the message context and can advance to the appropriate step based on its internal logic and the message content.</span></span>  
  
 <span data-ttu-id="ece24-124">路线处理机制支持消息传送和业务流程路线中的步骤单个路线的组合。</span><span class="sxs-lookup"><span data-stu-id="ece24-124">The itinerary processing mechanism supports the combination of messaging and orchestration itinerary steps within a single itinerary.</span></span> <span data-ttu-id="ece24-125">开发人员还可以定义自定义路线服务和配置自定义路线的步骤。</span><span class="sxs-lookup"><span data-stu-id="ece24-125">Developers can also define custom itinerary services and configure custom itinerary steps.</span></span>  
  
 <span data-ttu-id="ece24-126">有关路线的详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ece24-126">For more information about itineraries, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
 <span data-ttu-id="ece24-127">有关自定义路线服务和自定义路线步骤的详细信息，请参阅[创建自定义路线服务](../esb-toolkit/creating-a-custom-itinerary-service.md)。</span><span class="sxs-lookup"><span data-stu-id="ece24-127">For more information about custom itinerary services and custom itinerary steps, see [Creating a Custom Itinerary Service](../esb-toolkit/creating-a-custom-itinerary-service.md).</span></span>