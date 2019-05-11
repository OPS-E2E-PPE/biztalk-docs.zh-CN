---
title: 创建自定义路线消息传送服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2de44c21-68ca-4cf1-a117-bcb35af1b4a9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c773fcd093035f414fd4824a38e5b675484f51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291499"
---
# <a name="creating-a-custom-itinerary-messaging-service"></a><span data-ttu-id="72f4c-102">创建自定义路线消息传递服务</span><span class="sxs-lookup"><span data-stu-id="72f4c-102">Creating a Custom Itinerary Messaging Service</span></span>
<span data-ttu-id="72f4c-103">是的一部分的路线 framework[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持执行使用实现的类的路线步骤**IMessagingService**执行路线消息传递服务的接口。</span><span class="sxs-lookup"><span data-stu-id="72f4c-103">The itinerary framework that is part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports execution of itinerary steps using classes implementing the **IMessagingService** interface that execute itinerary messaging services.</span></span> <span data-ttu-id="72f4c-104">当你想要负责以下的服务时，可以实现自定义的消息传递服务：</span><span class="sxs-lookup"><span data-stu-id="72f4c-104">You can implement a custom messaging service when you want the service to be responsible for the following:</span></span>  
  
- <span data-ttu-id="72f4c-105">在路线中配置的自定义消息验证</span><span class="sxs-lookup"><span data-stu-id="72f4c-105">Custom message validation configured in the itinerary</span></span>  
  
- <span data-ttu-id="72f4c-106">在路线中配置的自定义消息转换</span><span class="sxs-lookup"><span data-stu-id="72f4c-106">Custom message transformation configured in the itinerary</span></span>  
  
- <span data-ttu-id="72f4c-107">自定义消息处理</span><span class="sxs-lookup"><span data-stu-id="72f4c-107">Custom processing of the message</span></span>  
  
  <span data-ttu-id="72f4c-108">在所有这些情况下，您实现自定义路线服务充当侦听器并调用由调度程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="72f4c-108">In all these cases, a custom itinerary service that you implement acts as an interceptor and is called by the Dispatcher pipeline component.</span></span>  
  
  <span data-ttu-id="72f4c-109">自定义的基于消息的路线服务或消息传送服务，所有实现**IMessagingService**接口。</span><span class="sxs-lookup"><span data-stu-id="72f4c-109">Custom messaging-based itinerary services, or messaging services, all implement the **IMessagingService** interface.</span></span> <span data-ttu-id="72f4c-110">此接口公开**名称**并**SupportsDisassemble**属性并**Execute**并**ShouldAdvanceStep**方法。</span><span class="sxs-lookup"><span data-stu-id="72f4c-110">This interface exposes the **Name** and **SupportsDisassemble** properties and the **Execute** and **ShouldAdvanceStep** methods.</span></span>  
  
  <span data-ttu-id="72f4c-111">**名称**属性是服务的名称，将显示在路线中。</span><span class="sxs-lookup"><span data-stu-id="72f4c-111">The **Name** property is the name of the service as it will appear in an itinerary.</span></span> <span data-ttu-id="72f4c-112">它必须匹配 Esb.config 文件中的路线服务配置中配置的名称。</span><span class="sxs-lookup"><span data-stu-id="72f4c-112">It must match the configured name in the itinerary services configuration in the Esb.config file.</span></span>  
  
  <span data-ttu-id="72f4c-113">**SupportsDisassemble**属性指示是否要创建支持自定义消息传送服务拆装和多个冲突解决程序的执行。</span><span class="sxs-lookup"><span data-stu-id="72f4c-113">The **SupportsDisassemble** property indicates whether the custom messaging service you are creating supports disassemble and the execution of multiple resolvers.</span></span>  
  
  <span data-ttu-id="72f4c-114">**ShouldAdvanceStep**方法接受当前的行程步骤，以及当前的消息，并返回一个布尔值，该值指示是否执行该服务之后，调度程序应处理路线。</span><span class="sxs-lookup"><span data-stu-id="72f4c-114">The **ShouldAdvanceStep** method takes in the current itinerary step, and the current message, and returns a Boolean value that indicates whether the dispatcher should advance the itinerary after the service executes.</span></span> <span data-ttu-id="72f4c-115">在几乎所有情况下，此方法应返回 **，则返回 true**。</span><span class="sxs-lookup"><span data-stu-id="72f4c-115">In almost all cases, this method should return **true**.</span></span>  
  
  <span data-ttu-id="72f4c-116">**Execute**方法为消息传递服务的最为重要的是，包含将在运行时执行的逻辑。</span><span class="sxs-lookup"><span data-stu-id="72f4c-116">The **Execute** method is of greatest importance for a messaging service and contains the logic that will be executed at run time.</span></span> <span data-ttu-id="72f4c-117">它采用管道上下文、 消息、 冲突解决程序字符串和当前行程步骤;它将返回已更新的消息。</span><span class="sxs-lookup"><span data-stu-id="72f4c-117">It takes in the pipeline context, the message, the resolver string, and the current itinerary step; and it returns the updated message.</span></span>  
  
  <span data-ttu-id="72f4c-118">引用实现**Execute** ESB 的 RoutingService.cs 文件中可以找到方法。Itinerary.Services 项目，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="72f4c-118">A reference implementation of the **Execute** method can be found in the RoutingService.cs file of the ESB.Itinerary.Services project, as shown in the following code.</span></span>  
  
```csharp  
public IBaseMessage ExecuteRoute(IPipelineContext context, IBaseMessage msg, string resolverString)  
        {  
            if (context == null)  
                throw new ArgumentNullException("context");  
            if (msg == null)  
                throw new ArgumentNullException("msg");  
            if (string.IsNullOrEmpty(resolverString))  
                throw new ArgumentException(Properties.Resources.ArgumentStringRequired, "resolverString");  
            try  
            {  
                ResolverInfo info = ResolverMgr.GetResolverInfo(ResolutionType.Endpoint, resolverString);  
                if (!info.Success)  
                    throw new RoutingException(Properties.Resources.ResolverStringInvalid, resolverString);  
  
                // Resolve configuration for routing.  
                Dictionary<string, string> resolverDictionary = ResolverMgr.Resolve(info, msg, context);  
  
                if (string.IsNullOrEmpty(resolverDictionary["Resolver.TransportLocation"]))  
                    throw new RoutingException(Properties.Resources.TransportLocationNotResolved, resolverString);  
  
                AdapterMgr.SetEndpoint(resolverDictionary, msg.Context);  
  
                return msg;  
            }  
            catch (System.Exception ex)  
            {  
                EventLogger.Write(MethodInfo.GetCurrentMethod(), ex);  
                throw;  
            }        
        }  
```  
  
 <span data-ttu-id="72f4c-119">**若要实现自定义路线服务的消息传送**</span><span class="sxs-lookup"><span data-stu-id="72f4c-119">**To implement a custom itinerary service for messaging**</span></span>  
  
1.  <span data-ttu-id="72f4c-120">创建派生的类的程序集**IMessagingService;** 中**Execute**方法，包括对进行修改的消息或消息上下文 （如果有） 所需的所有逻辑。</span><span class="sxs-lookup"><span data-stu-id="72f4c-120">Create an assembly with a class that derives from **IMessagingService;** in the **Execute** method, include all logic necessary to make modifications to the message or the message context (if any).</span></span>  
  
2.  <span data-ttu-id="72f4c-121">添加中的条目**itineraryServices**添加你的服务在 Esb.config 文件节**\<itineraryService\>** 具有一个 GUID 作为元素**id**属性，作为服务的名称**名称**属性，作为类的完全限定的名称**类型**属性，**消息传送**作为**作用域**特性，并且允许的阶段 (例如， **OnRampReceive**， **OnRampSend**， **OffRampSend**， **OffRampReceive**， **AllSend**， **AllReceive**，或**所有**) 作为**阶段**属性。</span><span class="sxs-lookup"><span data-stu-id="72f4c-121">Add an entry in the **itineraryServices** section of the Esb.config file for your service by adding an **\<itineraryService\>** element with a GUID as the **id** attribute, the name of the service as the **name** attribute, the fully qualified name of the class as the **type** attribute, **Messaging** as the **scope** attribute, and the allowed stage (for example, **OnRampReceive**, **OnRampSend**, **OffRampSend**, **OffRampReceive**, **AllSend**, **AllReceive**, or **All**) as the **stage** attribute.</span></span>  
  
3.  <span data-ttu-id="72f4c-122">在全局程序集缓存中注册新的程序集。</span><span class="sxs-lookup"><span data-stu-id="72f4c-122">Register the new assembly in the global assembly cache.</span></span>