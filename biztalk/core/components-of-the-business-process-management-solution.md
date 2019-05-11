---
title: 组件的业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195d40becd4eb35b757379c4d3c51c4feeb4f684
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356699"
---
# <a name="components-of-the-business-process-management-solution"></a>业务流程管理解决方案的组件
本部分介绍业务流程管理解决方案的主要 BizTalk Server 组件。 有关源文件的信息，请参阅[业务流程管理解决方案的文件清单](../core/file-inventory-for-the-business-process-management-solution.md)。  
  
## <a name="orchestrations"></a>业务流程  
 有两个主要业务流程：**OrderBroker**并**OrderManager**。 **OrderBroker**业务流程接受客户请求通过 Web 服务或通过 FTP，批量，并将返回到 Microsoft 消息队列 (MSMQ) 队列的答复。 从请求转**OrderBroker**到**OrderManager**。 两个业务流程与直接绑定通过 MessageBox 数据库。  
  
 **OrderManager**通过使用两个异步处理阶段来运行请求**CableOrder1**并**CableOrder2**业务流程。 集合在一起**CableOrder1**并**CableOrder2**业务流程表示单个业务流程。 但是，该过程已拆分为两个业务流程，以便更改阶段时不必中断订单处理。 有关设计阶段的详细信息，请参阅"划分业务流程"中[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
 **CableOrder1**业务流程将使用**验证**业务流程验证订单并请求代码翻译成操作，调用 Analyze 业务流程，用于分析的顺序，然后调用**激活**，**取消**，或**更改**具体取决于所需的操作的业务流程。 **CableOrder2**业务流程通过调用来处理完成订单**完成**业务流程。 请注意， **CableOrder1**并**CableOrder2**使用**调用**形状调用从属业务流程。  
  
> [!NOTE]
>  **取消**业务流程包含调用的补偿模块**激活**业务流程。 这可确保订单正确还原为对取消请求的补偿的一部分。  
  
 **CableOrder1**并**CableOrder2**业务流程使用直接绑定。 有关这些业务流程直接绑定的详细信息，请参阅[业务流程管理解决方案的实现重点](../core/implementation-highlights-of-the-business-process-management-solution.md)。  
  
 许多业务流程写入，以便它们可以处理使用期间中断**中断**业务流程。 有关中断机制的详细信息，请参阅[进程管理器逻辑](../core/process-manager-logic.md)。  
  
## <a name="back-end-applications"></a>后端应用程序  
 业务流程管理解决方案的所有后端应用程序都使用模拟。 **CableOrder1**， **CableOrder2**，并使用所有的业务流程采用一种特殊**OrderHandler**对象。 **OrderHandler**使用.NET 远程处理与模拟订单管理系统进行通信。 **CableProvisioningSystemClient**并**BTSScnBPMProvisioning** ( **CableProvisioningSystemServer**项目) 程序集模拟的前端和后端订单管理系统，分别。  
  
 该解决方案使用 Windows 窗体应用程序中， **BSTScnBPMFacilities** ( **FacilitiesSimulator**项目)，以模拟处理功能请求的 MSMQ 服务器。  
  
 除了这些组件，业务流程还在 SQL Server 数据库来维护的订单和它们的处理历史记录中生成条目。  
  
## <a name="pipelines"></a>管道  
 该解决方案使用只能通过 BizTalk 管理控制台或绑定文件配置的标准默认管道。 管道执行操作，但是，请广泛使用的每个实例的配置。 通过 FTP 发送的订单的接收端口使用基于实例的配置来配置信封。 有关每个实例配置的详细信息，请参阅[如何部署管道](../core/how-to-deploy-pipelines.md)。  
  
## <a name="custom-adapter"></a>自定义适配器  
 该解决方案使用自定义适配器**OpsAdapter**，以处理中检测到某些错误**OrderManager**并**ErrorHandler**业务流程。 该解决方案为哪些错误报告指定的端口上使用适配器。 适配器获取错误，并将它们发送到操作系统。 有关错误报告的详细信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
## <a name="client-application"></a>客户端应用程序  
 该解决方案包含 ASP.NET Web 页由C#程序中， **CSRMain.aspx**，以模拟客户服务系统。  
  
## <a name="other-assemblies"></a>其他程序集  
 该解决方案使用两个其他程序集**架构**并**实用程序**。 **架构**程序集定义该解决方案使用用于如不同的业务流程之间进行通信的消息**中断**消息。 该解决方案还使用多个.NET 消息中定义**SchemaClasses**程序集。  
  
 **实用程序**程序集包括的实用工具类和方法，以帮助处理消息，可以定义特定的异常类型的解决方案，以从 SSO 密钥存储区中读取配置值，并以帮助进行错误处理。 程序集还包括**Recaller**对象。  
  
 其他程序集包括映射和架构程序集，如下所述 **: OrderBrokerMaps**， **OrderBrokerSchemas**，**映射**， **MessagingSchemas**，并**SchemaClasses**。  
  
 **ServiceLevelTracking**程序集包含与 BAM 一起用于跟踪订单和处理的常见项目。 订单处理操作阶段使用位于**CableOrderActions**程序集。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)   
 [在业务流程管理解决方案中处理](../core/processing-in-the-business-process-management-solution.md)   
 [业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [监视业务流程管理解决方案使用 BAM](../core/monitoring-the-business-process-management-solution-with-bam.md)   
 [版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md)   
 [业务流程管理解决方案参考](../core/business-process-management-solution-reference.md)   
 [开发业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)   
 [业务流程管理解决方案中的文件清单](../core/file-inventory-for-the-business-process-management-solution.md)