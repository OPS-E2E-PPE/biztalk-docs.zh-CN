---
title: 管理和监视 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92724f79-32bb-40d3-a0af-147aba00d87e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea24b6e36de3920a820efe2ac1af177b8a00720d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973566"
---
# <a name="management-and-monitoring"></a>管理和监视
对每个基于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎建立的应用程序都需要进行管理。 如何安装新应用程序？ 可以进行哪些配置？ 系统内部的现况如何？ 本部分介绍为解答上述问题而提供的各种工具。  
  
## <a name="installing-biztalk-server"></a>安装 BizTalk Server  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括许多组件，并依赖于 Windows 环境的多个方面。 请确保提供了该产品需要的所有正确版本，然后正确安装所有产品组件，完成这一过程可能颇具挑战性。  
  
 不过，安装过程十分简单。 升级 BizTalk Server 2009 是自动完成的，为这一早期版本生成的所有项（业务流程、映射等）都能够继续使用。 为确保已存在适当的环境，新安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的管理员可以下载标准 .CAB 文件或引用早先下载的已有的 .CAB 文件。 无论在哪种情况下，此文件都包含安装该产品所需的可再发行的组件。 这包括正确版本的 Microsoft 数据访问组件 (MDAC)、Microsoft XML 解析程序 (MSXML)、最新的安全热修补程序以及其他必需软件。  
  
 安装此 .CAB 文件的内容后，可选择使用两种主要方法来安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 本身。 默认方法，也是开发人员创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境供其自身使用时通常可能采取的方法，即是使用单个帐户将该产品的所有组件安装到一台计算机上。 在启动该进程后，开发人员只需在安装这些组件时进行监视即可。 相比之下，设置生产 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境的管理员还可使用自定义配置选项。 使用此选项，可以将该产品部署到不同计算机上、定义和使用不同的帐户，以及进行其他更详细的配置。  
  
## <a name="creating-scalable-configurations"></a>创建灵活配置  
 如果不需要较高的可用性或冗余，则可以将整个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎都安装在一台计算机上。 然而，在某些情况下，这可能不是适当的解决方案。 该引擎必须处理的消息数对一台计算机来说可能太大，或者可能需要冗余以确保系统的可靠性。 为满足上述需要，可以通过多种方式部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎。  
  
 部署引擎的基本概念在于主机。 主机可以包含业务流程、适配器和管道等。 不过，主机只是逻辑构造。 若要使用主机，BizTalk Server 管理员必须创建主机实例。 每个主机实例都是一个 Windows 进程，正如下图所示，该进程可包含不同的项。 在此处显示的示例中，计算机 A 承载了两个主机实例。 其中一个实例包含接收适配器和接收管道，另一个实例包含业务流程 P 和业务流程 Q。计算机 B 仅运行一个主机实例，其中也包含两个业务流程 P 和 Q。和计算机 A 一样，计算机 C 也承载了两个主机实例，但它们都未包含任何业务流程。 不过，这两个实例都包含一个不同的发送管道和发送适配器。 最后，计算机 D 存储此配置中所有主机实例使用的 MessageBox 数据库。  
  
 ![](../core/media/understandingbts-09-hosts.gif "UnderstandingBTS_09_Hosts")  
  
 此示例阐释了使用主机的多种方法。 例如，由于计算机 A 和计算机 B 均承载了业务流程 P 和 Q，因此 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以根据每台计算机的可用性和当前负载，对这些业务流程的请求自动进行负载平衡。 这样，对于大容量进程，BizTalk 应用程序即可根据需要进行纵向扩展。 另外请注意，计算机 C 包含两个处理传出消息的不同方法。 一种方法依赖于诸如 HTTP 适配器之类的标准 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器，另一种方法使用自定义适配器与特定系统进行通信。 如上文所述，在单台计算机上对所有输出处理进行分组在某些情况下可能会很有用。 而且，由于每个主机实例都独立于其他任何主机实例（它们是不同的进程），因此在单独实例中运行不完全受信任的代码（如新的自定义适配器）会更加安全。 即使此示例仅包含 MessageBox 数据库的单个实例，也可以复制或群集该数据库以避免创建单个故障点。  
  
 在当前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中引入的 BizTalk 应用程序的抽象概念在本质上与主机不相关联。 对于简单的 BizTalk 应用程序，其所有组件可以包含在单个主机中，并且这些组件全都安装在同一台计算机上。 然而，如上图所示，在更加复杂的情况下，构成该应用程序的业务流程、适配器、管道等各种项目可以分布在多台计算机的多个主机上。 因此，将这些项目映射到物理计算机的进程不依赖于 BizTalk 应用程序的概念。  
  
