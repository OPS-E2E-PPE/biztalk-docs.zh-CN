---
title: 测试方案概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde553ad-2540-40d9-a74b-928fee873c31
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e412c771e321f364ecfd565bd2031e647d4e6e5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301742"
---
# <a name="test-scenario-overview"></a>测试方案概述
本主题概述了测试应用程序;测试，所使用的方法和列表的说明在负载测试期间捕获的关键绩效指标 (Kpi)。  

## <a name="test-application"></a>测试应用程序  
 同步请求-响应应用程序用于比较的物理硬件上运行的 BizTalk Server HYPER-V 上运行的 BizTalk Server 的性能。 此应用程序用于说明性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已被优化以低延迟的解决方案。 较低的延迟消息的某些情况下，如联机银行客户端发送一个请求，需要在非常短的时间间隔 （例如 < 3 秒） 内响应消息的位置至关重要。  

 下图显示使用的高级体系结构。 Visual Studio Team System (VSTS) 2008 Test Load Agent 调用自定义测试类，该类用于 WCF 传输生成负载与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在此方案中的应用程序公开请求-响应通过 Wcf-basichttp 接收位置。 VSTS 2008 Test Load Agent 用作测试客户端由于极大的它所提供的灵活性，包括配置的消息数的功能，同时线程总数，在发送和请求之间的休眠时间间隔发送。  

 多个 VSTS 2008 Test Load Agent 的计算机可以运行在迁移后，若要模拟现实世界的负载模式。 对于这些测试，VSTS 2008 Test Load Agent 的计算机的驱动力也在运行 BizUnit 3.0 的单个 VSTS 2008 测试负载代理控制器计算机。 因此，一致负载发送到的物理和虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 有关使用 VSTS 2008 Test Edition 来生成用于测试的模拟的负载的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=132311 ](http://go.microsoft.com/fwlink/?LinkID=132311)。  

 ![应用程序体系结构](../technical-guides/media/testapplicationarchitecture.gif "TestApplicationArchitecture")  
测试应用程序体系结构  

1. Wcf-basichttp: Wcf-basichttp 或 WCF 自定义请求-响应接收位置接收新 CalculatorRequest 从 Test Load Agent 的计算机。  

2. XML 拆装器组件将升级 CalculatorRequest xml 文档内的方法元素。 消息代理提交到 MessageBox 数据库 (BizTalkMsgBoxDb) 传入的消息。  

3. 入站的请求启动 LogicalPortsOrchestration 的新实例。 此业务流程使用直接绑定的端口接收与方法升级属性 CalculatorRequest 消息 ="LogicalPortsOrchestration"。  

4. LogicalPortsOrchestration 使用循环检索操作并为每个项，它调用下游计算器 WCF web 服务使用逻辑要求-响应端口。 创建使用助手组件计算器 WCF web 服务的请求消息并将其发布到 MessageBox。  

5. 请求消息都会使用 Wcf-basichttp 发送端口。  

6. Wcf-basichttp 发送端口调用的方法之一 （加、 减、 乘、 除） 计算器 WCF web 服务公开的。  

7. 计算器 WCF web 服务返回的响应消息。  

8. 响应消息发布到 MessageBox。  

9. 响应消息返回到调用方 LogicalPortsOrchestration。 业务流程的入站 CalculatorRequest xml 文档中的每个操作都重复此模式。  

10. LogicalPortsOrchestration 将 CalculatorResponse 消息发布到 MessageBox。  

11. 通过请求-响应 Wcf-basichttp 接收位置中检索响应消息。  

12. 响应消息返回到负载测试代理计算机。  

    在负载测试期间使用的业务流程的屏幕截图如下所示：  

> [!NOTE]  
>  为便于说明，如下所述的业务流程是实际在负载测试期间使用的业务流程的简化的版本。 在负载测试期间使用的业务流程包含多个作用域、 错误处理逻辑和其他端口类型。  

 ![测试应用程序业务流程](../technical-guides/media/logicalportsorchestration.gif "LogicalPortsOrchestration")  
测试应用程序业务流程  

## <a name="testing-methodology"></a>测试方法的更多信息  
 性能测试涉及许多任务，即如果手动执行了重复的、 单调，而且容易出错。 为了提高测试效率，并提供测试运行之间的一致性[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]BizUnit 3.0 与 Team System (VSTS) 测试版用于自动执行在测试过程中所需的任务。 VSTS 2008 Test Load Agent 的计算机用作测试客户端生成消息负载的系统和每个测试运行以提高一致性上使用的相同消息类型。 按此过程为每个测试运行提供一致的数据集。 有关 BizUnit 3.0 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=85168 ](http://go.microsoft.com/fwlink/?LinkID=85168)。 有关详细信息[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]Team System Test Edition，请参阅[ http://go.microsoft.com/fwlink/?LinkID=141387 ](http://go.microsoft.com/fwlink/?LinkID=141387)。  

 已自动执行以下步骤：  

- 停止 BizTalk 主机。  

- 清理测试目录。  

- 重新启动 IIS。  

- 清理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Messagebox 数据库。  

- 重新启动 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  

- 清除事件日志。  

- 创建存储关联的性能指标和日志文件每次运行的测试结果文件夹。  

- 启动 BizTalk 主机。  

- 加载性能监视器计数器。  

- 预热负载较小的 BizTalk 环境。  

- 通过运行代表发送。  

- 性能日志写入结果文件夹。  

- 收集应用程序日志，并写入到.csv 文件中的结果文件夹。  

- 针对收集的性能日志，以生成统计信息、 图表和报表运行性能分析的日志 (PAL) 工具、 重新记录和日志分析程序工具。 有关 PAL、 重新记录，以及日志分析程序的详细信息，请参阅[附录 d:性能度量工具](../technical-guides/appendix-d-tools-for-measuring-performance.md)。  

> [!NOTE]  
>  已禁用所有跟踪和测试过程中都禁用 BizTalk Server SQL Server 代理作业。  

 若要确保此实验的结果就能够提供的性能比较[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在物理和 HYPER-V 环境中，性能指标和日志中收集的每个测试运行一个集中位置。  

 测试客户端用于创建每个测试运行的唯一结果目录。 此目录包含所有性能日志、 事件日志和关联的数据所需的测试。 这种方法提供追溯分析之前测试的运行时所需信息是必需的。 在每个测试结束时，原始数据已编译成一组一致的结果和关键绩效指标 (Kpi)。 用于提供的点之间的不同的测试运行和不同的环境所需的比较的物理和虚拟机收集一致的结果集。 包含收集的数据：  

- **环境 –** 记录哪些环境测试针对物理硬件上的 BizTalk Server 或 BizTalk Server HYPER-V 上运行。  

- **测试运行数 –** 来唯一地标识每个测试运行  

- **测试用例-** 以记录测试过程中使用的 BizTalk Server 解决方案的体系结构。 （例如具有与使用内联的业务流程的逻辑端口的业务流程将发送）  

- **日期 –** 若要记录的日期和时间测试是否运行  

- **时间已启动 –** 所启动的第一个 VSTS 负载测试代理报告  

- **时间已停止 –** 报告的最后一个 VSTS 负载测试代理来完成  

- **在几分钟内 – 测试持续时间**以记录测试的持续时间。  

- **总计-发送的邮件数**以记录测试期间从负载代理计算机发送到 BizTalk Server 计算机的消息总数。  

- **每秒-发送的邮件数**来记录每秒从负载代理计算机到 BizTalk Server 计算机测试过程中发送的消息。  

- **平均客户端延迟 –** 记录的平均 Test Load Agent 客户端发起的请求和接收到的响应 BizTalk Server 计算机在负载测试期间之间的时间量。  

- **请求-响应持续时间平均 （毫秒） –** 报告**BizTalk: Messaging Latency\Request 响应延迟 （秒）** biztalkserverisolatedhost 性能监视器计数器  

  > [!NOTE]  
  >  使用其中多个虚拟化的 BizTalk 主机正在运行的这些计数器的平均值计算出从日志。  

- **每秒 – 业务流程已完成**报告**XLANG/s 业务流程 (BizTalkServerApplication) \Orchestrations 每秒完成**性能监视器计数器。 此计数器可很好的吞吐量测量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。  

- **消息处理 < 3 秒数 – %** 记录在测试期间的 3 分钟内处理的消息的总数。  

  VSTS 2008 负载测试用于生成整个所有测试的一致负载。 以下测试运行设置和测试，以调整每个测试的负载配置文件期间修改了负载模式：  

- **测试运行设置**  

   具体取决于正在执行的测试已修改以下测试运行设置：  

  - **运行持续时间 –** 指定测试运行的时间长度。  

    ![测试运行的设置](../technical-guides/media/wcfloadtestrunsettings.gif "WCFLoadTestRunSettings")  
    测试运行设置  

- **测试模式设置**  

   具体取决于正在执行的测试修改了以下测试模式设置：  

  1. **模式-** 指定负载测试期间如何调整模拟的用户负载。 负载模式为**常量**，**步骤**，或**目标**基于。 所有负载测试执行都为常数或步骤。  

     > [!NOTE]
     >  所有测试执行本指南使用了上述两**常量**负载模式或**步骤**负载模式。 常量负载模式和步骤的负载模式提供了以下功能：  
     > 
     > - **常量负载模式 –** 负载模式是相同的测试的持续时间内，模拟用户的数量从预定义级别开始，并不会更改。  
     >   -   **分级负载模式 –** 在测试运行期间增加的负载模式; 模拟用户的数量从预定义级别开始，就会递增预定义的金额按预定义的时间间隔的测试的持续时间。  

  2. **常数用户计数 （常量负载模式） –** 生成针对 Visual Studio 负载测试项目的 app.config 文件中指定的终结点地址的负载的虚拟用户数。 用于负载测试的负载模式设置中指定此值。  

  3. **初始用户计数 （分级负载模式） –** 生成针对分级负载模式测试的开始处的指定的终结点地址的负载的虚拟用户数。 用于负载测试的负载模式设置中指定此值。  

  4. **最大用户计数 （分级负载模式） –** 生成针对分级负载模式测试末尾处的指定的终结点地址的负载的虚拟用户数。 用于负载测试的负载模式设置中指定此值。  

  5. **单步持续时间 （分级负载模式） –** 虚拟用户生成针对负载测试步骤的指定的终结点地址的负载的秒数。  

  6. **单步用户计数 （分级负载模式） –** 可使用分级负载模式时增加的每个步骤的虚拟用户数。  

     ![测试模式设置](../technical-guides/media/wcfloadtestpatternsettings.gif "WCFLoadTestPatternSettings")  
     测试模式设置  

  有关使用负载测试中的详细信息[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]，请参阅主题**使用负载测试**中[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]Team System 文档[ http://go.microsoft.com/fwlink/?LinkId=141486 ](http://go.microsoft.com/fwlink/?LinkId=141486)。  

## <a name="key-performance-indicators-measured-during-testing"></a>在测试期间测量的关键绩效指标  
 适用于所有测试运行的关键绩效指标 (KPI) 作为捕获以下性能监视器计数器：  

> [!NOTE]  
>  有关评估性能监视器计数器的性能的详细信息，请参阅[核对清单：Hyper V 上测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  

 **BizTalk Server KPI**  

- **每秒-处理的文档**由度量**BizTalk： 消息传送/文档处理数/秒**计数器。  

- **延迟 –** 所返回的 VSTS 2008 负载测试控制器进行度量。  

  **SQL Server KPI**  

- **SQL Server 的处理器使用率 –** 由度量 **SQL\Processor(Total)\\%Processor Time**计数器。 此计数器测量的 CPU 使用率[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]处理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  

- **Transact SQL 命令处理性能 –** 由度量 **\SQL Server:SQL Statistics\Batch 请求数/秒**计数器。 此计数器测量的每秒接收的 TRANSACT-SQL 命令批处理的数目。 使用此计数器来测量吞吐量上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  

  **网络 KPI**  

- **BizTalk Server 的网络吞吐量 –** 由度量 **\Network 接口 (\*) \Bytes Total/sec**上的性能监视器计数器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  

- **SQL Server 网络吞吐量 –** 由度量**SQL Network Interface\Bytes Total/sec (Avg)** 返回的 VSTS 2008 负载测试控制器。  

  **内存 KPI**  

- **可用内存 — —** 由度量 **\Memory\Available Mbytes**的各种方案的计数器。  

## <a name="physical-infrastructure-specifics"></a>物理基础结构详细信息  
 为每个已安装的服务器已调整以下设置。  

 **对于所有服务器：**  

- 页面文件设置为分配的物理内存量的 1.5 倍。 分页文件通过确保初始大小和最大值相同以 mb 为单位设置为固定大小。  

- 高级系统属性屏幕中选择了"调整为最佳性能"性能选项。  

- 它已验证的系统具有已调整为获得最佳性能的系统属性的性能选项部分中的后台服务。  

- [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 已安装为上每个虚拟机的来宾操作系统。  

- Windows 更新已安装最新安全更新的所有服务器上成功运行了。  

  **对于 SQL Server:**  

- 根据安装指南位于安装了 SQL Server [ http://go.microsoft.com/fwlink/?LinkId=141021 ](http://go.microsoft.com/fwlink/?LinkId=141021)。  

- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 使用 SAN Lun 配置根据下表。 数据库和日志文件已隔离到在 Lun，如下所示，若要减少有可能发生磁盘 I/O 争用：  

  - Data_Sys 卷用于除 MessageBox 和 TempDb 数据库 （包括系统和 BizTalk 数据库） 的所有数据库文件都存储。  

  - Log_Sys 卷用于存储所有日志文件 (包括系统和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库) 除外的 MessageBox 和 TempDb 数据库。  

  - Data_TempDb 卷用于存储在 TempDb 数据库文件。  

  - Logs_TempDb 卷用于存储 TempDb 日志文件。  

  - MessageBox 数据库文件的存储上 Data_BtsMsgBox 卷和日志文件的存储 Log_BtsMsgBox 卷上。  

- 除此之外，单独的 LUN 提供 MSDTC 日志文件。 在高吞吐量 BizTalk 系统中，MSDTC 日志文件活动已被证实将导致 I/O 瓶颈，如果它将保留在操作系统所在的物理驱动器上。  


  |      卷名      |               文件               | LUN 大小 GB | 主机分区大小 GB | 群集大小 |
  |-----------------------|-----------------------------------|-------------|------------------------|--------------|
  |       Data_Sys        |    MASTER 和 MSDB 数据文件    |     10      |           10           |     64KB     |
  |       Logs_Sys        |     MASTER 和 MSDB 日志文件     |     10      |           10           |     64KB     |
  |      Data_TempDb      |         TempDB 数据文件          |     50      |           50           |     64KB     |
  |      Logs_TempDb      |          TempDB 日志文件          |     50      |           50           |     64KB     |
  |    Data_BtsMsgBox     |     BizTalkMsgBoxDb 数据文件     |     300     |          100           |     64KB     |
  |    Logs_BtsMsgBox     |     BizTalkMsgBoxDb 日志文件      |     100     |          100           |     64KB     |
  | Data_BAMPrimaryImport |    BAMPrimaryImport 数据文件     |     10      |           10           |     64KB     |
  | Logs_BAMPrimaryImport |     BAMPrimaryImport 日志文件     |     10      |           10           |     64KB     |
  | Data_BizTalkDatabases | 其他 BizTalk 数据库数据文件 |     20      |           20           |     64KB     |
  | Logs_BizTalkDatabases | 其他 BizTalk 数据库日志文件  |     20      |           20           |     64KB     |
  |          不可用          |          MSDTC 日志文件           |      5      |           5            |     不可用      |


- 根据安装指南位于安装了 BizTalk Server [ http://go.microsoft.com/fwlink/?LinkId=128383 ](http://go.microsoft.com/fwlink/?LinkId=128383)。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最佳做法分析器 (BPA) 工具用来在执行平台验证后已配置系统。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BPA 位于[ http://go.microsoft.com/fwlink/?LinkId=67150 ](http://go.microsoft.com/fwlink/?LinkId=67150)。  

## <a name="virtualization-specifics"></a>虚拟化细节  
 一个单一 50 GB 的固定大小的 VHD 用来承载每个 HYPER-V 虚拟机的操作系统。  

 固定的 Vhd 已使用而不是可动态调整大小的 Vhd，因为它们立即分配的最大存储为 VHD 的托管它的驱动器上的文件。 这可以减少发生物理驱动器上托管它的位置，这样可以提高磁盘 I/O 性能的 VHD 文件的碎片。  

 设置虚拟机，安装了[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]对单个 VHD 执行 64 位版本。 已安装所有合适的更新后使用 sysprep 实用工具一起安装的映像基础的虚拟机[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，%WINDIR%\system32\sysprep 目录中。  

 此基本 VHD 已复制，然后跨环境部署的所有 HYPER-V 虚拟机都用作的基础。 若要重置任何之前的系统的安全标识符的基本 VHD 映像上运行 Sysprep[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]二进制文件部署到系统。  

> [!NOTE]
>  运行 Sysprep 后已安装并在服务器上配置 BizTalk Server 可以通过使用 Sysprep 应答文件和 BizTalk Server 提供的脚本来完成。 向 BizTalk Server 安装在 32 位和 64 位版本的这些示例脚本专供[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]仅。 有关详细信息，请参阅 BizTalk Server 联机文档。  

 无人参与 Windows 安装程序参考位于[ http://go.microsoft.com/fwlink/?LinkId=142364 ](http://go.microsoft.com/fwlink/?LinkId=142364)。  

## <a name="see-also"></a>请参阅  
 [附录 c:BizTalk Server 和 SQL Server 的 HYPER-V 可支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)