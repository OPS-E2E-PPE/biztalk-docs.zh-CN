---
title: 在业务流程管理解决方案中有效使用 SSO |Microsoft Docs
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
ms.openlocfilehash: eda9b88ceb99e6487562ecc03f8f7009b09f533e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321679"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a><span data-ttu-id="84ff7-102">在业务流程管理解决方案中有效使用 SSO</span><span class="sxs-lookup"><span data-stu-id="84ff7-102">Using SSO Efficiently in the Business Process Management Solution</span></span>
<span data-ttu-id="84ff7-103">面向服务的解决方案，如业务流程管理解决方案使用企业单一登录 (SSO) 来存储配置值，例如订单处理阶段数。</span><span class="sxs-lookup"><span data-stu-id="84ff7-103">Like the Service Oriented solution, the Business Process Management solution uses Enterprise Single Sign-On (SSO) to store configuration values such as the number of order processing stages.</span></span> <span data-ttu-id="84ff7-104">它使用机密存储，因为它是只要安装 BizTalk 就存在，SSO 将缓存配置信息，以便值随时可用，并且它可以保护数据库连接字符串和密码等信息。</span><span class="sxs-lookup"><span data-stu-id="84ff7-104">It uses the secret store because it is present whenever BizTalk is installed, SSO caches the configuration information so that the values are readily available, and it can protect information such as database connection strings and passwords.</span></span> <span data-ttu-id="84ff7-105">所有这些原因，密钥存储区是配置信息的好地方即使单一登录不用于管理指向后端应用程序的连接。</span><span class="sxs-lookup"><span data-stu-id="84ff7-105">For all of these reasons, the secret store is a good place for the configuration information even if Single Sign-On weren't being used for managing connections to the backend applications.</span></span>  
  
 <span data-ttu-id="84ff7-106">若要减少延迟，解决方案时，可使用本地缓存来存储配置值。</span><span class="sxs-lookup"><span data-stu-id="84ff7-106">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="84ff7-107">该解决方案在每隔五分钟刷新的缓存。</span><span class="sxs-lookup"><span data-stu-id="84ff7-107">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="84ff7-108">本主题介绍该解决方案使用的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="84ff7-108">This topic describes the caching mechanism used by the solution.</span></span> <span data-ttu-id="84ff7-109">此解决方案采用稍有不同的方法来 SSO 缓存面向服务的解决方案。</span><span class="sxs-lookup"><span data-stu-id="84ff7-109">This solution takes a slightly different approach to SSO caching than does the service oriented solution.</span></span> <span data-ttu-id="84ff7-110">有关如何面向服务的解决方案的说明将缓存 SSO 值，请参阅[面向服务的解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="84ff7-110">For a description of how the service oriented solution caches SSO values, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md).</span></span>  
  
