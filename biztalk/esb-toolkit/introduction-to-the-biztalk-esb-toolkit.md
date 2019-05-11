---
title: BizTalk ESB 工具包简介 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ceb9afa836af951331cbb9f1649ab23f816024
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262047"
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包简介
介绍体系结构和内容的 Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 文档还演示了如何将应用开发企业应用程序，使灵活、 更安全，企业服务总线 (ESB) 体系结构模式和可重用的服务和新端到端的现有服务快速组织业务流程。  

## <a name="what-is-an-enterprise-service-bus"></a>什么是企业服务总线？  
 在实现启用面向服务的体系结构 (SOA) 的基础结构的上下文中广泛使用企业服务总线术语。 但是，与 SOA 解决方案的部署的实际经验已经演示了 ESB 是生成全面面向服务的基础结构 (SOI) 所需的许多组件之一。 术语"ESB"发展的数方向-与各个 ESB 和集成平台供应商的解释以及特定 SOA 计划的要求，其定义而异。  

 根据从许多成功的实际 SOI 实现收集了 Microsoft 的经验，Microsoft 认为企业服务总线体系结构模式基于在传统企业应用程序集成 (EAI) 中，为集合面向消息的中间件、 Web 服务、.NET 和 Java 互操作性、 主机系统集成和与服务注册表和资产储存库的互操作性。 图 1 演示了企业服务总线的体系结构。  

 ![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")  

 **图 1**  

 **提供的企业服务总线体系结构的连接的高级表示**  

<!---  Old text with old links
## The Industry View of ESB  
 There are many sources of information about ESB design, architecture, infrastructure, and implementation available from industry suppliers, system integrators, and independent sources.  
-->
<!---    
 IBM defines ESB as a system that "...enables a business to make use of a comprehensive, flexible, and consistent approach to integration while also reducing the complexity of the applications being integrated. Due to the complex and varying nature of business needs, ESB is an evolutional progression that unifies message oriented, event driven and service oriented approaches for integrating applications and service." IBM describes the advantages as "...greater reuse of IT assets by separating application logics and integration tasks, so you can reduce the number, size, and complexity of integration interfaces," and the ability to "...add or change services with minimal interruption to existing IT environment; reduce cost and risk involved as business changes and new opportunities arise." For more information, see [WebSphere software](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))on the IBM Web site.  
-->
<!---    Old text with old links
 Sonic Solutions provide a comprehensive examination of ESB, discussing the principle aspects, and the IT and business benefits. They describe the requirement for ESB: "To integrate old and new, service-oriented architecture (SOA) needs an infrastructure that can connect any IT resource, whatever its technology or wherever it is deployed." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) on the Sonic Solutions Web site.  
-->
<!---    Old text with old links
 TIBCO Software define ESB as "...a standards-based communication layer in a service- oriented architecture (SOA) that enables services to be used across multiple communication protocols [to] simplify service deployment and management, and promote service reuse in a heterogeneous environment." They suggest, in order to provide these capabilities, ESBs "...support both open standards and proprietary technologies, including Web services and UDDI-based registries to discover and publish services, Java Message Service (JMS) and other widely deployed messaging protocols, standards-based (XML) transformations, and basic message routing." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) on the TIBCO Web site.  
-->
<!---    Old text with old links
 In the description of his book, Enterprise Service Bus, author David Chappell states that "Rather than conform to the hub-and-spoke architecture of traditional enterprise application integration products, ESB provides a highly distributed approach to integration." He adds "...with unique capabilities that allow individual departments or business units to build out their integration projects in incremental, digestible chunks, maintaining their own local control and autonomy, while still being able to connect together each integration project into a larger, more global integration fabric, or grid." For more information, see Enterprise Service Bus by David Chappell:  
-->
<!---    Old text with old links
-   Chappell, David. Enterprise Service Bus. Sebastopol, CA: O'Reilly Media, Inc. 2004.  
-->


## <a name="the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包
 本文档中的，作为一个整体，引入了架构师和开发人员到 ESB 体系结构概念由[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并介绍了通过一系列普遍接受的 ESB 用例的 ESB 组件的功能。  

 本部分提供了简介[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并包括以下主题：  

- [BizTalk ESB 工具包概述](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  

- [BizTalk ESB 工具包内容](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  

  本文档还包括以下主题部分：  

- [BizTalk ESB 工具包入门](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  

- [主要方案和开发任务](../esb-toolkit/key-scenarios-and-development-tasks.md)  

- [使用路线设计器创建路线](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  

- [BizTalk ESB 工具包示例应用程序](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  

- [修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  

- [BizTalk ESB 工具包管理](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  

- [SOA 管理集成](../esb-toolkit/soa-governance-integration.md)  

- [故障排除](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)
