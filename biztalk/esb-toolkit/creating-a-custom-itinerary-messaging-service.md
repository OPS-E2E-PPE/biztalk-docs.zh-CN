---
title: 创建自定义路线消息传递服务 |Microsoft 文档
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
ms.openlocfilehash: 5f08168e69e26d56cb39fb5c05cc53c3cbb51202
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973731"
---
# <a name="creating-a-custom-itinerary-messaging-service"></a>创建自定义路线消息服务
是的一部分的路线 framework[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持使用类实现的路线步骤执行**IMessagingService**执行路线的消息传递服务的接口。 当你想要进行负责执行以下的服务时，你可以实现自定义的消息传递服务：  
  
-   配置在路线中的自定义消息验证  
  
-   在路线中配置的自定义消息转换  
  
-   自定义消息处理  
  
 在所有这些情况下，你实现的自定义路线服务充当拦截器，并由调度程序管道组件调用。  
  
 自定义基于消息的路线的服务或所有实现的消息传递服务**IMessagingService**接口。 此接口公开**名称**和**SupportsDisassemble**属性和**执行**和**ShouldAdvanceStep**方法。  
  
 **名称**属性是服务的名称，将显示在一条路线。 它必须与匹配 Esb.config 文件中的路线服务配置中的配置的名称。  
  
 **SupportsDisassemble**属性指示是否要创建支持自定义消息传递服务反汇编和多个冲突解决程序的执行。  
  
 **ShouldAdvanceStep**方法采用在当前路线步骤中，并且当前消息，并返回一个布尔值，该值指示服务执行后，调度程序是否应前进路线。 在几乎所有情况下，此方法应返回**true**。  
  
 **执行**方法的消息传递服务的最大重要性，并且包含将在运行时执行的逻辑。 设置将在管道上下文、 消息、 冲突解决程序字符串和当前路线步骤; 中然后它返回更新的消息。  
  
 参考实现**执行**ESB 的 RoutingService.cs 文件中找到方法。Itinerary.Services 项目，如下面的代码中所示。  
  
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
  
1.  与派生自的类创建一个程序集**IMessagingService;** 中**执行**方法，包括所需能够修改消息或消息上下文 （如果有） 的所有逻辑。  
  
2.  添加将项记入**itineraryServices**添加你的服务 Esb.config 文件节 **\<itineraryService\>**  GUID，则为具有元素**id**属性，作为服务的名称**名称**属性，作为类的完全限定的名称**类型**属性，**消息**作为**作用域**特性，并且允许的阶段 (例如， **OnRampReceive**， **OnRampSend**， **OffRampSend**， **OffRampReceive**， **AllSend**， **AllReceive**，或**所有**) 作为**阶段**属性。  
  
3.  在全局程序集缓存中注册新的程序集。