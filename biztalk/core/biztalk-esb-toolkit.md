---
title: BizTalk ESB 工具包 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08035518-17ad-44d2-ab06-90d725c95ced
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 535fd99ee5c1b9f9c25dd49e2a2441acb855c78a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="biztalk-esb-toolkit"></a>BizTalk ESB 工具包
Microsoft BizTalk ESB 工具包使用 Microsoft BizTalk Server 来支持松散连接的消息传送体系结构。 BizTalk Server 包含一个用于消息传送应用程序的强大发布/订阅机制，该机制通过创建和填充订阅进行运作，从而为面向服务的体系结构 (SOA) 应用程序提供一个高效的可扩展平台。 BizTalk ESB 工具包扩展了 BizTalk Server 的功能，使其可以提供一系列新功能，这些新功能专注于构建强大而互连的面向服务的应用程序，这些应用程序融合了用于轻型服务组合的基于行程的服务调用、终结点和映射的动态解析、Web 服务和 WS-* 集成、故障管理和报告，以及与第三方 SOA 监管解决方案的集成。  
  
## <a name="overview"></a>概述  
 BizTalk ESB 工具包提供了体系结构指南、模式及一组 BizTalk Server 和 .NET Framework 组件，以简化 Microsoft 平台上的 Enterprise Service Bus (ESB) 开发，让 Microsoft 客户可以扩展其自身的消息传送和集成解决方案。  
  
## <a name="common-scenarios"></a>常见方案  
 在实现启用面向服务的体系结构 (SOA) 的基础结构的上下文中，Enterprise Service Bus (ESB) 这一术语被广泛使用。 但部署 SOA 的实际经验表明，ESB 仅仅是组成全面面向服务的基础结构 (SOI) 的众多构建块中的一个。 ESB 术语的含义发生了一些不同方向的变化，其定义取决于各个 ESB 和集成平台供应商的解释，以及特定 SOA 计划的要求。 依据 Microsoft 从众多成功的实际 SOI 实现收集的经验，你可以将 ESB 看作是基于传统企业应用程序集成 (EAI)、面向消息的中间件、Web 服务、.NET 和 Java 互操作性、主机系统集成以及与服务注册表和资产储存库的互操作性的一组体系结构模型。  
  
## <a name="audience-requirements"></a>受众要求  
 BizTalk ESB 工具包面向创建 Microsoft BizTalk Server 解决方案或其他使用 BizTalk ESB 工具包组件的解决方案的开发人员。 为了充分利用 BizTalk ESB 工具包，开发人员应具有以下方面的知识和经验：  
  
1.  Microsoft BizTalk Server  
  
2.  Microsoft Visual Studio  
  
3.  Microsoft .NET 开发技术，包括开发 ASP.NET Web 服务和 .NET Framework 组件  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB 工具包的工作原理  
 BizTalk ESB 工具包可能（但不总是）通过执行进程（如转换、传送或任何其他自定义进程）来接受入站消息并对其进行操作。 为了指定所需的操作，核心处理组件要求消息包含相关说明或元数据，这些说明或元数据定义要使用消息内容应用的进程和执行的任务。   
此方法提供服务; 之间的松散耦合这意味着 ESB 不需要为每个消息事先了解特定的处理。 它只须了解可能的进程范围和如何应用各进程。 用于指定可用进程及进程与消息中说明间映射的选项众多，它们提供了一个配置和调整行为的灵活机制，不需要更改代码和重新部署组件。  
  
## <a name="getting-started"></a>入门  
 安装 BizTalk ESB 工具包，完成后，您应阅读中的"入门"主题 [BizTalk ESB 工具包文档](http://go.microsoft.com/fwlink/?LinkId=193578) 了解体系结构、 消息流，以及 BizTalk ESB 工具包的核心组件。 你还应该安装并运行 BizTalk ESB 工具包附带的示例，这些示例演示了“入门”主题中介绍的常见使用案例，以及一些其他消息传送方案。 此方法将帮助你快速掌握 BizTalk ESB 工具包的工作原理，以及如何在你自己的 SOA 应用程序中利用其功能。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 企业服务指南](http://go.microsoft.com/fwlink/?LinkId=193577)   
 [面向服务的解决方案](../core/service-oriented-solution.md)   
 [使用 Web 服务](../core/using-web-services.md)