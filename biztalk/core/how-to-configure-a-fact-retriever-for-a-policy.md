---
title: 如何为策略配置事实检索器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7095ae5a03b6c3aec2d4f66db2563e7a6986fb39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342286"
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a><span data-ttu-id="d70d4-102">如何为策略配置事实检索器</span><span class="sxs-lookup"><span data-stu-id="d70d4-102">How to Configure a Fact Retriever for a Policy</span></span>
<span data-ttu-id="d70d4-103">可以存储的事实数据，通常情况下，不会更改之前在主机应用程序首次执行循环，然后, 您可以从存储中检索这些事实，一次将其呈现给规则引擎进行缓存，和多个执行循环中重复使用它们。</span><span class="sxs-lookup"><span data-stu-id="d70d4-103">You can store facts that do not change frequently, and then before the first execution cycle of your host application, you can retrieve these facts from storage, present them once to the rule engine for caching, and reuse them over multiple execution cycles.</span></span>  
  
 <span data-ttu-id="d70d4-104">有两种方法将事实检索器与策略相关联。</span><span class="sxs-lookup"><span data-stu-id="d70d4-104">There are two ways to associate a fact retriever with a policy.</span></span> <span data-ttu-id="d70d4-105">您可以执行此操作使用业务规则编辑器或以编程方式使用**RuleSetExecutionConfiguration**对象。</span><span class="sxs-lookup"><span data-stu-id="d70d4-105">You can do this by using the Business Rule Composer or programmatically by using the **RuleSetExecutionConfiguration** object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d70d4-106">只有一个事实检索器实现可以与策略版本相关联。</span><span class="sxs-lookup"><span data-stu-id="d70d4-106">Only one fact retriever implementation can be associated with a policy version.</span></span>  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="d70d4-107">要与业务规则编辑器中的策略关联的事实检索器</span><span class="sxs-lookup"><span data-stu-id="d70d4-107">To associate a fact retriever with a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="d70d4-108">在策略浏览器窗口中，单击想要将事实检索器相关联的策略版本。</span><span class="sxs-lookup"><span data-stu-id="d70d4-108">In the Policy Explorer window, click the policy version with which you want to associate the fact retriever.</span></span>  
  
2.  <span data-ttu-id="d70d4-109">在属性窗口中，单击**省略号**中的按钮 （...）**事实检索器**以查找在事实检索器对象的全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="d70d4-109">In the Properties window, click the **ellipsis** button (…) in the **FactRetriever** property to browse in the global assembly cache for a fact retriever object.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d70d4-110">**省略号**按钮 （...） 单击才会出现**事实检索器**属性窗口中的行。</span><span class="sxs-lookup"><span data-stu-id="d70d4-110">The **ellipsis** button (…) does not appear until you click the **FactRetriever** row in the Property Window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70d4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d70d4-111">See Also</span></span>  
 [<span data-ttu-id="d70d4-112">如何创建事实检索器</span><span class="sxs-lookup"><span data-stu-id="d70d4-112">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)