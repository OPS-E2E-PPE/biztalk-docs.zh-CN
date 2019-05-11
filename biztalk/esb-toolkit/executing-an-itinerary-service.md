---
title: 执行路线服务 |Microsoft Docs
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
ms.openlocfilehash: 83551e31bfd822473e639c12abcf440c154dc826
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395123"
---
# <a name="executing-an-itinerary-service"></a><span data-ttu-id="60670-102">执行路线服务</span><span class="sxs-lookup"><span data-stu-id="60670-102">Executing an Itinerary Service</span></span>
<span data-ttu-id="60670-103">ESB 路线可以包含任何路线服务，可能是实现与业务流程或消息传递执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="60670-103">An ESB itinerary can contain any itinerary service that may be implemented as orchestration or messaging to perform the following tasks:</span></span>  
  
- <span data-ttu-id="60670-104">它可接收包含路线的消息。</span><span class="sxs-lookup"><span data-stu-id="60670-104">It can receive the message containing the itinerary.</span></span>  
  
- <span data-ttu-id="60670-105">它可以检索当前的行程步骤。</span><span class="sxs-lookup"><span data-stu-id="60670-105">It can retrieve the current itinerary step.</span></span>  
  
- <span data-ttu-id="60670-106">它可以处理服务。</span><span class="sxs-lookup"><span data-stu-id="60670-106">It can process the service.</span></span>  
  
- <span data-ttu-id="60670-107">它也可通过调用的传出消息上提前路线**提前**方法。</span><span class="sxs-lookup"><span data-stu-id="60670-107">It can advance the itinerary on the outgoing message by calling the **Advance** method.</span></span>  
  
