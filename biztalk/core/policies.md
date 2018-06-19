---
title: 策略 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, policies
- policies, about policies
- policies, deploying
- policies, Business Rules Engine
- policies
- business rules, policies
- policies, versioning
- policies, testing
- policies, creating
- policies, updating
ms.assetid: 2e0ae081-938d-4e2a-947e-1c0ecfebb4b8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd05d6cf67d89ee811cac45ac3950697db74f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264429"
---
# <a name="policies"></a><span data-ttu-id="b7f7a-102">策略</span><span class="sxs-lookup"><span data-stu-id="b7f7a-102">Policies</span></span>
<span data-ttu-id="b7f7a-103">策略是一组逻辑规则。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-103">A policy is a logical grouping of rules.</span></span> <span data-ttu-id="b7f7a-104">您可以撰写一个策略版本，保存该策略版本，通过将该策略版本应用于事实来对其进行测试，并在得到满意结果后，发布该策略版本并将其部署到产品环境中。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-104">You compose a version of a policy, save it, test it by applying it to facts, and, when you are satisfied with the results, publish it and deploy it to a production environment.</span></span>  
  
## <a name="policy-composition"></a><span data-ttu-id="b7f7a-105">撰写策略</span><span class="sxs-lookup"><span data-stu-id="b7f7a-105">Policy Composition</span></span>  
 <span data-ttu-id="b7f7a-106">可以在业务规则编辑器中通过根据事实和定义构造规则来撰写策略。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-106">You can compose policies in the Business Rule Composer by constructing rules from facts and definitions.</span></span> <span data-ttu-id="b7f7a-107">策略可以包含一个任意大小的规则集，但通常是根据与使用该策略的应用程序上下文中的特定业务域相关的规则来撰写策略。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-107">A policy can contain an arbitrarily large set of rules, but typically you compose a policy from rules that pertain to a specific business domain within the context of the application that will be using the policy.</span></span>  
  
## <a name="policy-testing"></a><span data-ttu-id="b7f7a-108">策略测试</span><span class="sxs-lookup"><span data-stu-id="b7f7a-108">Policy Testing</span></span>  
 <span data-ttu-id="b7f7a-109">在将策略发布和部署到产品环境中之前，可以有效地执行该策略的运行测试。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-109">You can effectively perform a test run of your policy before it is published and deployed in a production environment.</span></span> <span data-ttu-id="b7f7a-110">使用业务规则编辑器，您可以为策略提供事实实例，运行该策略并查看该策略的输出。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-110">The Business Rule Composer allows you to supply instances of facts to a policy, run the policy, and view its output.</span></span> <span data-ttu-id="b7f7a-111">输出包括事实活动、规则执行、条件评估和议程更新。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-111">The output includes fact activity, rule execution, condition evaluation, and updates to the agenda.</span></span>  
  
## <a name="policy-versions"></a><span data-ttu-id="b7f7a-112">策略版本</span><span class="sxs-lookup"><span data-stu-id="b7f7a-112">Policy Versions</span></span>  
 <span data-ttu-id="b7f7a-113">在策略中定义所有规则之后，可以发布策略版本。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-113">After you have defined all the rules in your policy, you can publish the policy version.</span></span> <span data-ttu-id="b7f7a-114">通过此方式可以锁定策略，并且策略行为将被固定下来。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-114">In this way the policy is locked down, and its behavior is well-defined.</span></span>  
  
 <span data-ttu-id="b7f7a-115">给定的策略版本可以在业务环境中的一组给定条件下使用，并在这些条件发生变化时由另一版本替代。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-115">A given policy version can be used under a given set of circumstances in your business environment, and replaced by another version when those circumstances change.</span></span> <span data-ttu-id="b7f7a-116">并且，新版本和旧版本可同时由不同的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-116">Also, both new and old versions can be used simultaneously by different applications.</span></span>  
  
## <a name="policy-deployment"></a><span data-ttu-id="b7f7a-117">策略部署</span><span class="sxs-lookup"><span data-stu-id="b7f7a-117">Policy Deployment</span></span>  
 <span data-ttu-id="b7f7a-118">当策略准备就绪，可在产品环境中运行时，可以部署该策略以使该策略可用于主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-118">When your policy is ready to be run in a production environment, you can deploy it to make it available to a hosting application.</span></span>  
  
## <a name="dynamic-policy-updates"></a><span data-ttu-id="b7f7a-119">动态策略更新</span><span class="sxs-lookup"><span data-stu-id="b7f7a-119">Dynamic Policy Updates</span></span>  
 <span data-ttu-id="b7f7a-120">使用动态策略更新，您可以修改策略而不会影响业务流程的运行。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-120">Dynamic policy updates allow you to modify policies independently of a running business process.</span></span> <span data-ttu-id="b7f7a-121">您可以创建和部署策略的更新版本，主机应用程序可以近乎实时地合并更新。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-121">You can create and deploy an updated version of the policy, and the hosting application can incorporate the update in near real time.</span></span> <span data-ttu-id="b7f7a-122">此更新不需要更改任何代码，因此，可以避免重新开发和重新部署应用程序所带来的开销。</span><span class="sxs-lookup"><span data-stu-id="b7f7a-122">This update does not require you to change any code, and thus you can avoid the overhead of redeveloping and redeploying the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f7a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7f7a-123">See Also</span></span>  
 [<span data-ttu-id="b7f7a-124">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="b7f7a-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)