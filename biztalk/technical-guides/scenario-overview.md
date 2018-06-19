---
title: 方案概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac14328d-c373-49da-a899-4b3ca7d6dc0a
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab36aa51d2dd28651895818caa781c49bf366f50
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "26010094"
---
# <a name="scenario-overview"></a>方案概述
本主题提供的负载测试已完成的 BizTalk Server 概述产品组以在现代企业级别的硬件上运行时评估 BizTalk 服务器的可伸缩性。  
  
 所有测试是使用专用的硬件隔离环境中执行的。 执行超过 200 个测试运行和所有结果已都验证由 BizTalk Server 产品组。  
  
 执行测试，使用消息传递方案和业务流程方案;这两种方案使用的 BizTalk WCF NetTcp 适配器。  
  
 若要评估的 BizTalk Server 引擎可能的最大性能，使用没有自定义管道组件;和仅非常简单的业务流程用于业务流程方案。 性能优化中所述[优化性能](../technical-guides/optimizing-performance.md)已应用到环境，并完全记录在[观测结果和建议](../technical-guides/observations-and-recommendations.md)。  
  
## <a name="test-goals"></a>测试目标  
 负载测试执行的目标包括以下方面：  
  
1.  提供常规的调整大小和缩放 BizTalk Server 的指南：  
  
    1.  量化将其他计算机添加到 BizTalk Server 组的影响。 对此测试，BizTalk Server 解决方案的性能进行测量 BizTalk Server 组运行，运行 BizTalk Server 的两个、 三个，和四个计算机时。  
  
    2.  量化将其他 BizTalk MessageBox 数据库添加到 BizTalk Server 组的影响。 对此测试，BizTalk Server 解决方案的性能进行测量组已配置为使用单个 MessageBox 数据库或四个 MessageBox 数据库时。  
  
        > [!NOTE]  
        >  由于存在是什么，如果有的话，性能好处，当从一到两个 MessageBox 数据库扩展未完成测试与两个 MessageBox 数据库。 事实上，缩放一到两个 MessageBox 数据库可能会影响性能。 有关横向扩展 MessageBox 的详细信息，请参阅[缩放出 SQL Server 层](../core/scaling-up-the-sql-server-tier.md)。
  
2.  提供以下方案的大小调整和缩放指南：  
  
    1.  WCF NetTcp 单向消息传递方案  
  
    2.  WCF NetTcp 单向 Orchestration 方案  
  
## <a name="test-measurements-used"></a>使用的测试度量值  
BizTalk Server 性能进行测量使用以下条件：  
  
1.  **总体吞吐量**– 使用测量**BizTalk： 消息传送 (*主机名*) 每秒接收 \Documents**和**BizTalk： 消息传送 (*主机名*)每秒处理 \Documents** BizTalk Server 的性能计数器接收和处理主机。  
  
2.  **CPU 使用率**– 测量与**\Processor(_Total)\\%Processor Time** BizTalk 服务器上的性能计数器] 和 SQL Server 计算机。 已全面审阅者所有测试结果和任何性能瓶颈中所述[观测结果和建议](../technical-guides/observations-and-recommendations.md)。  
  
## <a name="scaling-out-the-processing-tier-and-the-database-tier"></a>向外扩展处理层和数据库层  
BizTalk Server 能够轻松地通过将一个或多个 BizTalk Server 计算机添加到现有的 BizTalk Server 组容纳增加的处理层功能。 BizTalk Server 能够适应增加的数据库层通过添加 MessageBox 数据库的新功能。  
  
若要为 BizTalk Server 提供横向扩展度量值，与一个、 两个、 3 和 fourBizTalk 服务器计算机执行测试。 为了演示数据库层向外缩放的影响，针对单个和多 MessageBox 系统执行这些测试。  
  
## <a name="testing-scenarios"></a>测试方案  
 下面将详细描述了通过为这些方案的 BizTalk Server 环境的消息的流。  
  
### <a name="messaging-test-scenario"></a>消息传送的测试方案  
 ![消息传递方案](../technical-guides/media/messagingscenario.gif "MessagingScenario")  
  