- <span data-ttu-id="60670-108">它可以将已处理的消息发布回 Microsoft BizTalk Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="60670-108">It can publish the processed message back into the Microsoft BizTalk Message Box database.</span></span>  
  
  <span data-ttu-id="60670-109">例如，业务流程可收到一条消息，包含通过实现激活的接收形状上定义的筛选器中的图 1 所示的路线[将业务流程用作路线服务订阅方](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)。</span><span class="sxs-lookup"><span data-stu-id="60670-109">For example, an orchestration can receive a message that contains an itinerary by implementing a filter defined on the activated receive shape, as shown in Figure 1 of [Using an Orchestration as an Itinerary Service Subscriber](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="60670-110">但是，消息传送是略有不同： 管道的组件调用**GetItineraryStep**方法，以确定传入消息中是否存在一条路线。</span><span class="sxs-lookup"><span data-stu-id="60670-110">However, messaging is slightly different: the pipeline component calls the **GetItineraryStep** method to determine whether an itinerary exists in an incoming message.</span></span> <span data-ttu-id="60670-111">它还会检查消息属性来检查是否应处理它。</span><span class="sxs-lookup"><span data-stu-id="60670-111">It also examines the message properties to check whether it should process it.</span></span>  
  
  <span data-ttu-id="60670-112">![业务流程](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-业务流程")</span><span class="sxs-lookup"><span data-stu-id="60670-112">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  
  
  <span data-ttu-id="60670-113">**图 1**</span><span class="sxs-lookup"><span data-stu-id="60670-113">**Figure 1**</span></span>  
  
  <span data-ttu-id="60670-114">**将参与作为订阅者路线的业务流程的示例筛选表达式**</span><span class="sxs-lookup"><span data-stu-id="60670-114">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  
  
  <span data-ttu-id="60670-115">该服务获取消息后，它必须调用**GetItineraryStep**方法，返回的实例**ItineraryStep**类。</span><span class="sxs-lookup"><span data-stu-id="60670-115">After the service obtains the message, it must call the **GetItineraryStep** method, which returns an instance of the **ItineraryStep** class.</span></span> <span data-ttu-id="60670-116">以下列表演示如何从业务流程和自定义管道组件调用路线 API 的方法。</span><span class="sxs-lookup"><span data-stu-id="60670-116">The following listings demonstrate how you can call the methods of the itinerary API from both an orchestration and a custom pipeline component.</span></span> <span data-ttu-id="60670-117">下面的代码执行**GetItineraryStep**从业务流程表达式形状的方法。</span><span class="sxs-lookup"><span data-stu-id="60670-117">The following code executes the **GetItineraryStep** method from an orchestration Expression shape.</span></span>  
  
```  
  
//XLANGs  
// Retrieve the current itinerary step.  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
```  
  
 <span data-ttu-id="60670-118">下面的代码演示如何从自定义管道组件执行消息传送的服务方法。</span><span class="sxs-lookup"><span data-stu-id="60670-118">The following code shows how to execute the messaging service method from a custom pipeline component.</span></span>  
  
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
  
 <span data-ttu-id="60670-119">实例**IItineraryStep**类包含当前的服务，包括环境属性的当前服务执行环境的所有元数据。</span><span class="sxs-lookup"><span data-stu-id="60670-119">The instance of the **IItineraryStep** class contains all the metadata for the current service, including ambient properties of the current service execution environment.</span></span> <span data-ttu-id="60670-120">此选项均进行两个很好的示例**ServiceInstanceID**和当前**MessageDirection**管道组件属性。</span><span class="sxs-lookup"><span data-stu-id="60670-120">Two good examples of this are the **ServiceInstanceID** and the current **MessageDirection** properties for a pipeline component.</span></span>  
  
 <span data-ttu-id="60670-121">一个服务调用后**GetItineraryStep**方法，它可以检索所有关联的解析程序。</span><span class="sxs-lookup"><span data-stu-id="60670-121">After a service calls the **GetItineraryStep** method, it can retrieve any associated resolvers.</span></span> <span data-ttu-id="60670-122">**ResolverCollection**的属性**ItineraryStep**类返回的冲突解决程序，该服务可以在下面的示例所示通过枚举集合。</span><span class="sxs-lookup"><span data-stu-id="60670-122">The **ResolverCollection** property of the **ItineraryStep** class returns a collection of resolvers that the service can enumerate through, as shown in the following example.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 <span data-ttu-id="60670-123">中的每项**ResolverCollection**表示与某个冲突解决程序和适配器框架支持的类型匹配的冲突解决程序连接字符串。</span><span class="sxs-lookup"><span data-stu-id="60670-123">Each item in the **ResolverCollection** represents a resolver connection string that matches one of the types supported by the Resolver and Adapter Framework.</span></span> <span data-ttu-id="60670-124">例如，集合中的项可能如下所示的以下列表中。</span><span class="sxs-lookup"><span data-stu-id="60670-124">For example, an item in the collection could look like the following listing.</span></span>  
  
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
  
 <span data-ttu-id="60670-125">中的冲突解决程序和适配器提供程序框架的冲突解决程序管理器可解析终结点并设置消息的终结点属性。</span><span class="sxs-lookup"><span data-stu-id="60670-125">The resolver manager in the Resolver and Adapter Provider Framework can resolve the endpoints and set the endpoint properties of the message.</span></span> <span data-ttu-id="60670-126">有关如何发生这种情况的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="60670-126">For more information about how this occurs, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
 <span data-ttu-id="60670-127">该服务处理完该消息后，它必须前进的传出消息上的路线，并将消息发布回 Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="60670-127">After the service finishes processing the message, it must advance the itinerary on the outgoing message and publish the message back to the Message Box database.</span></span> <span data-ttu-id="60670-128">下面的示例显示了业务流程表达式形状的过程。</span><span class="sxs-lookup"><span data-stu-id="60670-128">The following example shows the process for an orchestration Expression shape.</span></span>  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 <span data-ttu-id="60670-129">下面的示例演示如何指示[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎应前移的自定义管道组件的路线。</span><span class="sxs-lookup"><span data-stu-id="60670-129">The following example shows how to indicate that [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine should advance itinerary for a custom pipeline component.</span></span>  
  
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