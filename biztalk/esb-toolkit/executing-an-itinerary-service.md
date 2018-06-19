---
title: 执行路线服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d86d228-da28-494f-85c7-4225b54f9b98
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4a4dc5c201b26ec33ee5666bc0dbeec8f54ccfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294453"
---
# <a name="executing-an-itinerary-service"></a><span data-ttu-id="7249e-102">执行路线服务</span><span class="sxs-lookup"><span data-stu-id="7249e-102">Executing an Itinerary Service</span></span>
<span data-ttu-id="7249e-103">ESB 路线可以包含任何路线服务都可能是实现作为业务流程或消息传递执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="7249e-103">An ESB itinerary can contain any itinerary service that may be implemented as orchestration or messaging to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="7249e-104">它可接收包含路线的消息。</span><span class="sxs-lookup"><span data-stu-id="7249e-104">It can receive the message containing the itinerary.</span></span>  
  
-   <span data-ttu-id="7249e-105">它可检索当前路线步骤。</span><span class="sxs-lookup"><span data-stu-id="7249e-105">It can retrieve the current itinerary step.</span></span>  
  
-   <span data-ttu-id="7249e-106">它可以处理服务。</span><span class="sxs-lookup"><span data-stu-id="7249e-106">It can process the service.</span></span>  
  
-   <span data-ttu-id="7249e-107">它可以对传出消息推进路线，通过调用**高级**方法。</span><span class="sxs-lookup"><span data-stu-id="7249e-107">It can advance the itinerary on the outgoing message by calling the **Advance** method.</span></span>  
  
