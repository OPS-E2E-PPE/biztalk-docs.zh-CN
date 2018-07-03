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
# <a name="short-term-facts-vs-long-term-facts"></a>短期事实与长期事实
两种类型的事实会添加到规则引擎的工作内存中 — 短期事实和长期事实。  
  
## <a name="short-term-facts"></a>短期事实  
 短期事实特定于规则引擎的单个执行循环。 策略执行之后会自动从规则引擎的工作内存中取消短期事实。 如果在策略的规则引擎的两次执行循环之间数据发生了更改，则您所提交的数据将作为短期事实提交给规则引擎。  
  
 短期事实的示例有：  
  
-   您作为参数提交给事实**Policy.Execute**方法。  
  
-   您作为参数提交给事实**调用规则**形状。  
  
-   从规则使用的操作将提交的事实**Assert**函数。  
  
## <a name="long-term-facts"></a>长期事实  
 长期事实加载到规则引擎的工作内存中，可跨任意数量的执行循环使用。 通常情况下，长期事实的变化较慢，在策略的执行间隔中通常不会发生更改。 例如，您可能只想创建一次数据库连接，并想使用同一数据库连接多次执行策略。 实际上，短期事实和长期事实之间唯一的差别在于实现。  
  
 若要将事实作为长期事实提交，需要执行以下步骤：  
  
1. 创建一个事实检索器组件实现**IFactRetriever**接口。 创建和这一事实添加到工作内存中的规则引擎何时**UpdateFacts**方法调用的第一个的时间和更新事实的后续调用，可在必要时**UpdateFacts**方法。  
  
2. 使用业务规则编辑器，将策略配置为使用事实检索器组件。  
  
   有关创建事实检索器和策略中使用的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。  
  
## <a name="see-also"></a>请参阅  
 [事实](../core/facts.md)