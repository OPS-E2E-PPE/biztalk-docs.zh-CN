---
title: BizTalk Server 2010 Hyper V 指南 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c38ecdd-de72-41d9-b639-2aa6bbfee917
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 937fcb3618bf3bde4883242d48da2a841f00dea5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-server-2010-hyper-v-guide"></a>BizTalk Server 2010 Hyper V 指南
本指南的目的是提供 Microsoft BizTalk Server 使用 Microsoft 的实践性指南[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V。 重点是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，但性能评估方法和测试方案的性能会用于分析虚拟化的服务器应用程序的性能通常很有用。 本指南将感兴趣的 IT 专业人员和开发人员社区。  
  
 若要下载本指南的副本，请转到[http://go.microsoft.com/fwlink/?LinkId=149267](http://go.microsoft.com/fwlink/?LinkId=149267)。  
  
## <a name="introduction"></a>简介  
 服务器虚拟化使公司能够在单个物理计算机上运行多个操作系统。 这使到较小的几个充分利用计算机的未充分利用服务器合并。 通过实现虚拟化，公司可以最小化操作和资本支出成本与部署和操作为企业应用程序所需的服务器。  
  
 潜在的成本节省具有提示 IT 部门能够评估新的和现有的应用程序，以确定适用于服务器虚拟化候选项。 最这样的计算，以期发现虚拟化的总成本。 虚拟化的总成本是硬件和 IT 运营的资金成本并相比可达成物理环境中的性能的虚拟化的性能开销的总数。 本指南重点介绍专门的虚拟化性能方面。  
  
 从 Windows Server 2008 开始，使用 HYPER-V 技术的服务器虚拟化已由操作系统的组成部分。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V 提供了可靠且经过优化的虚拟化解决方案，从而使组织能够提高服务器利用率并降低成本。 加上的新功能，如实时迁移功能、 扩展的处理器和内存支持为主机系统，支持动态虚拟机存储，它允许组织整合到单个物理服务器上的工作负荷，并为组织正在整合服务器以及开发和测试环境很好的解决方案。  
  
 BizTalk Server 利用作为的一部分包括的最新的虚拟化改进[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V，可能会导致降低通过生产服务器合并和业务连续性管理，以及多个动态创建的成本IT 基础结构。 聚类分析功能，而无需其他软件或硬件的多站点群集环境中部署的 BizTalk Server。 HYPER-V 提供了支持的虚拟化实例上运行的 BizTalk Server 几个实例[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 服务器虚拟化使 BizTalk 客户能够将未充分利用的资源整合以安全的方式来尽量减少 BizTalk 部署的硬件占用空间。  
  
 BizTalk Server 部署通常包含大量的其他组件包括： SQL Server、 Windows Server 和 Internet 信息服务 (IIS)。 HYPER-V 提供支持动态设置通过 System Center Virtual Machine Manager (VMM) 这样设置按需一个现实的方案。  
  
 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]提供了 HYPER-V 技术，以适应通过单个物理服务器上的多个操作系统实例的虚拟化进行服务器整合。 HYPER-V 提供的核心一部分[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]或作为独立产品以便尽可能客户能够采用在其组织中的虚拟化方便。 有几个主要方案实现 Hyper-v:  
  
-   **服务器合并**– 最小化 server 内存占用，操作和与通过将合并到一个框中的多个物理服务器运行应用程序关联的资本支出 (TCO)。  
  
-   **测试和开发**– 使用虚拟机，开发人员和架构师可以快速设置新机试用新技术和准确地反映物理环境的特征的安全环境中的方案。 虚拟化能让新机进行设置而无需新硬件所需的操作系统的宽平台上运行。 为测试和开发环境，这提供了很好的平台。  
  
-   **业务连续性和灾难恢复**– HYPER-V 包括功能强大的业务连续性和灾难恢复功能，如实时备份和快速迁移它使企业能够满足其服务级别协议。  
  
    > [!NOTE]  
    >  有关如何备份使用 Windows Server Backup 的 HYPER-V 虚拟机，请参阅 Microsoft 知识库文章 958662，"如何备份 HYPER-V 虚拟机从父分区的 Windows Server 2008 基于计算机上使用 Windows服务器备份"在[http://go.microsoft.com/fwlink/?LinkId=131207](http://go.microsoft.com/fwlink/?LinkId=131207)。  
    >   
    >  有关如何使用 HYPER-V 实时迁移提供的功能在 Windows Server 2008 R2 中的信息，请参阅"Hyper-v： 分步指南到使用实时迁移在 Windows Server 2008 R2"网址[http://go.microsoft.com/fwlink/?LinkID=139667](http://go.microsoft.com/fwlink/?LinkID=139667)。  
  
-   **动态数据中心**– 通过将 HYPER-V 与工具的 Microsoft System Center 套件结合，组织可以自动执行虚拟机配置和监视。 详细信息，请参阅"System Center Virtual Machine Manager"在[http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)。  
  
 本指南中的信息直接于 Hyper V 与服务器合并和测试和开发方案。 本指南的范围超出了与其他两个。  
  
 有关 HYPER-V 的核心方案的详细信息，请参阅[虚拟化 Hyper-v： 概述](http://go.microsoft.com/fwlink/?LinkID=202438)和中的主题[Appendices1](../technical-guides/appendices1.md)本指南的部分。  
  
### <a name="who-should-read-this"></a>谁应当阅读这？  
  
-   所有的 IT 专业人员使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   IT 专业人员部署、 优化和维护的应用程序环境  
  
-   IT 专业人员使用开发团队能够评估并优化系统体系结构  
  
-   开发人员创建和维护[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序  
  
-   开发人员感兴趣性能优化和识别性能瓶颈  
  
### <a name="goals-of-this-guide"></a>本指南的目标  
 本指南的主要目的是提供有关如何确定是否在 HYPER-V 上运行的 BizTalk Server 很可能达到性能预期的指南。 本指南也将的值作为辅助手段的已部署的优化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
 此项目已执行到了以下目标：  
  
-   提供的任何人是评估、 设计时，或者实现虚拟化环境的用户指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
-   提供的性能监视器计数器和工具用于度量的虚拟化的服务器的平台的性能功能的简介。  
  
-   用于确定虚拟化的成本为物理和虚拟化服务器环境之间的性能差异的函数提供一些准则。  
  
-   开发使用情况： 计划或优化虚拟化环境的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
-   提供体系结构指南，以帮助你确定如何部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]虚拟化环境中。  
  
-   确定并记录在虚拟化环境中的性能瓶颈。  
  
### <a name="whats-in-this-guide"></a>本指南中是什么？  
 用于实现指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 HYPER-V 虚拟化环境的解决方案。 本指南包含：  
  
-   **部署 HYPER-V 上的 BizTalk Server**: [HYPER-V 上部署 BizTalk Server](../technical-guides/deploying-biztalk-server-on-hyper-v.md)描述设置实验室环境，用于比较的性能时所遵循的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上运行的解决方案到相同的 HYPER-V 虚拟机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在物理硬件上运行的解决方案。  
  
-   **评估 HYPER-V 上的 BizTalk Server 性能**:[的 BizTalk Server 性能评估 HYPER-V](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)时测量性能的详细信息的重要注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 HYPER-V 上运行解决方案虚拟化的环境。  
  
-   **测试 HYPER-V 上的 BizTalk Server 性能**:[测试 BizTalk 服务器虚拟化性能](../technical-guides/testing-biztalk-server-virtualization-performance.md)提供的比较的性能的四种不同的测试方案的详细的结果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到相同 HYPER-V 虚拟机上运行的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在物理硬件上运行的解决方案。  
  
-   **附录**： 中的主题[Appendices1](../technical-guides/appendices1.md)提供包括本指南的重要的参考资料：  
  
    -   [附录 a： 优化应用到测试环境中计算机](../technical-guides/appendix-a-optimizations-applied-to-computers-in-test-environment.md)– 提供有关已应用于测试环境中的计算机的性能优化的详细的信息。  
  
    -   [附录 b: HYPER-V 体系结构和功能概述](../technical-guides/appendix-b-hyper-v-architecture-and-feature-overview.md)-提供 HYPER-V 体系结构的概述，描述的 HYPER-V，优点和缺点，并介绍 HYPER-V 和 Virtual Server 2005 之间的差异  
  
    -   [附录 c: BizTalk Server 和 SQL Server HYPER-V 可支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)– 介绍用于在 HYPER-V 虚拟机上运行 BizTalk Server 和 SQL Server 的支持策略。  
  
    -   [附录 d： 用于测量性能工具](../technical-guides/appendix-d-tools-for-measuring-performance.md)-介绍了几个工具可用来监视和评估 BizTalk Server 环境的性能。  
  
-   **术语表**: [Glossary8](../technical-guides/glossary8.md)定义本指南中使用的关键术语。