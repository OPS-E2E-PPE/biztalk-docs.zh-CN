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
ms.openlocfilehash: 4f52d8442f777d67b31b99c4fef336d6a5e71f60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400775"
---
# <a name="how-the-itinerary-on-ramp-sample-works"></a>路线接入点示例工作原理
示例路线测试客户端应用程序生成的 SOAP 标头包含在客户端应用程序窗口中，使用控件创建路线的一组从磁盘加载指定的消息文件、 路线标头附加到消息，并将其提交给 ESB 通过路线接入点进行处理。 如果路线时都生成响应，应用程序收集响应，并将其显示在应用程序窗口。  

 您可以选择从多个示例路线的配置文件以单向和双向的方案，请使用业务流程、 消息传递，或这两者的组合。  

 为了帮助你了解路线服务如何使用消息中的路线的信息，以下 XML 显示了名为 TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml 在前面的示例中使用的示例路线的配置文件。 此路线的第一个部分指定三个服务调用步骤。  

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

 该列表后面的服务调用中的步骤路线是部分，其中包含的 （由连接字符串） 的解析程序，允许路线服务，以便查找或提供每个服务中定义的解决方法信息的详细信息路线。  

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
>  每个的实际内容**\<冲突解决程序\>** 元素不包含用于在上述列表中换行空格字符。  

 在路线前述配置中定义的三个步骤如下：  

1. 执行 Microsoft.Practices.ESB.Services.Transform 业务流程将消息转换与 ResolverMap 策略使用 BizTalk 业务规则引擎 (BRE)。  

2. 执行用于将转换后的消息路由到多个位置使用路由 Microsoft.Practices.ESB.Services.Routing1 Microsoft.Practices.ESB.Services.Routing 业务流程。 **\<ResolverGroups\>** 部分包含**\<冲突解决程序\>** 标识符，用于定义连接字符串的元素。  

3. 执行此示例随附的 ProcessAndRespond 业务流程。 作为响应发送此业务流程的实现返回给路线测试客户端请求消息的副本。  

   与每个服务完成时，服务将推进路线，并将升级路线为当前服务实例，其状态设置为与中定义的下一个服务**挂起**。  

> [!NOTE]
>  路线接入点示例使用动态解析将消息发送到输出文件夹。 这是原因不静态发送端口定义为本示例。  

 以下是测试客户端应用程序将消息提交后发生的事件序列：  

- OnRamp.Itinerary 接收端口接收的消息。  

- ItineraryReceiveXml 管道从 SOAP 标头中提取路线、 验证和预先对其进行处理，将路线为消息上下文属性写入到入站消息，并将消息发布到 BizTalk Messagebox 数据库。  

- Microsoft.Practices.ESB.Services.Transform 服务业务流程的订阅就会触发此业务流程的调用。 业务流程首先检索当前的行程步骤通过将当前的消息传递作为参数，如下面的代码中所示。  

  ```csharp  
  itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  ```  

- **ItineraryStep**对象包含有关当前服务实例的执行，所有的信息以及与之关联的任何冲突解决程序。  

- **冲突解决程序**对象从检索**ItineraryStep**实例和 ESB 解析程序框架用于解析的完整名称的转换映射，如下面的代码中所示。  

  ```csharp  
  resolverDictionary =   
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transform type.  
  transformType = resolverDictionary.Item("Resolver.TransformType");  
  ```  

- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器框架来实现此功能通过加载相应的解析程序缓存中 （在此示例中，BizTalk 业务规则引擎冲突解决程序），这样调用 ResolverMap 策略并填充**ResolverDictionary**对象。  

- 业务流程完成后，该代码调用**AdvanceItinerary**方法，如以下代码所示。  

  ```csharp  
  // Call the Itinerary helper to advance to the next step.  
  itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
  ```  

- 这通过更新其属性以及将提升在路线中定义为一个接下来要执行的下一个服务，改进了当前的路线。 该方法将路线复制到该服务会发布回 Messagebox 数据库通过直接绑定的发送端口的出站消息。  

- Microsoft.Practices.ESB.Services.Delivery 服务业务流程的订阅就会触发此业务流程的调用。 此业务流程到第一个，获取当前的行程步骤遵循类似的过程。 但是，此业务流程循环访问返回的冲突解决程序的集合**ItineraryStep**实例。 对于集合中的每个冲突解决程序，交付业务流程使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器框架来解析传输位置并将它们提升为传出消息中的上下文属性，如下面的代码中所示。  

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

- ProcessAndRespond 业务流程的订阅会触发此业务流程的调用由于为筛选器表达式属性定义的消息上下文属性的匹配项。  

  ```  
  (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
  && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
  && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
  ```  

- ProcessAndRespond 业务流程将推进路线，并将原始请求消息发送回给路线测试客户端应用程序作为响应的接入点服务。