1.  正在测试的功能的 Visual Studio 2010 Ultimate edition 负载生成的 XML 消息，并将其发送到使用 NetTcp 传输运行 BizTalk Server 的计算机。  
  
    > [!NOTE]  
    >  有关 Visual Studio 2010 Ultimate edition 负载测试的详细信息，请参阅超链接""[测试应用程序](http://go.microsoft.com/fwlink/?LinkID=208247)(http://go.microsoft.com/fwlink/?LinkID=208247)。  
    >   
    >  有关如何我们使用在本测试环境中测试的功能的 Visual Studio 2010 Ultimate edition 负载的详细信息，请参阅[促进自动测试使用 Visual Studio](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)。  
  
2.  由 BizTalk 服务器接收 XML 消息接收位置使用 WCF NetTcp 接收适配器。 接收位置配置为使用 PassThruReceive 管道中，执行不会对消息处理。  
  
3.  BizTalk Server 终结点管理器 (EPM) 将消息发布到 BizTalk MessageBox 数据库。  
  
4.  使用 WCF NetTcp 发送适配器 BizTalk Server 发送端口订阅接收位置所发布消息，并从 BizTalk MessageBox 检索消息。 发送端口使用 PassThruTransmit 管道中，执行不会对消息处理。  
  
5.  消息传递到后端 WCF 服务由 WCF NetTcp 发送适配器。  
  
### <a name="orchestration-test-scenario"></a>业务流程测试方案  
 ![业务流程方案流](../technical-guides/media/orchestrationscenarioflow.gif "OrchestrationScenarioFlow")  
  
1.  正在测试的功能的 Visual Studio 2010 Ultimate edition 负载生成的 XML 消息，并将其发送到运行 BizTalk Server 使用 NetTcp 传输的计算机。  
  
2.  由 BizTalk 服务器接收 XML 消息接收使用 WCF NetTcp 接收适配器的端口。 接收端口被配置为使用 PassThruReceive，管道会执行不会对消息处理。  
  
3.  消息传递到简单的业务流程，其中仅包含接收端口 （步骤 2 中绑定到 WCF 接收端口） 和发送端口 （步骤 4 中绑定到 WCF 发送端口）。 消息变量是"非类型化"，这意味着的"System.XML.XmlDocument"的它们使用的"消息类型"。 业务流程只接收消息都通过其接收端口并通过其发送端口发送消息。 执行没有消息处理操作。  
  
4.  使用 WCF NetTcp 发送适配器单向 BizTalk Server 发送端口业务流程所发布消息订阅，并从 BizTalk MessageBox 检索消息。 发送端口使用 PassThruTransmit 管道中，执行不会对消息处理。  
  
5.  消息传递到后端 WCF 服务由 WCF NetTcp 发送适配器。  
  
## <a name="hardware-configuration"></a>硬件配置  
  
### <a name="lab-hardware-diagram-and-specifications"></a>实验室瓜和规范  
 为实验室使用的硬件配置如下所示。 若要轻松地适应外的处理和数据库层的缩放，已使用以下实验室硬件：  
  
-   两个企业类 Hewlett Packard DL-380 计算机和 BizTalk Server 处理层的两个企业类 Dell R710 计算机。  
  
-   四个数据库层，以提供多 MessageBox 功能的企业类 Dell R900 计算机。  
  
 下面提供的实验室中使用的硬件的关系图：  
  
 ![性能指南基础结构](../technical-guides/media/performanceguideinfrastructure.gif "PerformanceGuideInfrastructure")  
  
 下表提供有关在实验室中使用的硬件的更具体信息。  
  
|名称|Model|CPU 类型|CPU 数|内核/CPU 数|CPU 体系结构|内存|操作系统|软件|  
|----------|-----------|--------------|--------------------|--------------------------|----------------------|------------|----------------------|--------------|  
|R710-01|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|R710-02|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380G7-01|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380G7-02|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2 Enterprise Edition|BizTalk Server|  
|DL380-01|Hewlett Packard DL380|Intel Xeon 5150|2 x 2.66 GHz|2|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|SQL Server 2008 R2 负载测试数据库<br /><br /> Visual Studio 2010<br /><br /> WCF 后端服务|  
|DL380-02|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Visual Studio 2010 负载测试控制器|  
|DL380-03|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Visual Studio 2010 负载测试代理|  
|DL380-04|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2 Enterprise Edition|Visual Studio 2010 负载测试代理。<br /><br /> Perfmon 命令行|  
|R805-06|Dell PowerEdge R805|AMD 个四核 Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2 Enterprise Edition|Visual Studio 2010 负载测试代理|  
|R805-07|Dell PowerEdge R805|AMD 个四核 Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2 Enterprise Edition|Visual Studio 2010 负载测试代理|  
|R900-03|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|带累积更新 4 的 SQL Server 2008 R2|  
|R900-04|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|带累积更新 4 的 SQL Server 2008 R2|  
|R900-05|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|带累积更新 4 的 SQL Server 2008 R2|  
|R900-06|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 Enterprise Edition|带累积更新 4 的 SQL Server 2008 R2|  
  
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
  
2.  **哪些其他应用程序将在生产中使用 SAN？** – 请考虑什么其他应用程序将使用 SAN 在生产环境中。 如果其他数据库或否则为 I/O 密集型应用程序如 Exchange Server 将使用 SAN 在生产环境中，将相应地减少可用于运行 BizTalk Server 的计算机的 SAN 吞吐量的量。  
  
 为实验室环境中，使用专用的 SAN。 每个四个 SQL Server 计算机已连接到 SAN 交换机具有两个 4 Gbps 主机总线适配器 (Hba)，提供每个服务器的 8 Gbps 的总潜在吞吐量。 SAN 具有两个服务处理器，且每个服务处理器必须连接到纤程交换机，提供 16-Gbps SAN 交换机之间的总体潜在吞吐量的两个前端端口。  
  
 下面的 LUN 配置为每个四个在测试环境中运行 SQL Server 的计算机使用。  
  
|驱动器号|卷名|“文件”|LUN 的大小 (GB)|  
|------------------|-----------------|-----------|---------------------|  
|C|本地 C 驱动器|MASTER、 MSDB 和模型|136|  
|H|Data_Tempdb|TempDB 数据文件|50|  
|I|Logs_Tempdb|TempDB 日志文件|50|  
|J|Data_BtsMsgBox|BizTalk MsgBoxDB 数据文件和 （在 Master MsgBox 中) 上管理数据库，SSO DB DTA 数据库数据文件|120|  
|K|Logs_BtsMsgBox|BizTalk MsgBoxDB 日志文件和 （在 Master MsgBox 中) 上管理数据库、 SSO 数据库、 DTA 数据库日志文件|120|  
|O|Logs_Spare|不用于 SQL 文件。 用于存储 DTCLog 文件，因为 MSDTC 导致频繁的磁盘 I/O，特别是在多 MessageBox 环境。|20|  
  
