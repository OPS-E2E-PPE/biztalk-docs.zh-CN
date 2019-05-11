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
# <a name="creating-a-custom-itinerary-messaging-service"></a>创建自定义路线消息传递服务
是的一部分的路线 framework[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持执行使用实现的类的路线步骤**IMessagingService**执行路线消息传递服务的接口。 当你想要负责以下的服务时，可以实现自定义的消息传递服务：  
  
- 在路线中配置的自定义消息验证  
  
- 在路线中配置的自定义消息转换  
  
- 自定义消息处理  
  
  在所有这些情况下，您实现自定义路线服务充当侦听器并调用由调度程序管道组件。  
  
  自定义的基于消息的路线服务或消息传送服务，所有实现**IMessagingService**接口。 此接口公开**名称**并**SupportsDisassemble**属性并**Execute**并**ShouldAdvanceStep**方法。  
  
  **名称**属性是服务的名称，将显示在路线中。 它必须匹配 Esb.config 文件中的路线服务配置中配置的名称。  
  
  **SupportsDisassemble**属性指示是否要创建支持自定义消息传送服务拆装和多个冲突解决程序的执行。  
  
  **ShouldAdvanceStep**方法接受当前的行程步骤，以及当前的消息，并返回一个布尔值，该值指示是否执行该服务之后，调度程序应处理路线。 在几乎所有情况下，此方法应返回 **，则返回 true**。  
  
  **Execute**方法为消息传递服务的最为重要的是，包含将在运行时执行的逻辑。 它采用管道上下文、 消息、 冲突解决程序字符串和当前行程步骤;它将返回已更新的消息。  
  
  引用实现**Execute** ESB 的 RoutingService.cs 文件中可以找到方法。Itinerary.Services 项目，如下面的代码中所示。  
  
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
  
 **若要实现自定义路线服务的消息传送**  
  
1.  创建派生的类的程序集**IMessagingService;** 中**Execute**方法，包括对进行修改的消息或消息上下文 （如果有） 所需的所有逻辑。  
  
2.  添加中的条目**itineraryServices**添加你的服务在 Esb.config 文件节**\<itineraryService\>** 具有一个 GUID 作为元素**id**属性，作为服务的名称**名称**属性，作为类的完全限定的名称**类型**属性，**消息传送**作为**作用域**特性，并且允许的阶段 (例如， **OnRampReceive**， **OnRampSend**， **OffRampSend**， **OffRampReceive**， **AllSend**， **AllReceive**，或**所有**) 作为**阶段**属性。  
  
3.  在全局程序集缓存中注册新的程序集。