---
title: "规划 BizTalk 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 337883ce2ca3b7f28def19898930d872928a8ce4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="plan-for-your-biztalk-solution"></a>规划你的 BizTalk 解决方案
主要设计目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是尽可能容纳尽可能多的处理方案提供最大的灵活性。 由于此极大的灵活性，面对的 BizTalk 解决方案的开发人员的主要挑战之一是确定如何在中提供的功能的最佳使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为了最好地满足其业务需求。 规划[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以分解到不同的阶段下面概括了这些阶段。  
  
## <a name="scoping-the-solution"></a>作用域解决方案  
  
### <a name="performance-considerations"></a>性能注意事项  
 作用域 BizTalk 解决方案时考虑以下方面：  
  
-   需要哪些适配器和/或快捷键？  
  
-   在解决方案中实现业务流程的要求有哪些？  
  
-   文档吞吐量要求： 解决方案的最大可持续吞吐量要求是什么？  
  
-   延迟要求： 如何响应解决方案需要请求作出响应和请求-响应方案？  
  
-   从文档负载高峰期的时间段未程度恢复解决方案？  
  
-   解决方案的高可用性要求是什么？  
  
-   文档跟踪要求的解决方案有哪些？  
  
-   任何依赖的应用程序，如远程 Web 服务或其他系统的性能特征有哪些？ 如果依赖的应用程序执行不保留与所需的负载然后将相应地降低总体系统性能。  
  
-   将 BizTalk 应用程序正在消耗不相关数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]？ 例如，如果 BizTalk 应用程序过多占用 SQL Server 数据库使用 SQL 适配器的表中，表有效地配置？  
  
### <a name="hardware-considerations"></a>硬件考虑事项  
 当范围之外解决方案，创建包括以下高级硬件图示：  
  
-   计算机体系结构 （如 x86、 x64 和 IA64）  
  
-   （如类型、 速度、 数、 核心和使用超线程） 的 CPU 要求  
  
-   每台计算机的 RAM 要求  
  
-   本地磁盘存储 （类型、 大小、 速度）  
  
-   SAN (存储要求： 数 LUN;SAN 卡类型）  
  
-   网卡 (数字在每个计算机中，而不是 1 千兆比特的 100 兆位 (Mbps) (1 Gbps)。)  
  
-   如何将防火墙部署解决方案中？  
  
-   将使用网络负载平衡的硬件？  
  
-   是特定计算机其可以加入群集？  
  
-   将会使用虚拟环境涉及 Microsoft HYPER-V Server 或任何其他虚拟化产品？  
  
## <a name="planning-the-solution"></a>规划解决方案  
  
### <a name="solution-milestones-timeline"></a>解决方案里程碑时间线  
 使用用于完成你的 BizTalk 解决方案的特定方面的里程碑创建计划。 设置特定的里程碑将解决方案的可能性会增大及时完成。  
  
### <a name="non-microsoft-software-considerations"></a>非 Microsoft 软件注意事项  
 非 Microsoft 软件将与解决方案一起使用时，请考虑以下方法：  
  
-   确定如何软件或硬件配置要求才能获得。  
  
-   规划容量和调整大小以确保该非 Microsoft 软件不会成为你的解决方案中的瓶颈。  
  
-   确定用于安装所需的非 Microsoft 软件的操作的计划。  
  
-   创建配置和优化所需的非 Microsoft 软件的操作的计划。  
  
## <a name="preparing-for-the-solution"></a>准备解决方案  
 在准备阶段中包含下列元素：  
  
### <a name="detailed-design-of-the-solution-platform"></a>详细的解决方案平台的设计  
 详细的解决方案设计便于通信，并避免假设，从而提高灵活性和的所有活动的有效性。 你应完全记录以下元素：  
  
-   BizTalk Server 数据库和它们如何分布在计算机。  
  
-   BizTalk 主机设计和每个主机和其实例的说明。  
  
-   每个业务流程的说明。  
  
-   每个管道的说明。  
  
-   自定义组件，如.NET 程序集和 COM + 组件的说明。  
  
 **消息流关系图**  
  
 创建详细的消息流图，以帮助避免出现任何混淆或 false 的假设，有关什么是应该在处理期间不会发生情况的消息。 创建消息流关系图时，应考虑以下详细信息：  
  
-   描述了每种类型的消息从时间之前生成的所有消息都发送和完成所有相关的处理到达的接收位置的生命周期。  
  
-   描述如何处理更改为错误条件。  
  
-   包括有关相关、 传递通知和确认的详细信息。  
  
-   包括有关延迟和吞吐量的性能要求信息。  
  
 **非 Microsoft 软件详细信息**  
  
 使用的所有非 Microsoft 软件应完全记录详细的解决方案设计的一部分。  
  
 **详细的硬件堆栈**  
  
 在以前创建的高级硬件关系图上构建，下列硬件信息应将完全记录：  
  
-   Processors  
  
    -   类型  
  
    -   速度  
  
    -   内核数  
  
    -   超线程  
  
-   内存  
  
    -   Amount  
  
    -   速度  
  
    -   奇偶校验  
  
-   Network  
  
    -   网络接口卡 (Nic) 数  
  
    -   网络的速度  
  
-   SAN  
  
    -   每台计算机中的 SAN 卡数  
  
    -   每台计算机和每个 LUN 的用途的逻辑单元号 (Lun) 数  
  
    -   速度的存储区域网络 (SAN) 卡  
  
    -   SAN 卡配置详细信息  
  
    -   SAN 磁盘分配，格式设置，和分区  
  
-   磁盘  
  
    -   每台计算机的的本地磁盘详细信息  
  
    -   格式设置用于本地磁盘  
  
    -   分区本地磁盘的详细的信息  
  
-   Cache  
  
    -   L2 缓存量  
  
    -   L3 缓存量  
  
 **详细的软件堆栈**  
  
 应记录以下的软件信息：  
  
-   特定操作系统版本、 版本以及体系结构  
  
-   特定的操作系统功能  
  
-   每台计算机上安装的特定软件  
  
-   特定驱动程序  
  
-   Service Pack 和其他更新  
  
-   如果它们会不同于默认值所使用的所有软件和操作系统功能的配置值  
  
## <a name="building-out-the-environment-for-the-solution"></a>构建解决方案的环境  
 有关安装详细说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和软件要求处于[BizTalk Server 安装指南](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。
  
## <a name="see-also"></a>另请参阅  
 [规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md)
