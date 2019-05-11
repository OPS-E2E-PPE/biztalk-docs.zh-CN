---
title: 使用模式进行设计： 面向服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], examples
- examples, programming patterns
- patterns [service solutions], designing
- designing, programming patterns
ms.assetid: c196cd9d-2b2d-4548-bc7d-26196f7c2878
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0663a9ec82a1e50807f676f7e46211d433086bff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351585"
---
# <a name="designing-with-patterns-the-service-oriented-solution"></a>使用模式进行设计： 面向服务的解决方案
面向服务的解决方案演示如何公开以供使用的服务的 BizTalk 应用程序由其他应用程序。 提供程序作为服务使其他应用程序可以轻松地使用该信息以及它们提供的服务中使用它。 详细了解服务接口都在看到"服务接口" [ http://go.microsoft.com/fwlink/?LinkId=46185 ](http://go.microsoft.com/fwlink/?LinkId=46185)。 有关面向服务的集成的详细信息请参阅"面向服务集成"处[ http://go.microsoft.com/fwlink/?LinkId=46186 ](http://go.microsoft.com/fwlink/?LinkId=46186)。  
  
 解决方法是提供作为 Web 服务响应之后聚合中其他三个应用程序的相关信息, 的信息的信用额度信息应用程序。 应用程序将结果合并，并返回一条消息包含汇总的信用信息。 三个后端系统是按如下所示：  
  
- **SAP 企业系统。** SAP 后端提供了客户的信用总限额。 该解决方案与使用中的 SAP 适配器此后端系统进行通信[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  
  
- **挂起事务系统。** 挂起事务系统报告针对帐户未完成事务的总金额。 该解决方案使用 Microsoft Host Integration Server (HIS) 与大型机从 Windows Server 进行通信。 它还使用他的事务集成器技术。 这些筛选器可与大型机作为 Web 服务进行交互的系统。 BizTalk 业务流程使用此 Web 服务。  
  
- **付款跟踪系统。** 付款跟踪系统报告个人所做的最近付款。 此系统使用 MQSeries。  
  
  您可能还记得解决方案的概述，还可以使用通过 MQSeries 队列的非 Web 服务接口。 (有关应用程序的常规结构的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md))。 尽管 Web 服务的最常见方式构造面向服务体系结构，但并非所有应用程序可以使用它们。 与 BizTalk Server 解决方案可以提供的以及 Web 服务，旧版应用程序使用服务的备用方法。  
  
  MQSeries access 来模拟旧的交互式语音应答系统如何使用该解决方案。 MQSeries 访问，Web 服务访问权限，以及演示如何通过旧版应用程序和新应用程序使用单个解决方案。  
  
## <a name="patterns-used-in-the-service-oriented-solution"></a>面向解决方案在服务中使用的模式  
 下图显示模式的简化的版本的面向服务的解决方案中。  
  
 ![服务&#45;面向解决方案模式](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
 该解决方案包含四个主要部分，其中每个表示一种模式： 服务接口、 基于内容的路由器、 收件人列表和聚合器。 服务接口表示的接口机制，使用它可以连接到解决方案。 基于内容的路由器检查消息的有效性，并发送一条错误消息是否无效。 收件人列表将消息发送到三个后端应用程序。 因为后端应用程序做出响应，聚合器将响应合并到单个响应消息。 响应消息到请求者通过服务接口将返回。  
  
 请注意，还有许多未表达不在关系图中指定：  
  
-   在关系图将忽略消息转换器，以便与外部系统进行通信所需的解决方案。  
  
-   在关系图不会指定如何与后端进程进行通信。  
  
-   在关系图也不会指定服务接口的性质。  
  
-   不会在关系图指示使用同步或异步通信。  
  
## <a name="see-also"></a>请参阅  
 [开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)   
 [将服务的模式转换面向解决方案](../core/translating-the-patterns-of-the-service-oriented-solution.md)