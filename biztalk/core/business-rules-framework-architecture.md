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
ms.openlocfilehash: bb8ee592cbb83f9094a1430d12b08a573d858c88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357685"
---
# <a name="business-rules-framework-architecture"></a>业务规则框架体系结构
下图显示了业务规则框架的组件体系结构。  
  
 ![业务规则框架组件体系结构](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")  
Microsoft 业务规则框架体系结构  
  
 下面的段落中介绍了一些 framework 的组件。  
  
## <a name="policy-class"></a>Policy 类  
 一个**策略**对象是业务策略，一个单一实例，并提供基于规则的应用程序使用的接口。 它提供了抽象概念，使应用程序开发人员从规则存储的位置有关的问题实例化基础规则引擎的实例，并确保长期事实添加到从规则存储中提取规则集引擎。 在许多情况下，基于规则的应用程序使用的并发实例**策略**对象。 这些并行实例可以表示相同的策略、 同一策略的不同版本或不同版本的不同的策略。  
  
## <a name="ruleengine-class"></a>RuleEngine 类  
 **RuleEngine**对象充当业务策略的执行引擎。 它使用三个插件组件 （转换器、 推理引擎和跟踪侦听器） 来实现。 一个**RuleEngine**对象采用**RuleSet**对象表示业务策略作为输入，并使用转换器、 推理引擎和跟踪侦听器配置为规则集来实现业务规则集定义的策略。  
  
## <a name="fact-retriever"></a>事实检索器  
 事实检索器是一个可选的、 用户定义的插件组件负责收集供业务策略使用的长期事实。 有关详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。  
  
 在执行前**策略**对象实例提供了其**RuleEngine**对事实检索器，让其有机会更新的规则引擎中的事实数据集的实例的工作内存。 有关详细信息，请参阅[短期事实与。长期事实](../core/short-term-facts-vs-long-term-facts.md)。  
  
## <a name="rule-engine-update-service"></a>规则引擎更新服务  
 规则引擎更新服务提供了在分布式环境中的动态业务策略更新。 一个自动启动 Microsoft Windows NT 服务应用程序负责订阅策略部署和取消部署在更改业务策略时发生的事件。  
  
 在典型的企业方案中，业务策略进行部署后正在更新、 测试和版本控制。 部署包含将更新后的策略添加到安全、 持久化规则存储和 （可选） 若要将更新后的策略有关的信息发布到所有相关方对存储区执行逻辑 (请注意，发布有关策略的信息，而不策略本身）。  
  
 托管的基于规则的应用程序的服务器上运行的规则引擎更新服务接收策略更新通知，并缓存信息以供后续使用。 发布/订阅模型用于策略更新，可更改而无需服务停机或中断的近乎实时的业务策略。  
  
## <a name="policyvocabulary-authoring-tools"></a>策略/词汇创作工具  
 在 Microsoft 业务规则编辑器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供策略和词汇创作向最终用户和开发人员的功能。  
  
## <a name="rule-store"></a>规则存储  
 一个*规则存储*是业务策略和词汇的存储库。 存储库可以是一个简单的文件或安全、 可缩放、 持久的且可靠的数据库，例如 Microsoft SQL Server。 （SQL Server 用作默认规则存储为 framework）。  
  
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
  
7. **策略**对象取消从短期事实**RuleEngine**。 添加事实检索器的长期事实将保留在规则引擎工作内存中。  
  
   之后**Dispose**上调用方法**策略**对象， **RuleEngine**实例被释放回规则引擎缓存。  
  
   如果负载需要它，并且每个规则引擎实例都具有其自己的事实检索器实例，则规则引擎缓存将具有给定的策略版本的多个规则引擎实例。  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎](../core/business-rules-engine.md)