---
title: 使用管道组件读取路线 |Microsoft Docs
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
ms.openlocfilehash: 153f99e68e2c2457db44998b6c955c02af73a6c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396497"
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a><span data-ttu-id="b15e0-102">使用管道组件读取路线</span><span class="sxs-lookup"><span data-stu-id="b15e0-102">Using a Pipeline Component to Read an Itinerary</span></span>
<span data-ttu-id="b15e0-103">在接收管道中的消息可以包含其定义其处理要求 （客户端的路线） 的 SOAP 标头中的元数据。</span><span class="sxs-lookup"><span data-stu-id="b15e0-103">A message that arrives in a receive pipeline can contain metadata in its SOAP header that defines its processing requirements (client-side itinerary).</span></span> <span data-ttu-id="b15e0-104">图 1 说明了使用 ESB 路线和 ESB 调度程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="b15e0-104">Figure 1 illustrates the use of the ESB Itinerary and ESB Dispatcher pipeline components.</span></span>  

 <span data-ttu-id="b15e0-105">![管道组件读取](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")</span><span class="sxs-lookup"><span data-stu-id="b15e0-105">![Pipeline Component Read](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")</span></span>  

 <span data-ttu-id="b15e0-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="b15e0-106">**Figure 1**</span></span>  

 <span data-ttu-id="b15e0-107">**ESB 路线管道组件的示例**</span><span class="sxs-lookup"><span data-stu-id="b15e0-107">**Example of an ESB Itinerary pipeline component**</span></span>  

 <span data-ttu-id="b15e0-108">ESB 路线管道组件可用于为上下文属性，可以定义应用的 ESB 处理捕获的元数据的一条消息。</span><span class="sxs-lookup"><span data-stu-id="b15e0-108">An ESB Itinerary pipeline component can be used to capture the metadata from a message as context properties that can define the processing applied by the ESB.</span></span>  

 <span data-ttu-id="b15e0-109">以下部分介绍每个组件执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="b15e0-109">The following sections describe the steps performed by each component.</span></span>  

## <a name="esb-itinerary-pipeline-component-process-steps"></a><span data-ttu-id="b15e0-110">ESB 路线管道组件处理步骤</span><span class="sxs-lookup"><span data-stu-id="b15e0-110">ESB Itinerary Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="b15e0-111">在图 1 所示示例中，ESB 路线管道组件执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b15e0-111">In the example shown in Figure 1, the ESB Itinerary pipeline component executes the following steps:</span></span>  

- <span data-ttu-id="b15e0-112">它会读取路线 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="b15e0-112">It reads the itinerary SOAP header.</span></span> <span data-ttu-id="b15e0-113">提交的参与方的时他或她将消息提交将填充 SOAP 标头来设置路线。</span><span class="sxs-lookup"><span data-stu-id="b15e0-113">The submitting party sets the itinerary by populating the SOAP header when he or she submits the message.</span></span> <span data-ttu-id="b15e0-114">BizTalk 消息上下文属性的一系列表示 SOAP 标头;这些属性会有所不同，具体取决于所使用的 Web 服务适配器类型。</span><span class="sxs-lookup"><span data-stu-id="b15e0-114">A series of BizTalk message context properties represent the SOAP header; these properties vary, depending on the type of Web service adapter that is used.</span></span> <span data-ttu-id="b15e0-115">以下是相关的 Web 服务适配器：</span><span class="sxs-lookup"><span data-stu-id="b15e0-115">The following are the relevant Web service adapters:</span></span>  

  - <span data-ttu-id="b15e0-116">**WCF 适配器。**</span><span class="sxs-lookup"><span data-stu-id="b15e0-116">**WCF adapter.**</span></span> <span data-ttu-id="b15e0-117">此适配器将分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b15e0-117">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  


    |                                  <span data-ttu-id="b15e0-118">属性</span><span class="sxs-lookup"><span data-stu-id="b15e0-118">Properties</span></span>                                  |
    |------------------------------------------------------------------------------|
    |                             <span data-ttu-id="b15e0-119">**名称 = 路线**</span><span class="sxs-lookup"><span data-stu-id="b15e0-119">**Name = Itinerary**</span></span>                             |
    | <span data-ttu-id="b15e0-120">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**</span><span class="sxs-lookup"><span data-stu-id="b15e0-120">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**</span></span> |

    > [!NOTE]
    >  <span data-ttu-id="b15e0-121">默认情况下，Windows Communication Foundation (WCF) 适配器使用名为的 ItineraryDescription.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称作为 BizTalk 上下文**名称**参数，并作为 BizTalk 上下文使用的架构的目标命名空间**Namespace**参数。</span><span class="sxs-lookup"><span data-stu-id="b15e0-121">By default, the Windows Communication Foundation (WCF) adapter uses the root name of the schema named ItineraryDescription.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the target namespace of the schema as the BizTalk context **Namespace** argument.</span></span>  

  - <span data-ttu-id="b15e0-122">**SOAP 适配器。**</span><span class="sxs-lookup"><span data-stu-id="b15e0-122">**SOAP adapter.**</span></span> <span data-ttu-id="b15e0-123">此适配器将分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b15e0-123">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  


    |                              <span data-ttu-id="b15e0-124">属性</span><span class="sxs-lookup"><span data-stu-id="b15e0-124">Properties</span></span>                              |
    |----------------------------------------------------------------------|
    |                         <span data-ttu-id="b15e0-125">**名称 = 路线**</span><span class="sxs-lookup"><span data-stu-id="b15e0-125">**Name = Itinerary**</span></span>                         |
    | <span data-ttu-id="b15e0-126">**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**</span><span class="sxs-lookup"><span data-stu-id="b15e0-126">**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**</span></span> |

    > [!NOTE]
    >  <span data-ttu-id="b15e0-127">默认情况下，SOAP 适配器使用名为的 Itinerary.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称作为 BizTalk 上下文**名称**参数，并使用作为 SOAP 标头的命名空间BizTalk 上下文**Namespace**参数。</span><span class="sxs-lookup"><span data-stu-id="b15e0-127">By default, the SOAP Adapter uses the root name of the schema named Itinerary.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the namespace of the SOAP header as the BizTalk context **Namespace** argument.</span></span>  

