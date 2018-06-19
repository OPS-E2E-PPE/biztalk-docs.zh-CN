---
title: 服务的模式目录面向解决方案 |Microsoft 文档
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
ms.openlocfilehash: 9441ead974cdcaba66dd9d038e786a5a8c7b156e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265493"
---
# <a name="pattern-catalog-for-the-service-oriented-solution"></a>服务的模式目录面向解决方案
面向服务的解决方案中的模式包括特定于 BizTalk Server 的编程实践的模式，以及前面部分中的企业集成模式。 本部分中的列表包括这两种类型的模式。  
  
## <a name="pattern-types"></a>模式类型  
 以下主题中描述的条目对模式进行了简要说明，并指向说明该解决方案如何使用此模式的其他主题。 在使用常规模式（例如筛选器）的情况下，条目将指向更多常规主题。  
  
### <a name="aggregation-pattern"></a>聚合模式  
 聚合是接收来自多个来源的信息并将其合并为单个消息的模式。 面向服务的解决方案将来自三个不同来源的信用信息组合到单个响应中。 您可以通过多种不同方式进行聚合，这取决于要编写的解决方案的特性。 在某些情况下，您可能需要等待所有响应。 而在其他情况下，例如在申请贷款时，您可能希望只要提供最低数据量即可提早获得响应。 面向服务的解决方案会一直等到获得所有三个响应，因为它需要所有这三个响应才能得出要返回的完整信用报告。 有关详细信息，请参阅[转换服务面向解决方案的模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。  
  
### <a name="calling-pipelines-from-code-pattern"></a>通过代码模式调用管道  
 您现在可以从代码和业务流程中调用管道。 这允许重复使用的管道，并帮助维护从管道阶段的业务流程的分离。 有关详细信息，请参阅[从服务面向解决方案使用管道](../core/using-pipelines-from-the-service-oriented-solution.md)。  
  
### <a name="caching-pattern"></a>缓存模式  
 缓存是用于存储信息而不是每次请求信息时都从数据存储区中检索该信息的常规策略。 从企业单一登录系统中检索参考数据或配置数据已确认为解决方案中的一个限制性因素。 该解决方案将缓存信息，并定期刷新缓存。 有关详细信息，请参阅[服务面向解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)。 尽管业务流程管理解决方案使用的流程略有不同，但该解决方案也缓存 SSO 信息。 有关详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。  
  
### <a name="content-based-routing-pattern"></a>基于内容的路由模式  
 与 BizTalk 中相比，企业集成模式中更为广泛地考虑了基于内容的路由。 在企业集成模式中，基于内容的路由将根据消息内容的某个部分来确定该消息的收件人。 面向服务的解决方案使用一种十分简单的基于内容的路由形式：业务流程中的单个决策形状将消息发送到两个位置中的某一位置。 详细信息，请参阅"将转换组件到业务流程形状链接"中[转换服务面向解决方案的模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。  
  
### <a name="filter-pattern"></a>筛选器模式  
 筛选模式可以选择符合特定处理条件的消息。 在 BizTalk Server 中，筛选模式几乎总是以端口的筛选器表达式的形式来实现。 有关端口上的筛选器的详细信息，请参阅[使用筛选器与接收消息 Shape](../core/using-filters-with-the-receive-message-shape.md)。  
  
### <a name="inline-invocation-of-back-end-processes-pattern"></a>后端进程模式的内联调用  
 解决方案的内联版本通过自定义程序集来使用后端进程的内联调用。 这样做的好处是可以极大地改进性能。 不过，其代价是业务流程与传输协议的紧密连接。 有关详细信息，请参阅[内联后端调用](../core/inlining-back-end-invocation.md)。  
  
### <a name="recipient-list-pattern"></a>收件人列表模式  
 在抽象意义上，面向服务的解决方案实现了一个收件人列表，因为该解决方案向三个不同的系统发送消息。 就实际角度而言，已部署的应用程序通过将逻辑端口映射到特定位置来确定收件人。 对于应用程序的内联版本，将通过 SSO 中的配置信息进行连接。 有关详细信息，请参阅[转换服务面向解决方案的模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。  
  
### <a name="service-interface-pattern"></a>服务接口模式  
 面向服务的解决方案自身以 Web Services 形式出现，后者只是实现服务的多种方式之一。 有关作为 Web 服务使用业务流程的详细信息，请参阅[使用 Web 服务](../core/using-web-services.md)。  
  
### <a name="translator-pattern"></a>转换器模式  
 转换器（即将消息从一种格式转换为另一种格式）的企业模式经常翻译为 BizTalk Server 映射。 有关 BizTalk Server 映射的常规信息，请参阅[创建映射使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在服务中的模式面向解决方案](../core/patterns-in-the-service-oriented-solution.md)