---
title: 规划 BizTalk 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f337efa7b72a40c37a4cc3f42a2bd5d846923dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970950"
---
# <a name="plan-for-your-biztalk-solution"></a>规划您的 BizTalk 解决方案
主要设计目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是为了适应尽可能多的处理方案提供最大的灵活性。 由于此极大的灵活性，BizTalk 解决方案的开发人员所面临的主要挑战之一是确定如何在中提供的功能的最佳使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以最好地满足其业务需要。 规划[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以分解为不同的阶段下面进行了汇总。  
  
## <a name="scoping-the-solution"></a>范围解决方案  
  
### <a name="performance-considerations"></a>性能注意事项  
 范围在 BizTalk 解决方案时，请考虑以下：  
  
- 需要哪些适配器和/或加速器？  
  
- 在解决方案中实现业务流程要求是什么？  
  
- 文档的吞吐量要求： 解决方案的最大可承受吞吐量要求是什么？  
  
- 延迟要求： 响应能力如何解决方案需要位于要求-响应和请求-响应方案？  
  
- 如何从文档负载高峰期期间恢复解决方案？  
  
- 该解决方案的高可用性要求是什么？  
  
- 该解决方案的文档跟踪要求是什么？  
  
- 任何依赖的应用程序，如远程 Web 服务或其他系统的性能特征是什么？ 如果依赖的应用程序无法满足所需的负载与然后将相应地降级，总体系统性能。  
  
- 将 BizTalk 应用程序正在消耗与不相关的数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]？ 例如，如果 BizTalk 应用程序过多占用 SQL Server 数据库使用 SQL 适配器中的表，表有效地配置？  
  
### <a name="hardware-considerations"></a>硬件考虑事项  
 范围解决方案时创建的高级硬件关系图，包括以下：  
  
-   计算机体系结构 （如 x86、 x64 和 IA64）  
  
-   CPU 要求 （如类型、 速度、 数量、 内核数和使用超线程）  
  
-   每台计算机的 RAM 要求  
  
-   本地磁盘存储 （类型、 大小、 速度）  
  
-   SAN (存储要求： LUN; 的数字SAN 卡类型）  
  
-   网卡 (以每台计算机，100 兆位 (Mbps) 与 1 千兆比特数 (1 Gbps)。)  
  
-   如何将防火墙部署解决方案中？  
  
-   将使用网络负载平衡硬件？  
  
-   是特定计算机，其可以加入群集？  
  
-   将会使用虚拟环境涉及 Microsoft HYPER-V Server 或任何其他虚拟化产品？  
  
## <a name="planning-the-solution"></a>规划解决方案  
  
### <a name="solution-milestones-timeline"></a>解决方案里程碑时间线  
 创建具有用于完成您的 BizTalk 解决方案的特定方面的里程碑计划。 设置特定里程碑会增加解决方案的可能性及时完成。  
  
### <a name="non-microsoft-software-considerations"></a>非 Microsoft 软件注意事项  
 非 Microsoft 软件将与解决方案一起使用时，请考虑以下方法：  
  
-   确定如何软件或硬件配置要求获得。  
  
-   规划容量和大小调整，以确保该非 Microsoft 软件不会成为您的解决方案中的瓶颈。  
  
-   确定的计划安装所需的非 Microsoft 软件的操作。  
  
-   创建用于配置和优化所需的非 Microsoft 软件的操作的计划。  
  
## <a name="preparing-for-the-solution"></a>准备解决方案  
 在准备阶段中包括以下元素：  
  
### <a name="detailed-design-of-the-solution-platform"></a>解决方案平台的详细的设计  
 详细的解决方案设计便于通信，并避免假设，从而提高灵活性和所有活动的有效性。 你应完全记录以下元素：  
  
- BizTalk Server 数据库以及它们如何分布在计算机上。  
  
- BizTalk 主机设计和每个主机和其实例的说明。  
  
- 每个业务流程的说明。  
  
- 每个管道的说明。  
  
- 自定义组件，如.NET 程序集和 COM + 组件的说明。  
  
  **消息流关系图**  
  
  创建详细的消息流关系图，以帮助避免出现任何混淆或 false 的假设有关什么是应发生了状况消息处理过程。 创建消息流关系图时，应考虑以下详细信息：  
  
- 介绍了每种类型的消息的时间之前生成的所有消息都发送和已完成所有相关的处理到达的接收位置的生命周期。  
  
- 描述如何处理更改的错误情况。  
  
- 包括有关相关、 送达通知和确认详细信息。  
  
- 包括有关延迟和吞吐量的性能要求信息。  
  
  **非 Microsoft 软件的详细信息**  
  
  使用的所有非 Microsoft 软件应完整记录详细的解决方案设计的一部分。  
  
  **详细的硬件堆栈**  
  
  构建在以前创建的高级别硬件关系图上，下列硬件信息应完整记录：  
  
- Processors  
  
  -   类型  
  
  -   速度  
  
  -   核心数  
  
  -   超线程  
  
- 内存  
  
  -   Amount  
  
  -   速度  
  
  -   奇偶校验  
  
- 网络  
  
  -   网络接口卡 (Nic) 的数量  
  
  -   网络的速度  
  
- SAN  
  
  -   在每台计算机中的 SAN 卡数  
  
  -   每个计算机和目的，每个 LUN 的逻辑单元号 (Lun) 的数量  
  
  -   速度存储区域网络 (SAN) 卡  
  
  -   SAN 卡配置详细信息  
  
  -   SAN 磁盘分配，格式化和分区  
  
- 磁盘  
  
  -   每台计算机的的本地磁盘详细信息  
  
  -   格式设置为本地磁盘使用  
  
  -   分区的本地磁盘的详细信息  
  
- Cache  
  
  -   L2 缓存量  
  
  -   L3 缓存量  
  
  **详细的软件堆栈**  
  
  应记录以下的软件信息：  
  
- 特定操作系统版本、 版本和体系结构  
  
- 特定的操作系统功能  
  
- 在每台计算机上安装的特定软件  
  
- 特定驱动程序  
  
- Service Pack 和其他更新  
  
- 如果它们不同默认值，则使用的所有软件和操作系统功能的配置值  
  
## <a name="building-out-the-environment-for-the-solution"></a>构建解决方案的环境  
 有关安装的详细说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和软件要求处于[BizTalk Server 安装指南](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。
  
## <a name="see-also"></a>请参阅  
 [规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md)
