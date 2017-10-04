---
title: "方案概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac14328d-c373-49da-a899-4b3ca7d6dc0a
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9400b85cf706efab0e70278e2c6daed0de32922b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-overview"></a>方案概述
本主题提供的完成的负载测试概述[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品组以评估的可伸缩性[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]现代企业级别的硬件上运行时。  
  
 所有测试是使用专用的硬件隔离环境中执行的。 执行超过 200 个测试运行以及是否由已验证所有结果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品组。  
  
 执行测试，使用消息传递方案和业务流程方案;这两种方案使用的 BizTalk WCF NetTcp 适配器。  
  
 若要评估的最大可能性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎，使用没有自定义管道组件和仅非常简单的业务流程用于业务流程方案。 性能优化中所述[优化性能](../technical-guides/optimizing-performance.md)已应用到环境，并完全记录在[观测结果和建议](../technical-guides/observations-and-recommendations.md)。  
  
## <a name="test-goals"></a>测试目标  
 负载测试执行的目标包括以下方面：  
  
1.  提供常规的调整大小和缩放指南[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:  
  
    1.  量化添加运行 BizTalk Server 到其他计算机的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 此测试的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案进行测量时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组已运行，运行 BizTalk Server 的两个、 三个，和四个计算机。  
  
    2.  量化的影响添加其他 BizTalk MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 此测试的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案进行测量时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组已配置为使用单个 MessageBox 数据库或四个 MessageBox 数据库。  
  
        > [!NOTE]  
        >  由于存在是什么，如果有的话，性能好处，当从一到两个 MessageBox 数据库扩展未完成测试与两个 MessageBox 数据库。 事实上，缩放一到两个 MessageBox 数据库可能会影响性能。 有关向外扩展的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息框，请参阅[缩放出 SQL Server 层](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。  
  
2.  提供以下方案的大小调整和缩放指南：  
  
    1.  WCF NetTcp 单向消息传递方案  
  
    2.  WCF NetTcp 单向 Orchestration 方案  
  
## <a name="test-measurements-used"></a>使用的测试度量值  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能进行测量使用以下条件：  
  
1.  **总体吞吐量**– 使用测量 **BizTalk： 消息传送 (*主机名*) 收到的 \Documents / Sec * * 和 **BizTalk： 消息传送 (*主机名*) \Documents 处理 / Sec * * 性能计数器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收和处理主机。  
  
2.  **CPU 使用率**– 测量与**\Processor(_Total)\\%Processor Time**性能计数器上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。 已全面审阅者所有测试结果和任何性能瓶颈中所述[观测结果和建议](../technical-guides/observations-and-recommendations.md)。  
  
## <a name="scaling-out-the-processing-tier-and-the-database-tier"></a>向外扩展处理层和数据库层  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]增加的处理层功能通过添加一个或多个可轻易地容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机连接到现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还包含通过添加 MessageBox 数据库的更高的数据库层功能。  
  
 若要提供横向扩展指标[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，测试执行与一个、 两个、 3 和 4[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 为了演示数据库层向外缩放的影响，针对单个和多 MessageBox 系统执行这些测试。  
  
## <a name="testing-scenarios"></a>测试方案  
 通过消息流的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]下面详细地介绍这些方案的环境。  
  
### <a name="messaging-test-scenario"></a>消息传送的测试方案  
 ![消息传递方案](../technical-guides/media/messagingscenario.gif "MessagingScenario")  
  
1.  正在测试的功能的 Visual Studio 2010 Ultimate edition 负载生成的 XML 消息，并将其发送到使用 NetTcp 传输运行 BizTalk Server 的计算机。  
  
    > [!NOTE]  
    >  有关 Visual Studio 2010 Ultimate edition 负载测试的详细信息，请参阅超链接""[测试应用程序](http://go.microsoft.com/fwlink/?LinkID=208247)(http://go.microsoft.com/fwlink/?LinkID=208247)。  
    >   
    >  有关如何我们使用在本测试环境中测试的功能的 Visual Studio 2010 Ultimate edition 负载的详细信息，请参阅[促进自动测试使用 Visual Studio](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)。  
  
2.  收到的 XML 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置使用 WCF NetTcp 接收适配器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置配置为使用 PassThruReceive 管道中，执行不会对消息处理。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]终结点管理器 (EPM) 将消息发布到 BizTalk MessageBox 数据库。  
  
4.  A[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送使用 WCF NetTcp 发送适配器的端口订阅接收位置所发布消息，并从 BizTalk MessageBox 中检索消息。 发送端口使用 PassThruTransmit 管道中，执行不会对消息处理。  
  
5.  消息传递到后端 WCF 服务由 WCF NetTcp 发送适配器。  
  
### <a name="orchestration-test-scenario"></a>业务流程测试方案  
 ![业务流程方案流](../technical-guides/media/orchestrationscenarioflow.gif "OrchestrationScenarioFlow")  
  
1.  正在测试的功能的 Visual Studio 2010 Ultimate edition 负载生成的 XML 消息，并将其发送到运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 NetTcp 传输。  
  
2.  收到的 XML 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收使用 WCF NetTcp 接收适配器的端口。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收端口被配置为使用 PassThruReceive，管道会执行不会对消息处理。  
  
3.  消息传递到简单的业务流程，其中仅包含接收端口 （步骤 2 中绑定到 WCF 接收端口） 和发送端口 （步骤 4 中绑定到 WCF 发送端口）。 消息变量是"非类型化"，这意味着的"System.XML.XmlDocument"的它们使用的"消息类型"。 业务流程只接收消息都通过其接收端口并通过其发送端口发送消息。 执行没有消息处理操作。  
  
4.  单向[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送使用 WCF NetTcp 发送适配器的端口订阅发布的业务流程的消息，并从 BizTalk MessageBox 中检索消息。 发送端口使用 PassThruTransmit 管道中，执行不会对消息处理。  
  
5.  消息传递到后端 WCF 服务由 WCF NetTcp 发送适配器。  
  
## <a name="hardware-configuration"></a>硬件配置  
  
### <a name="lab-hardware-diagram-and-specifications"></a>实验室祑砰瓜和规范  
 为实验室使用的硬件配置如下所示。 若要轻松地适应外的处理和数据库层的缩放，已使用以下实验室硬件：  
  
-   两个企业类 Hewlett Packard DL-380 计算机和两个企业类 Dell R710 计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理层。  
  
-   四个数据库层，以提供多 MessageBox 功能的企业类 Dell R900 计算机。  
  
 下面提供的实验室中使用的硬件的关系图：  
  
 ![性能指南基础结构](../technical-guides/media/performanceguideinfrastructure.gif "PerformanceGuideInfrastructure")  
  
 下表提供有关在实验室中使用的硬件的更具体信息。  
  
|Name|Model|CPU 类型|CPU 数|内核/CPU 数|CPU 体系结构|内存|操作系统|软件|  
|----------|-----------|--------------|--------------------|--------------------------|----------------------|------------|----------------------|--------------|  
|R710-01|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[prague](../includes/prague-md.md)]|  
|R710-02|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[prague](../includes/prague-md.md)]|  
|DL380G7-01|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[prague](../includes/prague-md.md)]|  
|DL380G7-02|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[prague](../includes/prague-md.md)]|  
|DL380-01|Hewlett Packard DL380|Intel Xeon 5150|2 x 2.66 GHz|2|x64|8 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]负载测试数据库<br /><br /> [!INCLUDE[vs2010](../includes/vs2010-md.md)]<br /><br /> WCF 后端服务|  
|DL380-02|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 g h z|4|x64|8 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[vs2010](../includes/vs2010-md.md)]负载测试控制器|  
|DL380 03|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 g h z|4|x64|8 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[vs2010](../includes/vs2010-md.md)]负载测试代理|  
|DL380 04|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 g h z|4|x64|8 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[vs2010](../includes/vs2010-md.md)]负载测试代理。<br /><br /> Perfmon 命令行|  
|R805 06|Dell PowerEdge R805|AMD 个四核 Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[vs2010](../includes/vs2010-md.md)]负载测试代理|  
|R805-07|Dell PowerEdge R805|AMD 个四核 Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[vs2010](../includes/vs2010-md.md)]负载测试代理|  
|R900 03|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]带累积更新 4|  
|R900 04|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]带累积更新 4|  
|R900-05|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]带累积更新 4|  
|R900 06|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Enterprise Edition|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]带累积更新 4|  
  
