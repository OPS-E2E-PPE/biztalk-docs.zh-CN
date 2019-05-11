---
title: 测试方案服务器体系结构 |Microsoft Docs
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
ms.openlocfilehash: 4394ab90c9a20ebb081f5d8844a2ad727ac1c71b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301649"
---
# <a name="test-scenario-server-architecture"></a>测试方案服务器体系结构
本主题提供了在负载测试期间的服务器和对其执行负载测试的不同的服务器体系结构之间的消息流的概览。  
  
## <a name="overview-of-message-flow-during-load-testing"></a>在负载测试期间的消息流的概览  
 下图提供了用于所有测试方案和负载测试期间的服务器之间的消息流的服务器体系结构的一般概述。  
  
> [!NOTE]  
>  部分中描述进行了测试每个不同的服务器体系结构**基线服务器体系结构**。  
  
 下图提供消息流的概述。 在图中的数字对应于图下方列出的步骤。  
  
 ![消息流概述](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")  
消息流概述  
  
1. 负载测试的负载代理控制器计算机启动**VSTS_TestController**:  
  
   - 上的 Visual Studio 2008 项目**VSTS_TestController**执行。 项目加载 BizUnit 类的实例、 加载指定的 BizUnit XML 配置文件，并开始执行 BizUnit 配置文件中定义的步骤。  
  
     > [!NOTE]  
     >  有关使用 BizUnit 的 XML 配置文件的详细信息，请参见主题"定义测试使用 XML 配置文件"网址[ http://go.microsoft.com/fwlink/?LinkId=143432 ](http://go.microsoft.com/fwlink/?LinkId=143432)。  
  
   - 完成测试设置步骤后，BizUnit 项目中的步骤之一执行命令，将显示一个对话框，提示您启动"基本"测试运行需要将消息提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
   - 基本消息从一个单独的 Visual Studio 2008 测试项目上提交**VSTS_TestController**。 基本消息将发送"预热"的测试环境通过初始化系统缓存。  
  
   - 处理完所有基本消息; 之后BizUnit 实例加载所测试主要的测试运行中的所有计算机的性能监视器计数器，并执行命令，可以显示一个对话框，提示您将消息提交以主测试运行。  
  
   - 上的 Visual Studio 2008 负载测试项目**VSTS_TestController**指示要将消息提交以主测试运行的负载测试代理计算机。  
  
2. 向负载测试代理计算机提交测试消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]负载测试控制器计算机上 Visual Studio 2008 负载测试项目的 app.config 文件中指定的计算机 (**VSTS_TestController**)。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机接收提交的负载测试代理计算机的消息，消息通过两种方式接收到此负载测试请求-响应接收位置。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将消息发布到 MessageBox 数据库。  
  
   - 消息被供业务流程。  
  
   - 业务流程绑定到双向要求响应发送端口调用下游计算器服务。  
  
   > [!NOTE]  
   >  下游计算器服务基于 Windows Communication Foundation 示例中所述[ http://go.microsoft.com/fwlink/?LinkId=141762 ](http://go.microsoft.com/fwlink/?LinkId=141762)。 Windows Communication Foundation 示例都可在下载[ http://go.microsoft.com/fwlink/?LinkId=87352 ](http://go.microsoft.com/fwlink/?LinkId=87352)。  
  
4. 计算器服务消耗的请求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并将响应返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求响应发送端口。  
  
5. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理的响应，并保存到 MessageBox 数据库的响应消息。 然后从 BizTalk 请求-响应端口，通过 MessageBox 数据库中检索来自计算器 web 服务的响应消息并将响应的消息传递回的负载测试代理计算机。  
  
## <a name="baseline-server-architecture"></a>基本服务器体系结构  
 基准服务器体系结构中，HYPER-V 角色未安装且两[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 安装到主机操作系统。 这样做是为了建立的"基准"性能指标[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的物理硬件环境的解决方案。  
  
 下图描绘了物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和基线服务器体系结构的 SQL Server 层。  
  
 ![物理 BizTalk&#47;物理 SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")  
物理 BizTalk 服务器 / 物理 SQL 服务器 （基线）  
  
- **BizTalk Server** – 2 个 BizTalk Server 计算机配置，如下所示：  
  
  - 一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**6** GB RAM 和**8**可用的处理器内核。  
  
  - 一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**3** GB RAM 和**4**可用的处理器内核。  
  
  - 总数为 6 + 3 = **9**可用 GB RAM 和 8 + 4 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- **SQL Server** -1，如下所示配置的 SQL Server 计算机：  
  
  -   **8**可用 GB RAM。  
  
  -   **4**可用的处理器内核。  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a>虚拟 BizTalk 服务器 / 物理 SQL 服务器  
 下图描绘了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]层。  
  
 ![虚拟 BizTalk&#47;物理 SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")  
虚拟 BizTalk 服务器 / 物理 SQL 服务器  
  
 对于此方案中，负载测试已执行针对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的 HYPER-V 虚拟机和物理硬件上运行的 SQL Server 上运行。  
  
> [!NOTE]  
>  如下所述的 RAM 和处理器核心的分配时完全相同的每个非基线方案中，唯一的差别是某些计算机是否正在运行的 HYPER-V 虚拟机上或在物理硬件上。  
  
- **BizTalk Server** -3[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的计算机配置，如下所示：  
  
  - 3GB RAM 分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机总容量为 3 x 3 = **9** GB RAM 可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
  - 4 个处理器核心分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机总容量为 3 x 4 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- **SQL Server** -1，如下所示配置的 SQL Server 计算机：  
  
  -   **8**可用 GB RAM。  
  
  -   **4**可用的处理器内核。  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a>虚拟 BizTalk 服务器 / 虚拟 SQL Server  
 下图描绘了一个虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机上单独的 HYPER-V 主机计算机。  
  
 ![虚拟 BizTalk&#47;虚拟 SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")  
虚拟 BizTalk 服务器 / 虚拟 SQL Server  
  
 对于此方案中，负载测试已执行针对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机上运行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]独立的 HYPER-V 主机计算机上运行的 HYPER-V 虚拟机。  
  
> [!NOTE]
>  分配的 RAM 和处理器核心，以这种情况下是相同的分配的内存和处理器核心**虚拟 BizTalk 服务器 / 物理 SQL Server**方案中，唯一的差别是，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]是配置为在 HYPER-V 虚拟机而非物理硬件上运行。  
  
## <a name="consolidated-environment"></a>统一的环境  
 下图描绘了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机合并到一台 HYPER-V 主机计算机上。  
  
 ![虚拟 BizTalk&#47;虚拟 SQL&#47;合并](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")  
统一的环境  
  
 对于此方案中，负载测试已执行针对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机上运行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机在同一台 HYPER-V 主机计算机上运行。  
  
> [!NOTE]
>  分配的 RAM 和处理器核心，以这种情况下是相同的分配的内存和处理器核心**虚拟 BizTalk 服务器 / 虚拟 SQL Server**方案，唯一的差别是，这两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机已配置为在同一台 HYPER-V 主机计算机上运行。  
  
## <a name="see-also"></a>请参阅  
 [测试方案概述](../technical-guides/test-scenario-overview.md)