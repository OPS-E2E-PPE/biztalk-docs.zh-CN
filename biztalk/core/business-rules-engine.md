---
title: "业务规则引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Engine
- Business Rules Engine
- Business Rules Engine, rules
- Business Rules Engine, about Business Rules Engine
ms.assetid: 87b38507-9f6d-4863-88a6-9c20f15a4e55
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d99cff10324f1cf1ba97d99431524474ed5f039b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-engine"></a><span data-ttu-id="ac730-102">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="ac730-102">Business Rules Engine</span></span>
<span data-ttu-id="ac730-103">业务规则框架是一个符合 Microsoft .NET 的类库。</span><span class="sxs-lookup"><span data-stu-id="ac730-103">The Business Rules Framework is a Microsoft .NET-compliant class library.</span></span> <span data-ttu-id="ac730-104">它提供了一个有效的推理引擎，可以将高可读性、描述性和语义丰富的规则链接到任何业务对象（.NET 组件）、XML 文档或数据库表。</span><span class="sxs-lookup"><span data-stu-id="ac730-104">It provides an efficient inference engine that can link highly readable, declarative, semantically rich rules to any business objects (.NET components), XML documents, or database tables.</span></span> <span data-ttu-id="ac730-105">应用程序开发人员可以通过使用作用于 .NET 对象、数据库表和 XML 文档中所包含信息（事实）的小型业务逻辑生成块（小型规则集）来构造规则，进而构建业务规则。</span><span class="sxs-lookup"><span data-stu-id="ac730-105">Application developers can build business rules by constructing rules from small building blocks of business logic (small rule sets) that operate on information (facts) contained in .NET objects, database tables, and XML documents.</span></span> <span data-ttu-id="ac730-106">此设计模式可以提高代码重用率，简化设计，以及促进业务逻辑的模块化。</span><span class="sxs-lookup"><span data-stu-id="ac730-106">This design pattern promotes code reuse, design simplicity, and modularity of business logic.</span></span> <span data-ttu-id="ac730-107">此外，不会对业务应用程序的结构或设计强制应用该规则引擎。</span><span class="sxs-lookup"><span data-stu-id="ac730-107">In addition, the rule engine does not impose on the architecture or design of business applications.</span></span> <span data-ttu-id="ac730-108">事实上，您可以通过直接调用规则引擎向业务应用程序中添加规则技术，也可以使用外部逻辑来调用您的业务对象而不必对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="ac730-108">In fact, you can add rule technology to a business application by directly invoking the rule engine, or you can have external logic that invokes your business objects without modifying them.</span></span> <span data-ttu-id="ac730-109">简而言之，该技术使得开发人员只需投入极少的精力用于创建和维护应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac730-109">In short, the technology enables developers to create and maintain applications with minimal effort.</span></span>  
  
 <span data-ttu-id="ac730-110">在制订基于规则的应用程序的开发计划时，首先需要确定如何将规则融入您的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="ac730-110">In planning development of a rule-based application, you first need to determine how rules will fit into your business processes.</span></span> <span data-ttu-id="ac730-111">您的应用程序将创建一个策略实例，并为其提供要操作的数据（或事实）。</span><span class="sxs-lookup"><span data-stu-id="ac730-111">Your application will create an instance of a policy and supply it with data, or facts, on which to operate.</span></span> <span data-ttu-id="ac730-112">该策略对象包含规则引擎，并提供了一个单一入口点（通过该入口点来运行规则引擎）。</span><span class="sxs-lookup"><span data-stu-id="ac730-112">The policy object encapsulates the rule engine and provides a single point of entry through which to run it.</span></span>  
  
 <span data-ttu-id="ac730-113">您还将需要制订规则设计的开发和测试计划。</span><span class="sxs-lookup"><span data-stu-id="ac730-113">You also will need to plan for the development and testing of your rules design.</span></span> <span data-ttu-id="ac730-114">您必须考虑将如何部署和更新策略。</span><span class="sxs-lookup"><span data-stu-id="ac730-114">You must consider how you are going to deploy and update your policies.</span></span> <span data-ttu-id="ac730-115">您可能需要跟踪规则引擎的执行进度，并监视其当前状态。</span><span class="sxs-lookup"><span data-stu-id="ac730-115">You will likely want to track the progress of your rule engine's execution and monitor its current state.</span></span>  
  
 <span data-ttu-id="ac730-116">在制订规则开发计划时，请考虑执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ac730-116">Account for the following steps as you plan your rules development:</span></span>  
  
1.  <span data-ttu-id="ac730-117">规划如何将规则集成到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="ac730-117">Plan how to incorporate your rules into your application.</span></span>  
  
