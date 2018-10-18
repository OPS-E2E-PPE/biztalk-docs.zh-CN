---
title: 方案概述 |Microsoft Docs
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
ms.openlocfilehash: f5bbc23f4d6b9d1e2886059cf053a495562c1d01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007142"
---
# <a name="scenario-overview"></a>方案概述
本主题概述的负载测试由 BizTalk Server 已完成产品组，以在现代企业级别的硬件上运行时评估 BizTalk Server 的可伸缩性。  

 使用专用的硬件隔离环境中执行所有测试。 执行了超过 200 个测试运行并由 BizTalk Server 产品组已验证的所有结果。  

 使用消息传送方案和业务流程方案; 执行测试这两种方案利用 BizTalk WCF NetTcp 适配器。  

 若要评估的 BizTalk Server 引擎可能的最大性能，不使用任何自定义管道组件;仅在单一、 非常简单的业务流程用于业务流程方案。 性能优化中所述[优化性能](../technical-guides/optimizing-performance.md)已应用到环境，并完全记录在[观测和建议](../technical-guides/observations-and-recommendations.md)。  

## <a name="test-goals"></a>测试目标  
 负载测试执行的目标包括以下方面：  

1.  提供常规大小和规模的 BizTalk Server 的指南：  

    1.  量化向 BizTalk Server 组添加其他计算机的影响。 对于此测试，BizTalk Server 解决方案的性能进行测量的 BizTalk Server 组运行时，运行 BizTalk Server 的两个、 三个和四个计算机。  

    2.  量化向 BizTalk Server 组添加其他 BizTalk MessageBox 数据库的影响。 对于此测试，BizTalk Server 解决方案的性能进行测量组已配置为使用单个 MessageBox 数据库或四个 MessageBox 数据库时。  

        > [!NOTE]  
        >  因此没有什么，如果有，性能好处一到两个 MessageBox 数据库进行扩展时不进行测试了两个 MessageBox 数据库。 事实上，一到两个 MessageBox 数据库缩放可能会影响性能。 有关向外扩展 MessageBox 的详细信息，请参阅[缩放出 SQL Server 层](../core/scaling-up-the-sql-server-tier.md)。

2.  提供了以下方案的大小调整和缩放指南：  

    1.  WCF NetTcp 单向消息传送方案  

    2.  WCF NetTcp 单向业务流程方案  

## <a name="test-measurements-used"></a>使用的测试度量值  
BizTalk Server 性能进行测量使用以下条件：  

1.  **总体吞吐量**– 使用测量**BizTalk： 消息传送 (*主机名*) 每秒接收 \Documents**并**BizTalk： 消息传送 (*主机名*)每秒处理 \Documents**接收的 BizTalk Server 性能计数器和处理主机。  

2.  **CPU 使用率**– 使用测量**\Processor(_Total)\\%Processor Time** BizTalk Server 上的性能计数器] 和 SQL Server 计算机。 全面了解所有测试结果和中所述的任何性能瓶颈[观测和建议](../technical-guides/observations-and-recommendations.md)。  

## <a name="scaling-out-the-processing-tier-and-the-database-tier"></a>向外扩展的处理层和数据库层  
BizTalk Server 能够轻松地通过将一个或多个 BizTalk Server 计算机添加到现有 BizTalk Server 组容纳更强的处理层功能。 BizTalk Server 适合于通过 MessageBox 数据库添加更高的数据库层功能。  

若要为 BizTalk Server 提供横向扩展指标，一个、 两个、 三种类型，与 fourBizTalk 服务器计算机执行测试。 若要演示的向外扩展数据库层的影响，针对单个和多 MessageBox 系统执行这些测试。  

## <a name="testing-scenarios"></a>测试方案  
 下面将详细介绍了消息通过 BizTalk Server 环境对于这些方案的流。  

### <a name="messaging-test-scenario"></a>消息传送的测试方案  
 ![消息传递方案](../technical-guides/media/messagingscenario.gif "MessagingScenario")  

