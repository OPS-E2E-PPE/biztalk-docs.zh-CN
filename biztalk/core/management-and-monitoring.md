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
ms.openlocfilehash: f7b7bd79d927a63a0a7af2e9b7079c29aad2d3b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380441"
---
# <a name="management-and-monitoring"></a>管理和监视
基于每个应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎需要管理。 如何安装新的应用程序？ 可以进行哪些配置？ 发生了什么系统内部的稍后再试？ 本部分介绍提供来回答这些问题的工具。  
  
## <a name="installing-biztalk-server"></a>安装 BizTalk Server  
 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括多个组件，并依赖于 Windows 环境的多个方面。 确保该产品需要的所有内容的正确版本可用，则正确安装所有产品组件都可能是一个具有挑战性的过程。  
  
 但是，安装是非常简单。 从 BizTalk Server 2009 升级是自动的并且为这一早期版本构建的所有项，业务流程、 映射和等等 — 将继续工作。 若要确保在正确的环境存在，管理员在执行新安装的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以下载标准。CAB 文件或引用已可用。早先下载的 CAB 文件。 在任一情况下，此文件包含产品所需安装可再发行组件。 这包括正确版本的 Microsoft 数据访问组件 (MDAC)、 Microsoft XML Parser (MSXML)、 最新的安全热修补和其他必要的软件。  
  
 之后此内容。在安装 CAB 文件，有两个主要方法来安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]本身。 典型的是开发人员创建的默认方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境可能会执行其自身使用，用于安装所有产品的组件在单个帐户下的一台计算机上。 进程启动后，开发人员可以只是监视时安装这些组件。 管理员设置生产[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，与此相反，可以使用自定义配置选项。 此选项，可以将该产品部署到不同的计算机、 定义和使用不同的帐户，以及其他更详细的配置。  
  
## <a name="creating-scalable-configurations"></a>创建可缩放配置  
 如果不需要，整个高可用性或冗余[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎可以安装在一台计算机上。 在某些情况下，但是，这不是正确的解决方案。 可能是该引擎必须处理的消息数太多对一台计算机时或者您可能需要使系统更可靠，冗余很。 为满足上述需要，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以通过多种方式部署引擎。  
  
 部署引擎的基本概念在于主机。 主机可以包含各种操作，包括业务流程、 适配器和管道。 主机是只是逻辑构造，但是所示。 若要使用它们，BizTalk Server 管理员必须创建主机实例... 每个主机实例是一个 Windows 过程中，并作为关系图中所示，它可以包含不同的项。 在此处显示的示例，计算机 A 是宿主的两个主机实例。 一个包含接收适配器，接收管道时，另一个包含业务流程 P 和计算机 B 运行一个主机实例，还包含两个业务流程 P 和问： 机 C，计算机 A 一样，是承载了两个主机实例，但它们都未包含业务流程。 相反，这些实例的每个包含不同的发送管道和发送适配器。 最后，计算机 D 存储所有在此配置中的主机实例使用的 MessageBox 数据库。  
  
 ![](../core/media/understandingbts-09-hosts.gif "UnderstandingBTS_09_Hosts")  
  
 此示例说明了几种方法可能会在其中使用的主机。 例如，由于计算机 A 和 B 均承载了业务流程 P 和 Q，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以自动进行负载平衡请求对这些业务流程根据可用性和每台计算机上的当前负载。 这样，BizTalk 应用程序若要纵向扩展所需的大量进程。 请注意，计算机 C 也包含两种不同方式处理传出消息。 一种方法依赖一种标准[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器，如 HTTP 适配器，而另一个则使用自定义适配器与特定系统进行通信。 在某些情况下，对所有输出处理如下一台计算机上进行都分组可能会很有用。 而且由于每个主机实例都独立于其他每个主机实例 — 它们是不同的进程，会运行不完全受信任，如新的自定义适配器，在一个单独实例中的代码更加安全。 尽管此示例中包含单个实例的 MessageBox 数据库，可以将复制或群集该以避免创建单一故障点。  
  
 BizTalk 应用程序的当前版本中引入的抽象[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未本质上与主机相关联。 对于简单的 BizTalk 应用程序，其所有组件可能包含在单个主机中，所有这些安装在同一台计算机上。 在更复杂的情况下，但是，各种项目，组成应用程序 — 业务流程、 适配器、 管道和的详细信息 — 可能分布在多个主机上多台计算机，如图所示。 相应地，这些项目映射到物理计算机的过程不依赖于 BizTalk 应用程序的概念。  
  
## <a name="managing-applications"></a>管理应用程序  
 用于管理的主要工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎是 BizTalk Server 管理控制台中，Microsoft 管理控制台 (MMC) 管理单元，提供用户界面用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员。 此工具，管理员的许多功能，最重要的是能够做三件事：  
  
- **部署 BizTalk 应用程序。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使管理员能够使用完整的 BizTalk 应用程序作为一个单元。 使用 BizTalk Server 管理控制台，管理员可以创建 BizTalk 应用程序，并将其部署到一个或多个服务器。  
  
- **配置 BizTalk 应用程序。** 当开发人员创建业务流程时，它们将在逻辑词很大程度上工作。 若要定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎将与通信的特定应用程序，例如，开发人员可以选择 HTTP 适配器，而无需担心将使用的特定 URL。 同样，开发人员可以指定发送管道应包括对传出消息添加数字签名，而无需担心完全哪个密钥将用于创建此签名的组件。 但若要使应用程序正常工作，必须指定这些详细信息。 BizTalk Server 管理控制台，管理员可以创建和修改这些配置。  
  
- **监视 BizTalk 应用程序。** 使用**组中心**页在 BizTalk Server 管理控制台中，管理员可以监视 BizTalk 应用程序的操作。 组中心显示了这些应用程序的信息的当前状态和它们的应用程序可以通过各种方式检查。 不需要管理员的问题，例如，搜索**组中心**页使用彩色编码的指示器来显示这些问题。 这样管理员就可以采取更主动的方法来监视应用程序。  
  
  BizTalk 管理控制台中，依赖于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的管理数据库，还提供其他服务。 管理员可以动态添加计算机，指定主机应该是应用程序运行时分配给他们。 没有必要关闭应用程序进行这些更改。 管理控制台的功能也可以访问以编程方式通过 Windows Management Instrumentation (WMI)，允许管理员创建自动执行管理功能的脚本。  
  
## <a name="reporting-on-and-debugging-applications"></a>报告和调试应用程序  
 BizTalk 应用程序执行各种任务： 发送和接收消息、 处理业务流程内的消息、 与使用不同的协议，以及更多的各种系统通信。 保留的应用程序活动的记录，尤其是出现故障时，会非常有用。 同样，通过某种方法来调试业务流程和其他应用程序组件非常重要。 这两项功能提供的组中心[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   组中心提供了图形访问有关在引擎上运行的应用程序的信息。 业务流程开始和结束，每个形状的执行时，每条消息发送和接收这些消息和的详细信息的内容时，可以将此信息。 甚至，开发人员或管理员可以设置断点，以便业务流程，以停止并检查在预设的位置。 组中心还可检查已存档的数据，查找模式和在业务流程的执行过程中的趋势。 此信息对于调试很有用，回答业务问题 （如验证，消息确实已发送给客户），并保持统计数据可用于提高性能。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 消息引擎](../core/the-biztalk-server-messaging-engine.md)   
安装[BizTalk Server 2016](../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)或[BizTalk Server 2013 或 R2](../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)    
[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)  
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)   
 [使用“组中心”页](../core/using-the-group-hub-page.md)