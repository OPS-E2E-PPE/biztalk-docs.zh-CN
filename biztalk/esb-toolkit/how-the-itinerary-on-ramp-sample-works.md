---
title: 路线接入点示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f4f318c-b955-4a3d-88db-c0d324b63b21
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f282e49b8095059b273bd737d6fb38ff97090f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966062"
---
# <a name="how-the-itinerary-on-ramp-sample-works"></a><span data-ttu-id="d6996-102">路线接入点示例工作原理</span><span class="sxs-lookup"><span data-stu-id="d6996-102">How the Itinerary On-Ramp Sample Works</span></span>
<span data-ttu-id="d6996-103">示例路线测试客户端应用程序生成的 SOAP 标头包含在客户端应用程序窗口中，使用控件创建路线的一组从磁盘加载指定的消息文件、 路线标头附加到消息，并将其提交给 ESB 通过路线接入点进行处理。</span><span class="sxs-lookup"><span data-stu-id="d6996-103">The sample Itinerary Test Client application builds a set of SOAP headers that contain the itinerary that you create using the controls in the client application window, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an Itinerary on-ramp for processing.</span></span> <span data-ttu-id="d6996-104">如果路线时都生成响应，应用程序收集响应，并将其显示在应用程序窗口。</span><span class="sxs-lookup"><span data-stu-id="d6996-104">If the itinerary generates a response, the application collects the response and displays it in the application window.</span></span>  

 <span data-ttu-id="d6996-105">您可以选择从多个示例路线的配置文件以单向和双向的方案，请使用业务流程、 消息传递，或这两者的组合。</span><span class="sxs-lookup"><span data-stu-id="d6996-105">You can choose from several sample itinerary configuration files to see one-way and two-way scenarios that use orchestrations, messaging, or a combination of both.</span></span>  

 <span data-ttu-id="d6996-106">为了帮助你了解路线服务如何使用消息中的路线的信息，以下 XML 显示了名为 TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml 在前面的示例中使用的示例路线的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d6996-106">To help you understand how the Itinerary service uses the itinerary information in a message, the following XML shows the sample itinerary configuration file named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml used in the earlier example.</span></span> <span data-ttu-id="d6996-107">此路线的第一个部分指定三个服务调用步骤。</span><span class="sxs-lookup"><span data-stu-id="d6996-107">The first section of this itinerary specifies three service invocation steps.</span></span>  

```xml  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime="" completeTime="" state="Pending" isRequestResponse="false" servicecount="0" xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  <BizTalkSegment interchangeId="" epmRRCorrelationToken="" receiveInstanceId="" messageId="" xmlns="" />  
  <ServiceInstance name="Microsoft.Practices.ESB.Services.Transform" type="Orchestration" state="Pending" position="0" isRequestResponse="false" xmlns="" />  
  <Services xmlns="">  
    <Service uuid="92d3b293-e6d4-44a1-b27d-c42b48aec667" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Transform" type="Orchestration" state="Pending" isRequestResponse="false" position="0" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="774488bc-e5b9-4a4e-9ae7-d25cdf23fd1c" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Routing" type="Orchestration" state="Pending" isRequestResponse="false" position="1" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="ProcessAndRespond" type="Orchestration" state="Pending" isRequestResponse="true" position="2" serviceInstanceId="" />  
  </Services>  
  ...  
```  

 <span data-ttu-id="d6996-108">该列表后面的服务调用中的步骤路线是部分，其中包含的 （由连接字符串） 的解析程序，允许路线服务，以便查找或提供每个服务中定义的解决方法信息的详细信息路线。</span><span class="sxs-lookup"><span data-stu-id="d6996-108">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers (represented by connection strings) that allow the Itinerary service to locate or provide resolution information for each service defined in the itinerary.</span></span>  

```xml  
  ...  
<ResolverGroups xmlns="">  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Transform0"><![CDATA[BRE:\\Policy=ResolveMap;Version=1.0;UseMsg=False;]]></Resolvers>  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Routing1"><![CDATA[STATIC:\\TransportType=FILE;TransportLocation=C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml;Action=;EndpointConfig=;JaxRpcResponse=False;MessageExchangePattern=;TargetNamespace=;TransformType=;]]><![CDATA[UDDI3:\\ServerUrl=http://localhost/uddi;SearchQualifiers=andAllKeys;CategorySearch=;BindingKey=uddi:esb:orderfileservicev3.1;]]></Resolvers>  
    <Resolvers serviceId="ProcessAndRespond2" />  
  </ResolverGroups>  
</Itinerary>  
```  

> [!NOTE]
>  <span data-ttu-id="d6996-109">每个的实际内容**\<冲突解决程序\>** 元素不包含用于在上述列表中换行空格字符。</span><span class="sxs-lookup"><span data-stu-id="d6996-109">The actual content of each **\<Resolvers\>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  

 <span data-ttu-id="d6996-110">在路线前述配置中定义的三个步骤如下：</span><span class="sxs-lookup"><span data-stu-id="d6996-110">The following are the three steps defined in the itinerary preceding configuration:</span></span>  

