---
title: "业务规则 Framework 体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, caching
- Business Rules Framework, Rule Engine Update service
- rule store [Business Rules Framework]
- Policy class [Business Rules Engine]
- Business Rules Framework, architecture
- Business Rules Framework, RuleEngine class
- Business Rules Framework, Policy class
- Business Rules Framework, authoring tools
- RuleEngine class [Business Rules Engine]
- caching, Business Rules Framework
- Business Rules Framework, fact retrievers
- architecture, Business Rules Framework
- Business Rules Framework, rule store
ms.assetid: f5570cca-7664-4180-af9c-64ef90a0022b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4b23723d01a29606637689966cc07246cdfbc1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-framework-architecture"></a><span data-ttu-id="6ee34-102">业务规则 Framework 体系结构</span><span class="sxs-lookup"><span data-stu-id="6ee34-102">Business Rules Framework Architecture</span></span>
<span data-ttu-id="6ee34-103">下图显示了业务规则框架的组件结构。</span><span class="sxs-lookup"><span data-stu-id="6ee34-103">The following figure shows the component architecture of the Business Rules Framework.</span></span>  
  
 <span data-ttu-id="6ee34-104">![业务规则框架组件体系结构](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")</span><span class="sxs-lookup"><span data-stu-id="6ee34-104">![Business Rules Framework component architecture](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")</span></span>  
<span data-ttu-id="6ee34-105">Microsoft 业务规则框架结构</span><span class="sxs-lookup"><span data-stu-id="6ee34-105">Microsoft Business Rules Framework Architecture</span></span>  
  
 <span data-ttu-id="6ee34-106">以下段落对该框架的一些组件进行了说明。</span><span class="sxs-lookup"><span data-stu-id="6ee34-106">Some of the components of the framework are described in the following paragraphs.</span></span>  
  
## <a name="policy-class"></a><span data-ttu-id="6ee34-107">Policy 类</span><span class="sxs-lookup"><span data-stu-id="6ee34-107">Policy Class</span></span>  
 <span data-ttu-id="6ee34-108">A**策略**对象是业务策略的单个实例，并提供基于规则的应用程序使用的接口。</span><span class="sxs-lookup"><span data-stu-id="6ee34-108">A **Policy** object is a single instance of a business policy, and provides the interface that is used by rule-based applications.</span></span> <span data-ttu-id="6ee34-109">它提供一个抽象概念，使应用程序开发人员不必关心规则存储的位置，即可从规则存储中提取规则集，实例化基础规则引擎的实例，以及确保将长期事实添加到引擎中。</span><span class="sxs-lookup"><span data-stu-id="6ee34-109">It provides an abstraction that frees the application developer from concern about the location of the rule store, extracting rule sets from the rule store, instantiating instances of the underlying rule engine, and ensuring that long-term facts are asserted into the engine.</span></span> <span data-ttu-id="6ee34-110">在许多情况下，基于规则的应用程序使用的并发实例**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="6ee34-110">In many scenarios, a rule-based application uses concurrent instances of the **Policy** object.</span></span> <span data-ttu-id="6ee34-111">这些并行实例可以表示同一策略、同一策略的不同版本或不同策略的不同版本。</span><span class="sxs-lookup"><span data-stu-id="6ee34-111">These concurrent instances can represent the same policy, different versions of the same policy, or different versions of different policies.</span></span>  
  
## <a name="ruleengine-class"></a><span data-ttu-id="6ee34-112">RuleEngine 类</span><span class="sxs-lookup"><span data-stu-id="6ee34-112">RuleEngine Class</span></span>  
 <span data-ttu-id="6ee34-113">**RuleEngine**对象用作业务策略的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="6ee34-113">The **RuleEngine** object serves as the execution engine for business policies.</span></span> <span data-ttu-id="6ee34-114">它使用三个插件组件（转换器、推理引擎和跟踪侦听器）来实现业务策略。</span><span class="sxs-lookup"><span data-stu-id="6ee34-114">It uses three plug-in components (translator, inference engine, and tracking interceptor) for implementation.</span></span> <span data-ttu-id="6ee34-115">A **RuleEngine**对象采用**RuleSet**对象表示作为输入的业务策略并使用转换器推断引擎，为规则设置为实现配置的跟踪侦听器由规则集定义的业务策略。</span><span class="sxs-lookup"><span data-stu-id="6ee34-115">A **RuleEngine** object takes a **RuleSet** object representing a business policy as input and uses the translator, inference engine, and tracking interceptor configured for the rule set to implement the business policy defined by the rule set.</span></span>  
  