- <span data-ttu-id="b15e0-128">它从消息上下文中删除原始的路线值。</span><span class="sxs-lookup"><span data-stu-id="b15e0-128">It removes the original itinerary value from the message context.</span></span>  

- <span data-ttu-id="b15e0-129">它验证路线并设置特定属性来预设的默认值，如果它们处于 null 路线;例如：</span><span class="sxs-lookup"><span data-stu-id="b15e0-129">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  

  - <span data-ttu-id="b15e0-130">如果服务计数小于 1，组件会引发异常。</span><span class="sxs-lookup"><span data-stu-id="b15e0-130">If Service count is less than 1, the component throws an exception.</span></span>  

  - <span data-ttu-id="b15e0-131">该组件设置使用的服务计数，该标识符的值的路线根属性 (**Uuid**)、 开始时间 (**BeginTime**)，以及是否这是单向还是双向的请求 (**IsRequestResponse**)。</span><span class="sxs-lookup"><span data-stu-id="b15e0-131">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  

  - <span data-ttu-id="b15e0-132">该组件验证服务，设置的标识符，设置当前服务实例 （服务才能处理下一步），并验证任何关联的冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="b15e0-132">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  

  - <span data-ttu-id="b15e0-133">该组件设置 BizTalk 段的路线使用以下属性：</span><span class="sxs-lookup"><span data-stu-id="b15e0-133">The component sets the BizTalk Segment of the itinerary using the following properties:</span></span>  

    -   <span data-ttu-id="b15e0-134">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="b15e0-134">**correlationToken**</span></span>  

    -   <span data-ttu-id="b15e0-135">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="b15e0-135">**reqRespTransmitPipelineID**</span></span>  

    -   <span data-ttu-id="b15e0-136">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="b15e0-136">**interchangeId**</span></span>  

    -   <span data-ttu-id="b15e0-137">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="b15e0-137">**receiveInstanceId**</span></span>  

    -   <span data-ttu-id="b15e0-138">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="b15e0-138">**epmRRCorrelationToken**</span></span>  

  - <span data-ttu-id="b15e0-139">该组件将修改后的旅行计划写入到下使用系统 Properties.xsd 架构中定义的属性的表中列出的 BizTalk 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b15e0-139">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  


    |                                           <span data-ttu-id="b15e0-140">属性</span><span class="sxs-lookup"><span data-stu-id="b15e0-140">Properties</span></span>                                           |
    |------------------------------------------------------------------------------------------------|
    |                                   <span data-ttu-id="b15e0-141">**名称 = ItineraryHeader**</span><span class="sxs-lookup"><span data-stu-id="b15e0-141">**Name = ItineraryHeader**</span></span>                                   |
    | <span data-ttu-id="b15e0-142">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span><span class="sxs-lookup"><span data-stu-id="b15e0-142">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span> |


  - <span data-ttu-id="b15e0-143">组件会升级系统 Properties.xsd 架构中定义的值使用下表中列出的四个 BizTalk 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b15e0-143">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  

    |<span data-ttu-id="b15e0-144">属性</span><span class="sxs-lookup"><span data-stu-id="b15e0-144">Property</span></span>|<span data-ttu-id="b15e0-145">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b15e0-145">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="b15e0-146">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="b15e0-146">**ServiceName**</span></span>|<span data-ttu-id="b15e0-147">在路线中定义的当前服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b15e0-147">The name of the current service instance defined in the itinerary.</span></span>|  
    |<span data-ttu-id="b15e0-148">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="b15e0-148">**ServiceType**</span></span>|<span data-ttu-id="b15e0-149">设置为**业务流程**或**消息传送**</span><span class="sxs-lookup"><span data-stu-id="b15e0-149">Set to either **Orchestration** or **Messaging**</span></span>|  
    |<span data-ttu-id="b15e0-150">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="b15e0-150">**IsRequestResponse**</span></span>|<span data-ttu-id="b15e0-151">设置为 **，则返回 True**或**False**</span><span class="sxs-lookup"><span data-stu-id="b15e0-151">Set to either **True** or **False**</span></span>|  
    |<span data-ttu-id="b15e0-152">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="b15e0-152">**ServiceState**</span></span>|<span data-ttu-id="b15e0-153">设置为**挂起**</span><span class="sxs-lookup"><span data-stu-id="b15e0-153">Set to **Pending**</span></span>|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="b15e0-154">ESB 调度程序管道组件处理步骤</span><span class="sxs-lookup"><span data-stu-id="b15e0-154">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="b15e0-155">在图 1 所示示例中，ESB 调度程序管道组件执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b15e0-155">In the example shown in Figure 1, the ESB Dispatcher pipeline component executes the following steps:</span></span>  

