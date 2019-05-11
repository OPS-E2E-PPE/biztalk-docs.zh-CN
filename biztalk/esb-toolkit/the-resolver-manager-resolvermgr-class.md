---
title: Resolver Manager (ResolverMgr) 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89fa551d-0aca-4777-adbc-2bc46ab8664a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 230a22fa771e0791a705448d2a37fa07563fc603
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399686"
---
# <a name="the-resolver-manager-resolvermgr-class"></a>Resolver Manager (ResolverMgr) 类
转换和消息传送服务使用的路由**ResolverMgr**类来执行解析。 ESB 动态转换和动态传递代理还使用**ResolverManager**类来执行实时 (JIT) 解析。  
  
 ESB 核心安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**具有程序集**ResolverMgr**全局程序集缓存中的类。  
  
 可以在你自己的代码中使用此类，需要执行的终结点或地图的动态解析。 此外可以扩展此类，以使用自定义解决方法。 但是，请记住，此类已支持可以使用任何自定义冲突解决程序程序集，应适用于你可能需要的任何替代解析算法解决机制。  
  
 下面的代码示例演示如何使用**ResolverMgr**类来解析终结点。  
  
```csharp  
// Move to retrieve the first resolver.  
resolvers = itineraryStep.ResolverCollection;  
resolver = resolvers.Current;  
  
// Pass the resolver configuration to the Resolver Manager for resolution.  
resolverDictionary = Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage, resolver);  
  
// Set transport properties.  
transportLocation = resolverDictionary.Item("Resolver.TransportLocation");  
transportType = resolverDictionary.Item("Resolver.TransportType");  
```  
  
 通常情况下，冲突解决程序连接字符串指定至少一个解决方法，如规则策略、 自定义程序集，XPath 语句或通用描述、 发现和集成 (UDDI) 的标签和服务器名称的属性值。 最后，它返回的冲突解决程序的事实数据，可以轻松地使用具体的冲突解决程序的自定义事实填充集合的字典对象。  
  
 有关 ESB 解决机制的工作原理的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。