---
title: WCF 适配器常见问题解答：开发库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d05b635a-d46d-4f7d-896b-8ed7a799e80f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce226b4eca18007087378a04c115e95df957fe62
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393606"
---
# <a name="wcf-adapter-faq-development-libraries"></a>WCF 适配器常见问题解答：开发库
## <a name="when-does-it-make-more-sense-to-use-the-wcf-adapters-vs-a-wcf-custom-binding-to-communicate-with-an-external-application-or-system"></a>何时有意义多个要与 WCF 自定义绑定的 WCF 适配器用于与外部应用程序或系统进行通信？  
 BizTalk Server WCF 适配器提供与使用 WCF 的 BizTalk Server 相集成外部系统的两个新方法：  
  
- 您可以编写 WCF 客户端/服务代码，并使用标准 BizTalk Server WCF 适配器来处理通信。  
  
- 或者可以使用.NET WCF 框架开发新的自定义 WCF 绑定，并使用它代替 WCF 适配器来处理通信。  
  
  与 BizTalk Server 使用 WCF 适配器，可以开发 WCF 客户端代码，并调用 BizTalk Server 作为远程 WCF 服务，也可以编写 WCF 服务并配置 BizTalk Server 以便将其公开为 WCF 服务。 替代方法是，你可以实际编写全新的自定义的 WCF 绑定来处理通信。  
  
  编写标准 WCF 客户端或服务代码和编写 WCF 自定义绑定元素相比使用标准 BizTalk Server 适配器的优点是自定义绑定更难开发。 生成 WCF 客户端或服务存在于 BizTalk Server 管理 （监视、 配置和部署） 领域之外。 编写新的自定义绑定并将其使用 BizTalk WCF 自定义适配器承载的优点是，它可以紧密集成到这些 BizTalk Server 管理功能。 与基础结构支持方面，开发绑定关联的成本是显著高于开发服务。  
  
  请务必了解这两种方法为您提供机会与内部 BizTalk MessageBox 数据库集成，以事务的方式，并可提供类似的性能。 很多决定想要使解决方案复杂程度。  
  
  使用 WCF 时应首先尝试编写自定义服务和客户端和使用标准 BizTalk WCF 适配器来连接这两者。 .NET Framework 和 WCF 库专用于轻松执行此任务。 若要创建 WCF 服务，只需开发自定义界面、 设置相应的属性和实现约定后的代码。 WCF 负责从元数据对象序列化到的所有内容。 您然后可以编写您的 WCF 服务配置通过发送端口的 WCF 适配器与几个简单步骤中的服务进行通信。 您甚至可以配置事务，因此您的新服务可以参与与内部 BizTalk MessageBox 数据库的消息的事务性交换。  
  
  在接收端可以配置 BizTalk Server 以便接收位置在网络上看起来就像 WCF 服务一样。 一个可编写常规 WCF 客户端代码，并调用该服务时，您甚至可以使用事务。 将标准 BizTalk WCF 适配器用作直接从 WCF 客户端到 WCF 服务代码的可配置桥的优点是开发情景是非常简单。 WCF 适配器从以简单的方式在 WCF 服务环境到 BizTalk Server 中提供高性能的事务性桥。  
  
  总之，与外部系统进行通信可以编写 WCF 服务以便与外部系统，，，然后编写代码以作为更简单的解决方案与您的问题直接与 WCF 服务进行通信。 使用更复杂的方法，可以编写新的自定义绑定并与 BizTalk Server 使用任一 WCF 自定义适配器以更紧密的方式比使用 WCF 服务集成。 编写新的自定义绑定是较低级别的复杂开发练习。 此方法的好处是可实现紧密集成的解决方案的 BizTalk Server 管理、 配置和开发情景可统一使用整个解决方案。 如果适配器功能开发为外部 WCF 客户端和服务，配置必须是 BizTalk Server 环境之外，并因此缺少相关的基础结构支持。  
  
## <a name="what-are-the-differences-between-the-wcf-adapters-and-the-adapters-in-the-biztalk-adapter-pack"></a>BizTalk 适配器包中的 WCF 适配器和适配器之间的差别是什么？  
 WCF 适配器是 BizTalk Server 发行版标准随附的七个适配器：  
  
- WCF 自定义  
  
- WCF-CustomIsolated  
  
- WCF-NetTcp  
  
- WCF-BasicHttp  
  
- WCF-WsHttp  
  
- WCF-NetNamedPipe  
  
