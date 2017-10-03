---
title: "规划开发、 测试、 过渡和生产环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c83a42d-117f-4a24-a669-b3e4e1c9a056
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25eb6aadd41526adeecb9c5a249d38384fb532ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-the-development-testing-staging-and-production-environments"></a>规划开发、 测试、 过渡和生产环境
本主题讨论在发布管理过程中用于 BizTalk 解决方案的环境。 与任何企业软件解决方案，在开发和发布 BizTalk 解决方案时应遵循它成熟的软件版本管理准则。 此过程中应包括以下不同阶段：  
  
-   开发  
  
-   测试  
  
-   过渡  
  
-   Production  
  
 理想情况下，应完成独立于其他环境的离散环境中的版本管理过程中每个阶段。 实际上，你可能需要合并一个或多个由于硬件、 时间或其他资源约束的环境。 裸机至少应该将来自其他环境的生产环境。  
  
> [!NOTE]  
>  有关最新的安装和升级说明[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]都可用作上的单独下载[BizTalk Server 2010 文档页](http://go.microsoft.com/fwlink/?LinkID=194815)(http://go.microsoft.com/fwlink/?LinkID=194815)。  
  
##  <a name="BKMK_VirtualServ"></a>在版本管理过程中使用虚拟服务器  
 请考虑完成开发，单元测试，和过渡中"虚拟"的环境。 Microsoft 提供了一系列如 Microsoft Virtual Server 2005 R2、 Windows Server 2008 HYPER-V 和 Microsoft HYPER-V Server 2008 的虚拟化产品。 [Microsoft Virtual Server 2005 R2](http://go.microsoft.com/fwlink/?LinkId=71365) (http://go.microsoft.com/fwlink/?LinkId=71365) 是作为免费下载提供。 执行的开发工作，单元测试和在虚拟环境中的暂存提供极大的灵活性，并使用显著较少的硬件资源比否则要求。 如果使用虚拟环境，则为每个主机计算机和其他的 512 MB 的内存用于主机操作系统运行的虚拟机分配至少 512 MB 的内存。  
  
 例如，对于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 5 个虚拟机的环境 (两台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 两个 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集节点，并且一个域控制器)，要有 3 GB 的主计算机上安装的内存。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境需要超过 2 GB 的内存，请考虑在主机计算机，以确保已安装的内存最大数量是可访问的主机操作系统上安装 Windows 的 64 位版本。  
  
> [!NOTE]  
>  有关使用建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在虚拟环境中，请参阅[BizTalk Server 2009 HYPER-V 指南](http://go.microsoft.com/fwlink/?LinkId=151834)(http://go.microsoft.com/fwlink/?LinkId=151834)。  
  
> [!NOTE]  
>  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]完全支持上受支持的操作系统的任何 Microsoft 知识库文章 842301 中列出的虚拟化软件上运行[Microsoft BizTalk Server 可支持性的虚拟机上](http://go.microsoft.com/fwlink/?LinkId=158861)(http://go.microsoft.com/fwlink/？LinkId = 158861)。 但是，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]按预期如果安装在受支持的操作系统中除了知识库文章中所述的虚拟化软件的运行方式可能无法执行。  
  
## <a name="development-environment"></a>开发环境  
 在开发环境中创建用于 BizTalk 解决方案 BizTalk 项目。 应在使用中的计算机上安装以下软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发环境：  
  
-   Internet 信息服务 (IIS)  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] 客户端工具  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（包括以下组件）  
  
    -   文档  
  
    -   管理工具  
  
    -   开发人员工具和 SDK  
  
    -   其他软件  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库要在开发过程中本地托管。  
  
-   通常开发人员应具有其自己的开发计算机 （物理或虚拟） 所必需的软件安装。  
  
> [!NOTE]  
>  我们建议您购买，并将用于非生产环境的 MSDN 订阅许可证。 MSDN 订阅许可证从相同的软件的零售许可证的成本提供高折扣。 有关获取 MSDN 订阅的详细信息请参阅[MSDN 订阅](http://go.microsoft.com/fwlink/?LinkID=96006)(http://go.microsoft.com/fwlink/?LinkID=96006)。  
  
## <a name="testing-environment"></a>测试环境  
 单元测试可在虚拟环境中完成。 但是，它后，应该执行您在硬件和软件等同于生产环境的物理环境中测试的性能。  
  
 测试环境用于测量性能特征，如最大可持续吞吐量 (MST) 和 BizTalk 解决方案的最大可持续跟踪吞吐量。 因此，它应尽可能真实地匹配物理生产环境了。 BizTalk 解决方案的特征有关测量性能的详细信息请参阅[引擎性能特征](http://go.microsoft.com/fwlink/?LinkId=155771)(http://go.microsoft.com/fwlink/?LinkId = 155771) 或[BizTalk Server 2009 性能优化指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID = 150492)。  
  
## <a name="staging-environment"></a>过渡环境  
 通常使用过渡环境进行"单元测试"实际部署 BizTalk 解决方案。 过渡环境中安装的软件应接近生产环境中安装软件。 但是，所以可能，是可以接受的过渡环境中使用虚拟计算机，因为此环境是不能以衡量性能。 有关部署到过渡环境 BizTalk 应用程序的详细信息请参阅[BizTalk 应用程序部署的暂存任务](http://go.microsoft.com/fwlink/?LinkID=154686)(http://go.microsoft.com/fwlink/?LinkID=154686)。  
  
## <a name="production-environment"></a>生产环境  
 生产环境是将承载运行 BizTalk 解决方案的"实时"环境。 生产环境中发布管理过程的最后一个终结点，应仅主机 BizTalk 应用程序以前已进行开发，单元测试、 负载测试和在其他环境中的过渡。 全面的单元测试、 负载测试，和过渡事先将帮助确保最大的性能和在生产环境中 BizTalk 应用程序的运行时间。  
  
## <a name="guidelines-for-allocating-servers"></a>准则分配服务器  
 以下指南提供一条经验法则，BizTalk 服务器和 SQL server 应分配给每个阶段中发布管理过程假设有特定数量的物理计算机的数量应在生产中使用的： 它们是粗略如有更改，具体取决于你的体系结构的估计。  
  
> [!NOTE]  
>  虚拟服务器可用于在开发和过渡环境中，并且还用于单元测试。 应在与生产环境中的物理硬件匹配的物理硬件上执行所有性能测试。  
  
|在生产 （建议的物理硬件） 中运行 BizTalk Server 使用的计算机|开发服务器 （虚拟或物理硬件）|测试服务器 （建议的物理硬件）|暂存服务器 （虚拟或物理硬件）|总否。 运行 BizTalk Server 的计算机|  
|-------------------------------------------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------|------------------------------------------------------|---------------------------------------------------|  
|1|2|1|1|5|  
|2|2|2|1|7|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
|估计否。 运行在生产 （建议的物理硬件） 中使用的 SQL Server 的计算机|开发服务器 （虚拟或物理硬件）|测试服务器 （建议的物理硬件）|暂存服务器 （虚拟或物理硬件）|总否。 运行 SQL Server 的计算机|  
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------|------------------------------------------------------|-----------------------------------------------|  
|1|1|1|1|4|  
|2|1|2|1|6|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 规划环境](../technical-guides/planning-the-environment-for-biztalk-server.md)