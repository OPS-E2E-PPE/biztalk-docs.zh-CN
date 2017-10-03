---
title: "执行路线服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d86d228-da28-494f-85c7-4225b54f9b98
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4a4dc5c201b26ec33ee5666bc0dbeec8f54ccfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="executing-an-itinerary-service"></a>执行路线服务
ESB 路线可以包含任何路线服务都可能是实现作为业务流程或消息传递执行以下任务：  
  
-   它可接收包含路线的消息。  
  
-   它可检索当前路线步骤。  
  
-   它可以处理服务。  
  
-   它可以对传出消息推进路线，通过调用**高级**方法。  
  
-   它可以将已处理的消息发布回 Microsoft BizTalk 消息框数据库。  
  
 例如，业务流程可以接收一条消息，通过实现激活的接收形状上定义的筛选器的图 1 中所示包含一条路线[为路线服务的订阅服务器使用一个业务流程](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)。 但是，消息传送是略有不同： 管道的组件调用**GetItineraryStep**方法来确定传入消息中是否存在一条路线。 它还检查消息属性来检查是否应处理它。  
  
 ![业务流程](../esb-toolkit/media/ch4-orchestration.jpg "第四章第 4 业务流程")  
  
 **图 1**  
  
 **适用于将参与作为订阅服务器路线业务流程的示例筛选器表达式**  
  
 服务获取消息后，它必须调用**GetItineraryStep**方法，返回的实例**ItineraryStep**类。 以下列表演示如何从业务流程和自定义管道组件调用路线 API 的方法。 下面的代码执行**GetItineraryStep**从业务流程表达式形状的方法。  
  
```  
  
//XLANGs  
// Retrieve the current itinerary step.  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
```  
  
 下面的代码演示如何从自定义管道组件执行消息传递服务方法。  
  
```csharp  
// Execute messaging step.  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage msg, string resolverString, IItineraryStep step)  
{  
    if (null != step  
    && step.ServiceType == "Messaging"  
    && step.ServiceName == "SomeService")  
    {  
        // If the service name matches the required name, process the message here.  
    }  
    else  
    {  
        // Do not process the message.  
        return pInMsg;  
    }  
}  
```  
  
 实例**IItineraryStep**类包含对于当前的服务，包括当前的服务执行环境的环境属性的所有元数据。 两个很好的此示例**ServiceInstanceID**和当前**MessageDirection**管道组件的属性。  
  
 服务调用后**GetItineraryStep**方法，它可以检索任何关联的解析程序。 **ResolverCollection**属性**ItineraryStep**类返回的冲突解决程序，该服务可以在下面的示例所示通过枚举集合。  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 在每个项**ResolverCollection**表示与某个冲突解决程序和适配器框架支持的类型匹配的冲突解决程序连接字符串。 例如，集合中的项无法类似以下的列表。  
  
```idl  
BRE:\\policy=GetCanadaPurchaseEndPoint;version=;useMsg=;  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderFileServiceWBindings;  
STATIC:\\TransportLocation=http://localhost/ESB.CanadianServices/SubmitPOService.asmx;  
TargetNamespace=http://globalbank.esb.dynamicresolution.com/canadianservices/;  
XPATH:\\TransportType=; TransportLocation=/*[local-name()='OrderDoc' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*  
[local-name()='ID' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];  
TargetNamespace=/*[local-name()='OrderDoc' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*  
[local-name()='customerName' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];  
```  
  
 解决终结点并设置消息的终结点属性中的冲突解决程序和适配器提供程序框架的冲突解决程序管理器。 有关如何发生这种情况的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。  
  
 该服务处理完该消息后，它必须使路线前进对传出消息，然后将消息发布回消息框数据库。 下面的示例演示一个业务流程表达式形状的过程。  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 下面的示例演示如何指示[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎应前进自定义管道组件的路线。  
  
```csharp  
// Advance Itinerary  
// <summary>  
// Signals that the step should be advanced immediately following execution of the service.  
// </summary>  
// <param name="step">Current step</param>  
// <param name="msg">Current message</param>  
// <returns>True to advance the itinerary.</returns>  
public bool ShouldAdvanceStep(IItineraryStep step, IBaseMessage msg)  
{  
    return true;  
}  
```