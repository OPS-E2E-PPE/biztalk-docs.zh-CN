---
title: 规划开发、 测试、 过渡和生产环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c83a42d-117f-4a24-a669-b3e4e1c9a056
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40fa445127b5bb5e6a138820d9d321195580d823
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397023"
---
# <a name="planning-the-development-testing-staging-and-production-environments"></a>规划开发、 测试、 过渡和生产环境
本主题讨论在发布管理过程中使用的 BizTalk 解决方案的环境。 与任何企业软件解决方案一样，在开发和发布 BizTalk 解决方案时应遵循成熟的软件版本管理准则。 此过程中应包括以下不同的阶段：  
  
- 开发  
  
- 正在测试  
  
- 过渡环境  
  
- Production  
  
  理想情况下，应完成发布管理过程在独立环境中，独立于其他环境中的每个阶段。 实际上，您可能需要合并一个或多个环境中由于硬件、 时间或其他资源约束。 至少应分开来自其他环境的生产环境。  
  
> [!NOTE]
>  BizTalk Server 的最新的安装和升级说明将列在[BizTalk Server 的新增功能新建、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。 
> 
> ##  <a name="BKMK_VirtualServ"></a> 在发布管理过程期间使用虚拟服务器  
>  请考虑完成开发，单元测试和过渡中的"虚拟"的环境。 执行的开发工作，单元测试和过渡环境中的虚拟环境可提供极大的灵活性并且使用硬件的资源比否则所需的资源要少得多。 如果使用虚拟环境，则为每个主机计算机和额外的 512 MB 的内存的主机操作系统运行的虚拟机分配至少 512 MB 的内存。  
  
 例如，对于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用五个虚拟机的环境 (两台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 两个 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集节点，并且有一个域控制器)，你要计划 3 GB 的内存主机计算机上安装。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境要求超过 2 GB 的内存，请考虑以确保已安装内存的最长的主机操作系统可访问的主机计算机上安装 Windows 的 64 位版本。  
  
> [!NOTE]
>  有关使用建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在虚拟环境中，请参阅[BizTalk Server 2009 HYPER-V 指南](http://go.microsoft.com/fwlink/?LinkId=151834)(<http://go.microsoft.com/fwlink/?LinkId=151834>)。  
> 
> [!NOTE]
>  在任何 Microsoft 知识库文章 842301 中列出的虚拟化软件运行受支持操作系统上完全支持 BizTalk Server [的虚拟机上的MicrosoftBizTalkServer可支持性](https://support.microsoft.com/kb/842301). 但是，BizTalk Server 可能无法执行按预期方式如果不是在知识库文章中提到过虚拟化软件中运行受支持操作系统上安装。  
  
## <a name="development-environment"></a>开发环境  
 在开发环境中创建用于 BizTalk 解决方案的 BizTalk 项目。 应在使用中的计算机上安装以下软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发环境：  
  
- Internet 信息服务 (IIS)  
  
- Visual Studio  
  
- SQL Server 客户端工具  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] （包括以下组件）  
  
  -   文档  
  
  -   管理工具  
  
  -   开发人员工具和 SDK  
  
  -   其他软件  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库是以本地托管在开发过程。  
  
- 通常开发人员应具有其自己的开发计算机 （物理或虚拟） 并安装所需的软件。  
  
> [!NOTE]  
>  我们建议您购买和非生产环境中使用 Visual Studio 订阅。 Visual Studio 订阅均从相同的软件的零售许可证的成本提供可观的折扣。 请参阅[Visual Studio 订阅](https://visualstudio.com/subscriptions)。  
  
## <a name="testing-environment"></a>测试环境  
 单元测试可以在虚拟环境中完成。 但是，应该执行性能测试硬件和软件的等同于生产环境的物理环境中。  
  
 测试环境用于度量性能特征，例如最大可承受吞吐量 (MST) 和 BizTalk 解决方案的最大可承受跟踪吞吐量。 因此，它应尽可能接近地匹配物理生产环境。 有关测量性能的详细信息请参阅 BizTalk 解决方案的特征[引擎性能特征](../core/engine-performance-characteristics.md)，或[BizTalk Server 性能优化指南](../technical-guides/biztalk-server-2010-performance-optimization-guide.md)。
  
## <a name="staging-environment"></a>过渡环境  
 通常使用过渡环境进行"单元测试"实际部署的 BizTalk 解决方案。 在过渡环境中安装的软件应密切匹配在生产环境中安装的软件。 但是，是可以接受在过渡环境中使用的虚拟计算机，因为此环境并不是用于衡量性能。 有关部署到过渡环境的 BizTalk 应用程序的详细信息请参阅[BizTalk 应用程序部署的暂存任务](../core/staging-tasks-for-biztalk-application-deployment.md)。
  
## <a name="production-environment"></a>生产环境  
 在生产环境是将承载正在运行的 BizTalk 解决方案的"实时"环境。 生产环境中发布管理过程的最后一个终结点，应仅主机 BizTalk 应用程序之前经过了开发、 单元测试、 负载测试，以及在其他环境中的过渡。 全面的单元测试、 负载测试和过渡事先将帮助确保最大性能和 BizTalk 应用程序在生产环境中正常运行时间。  
  
## <a name="guidelines-for-allocating-servers"></a>准则分配服务器  
 以下指南提供有关 BizTalk server 的数目经验和 SQL server 应分配给每个阶段中发布管理过程提供了特定数量的物理计算机应在生产中使用：它们是粗略的估计值，这可能会有所更改，具体取决于您的体系结构。  
  
> [!NOTE]  
>  虚拟服务器可能用于在开发过程，在过渡环境中，还可用于单元测试。 应与生产环境中的物理硬件相匹配的物理硬件上执行所有的性能测试。  
  
|在生产环境 （物理硬件建议） 中使用运行 BizTalk Server 计算机|开发服务器 （虚拟或物理硬件）|测试服务器 （建议的物理硬件）|暂存服务器 （虚拟或物理硬件）|总否。 运行 BizTalk Server 的计算机|  
|---|---|---|---|---|  
|1|2|1|1|5|  
|2|2|2|1|7|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
|估计否。 运行生产 （建议的物理硬件） 中使用的 SQL Server 的计算机|开发服务器 （虚拟或物理硬件）|测试服务器 （建议的物理硬件）|暂存服务器 （虚拟或物理硬件）|总否。 运行 SQL Server 的计算机|  
|---|---|---|---|---|  
|1|1|1|1|4|  
|2|1|2|1|6|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk Server 规划环境](../technical-guides/planning-the-environment-for-biztalk-server.md)