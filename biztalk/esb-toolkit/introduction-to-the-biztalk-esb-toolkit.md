---
title: "BizTalk ESB 工具包简介 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9763e55c44fc3ea45ab93127ffae8c9c742f0dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包简介
说明的体系结构和内容的 Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 文档还演示了如何应用来开发企业应用程序启用灵活、 更安全的企业服务总线 (ESB) 体系结构模式和可重用的服务和快速单位的现有服务分成若干个新的端到端业务流程。  
  
## <a name="what-is-an-enterprise-service-bus"></a>什么是企业服务总线？  
 实现用于启用面向服务的体系结构 (SOA) 的基础结构的上下文中广泛使用企业服务总线的术语。 但是，SOA 解决方案部署的实际经验已经演示了 ESB 是生成全面面向服务基础结构 (SOI) 所需的许多组件之一。 术语"ESB"的发展经历了大量的方向-其定义各不相同，这是与单个 ESB 和集成平台供应商的解释和特定 SOA 方案的要求。  
  
 根据从许多成功的实际 SOI 实现已收集了 Microsoft 的体验，Microsoft 认为企业服务总线体系结构模式基于上传统企业应用程序集成 (EAI) 中的集合面向消息的中间件、 Web 服务、.NET 和 Java 的互操作性、 主机系统集成和与服务注册表和资产存储库互操作性。 图 1 说明企业服务总线体系的结构。  
  
 ![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **图 1**  
  
 **高级表示形式由企业服务总线体系结构提供的连接**  

\<！---与旧的链接的旧文本
## <a name="the-industry-view-of-esb"></a>ESB 该行业视图  
 行业供应商、 系统集成商和独立的源提供了有关 ESB 设计、 体系结构、 基础结构，以及实现的信息来源。  
-->
\<!---    
 IBM 作为系统定义 ESB，"...enables 企业能够对同时减少正在集成的应用程序的复杂性的集成进行全面、 灵活、 使用和一致的方法。 由于复杂和不同的特性的业务需求，ESB 统一面向消息的 evolutional 进展，事件驱动的和服务面向集成应用程序和服务的方法。" IBM 描述与好处"..分隔应用程序是逻辑和集成任务，因此数量、 大小和复杂性的集成接口，可以减少 IT 资产.greater 重用"以及的能力"...add 或更改的服务，只需极少现有 IT 环境中; 中断降低成本和风险涉及随着业务的变化和新的机会出现"。 有关详细信息，请参阅[WebSphere 软件](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958)) IBM Web 站点上。  
-->
\<！---与旧链接 Sonic 解决方案提供 ESB，全面检查讨论的原则方面和 IT 的旧文本和业务好处。 这些主题描述了 ESB 的要求:"若要将旧和新的集成，面向服务的体系结构 (SOA) 需要一种可以连接任何 IT 资源，任何基础结构其技术或部署任何位置。" 有关详细信息，请参阅[企业服务总线 (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) Sonic 解决方案 Web 站点上。  
-->
\<！---与旧链接 TIBCO 软件旧文本定义为 ESB"...a 基于标准的通信层中的面向服务的体系结构 (SOA)，使服务可用于跨多个通信协议 [] 简化服务部署和管理，并将升级服务异类环境中的重复使用。" 这些建议，以便提供这些功能，ESBs"...support 均是开放式标准和专有技术，包括 Web 服务和基于 UDDI 注册表，才能发现和发布服务，Java 消息服务 (JMS) 和其他广泛部署消息传递协议、 基于标准的 (XML) 转换和基本的邮件路由。" 有关详细信息，请参阅[企业服务总线 (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) TIBCO Web 站点上。  
-->
\<！---与书籍，企业服务总线的说明中的旧链接的旧文本作者 David Chappell 指出"而不是符合中心辐射体系结构的传统的企业应用程序集成产品，ESB 提供高度分布式的方法集成。" 他将添加"...使用唯一功能，以允许各个部门或业务单位来生成 out 增量备份，可以理解的区块，但仍然可以将连接在一起维护其自己的本地控制和自主性，其集成项目每个集成项目到更大、 更具有全局性集成构造或网格。" 有关详细信息，请参阅 David Chappell 企业服务总线：  
-->
\<！---与旧的链接的旧文本
-   Chappell，David。 企业服务总线。 Sebastopol，CA: O'Reilly 媒体，inc.2004.  
-->

  
## <a name="the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包
 本文档中的，作为一个整体，引入了架构师和开发人员 ESB 体系结构概念作为通过寻址[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并解释了一套广为接受 ESB 用例通过 ESB 组件的功能。  
  
 本部分提供的简介[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并包括以下主题：  
  
-   [BizTalk ESB 工具包的概述](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [BizTalk ESB 工具包的内容](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 本文档还包括以下主题各节：  
  
-   [Getting Started with BizTalk ESB 工具包](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [重要的方案和开发任务](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [创建使用路线设计器的路线](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [BizTalk ESB 工具包示例应用程序](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [管理 BizTalk ESB 工具包](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [SOA 监管集成](../esb-toolkit/soa-governance-integration.md)  
  
-   [故障排除](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)