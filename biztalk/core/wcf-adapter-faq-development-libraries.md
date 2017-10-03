---
title: "WCF 适配器常见问题： 开发库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d05b635a-d46d-4f7d-896b-8ed7a799e80f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee15769d5b6fb41edece8e30702f14acf1992a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faq-development-libraries"></a>WCF 适配器常见问题解答：开发库
## <a name="when-does-it-make-more-sense-to-use-the-wcf-adapters-vs-a-wcf-custom-binding-to-communicate-with-an-external-application-or-system"></a>使用 WCF 适配器和 WCF 自定义绑定与外部应用程序或系统进行通信何时更有意义？  
 [!INCLUDE[prague](../includes/prague-md.md)] WCF 适配器提供了两种新方法以使用 WCF 将外部系统与 BizTalk Server 相集成：  
  
-   你可以编写 WCF 客户端/服务代码，并使用标准 [!INCLUDE[prague](../includes/prague-md.md)] WCF 适配器处理通信。  
  
-   或者，你可以使用 .NET WCF 框架开发新的自定义 WCF 绑定，并使用其代替 WCF 适配器来处理通信。  
  
 使用 BizTalk Server 的 WCF 适配器，你可以开发 WCF 客户端代码并作为远程 WCF 服务调用 BizTalk Server，或者你可以编写 WCF 服务并配置 BizTalk Server 以将其作为 WCF 服务公开。 另一种方法是，你可以实际编写全新的自定义 WCF 绑定来处理通信。  
  
 与编写 WCF 自定义绑定元素相比，编写标准 WCF 客户端或服务代码以及使用标准 [!INCLUDE[prague](../includes/prague-md.md)] 适配器的优势在于自定义绑定更难开发。 生成的 WCF 客户端或服务存在于 BizTalk Server 管理（监视、配置和部署）范围之外。 编写你自己的新自定义绑定并使用 BizTalk WCF 自定义适配器承载绑定的优势在于可将其紧密集成到这些 BizTalk Server 管理功能中。 在基础结构支持方面，开发绑定的相关成本显著高于开发服务的相关成本。  
  
 了解这一点十分重要：两种方法均可使你以事务性方式与内部 BizTalk MessageBox 数据库集成，并可提供相似性能。 它更像是决定，你希望解决方案达到何种复杂程度。  
  
 使用 WCF 时，应首先尝试编写自定义服务和客户端并使用标准 BizTalk WCF 适配器连接两者。 .NET 框架和 WCF 库专用于轻松执行此任务。 要创建 WCF 服务，只需开发自定义界面，设置适当的属性，然后实现约定后的代码。 WCF 负责从元数据到对象序列化的所有任务。 编写 WCF 服务后，你可以使用几个简单步骤通过发送端口配置 WCF 适配器以便与服务进行对话。 甚至可以配置事务，以便新服务可以通过内部 BizTalk MessageBox 数据库参与消息的事务性交换。  
  
 在接收方，你可以配置 BizTalk Server，以便接收位置像网络中的 WCF 服务一样。 从而允许你编写常规 WCF 客户端代码，甚至还能在调用该服务时使用事务。 将标准 BizTalk WCF 适配器用作直接从 WCF 客户端到 WCF 服务代码的可配置桥的优势在于开发十分简单。 WCF 适配器以简单的方式在 WCF 服务环境的 BizTalk Server 中提供了高性能的事务性桥。  
  
 总之，要与外部系统通信，你可以编写 WCF 服务以与外部系统进行交互，然后编写代码以直接与 WCF 服务对话，作为针对你的问题的更简单解决方案。 如果使用更复杂的方法，你可以编写新的自定义绑定并使用任一 WCF 自定义适配器以更紧密的方式（与使用 WCF 服务相比）与 [!INCLUDE[prague](../includes/prague-md.md)] 集成。 编写新的自定义绑定是较低级别的复杂开发练习。 此方法的好处是可实现紧密集成的解决方案，整个解决方案可统一使用 BizTalk Server 管理、配置和开发案例。 如果适配器的功能开发为外部 WCF 客户端和服务，则配置必须在 BizTalk Server 环境外面，因此缺少相关基础结构支持。  
  
## <a name="what-are-the-differences-between-the-wcf-adapters-and-the-adapters-in-the-biztalk-adapter-pack"></a>WCF 适配器和 BizTalk Adapter Pack 中的适配器之间有哪些区别？  
 WCF 适配器是 [!INCLUDE[prague](../includes/prague-md.md)] 发行版标准随附的七个适配器：  
  
-   WCF-Custom  
  
-   WCF-CustomIsolated  
  
-   WCF-NetTcp  
  