- <span data-ttu-id="b15e0-156">它管理的类型的任何路线步骤执行**Messaging** ，并将提升路线。</span><span class="sxs-lookup"><span data-stu-id="b15e0-156">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="b15e0-157">ESB 调度程序组件是位置感知，执行消息传送处理周期，可能是根据其位置的逻辑**接收的入站、 发送传输**，**发送入站**，或**接收出站**。</span><span class="sxs-lookup"><span data-stu-id="b15e0-157">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound, Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="b15e0-158">ESB 调度程序管道组件调用 ESB 路线消息传递服务 Esb.config 文件中指定。</span><span class="sxs-lookup"><span data-stu-id="b15e0-158">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="b15e0-159">默认情况下，此组件用于路由和转换的配置属性相关联与以下服务：</span><span class="sxs-lookup"><span data-stu-id="b15e0-159">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  

  - <span data-ttu-id="b15e0-160">**Microsoft.Practices.ESB.Services.Transform.**</span><span class="sxs-lookup"><span data-stu-id="b15e0-160">**Microsoft.Practices.ESB.Services.Transform.**</span></span> <span data-ttu-id="b15e0-161">此服务执行针对入站消息的负载的 BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="b15e0-161">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="b15e0-162">服务验证转换要求并更新包含该文档规范名称和消息类型的 BizTalk 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b15e0-162">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="b15e0-163">ESB 调度程序管道组件的相应属性中所示，这是转换服务的名称，ESB 调度程序就会执行此服务。</span><span class="sxs-lookup"><span data-stu-id="b15e0-163">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  

  - <span data-ttu-id="b15e0-164"><strong>Microsoft.Practices.ESB.Services.Routing。</strong>此服务使用的冲突解决程序和适配器提供程序框架设置相应的终结点路由信息。</span><span class="sxs-lookup"><span data-stu-id="b15e0-164"><strong>Microsoft.Practices.ESB.Services.Routing.</strong>This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="b15e0-165">ESB 调度程序管道组件的相应属性中所示，这是路由服务的名称，ESB 调度程序就会执行此服务。</span><span class="sxs-lookup"><span data-stu-id="b15e0-165">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>
