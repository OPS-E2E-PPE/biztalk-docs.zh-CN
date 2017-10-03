---
title: "规则引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RuleEngine object
- Business Rules Engine, ruleset executor
- Business Rules Engine, ruleset translator
- Business Rules Engine, ruleset tracking interceptor
- Business Rules Engine, Business Rules Engine
ms.assetid: c4043a1f-357f-47bc-84e1-5e4bd9f8b5b8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dc2d293697ccbb64851591037440d0371c1346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="rule-engine"></a>规则引擎
本部分将介绍业务规则引擎的若干组件、功能和操作。 规则引擎为规则集提供了执行上下文。 **RuleEngine**对象将用于实现以下的即插即用-在组件：  
  
-   **规则集执行程序 （推理引擎）**。 实现负责规则条件评估和操作执行的算法。 默认规则集执行器是基于对比网络的正向链接推理引擎，该引擎设计为对内存中操作进行优化。  
  
-   **Ruleset 转换器**。 接受的输入**RuleSet**对象，并将生成可执行文件表示形式的规则集。 默认内存中转换器根据规则集定义来创建已编译的对比网络。  
  
-   **规则设置跟踪侦听器**。 接收来自规则集执行器（推理引擎）的输出，并将其转发到规则集跟踪和监视工具。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [条件计算和操作执行](../core/condition-evaluation-and-action-execution.md)  
  
-   [安排和优先级](../core/agenda-and-priority.md)  
  
-   [引擎控制功能](../core/engine-control-functions.md)  
  
-   [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)  
  
-   [规则操作副作用](../core/rule-action-side-effects.md)  
  
-   [针对业务规则引擎中的类继承的支持](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [规则引擎配置和优化参数](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [使用规则引擎时的性能注意事项](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a>另请参阅  
 [业务规则引擎](../core/business-rules-engine.md)