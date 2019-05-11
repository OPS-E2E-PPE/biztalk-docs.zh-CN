---
title: 业务规则框架体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8ee592cbb83f9094a1430d12b08a573d858c88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357685"
---
# <a name="business-rules-framework-architecture"></a><span data-ttu-id="1cda5-102">业务规则框架体系结构</span><span class="sxs-lookup"><span data-stu-id="1cda5-102">Business Rules Framework Architecture</span></span>
<span data-ttu-id="1cda5-103">下图显示了业务规则框架的组件体系结构。</span><span class="sxs-lookup"><span data-stu-id="1cda5-103">The following figure shows the component architecture of the Business Rules Framework.</span></span>  
  
 <span data-ttu-id="1cda5-104">![业务规则框架组件体系结构](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")</span><span class="sxs-lookup"><span data-stu-id="1cda5-104">![Business Rules Framework component architecture](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")</span></span>  
<span data-ttu-id="1cda5-105">Microsoft 业务规则框架体系结构</span><span class="sxs-lookup"><span data-stu-id="1cda5-105">Microsoft Business Rules Framework Architecture</span></span>  
  
 <span data-ttu-id="1cda5-106">下面的段落中介绍了一些 framework 的组件。</span><span class="sxs-lookup"><span data-stu-id="1cda5-106">Some of the components of the framework are described in the following paragraphs.</span></span>  
  
## <a name="policy-class"></a><span data-ttu-id="1cda5-107">Policy 类</span><span class="sxs-lookup"><span data-stu-id="1cda5-107">Policy Class</span></span>  
 <span data-ttu-id="1cda5-108">一个**策略**对象是业务策略，一个单一实例，并提供基于规则的应用程序使用的接口。</span><span class="sxs-lookup"><span data-stu-id="1cda5-108">A **Policy** object is a single instance of a business policy, and provides the interface that is used by rule-based applications.</span></span> <span data-ttu-id="1cda5-109">它提供了抽象概念，使应用程序开发人员从规则存储的位置有关的问题实例化基础规则引擎的实例，并确保长期事实添加到从规则存储中提取规则集引擎。</span><span class="sxs-lookup"><span data-stu-id="1cda5-109">It provides an abstraction that frees the application developer from concern about the location of the rule store, extracting rule sets from the rule store, instantiating instances of the underlying rule engine, and ensuring that long-term facts are asserted into the engine.</span></span> <span data-ttu-id="1cda5-110">在许多情况下，基于规则的应用程序使用的并发实例**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="1cda5-110">In many scenarios, a rule-based application uses concurrent instances of the **Policy** object.</span></span> <span data-ttu-id="1cda5-111">这些并行实例可以表示相同的策略、 同一策略的不同版本或不同版本的不同的策略。</span><span class="sxs-lookup"><span data-stu-id="1cda5-111">These concurrent instances can represent the same policy, different versions of the same policy, or different versions of different policies.</span></span>  
  
## <a name="ruleengine-class"></a><span data-ttu-id="1cda5-112">RuleEngine 类</span><span class="sxs-lookup"><span data-stu-id="1cda5-112">RuleEngine Class</span></span>  
 <span data-ttu-id="1cda5-113">**RuleEngine**对象充当业务策略的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="1cda5-113">The **RuleEngine** object serves as the execution engine for business policies.</span></span> <span data-ttu-id="1cda5-114">它使用三个插件组件 （转换器、 推理引擎和跟踪侦听器） 来实现。</span><span class="sxs-lookup"><span data-stu-id="1cda5-114">It uses three plug-in components (translator, inference engine, and tracking interceptor) for implementation.</span></span> <span data-ttu-id="1cda5-115">一个**RuleEngine**对象采用**RuleSet**对象表示业务策略作为输入，并使用转换器、 推理引擎和跟踪侦听器配置为规则集来实现业务规则集定义的策略。</span><span class="sxs-lookup"><span data-stu-id="1cda5-115">A **RuleEngine** object takes a **RuleSet** object representing a business policy as input and uses the translator, inference engine, and tracking interceptor configured for the rule set to implement the business policy defined by the rule set.</span></span>  
  
## <a name="fact-retriever"></a><span data-ttu-id="1cda5-116">事实检索器</span><span class="sxs-lookup"><span data-stu-id="1cda5-116">Fact Retriever</span></span>  
 <span data-ttu-id="1cda5-117">事实检索器是一个可选的、 用户定义的插件组件负责收集供业务策略使用的长期事实。</span><span class="sxs-lookup"><span data-stu-id="1cda5-117">A fact retriever is an optional, user-defined, plug-in component that is responsible for gathering long-term facts for use by business policies.</span></span> <span data-ttu-id="1cda5-118">有关详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。</span><span class="sxs-lookup"><span data-stu-id="1cda5-118">For more information, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
 <span data-ttu-id="1cda5-119">在执行前**策略**对象实例提供了其**RuleEngine**对事实检索器，让其有机会更新的规则引擎中的事实数据集的实例的工作内存。</span><span class="sxs-lookup"><span data-stu-id="1cda5-119">Before execution, a **Policy** object instance provides its **RuleEngine** instance to the fact retriever, giving it the opportunity to update the set of facts in the rule engine's working memory.</span></span> <span data-ttu-id="1cda5-120">有关详细信息，请参阅[短期事实与。长期事实](../core/short-term-facts-vs-long-term-facts.md)。</span><span class="sxs-lookup"><span data-stu-id="1cda5-120">For more information, see [Short-Term Facts vs. Long-Term Facts](../core/short-term-facts-vs-long-term-facts.md).</span></span>  
  
