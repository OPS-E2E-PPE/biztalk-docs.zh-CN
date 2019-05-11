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
# <a name="rule-engine"></a>规则引擎
本部分介绍几个组件、 功能和操作的业务规则引擎。 规则引擎为规则集提供的执行上下文。 **RuleEngine**对象使用以下插件组件来实现：  
  
-   **规则集执行器 （推理引擎）**。 实现负责规则条件评估和操作执行的算法。 默认规则集执行器是基于网络的正向链接推理引擎旨在优化内存中操作的对比。  
  
-   **规则集转换器**。 接受的输入**RuleSet**对象，并将生成的规则集的可执行表示形式。 默认内存中转换器创建规则集定义从编译的对比网络。  
  
-   **规则集跟踪侦听器**。 从规则集执行器 （推理引擎） 接收输出，并将其转发到规则集跟踪和监视工具。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [条件评估和操作执行](../core/condition-evaluation-and-action-execution.md)  
  
-   [议程和优先级](../core/agenda-and-priority.md)  
  
-   [引擎控制函数](../core/engine-control-functions.md)  
  
-   [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)  
  
-   [规则操作副作用](../core/rule-action-side-effects.md)  
  
-   [业务规则引擎中对类继承的支持](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [规则引擎的配置和优化参数](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [使用规则引擎时的性能注意事项](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎](../core/business-rules-engine.md)