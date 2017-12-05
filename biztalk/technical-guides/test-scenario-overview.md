---
title: "测试方案概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cde553ad-2540-40d9-a74b-928fee873c31
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86fd882f89caee27211c03a4e13e617fe12faef1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="test-scenario-overview"></a>测试方案概述
本主题提供测试应用程序; 的概述测试方法使用和列表的说明在负载测试期间捕获的关键绩效指标 (Kpi)。  
  
## <a name="test-application"></a>测试应用程序  
 同步请求-响应应用程序用于将 BizTalk Server 运行在物理硬件上将在 HYPER-V 上运行的 BizTalk 服务器性能进行比较。 此应用程序用于演示性能的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已被优化以低延迟的解决方案。 低延迟消息对于如联机银行客户端发送一个请求，需要在非常短的时间间隔 （例如 < 3 秒） 内响应消息的其中某些方案至关重要。  
  
 下图显示使用的高级体系结构。 Visual Studio Team System (VSTS) 2008年测试加载代理调用自定义测试类，该类用于 WCF 传输生成负载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公开在此方案中的应用已通过 WCF BasicHttp 请求-响应接收位置。 VSTS 2008 Load Test Agent 已使用测试客户端由于它提供了极大的灵活性，包括功能配置的消息数，同时线程总数，在发送和请求之间的休眠时间间隔发送。  
  
 可以结合，以模拟实际负载模式运行几个 VSTS 2008 Load Test Agent 的计算机。 对于这些测试，VSTS 2008 Load Test Agent 计算机已由还运行 BizUnit 3.0 的单个 VSTS 2008 测试负载代理控制器计算机进行驱动。 因此，一致负载已发送到物理和虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 有关使用 VSTS 2008 测试版来生成用于测试的模拟的负载的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=132311](http://go.microsoft.com/fwlink/?LinkID=132311)。  
  
 ![应用程序体系结构](../technical-guides/media/testapplicationarchitecture.gif "TestApplicationArchitecture")  
测试应用程序体系结构  
  
1.  WCF BasicHttp 或 WCF 自定义请求-响应接收位置接收新 CalculatorRequest 来自 Load Test Agent 计算机。  
  
2.  XML 反汇编程序组件提升 CalculatorRequest xml 文档内的方法元素。 消息代理将提交到 MessageBox 数据库 (BizTalkMsgBoxDb) 传入的消息。  
  
3.  入站的请求将启动 LogicalPortsOrchestration 的新实例。 此业务流程用于绑定的直接端口接收 CalculatorRequest 消息与方法提升属性 ="LogicalPortsOrchestration"。  
  
4.  LogicalPortsOrchestration 使用循环将检索操作并为每个项，它将调用下游计算器 WCF web 服务使用逻辑请求-响应端口。 创建使用帮助程序组件的计算器 WCF web 服务的请求消息并将其发布到 MessageBox。  
  
5.  请求消息都会使用 WCF BasicHttp 发送端口。  
  
6.  WCF BasicHttp 发送端口调用的方法之一 （加、 减、 乘、 划分） 由计算器 WCF web 服务公开。  
  
7.  计算器 WCF web 服务返回的响应消息。  
  
8.  响应消息发布到 MessageBox。  
  
9. 响应消息返回到调用方 LogicalPortsOrchestration。 业务流程的入站 CalculatorRequest xml 文档中的每个操作都重复此模式。  
  
10. LogicalPortsOrchestration 将 CalculatorResponse 消息发布到 MessageBox。  
  
11. 响应消息将检索的请求-响应 WCF BasicHttp 接收位置。  
  
12. 响应消息返回到负载测试代理计算机。  
  
 在负载测试期间使用的业务流程的屏幕快照所示：  
  
> [!NOTE]  
>  为便于说明，业务流程如下所示是实际了负载测试期间使用的业务流程的简化的版本。 负载测试过程中使用业务流程包括多个作用域、 错误处理逻辑和其他端口类型。  
  
 ![测试应用程序业务流程](../technical-guides/media/logicalportsorchestration.gif "LogicalPortsOrchestration")  
测试应用程序业务流程  
  
## <a name="testing-methodology"></a>测试方法的更多信息  
 性能测试涉及许多任务，即如果手动执行重复、 单调，而且容易出错。 为了提高测试效率并提供测试运行之间的一致性[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]Team System (VSTS) 测试与 BizUnit 3.0 版本用于自动执行在测试过程中所需的任务。 在每个测试运行以提高一致性上使用了相同的消息类型和 VSTS 2008 Load Test Agent 的计算机已用于测试客户端作为生成针对系统的消息负载。 此过程后对于每个测试运行提供一致的数据集。 有关 BizUnit 3.0 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=85168](http://go.microsoft.com/fwlink/?LinkID=85168)。 有关详细信息[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]Team System 测试 Edition，请参阅[http://go.microsoft.com/fwlink/?LinkID=141387](http://go.microsoft.com/fwlink/?LinkID=141387)。  
  
 已自动以下步骤：  
  
-   停止 BizTalk 主机。  
  
-   清理测试目录。  
  
-   重新启动 IIS。  
  
-   清理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Messagebox 数据库。  
  
-   重新启动 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
-   清除事件日志。  
  
-   创建用于存储相关的性能度量值和日志文件每次运行的测试结果文件夹。  
  
-   启动 BizTalk 主机。  
  
-   加载性能监视器计数器。  
  
-   预热 BizTalk 环境的小负载。  
  
-   通过运行代表发送。  
  
-   性能日志写入结果文件夹。  
  
-   收集应用程序日志，并写入结果文件夹中的.csv 文件。  
  
-   针对收集的性能日志，以生成统计信息、 图表和报表运行性能分析的日志 (PAL) 工具、 重新记录和 Log Parser 工具。 有关 PAL、 重新记录，以及日志分析器的详细信息，请参阅[测量性能的附录 d： 工具](../technical-guides/appendix-d-tools-for-measuring-performance.md)。  
  
> [!NOTE]  
>  所有跟踪已被都禁用，而在测试期间，BizTalk Server SQL Server 代理作业处于禁用都状态。  
  
 若要确认此实验室的结果是否能够提供的性能的比较[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在物理和 HYPER-V 环境中，性能指标和日志收集在中央位置的每个测试运行。  
  
 测试客户端用于创建每次测试运行的唯一结果目录。 此目录包含所有性能日志、 事件日志和相关联的数据所需的测试。 此方法提供所需的以前的测试的追溯分析运行时信息是必需。 在每个测试结束时，原始数据已编译成一组一致的结果和关键绩效指标 (Kpi)。 收集一致的结果设置为提供的点之间的不同的测试运行和不同的环境需要的比较的物理和虚拟机。 所收集的数据包括：  
  
-   **环境 –**要记录的环境已针对在物理硬件上的 BizTalk Server 或 HYPER-V 上的 BizTalk Server 正在运行测试。  
  
-   **测试运行数 –**来唯一地标识每个测试运行  
  
-   **测试用例 –**以记录测试过程中使用 BizTalk Server 解决方案的体系结构。 （例如具有逻辑端口而不是使用内联的业务流程的业务流程将发送）  
  
-   **日期 –**记录的日期和时间测试运行  
  
-   **时间已启动 –**报告启动第一个 VSTS 负载测试代理  
  
-   **时间已停止 –**报告的最后一个 VSTS 负载测试代理以完成  
  
-   **以分钟为单位 – 测试持续时间**以记录测试的持续时间。  
  
-   **总计 – 中的发送的邮件**以记录发送到的消息从负载代理计算机的 BizTalk Server 计算机在测试期间的总次数。  
  
-   **每秒-发送的邮件**来记录每秒从负载代理计算机到 BizTalk Server 计算机测试过程中发送的消息。  
  
-   **平均客户端延迟 –**记录的平均时测试加载代理客户端启动对请求和接收到的响应的 BizTalk Server 计算机在负载测试期间之间的时间量。  
  
-   **请求-响应持续时间平均 (ms) –**报告**BizTalk： 消息传送 Latency\Request 响应延迟 （秒）** BizTalkServerIsolatedHost 的性能监视器计数器  
  
    > [!NOTE]  
    >  使用其中多个虚拟化的 BizTalk 主机正在运行这些计数器的平均值计算从日志。  
  
-   **每秒 – 业务流程已完成**报告**XLANG/s 业务流程 (BizTalkServerApplication) \Orchestrations 完成每秒**性能监视器计数器。 此计数器提供的吞吐量很好地衡量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   **消息处理 < 3 秒数 – %**以记录在测试期间的 3 秒内处理的消息总数。  
  
 VSTS 2008 负载测试用于生成在所有测试整个一致负载。 以下测试运行设置，并且在测试调整每个测试的负载配置文件期间修改负载模式：  
  
-   **测试运行设置**  
  
     具体取决于正在执行测试修改以下测试运行设置：  
  
    -   **运行持续时间 –**指定测试运行的多长时间。  
  
     ![测试运行的设置](../technical-guides/media/wcfloadtestrunsettings.gif "WCFLoadTestRunSettings")  
测试运行设置  
  
-   **测试模式设置**  
  
     具体取决于正在执行测试修改了以下测试模式设置：  
  
    1.  **模式 –**指定负载测试期间如何调整模拟的用户负载。 负载模式都是**常量**，**步骤**，或**目标**基于。 所有负载测试执行都为常量或步骤。  
  
        > [!NOTE]  
        >  所有测试执行本指南使用了上述两**常量**负载模式或**步骤**负载模式。 常量负载模式和步骤的负载模式提供了以下功能：  
        >   
        >  -   **常量负载模式 –**负载模式是相同的测试的持续时间内，模拟用户的数量从预定义级别开始，并不会更改。  
        > -   **分级负载模式 –**在测试运行期间增加的负载模式; 模拟用户的数量从预定义级别开始，并且就会递增预定义的量在预定义的间隔为测试的持续时间。  
  
    2.  **常量用户计数 （常量负载模式） –**生成针对在 Visual Studio 负载测试项目的 app.config 文件中指定的终结点地址的负载的虚拟用户数。 用于负载测试的负载模式设置中指定此值。  
  
    3.  **初始用户计数 （分级负载模式） –**生成负载分级负载模式测试的开始处的指定的终结点地址的虚拟用户数。 用于负载测试的负载模式设置中指定此值。  
  
    4.  **最大用户计数 （分级负载模式） –**生成对照末尾的分级负载模式测试指定的终结点地址的负载的虚拟用户数。 用于负载测试的负载模式设置中指定此值。  
  
    5.  **单步持续时间 （分级负载模式） –**的虚拟用户生成针对负载测试步骤的指定的终结点地址的负载的秒数。  
  
    6.  **单步用户计数 （分级负载模式） –**来提高在每个步骤时使用的分级负载模式的虚拟用户数。  
  
     ![测试模式设置](../technical-guides/media/wcfloadtestpatternsettings.gif "WCFLoadTestPatternSettings")  
测试模式设置  
  
 有关使用负载测试中的详细信息[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]，请参阅主题**使用负载测试**中[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]Team System 文档[http://go.microsoft.com/fwlink/?LinkId=141486](http://go.microsoft.com/fwlink/?LinkId=141486)。  
  
## <a name="key-performance-indicators-measured-during-testing"></a>在测试期间测量的关键性能指标  
 为所有测试运行的关键绩效指标 (KPI) 中已捕获的以下性能监视器计数器：  
  
> [!NOTE]  
>  有关评估与性能监视器计数器的性能的详细信息，请参阅[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
 **BizTalk Server KPI**  
  
-   **每秒-处理的文档**测量**BizTalk： 消息传送/文档处理数/秒**计数器。  
  
-   **延迟 –**测量返回 VSTS 2008 负载测试控制器。  
  
 **SQL Server KPI**  
  
-   **SQL Server 处理器使用率 –**测量**SQL\Processor(Total)\\%Processor Time**计数器。 此计数器可测量的 CPU 使用率[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上处理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
-   **Transact SQL 命令的处理性能 –**测量**\SQL Server:SQL Statistics\Batch 每秒请求数**计数器。 此计数器测量每秒接收的 TRANSACT-SQL 命令批数。 此计数器用于测量吞吐量上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
 **网络 KPI**  
  
-   **BizTalk Server 网络吞吐量 –**测量**\Network 接口 (\*) \Bytes Total/sec**上的性能监视器计数器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
-   **SQL Server 网络吞吐量 –**测量**SQL Network Interface\Bytes Total/sec (Avg)**返回 VSTS 2008 负载测试控制器。  
  
 **内存 KPI**  
  
-   **可用内存 –**测量**\Memory\Available Mbytes**计数器的各种方案。  
  
## <a name="physical-infrastructure-specifics"></a>物理基础结构详细信息  
 为每个已安装的服务器已调整的以下设置。  
  
 **对于所有服务器：**  
  
-   分页文件被设置为分配的物理内存量的 1.5 倍。 分页文件通过确保初始大小和最大值相同以 mb 为单位设置为固定大小。  
  
-   在高级系统属性屏幕选择了"调整为最佳性能"性能选项。  
  
-   它已验证系统具有已调整为获得最佳性能的系统属性的性能选项部分中的后台服务。  
  
-   [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]已安装作为来宾操作系统上每个虚拟机。  
  
-   若要安装最新的安全更新的所有服务器上成功运行 Windows 更新。  
  
 **对于 SQL Server:**  
  
-   按照安装指南位于安装 SQL Server [http://go.microsoft.com/fwlink/?LinkId=141021](http://go.microsoft.com/fwlink/?LinkId=141021)。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用具有 SAN Lun 配置根据下表。 数据库和日志文件以分隔到跨 Lun，如下所示，以减少可能磁盘 I/O 争用：  
  
    -   Data_Sys 卷已用于存储所有数据库文件 （包括系统和 BizTalk 数据库） 除外的 MessageBox 和 TempDb 数据库。  
  
    -   Log_Sys 卷用于存储所有日志文件 (包括系统和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库) 除外的 MessageBox 和 TempDb 数据库。  
  
    -   Data_TempDb 卷用于存储 TempDb 数据库文件。  
  
    -   Logs_TempDb 卷用于存储 TempDb 日志文件。  
  
    -   Data_BtsMsgBox 卷上存储的 MessageBox 数据库文件和日志文件已存储在 Log_BtsMsgBox 卷上。  
  
-   除此之外，单独的 LUN 提供 MSDTC 日志文件。 高吞吐量 BizTalk 在系统上，MSDTC 日志文件活动已被证实将导致 I/O 瓶颈，如果它处于作为操作系统所在的物理驱动器上。  
  
    |卷名|文件|LUN 大小 GB|主机分区大小 GB|群集大小|  
    |-----------------|-----------|-----------------|----------------------------|------------------|  
    |Data_Sys|MASTER 和 MSDB 数据文件|10|10|64 KB|  
    |Logs_Sys|MASTER 和 MSDB 日志文件|10|10|64 KB|  
    |Data_TempDb|TempDB 数据文件|50|50|64 KB|  
    |Logs_TempDb|TempDB 日志文件|50|50|64 KB|  
    |Data_BtsMsgBox|BizTalkMsgBoxDb 数据文件|300|100|64 KB|  
    |Logs_BtsMsgBox|BizTalkMsgBoxDb 日志文件|100|100|64 KB|  
    |Data_BAMPrimaryImport|BAMPrimaryImport 数据文件|10|10|64 KB|  
    |Logs_BAMPrimaryImport|BAMPrimaryImport 日志文件|10|10|64 KB|  
    |Data_BizTalkDatabases|其他 BizTalk 数据库数据文件|20|20|64 KB|  
    |Logs_BizTalkDatabases|其他 BizTalk 数据库日志文件|20|20|64 KB|  
    |N/A|MSDTC 日志文件|5|5|N/A|  
  
-   按照安装指南可在安装 BizTalk Server [http://go.microsoft.com/fwlink/?LinkId=128383](http://go.microsoft.com/fwlink/?LinkId=128383)。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最佳做法分析器 (BPA) 工具已使用系统必须配置后执行平台验证。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BPA 位于[http://go.microsoft.com/fwlink/?LinkId=67150](http://go.microsoft.com/fwlink/?LinkId=67150)。  
  
## <a name="virtualization-specifics"></a>虚拟化详细信息  
 固定大小的 VHD 单个 50 GB 用于承载每个 HYPER-V 虚拟机的操作系统。  
  
 固定的 Vhd 已使用而不是动态调整了大小的 Vhd，因为它们会立即为的 VHD 的托管位置的驱动器上的文件中分配的最大存储。 这将减少碎片的托管位置，这可以提高磁盘输入/输出性能的物理驱动器上发生的 VHD 文件。  
  
 设置虚拟机，安装了[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]对单个 VHD 执行了 64 位版本。 已安装所有合适的更新后使用 sysprep 实用工具随安装映像基的虚拟机[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，%WINDIR%\system32\sysprep 目录中。  
  
 然后，此基 VHD 已复制，并用作的整个环境部署的所有 HYPER-V 虚拟机的基础。 若要重置之前的系统安全标识符的基本 VHD 映像上运行 Sysprep[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]二进制文件部署到系统。  
  
> [!NOTE]  
>  可以通过使用 Sysprep 应答文件和与 BizTalk Server 附带提供的脚本完成之后 BizTalk Server 已安装并配置服务器上运行 Sysprep。 与 BizTalk Server 在 32 位和 64 位版本上安装这些示例脚本旨在用于[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]仅。 有关详细信息请参阅 BizTalk Server 联机文档。  
  
 无人参与 Windows 安装参考位于[http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364)。  
  
## <a name="see-also"></a>另请参阅  
 [附录 C：BizTalk Server 和 SQL Server Hyper-V 支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)