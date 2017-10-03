---
title: "阶段 3： 准备评估 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 890047f6a13352d89d33d9514883dc20eacd4001
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="phase-3-preparing-for-the-assessment"></a>阶段 3： 准备评估
性能评估阶段可以被想象成审视阶段的"如何""怎么"和计划阶段的准备工作的"何时。" 此时在性能评估中，所有利益干系人应具有达成一致后用户参与策略和计划的范围进行试验室。 它是在其中执行计划和执行任何步骤以获取已准备好的性能实验室的执行性能评估的准备阶段。  
  
 本主题介绍将 BizTalk Server 性能评估的准备阶段的各个方面。  
  
## <a name="detailed-design-of-the-solution-platform"></a>详细的解决方案平台的设计  
 详细的解决方案设计便于通信，并避免假设，从而提高灵活性和的所有活动的有效性。 你应完全记录以下元素：  
  
-   **BizTalk Server 数据库以及它们如何分布跨计算机**-SQL Server 性能是整体 BizTalk Server 性能的关键因素之一。 如果 SQL Server 遇到资源约束，这将影响的 BizTalk Server 来处理消息的能力。 影响 BizTalk 数据库性能的主要因素是磁盘上托管的速度。 为每个 BizTalk 分隔的事务日志和数据库文件已对数据库分别放在不同的驱动器或 SAN LUN 被证实将大大提高 BizTalk Server 的整体性能。 因此，很重要，可以轻松进行访问的方式记录此信息。 将在生产环境中使用的值应记录详细的解决方案设计中。 下表提供了如何完成此操作的示例。  
  
    |BizTalk 数据库|卷名|文件|LUN # 或 ML_ #|物理 LUN 的大小 (GB)|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |MessageBox|Data_TempDb_1|TEMPDB、 MASTER 和 MSDB 数据文件|1|134|  
    ||Logs_TempDb_1|TEMPDB、 MASTER 和 MSDB 事务日志文件|2|134|  
    ||Data_BtsMsgBox|BizTalkMsgBoxDb 数据文件|3|134|  
    ||Logs_BtsMsgBox|BizTalkMsgBoxDb 事务日志文件|4|134|  
    |BAM|Data_TempDb_2|TEMPDB、 MASTER 和 MSDB 数据文件|5|67|  
    ||Logs_TempDb_2|TEMPDB、 MASTER 和 MSDB 事务日志文件|6|67|  
    ||Data_BAM|BAMPrimaryImport 数据文件|7|134|  
    ||Logs_BAM|BAMPrimaryImport 事务日志文件|8|134|  
    |BizTalk 跟踪、 管理、 单一登录，和规则引擎的数据库|Data_TempDb_3|TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 数据文件|9|67|  
    ||Logs_TempDb_3|TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 事务日志文件|10|67|  
  
-   **BizTalk 主机设计和每个主机和其实例的说明。**  
  
-   **每个业务流程的说明。**  
  
-   **每个管道的说明。**  
  
-   **自定义组件，如.NET 程序集和 COM + 组件的说明。**  
  
## <a name="detailed-architecture-diagram"></a>详细体系结构关系图  
 下图说明了可用于性能评估的体系结构关系图。  
  
 ![BizTalk 体系结构关系图](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")  
BizTalk 体系结构关系图  
  
## <a name="message-flow-diagrams"></a>消息流关系图  
 创建详细的消息流图，以帮助防止混淆或 false 的假设，有关什么是应该在处理期间不会发生情况的消息。  
  
 在整体考虑 BizTalk 解决方案，我们通常认为消息流经系统。 执行测试，因为流的所有部分都必须被都视为潜在瓶颈的性能时，此消息流透视一点尤其重要。 让消息流图阻止任何混淆或有关什么是应该在每个测试期间不会发生情况的消息错误的假定运行。  
  
 在以下示例中，使用简单 Visio 形状，创建与背景无关项目中的每个人都可以快速了解一条消息如何获取到系统、 解决方案的哪些部分消息、 交互和最后消息便之后的位置处理。  
  
 ![消息流图](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")  
消息流关系图  
  
 创建消息流关系图时，应考虑以下详细信息：  
  
-   描述了每种类型的消息从时间之前生成的所有消息都发送和完成所有相关的处理到达的接收位置的生命周期。  
  
-   描述如何处理更改为错误条件。  
  
-   包括有关相关、 传递通知和确认的详细信息。  
  
-   包括有关依赖于外部系统的详细信息。  
  
-   包括有关延迟和吞吐量的性能要求信息。  
  
## <a name="third-party-software-details"></a>第三方软件详细信息  
 使用的所有非 Microsoft 软件应完全记录详细的解决方案设计的一部分。  
  
## <a name="detailed-lab-hardware-stack"></a>详细的实验室硬件堆栈  
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
  
## <a name="detailed-lab-software-stack"></a>详细的实验室软件堆栈  
 应记录以下的软件信息：  
  
-   特定操作系统版本、 版本以及体系结构  
  
-   特定的操作系统功能  
  
-   每台计算机上安装的特定软件  
  
-   特定驱动程序  
  
-   Service Pack 和其他更新  
  
-   如果它们会不同于默认值所使用的所有软件和操作系统功能的配置值  
  
## <a name="see-also"></a>另请参阅  
 [性能评估阶段](../technical-guides/phases-of-a-performance-assessment.md)