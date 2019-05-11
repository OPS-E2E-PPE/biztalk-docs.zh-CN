---
title: 业务规则引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Engine
- Business Rules Engine
- Business Rules Engine, rules
- Business Rules Engine, about Business Rules Engine
ms.assetid: 87b38507-9f6d-4863-88a6-9c20f15a4e55
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aea07fd5b73fcc333a94c6d199db1e303fcc310d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357742"
---
# <a name="business-rules-engine"></a><span data-ttu-id="379f1-102">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="379f1-102">Business Rules Engine</span></span>
<span data-ttu-id="379f1-103">业务规则框架是 Microsoft。NET 符合类库。</span><span class="sxs-lookup"><span data-stu-id="379f1-103">The Business Rules Framework is a Microsoft .NET-compliant class library.</span></span> <span data-ttu-id="379f1-104">它提供了一种有效的推理引擎，可以将高可读性、 描述性和语义丰富的规则链接到任何业务对象 （.NET 组件）、 XML 文档或数据库表。</span><span class="sxs-lookup"><span data-stu-id="379f1-104">It provides an efficient inference engine that can link highly readable, declarative, semantically rich rules to any business objects (.NET components), XML documents, or database tables.</span></span> <span data-ttu-id="379f1-105">应用程序开发人员可以通过构造从小型构建基块的业务逻辑 （小型规则集） 在.NET 对象、 数据库表和 XML 文档中包含的信息 （事实） 上运行的规则来生成业务规则。</span><span class="sxs-lookup"><span data-stu-id="379f1-105">Application developers can build business rules by constructing rules from small building blocks of business logic (small rule sets) that operate on information (facts) contained in .NET objects, database tables, and XML documents.</span></span> <span data-ttu-id="379f1-106">此设计模式可以提高代码重用，简化设计，以及业务逻辑的模块性。</span><span class="sxs-lookup"><span data-stu-id="379f1-106">This design pattern promotes code reuse, design simplicity, and modularity of business logic.</span></span> <span data-ttu-id="379f1-107">此外，规则引擎不会施加业务线应用程序设计的体系结构上。</span><span class="sxs-lookup"><span data-stu-id="379f1-107">In addition, the rule engine does not impose on the architecture or design of business applications.</span></span> <span data-ttu-id="379f1-108">事实上，可以向业务应用程序添加规则技术，通过直接调用规则引擎，或可以使用外部逻辑来调用您的业务对象而无需修改它们。</span><span class="sxs-lookup"><span data-stu-id="379f1-108">In fact, you can add rule technology to a business application by directly invoking the rule engine, or you can have external logic that invokes your business objects without modifying them.</span></span> <span data-ttu-id="379f1-109">简单地说，该技术使开发人员能够创建和维护应用程序最小的工作量。</span><span class="sxs-lookup"><span data-stu-id="379f1-109">In short, the technology enables developers to create and maintain applications with minimal effort.</span></span>  
  
 <span data-ttu-id="379f1-110">在规划开发的基于规则的应用程序中，首先需要确定如何将规则融入您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="379f1-110">In planning development of a rule-based application, you first need to determine how rules will fit into your business processes.</span></span> <span data-ttu-id="379f1-111">你的应用程序将创建的策略实例，并提供数据或事实数据，用于执行操作。</span><span class="sxs-lookup"><span data-stu-id="379f1-111">Your application will create an instance of a policy and supply it with data, or facts, on which to operate.</span></span> <span data-ttu-id="379f1-112">策略对象封装规则引擎，并提供单一用来运行它的入口点。</span><span class="sxs-lookup"><span data-stu-id="379f1-112">The policy object encapsulates the rule engine and provides a single point of entry through which to run it.</span></span>  
  
 <span data-ttu-id="379f1-113">您还需要规划的开发和测试规则设计。</span><span class="sxs-lookup"><span data-stu-id="379f1-113">You also will need to plan for the development and testing of your rules design.</span></span> <span data-ttu-id="379f1-114">您必须考虑你将如何部署和更新你的策略。</span><span class="sxs-lookup"><span data-stu-id="379f1-114">You must consider how you are going to deploy and update your policies.</span></span> <span data-ttu-id="379f1-115">则可能会想要跟踪的规则引擎的执行进度和监视其当前状态。</span><span class="sxs-lookup"><span data-stu-id="379f1-115">You will likely want to track the progress of your rule engine's execution and monitor its current state.</span></span>  
  
 <span data-ttu-id="379f1-116">在规划规则开发的帐户的以下步骤：</span><span class="sxs-lookup"><span data-stu-id="379f1-116">Account for the following steps as you plan your rules development:</span></span>  
  
1.  <span data-ttu-id="379f1-117">规划如何将规则集成到应用程序。</span><span class="sxs-lookup"><span data-stu-id="379f1-117">Plan how to incorporate your rules into your application.</span></span>  
  
