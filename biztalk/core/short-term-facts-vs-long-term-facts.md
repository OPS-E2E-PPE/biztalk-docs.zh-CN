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
ms.openlocfilehash: 8319f0836d20a09765bb22933c129065d5393317
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393211"
---
# <a name="short-term-facts-vs-long-term-facts"></a>短期事实与长期事实
两种类型的事实将添加到规则引擎工作内存 — 短期事实和长期事实。  
  
## <a name="short-term-facts"></a>短期事实  
 短期事实是特定于规则引擎的单个执行循环。 短期事实从规则引擎工作内存策略执行之后自动取消。 如果你的数据更改之间的规则引擎策略执行循环，为规则引擎的短期事实提交数据。  
  
 短期事实的示例包括：  
  
-   您作为参数提交给事实**Policy.Execute**方法。  
  
-   您作为参数提交给事实**调用规则**形状。  
  
-   从规则使用的操作将提交的事实**Assert**函数。  
  
## <a name="long-term-facts"></a>长期事实  
 长期事实加载到任意数目的执行循环的使用规则引擎工作内存中。 通常情况下，长期事实变化较慢，通常不在策略的执行之间更改的事实。 例如，你可能想要创建的数据库连接一次，并使用相同的数据库连接多次执行策略。 短期事实与长期事实之间的唯一的真正差别在于实现。  
  
 若要提交事实作为长期事实，您需要执行以下步骤：  
  
1. 创建一个事实检索器组件实现**IFactRetriever**接口。 创建和这一事实添加到工作内存中的规则引擎何时**UpdateFacts**方法调用的第一个的时间和更新事实的后续调用，可在必要时**UpdateFacts**方法。  
  
2. 配置要使用业务规则编辑器中使用事实检索器组件的策略。  
  
   有关创建事实检索器和策略中使用的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。  
  
## <a name="see-also"></a>请参阅  
 [事实](../core/facts.md)