## <a name="fact-retriever"></a><span data-ttu-id="6ee34-116">事实检索器</span><span class="sxs-lookup"><span data-stu-id="6ee34-116">Fact Retriever</span></span>  
 <span data-ttu-id="6ee34-117">事实检索器是一种用户定义的可选插件组件，负责收集供业务策略使用的长期事实。</span><span class="sxs-lookup"><span data-stu-id="6ee34-117">A fact retriever is an optional, user-defined, plug-in component that is responsible for gathering long-term facts for use by business policies.</span></span> <span data-ttu-id="6ee34-118">有关详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee34-118">For more information, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
 <span data-ttu-id="6ee34-119">之前执行，**策略**对象实例提供其**RuleEngine**为它提供机会更新的规则引擎中的事实数据集的事实检索到的实例的工作内存。</span><span class="sxs-lookup"><span data-stu-id="6ee34-119">Before execution, a **Policy** object instance provides its **RuleEngine** instance to the fact retriever, giving it the opportunity to update the set of facts in the rule engine's working memory.</span></span> <span data-ttu-id="6ee34-120">有关详细信息，请参阅[短期事实 vs。长期事实](../core/short-term-facts-vs-long-term-facts.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee34-120">For more information, see [Short-Term Facts vs. Long-Term Facts](../core/short-term-facts-vs-long-term-facts.md).</span></span>  
  
## <a name="rule-engine-update-service"></a><span data-ttu-id="6ee34-121">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="6ee34-121">Rule Engine Update Service</span></span>  
 <span data-ttu-id="6ee34-122">规则引擎更新服务可以在分布式环境中提供动态业务策略更新。</span><span class="sxs-lookup"><span data-stu-id="6ee34-122">The Rule Engine Update service provides dynamic business policy updates in a distributed environment.</span></span> <span data-ttu-id="6ee34-123">一个自动启动 Microsoft Windows NT 服务应用程序负责订阅在更改业务策略时发生的策略部署和取消部署事件 。</span><span class="sxs-lookup"><span data-stu-id="6ee34-123">An autostart Microsoft Windows NT service application is responsible for subscribing to policy deployment and undeployment events that occur when business policies are changed.</span></span>  
  
 <span data-ttu-id="6ee34-124">在典型的企业方案中，业务策略在更新、测试和版本控制之后进行部署。</span><span class="sxs-lookup"><span data-stu-id="6ee34-124">In a typical enterprise scenario, business policies are deployed after being updated, tested, and versioned.</span></span> <span data-ttu-id="6ee34-125">部署包括将更新的策略添加到安全、持久化规则存储中，并可以选择对该存储执行逻辑，以便将与更新的策略有关的信息发布到所有有关方（请注意，是发布与策略有关的信息，而不是发布策略本身）。</span><span class="sxs-lookup"><span data-stu-id="6ee34-125">Deployment consists of adding the updated policy to a secure, persistent rule store and optionally executing logic on the store to publish information about the updated policy to all interested parties (note that information about the policy is published and not the policy itself).</span></span>  
  
 <span data-ttu-id="6ee34-126">在承载基于规则的应用程序的服务器上运行的规则引擎更新服务接收策略更新通知，并缓存信息以供后面使用。</span><span class="sxs-lookup"><span data-stu-id="6ee34-126">The Rule Engine Update service, running on a server hosting rule-based applications, receives the policy update notification and caches the information for subsequent use.</span></span> <span data-ttu-id="6ee34-127">通过将发布/订阅模型用于策略更新，您可以在不造成服务停机或中断的情况下以接近实时的方式更改业务策略。</span><span class="sxs-lookup"><span data-stu-id="6ee34-127">The use of a pub/sub model for policy updates enables you to change business policies in near real time without service downtime or interruption.</span></span>  
  
## <a name="policyvocabulary-authoring-tools"></a><span data-ttu-id="6ee34-128">策略/词汇创作工具</span><span class="sxs-lookup"><span data-stu-id="6ee34-128">Policy/Vocabulary Authoring Tools</span></span>  
 <span data-ttu-id="6ee34-129">在 Microsoft 中的业务规则编辑器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供策略和词汇创作向最终用户和开发人员的功能。</span><span class="sxs-lookup"><span data-stu-id="6ee34-129">The Business Rule Composer in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides policy and vocabulary authoring capabilities to both end users and developers.</span></span>  
  
## <a name="rule-store"></a><span data-ttu-id="6ee34-130">规则存储</span><span class="sxs-lookup"><span data-stu-id="6ee34-130">Rule Store</span></span>  
 <span data-ttu-id="6ee34-131">A*规则存储*是业务策略和词汇的存储库。</span><span class="sxs-lookup"><span data-stu-id="6ee34-131">A *rule store* is a repository for business policies and vocabularies.</span></span> <span data-ttu-id="6ee34-132">该存储库既可以是一个简单文件，也可以是安全、可伸缩、持久和可靠的数据库，例如 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="6ee34-132">The repository can be a simple file or a secure, scalable, persistent, and reliable database such as Microsoft SQL Server.</span></span> <span data-ttu-id="6ee34-133">（SQL Server 用作该框架的默认规则存储）。</span><span class="sxs-lookup"><span data-stu-id="6ee34-133">(SQL Server is used as the default rule store for the framework).</span></span>  
  
