---
title: "设计用于模式： 面向服务的解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], examples
- examples, programming patterns
- patterns [service solutions], designing
- designing, programming patterns
ms.assetid: c196cd9d-2b2d-4548-bc7d-26196f7c2878
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcfa7f7e4f492de139ae3f5a10f6cb39abaa73be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="designing-with-patterns-the-service-oriented-solution"></a>设计用于模式： 面向服务的解决方案
面向服务的解决方案演示如何公开 BizTalk 应用程序作为服务以使用其他应用程序。 提供一个应用程序作为服务使其他应用程序可以轻松地使用该信息并在它们提供的服务中使用它。 有关服务的详细信息接口都在看到"服务接口" [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185)。 有关面向服务的集成的详细信息请参阅"面向服务集成"网址[http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)。  
  
 解决方案是信用信息提供的应用程序作为 Web 服务响应之后聚合中三个其他应用程序的相关信息, 的信息。 应用程序将合并结果，并返回单个消息包含信用额度汇总的信息。 三个后端系统如下所示：  
  
-   **SAP 企业系统。** SAP 后端提供了客户的信用总限额。 该解决方案使用 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 中的 SAP 适配器与此后端系统进行通信。  
  
-   **挂起事务系统。** 挂起事务系统根据帐户来报告未完成事务的总数。 该解决方案使用 Microsoft 主机集成服务器 (HIS) 与从 Windows Server 主机进行通信。 它还使用他的事务系统集成商技术。 这些筛选器可与作为 Web 服务主机进行交互的系统。 BizTalk 业务流程使用此 Web 服务。  
  
-   **支付跟踪系统。** 付款跟踪系统报告个人所做的最近付款。 此系统使用 MQSeries。  
  
 您可能还记得从解决方案的概述，你还可以使用通过 MQSeries 队列的非 Web 服务接口。 (有关应用程序的一般结构的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md))。 虽然 Web 服务的最常见的方法来构建面向服务的体系结构，但并非所有应用程序可以使用它们。 与 BizTalk Server 解决方案可以提供，以及 Web 服务，为旧版应用程序以使用服务的备用方法。  
  
 MQSeries 访问模拟传统的交互式语音响应系统如何使用该解决方案。 MQSeries 访问，以及 Web 服务访问权限，演示如何通过旧的应用程序和新的应用程序都使用单个解决方案。  
  
## <a name="patterns-used-in-the-service-oriented-solution"></a>服务中使用的模式面向解决方案  
 下图显示在面向服务的解决方案中的模式的简化的版本。  
  
 ![服务 &#45; 面向的解决方案模式](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
 此解决方案由四个主要部分，其中每个表示模式组成： 服务接口、 基于内容的路由器、 收件人列表中，和聚合器。 服务接口表示使得来连接到解决方案的接口机制。 基于内容的路由器检查消息的有效性，并将发送一条错误消息，如果该值无效。 收件人列表将消息发送到三个后端应用程序。 如后端应用程序做出响应，聚合器会将响应合并到单个响应消息。 该响应消息将通过服务接口返回到请求方。  
  
 请注意，许多处于未指定关系图中：  
  
-   关系图省略消息转换器，以便与外部系统进行通信所需的解决方案。  
  
-   关系图不指定如何与后端进程通信。  
  
-   关系图也未指定服务接口的性质。  
  
-   也不关系图表示使用同步或异步通信。  
  
## <a name="see-also"></a>另请参阅  
 [面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md)   
 [转换的服务的模式面向解决方案](../core/translating-the-patterns-of-the-service-oriented-solution.md)