2.  <span data-ttu-id="ac730-118">标识出要在应用程序中使用规则来表示的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="ac730-118">Identify the business logic that you want to represent with rules in your application.</span></span> <span data-ttu-id="ac730-119">术语“业务逻辑”可以指代许多内容；例如，“超过五百美元的采购订单必须由经理批准”就是一个业务逻辑示例。</span><span class="sxs-lookup"><span data-stu-id="ac730-119">The term "business logic" can refer to many things; an example of business logic is "Purchase orders for more than five hundred dollars must be approved by a manager."</span></span>  
  
3.  <span data-ttu-id="ac730-120">标识出规则元素的数据源。</span><span class="sxs-lookup"><span data-stu-id="ac730-120">Identify data sources for your rule elements.</span></span> <span data-ttu-id="ac730-121">您可以选择定义和发布词汇（表示底层绑定的特定于领域的术语）。</span><span class="sxs-lookup"><span data-stu-id="ac730-121">You can optionally define and publish vocabularies (domain-specific nomenclature that represents underlying bindings).</span></span>  
  
4.  <span data-ttu-id="ac730-122">通过词汇定义或直接通过数据绑定来定义规则，并通过所定义的规则编写一个表示您的业务逻辑的策略。</span><span class="sxs-lookup"><span data-stu-id="ac730-122">Define rules from vocabulary definitions or directly from data bindings, and from them compose a policy that represents your business logic.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac730-123">必须先发布词汇，才能在规则中应用这些词汇。</span><span class="sxs-lookup"><span data-stu-id="ac730-123">Vocabularies must be published before they can be applied in rules.</span></span>  
  
5.  <span data-ttu-id="ac730-124">使用示例事实测试和调试策略。</span><span class="sxs-lookup"><span data-stu-id="ac730-124">Test and debug the policy with sample facts.</span></span> <span data-ttu-id="ac730-125">你可以使用业务规则编辑器中的测试策略功能，也可以使用**策略**或**PolicyTester**类来执行从应用程序、 命令行程序或业务流程。</span><span class="sxs-lookup"><span data-stu-id="ac730-125">You can either use the Test Policy functionality in the Business Rule Composer or use **Policy** or **PolicyTester** classes to execute from an application, command-line program, or orchestration.</span></span>  
  
6.  <span data-ttu-id="ac730-126">将策略版本发布到规则存储中。</span><span class="sxs-lookup"><span data-stu-id="ac730-126">Publish the policy version to the rule store.</span></span>  
  
7.  <span data-ttu-id="ac730-127">部署策略版本。</span><span class="sxs-lookup"><span data-stu-id="ac730-127">Deploy the policy version.</span></span>  
  
8.  <span data-ttu-id="ac730-128">在宿主应用程序中实例化和生成短期事实列表。</span><span class="sxs-lookup"><span data-stu-id="ac730-128">Instantiate and build the short-term fact list in the hosting application.</span></span> <span data-ttu-id="ac730-129">使用**调用规则**形状中业务流程执行你的业务策略或以编程方式实例化宿主应用程序中的策略版本。</span><span class="sxs-lookup"><span data-stu-id="ac730-129">Use the **Call Rules** shape in an orchestration to execute your business policy or programmatically instantiate a policy version in your hosting application.</span></span>  
  
9. <span data-ttu-id="ac730-130">根据需要监视和跟踪规则执行情况。</span><span class="sxs-lookup"><span data-stu-id="ac730-130">Monitor and track rule execution as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac730-131">默认跟踪侦听器只能监视和跟踪业务流程。</span><span class="sxs-lookup"><span data-stu-id="ac730-131">The default tracking interceptor works with orchestrations.</span></span> <span data-ttu-id="ac730-132">如果您的宿主应用程序不是业务流程，则必须编写自己的跟踪侦听器以实现监视和跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="ac730-132">If your hosting application is not an orchestration, you must write your own tracking interceptor to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac730-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="ac730-133">In This Section</span></span>  
  
-   [<span data-ttu-id="ac730-134">规则</span><span class="sxs-lookup"><span data-stu-id="ac730-134">Rules</span></span>](../core/rules.md)  
  
-   [<span data-ttu-id="ac730-135">策略</span><span class="sxs-lookup"><span data-stu-id="ac730-135">Policies</span></span>](../core/policies.md)  
  
-   [<span data-ttu-id="ac730-136">词汇表</span><span class="sxs-lookup"><span data-stu-id="ac730-136">Vocabularies</span></span>](../core/vocabularies.md)  
  
-   [<span data-ttu-id="ac730-137">业务规则 Framework 体系结构</span><span class="sxs-lookup"><span data-stu-id="ac730-137">Business Rules Framework Architecture</span></span>](../core/business-rules-framework-architecture.md)  
  
-   [<span data-ttu-id="ac730-138">事实</span><span class="sxs-lookup"><span data-stu-id="ac730-138">Facts</span></span>](../core/facts.md)  
  
-   [<span data-ttu-id="ac730-139">规则引擎</span><span class="sxs-lookup"><span data-stu-id="ac730-139">Rule Engine</span></span>](../core/rule-engine.md)