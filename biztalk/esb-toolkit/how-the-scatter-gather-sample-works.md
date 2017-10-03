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
# <a name="how-the-scatter-gather-sample-works"></a>散播-聚集示例的工作原理
示例应用程序生成一组包含从散播-聚集路线文件加载路线的 SOAP 标头、 从磁盘加载指定的消息文件、 将路线标头追加到消息，并将其提交到通过入口为 ESB处理。 如果路线生成响应，应用程序收集此，在应用程序窗口中显示。  
  
 为了帮助你了解如何路线服务的消息中使用路线的信息，以下列表显示了名为 ScatterGatherItinerary.xml 示例路线的配置文件。 此路线的第一个节指定两个服务调用步骤。  
  
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
  
 该列表后面的服务调用中的步骤路线是包含冲突解决程序和允许找到中路线，定义每个服务，如下面的 XML 中所示路线服务的连接字符串的详细信息的部分。  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 在此示例中，应用程序执行 SubmitPOService Web 服务，两次，因为两个冲突解决程序连接字符串解析为此服务 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx) 的位置。 若要激活，第一个路线服务定义如下所示示例中，消息上下文指定 Broker 业务流程。  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 Broker 业务流程分析其路线步骤的设置，并检索冲突解决程序与路线步骤关联的集合。 对于每个这些冲突解决，业务流程使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]用于解决问题的服务终结点的解析程序和适配器框架。 Broker 业务流程然后激活的 ServiceDispatcher 业务流程的 n 数以异步方式 （其中 n 是与路线中的 ScatterGather 服务关联的解析程序数） 来调度请求消息中的使用以下参数：  
  
-   **TransportLocation**。 冲突解决程序填充此参数。  
  
-   **TransportType**。 冲突解决程序填充此参数。  
  
-   **ResolverDictionary**。 此参数包含冲突解决程序事实的具体的解析程序实例所填充的集合。  
  
-   **InboundMessage**。 此参数包含包含路线的原始消息。  
  
-   **ServiceResponsePort**。 此参数是将收到响应来自 ServiceDispatcher 业务流程的实例的自相关响应端口的名称。  
  
 ServiceDispatcher 业务流程的每个实例使用 ResolveMapScatterGather 策略来请求和响应消息，基于 Microsoft BizTalk 映射类型解析**TransportType**和**TransportLocation**属性。 业务流程实例使用的解析的映射来将入站的消息转换为 Web 服务调用的请求消息。  
  
 ESB 适配器管理器在请求消息中，哪些 BizTalk 然后转发到请求-响应端口将名为 ServiceRequestPort 设置出站传输上下文属性。  
  
 当从服务接收到响应消息时，ServiceDispatcher 业务流程将解决的映射信息转换为规范格式的入站的响应消息。 然后内 ServiceResponse 信封换行的修改后的响应，并将其转发到 Broker 业务流程通过自助关联的端口。 Broker 业务流程聚合所有传入的响应，并准备使用 GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline，最终响应消息，如下面的代码中所示。  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 此代码包装在预定义信封内整个批处理的响应。 Broker 业务流程然后前进到路线**DynamicTest**路线步骤中，如下面的代码中所示。  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 因为名为的服务类型属性**DynamicTest**设置为**消息**、 **ItineraryHelper**类将冲突解决程序属性提升到的上下文名为消息**OutboundMessage**。 Broker 业务流程将此消息发送到 BizTalk 直接绑定的端口。 BizTalk 随后将转发到由动态发送端口消息**ServiceName**订阅，这是**DynamicTest**。 此发送端口将最终聚合的响应 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹进行序列化。