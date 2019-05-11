---
title: 词汇 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, vocabularies
- vocabularies, about vocabularies
- vocabularies
- Business Rules Engine, vocabularies
ms.assetid: 591673a0-2c4d-41ca-9997-b363c086dd66
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18e513687db2b291462843811d296c15d3509288
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320845"
---
# <a name="vocabularies"></a><span data-ttu-id="3965e-102">词汇</span><span class="sxs-lookup"><span data-stu-id="3965e-102">Vocabularies</span></span>
<span data-ttu-id="3965e-103">按域或特定于行业的命名法通常表示用于定义规则条件和操作的术语。</span><span class="sxs-lookup"><span data-stu-id="3965e-103">The terms used to define rule conditions and actions are usually expressed by domain or industry-specific nomenclature.</span></span> <span data-ttu-id="3965e-104">例如，电子邮件用户写入的消息的规则"收到来自"和"接收消息后，"而保险业务分析人员来编写规则"风险因素"和"保险金额"。</span><span class="sxs-lookup"><span data-stu-id="3965e-104">For example, an e-mail user writes rules in terms of messages "received from" and messages "received after," while an insurance business analyst writes rules in terms of "risk factors" and "coverage amount."</span></span>  
  
 <span data-ttu-id="3965e-105">基础此特定于域的术语是实施规则条件和规则操作的技术项目 （对象、 数据库表和 XML 文档）。</span><span class="sxs-lookup"><span data-stu-id="3965e-105">Underlying this domain-specific terminology are the technology artifacts (objects, database tables, and XML documents) that implement rule conditions and rule actions.</span></span> <span data-ttu-id="3965e-106">Vocabulariesare 设计为用于消除业务语义与实施之间的差距。</span><span class="sxs-lookup"><span data-stu-id="3965e-106">Vocabulariesare designed to bridge the gap between business semantics and implementation.</span></span>  
  
 <span data-ttu-id="3965e-107">例如，审批状态的数据绑定可能指向某个数据库，表示为一个 SQL 查询中某一行中的某列。</span><span class="sxs-lookup"><span data-stu-id="3965e-107">For example, a data binding for an approval status might point to a certain column in a certain row in a certain database, represented as an SQL query.</span></span> <span data-ttu-id="3965e-108">而不是在规则中插入这种复杂的表示形式，而是可以创建与数据绑定、"状态。"的友好名称与相关联的词汇定义</span><span class="sxs-lookup"><span data-stu-id="3965e-108">Instead of inserting this sort of complex representation in a rule, you might instead create a vocabulary definition, associated with that data binding, with a friendly name of "Status."</span></span> <span data-ttu-id="3965e-109">随后可以在任意数量的规则，包括"状态"和规则引擎可以从表中检索相应的数据。</span><span class="sxs-lookup"><span data-stu-id="3965e-109">Subsequently you can include "Status" in any number of rules, and the rule engine can retrieve the corresponding data from the table.</span></span>  
  
 <span data-ttu-id="3965e-110">一个*词汇*是定义的规则条件和操作中使用的事实的友好名称组成的集合。</span><span class="sxs-lookup"><span data-stu-id="3965e-110">A *vocabulary* is a collection of definitions consisting of friendly names for the facts used in rule conditions and actions.</span></span> <span data-ttu-id="3965e-111">词汇定义使规则更易于阅读、 理解和的特定业务域中的人员共享。</span><span class="sxs-lookup"><span data-stu-id="3965e-111">Vocabulary definitions make the rules easier to read, understand, and share by people in a particular business domain.</span></span>  
  
 <span data-ttu-id="3965e-112">可以使用业务规则编辑器来定义词汇，然后放置在共享的规则存储中。</span><span class="sxs-lookup"><span data-stu-id="3965e-112">You can use the Business Rule Composer to define vocabularies that are then placed in the shared rule store.</span></span> <span data-ttu-id="3965e-113">负责将规则创作到新的或现有的应用程序集成的工具开发人员也可以使用词汇。</span><span class="sxs-lookup"><span data-stu-id="3965e-113">Vocabularies can also be consumed by tool developers responsible for integrating rule authoring into new or existing applications.</span></span>  
  
 <span data-ttu-id="3965e-114">可以使用某一词汇之前，它必须标记为某个版本并发布规则存储中。</span><span class="sxs-lookup"><span data-stu-id="3965e-114">Before you can use a vocabulary, it must be stamped with a version and published in your rule store.</span></span> <span data-ttu-id="3965e-115">这是保证，不会更改在词汇定义，并保持引用完整性。</span><span class="sxs-lookup"><span data-stu-id="3965e-115">This is to guarantee that the definitions in the vocabulary will not change, and to preserve referential integrity.</span></span> <span data-ttu-id="3965e-116">这意味着，任何使用该特定版本的词汇的策略将不会意外失败由于底层词汇中的更改。</span><span class="sxs-lookup"><span data-stu-id="3965e-116">This means that any policies that use that particular version of the vocabulary will not fail unexpectedly due to changes in the underlying vocabulary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3965e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3965e-117">See Also</span></span>  
 [<span data-ttu-id="3965e-118">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="3965e-118">Business Rules Engine</span></span>](../core/business-rules-engine.md)