2.  <span data-ttu-id="379f1-118">标识你想要表示，并将你的应用程序中的规则的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="379f1-118">Identify the business logic that you want to represent with rules in your application.</span></span> <span data-ttu-id="379f1-119">术语"业务逻辑"可以指许多内容;业务逻辑的一个示例是"超过五百美元的采购订单必须批准由管理器。"</span><span class="sxs-lookup"><span data-stu-id="379f1-119">The term "business logic" can refer to many things; an example of business logic is "Purchase orders for more than five hundred dollars must be approved by a manager."</span></span>  
  
3.  <span data-ttu-id="379f1-120">确定所选规则的元素的数据源。</span><span class="sxs-lookup"><span data-stu-id="379f1-120">Identify data sources for your rule elements.</span></span> <span data-ttu-id="379f1-121">（可选） 可以定义和发布词汇 （表示底层绑定的特定于域的术语）。</span><span class="sxs-lookup"><span data-stu-id="379f1-121">You can optionally define and publish vocabularies (domain-specific nomenclature that represents underlying bindings).</span></span>  
  
4.  <span data-ttu-id="379f1-122">定义规则从词汇定义或直接通过数据绑定，并从这些撰写一个策略，表示您的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="379f1-122">Define rules from vocabulary definitions or directly from data bindings, and from them compose a policy that represents your business logic.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="379f1-123">它们可以在规则中应用之前，必须先发布词汇。</span><span class="sxs-lookup"><span data-stu-id="379f1-123">Vocabularies must be published before they can be applied in rules.</span></span>  
  
5.  <span data-ttu-id="379f1-124">测试和调试使用示例事实的策略。</span><span class="sxs-lookup"><span data-stu-id="379f1-124">Test and debug the policy with sample facts.</span></span> <span data-ttu-id="379f1-125">可以使用业务规则编辑器中的测试策略功能或使用**策略**或**PolicyTester**类，以从应用程序、 命令行程序或业务流程执行。</span><span class="sxs-lookup"><span data-stu-id="379f1-125">You can either use the Test Policy functionality in the Business Rule Composer or use **Policy** or **PolicyTester** classes to execute from an application, command-line program, or orchestration.</span></span>  
  
6.  <span data-ttu-id="379f1-126">将策略版本发布到规则存储。</span><span class="sxs-lookup"><span data-stu-id="379f1-126">Publish the policy version to the rule store.</span></span>  
  
7.  <span data-ttu-id="379f1-127">部署策略版本。</span><span class="sxs-lookup"><span data-stu-id="379f1-127">Deploy the policy version.</span></span>  
  
8.  <span data-ttu-id="379f1-128">实例化和生成短期事实列表宿主应用程序中。</span><span class="sxs-lookup"><span data-stu-id="379f1-128">Instantiate and build the short-term fact list in the hosting application.</span></span> <span data-ttu-id="379f1-129">使用**调用规则**形状在业务流程执行您的业务策略或以编程方式实例化宿主应用程序中的策略版本中。</span><span class="sxs-lookup"><span data-stu-id="379f1-129">Use the **Call Rules** shape in an orchestration to execute your business policy or programmatically instantiate a policy version in your hosting application.</span></span>  
  
9. <span data-ttu-id="379f1-130">监视和跟踪规则执行根据需要。</span><span class="sxs-lookup"><span data-stu-id="379f1-130">Monitor and track rule execution as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="379f1-131">默认跟踪侦听器只能监视和业务流程。</span><span class="sxs-lookup"><span data-stu-id="379f1-131">The default tracking interceptor works with orchestrations.</span></span> <span data-ttu-id="379f1-132">如果在宿主应用程序不是业务流程，则必须编写您自己的跟踪侦听器来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="379f1-132">If your hosting application is not an orchestration, you must write your own tracking interceptor to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="379f1-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="379f1-133">In This Section</span></span>  
  
-   [<span data-ttu-id="379f1-134">规则</span><span class="sxs-lookup"><span data-stu-id="379f1-134">Rules</span></span>](../core/rules.md)  
  
-   [<span data-ttu-id="379f1-135">策略</span><span class="sxs-lookup"><span data-stu-id="379f1-135">Policies</span></span>](../core/policies.md)  
  
-   [<span data-ttu-id="379f1-136">词汇</span><span class="sxs-lookup"><span data-stu-id="379f1-136">Vocabularies</span></span>](../core/vocabularies.md)  
  
-   [<span data-ttu-id="379f1-137">业务规则框架体系结构</span><span class="sxs-lookup"><span data-stu-id="379f1-137">Business Rules Framework Architecture</span></span>](../core/business-rules-framework-architecture.md)  
  
-   [<span data-ttu-id="379f1-138">事实</span><span class="sxs-lookup"><span data-stu-id="379f1-138">Facts</span></span>](../core/facts.md)  
  
-   [<span data-ttu-id="379f1-139">规则引擎</span><span class="sxs-lookup"><span data-stu-id="379f1-139">Rule Engine</span></span>](../core/rule-engine.md)