### <a name="storage-area-network-configuration"></a>存储区域网络配置  
 下图描绘了存储区域网络 (SAN) 配置用于实验室环境。  
  
 ![SAN 信息](../technical-guides/media/saninformation.gif "SANinformation")  
  
### <a name="emc-clariion-cx4-960-san-configuration"></a>EMC CLARiiON CX4 960 SAN 配置  
  
|服务处理器和缓存信息|LUN 配置|  
|---------------------------------------------|-----------------------|  
|两个服务处理器，每个都有：<br /><br /> -读取缓存大小： 2000 MB。<br />-写缓存大小： 8000 MB。<br />的连接到纤程交换机两个前端端口。 每个端口的 4 Gbps。|-64 个磁盘 (268 GB，15k RPM，光纤通道 Seagate。<br />-八个 8 磁盘 RAID 1 + 0 组划分从这些 64 个磁盘。<br />-每个 DB 服务器分配 5 Metalun 均匀地从这些 RAID 组配置。|  
  
 请务必确定 SAN 的最大可达成吞吐量并将该值设置为针对在生产 SAN 的预期负载进行比较。 这将有助于防止意外的 SAN 相关硬件支出，在将你的应用程序的测试/质量保证 (QA) 环境移动到生产环境时。 例如，为 SAN 可用吞吐量最大可能足以多个应用程序在沙盒测试环境。 但是，如果其他服务器应用程序将在生产中使用 SAN，可用 SAN 吞吐量可能不足，并且可能成为瓶颈。  
  
 评估性能的 SAN 时，考虑以下方面：  
  
1.  **什么是 SAN 的最大可达成吞吐量？** -这是使用最低的公用标准，在吞吐量，主机总线适配器 (HBA) 中的服务器、 交换机 SAN 吞吐量和 SAN 控制器卡的速度方面进行测量。  
  
2.  **哪些其他应用程序将在生产中使用 SAN？** – 请考虑什么其他应用程序将使用 SAN 在生产环境中。 如果其他数据库或否则为 I/O 密集型应用程序如 Exchange Server 将使用 SAN 在生产中，可用于运行的计算机的 SAN 吞吐量量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将相应地降低。  
  
 为实验室环境中，使用专用的 SAN。 每个四个 SQL Server 计算机已连接到 SAN 交换机具有两个 4 Gbps 主机总线适配器 (Hba)，提供每个服务器的 8 Gbps 的总潜在吞吐量。 SAN 具有两个服务处理器，且每个服务处理器必须连接到纤程交换机，提供 16-Gbps SAN 交换机之间的总体潜在吞吐量的两个前端端口。  
  
 下面的 LUN 配置为每个四个在测试环境中运行 SQL Server 的计算机使用。  
  
|驱动器号|卷名|文件|LUN 的大小 (GB)|  
|------------------|-----------------|-----------|---------------------|  
|C|本地 C 驱动器|MASTER、 MSDB 和模型|136|  
|H|Data_Tempdb|TempDB 数据文件|50|  
|I|Logs_Tempdb|TempDB 日志文件|50|  
|J|Data_BtsMsgBox|BizTalk MsgBoxDB 数据文件和 （在 Master MsgBox 中) 上管理数据库，SSO DB DTA 数据库数据文件|120|  
|K|Logs_BtsMsgBox|BizTalk MsgBoxDB 日志文件和 （在 Master MsgBox 中) 上管理数据库、 SSO 数据库、 DTA 数据库日志文件|120|  
|O|Logs_Spare|不用于 SQL 文件。 用于存储 DTCLog 文件，因为 MSDTC 导致频繁的磁盘 I/O，特别是在多 MessageBox 环境。|20|  
  
