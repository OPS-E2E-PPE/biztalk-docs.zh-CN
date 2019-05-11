---
title: 将服务的模式转换面向解决方案 |Microsoft Docs
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
ms.openlocfilehash: 71d95653dbfcbf3937509ceedfe0ff304c602a8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243085"
---
# <a name="translating-the-patterns-of-the-service-oriented-solution"></a>将服务的模式转换面向解决方案
本部分介绍如何在解决方案模式关系图将转换为 BizTalk Server 项目。  
  
 ![服务&#45;面向解决方案模式](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
## <a name="connections-and-completeness-conditions"></a>连接和完整性条件  
 我们几乎可以从任何位置开始将模式转换为 BizTalk Server 组件。 但是，各组件之间的连接是，实际上，组件的基础结构，因此启动的好时机。 此外，对于聚合模式中，我们需要考虑什么将通知它具有所有所需的信息。 这会影响这两个连接到其他组件，以及它的设计。  
  
 该解决方案需要提供一种方便的使用的一致方式。 服务接口指定其他应用程序可以使用它。 由于解决方案需要与使用 IBM WebSphere MQ 的旧版应用程序进行通信，IBM WebSphere MQ 必须是服务接口的一部分。 但是，对于更高版本的应用程序，Web 服务界面看起来显而易见的选择。 Web 服务接口提供了其他应用程序使用该服务的最大的灵活性。 在这里，我们可以使用 BizTalk Server 的灵活性以具有双服务界面。 有关将业务流程作为 Web 服务公开的信息，请参阅[如何映射到 Web 服务的业务流程](../core/how-to-map-orchestrations-to-web-services.md)。  
  
 其他连接包括： 服务界面和收件人列表，收件人列表和后端应用程序之间以及在后端应用程序、 聚合和服务接口之间。  
  
 如果到收件人列表的连接是同步的则不需要使用相关来确保发送和接收到收件人列表的所有消息解决方案。 出于相同原因，可以同步后端应用程序和聚合器之间的连接。 聚合需要来自所有这三个后端应用程序，以完成查询响应的响应。 响应时间应较短，以便同步连接适当并简化此解决方案。  
  
 在聚合器模式下，通常会有一个完整性条件。 在其中有多个后端服务器和响应时间较慢的情况下，完整性条件可能，例如，收到至少一个响应在给定的时间段内。 此面向服务的解决方案需要所有三个响应才能构造最终消息。 因此，在这里，完整性条件接收所有三个响应。  
  
> [!NOTE]
>  该解决方案时接收的请求通过 IBM WebSphere MQ，通过复制来添加相关标识符**MQMD_MsgId**值设置为**MQMD_CorrelId**的响应消息。 这是在请求-答复中使用 MQSeries 适配器以避免可能出现争用情况的标准方法的一部分。 有关详细信息，请参阅[关联的消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。  
  
## <a name="determining-orchestration-boundaries"></a>确定业务流程边界  
 该解决方案必须允许的请求通过 IBM WebSphere MQ 队列以及 Web 服务接口。 将服务接口放入一个业务流程、 IBM WebSphere MQ 输入放置另一个，并处理到第三个大容量保留的外部通信分开处理。  
  
## <a name="translating-the-components-into-orchestration-shapes"></a>将组件转换为业务流程形状  
 若要转换为形状的模式，在最终的解决方案中，将在单个业务流程中。 有很多方法可以在 BizTalk Server，包括创建 MessageBox 订阅中创建基于内容的路由器。 在解决方案中，路由使用 MessageBox 订阅。 表达式形状将评估该消息包含为必填字段的值。 决策形状评估表达式形状中设置的变量，并选择通过业务流程的路径。  
  
 **CustomerService**业务流程使用并行形状将消息发送到后端应用程序，同时接收响应。 它不必等到一个应用程序完成就可以开始下一个请求。 如果应用程序数量要经常发生更改，或连接到应用程序就不可靠，然后业务流程将需要以不同方式转换模式。  
  
 在解决方案中聚合函数必须将三个响应消息中的元素结合起来。 使用并行形状可确保与后端系统的通信是并行。 并且，由于不会终止形状，直到收到所有响应或超时，因此聚合始终知道时则会继续运行。 该业务流程使用转换形状将映射到响应消息中的元素从三个后端响应消息和原始请求消息的元素。  
  
> [!NOTE]
>  与后端系统的通信也可能超时。可以通过包含设置的超时期限**接收**形状中**作用域**形状和设置**超时**作用域的属性。  
  
 业务流程形状的完整列表，请参阅[业务流程形状](../core/orchestration-shapes.md)。  
  
## <a name="see-also"></a>请参阅  
 [面向解决方案在服务中的模式](../core/patterns-in-the-service-oriented-solution.md)   
 [面向服务的解决方案的组件](../core/components-of-the-service-oriented-solution.md)