- WCF-NetMsmq  
  
  [BizTalk Adapter Pack](http://www.microsoft.com/biztalk/en/us/adapter-pack.aspx)是提供单个解决方案，可轻松安全地连接到业务 (LOB) 数据从任何自定义开发.NET 应用程序，基于 SQL Server 的业务的 post BizTalk Server 发行版智能解决方案或 Office 业务应用程序 (OBA)。 在此版本中提供的三个适配器是 Siebel、 SAP 和 Oracle DB。 Adapter Pack 许可随附于 BizTalk Server Developer、 Standard 和 Enterprise 版本，但不包括 Branch 版本。 已购买具有软件保障的 BizTalk Server 的客户还将有权访问 BizTalk Adapter Pack 通过该计划。  
  
## <a name="what-is-the-recommended-order-for-deciding-to-use-the-biztalk-server-adapter-framework-the-wcf-lob-adapter-sdk-or-the-net-framework"></a>在决定使用 BizTalk Server 适配器框架、 WCF LOB 适配器 SDK 或.NET Framework 的建议的顺序是什么？  
 BizTalk 适配器框架是最不可取选项，因为它不基于标准.NET WCF。 因为有策略地进行您的解决方案应包括 WCF 最有可能，最佳的方式来执行此操作是什么？ 最简单的选项是编写 WCF 客户端和服务，以及如何将 WCF 适配器将其绑定在一起。 如果 BizTalk Server 外部程序，然后可以编写 WCF 自定义绑定与.NET Framework。  
  
 唯一一次为一个选项是如果您尝试解决很大程度以元数据为中心的 LOB 集成问题，您可以选择 WCF LOB 适配器 SDK。 WCF LOB 适配器 SDK 是另一种方式创建 WCF 绑定，且专用于元数据支持。 与通信的系统不具有固定的文档类型时需要此元数据的示例。 BizTalk Server 发送或接收 XML 文档和元数据描述文档中的数据的布局，以便在目标系统可以使用它。  
  
## <a name="what-are-the-differences-between-the-biztalk-adapter-framework-and-the-wcf-lob-adapter-sdk"></a>BizTalk 适配器框架和 WCF LOB 适配器 SDK 之间的区别是什么？  
 BizTalk 适配器框架用于生成自定义 WCF 适配器时的七个标准 WCF 适配器都不符合通信要求。 适配器框架提供了丰富的元数据以支持 LOB 应用程序，并共享的标准化的配置和管理方法使用标准 WCF 适配器的支持。  
  
 WCF LOB 适配器 SDK，可编写自定义绑定具有大量元数据要求的目标系统。 WCF LOB 适配器 SDK 的目标是实现统一开发可重用的面向元数据的基于 WCF 的适配器，使企业应用程序和数据库彼此集成。 因为使用 WCF LOB 适配器 SDK 生成 WCF 绑定，包括自定义.NET 应用程序、 BizTalk Server、 Microsoft Office SharePoint® Server 和 Microsoft SQL Server 集成的多个.NET 应用程序中，可以重复使用相同的开发的解决方案服务。 此外，WCF LOB 适配器 SDK 提供了一个通用的元数据对象模型以公开目标系统元数据，供适配器使用者浏览、 搜索和检索 WCF 约定从适配器。 你可以下载从 SDK [ http://go.microsoft.com/fwlink/?LinkID=96184 ](http://go.microsoft.com/fwlink/?LinkID=96184)。  
  
 虽然 BizTalk 适配器框架和 WCF LOB 适配器 SDK 具有相似之处在于，它们可帮助促进自定义适配器的开发，有一些值得注意的区别：  
  
- WCF LOB 适配器 SDK 是较新版本，并基于.NET Framework 3.0 类。 与早期的 BizTalk 适配器框架一样它提供了大量与元数据处理和管理连接; 的丰富功能但是，生成的适配器并未绑定到 BizTalk Server 体系结构。  
  
- 通过使用 WCF LOB 适配器 SDK 编写的适配器公开为自定义绑定，因此可调用任何 WCF 客户端应用程序。 此外可以扩展为 WCF 通道。 可以通过 BizTalk Server 调用适配器使用 BizTalk 适配器框架编写的。  
  
  没有显式开发工具支持的 BizTalk 适配器框架。 WCF LOB 适配器 SDK 的适配器代码生成向导将指导你完成一系列的步骤来收集各种信息的自定义适配器将需要使用，然后生成，以便在自定义适配器项目中使用的文件。