---
title: 短期事实与长期事实 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- facts, short-term
- facts, long-term
- short-term facts
- business rules, facts
- long-term facts
ms.assetid: de020b20-1012-498a-969e-4adc4549918c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed46b71c205ef7db5dc8d918ba0cdae68ebd41d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990006"
---
# <a name="short-term-facts-vs-long-term-facts"></a><span data-ttu-id="0cfaa-102">短期事实与长期事实</span><span class="sxs-lookup"><span data-stu-id="0cfaa-102">Short-Term Facts vs. Long-Term Facts</span></span>
<span data-ttu-id="0cfaa-103">两种类型的事实会添加到规则引擎的工作内存中 — 短期事实和长期事实。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-103">Two types of facts are asserted into the working memory of the rule engine—short-term facts and long-term facts.</span></span>  
  
## <a name="short-term-facts"></a><span data-ttu-id="0cfaa-104">短期事实</span><span class="sxs-lookup"><span data-stu-id="0cfaa-104">Short-Term Facts</span></span>  
 <span data-ttu-id="0cfaa-105">短期事实特定于规则引擎的单个执行循环。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-105">A short-term fact is specific to a single execution cycle of the rule engine.</span></span> <span data-ttu-id="0cfaa-106">策略执行之后会自动从规则引擎的工作内存中取消短期事实。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-106">Short-term facts are retracted automatically from the working memory of the rule engine after the policy executes.</span></span> <span data-ttu-id="0cfaa-107">如果在策略的规则引擎的两次执行循环之间数据发生了更改，则您所提交的数据将作为短期事实提交给规则引擎。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-107">If your data changes between execution cycles of the rule engine for a policy, you submit the data as a short-term fact to the rule engine.</span></span>  
  
 <span data-ttu-id="0cfaa-108">短期事实的示例有：</span><span class="sxs-lookup"><span data-stu-id="0cfaa-108">Examples of short-term facts are:</span></span>  
  
-   <span data-ttu-id="0cfaa-109">您作为参数提交给事实**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-109">The facts you submit as parameters to the **Policy.Execute** method.</span></span>  
  
-   <span data-ttu-id="0cfaa-110">您作为参数提交给事实**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-110">The facts you submit as parameters to the **Call Rules** shape.</span></span>  
  
-   <span data-ttu-id="0cfaa-111">从规则使用的操作将提交的事实**Assert**函数。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-111">The facts you submit from an action of a rule using the **Assert** function.</span></span>  
  
## <a name="long-term-facts"></a><span data-ttu-id="0cfaa-112">长期事实</span><span class="sxs-lookup"><span data-stu-id="0cfaa-112">Long-Term Facts</span></span>  
 <span data-ttu-id="0cfaa-113">长期事实加载到规则引擎的工作内存中，可跨任意数量的执行循环使用。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-113">A long-term fact is loaded into the working memory of the rule engine for use over an arbitrary number of execution cycles.</span></span> <span data-ttu-id="0cfaa-114">通常情况下，长期事实的变化较慢，在策略的执行间隔中通常不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-114">Typically, long-term facts are slowly changing facts that do not typically change between executions of a policy.</span></span> <span data-ttu-id="0cfaa-115">例如，您可能只想创建一次数据库连接，并想使用同一数据库连接多次执行策略。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-115">For example, you may want to create a database connection only once, and execute the policy several times by using the same database connection.</span></span> <span data-ttu-id="0cfaa-116">实际上，短期事实和长期事实之间唯一的差别在于实现。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-116">The only real distinction between short-term facts and long-term facts is in implementation.</span></span>  
  
 <span data-ttu-id="0cfaa-117">若要将事实作为长期事实提交，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0cfaa-117">To submit a fact as a long-term fact, you need to perform the following steps:</span></span>  
  
1. <span data-ttu-id="0cfaa-118">创建一个事实检索器组件实现**IFactRetriever**接口。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-118">Create a fact retriever component that implements the **IFactRetriever** interface.</span></span> <span data-ttu-id="0cfaa-119">创建和这一事实添加到工作内存中的规则引擎何时**UpdateFacts**方法调用的第一个的时间和更新事实的后续调用，可在必要时**UpdateFacts**方法。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-119">Create and assert the fact into the working memory of the rule engine when the **UpdateFacts** method is invoked for the first time, and update the fact when necessary on subsequent invocations of the **UpdateFacts** method.</span></span>  
  
2. <span data-ttu-id="0cfaa-120">使用业务规则编辑器，将策略配置为使用事实检索器组件。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-120">Configure the policy to use the fact retriever component by using the Business Rule Composer.</span></span>  
  
   <span data-ttu-id="0cfaa-121">有关创建事实检索器和策略中使用的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。</span><span class="sxs-lookup"><span data-stu-id="0cfaa-121">For more information about creating a fact retriever and using it in a policy, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cfaa-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cfaa-122">See Also</span></span>  
 [<span data-ttu-id="0cfaa-123">事实</span><span class="sxs-lookup"><span data-stu-id="0cfaa-123">Facts</span></span>](../core/facts.md)