1. <span data-ttu-id="d6996-111">执行 Microsoft.Practices.ESB.Services.Transform 业务流程将消息转换与 ResolverMap 策略使用 BizTalk 业务规则引擎 (BRE)。</span><span class="sxs-lookup"><span data-stu-id="d6996-111">Execute the Microsoft.Practices.ESB.Services.Transform orchestration to transform the message with the ResolverMap policy using BizTalk Business Rules Engine (BRE).</span></span>  

2. <span data-ttu-id="d6996-112">执行用于将转换后的消息路由到多个位置使用路由 Microsoft.Practices.ESB.Services.Routing1 Microsoft.Practices.ESB.Services.Routing 业务流程。</span><span class="sxs-lookup"><span data-stu-id="d6996-112">Execute the Microsoft.Practices.ESB.Services.Routing orchestration to route the transformed message to multiple locations using the routing Microsoft.Practices.ESB.Services.Routing1.</span></span> <span data-ttu-id="d6996-113">**\<ResolverGroups\>** 部分包含**\<冲突解决程序\>** 标识符，用于定义连接字符串的元素。</span><span class="sxs-lookup"><span data-stu-id="d6996-113">The **\<ResolverGroups\>** section contains a **\<Resolvers\>** element with this identifier, which defines the connection strings.</span></span>  

3. <span data-ttu-id="d6996-114">执行此示例随附的 ProcessAndRespond 业务流程。</span><span class="sxs-lookup"><span data-stu-id="d6996-114">Execute the ProcessAndRespond orchestration provided with this sample.</span></span> <span data-ttu-id="d6996-115">作为响应发送此业务流程的实现返回给路线测试客户端请求消息的副本。</span><span class="sxs-lookup"><span data-stu-id="d6996-115">The implementation of this orchestration sends as the response a copy of the request message back to the Itinerary Test Client.</span></span>  

   <span data-ttu-id="d6996-116">与每个服务完成时，服务将推进路线，并将升级路线为当前服务实例，其状态设置为与中定义的下一个服务**挂起**。</span><span class="sxs-lookup"><span data-stu-id="d6996-116">With the completion of each service, the service advances the itinerary and promotes the next service defined in the itinerary to be the current service instance, with its state set to **Pending**.</span></span>  

> [!NOTE]
>  <span data-ttu-id="d6996-117">路线接入点示例使用动态解析将消息发送到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="d6996-117">The Itinerary On-Ramp sample uses dynamic resolution to send messages to the output folder.</span></span> <span data-ttu-id="d6996-118">这是原因不静态发送端口定义为本示例。</span><span class="sxs-lookup"><span data-stu-id="d6996-118">This is why there is no static send port defined for this sample.</span></span>  

 <span data-ttu-id="d6996-119">以下是测试客户端应用程序将消息提交后发生的事件序列：</span><span class="sxs-lookup"><span data-stu-id="d6996-119">The following is the sequence of events that occur after the test client application submits the message:</span></span>  

- <span data-ttu-id="d6996-120">OnRamp.Itinerary 接收端口接收的消息。</span><span class="sxs-lookup"><span data-stu-id="d6996-120">The OnRamp.Itinerary receive port receives the message.</span></span>  

- <span data-ttu-id="d6996-121">ItineraryReceiveXml 管道从 SOAP 标头中提取路线、 验证和预先对其进行处理，将路线为消息上下文属性写入到入站消息，并将消息发布到 BizTalk Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="d6996-121">The ItineraryReceiveXml pipeline extracts the itinerary from the SOAP header, validates and pre-processes it, writes the itinerary as a message context property into the inbound message, and publishes the message to the BizTalk Message Box database.</span></span>  

- <span data-ttu-id="d6996-122">Microsoft.Practices.ESB.Services.Transform 服务业务流程的订阅就会触发此业务流程的调用。</span><span class="sxs-lookup"><span data-stu-id="d6996-122">A subscription for the Microsoft.Practices.ESB.Services.Transform service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="d6996-123">业务流程首先检索当前的行程步骤通过将当前的消息传递作为参数，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="d6996-123">The orchestration first retrieves the current itinerary step by passing the current message as a parameter, as shown in the following code.</span></span>  

  ```csharp  
  itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  ```  

- <span data-ttu-id="d6996-124">**ItineraryStep**对象包含有关当前服务实例的执行，所有的信息以及与之关联的任何冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="d6996-124">The **ItineraryStep** object contains all the information about the current service instance for execution, as well as any resolvers associated with it.</span></span>  