1.  Visual Studio 2010 Ultimate edition 负载测试功能生成的 XML 消息，并将其发送到使用 NetTcp 传输运行 BizTalk Server 的计算机。  

    > [!NOTE]  
    >  有关 Visual Studio 2010 Ultimate edition 负载测试的详细信息，请参阅 HYPERLINK""[测试应用程序](http://go.microsoft.com/fwlink/?LinkID=208247)(http://go.microsoft.com/fwlink/?LinkID=208247)。  
    >   
    >  有关我们如何使用 Visual Studio 2010 Ultimate edition 中的负载测试功能我们的测试环境的详细信息，请参阅[促进自动测试使用 Visual Studio](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)。  

2.  由 BizTalk Server 接收 XML 消息接收位置使用的 Wcf-nettcp 接收适配器。 接收位置配置为使用 PassThruReceive 管道，用于执行不处理消息。  

3.  BizTalk 服务器终结点管理器 (EPM) 将消息发布到 BizTalk MessageBox 数据库。  

4.  使用 Wcf-nettcp 发送适配器的 BizTalk Server 发送端口订阅由接收位置发布的消息和从 BizTalk MessageBox 中检索消息。 发送端口使用 PassThruTransmit 管道，用于执行不处理消息。  

5.  消息传递到后端 WCF 服务由 WCF NetTcp 发送适配器。  

### <a name="orchestration-test-scenario"></a>业务流程测试方案  
 ![业务流程的流程方案](../technical-guides/media/orchestrationscenarioflow.gif "OrchestrationScenarioFlow")  

1.  Visual Studio 2010 Ultimate edition 负载测试功能生成的 XML 消息，并将其发送到运行 BizTalk Server 使用 NetTcp 传输的计算机。  

2.  由 BizTalk Server 接收 XML 消息接收端口将使用 Wcf-nettcp 接收适配器。 接收端口配置为使用 PassThruReceive，管道的执行不会对消息处理。  

3.  消息传递到简单的业务流程，其中仅包含 （步骤 2 中绑定到 WCF 接收端口） 的接收端口和发送端口 （步骤 4 中绑定到 WCF 发送端口）。 消息变量是"非类型化"，这意味着的"System.XML.XmlDocument"的它们使用的"消息类型"。 业务流程只收到的消息通过其接收端口，并通过其发送端口发送消息。 不执行处理任何消息。  

4.  使用 Wcf-nettcp 发送适配器的单向 BizTalk Server 发送端口订阅由业务流程发布消息，并从 BizTalk MessageBox 中检索消息。 发送端口使用 PassThruTransmit 管道，用于执行不处理消息。  

5.  消息传递到后端 WCF 服务由 WCF NetTcp 发送适配器。  

## <a name="hardware-configuration"></a>硬件配置  

### <a name="lab-hardware-diagram-and-specifications"></a>实验室瓜和规范  
 使用实验室的硬件配置如下图所示。 若要轻松地适应个处理和数据库层横向扩展，已使用以下实验室硬件：  

- 两个企业类 Hewlett Packard DL 380 计算机和 BizTalk Server 处理层的两个企业 Dell R710 类计算机。  

- 要提供多 MessageBox 功能的数据库层的四个 Enterprise 类 Dell R900 计算机。  

  下面提供了在实验室中使用的硬件的关系图：  

  ![性能辅助基础结构](../technical-guides/media/performanceguideinfrastructure.gif "PerformanceGuideInfrastructure")  

  下表提供了有关在实验室中使用的硬件的更具体信息。  

|“属性”|“模型”|CPU 类型|CPU 数|核心/CPU 数|CPU 体系结构|内存|操作系统|软件|  
|----------|-----------|--------------|--------------------|--------------------------|----------------------|------------|----------------------|--------------|  
|R710-01|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2 企业版|BizTalk Server|  
|R710-02|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2 企业版|BizTalk Server|  
|DL380G7-01|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2 企业版|BizTalk Server|  
|DL380G7-02|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2 企业版|BizTalk Server|  
|DL380-01|Hewlett Packard DL380|Intel Xeon 5150|2 x 2.66 GHz|2|x64|8 GB|Windows Server 2008 R2 企业版|SQL Server 2008 R2 负载测试数据库<br /><br /> Visual Studio 2010<br /><br /> WCF 后端服务|  
|DL380-02|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2 企业版|Visual Studio 2010 负载测试控制器|  
|DL380-03|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2 企业版|Visual Studio 2010 负载测试代理|  
|DL380-04|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2 企业版|Visual Studio 2010 负载测试代理。<br /><br /> Perfmon 命令行|  
|R805-06|Dell PowerEdge R805|AMD 四核 Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2 企业版|Visual Studio 2010 负载测试代理|  
|R805-07|Dell PowerEdge R805|AMD 四核 Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2 企业版|Visual Studio 2010 负载测试代理|  
|R900-03|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 企业版|SQL Server 2008 R2 累积更新 4|  
|R900-04|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 企业版|SQL Server 2008 R2 累积更新 4|  
|R900-05|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 企业版|SQL Server 2008 R2 累积更新 4|  
|R900-06|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2 企业版|SQL Server 2008 R2 累积更新 4|  

### <a name="storage-area-network-configuration"></a>存储区域网络配置  
 下图描绘了存储区域网络 (SAN) 配置用于实验室环境。  

 ![SAN 信息](../technical-guides/media/saninformation.gif "SANinformation")  

### <a name="emc-clariion-cx4-960-san-configuration"></a>EMC CLARiiON CX4 960 SAN 配置  

|服务处理器和高速缓存信息|LUN 配置|  
|---------------------------------------------|-----------------------|  
|两个服务处理器，每个都有：<br /><br /> -读取缓存大小： 2000 MB。<br />-写入缓存大小： 8000 MB。<br />的连接到光纤交换机两个前端端口。 每个端口中 4 Gbps。|-64 个磁盘 (268 GB，15 k RPM，光纤通道 Seagate。<br />-八个 8 磁盘 RAID 1 + 0 从这些 64 个磁盘划分的组。<br />-每个 DB 服务器分配 5 个 Metalun 均匀地从这些 RAID 组配置。|  

 务必确定 SAN 的最大可以利用它来吞吐量，并将此值设置为针对在生产环境中 SAN 的预期负载进行比较。 这将有助于防止你的应用程序从测试/质量保证 (QA) 环境移动到生产环境时未预料到会产生与 SAN 相关硬件支出。 例如，SAN 的最大可用吞吐量可能多个足以满足您的沙盒测试环境中的应用程序。 但是，如果其他服务器应用程序将在生产环境中使用 SAN，可用 SAN 吞吐量可能不符合要求，并且可能会成为瓶颈。  

 评估您的 SAN 的性能时，考虑以下方面：  

1. **什么是 SAN 的最大可以利用它来吞吐量？** – 这是使用最低通用标准，在吞吐量、 主机总线适配器 (HBA) 中的服务器、 开关 SAN 吞吐量和 SAN 控制器卡的速度方面进行测量。  

2. **哪些应用程序将在生产环境中使用 SAN？** – 考虑什么其他应用程序将使用 SAN 在生产环境中。 如果其他数据库或否则为 I/O 密集型应用程序如 Exchange Server 将使用 SAN 在生产环境中，将相应地减少的 SAN 的吞吐量可用于运行 BizTalk Server 的计算机。  

   对于实验室环境中，使用了专用的 SAN。 每四个 SQL Server 计算机已连接到 SAN 交换机具有两个 4 Gbps 主机总线适配器 (Hba) 提供 8 Gbps 每个服务器的总潜在吞吐量。 SAN 有两个服务处理器，并且每个服务处理器有两个前端端口连接到光纤交换机，提供 16 Gbps SAN 和交换机之间的总潜在吞吐量。  

   下面的 LUN 配置为每个测试环境中运行 SQL Server 的四个计算机使用。  

|驱动器号|卷名|“文件”|LUN 的大小 (GB)|  
|------------------|-----------------|-----------|---------------------|  
|C|本地 C 驱动器|MASTER、 MSDB 和 MODEL|136|  
|H|Data_Tempdb|TempDB 数据文件|50|  
|I|Logs_Tempdb|TempDB 日志文件|50|  
|J|Data_BtsMsgBox|BizTalk MsgBoxDB 数据文件 + （在 Master MsgBox) Mgmt 数据库 DTA 数据库数据文件在 SSO 数据库|120|  
|K|Logs_BtsMsgBox|BizTalk MsgBoxDB 日志文件 + （在 Master MsgBox) Mgmt 数据库、 DTA DB SSO 数据库日志文件|120|  
|O|Logs_Spare|不使用的 SQL 文件。 用来存储 DTCLog 文件，作为 MSDTC 会导致频繁的磁盘 I/O，尤其是在多 MessageBox 环境中。|20|  