### <a name="sqlio-test-results"></a>SQLIO 测试结果  
 我们使用 SQLIO 工具来进行基准测试，并考虑在本实验室环境中使用的存储区域网络 (SAN) 配置的输入/输出容量。 该工具的名称可以看出，SQLIO 是用于测量的文件系统 I/O 对 SQL Server 性能的影响的重要工具。 可以从下载 SQLIO [http://go.microsoft.com/fwlink/?LinkID=210381](http://go.microsoft.com/fwlink/?LinkID=210381)。   
若要度量的存储区域网络 (SAN) 配置 SQL Server 数据库应用程序的输入/输出容量，请参阅[分析 I/O 特性和用于 SQL Server 数据库应用程序的大小调整存储系统](http://go.microsoft.com/fwlink/?LinkID=210379)(http://go.microsoft.com/fwlink/？LinkID = 210379)。  
  
 对于我们 SQLIO 测试，sqlio.exe 实用工具问题 8k 从 8 个线程读取请求和维护的 8 的 I/O 队列深度。 我们使用以下参数：  
  
-   所有测试都使用 8 个处理线程，每个运行状态，为 60 秒。  
  
-   8 kb 随机写入的数据文件。  
  
-   8 kb 随机读取数据到数据文件。  
  
-   所有文件大小将都调整为 25 GB。  
  
-   若要将基准检查的磁盘驱动器是 h:、 i:、 j:，和 K 驱动器。  
  
 使用的 SQLIO 命令行是如下所示：  
  
-   **读取的**: sqlio kR-s60 frandom-o8-t8-b8 LS-FParam.txt  
  
-   **对于写入**: sqlio-kW-s60 frandom-o8-t8-b8 LS-FParam.txt  
  
 Param.txt 文件包含以下项目：  
  
-   **驱动器数：** h:、 i:、 j:，和 K  
  
-   **测试文件的物理位置**:  
  
    -   H:\testfile.dat 2 0x0 25000  
  
    -   I:\testfile.dat 2 0x0 25000  
  
    -   J:\testfile.dat 2 0x0 25000  
  
    -   K:\testfile.dat 2 0x0 25000  
  
 下表列出的测试结果：  
  
-   8 KB 随机读取同时在 Lun h:，i:，j:，k: (用于我们的数据库文件的所有 Lun) 上的 25 GB 测试文件中  
  
    ###  
  
    |每秒 （Io 数/秒） 的输入/输出操作|兆字节每秒 （Mb/秒）|平均延迟|  
    |------------------------------------------------------|---------------------------------------|---------------------|  
    |10662.67|83.30|5 毫秒|  
  
-   8 KB 随机写入 25 GB 测试文件，同时对 Lun h:，i:，j:，k (用于我们的数据库文件的所有 Lun):  
  
    ###  
  
    |每秒 （Io 数/秒） 的输入/输出操作|兆字节每秒 （Mb/秒）|平均延迟|  
    |------------------------------------------------------|---------------------------------------|---------------------|  
    |31527.95|246.31|1 ms|  
  
## <a name="see-also"></a>另请参阅  
 [缩放生产 BizTalk Server 环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)