---
title: 冲突解决程序管理器 (ResolverMgr) 类 |Microsoft 文档
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
ms.openlocfilehash: 6621ad0c6b9edb5bf93950f9b9d05a7655f0e36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294741"
---
# <a name="the-resolver-manager-resolvermgr-class"></a><span data-ttu-id="85f48-102">冲突解决程序管理器 (ResolverMgr) 类</span><span class="sxs-lookup"><span data-stu-id="85f48-102">The Resolver Manager (ResolverMgr) Class</span></span>
<span data-ttu-id="85f48-103">转换和路由消息传递服务会使用**ResolverMgr**类来执行解析。</span><span class="sxs-lookup"><span data-stu-id="85f48-103">The Transform and Routing messaging services use the **ResolverMgr** class to perform resolution.</span></span> <span data-ttu-id="85f48-104">ESB 动态转换和动态传递代理还使用**ResolverManager**类来执行实时 (JIT) 解析。</span><span class="sxs-lookup"><span data-stu-id="85f48-104">The ESB dynamic transformation and dynamic delivery agents also use the **ResolverManager** class to perform just-in-time (JIT) resolution.</span></span>  
  
 <span data-ttu-id="85f48-105">ESB 核心安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**具有程序集**ResolverMgr**全局程序集缓存中的类。</span><span class="sxs-lookup"><span data-stu-id="85f48-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverMgr** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="85f48-106">可以在你自己的代码中使用此类，你需要执行的终结点或地图的动态解析。</span><span class="sxs-lookup"><span data-stu-id="85f48-106">You can use this class in your own code where you need to perform dynamic resolution of endpoints or maps.</span></span> <span data-ttu-id="85f48-107">你还可以扩展此类，以使用自定义解决方法。</span><span class="sxs-lookup"><span data-stu-id="85f48-107">You can also extend this class to use a custom resolution method.</span></span> <span data-ttu-id="85f48-108">但是，请记住，该类已支持可以使用任何自定义解析程序程序集，其中应适用于你可能需要的任何备用解析算法解决机制。</span><span class="sxs-lookup"><span data-stu-id="85f48-108">However, keep in mind that the class already supports a resolution mechanism that can use any custom resolver assembly, which should accommodate any alternative resolution algorithm you may require.</span></span>  
  
 <span data-ttu-id="85f48-109">下面的代码示例演示如何使用**ResolverMgr**类来解析终结点。</span><span class="sxs-lookup"><span data-stu-id="85f48-109">The following code example shows how to use the **ResolverMgr** class to resolve an endpoint.</span></span>  
  
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
  
 <span data-ttu-id="85f48-110">通常情况下，冲突解决程序连接字符串指定至少一个解决方法，如规则策略、 自定义程序集、 XPath 语句或通用、 描述、 发现和集成 (UDDI) 的标签和服务器名称的属性值。</span><span class="sxs-lookup"><span data-stu-id="85f48-110">Usually, your resolver connection string specifies the property values for at least one resolution method, such as a rules policy, custom assembly, XPath statement, or Universal Description, Discovery, and Integration (UDDI) label and server name.</span></span> <span data-ttu-id="85f48-111">最后，它返回的冲突解决程序事实，可以使用从具体的解析程序的自定义事实轻松填充的集合的字典对象。</span><span class="sxs-lookup"><span data-stu-id="85f48-111">Finally, it returns a dictionary object with a collection of resolver facts, which can be easily populated with custom facts from a concrete resolver.</span></span>  
  
 <span data-ttu-id="85f48-112">有关 ESB 解决机制的工作原理的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="85f48-112">For more information about how the ESB resolution mechanism works, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>