-   WCF-BasicHttp  
  
-   WCF-WsHttp  
  
-   WCF-NetNamedPipe  
  
-   WCF-NetMsmq  
  
 [BizTalk 适配器包](http://www.microsoft.com/biztalk/en/us/adapter-pack.aspx)是提供单一的解决方案，可轻松、 更安全地连接到的业务线 (LOB) 数据从任何自定义方式开发.NET 应用程序、 基于 SQL Server 的业务的 post BizTalk Server 发行版智能解决方案或 Office 业务应用程序 (OBA)。 此发行版中提供了三个适配器，分别为 Siebel、SAP 和 Oracle DB。 [!INCLUDE[prague](../includes/prague-md.md)] Developer、Standard 和 Enterprise 版本均包含 Adapter Pack 许可，但 Branch 版本尚未包含。 已购买具有软件保障的 [!INCLUDE[prague](../includes/prague-md.md)] 的客户还将有权通过该程序访问 BizTalk Adapter Pack。  
  
## <a name="what-is-the-recommended-order-for-deciding-to-use-the-biztalk-server-adapter-framework-the-wcf-lob-adapter-sdk-or-the-net-framework"></a>决定使用 BizTalk Server 适配器框架、WCF LOB 适配器 SDK 或 .NET Framework 时的建议顺序是什么？  
 最不建议使用 BizTalk 适配器框架，因为它不基于标准 .NET WCF。 由于从战略角度来看，解决方案应尽可能包含 WCF，包含 WCF 的最佳方式有哪些？ 最简单的方法是编写 WCF 客户端和服务，然后使用 WCF 适配器将其联系在一起。 如果程序位于 BizTalk Server 外部，则你可以使用 .NET Framework 编写 WCF 自定义绑定。  
  
 仅在以下情况下选择 WCF LOB 适配器 SDK 方案：你正在尝试解决严重的以元数据为中心的 LOB 集成问题。 WCF LOB 适配器 SDK 是另一种创建 WCF 绑定的方法，且专用于元数据支持。 例如，当你正在通信的系统没有固定的文档类型时，需要此元数据。 BizTalk Server 发送或接收 XML 文档，元数据描述文档中数据的布局以便目标系统能使用。  
  
## <a name="what-are-the-differences-between-the-biztalk-adapter-framework-and-the-wcf-lob-adapter-sdk"></a>BizTalk 适配器框架和 WCF LOB 适配器 SDK 之间有什么区别？  
 如果七个标准 WCF 适配器均不满足通信要求，BizTalk 适配器框架将用于生成自定义 WCF 适配器。 适配器框架为元数据提供了大量支持以支持 LOB 应用程序，并共享标准 WCF 适配器使用的标准化配置和管理方法。  
  
 WCF LOB 适配器 SDK 使你可以为具有大量元数据要求的目标系统编写自定义绑定。 WCF LOB 适配器 SDK 的目的是实现统一开发可重用的面向元数据且基于 WCF 的适配器，该适配器支持企业应用程序和数据库彼此集成。 因为使用 WCF LOB 适配器 SDK 生成 WCF 绑定，所以可在多个 .NET 应用程序（包括自定义 .NET 应用程序、[!INCLUDE[prague](../includes/prague-md.md)]、Microsoft Office SharePoint® Server 和 Microsoft SQL Server Integration Services）中重复使用已开发的相同解决方案。 此外，WCF LOB 适配器 SDK 提供了通用元数据对象模型以公开目标系统元数据，供适配器使用者从适配器浏览、搜索和检索 WCF 约定。 你可以下载 SDK 从[http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184)。  
  
 尽管 BizTalk 适配器框架和 WCF LOB 适配器 SDK 在帮助促进自定义适配器的开发方面有相似之处，但也有一些值得注意的不同之处：  
  
-   WCF LOB 适配器 SDK 是较新的发行版，且基于 .NET Framework 3.0 类。 与早期的 BizTalk 适配器框架一样，它提供了大量与元数据处理和管理连接相关的大量功能；但是生成的适配器并未绑定到 BizTalk Server 体系结构。  
  
-   使用 WCF LOB 适配器 SDK 编写的适配器公开为自定义绑定，因此可被任何 WCF 客户端应用程序调用。 还可以扩展为 WCF 通道。 使用 BizTalk 适配器框架编写的适配器只能被 BizTalk Server 调用。  
  
 BizTalk 适配器框架不具有显式开发工具支持。 对于 WCF LOB 适配器 SDK，适配器代码生成向导将指导你进行一系列步骤收集自定义适配器将需要使用的各种信息，然后生成文件以便你在自定义适配器项目中使用。