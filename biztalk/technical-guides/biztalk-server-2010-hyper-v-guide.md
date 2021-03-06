---
title: BizTalk Server 2010 HYPER-V 指南 |Microsoft Docs
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
ms.openlocfilehash: 3eb61f489eb22bcd2c73be3c528c788d97d23878
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399299"
---
# <a name="biztalk-server-2010-hyper-v-guide"></a>BizTalk Server 2010 HYPER-V 指南
本指南的目的是提供一些实践指导，用于将 Microsoft BizTalk Server 与 Microsoft[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]的 HYPER-V。 该技术着重于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，但性能评估方法和测试方案的性能非常适用于一般情况下分析虚拟化的服务器应用程序的性能。 本指南将对其感兴趣的 IT 专业人员和开发人员社区。  

 若要下载此指南的副本，请转到[ http://go.microsoft.com/fwlink/?LinkId=149267 ](http://go.microsoft.com/fwlink/?LinkId=149267)。  

## <a name="introduction"></a>简介  
 服务器虚拟化使公司能够在一台物理计算机上运行多个操作系统。 这使合并到较小数目的充分利用计算机上的未充分利用服务器。 通过实现虚拟化，公司可以最小化操作和资本支出成本与部署和操作所需的企业应用程序服务器相关联。  

 节省的成本也会 IT 部门来评估新的和现有的应用程序，以确定适合进行服务器虚拟化的候选对象。 发现虚拟化的总成本，以期最这样的计算。 虚拟化的总成本是针对硬件和 IT 操作的成本和相比性能可以利用它来在物理环境中的虚拟化的性能成本的总和。 本指南重点介绍专门的虚拟化性能方面。  

 从 Windows Server 2008 开始，使用 HYPER-V 技术的服务器虚拟化已由操作系统的组成部分。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] HYPER-V 提供了一套可靠、 优化虚拟化解决方案，使组织能够提高服务器利用率并降低成本。 添加了新功能，例如实时迁移功能、 扩展的处理器和内存支持主机系统，支持动态虚拟机存储，它可让组织合并到一台物理服务器上的工作负荷并且是对于正在整合服务器以及开发和测试环境的组织很好的解决方案。  

 BizTalk Server 将利用作为的一部分包含的最新的虚拟化改进[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V，可能会导致降低通过生产服务器合并和业务连续性管理，以及更多动态创建的成本IT 基础结构。 聚类分析功能允许在多站点而无需其他软件或硬件的聚类分析环境中部署 BizTalk Server。 HYPER-V 提供了支持的虚拟化实例上运行的 BizTalk Server 的多个实例[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 服务器虚拟化使 BizTalk 客户能够以安全的方式合并未充分利用的资源的 BizTalk 部署硬件的占用最小化。  

 BizTalk Server 部署通常包含多个其他组件包括：SQL Server、 Windows Server 和 Internet 信息服务 (IIS)。 HYPER-V 动态预配通过 System Center Virtual Machine Manager (VMM) 这使预配按需真实方案提供支持。  

 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 提供的 HYPER-V 技术，以容纳通过虚拟化到一台物理服务器上的多个操作系统实例的服务器合并。 作为的核心部分提供的 HYPER-V[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]或作为独立产品，以使其尽可能地接受在其组织中的虚拟化的客户轻松。 有几个主要方案实现 Hyper-v:  

- **服务器合并**– 最大程度减少服务器的内存占用、 操作和资本支出 (TCO) 与通过合并多个物理服务器到单机上的运行应用程序相关联。  

- **测试和开发**– 使用虚拟机，开发人员和架构师可以快速设置新机尝试新技术并准确地反映了物理环境的特征的安全环境中的方案。 虚拟化使新机，以将其预配的操作系统的通用平台上运行无需任何所需的新硬件。 这对于测试和开发环境提供优秀的平台。  

- **业务连续性和灾难恢复**– HYPER-V 包括功能强大的业务连续性和灾难恢复功能，如实时备份和快速迁移，从而使企业能够满足其服务级别协议。  

  > [!NOTE]  
  >  有关如何备份 HYPER-V 虚拟机使用 Windows Server Backup，请参阅 Microsoft 知识库文章 958662，"如何备份 HYPER-V 虚拟机从父分区的 Windows Server 2008 基于计算机上使用 Windows在进行服务器备份" [ http://go.microsoft.com/fwlink/?LinkId=131207 ](http://go.microsoft.com/fwlink/?LinkId=131207)。  
  >   
  >  有关如何使用 HYPER-V 实时迁移提供的功能在 Windows Server 2008 R2 中的信息，请参阅"Hyper-v:在 Windows Server 2008 R2 中使用实时迁移的分步指南"处[ http://go.microsoft.com/fwlink/?LinkID=139667 ](http://go.microsoft.com/fwlink/?LinkID=139667)。  

- **动态数据中心**-通过将 HYPER-V 结合使用的工具 Microsoft System Center 套件，组织可以自动执行虚拟机配置和监视。 详细信息，请参阅"System Center Virtual Machine Manager"网址[ http://go.microsoft.com/fwlink/?LinkID=111303 ](http://go.microsoft.com/fwlink/?LinkID=111303)。  

  本指南中的信息与直接相关的服务器合并和测试和开发方案的 HYPER-V。 本指南的范围超出了另外两个。  

  有关 HYPER-V 的核心方案的详细信息，请参阅[Hyper-v： 使用虚拟化概述](http://go.microsoft.com/fwlink/?LinkID=202438)和中的主题[Appendices1](../technical-guides/appendices1.md)本指南的部分。  

### <a name="who-should-read-this"></a>谁应该读懂？  

- 所有 IT 专业人员使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- IT 专业人员部署、 优化和维护应用程序环境  

- IT 专业人员与开发团队来评估和优化系统体系结构  

- 开发人员创建和维护[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序  

- 开发人员感兴趣的性能优化和确定性能瓶颈  

### <a name="goals-of-this-guide"></a>本指南的目标  
 本指南的主要目标是提供有关如何确定是否有可能达到性能预期的 HYPER-V 上运行的 BizTalk Server 的指南。 本指南还将的值作为优化的已部署的辅助手段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  

 此项目已执行与以下目标：  

- 提供评估、 设计时，或实现虚拟化环境的任何人的具体指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  

- 提供的性能监视器计数器和用于测量虚拟化的服务器平台的性能功能的工具的简介。  

- 提供指导原则，用于确定虚拟化的成本为物理和虚拟化服务器环境之间的性能差异的函数。  

- 开发规划或优化虚拟化时使用的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  

- 提供可帮助您确定如何部署的体系结构指导[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]虚拟化环境中。  

- 确定并记录在虚拟化环境中的性能瓶颈。  

### <a name="whats-in-this-guide"></a>本指南中是什么？  
 实现指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 HYPER-V 虚拟化环境的解决方案。 本指南包括：  

- **HYPER-V 上部署 BizTalk Server**:[部署 BizTalk Server 上的 HYPER-V](../technical-guides/deploying-biztalk-server-on-hyper-v.md)介绍的步骤来设置用于比较的性能在实验室环境中遵循[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 HYPER-V 虚拟机运行到同一个解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在运行的解决方案物理硬件。  

- **评估 HYPER-V 上的 BizTalk Server 性能**:[评估 HYPER-V 上的 BizTalk Server 性能](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)时测量性能的详细信息的重要注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的 HYPER-V 虚拟化环境中运行的解决方案。  

- **测试 HYPER-V 上的 BizTalk Server 性能**:[测试 BizTalk Server 虚拟化性能](../technical-guides/testing-biztalk-server-virtualization-performance.md)提供的性能进行比较的四个不同的测试方案的详细的结果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 HYPER-V 虚拟机运行到同一个解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案在物理硬件上运行。  

- **附录**:中的主题[Appendices1](../technical-guides/appendices1.md)提供本指南中包括的重要参考资料：  

  -   [附录 a:优化应用到测试环境中计算机](../technical-guides/appendix-a-optimizations-applied-to-computers-in-test-environment.md)– 提供有关已应用到测试环境中的计算机的性能优化的详细的信息。  

  -   [附录 b:HYPER-V 体系结构和功能概述](../technical-guides/appendix-b-hyper-v-architecture-and-feature-overview.md)-提供 HYPER-V 体系结构的概述，描述了 HYPER-V 的优点和缺点和描述的 HYPER-V 和 Virtual Server 2005 之间的差异  

  -   [附录 c:BizTalk Server 和 SQL Server 的 HYPER-V 可支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)– 描述的 HYPER-V 虚拟机上运行 BizTalk Server 和 SQL Server 支持策略。  

  -   [附录 d:用于测量性能工具](../technical-guides/appendix-d-tools-for-measuring-performance.md)-描述可用于监视和评估 BizTalk Server 环境的性能的几个工具。  

- **术语表**:[Glossary8](../technical-guides/glossary8.md)定义本指南中使用的关键术语。
