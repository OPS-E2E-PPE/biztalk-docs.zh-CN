---
title: "在代码中使用的冲突解决程序组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d197cb28-78a9-4c8a-872b-f61ef15e6622
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220ae4983f2fcbf60f6de02f818095fe5c0c50a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-resolver-components-in-your-code"></a>在代码中使用的冲突解决程序组件
从动态转换代理中的以下代码片段演示默认在实时 (JIT) 解析功能。 你可以轻松地实现解析自己的应用程序中，这需要使用类似的代码来实现。  
  
```  
  
//XLANGs  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
resolvers = step.ItineraryStep.ResolverCollection;  
resolvers.MoveNext();  
resolver = resolvers.Current;  
  
// Pass the resolver configuration to the Resolver mgr for resolution.  
resolverDictionary = Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage, resolver);  
  
// Set the transform type.  
transformType = resolverDictionary.Item("Resolver.TransformType");  
```  
  
 在前面的列表中，**解决**方法**ResolverMgr**类返回**字典**对象，其中包含所有默认解析属性及其解析值。 任何自定义解析程序可以添加到自定义属性**字典**对象; 不采取这使这些可用于任何自定义的路线服务的属性。  
  
 下表显示可以根据需要填充中包含的解析程序的属性[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 任何路线服务可以通过提取这些密码从返回检索这些属性值**字典**对象。  
  
 **属性**:  
  
||||  
|-|-|-|  
|**Resolver.Action**|**Resolver.ActionField**|**Resolver.DocumentSpecName**|  
|**Resolver.Success**|**Resolver.EndpointConfig**|**Resolver.DocumentSpecStrongName**|  
|**Resolver.FixJaxRpc**|**Resolver.InboundTransportType**|**Resolver.EpmRRCorrelationToken**|  
|**Resolver.InterchangeId**|**Resolver.IsRequestResponse**|**Resolver.InboundTransportLocation**|  
|**Resolver.MessageType**|**Resolver.MethodName**|**Resolver.MessageExchangePattern**|  
|**Resolver.ReceivePortName**|**Resolver.TransportLocation**|**Resolver.OutboundTransportCLSID**|  
|**Resolver.TransformType**|**Resolver.TargetNamespace**|**Resolver.ReceiveLocationName**|  
|**Resolver.TransportType**|**Resolver.TransportNamespace**|**Resolver.WindowUserField**|  
|**Resolver.CacheTimeout**|||  
  
 之后冲突解决程序管理器将返回**字典**对象实例的适配器管理器设置消息的特定的 BizTalk 适配器上下文属性。 从路由代理中的以下代码片段演示如何使用适配器 manager 设置传出消息的终结点属性。  
  
```  
  
//XLANGs  
// Set the transport properties.  
transportLocation = resolverDictionary.Item("Resolver.TransportLocation");  
transportType = resolverDictionary.Item("Resolver.TransportType");  
  
// Create the delivery message.  
DeliveryMessage = InboundMessage;  
  
// Call the adapter manager to set all necessary properties on the message.  
Microsoft.Practices.ESB.Adapter.AdapterMgr.SetEndpoint(  
                                resolverDictionary,DeliveryMessage);  
  
// Set the delivery port address.  
DeliveryPort(Microsoft.XLANGs.BaseTypes.Address) = transportLocation;  
DeliveryPort(Microsoft.XLANGs.BaseTypes.TransportType) = transportType;  
```  
  
 从路由代理中的以下代码片段演示如何使用适配器管理器从自定义管道组件内的设置的传出消息的终结点属性。  
  
```csharp  
// Resolve the configuration for routing.  
ResolverDictionary = ResolverMgr.Resolve(info, pInMsg, pContext);  
  
// Call the adapter manager to set all required message properties.  
AdapterMgr.SetEndpoint(ResolverDictionary, pInMsg.Context);  
```