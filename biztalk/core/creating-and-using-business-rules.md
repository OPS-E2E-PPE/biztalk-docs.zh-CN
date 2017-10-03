---
title: "创建和使用业务规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Editor
- Business Rules Editor
ms.assetid: a15fd09b-ff4e-4c26-8cb6-5ffd258a2182
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76a6b51c72f04d5c7918da637f4266567f92e8bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-using-business-rules"></a><span data-ttu-id="2de56-102">创建和使用业务规则</span><span class="sxs-lookup"><span data-stu-id="2de56-102">Creating and Using Business Rules</span></span>
<span data-ttu-id="2de56-103">业务规则（或业务策略）定义并控制着组织的结构、运作和策略。</span><span class="sxs-lookup"><span data-stu-id="2de56-103">Business rules (or business policies) define and control the structure, operation, and strategy of an organization.</span></span> <span data-ttu-id="2de56-104">业务规则可能在操作程序手册、合同或协议中正式定义，也可能作为知识或员工所拥有的专门技术存在着。</span><span class="sxs-lookup"><span data-stu-id="2de56-104">Business rules may be formally defined in procedure manuals, contracts, or agreements, or may exist as knowledge or expertise embodied in employees.</span></span> <span data-ttu-id="2de56-105">业务规则是动态的，可能随时间的推移而不断变更，并存在于各种类型的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="2de56-105">Business rules are dynamic and subject to change over time, and can be found in all types of applications.</span></span> <span data-ttu-id="2de56-106">金融和保险、电子商务、运输、电信、基于 Web 的服务以及个性化只是受业务规则支配的众多业务领域中的几种。</span><span class="sxs-lookup"><span data-stu-id="2de56-106">Finance and insurance, e-business, transportation, telecommunications, Web-based services, and personalization are just a few of the many business domains that are governed by business rules.</span></span> <span data-ttu-id="2de56-107">这些业务领域中的每一种都需要将业务战略、策略和规章传递给信息技术 (IT) 人员，以便使之包括在软件应用程序中。</span><span class="sxs-lookup"><span data-stu-id="2de56-107">Each of these business domains shares the need to convey business strategies, policies, and regulations to information technology (IT) personnel for inclusion into software applications.</span></span>  
  
 <span data-ttu-id="2de56-108">传统的过程编程语言和面向对象的编程语言，如 C、C++ 和 Microsoft Visual Basic，都是面向程序员的。</span><span class="sxs-lookup"><span data-stu-id="2de56-108">Traditional procedural and object-oriented programming languages, such as C, C++, and Microsoft Visual Basic, are oriented towards programmers.</span></span> <span data-ttu-id="2de56-109">即使是面向对象的高级语言，如 Java 和 C#，仍然主要是程序员的语言。</span><span class="sxs-lookup"><span data-stu-id="2de56-109">Even advanced object-oriented languages, such as Java and C#, are still primarily programmers' languages.</span></span> <span data-ttu-id="2de56-110">包括设计、开发、编译和测试在内的传统软件开发周期需要大量时间和协调，无法使非程序员参与自动化的业务策略的维护。</span><span class="sxs-lookup"><span data-stu-id="2de56-110">The traditional software development cycle of design, develop, compile, and test requires substantial time and coordination, and does not enable nonprogrammers to participate in the maintenance of automated business policies.</span></span> <span data-ttu-id="2de56-111">业务规则框架提供的开发环境可以迅速创建应用程序，无需像传统应用程序那样经历冗长的编程周期，从而解决了这一问题。</span><span class="sxs-lookup"><span data-stu-id="2de56-111">The Business Rules Framework addresses this problem by providing a development environment that allows rapid application creation without the lengthy cycle of traditional application programming.</span></span> <span data-ttu-id="2de56-112">例如，使用此框架构建的业务策略无需重新编译和重新部署相关联的业务流程就可以更新。</span><span class="sxs-lookup"><span data-stu-id="2de56-112">For example, business policies constructed by using this framework can be updated without recompiling and redeploying the associated orchestrations.</span></span>  
  
 <span data-ttu-id="2de56-113">业务规则框架与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 紧密集成，开发人员可以使用以下功能来构建和管理业务规则：</span><span class="sxs-lookup"><span data-stu-id="2de56-113">The Business Rules Framework is tightly integrated with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and developers can use the following features to build and manage business rules:</span></span>  
  
