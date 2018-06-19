---
title: 使用管道组件来选择现有路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a733da2348de13120ce37a205b77d2e8194c7790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295885"
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a><span data-ttu-id="71139-102">使用管道组件来选择现有路线</span><span class="sxs-lookup"><span data-stu-id="71139-102">Using a Pipeline Component to Select an Existing Itinerary</span></span>
## <a name="esb-itinerary-selector-pipeline-component"></a><span data-ttu-id="71139-103">ESB 路线的选择器管道组件</span><span class="sxs-lookup"><span data-stu-id="71139-103">ESB Itinerary Selector Pipeline Component</span></span>  
 <span data-ttu-id="71139-104">使用泛型路线上-渐变提交的消息将会提交没有路线标头。</span><span class="sxs-lookup"><span data-stu-id="71139-104">Messages submitted using generic itinerary on-ramps are submitted without an itinerary header.</span></span> <span data-ttu-id="71139-105">若要解决适当路线，并将其附加到传入的消息，在负载增加必须提供一种机制，可以将配置为从中央存储库访问路线。</span><span class="sxs-lookup"><span data-stu-id="71139-105">To resolve the appropriate itinerary and attach it to the incoming message, the on-ramp must provide a mechanism that can be configured to access itineraries from a central repository.</span></span>  
  
 <span data-ttu-id="71139-106">ESB 路线选择器管道组件使用的解析程序连接字符串，结合专用解析程序解析 （默认情况下，SQL Server） 存储在一个中心存储库服务器端路线的内容。</span><span class="sxs-lookup"><span data-stu-id="71139-106">The ESB Itinerary Selector pipeline component uses a resolver connection string, in conjunction with specialized resolvers, to resolve the content of a server-side itinerary stored in a central repository (by default, SQL Server).</span></span>  
  
 <span data-ttu-id="71139-107">当 WCF 上-渐变结合路线静态冲突解决程序中使用 ESB 路线选择器管道组件时，从消息上下文检索的名称和版本 （如在 SOAP 标头中表示），客户端请求路线和用于选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="71139-107">When the ESB Itinerary Selector pipeline component is used in WCF on-ramps in conjunction with the ITINERARY-STATIC resolver, the name and version of the itinerary requested by the client (as represented in the SOAP header) is retrieved from the message context and is used to select the appropriate itinerary.</span></span>  
  
 <span data-ttu-id="71139-108">默认情况下，ESB 路线选择器管道组件驻留在以下管道：</span><span class="sxs-lookup"><span data-stu-id="71139-108">By default, the ESB Itinerary Selector pipeline component resides in the following pipelines:</span></span>  
  
-   <span data-ttu-id="71139-109">ItinerarySelectReceive</span><span class="sxs-lookup"><span data-stu-id="71139-109">ItinerarySelectReceive</span></span>  
  
-   <span data-ttu-id="71139-110">ItinerarySelectReceivePassthrough</span><span class="sxs-lookup"><span data-stu-id="71139-110">ItinerarySelectReceivePassthrough</span></span>  
  
-   <span data-ttu-id="71139-111">ItinerarySelectReceiveXml</span><span class="sxs-lookup"><span data-stu-id="71139-111">ItinerarySelectReceiveXml</span></span>  
  
-   <span data-ttu-id="71139-112">ItinerarySelectSendReceive</span><span class="sxs-lookup"><span data-stu-id="71139-112">ItinerarySelectSendReceive</span></span>  
  
 <span data-ttu-id="71139-113">以下各节描述了每个组件执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="71139-113">The following sections describe the steps performed by each component.</span></span>  
  
## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a><span data-ttu-id="71139-114">ESB 路线的选择器管道组件处理步骤</span><span class="sxs-lookup"><span data-stu-id="71139-114">ESB Itinerary Selector Pipeline Component Processing Steps</span></span>  
 <span data-ttu-id="71139-115">ESB 路线选择器管道组件执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="71139-115">The ESB Itinerary Selector pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="71139-116">正在提交方提交邮件以进行处理。</span><span class="sxs-lookup"><span data-stu-id="71139-116">The submitting party submits a message for processing.</span></span> <span data-ttu-id="71139-117">路线选择器组件使用指定为属性连接字符串，由开发人员，配置的冲突解决程序来确定并从路线存储，基于消息内容或上下文中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="71139-117">The Itinerary Selector component uses a resolver specified as a property connection string, configured by the developer, to determine and select the appropriate itinerary from the itinerary store, based on message content or context.</span></span>  
  
