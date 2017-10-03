---
title: "组件的业务流程管理解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, back-end systems, process management solutions
- process management solution tutorial, client applications
- orchestrations, process management solutions
- adapters, process management solutions
- process management solution tutorial, adapters
- client applications, process management solutions
- process management solution tutorial, components
- process management solution tutorial, orchestrations
- pipelines, process management solutions
- process management solution tutorial, pipelines
- assemblies, process management solutions
- process management solution tutorial, assemblies
ms.assetid: e3ccebb9-b677-4c17-acd2-0f986f7bd3f0
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b63234dbf4a8dc62a620bf2b384b832e4887b0d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="components-of-the-business-process-management-solution"></a>业务流程管理解决方案的组件
本部分对业务流程管理解决方案的主要 BizTalk Server 组件进行了说明。 有关源文件的信息，请参阅[业务流程管理解决方案的文件清单](../core/file-inventory-for-the-business-process-management-solution.md)。  
  
## <a name="orchestrations"></a>业务流程  
 有两个主要业务流程： **OrderBroker**和**OrderManager**。 **OrderBroker** orchestration 接受客户请求通过 Web 服务或分批通过 FTP，并发送回通过 Microsoft 消息队列 (MSMQ) 队列的答复。 从请求转**OrderBroker**到**OrderManager**。 这两个业务流程可通过 MessageBox 数据库直接绑定。  
  
 **OrderManager**通过使用两个异步处理阶段运行请求**CableOrder1**和**CableOrder2**业务流程。 综上所述， **CableOrder1**和**CableOrder2**业务流程表示单个业务流程。 但是，该流程已拆分为两个业务流程，以便更改阶段时不必中断订单处理。 有关设计的几个阶段的详细信息，请参阅"除以业务流程"中[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
 **CableOrder1**业务流程使用**验证**验证订单，并将请求代码转换操作，业务流程调用分析业务流程分析顺序，，然后调用**激活**，**取消**，或**更改**具体取决于所需的操作的业务流程。 **CableOrder2**业务流程完成订单处理通过调用**完成**业务流程。 请注意， **CableOrder1**和**CableOrder2**使用**调用**形状来调用从属业务流程。  
  
> [!NOTE]
>  **取消**业务流程包括调用的补偿块**激活**业务流程。 这可以确保订单正确还原为对取消请求的补偿的一部分。  
  
 **CableOrder1**和**CableOrder2**业务流程使用直接绑定。 有关这些业务流程的直接绑定的详细信息，请参阅[实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)。  
  
 许多业务流程，以便它们可以在过程中处理使用中断编写**中断**业务流程。 有关中断机制的详细信息，请参阅[过程管理器逻辑](../core/process-manager-logic.md)。  
  
## <a name="back-end-applications"></a>后端应用程序  
 业务流程管理解决方案可以使用对所有后端应用程序的模拟。 **CableOrder1**， **CableOrder2**，而它们使用所有的业务流程使用特殊**OrderHandler**对象。 **OrderHandler**使用.NET 远程处理与对模拟的订单管理系统进行通信。 **CableProvisioningSystemClient**和**BTSScnBPMProvisioning** ( **CableProvisioningSystemServer**项目) 的程序集模拟的前端和后端分别管理系统，顺序。  
  
 此解决方案使用 Windows 窗体应用程序， **BSTScnBPMFacilities** ( **FacilitiesSimulator**项目)，以模拟处理设施请求 MSMQ 服务器。  
  
 除了这些组件以外，业务流程还在 SQL Server 数据库中生成条目以维护订单及其处理的历史记录。  
  
## <a name="pipelines"></a>管道  
 解决方案只使用通过 BizTalk 管理控制台或绑定文件配置的标准默认管道。 但是，管道可广泛使用基于实例的配置。 由 FTP 发送的订单的接收端口使用基于实例的配置来配置信封。 有关每个实例配置的详细信息，请参阅[如何部署管道](../core/how-to-deploy-pipelines.md)。  
  
## <a name="custom-adapter"></a>自定义适配器  
 该解决方案使用的自定义适配器**OpsAdapter**，以处理在检测到某些错误**OrderManager**和**ErrorHandler**业务流程。 解决方案使用为其指定错误报告的端口上的适配器。 该适配器将获取错误，并将它们发送到操作系统。 有关错误报告的详细信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
## <a name="client-application"></a>客户端应用程序  
 此解决方案包括一个 C# 程序，由支持 ASP.NET 网页**CSRMain.aspx**，以模拟客户服务系统。  
  
## <a name="other-assemblies"></a>其他程序集  
 此解决方案使用两个其他程序集，**架构**和**实用工具**。 **架构**程序集定义的解决方案使用用于如在不同的业务流程之间进行通信的消息**中断**消息。 该解决方案还使用在中定义的多个.NET 邮件**SchemaClasses**程序集。  
  
 **实用工具**程序集包括实用工具类和方法，以帮助处理消息，特定异常类型定义为解决方案，来配置值读取 SSO 密钥存储，并带有错误处理帮助。 程序集还包括**Recaller**对象。  
  
 其他程序集包括映射和架构的程序集，如**OrderBrokerMaps**， **OrderBrokerSchemas**，**地图**， **MessagingSchemas**，和**SchemaClasses**。  
  
 **ServiceLevelTracking**程序集包含与 BAM 用于跟踪订单和处理常见项目。 使用阶段的顺序处理操作处于**CableOrderActions**程序集。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)   
 [在业务流程管理解决方案中进行处理](../core/processing-in-the-business-process-management-solution.md)   
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [监视与 BAM 业务流程管理解决方案](../core/monitoring-the-business-process-management-solution-with-bam.md)   
 [版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md)   
 [业务流程管理解决方案参考](../core/business-process-management-solution-reference.md)   
 [开发一个业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)   
 [业务流程管理解决方案的文件清单](../core/file-inventory-for-the-business-process-management-solution.md)