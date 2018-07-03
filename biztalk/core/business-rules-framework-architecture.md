---
title: 业务规则框架体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, caching
- Business Rules Framework, Rule Engine Update service
- rule store [Business Rules Framework]
- Policy class [Business Rules Engine]
- Business Rules Framework, architecture
- Business Rules Framework, RuleEngine class
- Business Rules Framework, Policy class
- Business Rules Framework, authoring tools
- RuleEngine class [Business Rules Engine]
- caching, Business Rules Framework
- Business Rules Framework, fact retrievers
- architecture, Business Rules Framework
- Business Rules Framework, rule store
ms.assetid: f5570cca-7664-4180-af9c-64ef90a0022b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55c624f8eaac517d11774ec2c542bf4ddbe0351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971838"
---
# <a name="business-rules-framework-architecture"></a>业务规则框架体系结构
下图显示了业务规则框架的组件结构。  
  
 ![业务规则框架组件体系结构](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")  
Microsoft 业务规则框架结构  
  
 以下段落对该框架的一些组件进行了说明。  
  
## <a name="policy-class"></a>Policy 类  
 一个**策略**对象是业务策略，一个单一实例，并提供基于规则的应用程序使用的接口。 它提供一个抽象概念，使应用程序开发人员不必关心规则存储的位置，即可从规则存储中提取规则集，实例化基础规则引擎的实例，以及确保将长期事实添加到引擎中。 在许多情况下，基于规则的应用程序使用的并发实例**策略**对象。 这些并行实例可以表示同一策略、同一策略的不同版本或不同策略的不同版本。  
  
## <a name="ruleengine-class"></a>RuleEngine 类  
 **RuleEngine**对象充当业务策略的执行引擎。 它使用三个插件组件（转换器、推理引擎和跟踪侦听器）来实现业务策略。 一个**RuleEngine**对象采用**RuleSet**对象表示业务策略作为输入，并使用转换器、 推理引擎和跟踪侦听器配置为规则集来实现业务规则集定义的策略。  
  
## <a name="fact-retriever"></a>事实检索器  
 事实检索器是一种用户定义的可选插件组件，负责收集供业务策略使用的长期事实。 有关详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。  
  
 在执行前**策略**对象实例提供了其**RuleEngine**对事实检索器，让其有机会更新的规则引擎中的事实数据集的实例的工作内存。 有关详细信息，请参阅[短期事实与。长期事实](../core/short-term-facts-vs-long-term-facts.md)。  
  
## <a name="rule-engine-update-service"></a>规则引擎更新服务  
 规则引擎更新服务可以在分布式环境中提供动态业务策略更新。 一个自动启动 Microsoft Windows NT 服务应用程序负责订阅在更改业务策略时发生的策略部署和取消部署事件 。  
  
 在典型的企业方案中，业务策略在更新、测试和版本控制之后进行部署。 部署包括将更新的策略添加到安全、持久化规则存储中，并可以选择对该存储执行逻辑，以便将与更新的策略有关的信息发布到所有有关方（请注意，是发布与策略有关的信息，而不是发布策略本身）。  
  
 在承载基于规则的应用程序的服务器上运行的规则引擎更新服务接收策略更新通知，并缓存信息以供后面使用。 通过将发布/订阅模型用于策略更新，您可以在不造成服务停机或中断的情况下以接近实时的方式更改业务策略。  
  
## <a name="policyvocabulary-authoring-tools"></a>策略/词汇创作工具  
 在 Microsoft 业务规则编辑器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供策略和词汇创作向最终用户和开发人员的功能。  
  
## <a name="rule-store"></a>规则存储  
 一个*规则存储*是业务策略和词汇的存储库。 该存储库既可以是一个简单文件，也可以是安全、可伸缩、持久和可靠的数据库，例如 Microsoft SQL Server。 （SQL Server 用作该框架的默认规则存储）。  
  
## <a name="caching"></a>Caching  
 业务规则引擎框架提供的一种缓存机制**RuleEngine**实例。 每个**RuleEngine**实例包含特定策略版本的内存中表示形式。  
  
 以下步骤介绍了如何新建**策略**实例进行实例化 (通过调用 API，或执行**调用规则**形状):  
  
1. **策略**对象请求**RuleEngine**从规则引擎缓存实例。  
  
2. 如果**RuleEngine**实例的策略版本在缓存中，存在**RuleEngine**实例返回到**策略**对象。 如果**RuleEngine**实例不可用，请在缓存创建的新实例。 当**RuleEngine**实例被实例化，匹配，反过来，如果其中一个配置为策略版本创建新的事实检索器实例。  
  
   当**Execute**上调用方法**策略**对象，将执行以下步骤：  
  
3. 策略的对象调用**UpdateFacts**事实检索器实例中，如果存在事实检索器上的方法。 方法的事实检索器实现可能会添加到工作内存中的长期事实**RuleEngine**。  
  
4. **策略**对象添加中包含的短期事实**数组**为传入**Execute**调用。  
  
5. **策略**对象调用**Execute**上**RuleEngine**。  
  
6. **RuleEngine**完成执行，并将控制权返回给**策略**对象。  
  
7. **策略**对象取消从短期事实**RuleEngine**。 事实检索器添加的长期事实将保留在规则引擎的工作内存中。  
  
   之后**Dispose**上调用方法**策略**对象， **RuleEngine**实例被释放回规则引擎缓存。  
  
   对于给定的策略版本（如果负载需要该版本），规则引擎缓存将具有多个规则引擎实例，并且每个规则引擎实例都具有自己的事实检索器实例。  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎](../core/business-rules-engine.md)