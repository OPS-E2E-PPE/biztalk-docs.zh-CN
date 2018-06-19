---
title: 使用管道组件读取一条路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bceec4df732247be043e006b52c7abbfbf6a6b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296189"
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a><span data-ttu-id="83517-102">使用管道组件读取一条路线</span><span class="sxs-lookup"><span data-stu-id="83517-102">Using a Pipeline Component to Read an Itinerary</span></span>
<span data-ttu-id="83517-103">在接收管道到达的消息可以包含在其定义其处理要求 （客户端路线） 的 SOAP 标头的元数据。</span><span class="sxs-lookup"><span data-stu-id="83517-103">A message that arrives in a receive pipeline can contain metadata in its SOAP header that defines its processing requirements (client-side itinerary).</span></span> <span data-ttu-id="83517-104">图 1 说明 ESB 路线和 ESB 调度程序管道组件的用法。</span><span class="sxs-lookup"><span data-stu-id="83517-104">Figure 1 illustrates the use of the ESB Itinerary and ESB Dispatcher pipeline components.</span></span>  
  
 <span data-ttu-id="83517-105">![管道组件读取](../esb-toolkit/media/ch4-pipelinecomponentread.gif "第四章第 4 PipelineComponentRead")</span><span class="sxs-lookup"><span data-stu-id="83517-105">![Pipeline Component Read](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")</span></span>  
  
 <span data-ttu-id="83517-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="83517-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="83517-107">**ESB 路线管道组件的示例**</span><span class="sxs-lookup"><span data-stu-id="83517-107">**Example of an ESB Itinerary pipeline component**</span></span>  
  
 <span data-ttu-id="83517-108">ESB 路线管道组件可以用于捕获从消息的元数据作为可以定义 ESB 由应用处理的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="83517-108">An ESB Itinerary pipeline component can be used to capture the metadata from a message as context properties that can define the processing applied by the ESB.</span></span>  
  
 <span data-ttu-id="83517-109">以下各节描述了每个组件执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="83517-109">The following sections describe the steps performed by each component.</span></span>  
  
## <a name="esb-itinerary-pipeline-component-process-steps"></a><span data-ttu-id="83517-110">ESB 路线管道组件过程步骤</span><span class="sxs-lookup"><span data-stu-id="83517-110">ESB Itinerary Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="83517-111">在图 1 所示示例中，ESB 路线管道组件执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="83517-111">In the example shown in Figure 1, the ESB Itinerary pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="83517-112">读取路线 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="83517-112">It reads the itinerary SOAP header.</span></span> <span data-ttu-id="83517-113">正在提交方的时他或她将消息提交将填充的 SOAP 标头设置路线。</span><span class="sxs-lookup"><span data-stu-id="83517-113">The submitting party sets the itinerary by populating the SOAP header when he or she submits the message.</span></span> <span data-ttu-id="83517-114">BizTalk 消息上下文属性的一系列表示 SOAP 标头;这些属性因所使用的 Web 服务适配器的类型而异。</span><span class="sxs-lookup"><span data-stu-id="83517-114">A series of BizTalk message context properties represent the SOAP header; these properties vary, depending on the type of Web service adapter that is used.</span></span> <span data-ttu-id="83517-115">以下是相关的 Web 服务适配器：</span><span class="sxs-lookup"><span data-stu-id="83517-115">The following are the relevant Web service adapters:</span></span>  
  
    -   <span data-ttu-id="83517-116">**WCF 适配器。**</span><span class="sxs-lookup"><span data-stu-id="83517-116">**WCF adapter.**</span></span> <span data-ttu-id="83517-117">此适配器分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="83517-117">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  
  
        |<span data-ttu-id="83517-118">属性</span><span class="sxs-lookup"><span data-stu-id="83517-118">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="83517-119">**名称 = 路线**</span><span class="sxs-lookup"><span data-stu-id="83517-119">**Name = Itinerary**</span></span>|  
        |<span data-ttu-id="83517-120">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**</span><span class="sxs-lookup"><span data-stu-id="83517-120">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="83517-121">默认情况下，Windows Communication Foundation (WCF) 适配器所使用的作为 BizTalk 上下文的名为的 ItineraryDescription.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称**名称**自变量，它作为 BizTalk 上下文使用的架构的目标命名空间和**Namespace**自变量。</span><span class="sxs-lookup"><span data-stu-id="83517-121">By default, the Windows Communication Foundation (WCF) adapter uses the root name of the schema named ItineraryDescription.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the target namespace of the schema as the BizTalk context **Namespace** argument.</span></span>  
  
    -   <span data-ttu-id="83517-122">**SOAP 适配器。**</span><span class="sxs-lookup"><span data-stu-id="83517-122">**SOAP adapter.**</span></span> <span data-ttu-id="83517-123">此适配器分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="83517-123">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  
  
        |<span data-ttu-id="83517-124">属性</span><span class="sxs-lookup"><span data-stu-id="83517-124">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="83517-125">**名称 = 路线**</span><span class="sxs-lookup"><span data-stu-id="83517-125">**Name = Itinerary**</span></span>|  
        |<span data-ttu-id="83517-126">**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**</span><span class="sxs-lookup"><span data-stu-id="83517-126">**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="83517-127">默认情况下，SOAP 适配器所使用的作为 BizTalk 上下文的名为的 Itinerary.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称**名称**自变量，并使用作为 SOAP 头的命名空间BizTalk 上下文**Namespace**自变量。</span><span class="sxs-lookup"><span data-stu-id="83517-127">By default, the SOAP Adapter uses the root name of the schema named Itinerary.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the namespace of the SOAP header as the BizTalk context **Namespace** argument.</span></span>  
  
-   <span data-ttu-id="83517-128">它会从消息上下文中删除原始路线值。</span><span class="sxs-lookup"><span data-stu-id="83517-128">It removes the original itinerary value from the message context.</span></span>  
  
-   <span data-ttu-id="83517-129">它验证路线，并设置要预设默认值，如果它们处于 null 路线; 的特定属性例如：</span><span class="sxs-lookup"><span data-stu-id="83517-129">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  
  
    -   <span data-ttu-id="83517-130">如果服务计数等于或大于 1，组件会引发异常。</span><span class="sxs-lookup"><span data-stu-id="83517-130">If Service count is less than 1, the component throws an exception.</span></span>  
  
    -   <span data-ttu-id="83517-131">该组件设置使用的服务计数，标识符的值的路线根特性 (**Uuid**)、 开始时间 (**BeginTime**)，以及是否这是单向还是双向的请求 (**IsRequestResponse**)。</span><span class="sxs-lookup"><span data-stu-id="83517-131">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  
  
    -   <span data-ttu-id="83517-132">组件验证服务，设置标识符，设置当前服务实例 （使服务能够处理下一步），并验证任何关联的解析程序。</span><span class="sxs-lookup"><span data-stu-id="83517-132">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  
  
    -   <span data-ttu-id="83517-133">该组件设置使用以下属性路线 BizTalk 段：</span><span class="sxs-lookup"><span data-stu-id="83517-133">The component sets the BizTalk Segment of the itinerary using the following properties:</span></span>  
  
        -   <span data-ttu-id="83517-134">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="83517-134">**correlationToken**</span></span>  
  
        -   <span data-ttu-id="83517-135">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="83517-135">**reqRespTransmitPipelineID**</span></span>  
  
        -   <span data-ttu-id="83517-136">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="83517-136">**interchangeId**</span></span>  
  
        -   <span data-ttu-id="83517-137">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="83517-137">**receiveInstanceId**</span></span>  
  
        -   <span data-ttu-id="83517-138">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="83517-138">**epmRRCorrelationToken**</span></span>  
  
    -   <span data-ttu-id="83517-139">组件将写入使用系统 Properties.xsd 架构中定义的属性下表中列出的 BizTalk 消息上下文属性的修改后的路线。</span><span class="sxs-lookup"><span data-stu-id="83517-139">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="83517-140">属性</span><span class="sxs-lookup"><span data-stu-id="83517-140">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="83517-141">**名称 = ItineraryHeader**</span><span class="sxs-lookup"><span data-stu-id="83517-141">**Name = ItineraryHeader**</span></span>|  
        |<span data-ttu-id="83517-142">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span><span class="sxs-lookup"><span data-stu-id="83517-142">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span>|  
  
    -   <span data-ttu-id="83517-143">组件提升下使用系统 Properties.xsd 架构中定义的值的表中列出的四个 BizTalk 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="83517-143">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="83517-144">属性</span><span class="sxs-lookup"><span data-stu-id="83517-144">Property</span></span>|<span data-ttu-id="83517-145">值</span><span class="sxs-lookup"><span data-stu-id="83517-145">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="83517-146">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="83517-146">**ServiceName**</span></span>|<span data-ttu-id="83517-147">定义在路线中的当前服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="83517-147">The name of the current service instance defined in the itinerary.</span></span>|  
        |<span data-ttu-id="83517-148">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="83517-148">**ServiceType**</span></span>|<span data-ttu-id="83517-149">设置为**Orchestration**或**消息传送**</span><span class="sxs-lookup"><span data-stu-id="83517-149">Set to either **Orchestration** or **Messaging**</span></span>|  
        |<span data-ttu-id="83517-150">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="83517-150">**IsRequestResponse**</span></span>|<span data-ttu-id="83517-151">设置为**True**或**False**</span><span class="sxs-lookup"><span data-stu-id="83517-151">Set to either **True** or **False**</span></span>|  
        |<span data-ttu-id="83517-152">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="83517-152">**ServiceState**</span></span>|<span data-ttu-id="83517-153">设置为**挂起**</span><span class="sxs-lookup"><span data-stu-id="83517-153">Set to **Pending**</span></span>|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="83517-154">ESB 调度程序管道组件过程步骤</span><span class="sxs-lookup"><span data-stu-id="83517-154">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="83517-155">在图 1 所示示例中，ESB 调度程序管道组件执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="83517-155">In the example shown in Figure 1, the ESB Dispatcher pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="83517-156">它管理的类型的任何路线步骤执行**消息**并提升路线。</span><span class="sxs-lookup"><span data-stu-id="83517-156">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="83517-157">位置识别并执行逻辑在消息处理周期，可能是根据其位置 ESB 调度程序组件**接收入站，发送传输**，**发送入站**，或**接收出站**。</span><span class="sxs-lookup"><span data-stu-id="83517-157">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound, Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="83517-158">ESB 调度程序管道组件调用路线 ESB Esb.config 文件中指定的消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="83517-158">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="83517-159">默认情况下，此组件用于路由和转换的配置属性是与以下服务：</span><span class="sxs-lookup"><span data-stu-id="83517-159">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  
  
    -   <span data-ttu-id="83517-160">**Microsoft.Practices.ESB.Services.Transform。**</span><span class="sxs-lookup"><span data-stu-id="83517-160">**Microsoft.Practices.ESB.Services.Transform.**</span></span> <span data-ttu-id="83517-161">此服务执行对入站消息的负载的 BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="83517-161">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="83517-162">服务验证转换要求，并更新包含文档的规范名称和消息类型的 BizTalk 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="83517-162">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="83517-163">这是转换服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。</span><span class="sxs-lookup"><span data-stu-id="83517-163">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  
  
    -   <span data-ttu-id="83517-164">**Microsoft.Practices.ESB.Services.Routing。** 此服务使用的解析程序和适配器提供程序框架设置相应的终结点路由信息。</span><span class="sxs-lookup"><span data-stu-id="83517-164">**Microsoft.Practices.ESB.Services.Routing.** This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="83517-165">这是路由服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。</span><span class="sxs-lookup"><span data-stu-id="83517-165">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>