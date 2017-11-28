---
title: "散播-聚集示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ccfacb7-4fd2-4a1a-bece-27eedd86bbe9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1221c038fa2e59636092c5cb49c6cbc40053708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-scatter-gather-sample-works"></a><span data-ttu-id="86918-102">散播-聚集示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="86918-102">How the Scatter-Gather Sample Works</span></span>
<span data-ttu-id="86918-103">示例应用程序生成一组包含从散播-聚集路线文件加载路线的 SOAP 标头、 从磁盘加载指定的消息文件、 将路线标头追加到消息，并将其提交到通过入口为 ESB处理。</span><span class="sxs-lookup"><span data-stu-id="86918-103">The sample application builds a set of SOAP headers containing the itinerary loaded from the Scatter-Gather itinerary file, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an on-ramp for processing.</span></span> <span data-ttu-id="86918-104">如果路线生成响应，应用程序收集此，在应用程序窗口中显示。</span><span class="sxs-lookup"><span data-stu-id="86918-104">If the itinerary generates a response, the application collects this and displays it in the application window.</span></span>  
  
 <span data-ttu-id="86918-105">为了帮助你了解如何路线服务的消息中使用路线的信息，以下列表显示了名为 ScatterGatherItinerary.xml 示例路线的配置文件。</span><span class="sxs-lookup"><span data-stu-id="86918-105">To help you understand how the Itinerary service uses the itinerary information in a message, the following listing shows the sample itinerary configuration file named ScatterGatherItinerary.xml.</span></span> <span data-ttu-id="86918-106">此路线的第一个节指定两个服务调用步骤。</span><span class="sxs-lookup"><span data-stu-id="86918-106">The first section of this itinerary specifies two service invocation steps.</span></span>  
  
