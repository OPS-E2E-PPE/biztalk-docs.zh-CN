---
title: BizTalk ESB 工具包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08035518-17ad-44d2-ab06-90d725c95ced
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ba628683b5ae54b407fc30e655a462a87e18957
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358087"
---
# <a name="biztalk-esb-toolkit"></a>BizTalk ESB 工具包
Microsoft BizTalk ESB 工具包使用 Microsoft BizTalk Server 来支持松散耦合的消息传递体系结构。 BizTalk Server 包含的强大发布/订阅消息传送应用程序可通过创建和填充订阅机制，从而为面向服务的体系结构 (SOA) 应用程序提供高度高效、 可缩放的平台。 BizTalk ESB 工具包扩展了 BizTalk Server 能够提供各种新功能，专注于构建强大、 连接、 面向服务的整合为轻型服务基于路线的服务调用的应用程序的功能组合、 动态解析的终结点和地图，Web 服务和 WS-* 集成、 故障管理和报告和与第三方 SOA 监管解决方案的集成。  
  
## <a name="overview"></a>概述  
 BizTalk ESB 工具包提供的体系结构指南、 模式和 BizTalk Server 和.NET Framework 组件以简化开发在 Microsoft 平台上的企业服务总线 (ESB) 并允许 Microsoft 客户可以扩展的集合他们自己的消息传送和集成解决方案。  
  
## <a name="common-scenarios"></a>常见方案  
 企业服务总线 (ESB) 广泛实现启用面向服务的体系结构 (SOA) 的基础结构的上下文中使用的术语。 但是，部署 Soa 的实际经验表明，ESB 是进行了全面面向服务的基础结构 (SOI) 的多个构建基块之一。 术语的 ESB 越来越，具有相似通过多种不同的方向，并且其定义取决于各个 ESB 和集成平台供应商的解释以及特定 SOA 计划的要求。 基于已从许多成功的实际 SOI 实现收集了 Microsoft 的体验，您可以将 ESB 视为一系列体系结构模式基于传统的企业应用程序集成 (EAI)，面向消息的中间件，Web 服务、.NET 和 Java 互操作性、 主机系统集成和与服务注册表和资产储存库的互操作性。  
  
## <a name="audience-requirements"></a>受众要求  
 BizTalk ESB 工具包面向创建 Microsoft BizTalk Server 解决方案或其他解决方案使用 BizTalk ESB 工具包组件的开发人员。 若要充分利用 BizTalk ESB 工具包，开发人员应具备的知识和体验使用以下工作：  
  
1.  Microsoft BizTalk Server  
  
2.  Microsoft Visual Studio  
  
3.  Microsoft.NET 开发技术，包括 ASP.NET Web 服务和.NET Framework 组件的开发  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB 工具包的工作原理  
 BizTalk ESB 工具包接受入站的消息并对其进行操作，可能是 （但不是总是） 通过执行进程，例如转换、 传送或任何其他自定义的进程。 若要指定的操作需要，核心处理组件要求消息包含相关联的说明或定义应用的进程的元数据以及使用消息内容来执行的任务。   
这种方法提供服务; 之间的松散耦合这意味着 ESB 不需要事先了解的特定处理每条消息。 它只须了解可能范围的进程以及如何将应用每个进程。 多种选项用于指定可用进程及进程与消息中的说明进行操作之间的映射提供了用于配置和调整行为，而无需更改代码和重新部署的灵活机制组件。  
  
## <a name="getting-started"></a>入门  
 安装 BizTalk ESB 工具包，完成后，您应阅读中的"入门"主题[BizTalk ESB 工具包文档](http://go.microsoft.com/fwlink/?LinkId=193578)了解体系结构、 消息流和 BizTalk ESB 工具包的核心组件。 您还应安装并运行附带 BizTalk ESB 工具包，其中演示了"入门"主题和其他消息传送方案中所述的常见用例的示例。 此方法将帮助你快速掌握 BizTalk ESB 工具包的工作原理以及您可以在自己的 SOA 应用程序中充分利用其功能。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk 企业服务指南](http://go.microsoft.com/fwlink/?LinkId=193577)   
 [面向服务的解决方案](../core/service-oriented-solution.md)   
 [使用 Web 服务](../core/using-web-services.md)