### <a name="sqlio-test-results"></a>SQLIO 测试结果  
 我们使用的 SQLIO 工具来制定基准和度量值在我们的实验室环境中使用的存储区域网络 (SAN) 配置的输入/输出容量。 该工具的名称可以看出，SQLIO 是一个重要的工具，用于测量上的 SQL Server 性能的文件系统 I/O 的影响。 

若要度量值的存储区域网络 (SAN) 配置的 SQL Server 数据库应用程序的输入/输出容量，请参阅[分析 I/O 特性和用于 SQL Server 数据库应用程序的大小调整存储系统](https://msdn.microsoft.com/library/ee410782(SQL.100).aspx)。  

 对于我们 SQLIO 测试，sqlio.exe 实用工具问题 8 K 从 8 个线程读取请求和维护 8 个 I/O 队列深度。 我们使用以下参数：  

- 所有测试都使用 8 个处理线程，每个运行 60 秒。  

- 8 kb 的随机写入的数据文件。  

- 8 kb 的随机读取的数据文件。  

- 所有文件大小将都调整为 25 GB。  

- 若要进行基准检查的磁盘驱动器是 h:、 i:、 j:，和 K 驱动器。  

  使用 SQLIO 命令行中包含如下所示：  

- **对于读取**: sqlio 韩国-s60 frandom-o8-t8-b8 LS-FParam.txt  

- **对于写入**: sqlio-kW-s60 frandom-o8-t8-b8 LS-FParam.txt  

  Param.txt 文件包含以下信息：  

- **驱动器数量：** h:、 i:、 j:，和 K  

- **测试文件的物理位置**:  

  -   H:\testfile.dat 2 0x0 25000  

  -   I:\testfile.dat 2 0x0 25000  

  -   J:\testfile.dat 2 0x0 25000  

  -   K:\testfile.dat 2 0x0 25000  

  下表列出了测试结果：  

- 从在 Lun h:，i:，j:，k: (用于我们的数据库文件的所有 Lun) 上同时 25 GB 测试文件中读取 8 KB 随机  

  ###  

  | 每秒 （Io 数/秒） 的输入/输出操作 | 兆字节为单位每秒 （Mb/秒） | 平均延迟 |
  |----------------------------------------------|--------------------------------|-----------------|
  |                   10662.67                   |             83.30              |      5 毫秒       |


- 8 KB 的随机写入同时在 Lun h:，i:，j:，k: (用于我们的数据库文件的所有 Lun) 上的 25 GB 测试文件  

  ###  

  |每秒 （Io 数/秒） 的输入/输出操作|兆字节为单位每秒 （Mb/秒）|平均延迟|  
  |------------------------------------------------------|---------------------------------------|---------------------|  
  |31527.95|246.31|1 ms|  

## <a name="see-also"></a>请参阅  
 [缩放 BizTalk Server 生产环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)