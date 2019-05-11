---
title: 规则引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RuleEngine object
- Business Rules Engine, ruleset executor
- Business Rules Engine, ruleset translator
- Business Rules Engine, ruleset tracking interceptor
- Business Rules Engine, Business Rules Engine
ms.assetid: c4043a1f-357f-47bc-84e1-5e4bd9f8b5b8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30e250dcc058202d91066e1d2d4cd367a8dfad06
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254634"
---
# <a name="rule-engine"></a><span data-ttu-id="40e45-102">规则引擎</span><span class="sxs-lookup"><span data-stu-id="40e45-102">Rule Engine</span></span>
<span data-ttu-id="40e45-103">本部分介绍几个组件、 功能和操作的业务规则引擎。</span><span class="sxs-lookup"><span data-stu-id="40e45-103">This section describes several components, functionalities, and operations of the Business Rule engine.</span></span> <span data-ttu-id="40e45-104">规则引擎为规则集提供的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="40e45-104">The rule engine provides the execution context for a rule set.</span></span> <span data-ttu-id="40e45-105">**RuleEngine**对象使用以下插件组件来实现：</span><span class="sxs-lookup"><span data-stu-id="40e45-105">The **RuleEngine** object uses the following plug–in components for implementation:</span></span>  
  
-   <span data-ttu-id="40e45-106">**规则集执行器 （推理引擎）**。</span><span class="sxs-lookup"><span data-stu-id="40e45-106">**Ruleset executor (inference engine)**.</span></span> <span data-ttu-id="40e45-107">实现负责规则条件评估和操作执行的算法。</span><span class="sxs-lookup"><span data-stu-id="40e45-107">Implements the algorithm responsible for rule condition evaluation and action execution.</span></span> <span data-ttu-id="40e45-108">默认规则集执行器是基于网络的正向链接推理引擎旨在优化内存中操作的对比。</span><span class="sxs-lookup"><span data-stu-id="40e45-108">The default rule set executor is a discrimination network-based forward-chaining inference engine designed to optimize in-memory operation.</span></span>  
  
-   <span data-ttu-id="40e45-109">**规则集转换器**。</span><span class="sxs-lookup"><span data-stu-id="40e45-109">**Ruleset translator**.</span></span> <span data-ttu-id="40e45-110">接受的输入**RuleSet**对象，并将生成的规则集的可执行表示形式。</span><span class="sxs-lookup"><span data-stu-id="40e45-110">Takes as input a **RuleSet** object and produces an executable representation of the rule set.</span></span> <span data-ttu-id="40e45-111">默认内存中转换器创建规则集定义从编译的对比网络。</span><span class="sxs-lookup"><span data-stu-id="40e45-111">The default in-memory translator creates a compiled discrimination network from the rule set definition.</span></span>  
  
-   <span data-ttu-id="40e45-112">**规则集跟踪侦听器**。</span><span class="sxs-lookup"><span data-stu-id="40e45-112">**Rule set tracking interceptor**.</span></span> <span data-ttu-id="40e45-113">从规则集执行器 （推理引擎） 接收输出，并将其转发到规则集跟踪和监视工具。</span><span class="sxs-lookup"><span data-stu-id="40e45-113">Receives output from the rule set executor (inference engine) and forwards it to rule set tracking and monitoring tools.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40e45-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="40e45-114">In This Section</span></span>  
  
-   [<span data-ttu-id="40e45-115">条件评估和操作执行</span><span class="sxs-lookup"><span data-stu-id="40e45-115">Condition Evaluation and Action Execution</span></span>](../core/condition-evaluation-and-action-execution.md)  
  
-   [<span data-ttu-id="40e45-116">议程和优先级</span><span class="sxs-lookup"><span data-stu-id="40e45-116">Agenda and Priority</span></span>](../core/agenda-and-priority.md)  
  
-   [<span data-ttu-id="40e45-117">引擎控制函数</span><span class="sxs-lookup"><span data-stu-id="40e45-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)  
  
-   [<span data-ttu-id="40e45-118">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="40e45-118">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="40e45-119">规则操作副作用</span><span class="sxs-lookup"><span data-stu-id="40e45-119">Rule Action Side Effects</span></span>](../core/rule-action-side-effects.md)  
  
-   [<span data-ttu-id="40e45-120">业务规则引擎中对类继承的支持</span><span class="sxs-lookup"><span data-stu-id="40e45-120">Support for Class Inheritance in the Business Rule Engine</span></span>](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="40e45-121">规则引擎的配置和优化参数</span><span class="sxs-lookup"><span data-stu-id="40e45-121">Rule Engine Configuration and Tuning Parameters</span></span>](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [<span data-ttu-id="40e45-122">使用规则引擎时的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="40e45-122">Performance Considerations When Using the Rule Engine</span></span>](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a><span data-ttu-id="40e45-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="40e45-123">See Also</span></span>  
 [<span data-ttu-id="40e45-124">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="40e45-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)