-   <span data-ttu-id="2de56-114">实施干预机制来评价业务规则的高性能规则引擎。</span><span class="sxs-lookup"><span data-stu-id="2de56-114">A high-performance rule engine that implements an inference mechanism to evaluate the business rules.</span></span>  
  
-   <span data-ttu-id="2de56-115">用于开发基于规则的应用程序的各种各样的应用程序编程接口 (API)。</span><span class="sxs-lookup"><span data-stu-id="2de56-115">A rich set of application programming interfaces (APIs) for developing rule-based applications.</span></span>  
  
-   <span data-ttu-id="2de56-116">图形用户界面、业务规则编辑器，开发人员业务分析员和管理员可以通过各种方式来使用它们，以便有效地开发和应用规则和策略。</span><span class="sxs-lookup"><span data-stu-id="2de56-116">A graphical user interface, the Business Rule Composer, which developers, business analysts, and administrators can use in various ways to efficiently develop and apply rules and policies.</span></span>  
  
-   <span data-ttu-id="2de56-117">与 BizTalk 业务流程的无缝集成，使您能够从 BizTalk 业务流程调用业务策略或一组业务规则。</span><span class="sxs-lookup"><span data-stu-id="2de56-117">A seamless integration with BizTalk orchestrations, which enables you to invoke a business policy or a set of business rules from a BizTalk orchestration.</span></span>  
  
-   <span data-ttu-id="2de56-118">规则引擎部署向导，使您能够迅速地导入或导出业务规则或规则使用的词汇，以及部署或取消部署这些规则。</span><span class="sxs-lookup"><span data-stu-id="2de56-118">The Rule Engine Deployment Wizard, which enables you to rapidly import or export business rules or the vocabularies used by the rules, as well as to deploy or undeploy these rules.</span></span>  
  
 <span data-ttu-id="2de56-119">使用业务规则框架创建的业务规则（策略）可以在已编排为业务流程的业务程序中使用，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="2de56-119">The business rules (policy) you create by using the Business Rules Framework can be used in an orchestrated business process, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="2de56-120">![显示 buisness 策略过程中的图示。] (../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")</span><span class="sxs-lookup"><span data-stu-id="2de56-120">![Diagram showing buisness policy in process.](../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")</span></span>  
<span data-ttu-id="2de56-121">业务策略</span><span class="sxs-lookup"><span data-stu-id="2de56-121">Business Policy</span></span>  
  
 <span data-ttu-id="2de56-122">本部分提供有关如何利用业务规则框架和使用的工具的概念性信息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供开发业务规则。</span><span class="sxs-lookup"><span data-stu-id="2de56-122">This section provides conceptual information about how you can leverage the Business Rules Framework and use the tools that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides to develop business rules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2de56-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="2de56-123">In This Section</span></span>  
  
-   [<span data-ttu-id="2de56-124">创建业务规则</span><span class="sxs-lookup"><span data-stu-id="2de56-124">Creating Business Rules</span></span>](../core/creating-business-rules-using-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="2de56-125">业务规则 Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="2de56-125">Business Rules Framework Security</span></span>](../core/business-rules-framework-security.md)  
  
-   [<span data-ttu-id="2de56-126">使用业务规则框架编程</span><span class="sxs-lookup"><span data-stu-id="2de56-126">Programming with Business Rules Framework</span></span>](../core/programming-with-business-rules-framework.md)  
  
-   [<span data-ttu-id="2de56-127">规则引擎配置和优化参数</span><span class="sxs-lookup"><span data-stu-id="2de56-127">Rule Engine Configuration and Tuning Parameters</span></span>](../core/rule-engine-configuration-and-tuning-parameters.md)