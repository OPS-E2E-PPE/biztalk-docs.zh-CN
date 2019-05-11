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
# <a name="vocabularies"></a>词汇
按域或特定于行业的命名法通常表示用于定义规则条件和操作的术语。 例如，电子邮件用户写入的消息的规则"收到来自"和"接收消息后，"而保险业务分析人员来编写规则"风险因素"和"保险金额"。  
  
 基础此特定于域的术语是实施规则条件和规则操作的技术项目 （对象、 数据库表和 XML 文档）。 Vocabulariesare 设计为用于消除业务语义与实施之间的差距。  
  
 例如，审批状态的数据绑定可能指向某个数据库，表示为一个 SQL 查询中某一行中的某列。 而不是在规则中插入这种复杂的表示形式，而是可以创建与数据绑定、"状态。"的友好名称与相关联的词汇定义 随后可以在任意数量的规则，包括"状态"和规则引擎可以从表中检索相应的数据。  
  
 一个*词汇*是定义的规则条件和操作中使用的事实的友好名称组成的集合。 词汇定义使规则更易于阅读、 理解和的特定业务域中的人员共享。  
  
 可以使用业务规则编辑器来定义词汇，然后放置在共享的规则存储中。 负责将规则创作到新的或现有的应用程序集成的工具开发人员也可以使用词汇。  
  
 可以使用某一词汇之前，它必须标记为某个版本并发布规则存储中。 这是保证，不会更改在词汇定义，并保持引用完整性。 这意味着，任何使用该特定版本的词汇的策略将不会意外失败由于底层词汇中的更改。  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎](../core/business-rules-engine.md)