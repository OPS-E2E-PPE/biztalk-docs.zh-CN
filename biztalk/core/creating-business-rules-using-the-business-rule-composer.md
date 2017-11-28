---
title: "创建业务规则使用业务规则编辑器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, business rules
- business rules, creating
ms.assetid: 0600a2b2-36a2-4496-8ba1-c5f6e2fa4760
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5b1281acab139159dd837f63cf80af56d388c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-business-rules-using-the-business-rule-composer"></a><span data-ttu-id="34f0e-102">创建业务规则使用业务规则编辑器</span><span class="sxs-lookup"><span data-stu-id="34f0e-102">Creating Business Rules Using the Business Rule Composer</span></span>
<span data-ttu-id="34f0e-103">使用业务规则编辑器，您可以创建具有一个或多个业务规则的业务策略，并部署这些策略。</span><span class="sxs-lookup"><span data-stu-id="34f0e-103">The Business Rule Composer allows you to create business policies with one or more business rules, and it allows you to deploy these policies.</span></span> <span data-ttu-id="34f0e-104">也可以浏览事实（XML、数据库和 .NET），并在业务规则中使用事实。</span><span class="sxs-lookup"><span data-stu-id="34f0e-104">It also allows you to browse for facts (XML, database, and .NET), and use the facts in business rules.</span></span> <span data-ttu-id="34f0e-105">此外，还可以创建基于事实的业务词汇，并在业务规则中使用这些词汇。</span><span class="sxs-lookup"><span data-stu-id="34f0e-105">In addition, it allows you to create business vocabularies based on facts, and to use the vocabularies in business rules.</span></span>  
  
 <span data-ttu-id="34f0e-106">本部分提供有关使用业务规则编辑器创建业务规则的特定于任务的信息。</span><span class="sxs-lookup"><span data-stu-id="34f0e-106">This section provides task-specific information about using the Business Rule Composer to create business rules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34f0e-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="34f0e-107">In This Section</span></span>  
  
-   [<span data-ttu-id="34f0e-108">如何启动业务规则编辑器和加载策略</span><span class="sxs-lookup"><span data-stu-id="34f0e-108">How to Start the Business Rule Composer and Load a Policy</span></span>](../core/how-to-start-the-business-rule-composer-and-load-a-policy.md)  
  
-   [<span data-ttu-id="34f0e-109">业务规则编辑器的窗口</span><span class="sxs-lookup"><span data-stu-id="34f0e-109">Windows of the Business Rule Composer</span></span>](../core/windows-of-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="34f0e-110">选择事实</span><span class="sxs-lookup"><span data-stu-id="34f0e-110">Selecting Facts</span></span>](../core/selecting-facts.md)  
  
-   [<span data-ttu-id="34f0e-111">如何创建策略和规则</span><span class="sxs-lookup"><span data-stu-id="34f0e-111">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)  
  
-   [<span data-ttu-id="34f0e-112">如何修改规则</span><span class="sxs-lookup"><span data-stu-id="34f0e-112">How to Modify Rules</span></span>](../core/how-to-modify-rules.md)  
  
-   [<span data-ttu-id="34f0e-113">如何维护策略版本</span><span class="sxs-lookup"><span data-stu-id="34f0e-113">How to Maintain Policy Versions</span></span>](../core/how-to-maintain-policy-versions.md)  
  
-   [<span data-ttu-id="34f0e-114">如何为策略配置事实检索器</span><span class="sxs-lookup"><span data-stu-id="34f0e-114">How to Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)  
  
-   [<span data-ttu-id="34f0e-115">如何开发词汇</span><span class="sxs-lookup"><span data-stu-id="34f0e-115">How to Develop Vocabularies</span></span>](../core/how-to-develop-vocabularies.md)  
  
-   [<span data-ttu-id="34f0e-116">如何处理 Null 和 DBNull</span><span class="sxs-lookup"><span data-stu-id="34f0e-116">How to Handle Null and DBNull</span></span>](../core/how-to-handle-null-and-dbnull.md)  
  
-   [<span data-ttu-id="34f0e-117">如何分析的业务规则中的相同类型的多个对象</span><span class="sxs-lookup"><span data-stu-id="34f0e-117">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>](../core/how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule.md)  
  
-   [<span data-ttu-id="34f0e-118">测试策略</span><span class="sxs-lookup"><span data-stu-id="34f0e-118">Testing Policies</span></span>](../core/testing-policies.md)  
  
-   [<span data-ttu-id="34f0e-119">如何部署和取消部署策略和词汇</span><span class="sxs-lookup"><span data-stu-id="34f0e-119">How to Deploy and Undeploy Policies and Vocabularies</span></span>](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)  
  
-   [<span data-ttu-id="34f0e-120">算术运算符</span><span class="sxs-lookup"><span data-stu-id="34f0e-120">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)  
  
-   [<span data-ttu-id="34f0e-121">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="34f0e-121">Logical Operators</span></span>](../core/logical-operators.md)  
  
-   [<span data-ttu-id="34f0e-122">调用来自另一个策略的策略</span><span class="sxs-lookup"><span data-stu-id="34f0e-122">Invoking a Policy from Another Policy</span></span>](../core/invoking-a-policy-from-another-policy.md)  
  
-   [<span data-ttu-id="34f0e-123">如何从一个策略返回 True 或 False</span><span class="sxs-lookup"><span data-stu-id="34f0e-123">How to Return True or False from a Policy</span></span>](../core/how-to-return-true-or-false-from-a-policy.md)