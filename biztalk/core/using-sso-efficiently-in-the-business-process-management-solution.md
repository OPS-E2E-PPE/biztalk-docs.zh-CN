---
title: 在业务流程管理解决方案中有效地使用 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, process management solutions
- SSO, configuration values
- caching, configuration values [SSO]
- SSO, caching
- process management solution tutorial, SSO
ms.assetid: 39fbc42d-caa4-4003-a13b-5cde578eb5e1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99575e54b887124bfa4c33fc5257cd057ea818fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288517"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a><span data-ttu-id="9ae7a-102">在业务流程管理解决方案中有效地使用 SSO</span><span class="sxs-lookup"><span data-stu-id="9ae7a-102">Using SSO Efficiently in the Business Process Management Solution</span></span>
<span data-ttu-id="9ae7a-103">与面向服务的解决方案类似，业务流程管理解决方案使用企业单一登录 (SSO) 来存储配置值，例如订单处理阶段数。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-103">Like the Service Oriented solution, the Business Process Management solution uses Enterprise Single Sign-On (SSO) to store configuration values such as the number of order processing stages.</span></span> <span data-ttu-id="9ae7a-104">由于只要安装 BizTalk 就会存在密钥存储区，因此该解决方案将使用密钥存储区；SSO 将缓存配置信息以便随时可以使用这些值，并且可以保护诸如数据库连接字符串和密码之类的信息。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-104">It uses the secret store because it is present whenever BizTalk is installed, SSO caches the configuration information so that the values are readily available, and it can protect information such as database connection strings and passwords.</span></span> <span data-ttu-id="9ae7a-105">由于上述这些原因，因此密钥存储区是配置信息的适当位置，即使不将单一登录用于管理指向后端应用程序的连接。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-105">For all of these reasons, the secret store is a good place for the configuration information even if Single Sign-On weren't being used for managing connections to the backend applications.</span></span>  
  
 <span data-ttu-id="9ae7a-106">为缩短延迟时间，该解决方案使用本地缓存来存储配置值。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-106">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="9ae7a-107">该解决方案每隔五分钟刷新一次缓存。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-107">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="9ae7a-108">本主题将介绍该解决方案使用的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-108">This topic describes the caching mechanism used by the solution.</span></span> <span data-ttu-id="9ae7a-109">此解决方案采用的 SSO 缓存方法与面向服务的解决方案采用的方法略有不同。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-109">This solution takes a slightly different approach to SSO caching than does the service oriented solution.</span></span> <span data-ttu-id="9ae7a-110">有关如何面向解决方案服务的说明缓存 SSO 值，请参阅[服务面向解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-110">For a description of how the service oriented solution caches SSO values, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md).</span></span>  
  
## <a name="caching-configuration-values-locally"></a><span data-ttu-id="9ae7a-111">在本地缓存配置值</span><span class="sxs-lookup"><span data-stu-id="9ae7a-111">Caching Configuration Values Locally</span></span>  
 <span data-ttu-id="9ae7a-112">业务流程管理解决方案使用单一对象的属性来提供对 SSO 值的访问。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-112">The business process management solution uses properties on a singleton object to provide access to the SSO values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ae7a-113">请注意，单一对象是只能具有一个实例的对象。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-113">Recall that a singleton object is an object that can have only one instance.</span></span> <span data-ttu-id="9ae7a-114">有关单一实例对象并在 C# 中创建它们的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806)。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-114">For more information about singleton objects and creating them in C#, see [http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806).</span></span>  
  
 <span data-ttu-id="9ae7a-115">在解决方案中，业务流程首先检索单一实例对象，并随后引用通过对象的属性的值。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-115">In the solution, an orchestration first retrieves the singleton object and then references the values through the object's properties.</span></span> <span data-ttu-id="9ae7a-116">以下是从代码**OrderManager**业务流程：</span><span class="sxs-lookup"><span data-stu-id="9ae7a-116">Here is code from the **OrderManager** orchestration:</span></span>  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 <span data-ttu-id="9ae7a-117">业务流程调用**Singleton**方法**SsoConfigHelper**对象才能访问对象的一个副本。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-117">The orchestration calls the **Singleton** method on the **SsoConfigHelper** object to get access to the one copy of the object.</span></span> <span data-ttu-id="9ae7a-118">业务流程与中现有对象，检索的数目处理阶段**TotalStages**。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-118">With the object in hand, the orchestration retrieves the number of processing stages, **TotalStages**.</span></span>  
  
 <span data-ttu-id="9ae7a-119">解决方案遵循创建单一实例的常见方法： 将设为私有构造函数，必须创建自身的一个实例和分配给一个私有变量，并通过方法或属性中，提供该变量的值的访问的对象。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-119">The solution follows a common method of creating a singleton: make the constructor private, have the object create an instance of itself and assign that to a private variable, and, through a method or property, provide access to the value of that variable.</span></span> <span data-ttu-id="9ae7a-120">**SsoConfigHelper**对象使用属性， **Singleton**，以提供对其自身的单个副本的访问。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-120">The **SsoConfigHelper** object uses a property, **Singleton**, to provide access to the single copy of itself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ae7a-121">**SsoConfigHelper**对象使用的静态构造函数来从 SSO 缓存中获取初始值以及设置刷新机制。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-121">The **SsoConfigHelper** object uses a static constructor to get the initial values from the SSO cache and to set up the refresh mechanism.</span></span> <span data-ttu-id="9ae7a-122">由于无法调用静态构造函数，因此该函数将保留单一设计。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-122">Because a static constructor cannot be called, it preserves the singleton design.</span></span> <span data-ttu-id="9ae7a-123">有关静态构造函数的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142)。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-123">For more information about static constructors, see [http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142).</span></span>  
  
 <span data-ttu-id="9ae7a-124">业务流程引用（无论是直接还是间接引用）的所有对象都必须是可序列化的。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-124">All objects that an orchestration references, whether directly or indirectly, must be serializable.</span></span> <span data-ttu-id="9ae7a-125">有关详细信息，请参阅"序列化"[持久性和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-125">For more information, see "Serialization" in [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span> <span data-ttu-id="9ae7a-126">尽管**SsoConfigHelper**对象是一定可序列化，如果引擎 dehydrates 业务流程，当它仍将业务流程 rehydrates 使用单个对象的当前实例。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-126">Although the **SsoConfigHelper** object is necessarily serializable, if the engine dehydrates the orchestration, when the orchestration rehydrates it will still use the single, current instance of the object.</span></span> <span data-ttu-id="9ae7a-127">有关序列化和 BizTalk Server 变量的详细信息，请参阅[Orchestration 变量类型](../core/orchestration-variable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-127">For more information about serialization and BizTalk Server variables, see [Orchestration Variable Types](../core/orchestration-variable-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ae7a-128">面向服务的解决方案中的对象上的所有公共方法都是静态的。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-128">All public methods on the object in the service oriented solution are static.</span></span> <span data-ttu-id="9ae7a-129">因此，该业务流程不需要向变量分配实例，也不需要对类进行序列化。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-129">Thus the orchestration does not need to assign an instance to a variable, and there is no need for the class to be serialized.</span></span>  
  
 <span data-ttu-id="9ae7a-130">**SsoConfigHelper**对象使用了相同的机制来检索和面向服务解决方案一样刷新配置值。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-130">The **SsoConfigHelper** object uses the same mechanisms to retrieve and refresh configuration values as does the service oriented solution.</span></span> <span data-ttu-id="9ae7a-131">也使用相同的锁定模式。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-131">The same pattern of locking is also used.</span></span> <span data-ttu-id="9ae7a-132">有关这些机制的详细信息，请参阅[服务面向解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)和的源代码**SsoConfigHelper**。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-132">For more information about these mechanisms, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md) and the source code for **SsoConfigHelper**.</span></span>  
  
 <span data-ttu-id="9ae7a-133">业务流程管理解决方案上单一登录缓存在面向服务解决方案中执行，如实现**IPropertyBag**接口从**Microsoft.BizTalk.SSOClient.Interop**命名空间来存储的值。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-133">Like the Single Sign-On caching performed in the service oriented solution, the business process management solution implements the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace to store the values.</span></span> <span data-ttu-id="9ae7a-134">业务流程管理解决方案使用**HybridDictionary**对象而不是**NameValueCollection**对象。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-134">The business process management solution uses a **HybridDictionary** object rather than a **NameValueCollection** object.</span></span>  
  
 <span data-ttu-id="9ae7a-135">与面向服务的解决方案不同，业务流程管理解决方案公开了一个具有对应于配置数据的属性的对象。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-135">Unlike the Service Oriented solution, the Business Process Management solution exposes an object with properties that correspond to the configuration data.</span></span> <span data-ttu-id="9ae7a-136">这样，业务流程就不必处理消息类型之间的差异。</span><span class="sxs-lookup"><span data-stu-id="9ae7a-136">This prevents the orchestration from having to deal with differences in message types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae7a-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ae7a-137">See Also</span></span>  
 [<span data-ttu-id="9ae7a-138">实现突出显示的业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="9ae7a-138">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)