---
title: Microsoft BizTalk ESB 工具包 |Microsoft 文档
description: 简介、 常见方案和 BizTalk Server 中的 ESB 工具包的组件
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
ms.openlocfilehash: 1763ed4bb7f090b91565c3a5f5f480d2c081b48c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297029"
---
# <a name="microsoft-biztalk-esb-toolkit"></a>Microsoft BizTalk ESB 工具包
![BizTalk ESB 工具包徽标](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")  
  
## <a name="summary"></a>摘要  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]以支持松散耦合的消息传递体系结构。 BizTalk Server 包含一个用于消息传送应用程序的强大发布/订阅机制，该机制通过创建和填充订阅进行运作，从而为面向服务的体系结构 (SOA) 应用程序提供一个高效的可扩展平台。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展 BizTalk Server 提供一系列上构建强大、 连接、 面向服务的应用程序包含为轻型服务基于路线的服务调用的已设定焦点的新功能的功能组合、 动态解析终结点以及图、 Web 服务和 WS-* 集成、 错误管理和报告和与第三方 SOA 管理解决方案的集成。  
  
## <a name="overview"></a>概述  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供体系结构指南、 模式和 BizTalk Server 和.NET Framework 组件，以便简化的开发在 Microsoft 平台上企业服务总线 (ESB) 的并可让 Microsoft 客户扩展的集合他们自己的消息传送和集成解决方案。  
  
## <a name="common-scenarios"></a>常见方案  
 在实现启用面向服务的体系结构 (SOA) 的基础结构的上下文中，Enterprise Service Bus (ESB) 这一术语被广泛使用。 但部署 SOA 的实际经验表明，ESB 仅仅是组成全面面向服务的基础结构 (SOI) 的众多构建块中的一个。 ESB 术语的含义发生了一些不同方向的变化，其定义取决于各个 ESB 和集成平台供应商的解释，以及特定 SOA 计划的要求。  
  
 依据 Microsoft 从众多成功的实际 SOI 实现收集的经验，你可以将 ESB 看作是基于传统企业应用程序集成 (EAI)、面向消息的中间件、Web 服务、.NET 和 Java 互操作性、主机系统集成以及与服务注册表和资产储存库的互操作性的一组体系结构模型。  
  
 图 1 显示的一种 ESB 体系结构可以提供间的相互连接的高级视图。  
  
 ![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **图 1**  
  
 **提供的连接的高级示例的企业服务总线体系结构**  
  
## <a name="audience-requirements"></a>受众要求  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]适用于开发人员创建 Microsoft BizTalk Server 解决方案或使用其他解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件。 若要充分利用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，开发人员应拥有知识和体验替换为以下工作：  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
-   Microsoft .NET 开发技术，包括开发 ASP.NET Web 服务和 .NET Framework 组件  
  
## <a name="design-goals"></a>设计目标  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持和实现松散耦合的消息传递环境，它使更轻松地生成基于消息的企业应用程序的组件进行互操作的一系列组成。 服务和组件自然地划分为以下的七种类别：  
  
-   **Web 服务**： 这些公开内部服务，例如路线处理，异常管理终结点和地图、 BizTalk 服务器操作和消息转换的分辨率。  
  
-   **路线服务**： 其中包括用于执行基于路线的路由的基于业务流程和基于消息的服务[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 你可以创建用于路线基于路由的自定义服务。  
  
-   **路线上的渐变。** 这些接收外部消息、 附加相应路线每条消息，并执行路线处理;它们使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态解析终结点以及元数据适配器提供程序框架。  
  
-   **上渐变**： 这些格式和传输协议，如 HTTP、 JMS、 WMQ、 FTP、 平面文件和 XML 的一系列中接收外部的消息。 它们是典型的 BizTalk Server 接收 （可选） 使用的位置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态解析终结点以及元数据适配器提供程序框架。  
  
-   **关闭渐变**： 这些实现使用的格式和传输如 SOAP、 WCF、 JMS、 WMQ、 FTP、 HTTP、 平面文件、 XML 或任何其他自定义格式的消息的传递的发送端口。 它们是典型的 BizTalk Server 动态发送端口的是直接绑定到消息框和 （可选） 使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态终结点解析适配器提供程序框架和元数据。  
  
-   **异常 Management Framework** ： 这包括异常 Web 服务，异常管理 API，以及丰富，组件处理，并将异常详细信息传递到 ESB 管理门户。  
  
-   **ESB 管理门户**： 这将提供注册表设置、 异常中介，警报通知和分析。  
  
 这些组件和服务的许多依赖于由实现的功能[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，如业务流程、 转换和业务规则引擎和消息框数据库。 图 2 显示类别; 的示意图组件和服务通常发生在每个类别;和使用的核心 BizTalk Server 系统组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 ![ESB 体系结构](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
 **图 2**  
  
 **体系结构和组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB 工具包的工作原理  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]接受入站的消息，并对它们，可能 （但不是总是） 通过执行如转换、 传递或任何其他自定义定义的进程的进程。 为了指定所需的操作，核心处理组件要求消息包含相关说明或元数据，这些说明或元数据定义要使用消息内容应用的进程和执行的任务。  
  
 此方法提供服务; 之间的松散耦合这意味着 ESB 不需要为每个消息事先了解特定的处理。 它只须了解可能的进程范围和如何应用各进程。 用于指定可用进程及进程与消息中说明间映射的选项众多，它们提供了一个配置和调整行为的灵活机制，不需要更改代码和重新部署组件。  
  
## <a name="in-this-section"></a>在本节中

- [安装和配置 Microsoft BizTalk ESB 工具包](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [BizTalk ESB 工具包简介](introduction-to-the-biztalk-esb-toolkit.md)

- [入门和了解 BizTalk ESB 工具包](getting-started-with-the-biztalk-esb-toolkit.md)

- [重要的方案和开发任务](key-scenarios-and-development-tasks.md)

- [创建使用路线设计器的路线](creating-itineraries-using-itinerary-designer.md)

- [BizTalk ESB 工具包示例应用程序](biztalk-esb-toolkit-sample-applications.md)

- [修改和扩展 BizTalk ESB 工具包](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [管理 BizTalk ESB 工具包](administration-with-the-biztalk-esb-toolkit.md)

- [SOA 监管集成](soa-governance-integration.md)

- [故障排除 BizTalk ESB 工具包](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a>相关主题  
  
-   [面向 BizTalk 服务解决方案](../core/service-oriented-solution.md)

- [与 BizTalk Server 中使用 Web 服务](../core/using-web-services.md)  