---
title: 业务规则引擎 |Microsoft 文档
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
ms.openlocfilehash: d99cff10324f1cf1ba97d99431524474ed5f039b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232613"
---
# <a name="business-rules-engine"></a>业务规则引擎
业务规则框架是一个符合 Microsoft .NET 的类库。 它提供了一个有效的推理引擎，可以将高可读性、描述性和语义丰富的规则链接到任何业务对象（.NET 组件）、XML 文档或数据库表。 应用程序开发人员可以通过使用作用于 .NET 对象、数据库表和 XML 文档中所包含信息（事实）的小型业务逻辑生成块（小型规则集）来构造规则，进而构建业务规则。 此设计模式可以提高代码重用率，简化设计，以及促进业务逻辑的模块化。 此外，不会对业务应用程序的结构或设计强制应用该规则引擎。 事实上，您可以通过直接调用规则引擎向业务应用程序中添加规则技术，也可以使用外部逻辑来调用您的业务对象而不必对其进行修改。 简而言之，该技术使得开发人员只需投入极少的精力用于创建和维护应用程序。  
  
 在制订基于规则的应用程序的开发计划时，首先需要确定如何将规则融入您的业务流程中。 您的应用程序将创建一个策略实例，并为其提供要操作的数据（或事实）。 该策略对象包含规则引擎，并提供了一个单一入口点（通过该入口点来运行规则引擎）。  
  
 您还将需要制订规则设计的开发和测试计划。 您必须考虑将如何部署和更新策略。 您可能需要跟踪规则引擎的执行进度，并监视其当前状态。  
  
 在制订规则开发计划时，请考虑执行以下步骤：  
  
1.  规划如何将规则集成到应用程序中。  
  
2.  标识出要在应用程序中使用规则来表示的业务逻辑。 术语“业务逻辑”可以指代许多内容；例如，“超过五百美元的采购订单必须由经理批准”就是一个业务逻辑示例。  
  
3.  标识出规则元素的数据源。 您可以选择定义和发布词汇（表示底层绑定的特定于领域的术语）。  
  
4.  通过词汇定义或直接通过数据绑定来定义规则，并通过所定义的规则编写一个表示您的业务逻辑的策略。  
  
    > [!NOTE]
    >  必须先发布词汇，才能在规则中应用这些词汇。  
  
5.  使用示例事实测试和调试策略。 你可以使用业务规则编辑器中的测试策略功能，也可以使用**策略**或**PolicyTester**类来执行从应用程序、 命令行程序或业务流程。  
  
6.  将策略版本发布到规则存储中。  
  
7.  部署策略版本。  
  
8.  在宿主应用程序中实例化和生成短期事实列表。 使用**调用规则**形状中业务流程执行你的业务策略或以编程方式实例化宿主应用程序中的策略版本。  
  
9. 根据需要监视和跟踪规则执行情况。  
  
    > [!NOTE]
    >  默认跟踪侦听器只能监视和跟踪业务流程。 如果您的宿主应用程序不是业务流程，则必须编写自己的跟踪侦听器以实现监视和跟踪功能。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [规则](../core/rules.md)  
  
-   [策略](../core/policies.md)  
  
-   [词汇表](../core/vocabularies.md)  
  
-   [业务规则 Framework 体系结构](../core/business-rules-framework-architecture.md)  
  
-   [事实](../core/facts.md)  
  
-   [规则引擎](../core/rule-engine.md)