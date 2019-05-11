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
ms.openlocfilehash: 6f866df79f46f941604bc72a189a080f56aea170
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292672"
---
# <a name="understanding-the-business-process-management-solution"></a>了解业务流程管理解决方案
在本部分中所述的解决方案提供了一种可实现业务流程管理应用程序。 在理想的业务流程管理器，代表业务流程解决方案的部分中，与特定后端系统，发送响应消息进行通信的业务规则 — 分开支持过程的基础结构。  
  
 此解决方案中的有线服务订购系统 Southridge video 的业务流程将划分成一系列阶段。 相关信息一无所知的业务规则和后端系统，订单管理器指示阶段的操作。 订单管理器接收来自 orderbroker，后者可以将多个不同的 ordermanager 的订单的订单。  
  
 该解决方案可广泛使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能，并演示如何在等来协调应用程序的各个部分的消息应用程序内部使用。  
  
## <a name="reader-guidance"></a>读者指南  
 本文档假定你熟悉[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 它还假定您了解有关企业应用程序集成和 Web 服务的基本概念。  
  
 此外，若要阅读并遵循开发人员文档，应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并熟悉如何执行以下任务： 创建项目、 设置引用以及调试和测试 BizTalk解决方案。  
  
## <a name="ordering-cable-service-from-southridge-video"></a>从 Southridge Video 订购有线服务  
 业务流程管理解决方案实现 Southridge Video 订购系统的有线服务。 为呼叫中心的客户服务代表客户电话会将订单并将它输入到订单系统。 下图显示了订单在系统的常规流程：  
  
 ![业务流程管理解决方案工作流](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")  
  
 订单都进入顺序 broker，它将发送到订单管理器的顺序。 订单管理器运行以正确的顺序来处理订单处理阶段。 请注意某些种类的错误可转到运营中心进行更正和重新提交，并且解决方案中的 SQL Server 表中记录的每个订单的历史记录。  
  
 下图显示了处理订单的广泛概括了这些步骤。  
  
 ![业务流程管理解决方案序列](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")  
  
 请注意，订单可以进行更新，以及已取消。  
  
## <a name="business-requirements"></a>业务要求  
 业务流程管理解决方案是 Southridge Video，有线电视服务提供商的订单系统的示例。 它显示在 Microsoft BizTalk Server 中实现流程管理器模式的一种方法。 该解决方案使用业务流程管理中的订单通过实现业务流程的两个附属业务流程。 此结构不再是解决方案的业务要求，其中包括以下各项：  
  
- 版本的业务流程的能力  
  
- 进程长时间运行的订单  
  
- 修改或取消仍在处理的订单 （补充正在处理的订单）  
  
- 避免挂起的订单  
  
- 跟踪订单的整个过程  
  
- 成批处理订单  
  
- 接受来自远程数据中心的订单  
  
- 允许不同的组来处理部分的订单处理  
  
- 通过添加 BizTalk 组中缩放应用程序  
  
- 公开，通过远程处理，作为应用程序服务器的订单管理器  
  
  Southridge Video 的业务要求生成三部分组成的结构： orderbroker、 流程管理器和业务流程自身。 了 Southridge Video 的两个不同的 IT 小组所涉及的应用程序中。 消息组维护公司的消息传送基础结构，并连接到该基础结构的应用程序提供的组件。 另一个小组负责编写和维护用于特定业务流程的应用程序。 因此，orderbroker 就独立于订单流程管理器和处理阶段，以便它可以通过单独的组进行维护。 因为它是一个单独的组件，还可以扩展 orderbroker 代理向多个进程管理器的订单。 可能会添加流程管理器，以支持新业务，例如 VIP 服务。  
  
  Southridge Video 订单是长时间运行的进程： 有线订单可能需要一分钟一年时间才能完成。 因为 BizTalk 业务流程的实例必须运行完毕，这意味着业务流程实例可能有长达一年的生存期。  
  
  Southridge Video 需长时间运行的进程，允许在订单处理过程中更改应用程序组件的结构。 因此，Southridge 可以将订单处理划分为多个阶段，以便使用最新的流程组件来完成订单。 有关如何确定业务流程中的各阶段界限的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
  较长的处理时间为订单，此外，部分，确定需要更改正在处理的订单。 修改订单是该解决方案包含大量系统的中断的原因之一。 这一中断系统简化了使顺序更改或取消操作完成前。 该解决方案使用.NET 消息来处理中断的解决方案的各个功能部分之间进行通信。  
  
  由于系统有许多外部依存关系，因此可以发生故障后重试某些操作。 例如，如果后端系统，并且向其请求超时时，解决方案将等待适当的时间间隔，然后重试请求。 由于与外部系统的连接是通过自定义代码，此部分的解决方案，可广泛使用.NET 反射技术，以便对象方法将重试。  
  
  该解决方案，基于真实公司一样假定订单处理问题可以由运营组中的人。 同样，某些种类的订单错误将返回引用与客户服务代表他们可能会取消或更正并重新提交订单。  
  
## <a name="business-process-management-solution-resources"></a>业务流程管理解决方案资源  
 请阅读以下文档有关业务流程管理解决方案的其他信息。  
  
### <a name="business-process-management-solution-resources"></a>业务流程管理解决方案资源  
  
-   [开发业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)  
  
     开发人员和软件架构师可以使用本指南记录所有代码、 模式、 体系结构，以及性能设计问题所需生成并运行业务流程管理应用程序。  
  
-   [部署业务流程管理解决方案](../core/deploying-the-business-process-management-solution.md)  
  
     IT 专业人士的 BizTalk Server 有一个大致了解可以使用本指南生成并运行业务流程管理应用程序。 本指南假定大致了解应用程序在分布式环境中工作原理。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案](../core/business-process-management-solution.md)