---
title: 词汇 |Microsoft 文档
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
ms.openlocfilehash: a9e20dfead51d54822d3316c8819d04a259cfa83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288005"
---
# <a name="vocabularies"></a><span data-ttu-id="2eeda-102">词汇表</span><span class="sxs-lookup"><span data-stu-id="2eeda-102">Vocabularies</span></span>
<span data-ttu-id="2eeda-103">通常使用特定于领域或行业的命名法来表示用于定义规则条件和操作的术语。</span><span class="sxs-lookup"><span data-stu-id="2eeda-103">The terms used to define rule conditions and actions are usually expressed by domain or industry-specific nomenclature.</span></span> <span data-ttu-id="2eeda-104">例如，电子邮件用户使用“接收自”消息和“收到时间晚于”消息等术语来编写规则，而保险业务分析员则使用“风险因素”和“保险金额”等术语来编写规则。</span><span class="sxs-lookup"><span data-stu-id="2eeda-104">For example, an e-mail user writes rules in terms of messages "received from" and messages "received after," while an insurance business analyst writes rules in terms of "risk factors" and "coverage amount."</span></span>  
  
 <span data-ttu-id="2eeda-105">这种特定于领域的术语的底层是实施规则条件和规则操作的技术项目（对象、数据库表和 XML 文档）。</span><span class="sxs-lookup"><span data-stu-id="2eeda-105">Underlying this domain-specific terminology are the technology artifacts (objects, database tables, and XML documents) that implement rule conditions and rule actions.</span></span> <span data-ttu-id="2eeda-106">Vocabulariesare 旨在业务语义和实现之间的桥梁。</span><span class="sxs-lookup"><span data-stu-id="2eeda-106">Vocabulariesare designed to bridge the gap between business semantics and implementation.</span></span>  
  
 <span data-ttu-id="2eeda-107">例如，审批状态的数据绑定可能指向以 SQL 查询的形式表示的某个数据库中某行的某一列。</span><span class="sxs-lookup"><span data-stu-id="2eeda-107">For example, a data binding for an approval status might point to a certain column in a certain row in a certain database, represented as an SQL query.</span></span> <span data-ttu-id="2eeda-108">您可能会使用友好名称“状态”来创建一个与该数据绑定相关联的词汇定义，而不是在规则中插入这种复杂的表示形式。</span><span class="sxs-lookup"><span data-stu-id="2eeda-108">Instead of inserting this sort of complex representation in a rule, you might instead create a vocabulary definition, associated with that data binding, with a friendly name of "Status."</span></span> <span data-ttu-id="2eeda-109">随后您可以将“状态”包含在任意数量的规则中，而规则引擎可以从该表中检索相应的数据。</span><span class="sxs-lookup"><span data-stu-id="2eeda-109">Subsequently you can include "Status" in any number of rules, and the rule engine can retrieve the corresponding data from the table.</span></span>  
  
 <span data-ttu-id="2eeda-110">A*词汇*是定义包含规则条件和操作中使用的事实数据的友好名称的集合。</span><span class="sxs-lookup"><span data-stu-id="2eeda-110">A *vocabulary* is a collection of definitions consisting of friendly names for the facts used in rule conditions and actions.</span></span> <span data-ttu-id="2eeda-111">通过词汇定义，处于特定业务领域中的人们可以更容易地阅读、了解和共享这些规则。</span><span class="sxs-lookup"><span data-stu-id="2eeda-111">Vocabulary definitions make the rules easier to read, understand, and share by people in a particular business domain.</span></span>  
  
 <span data-ttu-id="2eeda-112">您可以使用业务规则编辑器来定义词汇，然后将这些词汇放置在共享规则存储中。</span><span class="sxs-lookup"><span data-stu-id="2eeda-112">You can use the Business Rule Composer to define vocabularies that are then placed in the shared rule store.</span></span> <span data-ttu-id="2eeda-113">负责将规则创作集成到新应用程序或现有应用程序中的工具开发人员也可以使用词汇。</span><span class="sxs-lookup"><span data-stu-id="2eeda-113">Vocabularies can also be consumed by tool developers responsible for integrating rule authoring into new or existing applications.</span></span>  
  
 <span data-ttu-id="2eeda-114">必须将词汇标记为某个版本并在规则存储中发布该词汇，然后您才能使用该词汇。</span><span class="sxs-lookup"><span data-stu-id="2eeda-114">Before you can use a vocabulary, it must be stamped with a version and published in your rule store.</span></span> <span data-ttu-id="2eeda-115">这样是为了确保词汇中的定义不会发生更改并保持引用完整性。</span><span class="sxs-lookup"><span data-stu-id="2eeda-115">This is to guarantee that the definitions in the vocabulary will not change, and to preserve referential integrity.</span></span> <span data-ttu-id="2eeda-116">这意味着任何使用该特定版本词汇的策略都不会由于底层词汇的更改而意外失败。</span><span class="sxs-lookup"><span data-stu-id="2eeda-116">This means that any policies that use that particular version of the vocabulary will not fail unexpectedly due to changes in the underlying vocabulary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eeda-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eeda-117">See Also</span></span>  
 [<span data-ttu-id="2eeda-118">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="2eeda-118">Business Rules Engine</span></span>](../core/business-rules-engine.md)