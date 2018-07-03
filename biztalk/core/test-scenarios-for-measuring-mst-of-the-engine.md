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
ms.openlocfilehash: 4fe9fd977563553e62d10675ee35caa673cf0c8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998918"
---
# <a name="test-scenarios-for-measuring-mst-of-the-engine"></a>测量引擎的 MST 的测试方案
本部分介绍的测试方案用于度量在三个不同负载级别上驱动 BizTalk 系统的效果：  
  
- [可承受负载测试](../core/sustainable-load-test.md)。 对于这些测试，可承受负载本主题中所述[可承受性能？](../core/what-is-sustainable-performance.md)。  
  
- [据以加快负载测试](../core/overdrive-load-test.md)。 Overdrive 负载定义为超过 MST 的一致负载。  
  
- [突发高负载测试](../core/floodgate-load-test.md)。 突发高负载定义为低负载超过 MST 的间歇峰值的负载。  
  
  本主题介绍了测试硬件配置、测试方案，并讨论了所有这些测试的结果。  
  
> [!IMPORTANT]
>  读者应了解本部分所包含的信息代表了 Microsoft 对讨论的数据发布问题的当前观点。 由于我们必须对市场条件和技术的更改作出响应，所以 Microsoft 无法确保数据发布后的所有信息的准确性。  
  
## <a name="test-system-configuration"></a>测试系统配置  
 以下硬件将用于此测试方案：  
  
- **六台 BizTalk 服务器**。 每台均配备有双 3GHz 处理器和 2GB RAM。 每台服务器均使用本地磁盘。 两台配置了接收主机实例的 BizTalk Server 服务器、两台配置了发送主机实例的 BizTalk Server 服务器、以及两台配置了用于处理业务流程的主机实例的 BizTalk Server 服务器。  
  
- **一个用于主 MessageBox 数据库和非 MessageBox 数据库的 SQL Server**。 配备有八个 2GHz 处理器和 4 GB RAM。 此服务器通过光纤连接到快速 SAN 磁盘子系统。 禁用消息发布。  
  
- **正在发布到 Messagebox 数据库的三个 SQL Server**。 配备有四个 2GHz 处理器和 4GB RAM。 这些服务器全部通过光纤连接到快速 SAN 磁盘子系统。 MessageBox 数据库的数据和事务日志文件位于单独的存储区域网络 (SAN) 逻辑单位号 (LUN) 上。  
  
- **负载驱动程序客户端计算机**。 配备有双 3GHz 处理器和 2GB RAM。 此服务器用于生成测试 BizTalk 系统的负载。  
  
  下面是用于负载测试的拓扑。  
  
  **用于负载测试的拓扑**  
  
  ![为 BizTalk Server 负载测试的硬件拓扑](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")  
  
## <a name="the-test-scenario"></a>测试方案  
 测试方案非常简单。 负载生成工具 LoadGen 2007 安装在负载驱动程序服务器上，并用于向文件适配器监视的共享位置发送文件副本。 负载生成工具在各个文件共享位置之间均衡地分发输入文件实例的副本。  
  
> [!NOTE]
>  下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。 此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[ http://go.microsoft.com/fwlink/?linkid=108999 ](http://go.microsoft.com/fwlink/?linkid=108999)。 有关将 LoadGen 与 MSMQ 适配器的信息，请参阅[与 MSMQ 将 LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)。  
  
 BizTalk 文件适配器配置为监视文件共享，并将消息发布到 MessageBox 中。 只包含一个接收形状和一个发送形状的简单业务流程将订阅所发布的消息。 由业务流程发布回 MessageBox 中的消息将由文件发送端口提取出来，并发送到 SAN 上定义的公用共享位置。 到达输出 SAN 共享位置的文件将立即删除，这是为了避免在长期运行测试期间，文件在该共享位置发生累积。  
  
 该方案定义了四个主机，一个用于接收位置，一个用于业务流程，一个用于发送端口，一个用于跟踪。 为了观察引擎积压行为，在测试运行期间将完全关闭跟踪功能。 默认情况下，只对管道和业务流程启用跟踪功能，因此对于所使用的业务流程和管道，需要在 BizTalk 管理器中将跟踪显式关闭。  
  
 由于关闭了跟踪功能以对这些测试隔离核心 MessageBox 行为，因此没有创建任何跟踪主机实例。  
  
 使用简单架构，并且用于测试的实例文件的大小均为 10KB。 XMLReceive 管道用于入站文档，并且没有使用任何映射组件或出站组件，以便保持测试方案的简单性和着重观察 MessageBox 的行为。  
  
## <a name="parameters-measured-in-the-test"></a>测试中度量的参数  
 下面是在此测试中度量的参数：  
  
 **度量的主要测试参数**  
  
 以下参数是度量 MST 时使用的主要指标：  
  
- MessageBox 积压工作由度量**后台处理大小**随附的计数器**此计数器**性能对象。 Messagebox 积压是可维持性的关键指标。 显然，如果最后未出现问题，则 MessageBox 积压将不会继续无限地增长。 因此，MessageBox 数据库积压的深度（随时间进行监视）可用于计算可维持性。  
  
   名为的 MessageBox 表**spool**包含系统中的每个消息的记录 (活动或等待进行垃圾收集)。 通过在系统负载增加的同时对此表中的行数以及每秒收到的消息数进行监视，可以很容易地对最大可承受吞吐量进行度量。 此度量也称为**后台处理表深度**或**后台处理深度**。  
  
- 每秒由度量收到的文档数**记录了 received/Sec**随附的计数器**BizTalk： 消息传送**性能对象。  
  
  **度量的辅助测试参数**  
  
  以下参数是可在度量 MST 时计算的辅助指标。 这些参数可能会影响后台处理深度的主要指标，以及每秒收到的文档数。  
  
- 物理磁盘空闲时间的 MessageBox 数据和事务文件磁盘由度量 **%空闲时间**计数器适用于**逻辑磁盘使用情况**性能对象。  
  
- CPU 使用率 （%） MessageBox 服务器由度量 **%Processor Time**计数器适用于**处理器**性能对象。  
  
- 每秒锁超时在 MessageBox 数据库由度量**Lock Timeouts/sec**计数器适用于**sqlserver: Locks**性能对象。  
  
- 最近运行 SQL 代理作业的时间（秒），该作业用于清除与删除的消息关联的 MessageBox 表。 这通过测量**MsgBox Msg Cleanup(Purge Jobs)** 计数器适用于**此计数器**性能对象。  
  
- 最近运行 SQL 代理作业的时间（秒），该作业用于清除与删除消息的各部分关联的 MessageBox 表。 这通过测量**MsgBox 部件 Cleanup(Purge Jobs)** 计数器适用于**此计数器**性能对象。  
  
  在测试以确定最大可承受吞吐量时，输入负载将增大到后台处理表开始无限增长的点上。  
  
> [!NOTE]
>  如果无法生成足够大的负载以导致后台处理表无限增长，则只表示系统的最缓慢部分在接收端，而不是在处理/发送端。  
  

## <a name="next"></a>Next
  
-   [使用 Microsoft BizTalk LoadGen 2007 工具](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)  
  
-   [可承受负载测试](../core/sustainable-load-test.md)  
  
-   [过载测试](../core/overdrive-load-test.md)  
  
-   [突发高负载测试](../core/floodgate-load-test.md)