## <a name="rule-engine-update-service"></a><span data-ttu-id="1cda5-121">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="1cda5-121">Rule Engine Update Service</span></span>  
 <span data-ttu-id="1cda5-122">规则引擎更新服务提供了在分布式环境中的动态业务策略更新。</span><span class="sxs-lookup"><span data-stu-id="1cda5-122">The Rule Engine Update service provides dynamic business policy updates in a distributed environment.</span></span> <span data-ttu-id="1cda5-123">一个自动启动 Microsoft Windows NT 服务应用程序负责订阅策略部署和取消部署在更改业务策略时发生的事件。</span><span class="sxs-lookup"><span data-stu-id="1cda5-123">An autostart Microsoft Windows NT service application is responsible for subscribing to policy deployment and undeployment events that occur when business policies are changed.</span></span>  
  
 <span data-ttu-id="1cda5-124">在典型的企业方案中，业务策略进行部署后正在更新、 测试和版本控制。</span><span class="sxs-lookup"><span data-stu-id="1cda5-124">In a typical enterprise scenario, business policies are deployed after being updated, tested, and versioned.</span></span> <span data-ttu-id="1cda5-125">部署包含将更新后的策略添加到安全、 持久化规则存储和 （可选） 若要将更新后的策略有关的信息发布到所有相关方对存储区执行逻辑 (请注意，发布有关策略的信息，而不策略本身）。</span><span class="sxs-lookup"><span data-stu-id="1cda5-125">Deployment consists of adding the updated policy to a secure, persistent rule store and optionally executing logic on the store to publish information about the updated policy to all interested parties (note that information about the policy is published and not the policy itself).</span></span>  
  
 <span data-ttu-id="1cda5-126">托管的基于规则的应用程序的服务器上运行的规则引擎更新服务接收策略更新通知，并缓存信息以供后续使用。</span><span class="sxs-lookup"><span data-stu-id="1cda5-126">The Rule Engine Update service, running on a server hosting rule-based applications, receives the policy update notification and caches the information for subsequent use.</span></span> <span data-ttu-id="1cda5-127">发布/订阅模型用于策略更新，可更改而无需服务停机或中断的近乎实时的业务策略。</span><span class="sxs-lookup"><span data-stu-id="1cda5-127">The use of a pub/sub model for policy updates enables you to change business policies in near real time without service downtime or interruption.</span></span>  
  
## <a name="policyvocabulary-authoring-tools"></a><span data-ttu-id="1cda5-128">策略/词汇创作工具</span><span class="sxs-lookup"><span data-stu-id="1cda5-128">Policy/Vocabulary Authoring Tools</span></span>  
 <span data-ttu-id="1cda5-129">在 Microsoft 业务规则编辑器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供策略和词汇创作向最终用户和开发人员的功能。</span><span class="sxs-lookup"><span data-stu-id="1cda5-129">The Business Rule Composer in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides policy and vocabulary authoring capabilities to both end users and developers.</span></span>  
  
## <a name="rule-store"></a><span data-ttu-id="1cda5-130">规则存储</span><span class="sxs-lookup"><span data-stu-id="1cda5-130">Rule Store</span></span>  
 <span data-ttu-id="1cda5-131">一个*规则存储*是业务策略和词汇的存储库。</span><span class="sxs-lookup"><span data-stu-id="1cda5-131">A *rule store* is a repository for business policies and vocabularies.</span></span> <span data-ttu-id="1cda5-132">存储库可以是一个简单的文件或安全、 可缩放、 持久的且可靠的数据库，例如 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1cda5-132">The repository can be a simple file or a secure, scalable, persistent, and reliable database such as Microsoft SQL Server.</span></span> <span data-ttu-id="1cda5-133">（SQL Server 用作默认规则存储为 framework）。</span><span class="sxs-lookup"><span data-stu-id="1cda5-133">(SQL Server is used as the default rule store for the framework).</span></span>  
  
## <a name="caching"></a><span data-ttu-id="1cda5-134">Caching</span><span class="sxs-lookup"><span data-stu-id="1cda5-134">Caching</span></span>  
 <span data-ttu-id="1cda5-135">业务规则引擎框架提供的一种缓存机制**RuleEngine**实例。</span><span class="sxs-lookup"><span data-stu-id="1cda5-135">The Business Rules Engine Framework provides a caching mechanism for **RuleEngine** instances.</span></span> <span data-ttu-id="1cda5-136">每个**RuleEngine**实例包含特定策略版本的内存中表示形式。</span><span class="sxs-lookup"><span data-stu-id="1cda5-136">Each **RuleEngine** instance contains an in-memory representation of a specific policy version.</span></span>  
  
 <span data-ttu-id="1cda5-137">以下步骤介绍了如何新建**策略**实例进行实例化 (通过调用 API，或执行**调用规则**形状):</span><span class="sxs-lookup"><span data-stu-id="1cda5-137">The following steps describe the process when a new **Policy** instance is instantiated (either with a call on the API or execution of the **Call Rules** shape):</span></span>  
  
1. <span data-ttu-id="1cda5-138">**策略**对象请求**RuleEngine**从规则引擎缓存实例。</span><span class="sxs-lookup"><span data-stu-id="1cda5-138">The **Policy** object requests a **RuleEngine** instance from the rule engine cache.</span></span>  
  
2. <span data-ttu-id="1cda5-139">如果**RuleEngine**实例的策略版本在缓存中，存在**RuleEngine**实例返回到**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="1cda5-139">If a **RuleEngine** instance for the policy version exists in the cache, the **RuleEngine** instance is returned to the **Policy** object.</span></span> <span data-ttu-id="1cda5-140">如果**RuleEngine**实例不可用，请在缓存创建的新实例。</span><span class="sxs-lookup"><span data-stu-id="1cda5-140">If a **RuleEngine** instance is not available, the cache creates a new instance.</span></span> <span data-ttu-id="1cda5-141">当**RuleEngine**实例被实例化，匹配，反过来，如果其中一个配置为策略版本创建新的事实检索器实例。</span><span class="sxs-lookup"><span data-stu-id="1cda5-141">When a **RuleEngine** instance is instantiated, it does, in turn, create a new fact retriever instance if one is configured for the policy version.</span></span>  
  
   <span data-ttu-id="1cda5-142">当**Execute**上调用方法**策略**对象，将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1cda5-142">When the **Execute** method is called on the **Policy** object, the following steps occur:</span></span>  
  
3. <span data-ttu-id="1cda5-143">策略的对象调用**UpdateFacts**事实检索器实例中，如果存在事实检索器上的方法。</span><span class="sxs-lookup"><span data-stu-id="1cda5-143">The Policy object calls the **UpdateFacts**method on the fact retriever instance if a fact retriever exists.</span></span> <span data-ttu-id="1cda5-144">方法的事实检索器实现可能会添加到工作内存中的长期事实**RuleEngine**。</span><span class="sxs-lookup"><span data-stu-id="1cda5-144">The fact retriever's implementation of the method may assert long term facts into the working memory of the **RuleEngine**.</span></span>  
  
4. <span data-ttu-id="1cda5-145">**策略**对象添加中包含的短期事实**数组**为传入**Execute**调用。</span><span class="sxs-lookup"><span data-stu-id="1cda5-145">The **Policy** object asserts the short term facts contained in the **Array** that was passed in the **Execute** call.</span></span>  
  
5. <span data-ttu-id="1cda5-146">**策略**对象调用**Execute**上**RuleEngine**。</span><span class="sxs-lookup"><span data-stu-id="1cda5-146">The **Policy** object calls **Execute** on the **RuleEngine**.</span></span>  
  
6. <span data-ttu-id="1cda5-147">**RuleEngine**完成执行，并将控制权返回给**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="1cda5-147">The **RuleEngine** completes execution and returns control to the **Policy**object.</span></span>  
  
7. <span data-ttu-id="1cda5-148">**策略**对象取消从短期事实**RuleEngine**。</span><span class="sxs-lookup"><span data-stu-id="1cda5-148">The**Policy**object retracts the short term facts from the **RuleEngine**.</span></span> <span data-ttu-id="1cda5-149">添加事实检索器的长期事实将保留在规则引擎工作内存中。</span><span class="sxs-lookup"><span data-stu-id="1cda5-149">The long term facts asserted by the fact retriever will remain in the working memory of the rule engine.</span></span>  
  
   <span data-ttu-id="1cda5-150">之后**Dispose**上调用方法**策略**对象， **RuleEngine**实例被释放回规则引擎缓存。</span><span class="sxs-lookup"><span data-stu-id="1cda5-150">After the **Dispose** method is called on the **Policy** object, the **RuleEngine** instance is released back to the rule engine cache.</span></span>  
  
   <span data-ttu-id="1cda5-151">如果负载需要它，并且每个规则引擎实例都具有其自己的事实检索器实例，则规则引擎缓存将具有给定的策略版本的多个规则引擎实例。</span><span class="sxs-lookup"><span data-stu-id="1cda5-151">The rule engine cache will have multiple rule engine instances for a given policy version if the load requires it, and each rule engine instance has its own fact retriever instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cda5-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cda5-152">See Also</span></span>  
 [<span data-ttu-id="1cda5-153">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="1cda5-153">Business Rules Engine</span></span>](../core/business-rules-engine.md)