## <a name="caching-configuration-values-locally"></a><span data-ttu-id="84ff7-111">本地缓存配置值</span><span class="sxs-lookup"><span data-stu-id="84ff7-111">Caching Configuration Values Locally</span></span>  
 <span data-ttu-id="84ff7-112">业务流程管理解决方案使用单一对象的属性来提供对 SSO 值的访问。</span><span class="sxs-lookup"><span data-stu-id="84ff7-112">The business process management solution uses properties on a singleton object to provide access to the SSO values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84ff7-113">请注意，单一实例对象是一个对象，可以只有一个实例。</span><span class="sxs-lookup"><span data-stu-id="84ff7-113">Recall that a singleton object is an object that can have only one instance.</span></span> <span data-ttu-id="84ff7-114">有关单一对象和中创建它们的详细信息C#，请参阅[ http://go.microsoft.com/fwlink/?LinkId=58806 ](http://go.microsoft.com/fwlink/?LinkId=58806)。</span><span class="sxs-lookup"><span data-stu-id="84ff7-114">For more information about singleton objects and creating them in C#, see [http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806).</span></span>  
  
 <span data-ttu-id="84ff7-115">在解决方案中，业务流程首先检索单一对象，然后引用通过对象的属性的值。</span><span class="sxs-lookup"><span data-stu-id="84ff7-115">In the solution, an orchestration first retrieves the singleton object and then references the values through the object's properties.</span></span> <span data-ttu-id="84ff7-116">下面是从代码**OrderManager**业务流程：</span><span class="sxs-lookup"><span data-stu-id="84ff7-116">Here is code from the **OrderManager** orchestration:</span></span>  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 <span data-ttu-id="84ff7-117">业务流程调用**Singleton**方法**SsoConfigHelper**对象有权访问的对象的一个副本。</span><span class="sxs-lookup"><span data-stu-id="84ff7-117">The orchestration calls the **Singleton** method on the **SsoConfigHelper** object to get access to the one copy of the object.</span></span> <span data-ttu-id="84ff7-118">手中的对象，该业务流程检索处理阶段数**TotalStages**。</span><span class="sxs-lookup"><span data-stu-id="84ff7-118">With the object in hand, the orchestration retrieves the number of processing stages, **TotalStages**.</span></span>  
  
 <span data-ttu-id="84ff7-119">该解决方案按照通用方法来创建单一实例： 将构造函数设置为私有，要求该对象创建自身的实例和将其分配给私有变量，并通过方法或属性，提供对该变量的值的访问。</span><span class="sxs-lookup"><span data-stu-id="84ff7-119">The solution follows a common method of creating a singleton: make the constructor private, have the object create an instance of itself and assign that to a private variable, and, through a method or property, provide access to the value of that variable.</span></span> <span data-ttu-id="84ff7-120">**SsoConfigHelper**对象使用一个属性**单独**，以提供对其自身的单个副本的访问权限。</span><span class="sxs-lookup"><span data-stu-id="84ff7-120">The **SsoConfigHelper** object uses a property, **Singleton**, to provide access to the single copy of itself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84ff7-121">**SsoConfigHelper**对象使用静态构造函数来从 SSO 缓存中获取的初始值并设置刷新机制。</span><span class="sxs-lookup"><span data-stu-id="84ff7-121">The **SsoConfigHelper** object uses a static constructor to get the initial values from the SSO cache and to set up the refresh mechanism.</span></span> <span data-ttu-id="84ff7-122">由于不能调用静态构造函数，它将保留单一设计。</span><span class="sxs-lookup"><span data-stu-id="84ff7-122">Because a static constructor cannot be called, it preserves the singleton design.</span></span> <span data-ttu-id="84ff7-123">有关静态构造函数的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=59142 ](http://go.microsoft.com/fwlink/?LinkId=59142)。</span><span class="sxs-lookup"><span data-stu-id="84ff7-123">For more information about static constructors, see [http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142).</span></span>  
  
 <span data-ttu-id="84ff7-124">业务流程引用，无论是直接还是间接的所有对象必须都可序列化。</span><span class="sxs-lookup"><span data-stu-id="84ff7-124">All objects that an orchestration references, whether directly or indirectly, must be serializable.</span></span> <span data-ttu-id="84ff7-125">详细信息，请参阅"序列化"中[持久化和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="84ff7-125">For more information, see "Serialization" in [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span> <span data-ttu-id="84ff7-126">尽管**SsoConfigHelper**对象是一定是可序列化，如果引擎冻结业务流程中，当业务流程解除冻结后，将仍然使用单个对象的当前实例。</span><span class="sxs-lookup"><span data-stu-id="84ff7-126">Although the **SsoConfigHelper** object is necessarily serializable, if the engine dehydrates the orchestration, when the orchestration rehydrates it will still use the single, current instance of the object.</span></span> <span data-ttu-id="84ff7-127">有关序列化和 BizTalk Server 变量的详细信息，请参阅[业务流程变量类型](../core/orchestration-variable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="84ff7-127">For more information about serialization and BizTalk Server variables, see [Orchestration Variable Types](../core/orchestration-variable-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84ff7-128">面向服务的解决方案中的对象上的所有公共方法是静态的。</span><span class="sxs-lookup"><span data-stu-id="84ff7-128">All public methods on the object in the service oriented solution are static.</span></span> <span data-ttu-id="84ff7-129">因此该业务流程不需要将实例分配给一个变量，并且没有要进行序列化的类不需要。</span><span class="sxs-lookup"><span data-stu-id="84ff7-129">Thus the orchestration does not need to assign an instance to a variable, and there is no need for the class to be serialized.</span></span>  
  
 <span data-ttu-id="84ff7-130">**SsoConfigHelper**对象使用的相同机制来检索和刷新配置值，如面向服务的解决方案。</span><span class="sxs-lookup"><span data-stu-id="84ff7-130">The **SsoConfigHelper** object uses the same mechanisms to retrieve and refresh configuration values as does the service oriented solution.</span></span> <span data-ttu-id="84ff7-131">此外使用相同的锁定模式。</span><span class="sxs-lookup"><span data-stu-id="84ff7-131">The same pattern of locking is also used.</span></span> <span data-ttu-id="84ff7-132">有关这些机制的详细信息，请参阅[面向服务的解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)和的源代码**SsoConfigHelper**。</span><span class="sxs-lookup"><span data-stu-id="84ff7-132">For more information about these mechanisms, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md) and the source code for **SsoConfigHelper**.</span></span>  
  
 <span data-ttu-id="84ff7-133">在面向服务的解决方案中执行单一登录缓存，如业务流程管理解决方案实现**IPropertyBag**接口从**Microsoft.BizTalk.SSOClient.Interop**命名空间来存储的值。</span><span class="sxs-lookup"><span data-stu-id="84ff7-133">Like the Single Sign-On caching performed in the service oriented solution, the business process management solution implements the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace to store the values.</span></span> <span data-ttu-id="84ff7-134">使用业务流程管理解决方案**HybridDictionary**对象而非**NameValueCollection**对象。</span><span class="sxs-lookup"><span data-stu-id="84ff7-134">The business process management solution uses a **HybridDictionary** object rather than a **NameValueCollection** object.</span></span>  
  
 <span data-ttu-id="84ff7-135">与面向服务的解决方案，不同的业务流程管理解决方案公开的对象具有对应于配置数据的属性。</span><span class="sxs-lookup"><span data-stu-id="84ff7-135">Unlike the Service Oriented solution, the Business Process Management solution exposes an object with properties that correspond to the configuration data.</span></span> <span data-ttu-id="84ff7-136">这样，业务流程就不必处理消息类型之间的差异。</span><span class="sxs-lookup"><span data-stu-id="84ff7-136">This prevents the orchestration from having to deal with differences in message types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ff7-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="84ff7-137">See Also</span></span>  
 [<span data-ttu-id="84ff7-138">业务流程管理解决方案的实施重点</span><span class="sxs-lookup"><span data-stu-id="84ff7-138">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)