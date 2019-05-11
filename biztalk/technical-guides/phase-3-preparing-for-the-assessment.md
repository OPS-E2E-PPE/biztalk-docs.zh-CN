---
title: 阶段 3:评估准备 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9df65cbac6b612db6faa979cd2ff57d1a53bd83f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399591"
---
# <a name="phase-3-preparing-for-the-assessment"></a>阶段 3:评估准备
准备性能评估阶段可以认为的"如何"审视阶段的"what"和计划阶段的"when"。 此时在性能评估中，所有利益相关者应具有达成一致后执行实验室 engagement 和计划的范围。 它是在其中执行计划并采取步骤来获取已准备好的性能实验室执行的性能评估的准备阶段。  
  
 本主题介绍 BizTalk Server 性能评估的准备阶段的各个方面。  
  
## <a name="detailed-design-of-the-solution-platform"></a>解决方案平台的详细的设计  
 详细的解决方案设计便于通信，并避免假设，从而提高灵活性和所有活动的有效性。 你应完全记录以下元素：  
  
-   **BizTalk Server 数据库和它们如何分布在计算机**-SQL Server 的性能是在 BizTalk 服务器的总体性能的关键因素之一。 如果 SQL Server 遇到资源限制，这会影响 BizTalk server 处理消息的功能。 会影响 BizTalk 数据库性能的主要因素是托管的磁盘的速度。 将事务日志和数据库文件分开的每个 BizTalk 数据库分别放在不同的驱动器或 SAN LUN 已证实非常改进 BizTalk Server 的整体性能。 因此，很重要，可以轻松进行访问的方式记录此信息。 将在生产环境中使用的值应记录在详细的解决方案设计。 下表提供了如何执行此操作的示例。  
  
    |BizTalk 数据库|卷名|文件|LUN # 或 ML_ #|物理 LUN 的大小 (GB)|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |MessageBox|Data_TempDb_1|TEMPDB 和 MASTER、 MSDB 数据文件|1|134|  
    ||Logs_TempDb_1|TEMPDB、 MASTER 和 MSDB 事务日志文件|2|134|  
    ||Data_BtsMsgBox|BizTalkMsgBoxDb 数据文件|3|134|  
    ||Logs_BtsMsgBox|BizTalkMsgBoxDb 事务日志文件|4|134|  
    |BAM|Data_TempDb_2|TEMPDB 和 MASTER、 MSDB 数据文件|5|67|  
    ||Logs_TempDb_2|TEMPDB、 MASTER 和 MSDB 事务日志文件|6|67|  
    ||Data_BAM|BAMPrimaryImport 数据文件|7|134|  
    ||Logs_BAM|BAMPrimaryImport 事务日志文件|8|134|  
    |BizTalk 跟踪、 管理、 单一登录，和规则引擎数据库|Data_TempDb_3|TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 数据文件|9|67|  
    ||Logs_TempDb_3|TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 事务日志文件|10|67|  
  
-   **BizTalk 主机设计和每个主机和其实例的说明。**  
  
-   **每个业务流程的说明。**  
  
-   **每个管道的说明。**  
  
-   **自定义组件，如.NET 程序集和 COM + 组件的说明。**  
  
## <a name="detailed-architecture-diagram"></a>详细的体系结构关系图  
 下图说明了可用于性能评估体系结构关系图。  
  
 ![BizTalk 体系结构关系图](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")  
BizTalk 体系结构关系图  
  
## <a name="message-flow-diagrams"></a>消息流关系图  
 创建详细的消息流关系图，以帮助防止混淆或 false 的假设有关什么是应发生了状况消息处理过程。  
  
 时全面考虑 BizTalk 解决方案，我们倾向于将整个系统的消息流。 执行性能测试，因为流的所有部分必须都视为潜在的瓶颈时，此消息流角度来看是尤为重要。 具有消息流关系图是为了防止任何混淆或错误的假设有关什么是应发生了状况消息在每个测试期间运行。  
  
 在以下示例中，创建使用简单的 Visio 形状，而不考虑背景项目中的每个人都可以快速了解到系统获取一条消息的方式、 解决方案的哪些部分进行交互并显示消息，以及最后其中消息进入后正在处理。  
  
 ![消息流关系图](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")  
消息流关系图  
  
 创建消息流关系图时，应考虑以下详细信息：  
  
-   介绍了每种类型的消息的时间之前生成的所有消息都发送和已完成所有相关的处理到达的接收位置的生命周期。  
  
-   描述如何处理更改的错误情况。  
  
-   包括有关相关、 送达通知和确认详细信息。  
  
-   包括有关依赖于外部系统的详细信息。  
  
-   包括有关延迟和吞吐量的性能要求信息。  
  
## <a name="third-party-software-details"></a>第三方软件的详细信息  
 使用的所有非 Microsoft 软件应完整记录详细的解决方案设计的一部分。  
  
## <a name="detailed-lab-hardware-stack"></a>详细的实验室硬件堆栈  
 构建在以前创建的高级硬件关系图上，下列硬件信息应完整记录：  
  
-   Processors  
  
    -   类型  
  
    -   速度  
  
    -   核心数  
  
    -   超线程  
  
-   内存  
  
    -   Amount  
  
    -   速度  
  
    -   奇偶校验  
  
-   网络  
  
    -   网络接口卡 (Nic) 的数量  
  
    -   网络的速度  
  
-   SAN  
  
    -   在每台计算机中的 SAN 卡数  
  
    -   每个计算机和目的，每个 LUN 的逻辑单元号 (Lun) 的数量  
  
    -   速度存储区域网络 (SAN) 卡  
  
    -   SAN 卡配置详细信息  
  
    -   SAN 磁盘分配，格式化和分区  
  
-   磁盘  
  
    -   每台计算机的的本地磁盘详细信息  
  
    -   格式设置为本地磁盘使用  
  
    -   分区的本地磁盘的详细信息  
  
-   Cache  
  
    -   L2 缓存量  
  
    -   L3 缓存量  
  
## <a name="detailed-lab-software-stack"></a>详细的实验室软件堆栈  
 应记录以下的软件信息：  
  
-   特定操作系统版本、 版本和体系结构  
  
-   特定的操作系统功能  
  
-   在每台计算机上安装的特定软件  
  
-   特定驱动程序  
  
-   Service Pack 和其他更新  
  
-   如果它们不同默认值，则使用的所有软件和操作系统功能的配置值  
  
## <a name="see-also"></a>请参阅  
 [性能评估阶段](../technical-guides/phases-of-a-performance-assessment.md)