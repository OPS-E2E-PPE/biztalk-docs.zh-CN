---
title: 面向服务的模式目录解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Calling Pipelines from Code pattern [service solutions]
- Recipient List pattern [service solutions]
- filters, design patterns
- Filter pattern [service solutions]
- caching, patterns [service solutions]
- Service Interface pattern [service solutions]
- Content-Based Routing pattern [service solutions]
- Inline Invocation of Back-End Processes pattern [service solutions]
- content-based routing, patterns [service solutions]
- messages, Translator pattern [service solutions]
- aggregations, patterns [service solutions]
- Translator pattern, service solutions
- Caching pattern [service solutions]
- Aggregation pattern [service solutions]
- patterns [service solutions], pattern types
- back-end processes
- services, interface pattern [service solutions]
ms.assetid: 5d8135c5-d5de-4e61-b3e8-2aa7f6de98c8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e014520057a47145daeeb0ee2a1e03a4f88e1af6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291882"
---
# <a name="pattern-catalog-for-the-service-oriented-solution"></a>面向服务的模式目录的解决方案
面向服务的解决方案中的模式包括前面部分中的特定于 BizTalk Server 的编程做法模式以及企业集成模式。 本部分中的列表包括这两种类型的模式。  
  
## <a name="pattern-types"></a>模式类型  
 简要介绍以下主题中的条目来描述模式，并指向说明该解决方案如何使用此模式的其他主题。 在常规模式，例如筛选器的情况下条目指向更多常规主题。  
  
### <a name="aggregation-pattern"></a>聚合模式  
 聚合是从多个源接收的信息，并且合并为单个消息的模式。 面向服务的解决方案将组合到单个响应的信用额度信息来自三个不同的源。 你可以执行聚合多个不同的方式，具体取决于您正在编写的解决方案的特性。 在某些情况下，可能需要等待所有响应。 在其他情况下，例如在申请贷款时，您可能不会放弃获得响应，因此只要有一些最小数目。 面向服务的解决方案等待，直到它具有所有三个响应，因为它需要所有这三个以便具有返回的完整信用报告。 有关详细信息，请参阅[转换的面向服务的解决方案模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。  
  
### <a name="calling-pipelines-from-code-pattern"></a>通过代码模式调用管道  
 现在可以从您的代码和业务流程调用管道。 这允许重复使用的管道，并有助于保持业务流程与管道阶段的分离。 有关详细信息，请参阅[从面向服务的解决方案使用管道](../core/using-pipelines-from-the-service-oriented-solution.md)。  
  
### <a name="caching-pattern"></a>缓存模式  
 缓存是存储信息而不必每次请求时从数据存储区检索的常规策略。 从企业单一登录系统中检索引用或配置数据被证明是解决方案中的限制因素。 该解决方案将缓存的信息，并定期刷新缓存。 有关详细信息，请参阅[面向服务的解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)。 业务流程管理解决方案也缓存 SSO 信息，但它使用过程略有不同。 有关详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。  
  
### <a name="content-based-routing-pattern"></a>基于内容的路由模式  
 在企业集成模式，基于内容的路由是 BizTalk 比更为广泛地考虑。 在企业集成模式中，基于内容的路由确定基于消息的内容的某些部分消息的收件人。 面向服务的解决方案使用非常简单的基于内容的路由形式 — 在业务流程中的单个决策形状将发送的消息的两个位置之一。 有关详细信息，请参阅"将转换组件到业务流程形状"中[转换的面向服务的解决方案模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。  
  
### <a name="filter-pattern"></a>筛选器模式  
 筛选器模式可以选择符合特定处理条件的消息。 在 BizTalk Server 中，筛选模式几乎总是会变为端口上的筛选器表达式。 有关端口的筛选器的详细信息，请参阅[使用筛选器与接收消息形状](../core/using-filters-with-the-receive-message-shape.md)。  
  
### <a name="inline-invocation-of-back-end-processes-pattern"></a>后端进程模式的内联调用  
 该解决方案的内联版本使用通过自定义程序集的后端进程的内联调用。 这样做的好处的极大地提高性能。 它需要付出一定代价，但是的紧密连接的传输协议的业务流程。 有关详细信息，请参阅[内联后端调用](../core/inlining-back-end-invocation.md)。  
  
### <a name="recipient-list-pattern"></a>收件人列表模式  
 在抽象意义上，面向服务的解决方案，它将消息发送到三个不同的系统实现收件人列表。 实际上，部署的应用程序通过将逻辑端口映射到特定位置来确定收件人。 对于内联版本的应用程序，通过 SSO 中的配置信息进行连接。 有关详细信息，请参阅[转换的面向服务的解决方案模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。  
  
### <a name="service-interface-pattern"></a>服务接口模式  
 面向服务的解决方案自身都表示为 Web 服务，实现服务的多种方式之一。 有关使用业务流程作为 Web 服务的详细信息，请参阅[使用 Web 服务的](../core/using-web-services.md)。  
  
### <a name="translator-pattern"></a>转换器模式  
 转换器的企业模式 — 即的一条消息从一个格式转换为另一种形式 — 经常翻译为 BizTalk Server 映射。 有关 BizTalk Server 映射的常规信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。  
  
## <a name="see-also"></a>请参阅  
 [面向服务的解决方案中的模式](../core/patterns-in-the-service-oriented-solution.md)