## <a name="caching"></a><span data-ttu-id="6ee34-134">Caching</span><span class="sxs-lookup"><span data-stu-id="6ee34-134">Caching</span></span>  
 <span data-ttu-id="6ee34-135">业务规则引擎框架提供的缓存机制**RuleEngine**实例。</span><span class="sxs-lookup"><span data-stu-id="6ee34-135">The Business Rules Engine Framework provides a caching mechanism for **RuleEngine** instances.</span></span> <span data-ttu-id="6ee34-136">每个**RuleEngine**实例包含的内存中表示形式的特定策略版本。</span><span class="sxs-lookup"><span data-stu-id="6ee34-136">Each **RuleEngine** instance contains an in-memory representation of a specific policy version.</span></span>  
  
 <span data-ttu-id="6ee34-137">以下步骤介绍过程中，当新**策略**实例已实例化 (使用 API 或执行的某个调用**调用规则**形状):</span><span class="sxs-lookup"><span data-stu-id="6ee34-137">The following steps describe the process when a new **Policy** instance is instantiated (either with a call on the API or execution of the **Call Rules** shape):</span></span>  
  
1.  <span data-ttu-id="6ee34-138">**策略**对象请求**RuleEngine**从规则引擎缓存实例。</span><span class="sxs-lookup"><span data-stu-id="6ee34-138">The **Policy** object requests a **RuleEngine** instance from the rule engine cache.</span></span>  
  
2.  <span data-ttu-id="6ee34-139">如果**RuleEngine**实例在缓存中，存在策略版本**RuleEngine**实例返回到**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="6ee34-139">If a **RuleEngine** instance for the policy version exists in the cache, the **RuleEngine** instance is returned to the **Policy** object.</span></span> <span data-ttu-id="6ee34-140">如果**RuleEngine**实例不可用，缓存创建的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ee34-140">If a **RuleEngine** instance is not available, the cache creates a new instance.</span></span> <span data-ttu-id="6ee34-141">当**RuleEngine**实例已实例化，则它不，反过来，如果其中一个配置策略版本创建新的事实检索器实例。</span><span class="sxs-lookup"><span data-stu-id="6ee34-141">When a **RuleEngine** instance is instantiated, it does, in turn, create a new fact retriever instance if one is configured for the policy version.</span></span>  
  
 <span data-ttu-id="6ee34-142">当**执行**方法调用**策略**对象，将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6ee34-142">When the **Execute** method is called on the **Policy** object, the following steps occur:</span></span>  
  
1.  <span data-ttu-id="6ee34-143">策略对象调用**UpdateFacts**如果事实检索器存在的事实检索器实例上的方法。</span><span class="sxs-lookup"><span data-stu-id="6ee34-143">The Policy object calls the **UpdateFacts**method on the fact retriever instance if a fact retriever exists.</span></span> <span data-ttu-id="6ee34-144">该方法的事实检索器的实现可能到的工作内存断言从长远来看事实**RuleEngine**。</span><span class="sxs-lookup"><span data-stu-id="6ee34-144">The fact retriever's implementation of the method may assert long term facts into the working memory of the **RuleEngine**.</span></span>  
  
2.  <span data-ttu-id="6ee34-145">**策略**对象断言中包含的短期事实数据**数组**为传入**执行**调用。</span><span class="sxs-lookup"><span data-stu-id="6ee34-145">The **Policy** object asserts the short term facts contained in the **Array** that was passed in the **Execute** call.</span></span>  
  
3.  <span data-ttu-id="6ee34-146">**策略**对象调用**执行**上**RuleEngine**。</span><span class="sxs-lookup"><span data-stu-id="6ee34-146">The **Policy** object calls **Execute** on the **RuleEngine**.</span></span>  
  
4.  <span data-ttu-id="6ee34-147">**RuleEngine**完成执行，并将控制权返回到**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="6ee34-147">The **RuleEngine** completes execution and returns control to the **Policy**object.</span></span>  
  
5.  <span data-ttu-id="6ee34-148">**策略**对象将收回从短期事实**RuleEngine**。</span><span class="sxs-lookup"><span data-stu-id="6ee34-148">The**Policy**object retracts the short term facts from the **RuleEngine**.</span></span> <span data-ttu-id="6ee34-149">事实检索器添加的长期事实将保留在规则引擎的工作内存中。</span><span class="sxs-lookup"><span data-stu-id="6ee34-149">The long term facts asserted by the fact retriever will remain in the working memory of the rule engine.</span></span>  
  
 <span data-ttu-id="6ee34-150">后**释放**方法调用**策略**对象， **RuleEngine**回规则引擎缓存中释放该实例。</span><span class="sxs-lookup"><span data-stu-id="6ee34-150">After the **Dispose** method is called on the **Policy** object, the **RuleEngine** instance is released back to the rule engine cache.</span></span>  
  
 <span data-ttu-id="6ee34-151">对于给定的策略版本（如果负载需要该版本），规则引擎缓存将具有多个规则引擎实例，并且每个规则引擎实例都具有自己的事实检索器实例。</span><span class="sxs-lookup"><span data-stu-id="6ee34-151">The rule engine cache will have multiple rule engine instances for a given policy version if the load requires it, and each rule engine instance has its own fact retriever instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee34-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ee34-152">See Also</span></span>  
 [<span data-ttu-id="6ee34-153">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="6ee34-153">Business Rules Engine</span></span>](../core/business-rules-engine.md)