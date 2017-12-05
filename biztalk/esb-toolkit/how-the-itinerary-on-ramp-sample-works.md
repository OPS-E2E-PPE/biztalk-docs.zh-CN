---
title: "路线上负载增加示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f4f318c-b955-4a3d-88db-c0d324b63b21
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b73b4379944db548a30898403239ffcf9704791a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-the-itinerary-on-ramp-sample-works"></a>路线上负载增加示例的工作原理
该示例路线测试客户端应用程序生成一组包含你在客户端应用程序窗口中，使用控件创建路线的 SOAP 标头从磁盘加载指定的消息文件、 将路线标头追加到消息、 和将其提交到 ESB 通过路线入口进行处理。 如果路线生成响应，应用程序收集响应，并将其显示在应用程序窗口。  
  
 你可以选择从多个示例路线的配置文件，请参阅使用业务流程、 消息或两者的组合的单向和双向方案。  
  
 为了帮助你了解如何路线服务的消息中使用路线的信息，下面的 XML 演示指定 TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml 前面示例中使用的示例路线的配置文件。 此路线的第一个节指定三个服务调用步骤。  
  
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
  
 该列表后面的服务调用中的步骤路线是包含 （由连接字符串） 的解析程序，允许路线服务以查找或提供每个服务中定义的解决方法信息的详细信息的部分路线。  
  
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
>  每个的实际内容**\<冲突解决程序\>**元素不包含使用在前面的列表中将行的空白字符。  
  
 以下是在路线前面的配置中定义的三个步骤：  
  
1.  执行 Microsoft.Practices.ESB.Services.Transform 业务流程将消息转换与使用 BizTalk 业务规则引擎 (BRE) ResolverMap 策略。  
  
2.  执行 Microsoft.Practices.ESB.Services.Routing 业务流程将已转换的消息路由到多个位置使用路由 Microsoft.Practices.ESB.Services.Routing1。  **\<ResolverGroups\>** 部分包含**\<冲突解决程序\>**标识符，用于定义连接字符串的元素。  
  
3.  执行本示例提供 ProcessAndRespond 业务流程。 作为响应发送此业务流程的实现回路线测试客户端的请求消息的副本。  
  
 与每个服务完成时，服务提升路线，并将该路线为当前服务实例，其状态设置为与中定义的下一步服务提升**挂起**。  
  
> [!NOTE]
>  路线入口示例使用动态解析将消息发送到输出文件夹。 这是为什么没有不静态发送端口为此示例定义。  
  
 以下是测试客户端应用程序提交消息后会发生的事件的顺序：  
  
-   OnRamp.Itinerary 接收端口接收消息。  
  
-   ItineraryReceiveXml 管道从 SOAP 标头中提取路线、 验证和预先对其进行处理，将路线作为消息上下文属性写入到入站消息，和将消息发布到 BizTalk 消息框数据库。  
  
-   Microsoft.Practices.ESB.Services.Transform 服务业务流程的订阅将触发此业务流程的调用。 业务流程首先检索当前路线步骤，通过将当前的消息传递作为参数，如下面的代码中所示。  
  
    ```csharp  
    itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
    ```  
  
-   **ItineraryStep**对象包含有关执行的当前服务实例的所有信息以及与之关联的任何冲突解决程序。  
  
-   **冲突解决程序**对象检索从**ItineraryStep**实例和 ESB 冲突解决程序框架用于解析的完整名称的转换映射，如下面的代码中所示。  
  
    ```csharp  
    resolverDictionary =   
       Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                            resolver);  
  
    // Set the transform type.  
    transformType = resolverDictionary.Item("Resolver.TransformType");  
    ```  
  
-   [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器框架通过实现此功能通过从缓存 （在此示例中，由 BizTalk 业务规则引擎冲突解决程序），也不能调用 ResolverMap 策略填充加载相应的冲突解决程序来**ResolverDictionary**对象。  
  
-   业务流程完成之后，该代码调用**AdvanceItinerary**方法，如下面的代码中所示。  
  
    ```csharp  
    // Call the Itinerary helper to advance to the next step.  
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
-   这可以通过更新其属性并将在路线中定义为一个后，接下来要执行的下一个服务提升推进当前路线。 该方法将路线复制到出站消息，该服务发布回消息框数据库通过直接绑定发送端口。  
  
-   Microsoft.Practices.ESB.Services.Delivery 服务业务流程的订阅将触发此业务流程的调用。 此业务流程到第一个，获取当前的路线步骤遵循类似的过程。 但是，此业务流程循环访问冲突解决程序返回的集合**ItineraryStep**实例。 集合中的每个冲突解决程序，对于交付业务流程使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器框架来解析传输位置并将它们提升为在传出消息中，上下文属性，如下面的代码中所示。  
  
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
  
-   ProcessAndRespond 业务流程的订阅将触发此业务流程的调用由于消息上下文属性为筛选器表达式属性定义的匹配项。  
  
    ```  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
    && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
    ```  
  
-   ProcessAndRespond 业务流程提升路线，并将原始请求消息发送回响应路线测试客户端应用程序的入口服务。