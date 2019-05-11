---
title: 测量引擎的 MST 的测试方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e54667b9-7262-43c8-a013-9242eb062daf
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 071bc814964aa2502e77bd02d975c978fc02fd77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299424"
---
# <a name="test-scenarios-for-measuring-mst-of-the-engine"></a>测量引擎的 MST 的测试方案
本部分介绍用于度量在三个不同的负载级别驱动 BizTalk 系统的影响的测试方案：  
  
- [可承受负载测试](../core/sustainable-load-test.md)。 对于这些测试，可承受负载本主题中所述[可承受性能？](../core/what-is-sustainable-performance.md)。  
  
- [据以加快负载测试](../core/overdrive-load-test.md)。 Overdrive 负载定义为超过 MST 的一致负载。  
  
- [突发高负载测试](../core/floodgate-load-test.md)。 突发高负载定义为低负载超过 MST 的间歇峰值的负载。  
  
  本主题介绍测试硬件配置、 测试方案中，并讨论了每个测试的发现结果。  
  
> [!IMPORTANT]
>  读者应了解在本部分中包含的信息代表 Microsoft 对截至发布日期所讨论问题的当前观点。 因为我们必须应对不断变化的市场条件和技术，Microsoft 无法保证发布日期之后所提供的任何信息的准确性。  
  
## <a name="test-system-configuration"></a>测试系统配置  
 以下硬件用于此测试方案：  
  
- **六台 BizTalk 服务器**。 每台均配备有双 3ghz 处理器和 2 GB 的 RAM。 每个服务器均使用本地磁盘。 两台 BizTalk 服务器配置的接收主机实例、 两台配置的发送主机实例和两个配置了用于处理业务流程的主机的实例。  
  
- **一个用于主 MessageBox 数据库和非 MessageBox 数据库的 SQL Server**。 配备有八个 2ghz 处理器和 4 GB 的 RAM。 此服务器连接到通过光纤快速 SAN 磁盘子系统。 禁用消息发布。  
  
- **正在发布到 Messagebox 数据库的三个 SQL Server**。 配备有四个 2ghz 处理器和 4 GB 的 RAM。 这些服务器每个到快速 SAN 磁盘子系统通过光纤连接。 MessageBox 数据库的数据和事务日志文件位于单独的存储区域网络 (SAN) 逻辑单元号 (Lun)。  
  
- **负载驱动程序客户端计算机**。 配备有双 3ghz 处理器和 2 GB 的 RAM。 此服务器用于生成测试 BizTalk 系统的负载。  
  
  用于负载测试的拓扑如下图所示。  
  
  **用于负载测试的拓扑**  
  
  ![为 BizTalk Server 负载测试的硬件拓扑](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")  
  
## <a name="the-test-scenario"></a>测试方案  
 测试方案是非常简单。 负载生成工具 LoadGen 2007 已安装在负载驱动程序服务器上，并用于将文件的副本发送到文件适配器监视的共享。 负载生成工具在文件共享之间均匀地分发输入的文件实例的副本。  
  
> [!NOTE]
>  下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。 此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[ http://go.microsoft.com/fwlink/?linkid=108999 ](http://go.microsoft.com/fwlink/?linkid=108999)。 有关将 LoadGen 与 MSMQ 适配器的信息，请参阅[与 MSMQ 将 LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)。  
  
 BizTalk 文件适配器配置为监视文件共享并将消息发布到 MessageBox。 包含接收形状和发送形状的简单业务流程订阅已发布的消息。 文件发送端口提取和发送到公共共享，在 SAN 上定义的业务流程发布回 MessageBox 的消息。 到达的输出 SAN 共享的文件将立即删除以避免在很长的测试运行期间在该共享的文件累积。  
  
 对于该方案，其中一个每个接收位置、 业务流程、 发送端口，以及跟踪定义了四个主机。 为了观察引擎积压行为，跟踪是在中彻底关闭测试运行。 跟踪仅可用于管道和业务流程默认情况下使跟踪被显式关闭 BizTalk 管理员中的业务流程和使用的管道。  
  
 由于关闭了跟踪功能来隔离核心 MessageBox 行为对于这些测试，已不创建跟踪主机的任何实例。  
  
 用一个简单的架构，并且用于测试的实例文件是所有 10 KB 大小。 XMLReceive 管道用于入站文档和没有映射组件或出站组件使用以保持测试方案的简单和着重观察 MessageBox 的行为。  
  
## <a name="parameters-measured-in-the-test"></a>在测试中度量的参数  
 在此测试中度量的参数如下所示：  
  
 **度量的主要测试参数**  
  
 以下参数是度量 MST 时使用的主要指标：  
  
- MessageBox 积压工作由度量**后台处理大小**随附的计数器**此计数器**性能对象。 Messagebox 积压是可维持性的关键指标。 很明显，无法继续 MessageBox 积压无限增长，如果最后未出现问题。 因此，随着时间推移，监视在 MessageBox 数据库积压的深度用于计算可维持性。  
  
   名为的 MessageBox 表**spool**包含系统中的每个消息的记录 (活动或等待进行垃圾收集)。 监视此表中的行数和虽然系统负载增加提供了方便地测量的最大可承受吞吐量每秒接收的消息数。 此度量也称为**后台处理表深度**或**后台处理深度**。  
  
- 每秒由度量收到的文档数**记录了 received/Sec**随附的计数器**BizTalk： 消息传送**性能对象。  
  
  **度量的辅助测试参数**  
  
  以下参数是可以度量 MST 时计算的辅助指标。 这些参数可能会影响后台处理深度和每秒收到的文档数的主要指标。  
  
- 物理磁盘空闲时间的 MessageBox 数据和事务文件磁盘由度量 **%空闲时间**计数器适用于**逻辑磁盘使用情况**性能对象。  
  
- CPU 使用率 （%）MessageBox 服务器由度量 **%Processor Time**计数器适用于**处理器**性能对象。  
  
- 每秒锁超时在 MessageBox 数据库由度量**Lock Timeouts/sec**计数器适用于**sqlserver: Locks**性能对象。  
  
- 清除与删除的消息关联的 messagebox 表的 SQL 代理作业运行的时间以秒为单位的最新。 这通过测量**MsgBox Msg Cleanup(Purge Jobs)** 计数器适用于**此计数器**性能对象。  
  
- 以秒为单位的最新的时间运行的 SQL 代理作业用于清除与已删除的消息部分关联的 messagebox 表。 这通过测量**MsgBox 部件 Cleanup(Purge Jobs)** 计数器适用于**此计数器**性能对象。  
  
  在测试以确定最大可承受吞吐量，输入的负载将增大到点的后台处理表开始无限增长。  
  
> [!NOTE]
>  如果你不能生成足够的负载以导致后台处理表无限增长，这只是意味着您的系统的最缓慢部分位于接收端，而不是处理/发送端。  
  

## <a name="next"></a>Next
  
-   [使用 Microsoft BizTalk LoadGen 2007 工具](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)  
  
-   [可承受负载测试](../core/sustainable-load-test.md)  
  
-   [过载测试](../core/overdrive-load-test.md)  
  
-   [突发高负载测试](../core/floodgate-load-test.md)