## <a name="managing-applications"></a>管理应用程序  
 用于管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎的主要工具是 BizTalk Server 管理控制台，该控制台是一个 Microsoft 管理控制台 (MMC) 管理单元，可为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员提供新的用户界面。 使用此工具，管理员能够执行许多任务，尽管如此，其中最重要的功能是执行以下三个任务：  
  
- **部署 BizTalk 应用程序。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使管理员能够使用完整的 BizTalk 应用程序作为一个单元。 使用 BizTalk Server 管理控制台，管理员可以创建 BizTalk 应用程序并将其部署到一个或多个服务器。  
  
- **配置 BizTalk 应用程序。** 当开发人员创建业务流程时，他们基本上使用逻辑术语进行工作。 例如，若要定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎将如何与特定应用程序进行通信，开发人员可以选择 HTTP 适配器而无需为要使用的特定 URL 而操心。 同样，开发人员可以指定发送管道应包括一个用于向传出消息添加数字签名的组件，而无需精确考虑要用于创建此签名的密钥。 尽管如此，若要使应用程序正常工作，必须指定这些详细信息。 使用 BizTalk Server 管理控制台，管理员可以创建并修改这些配置。  
  
- **监视 BizTalk 应用程序。** 使用**组中心**页在 BizTalk Server 管理控制台中，管理员可以监视 BizTalk 应用程序的操作。 组中心显示有关这些应用程序的当前状态的信息，并且可以通过各种方式检查这些应用程序。 不需要管理员的问题，例如，搜索**组中心**页使用彩色编码的指示器来显示这些问题。 这样，管理员就可以采取更主动的方法来监视应用程序。  
  
  依赖于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的 BizTalk 管理控制台还可提供其他服务。 管理员可以在运行应用程序时动态添加计算机并指定应为其分配的主机。 无需关闭该应用程序即可进行这些更改。 还可以通过 Windows 管理规范 (WMI) 以编程方式访问管理控制台的功能，以便管理员创建自动执行管理功能的脚本。  
  
## <a name="reporting-on-and-debugging-applications"></a>报告和调试应用程序  
 BizTalk 应用程序执行各种任务： 发送和接收消息、 处理业务流程内的消息、 与使用不同的协议，以及更多的各种系统通信。 保留应用程序活动的记录十分有用，在出现故障时尤其如此。 同样，通过某种方法来调试业务流程和其他应用程序组件也非常重要。 这两个功能 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的组中心均已提供。  
  
-   通过使用组中心，可以按图形方式访问有关在引擎上运行的应用程序的信息。 这些信息可能包括业务流程的开始时间和结束时间、其中每个形状的执行时间、发送和接收每条消息的时间、这些消息的内容，等等。 开发人员或管理员甚至可以设置断点，以便在预设的位置停止业务流程并对其进行检查。 组中心还可检查已存档的数据，查找模式和在业务流程的执行过程中的趋势。 这些信息可用于进行调试、解答业务问题（例如验证消息确实已发送给客户），以及随时记录可用于提高性能的统计数据。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 消息引擎](../core/the-biztalk-server-messaging-engine.md)   
安装[BizTalk Server 2016](../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)或[BizTalk Server 2013 或 R2](../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)    
[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)  
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)   
 [使用“组中心”页](../core/using-the-group-hub-page.md)