- <span data-ttu-id="d6996-125">**冲突解决程序**对象从检索**ItineraryStep**实例和 ESB 解析程序框架用于解析的完整名称的转换映射，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="d6996-125">The **Resolver** object is retrieved from the **ItineraryStep** instance and the ESB Resolver Framework is used to resolve the full name of the transformation map, as shown in the following code.</span></span>  

  ```csharp  
  resolverDictionary =   
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transform type.  
  transformType = resolverDictionary.Item("Resolver.TransformType");  
  ```  

- <span data-ttu-id="d6996-126">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器框架来实现此功能通过加载相应的解析程序缓存中 （在此示例中，BizTalk 业务规则引擎冲突解决程序），这样调用 ResolverMap 策略并填充**ResolverDictionary**对象。</span><span class="sxs-lookup"><span data-stu-id="d6996-126">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework accomplishes this by loading the appropriate resolver from the cache (in this example, the BizTalk Business Rules Engine resolver), which invokes the ResolverMap policy and populates the **ResolverDictionary** object.</span></span>  

- <span data-ttu-id="d6996-127">业务流程完成后，该代码调用**AdvanceItinerary**方法，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="d6996-127">After the orchestration completes, the code calls the **AdvanceItinerary** method, as shown in the following code.</span></span>  

  ```csharp  
  // Call the Itinerary helper to advance to the next step.  
  itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
  ```  

- <span data-ttu-id="d6996-128">这通过更新其属性以及将提升在路线中定义为一个接下来要执行的下一个服务，改进了当前的路线。</span><span class="sxs-lookup"><span data-stu-id="d6996-128">This advances the current itinerary by updating its properties and promoting the next service defined in the itinerary as the one to execute next.</span></span> <span data-ttu-id="d6996-129">该方法将路线复制到该服务会发布回 Messagebox 数据库通过直接绑定的发送端口的出站消息。</span><span class="sxs-lookup"><span data-stu-id="d6996-129">The method copies the itinerary into the outbound message, which the service publishes back into the Message Box database through a direct-bound send port.</span></span>  

- <span data-ttu-id="d6996-130">Microsoft.Practices.ESB.Services.Delivery 服务业务流程的订阅就会触发此业务流程的调用。</span><span class="sxs-lookup"><span data-stu-id="d6996-130">A subscription for the Microsoft.Practices.ESB.Services.Delivery service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="d6996-131">此业务流程到第一个，获取当前的行程步骤遵循类似的过程。</span><span class="sxs-lookup"><span data-stu-id="d6996-131">This orchestration follows a similar process to the first one, obtaining the current Itinerary step.</span></span> <span data-ttu-id="d6996-132">但是，此业务流程循环访问返回的冲突解决程序的集合**ItineraryStep**实例。</span><span class="sxs-lookup"><span data-stu-id="d6996-132">However, this orchestration iterates through a collection of resolvers returned by the **ItineraryStep** instance.</span></span> <span data-ttu-id="d6996-133">对于集合中的每个冲突解决程序，交付业务流程使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器框架来解析传输位置并将它们提升为传出消息中的上下文属性，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="d6996-133">For each resolver in the collection, the delivery orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the transport locations and promote them as context properties within the outgoing message, as shown in the following code.</span></span>  

  ```csharp  
  // Move to retrieve the first resolver.  
  resolver = resolvers.Current;  

  // Pass the resolver configuration to the Resolver Manager   
  // for resolution.  
  resolverDictionary =  
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transport properties.  
  transportLocation =   
     resolverDictionary.Item("Resolver.TransportLocation");  
  transportType =   
     resolverDictionary.Item("Resolver.TransportType");  

  // Call the Adapter Manager to set all necessary properties.  
  Microsoft.Practices.ESB.Adapter.AdapterMgr.SetEndpoint(  
                                  resolverDictionary, DeliveryMessage);  

  // Set the delivery port address and type.  
  DeliveryPort(Microsoft.XLANGs.BaseTypes.Address) = transportLocation;  
  DeliveryPort(Microsoft.XLANGs.BaseTypes.TransportType) = transportType;  
  ```  

- <span data-ttu-id="d6996-134">ProcessAndRespond 业务流程的订阅会触发此业务流程的调用由于为筛选器表达式属性定义的消息上下文属性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d6996-134">A subscription for the ProcessAndRespond orchestration triggers invocation of this orchestration because of a match of the message context properties defined for the filter expression properties.</span></span>  

  ```  
  (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
  && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
  && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
  ```  

- <span data-ttu-id="d6996-135">ProcessAndRespond 业务流程将推进路线，并将原始请求消息发送回给路线测试客户端应用程序作为响应的接入点服务。</span><span class="sxs-lookup"><span data-stu-id="d6996-135">The ProcessAndRespond orchestration advances the itinerary and sends the original request message back to the on-ramp service to the Itinerary Test Client application as the response.</span></span>
