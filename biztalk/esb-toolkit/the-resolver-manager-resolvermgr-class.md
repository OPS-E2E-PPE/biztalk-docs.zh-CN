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
# <a name="the-resolver-manager-resolvermgr-class"></a><span data-ttu-id="a6ae8-102">Resolver Manager (ResolverMgr) 类</span><span class="sxs-lookup"><span data-stu-id="a6ae8-102">The Resolver Manager (ResolverMgr) Class</span></span>
<span data-ttu-id="a6ae8-103">转换和消息传送服务使用的路由**ResolverMgr**类来执行解析。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-103">The Transform and Routing messaging services use the **ResolverMgr** class to perform resolution.</span></span> <span data-ttu-id="a6ae8-104">ESB 动态转换和动态传递代理还使用**ResolverManager**类来执行实时 (JIT) 解析。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-104">The ESB dynamic transformation and dynamic delivery agents also use the **ResolverManager** class to perform just-in-time (JIT) resolution.</span></span>  
  
 <span data-ttu-id="a6ae8-105">ESB 核心安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**具有程序集**ResolverMgr**全局程序集缓存中的类。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverMgr** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="a6ae8-106">可以在你自己的代码中使用此类，需要执行的终结点或地图的动态解析。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-106">You can use this class in your own code where you need to perform dynamic resolution of endpoints or maps.</span></span> <span data-ttu-id="a6ae8-107">此外可以扩展此类，以使用自定义解决方法。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-107">You can also extend this class to use a custom resolution method.</span></span> <span data-ttu-id="a6ae8-108">但是，请记住，此类已支持可以使用任何自定义冲突解决程序程序集，应适用于你可能需要的任何替代解析算法解决机制。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-108">However, keep in mind that the class already supports a resolution mechanism that can use any custom resolver assembly, which should accommodate any alternative resolution algorithm you may require.</span></span>  
  
 <span data-ttu-id="a6ae8-109">下面的代码示例演示如何使用**ResolverMgr**类来解析终结点。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-109">The following code example shows how to use the **ResolverMgr** class to resolve an endpoint.</span></span>  
  
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
  
 <span data-ttu-id="a6ae8-110">通常情况下，冲突解决程序连接字符串指定至少一个解决方法，如规则策略、 自定义程序集，XPath 语句或通用描述、 发现和集成 (UDDI) 的标签和服务器名称的属性值。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-110">Usually, your resolver connection string specifies the property values for at least one resolution method, such as a rules policy, custom assembly, XPath statement, or Universal Description, Discovery, and Integration (UDDI) label and server name.</span></span> <span data-ttu-id="a6ae8-111">最后，它返回的冲突解决程序的事实数据，可以轻松地使用具体的冲突解决程序的自定义事实填充集合的字典对象。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-111">Finally, it returns a dictionary object with a collection of resolver facts, which can be easily populated with custom facts from a concrete resolver.</span></span>  
  
 <span data-ttu-id="a6ae8-112">有关 ESB 解决机制的工作原理的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="a6ae8-112">For more information about how the ESB resolution mechanism works, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>