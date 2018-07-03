---
title: 散播-聚集示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ccfacb7-4fd2-4a1a-bece-27eedd86bbe9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c675f2c6a9f558be597f7765ec936daf0a5a2dde
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001094"
---
# <a name="how-the-scatter-gather-sample-works"></a>散播-聚集示例工作原理
示例应用程序生成一组 SOAP 标头包含从散播-聚集路线文件加载路线、 从磁盘加载指定的消息文件、 路线标头附加到消息，并将其提交到 ESB 接入点为通过正在处理。 如果路线时都生成响应，该应用程序收集这和在应用程序窗口中显示。  
  
 为了帮助你了解路线服务如何使用路线信息消息中，以下列表显示了名为 ScatterGatherItinerary.xml 示例路线的配置文件。 此路线的第一个部分指定两个服务调用步骤。  
  
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
  
 后面的路线中的服务调用步骤列表是包含冲突解决程序和允许路线服务来查找在路线中定义每个服务，如下面的 XML 中所示的连接字符串的详细信息的部分。  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 在此示例中，应用程序执行 SubmitPOService Web 服务，两次因为两个冲突解决程序连接字符串解析到此服务的位置 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx)。 消息上下文指定 Broker 业务流程的第一个的路线服务，若要激活，如下所示示例中定义。  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 Broker 业务流程分析其行程步骤的设置，并检索与行程步骤相关联的冲突解决程序的集合。 对于每个这些冲突解决程序，该业务流程使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器框架来解析服务终结点。 Broker 业务流程随后激活 n ServiceDispatcher 业务流程数以异步方式 （其中 n 是冲突解决程序 ScatterGather 中与服务相关的路线数） 来调度请求消息使用以下参数：  
  
- **TransportLocation**。 冲突解决程序填充此参数。  
  
- **TransportType**。 冲突解决程序填充此参数。  
  
- **ResolverDictionary**。 此参数包含的冲突解决程序事实填充具体的解析程序实例的集合。  
  
- **InboundMessage**。 此参数包含包含路线的原始消息。  
  
- **ServiceResponsePort**。 此参数是自相关接收响应的 ServiceDispatcher 业务流程实例的响应端口的名称。  
  
  ServiceDispatcher 业务流程的每个实例使用 ResolveMapScatterGather 策略来请求和响应消息，根据 Microsoft BizTalk 映射类型解析**TransportType**和**TransportLocation**属性。 业务流程实例使用的解析的映射来将入站的消息转换为 Web 服务调用的请求消息。  
  
  ESB 适配器管理器设置出站传输上的 BizTalk 然后转发到要求响应端口将名为 ServiceRequestPort 的请求消息上下文属性。  
  
  从服务收到响应消息时, ServiceDispatcher 业务流程使用解析的映射信息转换为规范格式的入站的响应消息。 然后 ServiceResponse 信封内换行的修改后的响应，并将其转发到 Broker 业务流程通过自相关端口。 Broker 业务流程聚合所有传入响应，并准备使用 GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline，最终响应消息，如下面的代码中所示。  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 此代码在预定义信封包装整个批处理的响应。 Broker 业务流程然后前进到路线**DynamicTest**路线步骤中，如下面的代码中所示。  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 因为名为的服务类型属性**DynamicTest**设置为**消息传送**，则**ItineraryHelper**类将冲突解决程序的属性升级到的上下文名为消息**OutboundMessage**。 Broker 业务流程将此消息发送到 BizTalk 直接绑定端口。 BizTalk 然后将消息转发到表示的动态发送端口**ServiceName**订阅，这是**DynamicTest**。 此发送端口将序列化到 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹最终聚合的响应。