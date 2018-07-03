---
title: 了解业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solutions, resources
- process management solutions, applications
- process management solution tutorial, background information
- process management solutions, about process management solutions
- applications, process management solutions
ms.assetid: fa6ad8d2-08d7-4770-9394-835f99bfd146
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4742ad9625c91c9a8f92f8359c4e0becbb166eab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004902"
---
# <a name="understanding-the-business-process-management-solution"></a>了解业务流程管理解决方案
使用本部分中介绍的解决方案可以实现业务流程管理应用程序。 在理想的业务流程管理器，代表业务流程解决方案的部分中，与特定后端系统，发送响应消息进行通信的业务规则 — 分开支持过程的基础结构。  
  
 在此解决方案（Southridge Video 的有线服务订购系统）中，业务流程分为一系列阶段。 各个阶段的操作由一个对业务规则和后端系统的相关信息一无所知的 OrderManager 进行管理。 OrderManager 接收来自 OrderBroker 的订单，后者可以将订单传至若干不同的 OrderManager。  
  
 该解决方案广泛地应用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的功能，并且显示了如何使用应用程序内部消息来协调应用程序的各个部分。此外，还展示了一些其他功能。  
  
## <a name="reader-guidance"></a>读者指南  
 本文档假定您熟悉 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 它还假定您了解有关企业应用程序集成和 Web 服务的基本概念。  
  
 此外，若要阅读并遵循开发人员文档，应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并熟悉如何执行以下任务： 创建项目、 设置引用以及调试和测试 BizTalk解决方案。  
  
## <a name="ordering-cable-service-from-southridge-video"></a>从 Southridge Video 订购有线服务  
 该业务流程管理解决方案实现 Southridge Video 的有线服务订购系统。 联系中心的客户服务代表在接到客户向联系中心拨打的电话后，会将订单信息输入到订单系统中。 下面的关系图显示了订单在该系统中的常规流程：  
  
 ![业务流程管理解决方案工作流](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")  
  
 订单将传至 OrderBroker，并由后者发送至 OrderManager。 OrderManager 会以正确的顺序运行各处理阶段来处理订单。 请注意，某些种类的错误会传至运营中心进行更正和重新提交，并且解决方案会在一个 SQL Server 表中记录每个订单的历史记录。  
  
 下面的关系图概略显示了处理订单时的步骤：  
  
 ![业务流程管理解决方案序列](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")  
  
 请注意，订单可以更新，也可以取消。  
  
## <a name="business-requirements"></a>业务需求  
 此业务流程管理解决方案是 Southridge Video（一家有线服务提供商）的一个订单系统示例。 它显示了一种在 Microsoft BizTalk Server 中实现流程管理器模式的方法。 该解决方案使用一个业务流程来管理两个用于实现业务程序的附属业务流程中的订单流程。 此结构基于解决方案的业务需求而构建，这些需求包括：  
  
- 能够对业务流程进行版本控制  
  
- 处理长时间运行的订单  
  
- 修改或取消仍在处理的订单（补充正在处理的订单）  
  
- 避免挂起订单  
  
- 跟踪订单的整个处理过程  
  
- 成批处理订单  
  
- 接受来自远程数据中心的订单  
  
- 允许不同的组处理订单处理的各部分过程  
  
- 通过添加 BizTalk 组来扩展应用程序  
  
- 远程将 OrderManager 作为应用程序服务器公开  
  
  Southridge Video 的业务要求生成三部分组成的结构： orderbroker、 流程管理器和业务流程自身。 该应用程序涉及了 Southridge Video 的两个不同的 IT 小组。 一个是消息传送小组，负责维护公司的消息传送基础结构，并提供用于将应用程序连接到该基础结构的组件。 另一个小组负责编写和维护用于特定业务流程的应用程序。 这样，OrderBroker 就独立于订单流程管理器和处理阶段，因而可以由一个单独的小组进行维护。 由于 OrderBroker 是一个单独的组件，因此还可以进行扩展，作为多个流程管理器的 OrderBroker。 可以添加流程管理器以支持新业务，例如 VIP 服务。  
  
  Southridge Video 订单是长时间运行的进程： 有线订单可能需要一分钟一年时间才能完成。 因为 BizTalk 业务流程实例必须运行到完成为止，所以这意味着业务流程实例的生存期可能长达一年。  
  
  Southridge Video 所需的结构应支持长时间运行的流程，并允许在订单处理期间更改应用程序组件。 这样，Southridge 可以将订单处理分为多个阶段，以便使用最新的流程组件来完成订单。 有关如何确定业务流程中的各阶段界限的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
  订单处理需要很长时间也在一定程度上决定了更改正在处理的订单的需要。 修改订单正是该解决方案包含一系列中断的原因之一。 这一中断系统简化了在订单完成之前进行的订购更改或取消操作。 为处理中断，解决方案使用 .NET 消息在该解决方案的各个功能部分之间进行通信。  
  
  由于系统有许多外部依存关系，因此某些操作可以在失败后重试。 例如，如果某个后端系统不可用，而对该后端系统的某个请求超时，该解决方案将等待适当的时间间隔，然后重试该请求。 由于与外部系统之间的连接是通过自定义代码建立的，因此该部分的解决方案广泛地使用了 .NET 反射技术，以便重试对象方法。  
  
  就像该解决方案所基于的真实公司一样，该解决方案假定订单处理问题可以由运营组中的人员来处理。 同样，某些种类的订单错误将返回给客户服务代表进行处理。客户服务代表可以取消订单，也可以在更正后重新提交订单。  
  
## <a name="business-process-management-solution-resources"></a>业务流程管理解决方案资源  
 请阅读以下文档，以了解有关业务流程管理解决方案的其他信息。  
  
### <a name="business-process-management-solution-resources"></a>业务流程管理解决方案资源  
  
-   [开发业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)  
  
     开发人员和软件设计师可以使用此指南记录生成和运行业务流程管理应用程序所需的全部代码、模式、结构和性能设计问题。  
  
-   [部署业务流程管理解决方案](../core/deploying-the-business-process-management-solution.md)  
  
     掌握 BizTalk Server 常规知识的 IT 专业人士可以使用此指南生成和运行业务流程管理应用程序。 该指南假定读者掌握有关应用程序在分布式环境中的工作原理的常规知识。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案](../core/business-process-management-solution.md)