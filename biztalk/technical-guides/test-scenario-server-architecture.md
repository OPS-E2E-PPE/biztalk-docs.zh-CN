---
title: 测试方案服务器体系结构 |Microsoft 文档
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49a51244b7033c6cebc978a39ad37dd5732fa38d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010846"
---
# <a name="test-scenario-server-architecture"></a>测试方案服务器体系结构
本主题概述了在负载测试期间的服务器和对其执行负载测试的不同服务器体系结构之间的消息流。  
  
## <a name="overview-of-message-flow-during-load-testing"></a>在负载测试期间的消息流的概述  
 下图提供了用于所有方案中测试和负载测试期间的服务器之间的消息流的服务器体系结构的泛型概述。  
  
> [!NOTE]  
>  本节介绍测试了每个不同的服务器体系结构**基线服务器体系结构**。  
  
 下图提供消息流的概述。 图中的数字对应于图下方列出的步骤。  
  
 ![消息流概述](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")  
“消息流”概述  
  
1.  负载测试可由负载代理控制器计算机**VSTS_TestController**:  
  
    -   上的 Visual Studio 2008 项目**VSTS_TestController**执行。 项目加载 BizUnit 类的实例，加载指定的 BizUnit XML 配置文件，并开始执行 BizUnit 配置文件中定义的步骤。  
  
        > [!NOTE]  
        >  有关使用 BizUnit 的 XML 配置文件的详细信息，请参阅主题"定义测试使用 XML 配置文件"在[http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432)。  
  
    -   完成测试安装步骤后，一个 BizUnit 项目中的步骤执行用于显示一个对话框，通过该对话框提示您以启动"需要"的测试运行以提交到需要消息的命令[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
    -   需要消息的单独的 Visual Studio 2008 测试项目中提交的**VSTS_TestController**。 需要消息将发送"预热"的测试环境初始化系统缓存。  
  
    -   处理完所有需要消息; 之后BizUnit 实例加载在主要的测试运行中进行测试的所有计算机的性能监视器计数器，并执行命令以显示一个对话框，通过该对话框提示您提交主测试运行的消息。  
  
    -   上的 Visual Studio 2008 负载测试项目**VSTS_TestController**指示要提交邮件用于主测试运行的负载测试代理计算机。  
  
2.  负载测试代理计算机提交测试消息都传送到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]负载测试控制器计算机上 Visual Studio 2008 负载测试项目的 app.config 文件中指定的计算机 (**VSTS_TestController**)。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机接收提交的负载测试代理计算机的消息，则为两种方式接收的消息已此负载测试请求-响应接收位置。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将消息发布到 MessageBox 数据库。  
  
    -   消息被使用业务流程。  
  
    -   业务流程所绑定到为双向请求作出响应发送调用下游计算器服务的端口。  
  
    > [!NOTE]  
    >  下游计算器服务基于 Windows Communication Foundation 示例中所述[http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762)。 Windows Communication Foundation 示例将可供在下载[http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352)。  
  
4.  计算器服务使用来自请求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并返回到响应[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请求作出响应发送端口。  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理响应并保存到 MessageBox 数据库响应消息。 然后从 BizTalk 请求-响应端口，MessageBox 数据库检索来自计算器 web 服务的响应消息和响应消息发送回的负载测试代理计算机。  
  
## <a name="baseline-server-architecture"></a>基线服务器体系结构  
 对于基线服务器体系结构，HYPER-V 角色未安装且两[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 安装到主机操作系统。 这样做是为了建立的"基准"性能指标[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案上的物理硬件环境。  
  
 下图描述了物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 层的基线服务器体系结构。  
  
 ![物理 BizTalk &#47;物理 SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")  
物理 BizTalk Server / 物理 SQL Server （基线）  
  
-   **BizTalk Server** -2，如下所示配置 BizTalk Server 计算机：  
  
    -   一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**6** GB 的 RAM 和**8**处理器内核可用。  
  
    -   一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**3** GB 的 RAM 和**4**处理器内核可用。  
  
    -   总的 6 + 3 = **9**可用 GB RAM 和 8 + 4 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   **SQL Server** -1，如下所示配置的 SQL Server 计算机：  
  
    -   **8** GB RAM 可。  
  
    -   **4**处理器内核可用。  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a>虚拟 BizTalk Server / 物理 SQL Server  
 下图描述了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]层。  
  
 ![虚拟 BizTalk &#47;物理 SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")  
虚拟 BizTalk Server / 物理 SQL Server  
  
 对于此方案中，针对执行负载测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机和物理硬件上运行的 SQL Server 上运行。  
  
> [!NOTE]  
>  如下所述的 RAM 和处理器内核的分配时相同对于每个非基线方案，唯一的区别是某些计算机是否有运行在 HYPER-V 虚拟机上或在物理硬件上。  
  
-   **BizTalk Server** -3[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的计算机配置，如下所示：  
  
    -   3 GB RAM 分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机具有的 3 x 3 总 = **9** GB RAM 可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    -   4 个处理器核心分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机具有的 3 x 4 总 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   **SQL Server** -1，如下所示配置的 SQL Server 计算机：  
  
    -   **8** GB RAM 可。  
  
    -   **4**处理器内核可用。  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a>虚拟 BizTalk Server / 虚拟 SQL Server  
 下图描述了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机上单独的 HYPER-V 主机计算机。  
  
 ![虚拟 BizTalk &#47;虚拟 SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")  
虚拟 BizTalk Server / 虚拟 SQL Server  
  
 对于此方案中，针对执行负载测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机上运行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在单独的 HYPER-V 主机计算机上运行 HYPER-V 虚拟机。  
  
> [!NOTE]  
>  RAM 和处理器内核用于这种情况下分配是相同的分配的内存和处理器内核**虚拟 BizTalk Server / 物理 SQL Server**方案、 唯一的区别是，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]已配置为在 HYPER-V 虚拟机，而不是物理硬件上运行。  
  
## <a name="consolidated-environment"></a>统一的环境  
 下图描述了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机合并到一台 HYPER-V 主机计算机上。  
  
 ![虚拟 BizTalk &#47;虚拟 SQL &#47;合并](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")  
统一的环境  
  
 对于此方案中，针对执行负载测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机上运行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机已在同一个 HYPER-V 主机计算机上运行。  
  
> [!NOTE]  
>  RAM 和处理器内核用于这种情况下分配是相同的分配的内存和处理器内核**虚拟 BizTalk Server / 虚拟 SQL Server**方案、 唯一的区别是，这两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机配置为在同一个 HYPER-V 主机计算机上运行。  
  
## <a name="see-also"></a>另请参阅  
 [测试方案概述](../technical-guides/test-scenario-overview.md)