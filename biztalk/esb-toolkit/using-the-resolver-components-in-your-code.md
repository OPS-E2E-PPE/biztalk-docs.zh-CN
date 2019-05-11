---
title: 在你的代码中使用冲突解决程序组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d197cb28-78a9-4c8a-872b-f61ef15e6622
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 901ade5dd611c047c480f05ef0da8271150139d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396390"
---
# <a name="using-the-resolver-components-in-your-code"></a>在你的代码中使用冲突解决程序组件
动态转换代理从下面的代码段显示了默认在实时 (JIT) 解析功能。 通过使用类似的代码，可以轻松在自己的应用程序中实现解决方法。  
  
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
  
 在前面的列表中，**解决**方法**ResolverMgr**类返回**字典**对象，其中包含所有默认解析属性及其解析的值。 任何自定义冲突解决程序可以添加到自定义属性**字典**对象; 不采取这使这些属性可用于任何自定义路线服务。  
  
 下表显示了通过包含在冲突解决程序可以根据需要填充属性[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 任何路线服务可以检索这些属性值由从返回提取这些**字典**对象。  
  
 **属性**：  
  
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
  
 之后冲突解决程序管理器返回**字典**对象实例，适配器管理器设置特定的 BizTalk 适配器上下文属性的消息。 从路由代理的以下代码片段演示如何使用适配器管理器来设置传出消息的终结点属性。  
  
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
  
 从路由代理的以下代码片段演示如何使用适配器管理器从自定义管道组件中的设置传出消息的终结点属性。  
  
```csharp  
// Resolve the configuration for routing.  
ResolverDictionary = ResolverMgr.Resolve(info, pInMsg, pContext);  
  
// Call the adapter manager to set all required message properties.  
AdapterMgr.SetEndpoint(ResolverDictionary, pInMsg.Context);  
```