-   <span data-ttu-id="71139-118">它验证路线，并设置要预设默认值，如果它们处于 null 路线; 的特定属性例如：</span><span class="sxs-lookup"><span data-stu-id="71139-118">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  
  
    -   <span data-ttu-id="71139-119">如果服务计数等于或大于 1，组件会引发异常。</span><span class="sxs-lookup"><span data-stu-id="71139-119">If Service count is less than 1, the component throws an exception.</span></span>  
  
    -   <span data-ttu-id="71139-120">该组件设置使用的服务计数，标识符的值的路线根特性 (**Uuid**)、 开始时间 (**BeginTime**)，以及是否这是单向还是双向的请求 (**IsRequestResponse**)。</span><span class="sxs-lookup"><span data-stu-id="71139-120">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  
  
    -   <span data-ttu-id="71139-121">组件验证服务，设置标识符，设置当前服务实例 （使服务能够处理下一步），并验证任何关联的解析程序。</span><span class="sxs-lookup"><span data-stu-id="71139-121">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  
  
    -   <span data-ttu-id="71139-122">该组件设置的 Microsoft BizTalk Server 段的路线使用以下属性：</span><span class="sxs-lookup"><span data-stu-id="71139-122">The component sets the Microsoft BizTalk Server segment of the itinerary using the following properties:</span></span>  
  
        -   <span data-ttu-id="71139-123">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="71139-123">**correlationToken**</span></span>  
  
        -   <span data-ttu-id="71139-124">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="71139-124">**reqRespTransmitPipelineID**</span></span>  
  
        -   <span data-ttu-id="71139-125">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="71139-125">**interchangeId**</span></span>  
  
        -   <span data-ttu-id="71139-126">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="71139-126">**receiveInstanceId**</span></span>  
  
        -   <span data-ttu-id="71139-127">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="71139-127">**epmRRCorrelationToken**</span></span>  
  
    -   <span data-ttu-id="71139-128">组件将写入使用系统 Properties.xsd 架构中定义的属性下表中列出的 BizTalk 消息上下文属性的修改后的路线。</span><span class="sxs-lookup"><span data-stu-id="71139-128">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="71139-129">属性</span><span class="sxs-lookup"><span data-stu-id="71139-129">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="71139-130">**名称 = ItineraryHeader**</span><span class="sxs-lookup"><span data-stu-id="71139-130">**Name = ItineraryHeader**</span></span>|  
        |<span data-ttu-id="71139-131">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span><span class="sxs-lookup"><span data-stu-id="71139-131">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span>|  
  
    -   <span data-ttu-id="71139-132">组件提升下使用系统 Properties.xsd 架构中定义的值的表中列出的四个 BizTalk 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="71139-132">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="71139-133">属性</span><span class="sxs-lookup"><span data-stu-id="71139-133">Property</span></span>|<span data-ttu-id="71139-134">值</span><span class="sxs-lookup"><span data-stu-id="71139-134">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="71139-135">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="71139-135">**ServiceName**</span></span>|<span data-ttu-id="71139-136">定义在路线中的当前服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="71139-136">The name of the current service instance defined in the itinerary.</span></span>|  
        |<span data-ttu-id="71139-137">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="71139-137">**ServiceType**</span></span>|<span data-ttu-id="71139-138">设置为**Orchestration**或**消息传送**。</span><span class="sxs-lookup"><span data-stu-id="71139-138">Set to either **Orchestration** or **Messaging**.</span></span>|  
        |<span data-ttu-id="71139-139">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="71139-139">**IsRequestResponse**</span></span>|<span data-ttu-id="71139-140">设置为**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="71139-140">Set to either **True** or **False**.</span></span>|  
        |<span data-ttu-id="71139-141">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="71139-141">**ServiceState**</span></span>|<span data-ttu-id="71139-142">设置为**挂起**。</span><span class="sxs-lookup"><span data-stu-id="71139-142">Set to **Pending**.</span></span>|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="71139-143">ESB 调度程序管道组件过程步骤</span><span class="sxs-lookup"><span data-stu-id="71139-143">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="71139-144">ESB 调度程序管道组件执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="71139-144">The ESB Dispatcher pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="71139-145">它管理的类型的任何路线步骤执行**消息**并提升路线。</span><span class="sxs-lookup"><span data-stu-id="71139-145">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="71139-146">位置识别并执行逻辑在消息处理周期，可能是根据其位置 ESB 调度程序组件**接收入站**，**发送传输**，**发送入站**，或**接收出站**。</span><span class="sxs-lookup"><span data-stu-id="71139-146">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound**, **Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="71139-147">ESB 调度程序管道组件调用路线 ESB Esb.config 文件中指定的消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="71139-147">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="71139-148">默认情况下，此组件用于路由和转换的配置属性是与以下服务：</span><span class="sxs-lookup"><span data-stu-id="71139-148">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  
  
    -   <span data-ttu-id="71139-149">**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="71139-149">**Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="71139-150">此服务执行对入站消息的负载的 BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="71139-150">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="71139-151">服务验证转换要求，并更新包含文档的规范名称和消息类型的 BizTalk 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="71139-151">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="71139-152">这是转换服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。</span><span class="sxs-lookup"><span data-stu-id="71139-152">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  
  
    -   <span data-ttu-id="71139-153">**Microsoft.Practices.ESB.Services.Routing。**</span><span class="sxs-lookup"><span data-stu-id="71139-153">**Microsoft.Practices.ESB.Services.Routing.**</span></span> <span data-ttu-id="71139-154">此服务使用的解析程序和适配器提供程序框架设置相应的终结点路由信息。</span><span class="sxs-lookup"><span data-stu-id="71139-154">This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="71139-155">这是路由服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。</span><span class="sxs-lookup"><span data-stu-id="71139-155">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>