```xml  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime=""   
    completeTime="" state="Pending" isRequestResponse="false"   
    xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  <ServiceInstance uuid="" name="ScatterGather" type="Orchestration"  
                   state="Pending" position="0"   
                   isRequestResponse="false" xmlns="" />  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="ScatterGather"  
             type="Orchestration" state="Pending" isRequestResponse="false"  
             position="0" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="DynamicTest"  
             type="Messaging" state="Pending" isRequestResponse="false"  
             position="1" serviceInstanceId="" />  
  </Services>  
</Itinerary>  
...  
```  
  
 <span data-ttu-id="86918-107">该列表后面的服务调用中的步骤路线是包含冲突解决程序和允许找到中路线，定义每个服务，如下面的 XML 中所示路线服务的连接字符串的详细信息的部分。</span><span class="sxs-lookup"><span data-stu-id="86918-107">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers and connection strings that allow the Itinerary service to locate each service defined in the itinerary, as shown in the following XML.</span></span>  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 <span data-ttu-id="86918-108">在此示例中，应用程序执行 SubmitPOService Web 服务，两次，因为两个冲突解决程序连接字符串解析为此服务 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx) 的位置。</span><span class="sxs-lookup"><span data-stu-id="86918-108">In this example, the application executes the SubmitPOService Web service twice because both resolver connection strings resolve to the location of this service (http://localhost/ESB.CanadianServices/SubmitPOService.asmx).</span></span> <span data-ttu-id="86918-109">若要激活，第一个路线服务定义如下所示示例中，消息上下文指定 Broker 业务流程。</span><span class="sxs-lookup"><span data-stu-id="86918-109">The message context specifies the Broker orchestration as the first itinerary service to activate, defined in the sample as the following.</span></span>  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 <span data-ttu-id="86918-110">Broker 业务流程分析其路线步骤的设置，并检索冲突解决程序与路线步骤关联的集合。</span><span class="sxs-lookup"><span data-stu-id="86918-110">The Broker orchestration analyzes the settings for its itinerary step and retrieves a collection of resolvers associated with the itinerary step.</span></span> <span data-ttu-id="86918-111">对于每个这些冲突解决，业务流程使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]用于解决问题的服务终结点的解析程序和适配器框架。</span><span class="sxs-lookup"><span data-stu-id="86918-111">For each of these resolvers, the orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the service endpoint.</span></span> <span data-ttu-id="86918-112">Broker 业务流程然后激活的 ServiceDispatcher 业务流程的 n 数以异步方式 （其中 n 是与路线中的 ScatterGather 服务关联的解析程序数） 来调度请求消息中的使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="86918-112">The Broker orchestration then activates n number of ServiceDispatcher orchestrations asynchronously (where n is the number of resolvers associated with the ScatterGather service in the itinerary) to dispatch the request message with following parameters:</span></span>  
  
-   <span data-ttu-id="86918-113">**TransportLocation**。</span><span class="sxs-lookup"><span data-stu-id="86918-113">**TransportLocation**.</span></span> <span data-ttu-id="86918-114">冲突解决程序填充此参数。</span><span class="sxs-lookup"><span data-stu-id="86918-114">The resolver populates this parameter.</span></span>  
  
-   <span data-ttu-id="86918-115">**TransportType**。</span><span class="sxs-lookup"><span data-stu-id="86918-115">**TransportType**.</span></span> <span data-ttu-id="86918-116">冲突解决程序填充此参数。</span><span class="sxs-lookup"><span data-stu-id="86918-116">The resolver populates this parameter.</span></span>  
  
-   <span data-ttu-id="86918-117">**ResolverDictionary**。</span><span class="sxs-lookup"><span data-stu-id="86918-117">**ResolverDictionary**.</span></span> <span data-ttu-id="86918-118">此参数包含冲突解决程序事实的具体的解析程序实例所填充的集合。</span><span class="sxs-lookup"><span data-stu-id="86918-118">This parameter contains a collection of resolver facts populated by the concrete resolver instance.</span></span>  
  
-   <span data-ttu-id="86918-119">**InboundMessage**。</span><span class="sxs-lookup"><span data-stu-id="86918-119">**InboundMessage**.</span></span> <span data-ttu-id="86918-120">此参数包含包含路线的原始消息。</span><span class="sxs-lookup"><span data-stu-id="86918-120">This parameter contains the original message that contains the itinerary.</span></span>  
  
-   <span data-ttu-id="86918-121">**ServiceResponsePort**。</span><span class="sxs-lookup"><span data-stu-id="86918-121">**ServiceResponsePort**.</span></span> <span data-ttu-id="86918-122">此参数是将收到响应来自 ServiceDispatcher 业务流程的实例的自相关响应端口的名称。</span><span class="sxs-lookup"><span data-stu-id="86918-122">This parameter is the name of the self-correlating response port that will receive responses from the instances of the ServiceDispatcher orchestration.</span></span>  
  
 <span data-ttu-id="86918-123">ServiceDispatcher 业务流程的每个实例使用 ResolveMapScatterGather 策略来请求和响应消息，基于 Microsoft BizTalk 映射类型解析**TransportType**和**TransportLocation**属性。</span><span class="sxs-lookup"><span data-stu-id="86918-123">Each instance of the ServiceDispatcher orchestration uses the ResolveMapScatterGather policy to resolve the Microsoft BizTalk map types for the request and response message, based on **TransportType** and **TransportLocation** properties.</span></span> <span data-ttu-id="86918-124">业务流程实例使用的解析的映射来将入站的消息转换为 Web 服务调用的请求消息。</span><span class="sxs-lookup"><span data-stu-id="86918-124">The orchestration instances use the resolved maps to transform the inbound message into the request message for the Web service call.</span></span>  
  
 <span data-ttu-id="86918-125">ESB 适配器管理器在请求消息中，哪些 BizTalk 然后转发到请求-响应端口将名为 ServiceRequestPort 设置出站传输上下文属性。</span><span class="sxs-lookup"><span data-stu-id="86918-125">The ESB Adapter Manager sets the outbound transport context properties on the request message, which BizTalk then forwards to the solicit-response port named ServiceRequestPort.</span></span>  
  
 <span data-ttu-id="86918-126">当从服务接收到响应消息时，ServiceDispatcher 业务流程将解决的映射信息转换为规范格式的入站的响应消息。</span><span class="sxs-lookup"><span data-stu-id="86918-126">When it receives a response message from a service, the ServiceDispatcher orchestration uses the resolved map information to transform the inbound response message to a canonical format.</span></span> <span data-ttu-id="86918-127">然后内 ServiceResponse 信封换行的修改后的响应，并将其转发到 Broker 业务流程通过自助关联的端口。</span><span class="sxs-lookup"><span data-stu-id="86918-127">It then wraps the modified response within the ServiceResponse envelope and forwards it to the Broker orchestration through the self-correlating port.</span></span> <span data-ttu-id="86918-128">Broker 业务流程聚合所有传入的响应，并准备使用 GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline，最终响应消息，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="86918-128">The Broker orchestration aggregates all incoming responses and prepares the final response message using GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline, as shown in the following code.</span></span>  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 <span data-ttu-id="86918-129">此代码包装在预定义信封内整个批处理的响应。</span><span class="sxs-lookup"><span data-stu-id="86918-129">This code wraps the entire batch of responses within a predefined envelope.</span></span> <span data-ttu-id="86918-130">Broker 业务流程然后前进到路线**DynamicTest**路线步骤中，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="86918-130">The Broker orchestration then advances the itinerary to the **DynamicTest** itinerary step, as shown in the following code.</span></span>  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 <span data-ttu-id="86918-131">因为名为的服务类型属性**DynamicTest**设置为**消息**、 **ItineraryHelper**类将冲突解决程序属性提升到的上下文名为消息**OutboundMessage**。</span><span class="sxs-lookup"><span data-stu-id="86918-131">Because the service type attribute named **DynamicTest** is set to **Messaging**, the **ItineraryHelper** class promotes the resolver properties into the context of the message named **OutboundMessage**.</span></span> <span data-ttu-id="86918-132">Broker 业务流程将此消息发送到 BizTalk 直接绑定的端口。</span><span class="sxs-lookup"><span data-stu-id="86918-132">The Broker orchestration sends this message to a BizTalk direct-bound port.</span></span> <span data-ttu-id="86918-133">BizTalk 随后将转发到由动态发送端口消息**ServiceName**订阅，这是**DynamicTest**。</span><span class="sxs-lookup"><span data-stu-id="86918-133">BizTalk then forwards the message to the dynamic send port represented by the **ServiceName** subscription, which is **DynamicTest**.</span></span> <span data-ttu-id="86918-134">此发送端口将最终聚合的响应 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹进行序列化。</span><span class="sxs-lookup"><span data-stu-id="86918-134">This send port serializes the final aggregated response to the \Source\Samples\DynamicResolution\Test\Filedrop\Out folder.</span></span>