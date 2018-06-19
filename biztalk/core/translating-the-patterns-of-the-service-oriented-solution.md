---
title: 转换的服务的模式面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], translating patterns to orchestration shapes
- artifacts, patterns
- orchestrations, patterns
- patterns [process management solutions], connections
- patterns [service solutions], orchestration boundaries
- patterns [process management solutions], translating patterns to orchestrations
- orchestrations, boundaries
- patterns [service solutions], translating patterns to artifacts
ms.assetid: ff17cc41-2a7b-4304-b5bd-96b1174cea7f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95285c93bdb290adbee988305dbcd365e4e729a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279997"
---
# <a name="translating-the-patterns-of-the-service-oriented-solution"></a>转换的服务的模式面向解决方案
本部分将介绍该解决方案如何将模式关系图转换为 BizTalk Server 项目。  
  
 ![服务 &#45; 面向的解决方案模式](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
## <a name="connections-and-completeness-conditions"></a>连接和完整性条件  
 几乎可以从任何位置开始将模式转换为 BizTalk Server 组件。 但是，组件之间的连接实际上是组件的基础结构，因此从连接位置开始比较合适。 此外，对于聚合模式，需要考虑什么将通知该模式其已具有所需的所有信息。 这会影响与其他组件的连接及其设计。  
  
 解决方案需要提供便捷、一致的使用方式。 服务界面将指定其他应用程序如何使用它。 由于解决方案需要与使用 IBM WebSphere MQ 的旧版应用程序进行通信，因此 IBM WebSphere MQ 应该是服务界面的一部分。 但是，对于较新的应用程序，Web Services 界面是个明显的选择。 Web Services 界面为其他应用程序使用该服务提供了最大的灵活性。 这里，可以利用 BizTalk Server 的灵活性使用双服务界面。 有关公开作为 Web 服务的业务流程的信息，请参阅[如何映射到 Web 服务的业务流程](../core/how-to-map-orchestrations-to-web-services.md)。  
  
 其他连接包括：服务界面和收件人列表之间的连接，收件人列表和后端应用程序之间的连接，后端应用程序、聚合和服务界面之间的连接。  
  
 如果到收件人列表的连接是同步的，则解决方案不需要使用相关来确保到达收件人列表的所有消息均已发送和接收。 出于相同原因，可以同步后端应用程序和聚合之间的连接。 聚合需要来自所有三个后端应用程序的响应来完成查询响应。 响应时间应较短，以便同步连接适当并简化解决方案。  
  
 在聚合模式中通常有一个完整性条件。 如果存在多个后端服务器并且响应时间较慢，则完整性条件可以是（例如）：在给定时间段内至少接收一个响应。 此面向服务的解决方案需要所有三个响应，以便构造最终消息。 因此，完整性条件在这里是接收所有三个响应。  
  
> [!NOTE]
>  在接收时通过 IBM WebSphere MQ 请求，解决方案通过复制将添加相关标识符**MQMD_MsgId**值赋给**MQMD_CorrelId**的响应消息。 这是在请求-答复中使用 MQSeries 适配器以避免可能争用条件的标准方法的一部分。 有关详细信息，请参阅[关联消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。  
  
## <a name="determining-orchestration-boundaries"></a>确定业务流程边界  
 解决方案必须允许来自 IBM WebSphere MQ 队列以及通过 Web Services 界面的请求。 将服务界面放置在一个业务流程中，将 IBM WebSphere MQ 输入放置在另一个业务流程中，将处理块放置在第三个业务流程中，以确保外部通信与处理相互独立。  
  
## <a name="translating-the-components-into-orchestration-shapes"></a>将组件转换为业务流程形状  
 在最终解决方案中转换为形状的模式在单个业务流程中。 在 BizTalk Server 中创建基于内容的路由器有多种方法，包括创建 MessageBox 订阅。 在解决方案中，路由使用 MessageBox 订阅。 表达式形状将评估消息是否包括所需字段的值。 决策形状评估表达式形状中设置的变量并选择通过业务流程的路径。  
  
 **CustomerService**业务流程使用并行形状来将消息发送到后端应用程序并同时接收响应。 它不必等到一个应用程序完成就可以开始下一个请求。 如果应用程序的数目经常变化，或者到应用程序的连接不可靠，则该业务流程需要以不同方式转换模式。  
  
 在解决方案中，聚合必须合并来自三个响应消息的各个元素。 使用并行形状以确保与后端系统的通信是并行的。 此外，由于形状直到接收到所有响应或超时之后才会终止，因此聚合始终知道何时可以继续操作。 业务流程使用转换形状将来自三个后端响应消息以及原始请求消息的元素映射到响应消息中的元素。  
  
> [!NOTE]
>  与后端系统的通信也可能超时。你可以通过将设置的超时期**接收**中调整**作用域**形状和设置**超时**作用域的属性。  
  
 业务流程形状的完整列表，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在服务中的模式面向解决方案](../core/patterns-in-the-service-oriented-solution.md)   
 [服务组件面向解决方案](../core/components-of-the-service-oriented-solution.md)