-   <span data-ttu-id="7249e-108">它可以将已处理的消息发布回 Microsoft BizTalk 消息框数据库。</span><span class="sxs-lookup"><span data-stu-id="7249e-108">It can publish the processed message back into the Microsoft BizTalk Message Box database.</span></span>  
  
 <span data-ttu-id="7249e-109">例如，业务流程可以接收一条消息，通过实现激活的接收形状上定义的筛选器的图 1 中所示包含一条路线[为路线服务的订阅服务器使用一个业务流程](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)。</span><span class="sxs-lookup"><span data-stu-id="7249e-109">For example, an orchestration can receive a message that contains an itinerary by implementing a filter defined on the activated receive shape, as shown in Figure 1 of [Using an Orchestration as an Itinerary Service Subscriber](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="7249e-110">但是，消息传送是略有不同： 管道的组件调用**GetItineraryStep**方法来确定传入消息中是否存在一条路线。</span><span class="sxs-lookup"><span data-stu-id="7249e-110">However, messaging is slightly different: the pipeline component calls the **GetItineraryStep** method to determine whether an itinerary exists in an incoming message.</span></span> <span data-ttu-id="7249e-111">它还检查消息属性来检查是否应处理它。</span><span class="sxs-lookup"><span data-stu-id="7249e-111">It also examines the message properties to check whether it should process it.</span></span>  
  
 <span data-ttu-id="7249e-112">![业务流程](../esb-toolkit/media/ch4-orchestration.jpg "第四章第 4 业务流程")</span><span class="sxs-lookup"><span data-stu-id="7249e-112">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  
  
 <span data-ttu-id="7249e-113">**图 1**</span><span class="sxs-lookup"><span data-stu-id="7249e-113">**Figure 1**</span></span>  
  
 <span data-ttu-id="7249e-114">**适用于将参与作为订阅服务器路线业务流程的示例筛选器表达式**</span><span class="sxs-lookup"><span data-stu-id="7249e-114">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  
  
 <span data-ttu-id="7249e-115">服务获取消息后，它必须调用**GetItineraryStep**方法，返回的实例**ItineraryStep**类。</span><span class="sxs-lookup"><span data-stu-id="7249e-115">After the service obtains the message, it must call the **GetItineraryStep** method, which returns an instance of the **ItineraryStep** class.</span></span> <span data-ttu-id="7249e-116">以下列表演示如何从业务流程和自定义管道组件调用路线 API 的方法。</span><span class="sxs-lookup"><span data-stu-id="7249e-116">The following listings demonstrate how you can call the methods of the itinerary API from both an orchestration and a custom pipeline component.</span></span> <span data-ttu-id="7249e-117">下面的代码执行**GetItineraryStep**从业务流程表达式形状的方法。</span><span class="sxs-lookup"><span data-stu-id="7249e-117">The following code executes the **GetItineraryStep** method from an orchestration Expression shape.</span></span>  
  
```  
  
//XLANGs  
// Retrieve the current itinerary step.  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
```  
  
 <span data-ttu-id="7249e-118">下面的代码演示如何从自定义管道组件执行消息传递服务方法。</span><span class="sxs-lookup"><span data-stu-id="7249e-118">The following code shows how to execute the messaging service method from a custom pipeline component.</span></span>  
  
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
  
 <span data-ttu-id="7249e-119">实例**IItineraryStep**类包含对于当前的服务，包括当前的服务执行环境的环境属性的所有元数据。</span><span class="sxs-lookup"><span data-stu-id="7249e-119">The instance of the **IItineraryStep** class contains all the metadata for the current service, including ambient properties of the current service execution environment.</span></span> <span data-ttu-id="7249e-120">两个很好的此示例**ServiceInstanceID**和当前**MessageDirection**管道组件的属性。</span><span class="sxs-lookup"><span data-stu-id="7249e-120">Two good examples of this are the **ServiceInstanceID** and the current **MessageDirection** properties for a pipeline component.</span></span>  
  
 <span data-ttu-id="7249e-121">服务调用后**GetItineraryStep**方法，它可以检索任何关联的解析程序。</span><span class="sxs-lookup"><span data-stu-id="7249e-121">After a service calls the **GetItineraryStep** method, it can retrieve any associated resolvers.</span></span> <span data-ttu-id="7249e-122">**ResolverCollection**属性**ItineraryStep**类返回的冲突解决程序，该服务可以在下面的示例所示通过枚举集合。</span><span class="sxs-lookup"><span data-stu-id="7249e-122">The **ResolverCollection** property of the **ItineraryStep** class returns a collection of resolvers that the service can enumerate through, as shown in the following example.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 <span data-ttu-id="7249e-123">在每个项**ResolverCollection**表示与某个冲突解决程序和适配器框架支持的类型匹配的冲突解决程序连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7249e-123">Each item in the **ResolverCollection** represents a resolver connection string that matches one of the types supported by the Resolver and Adapter Framework.</span></span> <span data-ttu-id="7249e-124">例如，集合中的项无法类似以下的列表。</span><span class="sxs-lookup"><span data-stu-id="7249e-124">For example, an item in the collection could look like the following listing.</span></span>  
  
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
  
 <span data-ttu-id="7249e-125">解决终结点并设置消息的终结点属性中的冲突解决程序和适配器提供程序框架的冲突解决程序管理器。</span><span class="sxs-lookup"><span data-stu-id="7249e-125">The resolver manager in the Resolver and Adapter Provider Framework can resolve the endpoints and set the endpoint properties of the message.</span></span> <span data-ttu-id="7249e-126">有关如何发生这种情况的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="7249e-126">For more information about how this occurs, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
 <span data-ttu-id="7249e-127">该服务处理完该消息后，它必须使路线前进对传出消息，然后将消息发布回消息框数据库。</span><span class="sxs-lookup"><span data-stu-id="7249e-127">After the service finishes processing the message, it must advance the itinerary on the outgoing message and publish the message back to the Message Box database.</span></span> <span data-ttu-id="7249e-128">下面的示例演示一个业务流程表达式形状的过程。</span><span class="sxs-lookup"><span data-stu-id="7249e-128">The following example shows the process for an orchestration Expression shape.</span></span>  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 <span data-ttu-id="7249e-129">下面的示例演示如何指示[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎应前进自定义管道组件的路线。</span><span class="sxs-lookup"><span data-stu-id="7249e-129">The following example shows how to indicate that [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine should advance itinerary for a custom pipeline component.</span></span>  
  
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