### <a name="sqlio-test-results"></a>SQLIO 测试结果  
 我们使用 SQLIO 工具来进行基准测试，并考虑在本实验室环境中使用的存储区域网络 (SAN) 配置的输入/输出容量。 该工具的名称可以看出，SQLIO 是用于测量的文件系统 I/O 对 SQL Server 性能的影响的重要工具。 

若要度量的存储区域网络 (SAN) 配置 SQL Server 数据库应用程序的输入/输出容量，请参阅[分析 I/O 特性和用于 SQL Server 数据库应用程序的大小调整存储系统](https://msdn.microsoft.com/library/ee410782(SQL.100).aspx)。  
  
 对于我们 SQLIO 测试，sqlio.exe 实用工具问题 8k 从 8 个线程读取请求和维护的 8 的 I/O 队列深度。 我们使用以下参数：  
  
-   所有测试都使用 8 个处理线程，每个运行状态，为 60 秒。  
  
-   8 kb 随机写入的数据文件。  
  
-   8 kb 随机读取数据到数据文件。  
  
-   所有文件大小将都调整为 25 GB。  
  
-   若要将基准检查的磁盘驱动器是 h:、 i:、 j:，和 K 驱动器。  
  
 使用的 SQLIO 命令行是如下所示：  
  
-   **读取的**: sqlio kR-s60 frandom-o8-t8-b8 LS-FParam.txt  
  
-   **For writes**: sqlio -kW -s60 -frandom -o8 -t8 -b8 -LS -FParam.txt  
  
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
 [缩放 BizTalk Server 生产环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)