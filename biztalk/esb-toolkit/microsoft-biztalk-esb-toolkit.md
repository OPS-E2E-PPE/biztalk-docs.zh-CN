---
title: Microsoft BizTalk ESB 工具包 |Microsoft Docs
description: 简介、 常见的方案，以及 BizTalk Server 中的 ESB 工具包组件
caps.latest.revision: 14
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ffaebc-7e33-4de8-8e94-109cd5d16ca0
ms.author: mandia
ms.openlocfilehash: f425c02e8f869952658f93185c78474e58df304b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023395"
---
# <a name="microsoft-biztalk-esb-toolkit"></a>Microsoft BizTalk ESB 工具包
![BizTalk ESB 工具包徽标](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")  
  
## <a name="summary"></a>“摘要”  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]来支持松散耦合的消息传递体系结构。 BizTalk Server 包含一个用于消息传送应用程序的强大发布/订阅机制，该机制通过创建和填充订阅进行运作，从而为面向服务的体系结构 (SOA) 应用程序提供一个高效的可扩展平台。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展了 BizTalk Server 能够提供各种新功能，专注于构建强大、 连接、 面向服务的整合为轻型服务基于路线的服务调用的应用程序的功能组合、 动态解析的终结点和地图，Web 服务和 WS-* 集成、 故障管理和报告和与第三方 SOA 监管解决方案的集成。  
  
## <a name="overview"></a>概述  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供的体系结构指南、 模式和 BizTalk Server 和.NET Framework 组件以简化开发在 Microsoft 平台上的企业服务总线 (ESB) 并允许 Microsoft 客户可以扩展的集合他们自己的消息传送和集成解决方案。  
  
## <a name="common-scenarios"></a>常见方案  
 在实现启用面向服务的体系结构 (SOA) 的基础结构的上下文中，Enterprise Service Bus (ESB) 这一术语被广泛使用。 但部署 SOA 的实际经验表明，ESB 仅仅是组成全面面向服务的基础结构 (SOI) 的众多构建块中的一个。 ESB 术语的含义发生了一些不同方向的变化，其定义取决于各个 ESB 和集成平台供应商的解释，以及特定 SOA 计划的要求。  
  
 依据 Microsoft 从众多成功的实际 SOI 实现收集的经验，你可以将 ESB 看作是基于传统企业应用程序集成 (EAI)、面向消息的中间件、Web 服务、.NET 和 Java 互操作性、主机系统集成以及与服务注册表和资产储存库的互操作性的一组体系结构模型。  
  
 图 1 显示了 ESB 体系结构可以提供间的相互连接的类型的高级视图。  
  
 ![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **图 1**  
  
 **提供的企业服务总线体系结构的连接的高级示例**  
  
## <a name="audience-requirements"></a>受众要求  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]适用于开发人员创建 Microsoft BizTalk Server 解决方案或使用其他解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件。 若要充分利用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，开发人员应具备的知识和体验以下工作：  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
- Microsoft .NET 开发技术，包括开发 ASP.NET Web 服务和 .NET Framework 组件  
  
## <a name="design-goals"></a>设计目标  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]系列进行互操作支持和实现松散耦合的消息传送环境可简化构建基于消息的企业应用程序组件组成。 服务和组件很自然地划分为以下七个类别：  
  
- **Web 服务**： 这些公开内部服务，例如路线处理，异常管理终结点和映射，BizTalk Server 操作和消息转换的解决方法。  
  
- **路线服务**： 其中包括用于执行基于路线的路由的基于业务流程和基于消息传送服务[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 可以创建自定义基于路线的路由的服务。  
  
- **路线接入。** 这些接收外部消息、 附加为每个消息，适当的旅行计划和执行路线处理;它们使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。  
  
- **接入**： 这些接收外部消息格式和传输，如 HTTP、 JMS、 WMQ、 FTP、 平面文件和 XML 的范围内。 它们是典型的 BizTalk Server 接收位置 （可选） 使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作的管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。  
  
- **接出点**： 这些实现使用的格式和传输如 SOAP、 WCF、 JMS、 WMQ、 FTP、 HTTP、 平面文件、 XML 或任何其他自定义格式的消息的发送的发送端口。 它们是典型的 BizTalk Server 动态发送端口，是直接绑定到 Messagebox 和 （可选） 使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作的管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。  
  
- **异常管理框架**： 这包括异常 Web 服务、 异常管理 API，以及丰富，组件处理，并将异常详细信息传递到 ESB 管理门户。  
  
- **ESB 管理门户**： 这提供了注册表设置、 异常中介、 警报通知和分析。  
  
  许多这些组件和服务的依赖功能由实现[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，如业务流程、 转换和业务规则引擎和 Messagebox 数据库。 图 2 显示了类别; 的示意图组件和服务通常发生在每个类别;使用的核心 BizTalk Server 系统组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
  ![ESB 体系结构](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
  **图 2**  
  
  **体系结构和组件 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB 工具包的工作原理  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]接受入站的消息并对其进行操作，可能是 （但不是总是） 通过执行进程，例如转换、 传送或任何其他自定义的进程。 为了指定所需的操作，核心处理组件要求消息包含相关说明或元数据，这些说明或元数据定义要使用消息内容应用的进程和执行的任务。  
  
 这种方法提供服务; 之间的松散耦合这意味着 ESB 不需要事先了解的特定处理每条消息。 它只须了解可能的进程范围和如何应用各进程。 用于指定可用进程及进程与消息中说明间映射的选项众多，它们提供了一个配置和调整行为的灵活机制，不需要更改代码和重新部署组件。  
  
## <a name="in-this-section"></a>本节内容

- [安装和配置 Microsoft BizTalk ESB 工具包](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [BizTalk ESB 工具包简介](introduction-to-the-biztalk-esb-toolkit.md)

- [入门和了解 BizTalk ESB 工具包](getting-started-with-the-biztalk-esb-toolkit.md)

- [关键方案和开发任务](key-scenarios-and-development-tasks.md)

- [创建使用路线设计器的路线](creating-itineraries-using-itinerary-designer.md)

- [BizTalk ESB 工具包示例应用程序](biztalk-esb-toolkit-sample-applications.md)

- [修改和扩展 BizTalk ESB 工具包](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [BizTalk ESB 工具包管理](administration-with-the-biztalk-esb-toolkit.md)

- [SOA 管理集成](soa-governance-integration.md)

- [BizTalk ESB 工具包疑难解答](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a>相关主题  
  
-   [面向解决方案的 BizTalk 服务](../core/service-oriented-solution.md)

- [与 BizTalk Server 使用 Web 服务](../core/using-web-services.md)  