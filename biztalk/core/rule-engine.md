---
title: 规则引擎 |Microsoft 文档
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
ms.openlocfilehash: b0dc2d293697ccbb64851591037440d0371c1346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268725"
---
# <a name="rule-engine"></a><span data-ttu-id="9fe28-102">规则引擎</span><span class="sxs-lookup"><span data-stu-id="9fe28-102">Rule Engine</span></span>
<span data-ttu-id="9fe28-103">本部分将介绍业务规则引擎的若干组件、功能和操作。</span><span class="sxs-lookup"><span data-stu-id="9fe28-103">This section describes several components, functionalities, and operations of the Business Rule engine.</span></span> <span data-ttu-id="9fe28-104">规则引擎为规则集提供了执行上下文。</span><span class="sxs-lookup"><span data-stu-id="9fe28-104">The rule engine provides the execution context for a rule set.</span></span> <span data-ttu-id="9fe28-105">**RuleEngine**对象将用于实现以下的即插即用-在组件：</span><span class="sxs-lookup"><span data-stu-id="9fe28-105">The **RuleEngine** object uses the following plug–in components for implementation:</span></span>  
  
-   <span data-ttu-id="9fe28-106">**规则集执行程序 （推理引擎）**。</span><span class="sxs-lookup"><span data-stu-id="9fe28-106">**Ruleset executor (inference engine)**.</span></span> <span data-ttu-id="9fe28-107">实现负责规则条件评估和操作执行的算法。</span><span class="sxs-lookup"><span data-stu-id="9fe28-107">Implements the algorithm responsible for rule condition evaluation and action execution.</span></span> <span data-ttu-id="9fe28-108">默认规则集执行器是基于对比网络的正向链接推理引擎，该引擎设计为对内存中操作进行优化。</span><span class="sxs-lookup"><span data-stu-id="9fe28-108">The default rule set executor is a discrimination network-based forward-chaining inference engine designed to optimize in-memory operation.</span></span>  
  
-   <span data-ttu-id="9fe28-109">**Ruleset 转换器**。</span><span class="sxs-lookup"><span data-stu-id="9fe28-109">**Ruleset translator**.</span></span> <span data-ttu-id="9fe28-110">接受的输入**RuleSet**对象，并将生成可执行文件表示形式的规则集。</span><span class="sxs-lookup"><span data-stu-id="9fe28-110">Takes as input a **RuleSet** object and produces an executable representation of the rule set.</span></span> <span data-ttu-id="9fe28-111">默认内存中转换器根据规则集定义来创建已编译的对比网络。</span><span class="sxs-lookup"><span data-stu-id="9fe28-111">The default in-memory translator creates a compiled discrimination network from the rule set definition.</span></span>  
  
-   <span data-ttu-id="9fe28-112">**规则设置跟踪侦听器**。</span><span class="sxs-lookup"><span data-stu-id="9fe28-112">**Rule set tracking interceptor**.</span></span> <span data-ttu-id="9fe28-113">接收来自规则集执行器（推理引擎）的输出，并将其转发到规则集跟踪和监视工具。</span><span class="sxs-lookup"><span data-stu-id="9fe28-113">Receives output from the rule set executor (inference engine) and forwards it to rule set tracking and monitoring tools.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9fe28-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="9fe28-114">In This Section</span></span>  
  
-   [<span data-ttu-id="9fe28-115">条件计算和操作执行</span><span class="sxs-lookup"><span data-stu-id="9fe28-115">Condition Evaluation and Action Execution</span></span>](../core/condition-evaluation-and-action-execution.md)  
  
-   [<span data-ttu-id="9fe28-116">安排和优先级</span><span class="sxs-lookup"><span data-stu-id="9fe28-116">Agenda and Priority</span></span>](../core/agenda-and-priority.md)  
  
-   [<span data-ttu-id="9fe28-117">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="9fe28-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)  
  
-   [<span data-ttu-id="9fe28-118">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="9fe28-118">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="9fe28-119">规则操作副作用</span><span class="sxs-lookup"><span data-stu-id="9fe28-119">Rule Action Side Effects</span></span>](../core/rule-action-side-effects.md)  
  
-   [<span data-ttu-id="9fe28-120">针对业务规则引擎中的类继承的支持</span><span class="sxs-lookup"><span data-stu-id="9fe28-120">Support for Class Inheritance in the Business Rule Engine</span></span>](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="9fe28-121">规则引擎配置和优化参数</span><span class="sxs-lookup"><span data-stu-id="9fe28-121">Rule Engine Configuration and Tuning Parameters</span></span>](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [<span data-ttu-id="9fe28-122">使用规则引擎时的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="9fe28-122">Performance Considerations When Using the Rule Engine</span></span>](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a><span data-ttu-id="9fe28-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fe28-123">See Also</span></span>  
 [<span data-ttu-id="9fe28-124">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="9fe28-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)