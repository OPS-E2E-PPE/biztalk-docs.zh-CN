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
# <a name="vocabularies"></a>词汇表
通常使用特定于领域或行业的命名法来表示用于定义规则条件和操作的术语。 例如，电子邮件用户使用“接收自”消息和“收到时间晚于”消息等术语来编写规则，而保险业务分析员则使用“风险因素”和“保险金额”等术语来编写规则。  
  
 这种特定于领域的术语的底层是实施规则条件和规则操作的技术项目（对象、数据库表和 XML 文档）。 Vocabulariesare 旨在业务语义和实现之间的桥梁。  
  
 例如，审批状态的数据绑定可能指向以 SQL 查询的形式表示的某个数据库中某行的某一列。 您可能会使用友好名称“状态”来创建一个与该数据绑定相关联的词汇定义，而不是在规则中插入这种复杂的表示形式。 随后您可以将“状态”包含在任意数量的规则中，而规则引擎可以从该表中检索相应的数据。  
  
 A*词汇*是定义包含规则条件和操作中使用的事实数据的友好名称的集合。 通过词汇定义，处于特定业务领域中的人们可以更容易地阅读、了解和共享这些规则。  
  
 您可以使用业务规则编辑器来定义词汇，然后将这些词汇放置在共享规则存储中。 负责将规则创作集成到新应用程序或现有应用程序中的工具开发人员也可以使用词汇。  
  
 必须将词汇标记为某个版本并在规则存储中发布该词汇，然后您才能使用该词汇。 这样是为了确保词汇中的定义不会发生更改并保持引用完整性。 这意味着任何使用该特定版本词汇的策略都不会由于底层词汇的更改而意外失败。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则引擎](../core/business-rules-engine.md)