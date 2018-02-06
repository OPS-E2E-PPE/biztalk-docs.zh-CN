---
title: "创建使用业务规则编辑器规则 |Microsoft 文档"
ms.custom: 
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0600a2b2-36a2-4496-8ba1-c5f6e2fa4760
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74a4ccb0a4cdb7592dabfeb4dae96530c04cea38
ms.sourcegitcommit: 78376935362715684b451eb6da9f2b1e8c129c2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="create-business-rules-using-the-business-rule-composer"></a><span data-ttu-id="fdc09-102">创建业务规则使用业务规则编辑器</span><span class="sxs-lookup"><span data-stu-id="fdc09-102">Create Business Rules Using the Business Rule Composer</span></span>

## <a name="overview"></a><span data-ttu-id="fdc09-103">概述</span><span class="sxs-lookup"><span data-stu-id="fdc09-103">Overview</span></span>
<span data-ttu-id="fdc09-104">使用业务规则编辑器，您可以创建具有一个或多个业务规则的业务策略，并部署这些策略。</span><span class="sxs-lookup"><span data-stu-id="fdc09-104">The Business Rule Composer allows you to create business policies with one or more business rules, and it allows you to deploy these policies.</span></span> <span data-ttu-id="fdc09-105">也可以浏览事实（XML、数据库和 .NET），并在业务规则中使用事实。</span><span class="sxs-lookup"><span data-stu-id="fdc09-105">It also allows you to browse for facts (XML, database, and .NET), and use the facts in business rules.</span></span> <span data-ttu-id="fdc09-106">此外，还可以创建基于事实的业务词汇，并在业务规则中使用这些词汇。</span><span class="sxs-lookup"><span data-stu-id="fdc09-106">In addition, it allows you to create business vocabularies based on facts, and to use the vocabularies in business rules.</span></span>  
  
 <span data-ttu-id="fdc09-107">本部分提供有关使用业务规则编辑器创建业务规则的特定于任务的信息。</span><span class="sxs-lookup"><span data-stu-id="fdc09-107">This section provides task-specific information about using the Business Rule Composer to create business rules.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fdc09-108">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fdc09-108">Next steps</span></span>
  
-   [<span data-ttu-id="fdc09-109">启动业务规则编辑器并加载策略</span><span class="sxs-lookup"><span data-stu-id="fdc09-109">Start the Business Rule Composer and Load a Policy</span></span>](../core/how-to-start-the-business-rule-composer-and-load-a-policy.md)  
  
-   [<span data-ttu-id="fdc09-110">业务规则编辑器的窗口</span><span class="sxs-lookup"><span data-stu-id="fdc09-110">Windows of the Business Rule Composer</span></span>](../core/windows-of-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="fdc09-111">选择事实</span><span class="sxs-lookup"><span data-stu-id="fdc09-111">Selecting Facts</span></span>](../core/selecting-facts.md)  
  
-   [<span data-ttu-id="fdc09-112">创建策略和规则</span><span class="sxs-lookup"><span data-stu-id="fdc09-112">Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)  
  
-   [<span data-ttu-id="fdc09-113">修改规则</span><span class="sxs-lookup"><span data-stu-id="fdc09-113">Modify Rules</span></span>](../core/how-to-modify-rules.md)  
  
-   [<span data-ttu-id="fdc09-114">维护策略版本</span><span class="sxs-lookup"><span data-stu-id="fdc09-114">Maintain Policy Versions</span></span>](../core/how-to-maintain-policy-versions.md)  
  
-   [<span data-ttu-id="fdc09-115">配置策略的事实检索器</span><span class="sxs-lookup"><span data-stu-id="fdc09-115">Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)  
  
-   [<span data-ttu-id="fdc09-116">制定词汇</span><span class="sxs-lookup"><span data-stu-id="fdc09-116">Develop Vocabularies</span></span>](../core/how-to-develop-vocabularies.md)  
  
-   [<span data-ttu-id="fdc09-117">处理 Null 和 DBNull</span><span class="sxs-lookup"><span data-stu-id="fdc09-117">Handle Null and DBNull</span></span>](../core/how-to-handle-null-and-dbnull.md)  
  
-   [<span data-ttu-id="fdc09-118">在业务规则中分析相同类型的多个对象</span><span class="sxs-lookup"><span data-stu-id="fdc09-118">Analyze Multiple Objects of the Same Type in a Business Rule</span></span>](../core/how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule.md)  
  
-   [<span data-ttu-id="fdc09-119">测试策略</span><span class="sxs-lookup"><span data-stu-id="fdc09-119">Testing Policies</span></span>](../core/testing-policies.md)  
  
-   [<span data-ttu-id="fdc09-120">一同和取消部署策略和词汇</span><span class="sxs-lookup"><span data-stu-id="fdc09-120">eploy and Undeploy Policies and Vocabularies</span></span>](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)  
  
-   [<span data-ttu-id="fdc09-121">算术运算符</span><span class="sxs-lookup"><span data-stu-id="fdc09-121">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)  
  
-   [<span data-ttu-id="fdc09-122">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="fdc09-122">Logical Operators</span></span>](../core/logical-operators.md)  
  
-   [<span data-ttu-id="fdc09-123">调用来自另一个策略的策略</span><span class="sxs-lookup"><span data-stu-id="fdc09-123">Invoke a Policy from Another Policy</span></span>](../core/invoking-a-policy-from-another-policy.md)  
  
-   [<span data-ttu-id="fdc09-124">从策略返回 True 或 False</span><span class="sxs-lookup"><span data-stu-id="fdc09-124">Return True or False from a Policy</span></span>](../core/how-to-return-true-or-false-from-a-policy.md)
