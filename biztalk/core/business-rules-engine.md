---
title: 业务规则引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Engine
- Business Rules Engine
- Business Rules Engine, rules
- Business Rules Engine, about Business Rules Engine
ms.assetid: 87b38507-9f6d-4863-88a6-9c20f15a4e55
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aea07fd5b73fcc333a94c6d199db1e303fcc310d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357742"
---
# <a name="business-rules-engine"></a>业务规则引擎
业务规则框架是 Microsoft。NET 符合类库。 它提供了一种有效的推理引擎，可以将高可读性、 描述性和语义丰富的规则链接到任何业务对象 （.NET 组件）、 XML 文档或数据库表。 应用程序开发人员可以通过构造从小型构建基块的业务逻辑 （小型规则集） 在.NET 对象、 数据库表和 XML 文档中包含的信息 （事实） 上运行的规则来生成业务规则。 此设计模式可以提高代码重用，简化设计，以及业务逻辑的模块性。 此外，规则引擎不会施加业务线应用程序设计的体系结构上。 事实上，可以向业务应用程序添加规则技术，通过直接调用规则引擎，或可以使用外部逻辑来调用您的业务对象而无需修改它们。 简单地说，该技术使开发人员能够创建和维护应用程序最小的工作量。  
  
 在规划开发的基于规则的应用程序中，首先需要确定如何将规则融入您的业务流程。 你的应用程序将创建的策略实例，并提供数据或事实数据，用于执行操作。 策略对象封装规则引擎，并提供单一用来运行它的入口点。  
  
 您还需要规划的开发和测试规则设计。 您必须考虑你将如何部署和更新你的策略。 则可能会想要跟踪的规则引擎的执行进度和监视其当前状态。  
  
 在规划规则开发的帐户的以下步骤：  
  
1.  规划如何将规则集成到应用程序。  
  
2.  标识你想要表示，并将你的应用程序中的规则的业务逻辑。 术语"业务逻辑"可以指许多内容;业务逻辑的一个示例是"超过五百美元的采购订单必须批准由管理器。"  
  
3.  确定所选规则的元素的数据源。 （可选） 可以定义和发布词汇 （表示底层绑定的特定于域的术语）。  
  
4.  定义规则从词汇定义或直接通过数据绑定，并从这些撰写一个策略，表示您的业务逻辑。  
  
    > [!NOTE]
    >  它们可以在规则中应用之前，必须先发布词汇。  
  
5.  测试和调试使用示例事实的策略。 可以使用业务规则编辑器中的测试策略功能或使用**策略**或**PolicyTester**类，以从应用程序、 命令行程序或业务流程执行。  
  
6.  将策略版本发布到规则存储。  
  
7.  部署策略版本。  
  
8.  实例化和生成短期事实列表宿主应用程序中。 使用**调用规则**形状在业务流程执行您的业务策略或以编程方式实例化宿主应用程序中的策略版本中。  
  
9. 监视和跟踪规则执行根据需要。  
  
    > [!NOTE]
    >  默认跟踪侦听器只能监视和业务流程。 如果在宿主应用程序不是业务流程，则必须编写您自己的跟踪侦听器来执行此操作。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [规则](../core/rules.md)  
  
-   [策略](../core/policies.md)  
  
-   [词汇](../core/vocabularies.md)  
  
-   [业务规则框架体系结构](../core/business-rules-framework-architecture.md)  
  
-   [事实](../core/facts.md)  
  
-   [规则引擎](../core/rule-engine.md)