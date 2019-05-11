---
title: 处理详细信息中的说明 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d65b3e7489171236acdee6313bda2485f31553a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301764"
---
# <a name="processing-instructions-in-detail"></a><span data-ttu-id="62c56-102">在详细信息的处理指令</span><span class="sxs-lookup"><span data-stu-id="62c56-102">Processing Instructions in Detail</span></span>
<span data-ttu-id="62c56-103">本主题介绍的格式和系统 Properties.xsd 属性架构，用于定义路线处理所需的多个上下文属性的结构。</span><span class="sxs-lookup"><span data-stu-id="62c56-103">This topic describes the format and structure of the System-Properties.xsd property schema, which defines several context properties required for itinerary processing.</span></span> <span data-ttu-id="62c56-104">这些属性将升级时接收并处理通过 BizTalk Server 管道; 一条消息由于它们是升级的属性，它们都可以访问 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="62c56-104">These properties are promoted when a message is received and processed through BizTalk Server pipelines; because they are promoted properties, they are accessible to BizTalk Server components.</span></span> <span data-ttu-id="62c56-105">系统 Properties.xsd 属性架构中定义以下属性：</span><span class="sxs-lookup"><span data-stu-id="62c56-105">The following properties are defined in the System-Properties.xsd property schema:</span></span>  
  
- <span data-ttu-id="62c56-106">**ItineraryHeader.**</span><span class="sxs-lookup"><span data-stu-id="62c56-106">**ItineraryHeader.**</span></span> <span data-ttu-id="62c56-107">此属性包含所有路线信息和路线服务通过一系列的路线步骤要调用的列表。</span><span class="sxs-lookup"><span data-stu-id="62c56-107">This property contains all the itinerary information and a list of itinerary services to be invoked through a sequence of itinerary steps.</span></span> <span data-ttu-id="62c56-108">路线 API 在内部使用此属性。</span><span class="sxs-lookup"><span data-stu-id="62c56-108">The Itinerary API uses this property internally.</span></span>  
  
- <span data-ttu-id="62c56-109">**ServiceName。**</span><span class="sxs-lookup"><span data-stu-id="62c56-109">**ServiceName.**</span></span> <span data-ttu-id="62c56-110">此属性包含要处理的当前路线服务的名称。</span><span class="sxs-lookup"><span data-stu-id="62c56-110">This property contains the name of the current itinerary service to process.</span></span>  
  
- <span data-ttu-id="62c56-111">**ServiceState.**</span><span class="sxs-lookup"><span data-stu-id="62c56-111">**ServiceState.**</span></span> <span data-ttu-id="62c56-112">此属性包含当前的路线服务的状态：**挂起**，**完整**，或**Active**。</span><span class="sxs-lookup"><span data-stu-id="62c56-112">This property contains the state of the current itinerary service: **Pending**, **Complete**, or **Active**.</span></span> <span data-ttu-id="62c56-113">所有服务都订阅包含行程步骤**ServiceState**的值**挂起**。</span><span class="sxs-lookup"><span data-stu-id="62c56-113">All services subscribe to an itinerary step that contains a **ServiceState** value of **Pending**.</span></span>  
  
- <span data-ttu-id="62c56-114">**ServiceType.**</span><span class="sxs-lookup"><span data-stu-id="62c56-114">**ServiceType.**</span></span> <span data-ttu-id="62c56-115">此属性定义路线步骤的类型 (**Messaging**或**业务流程**)。</span><span class="sxs-lookup"><span data-stu-id="62c56-115">This property defines the type of the itinerary step (**Messaging** or **Orchestration**).</span></span>  
  
- <span data-ttu-id="62c56-116">**IsRequestResponse。**</span><span class="sxs-lookup"><span data-stu-id="62c56-116">**IsRequestResponse.**</span></span> <span data-ttu-id="62c56-117">此属性定义的消息类型 (单向或请求-响应)。</span><span class="sxs-lookup"><span data-stu-id="62c56-117">This property defines the messaging type (one-way or request-response).</span></span>  
  
  <span data-ttu-id="62c56-118">路线服务中有两种，具体取决于值执行路线步骤**ServiceType**属性：</span><span class="sxs-lookup"><span data-stu-id="62c56-118">The Itinerary service executes itinerary steps in one of two ways, depending on the value of the **ServiceType** property:</span></span>  
  
- <span data-ttu-id="62c56-119">路线的管道组件执行所有路线步骤**ServiceType**的属性**消息传送**。</span><span class="sxs-lookup"><span data-stu-id="62c56-119">Itinerary pipeline components execute all itinerary steps with a **ServiceType** property of **Messaging**.</span></span> <span data-ttu-id="62c56-120">开发人员可以扩展此过程使用的自定义管道和路线 API。</span><span class="sxs-lookup"><span data-stu-id="62c56-120">Developers can extend this process using a custom pipeline and the Itinerary API.</span></span>  
  
- <span data-ttu-id="62c56-121">当**ServiceType**属性是**业务流程**，由对路线上下文属性的订阅激活业务流程执行路线的步骤。</span><span class="sxs-lookup"><span data-stu-id="62c56-121">When the **ServiceType** property is **Orchestration**, an orchestration, activated by a subscription to itinerary context properties, executes the itinerary step.</span></span>  
  
  <span data-ttu-id="62c56-122">当路线服务处理行程步骤时，此服务负责提前路线和调度的消息的新的路线上下文以进行进一步处理使用发布的订阅的 BizTalk Server 功能。</span><span class="sxs-lookup"><span data-stu-id="62c56-122">When an Itinerary service processes an itinerary step, the service is responsible for advancing the itinerary and dispatching the message with a new itinerary context for further processing using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="62c56-123">路线服务具有完全控制权限的消息上下文中路线，并可以转到相应的步骤基于其内部逻辑和消息内容。</span><span class="sxs-lookup"><span data-stu-id="62c56-123">An itinerary service has full control of the itinerary in the message context and can advance to the appropriate step based on its internal logic and the message content.</span></span>  
  
  <span data-ttu-id="62c56-124">路线的处理机制支持单个路线中的消息传送和业务流程路线步骤的组合。</span><span class="sxs-lookup"><span data-stu-id="62c56-124">The itinerary processing mechanism supports the combination of messaging and orchestration itinerary steps within a single itinerary.</span></span> <span data-ttu-id="62c56-125">开发人员还可以定义自定义路线服务和配置自定义路线的步骤。</span><span class="sxs-lookup"><span data-stu-id="62c56-125">Developers can also define custom itinerary services and configure custom itinerary steps.</span></span>  
  
  <span data-ttu-id="62c56-126">关于路线的详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="62c56-126">For more information about itineraries, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
  <span data-ttu-id="62c56-127">有关自定义路线服务和自定义路线步骤的详细信息，请参阅[创建自定义路线服务](../esb-toolkit/creating-a-custom-itinerary-service.md)。</span><span class="sxs-lookup"><span data-stu-id="62c56-127">For more information about custom itinerary services and custom itinerary steps, see [Creating a Custom Itinerary Service](../esb-toolkit/creating-a-custom-itinerary-service.md).</span></span>