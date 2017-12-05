---
title: "使用 BizUnit 和 LoadGen 来自动执行性能和稳定性测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73c2a97a-6256-4010-8374-433017cb15d4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e84fcd29af6b698713623fbca556d988e037d8c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-bizunit-and-loadgen-to-automate-performance-and-stability-testing"></a>使用 BizUnit 和 LoadGen 来自动执行性能和稳定性测试
本主题提供有关如何使用 Microsoft BizTalk LoadGen 2007 工具和 BizUnit 来自动执行性能和稳定性测试 BizTalk Server 解决方案的信息。  
  
## <a name="biztalk-server-performance-testing-step-by-step"></a>BizTalk Server 性能测试的分步  
 调查如何自动执行 BizTalk Server 性能测试之前, 是有助于你了解通常在性能测试中执行哪些步骤。 以下步骤是代表"典型"BizTalk Server 性能测试过程：  
  
1.  创建一个测试结果目录来存储结果和数据收集，例如，事件日志、 跟踪日志，性能监视器数据。  
  
2.  清除测试环境内的所有服务器上的事件日志。  
  
3.  停止所有 BizTalk 主机实例。  
  
4.  停止正在运行独立的 BizTalk 主机，如 SOAP 和 HTTP 接收适配器处理程序的任何 IIS 实例。  
  
5.  重新启动计算机运行 BizTalk Server 使用的 SQL Server 的所有实例。  
  
6.  清理 MessageBox 数据库，以确保没有剩余数据来自以前的测试运行。 这非常重要，因为任何剩余的数据无法使测试结果产生偏差。  
  
7.  启动 BizTalk 主机实例。  
  
8.  在测试环境中的所有服务器上启动相关的性能监视器计数器。  
  
9. "需要"通过发送邮件系统初始化系统缓存。  
  
10. 处理需要消息后，跟踪 SQL Server 测试结果数据库中的测试开始时间。  
  
11. 通过启动 LoadGen 测试代理的所有启动的性能测试。  
  
12. 等待要完成的测试 – 通常可以系统地通过度量如主机队列长度性能监视器计数器的值。  
  
13. 跟踪测试结束时间，在 SQL 测试结果数据库。  
  
14. 在测试环境中的所有服务器上停止相关的性能监视器计数器。  
  
15. 将测试数据保存到先前创建的测试结果目录。  
  
16. 下一步的测试运行中执行任何必要的清除。  
  
 可以使用 BizUnit 自动执行每个只列出的步骤之一。 通过利用 BizUnit 提供的现有测试步骤资产，你可以快速轻松地生成适用于 BizTalk Server 解决方案自动的性能测试。 自动化使用 BizUnit 来测试性能的主要优点之一是能够灵活地运行测试夜间 – 这意味着在上午结果已准备好进行分析。 这会大大减少性能测试的项目团队的负担。  
  
## <a name="the-microsoft-biztalk-loadgen-2007-tool"></a>Microsoft BizTalk LoadGen 2007 工具  
 BizTalk LoadGen 2007 工具 (LoadGen) 是负载测试由 BizTalk Server 2006 产品组中压力和性能测试的团队开发的工具。 LoadGen 旨在快速、 轻松地，可靠地定义的负载测试中模拟生产级别的消息量。 LoadGen 多线程、 配置驱动的并支持多个传输协议。 BizTalk 产品组使用 LoadGen 每天;因此，你可以相信该工具是持久的适合目的，并且能够模拟各种 BizTalk 方案度很高。  
  
 LoadGen 采用模块化设计的三个层组成：**演示文稿**， **framework**和**组件**。 表示层包含，命令行的驱动程序，它负责驱动框架。 框架层读取配置文件，然后执行所指定的组件。 组件层包含三种类型的组件：**加载生成器**，**消息创建者**和**限制控制器**。 每个这些组件是方案的可扩展的的因此你可以创建你自己，然后将其插入 LoadGen 为了满足你。 由于 LoadGen 已开发了 BizTalk Server 产品组中，你应查找的现成可用组件将满足大部分负载测试要求。 每个组件是中更详细地此处所述。  
  
-   **加载生成器**负责传输通过特定传输的消息。 负载生成器提供下列传输：  
  
    -   文件  
  
    -   HTTP  
  
    -   MQSeries  
  
    -   MSMQLarge  
  
    -   MSMQ  
  
    -   SOAP  
  
    -   Web Services Enhancements (WSE)  
  
    -   Windows SharePoint Services (WSS)  
  
    -   Windows Communication Foundation (WCF)  
  
-   **消息创建者**是一个可选组件，可在你需要生成包含唯一的数据的消息时。 消息创建者使用两种创建; 模式之一同步和异步。 如果指定的同步消息创建模式，则 LoadGen 将使用只有一个线程来创建邮件，以确保每条消息包含唯一的负载。 在同步模式下保证每个消息中的唯一数据，此模式还限制可伸缩性。 LoadGen 还提供使用多个执行线程; 的异步消息创建者这使 LoadGen 以满足目标消息速率 （因为它可以只需创建更多的线程）。 在异步模式下，可以配置消息创建者为随机修改每个单独的消息的数据。 但是，由于它使用多个线程，它不保证在测试期间生成的所有消息将都包含唯一的负载。  
  
-   **限制控制器**确保在运行测试时控制负载生成器，以恒定速率传输消息。 LoadGen 还公开自定义的限制，从中可以控制基于条件包括对消息流：  
  
    -   文件夹中的文件数  
  
    -   数据库表中的行数  
  
    -   MSMQ 或 MQSeries 消息队列的深度  
  
 Microsoft [BizTalk LoadGen 2007 工具](http://go.microsoft.com/fwlink/?LinkId=59841)是下载[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841)。  
  
### <a name="sample-loadgen-configuration-file"></a>示例 LoadGen 配置文件  
 所有 LoadGen 配置信息都存储在 xml 文件中。 LoadGen 配置文件包含\<CommonSection\> LoadGen 方案中配置所有 LoadGen 任务的默认设置的元素。 LoadGen 配置文件还可以包含一个或多个\<部分\>提供特定的 LoadGen 任务的配置设置的元素。 中的条目\<部分\>元素取代中指定任何默认值\<CommonSection\>元素。  
  
 下面的示例 LoadGen 配置文件是包含 LoadGen 安装目录的 \ConfigFiles\ConsoleConfigFiles 子目录中的 FileToFileLG.xml 示例配置文件的略有修改的版本。 此测试将发送 25 的消息\<LotSizePerInterval\>每隔 200 毫秒\<SleepInterval\>，每个负载生成器的 5 线程\<NumThreadsperSection\>，并且将停止负载5000 消息之后，测试\<NumFiles\>已发送。  
  
 中指定的文件限制控制器\<ThrottleController\>部分。 值\<ThresholdRange\>设置为 1000年-2000，这意味着，如果该文件位置 C:\Scenarios\FileToFile\Receive （参数） 必须小于 1000年或多个 2000年文件，限制控制器将限制该文件根据负载生成器和相应增大/减少。 中的文件位置的文件数将检查每隔 1000年毫秒\<SleepInterval\>。 \<FileSection\>元素定义要由负载生成器发送的消息的属性。 FileToFileLG.xml 文件\<SrcFilePath\>将通过 LoadGen 复制到 filedrop C:\Scenarios\FileToFile\Receive \<DstFilePath >。 因为这是中指定的默认传输此处使用文件传输\<传输名称\>中的元素\<CommonSection\>元素。  
  
```  
<LoadGenFramework>  
   <CommonSection>  
      <LoadGenVersion>2</LoadGenVersion>  
      <OptimizeLimitFileSize>204800</OptimizeLimitFileSize>  
      <NumThreadsPerSection>5</NumThreadsPerSection>  
      <SleepInterval>200</SleepInterval>  
      <LotSizePerInterval>25</LotSizePerInterval>  
      <RetryInterval>10000</RetryInterval>  
      <StopMode Mode="Files">  
         <NumFiles>5000</NumFiles>  
      </StopMode>  
      <Transport Name="FILE">  
         <Assembly>FileTransport.dll/FileTransport.FileTransport</Assembly>  
      </Transport>  
      <ThrottleController Mode="Custom">  
         <Monitor Name="File">  
            <Assembly>FileMonitor.dll/DropLocationFileMonitor.DropLocationFileMonitor</Assembly>  
            <ThresholdRange>1000-2000</ThresholdRange>  
            <SleepInterval>1000</SleepInterval>  
            <Parameters>C:\Scenarios\FileToFile\Receive</Parameters>  
         </Monitor>  
         <ThrottleCondition>File</ThrottleCondition>  
      </ThrottleController>  
   </CommonSection>  
   <Section Name="FileSection">  
      <SrcFilePath>C:\LoadGen\ConfigFiles\ConsoleConfigFiles\FileToFileLG.xml</SrcFilePath>  
      <DstLocation>  
         <Parameters>  
            <DstFilePath>C:\Scenarios\FileToFile\Receive</DstFilePath>  
         </Parameters>  
      </DstLocation>  
   </Section>  
</LoadGenFramework>  
```  
  
### <a name="using-bizunit-to-drive-loadgen"></a>使用到驱动器 LoadGen BizUnit  
 BizUnit 提供**LoadGenExecuteStep**以方便进行自动完成的性能和稳定性测试。 **TestExecution**阶段使用的示例 BizUnit 配置文件**LoadGenExecuteStep**中下面的代码示例所示。 请注意，此步骤将接受一个单一配置参数，它是 LoadGen 配置文件的位置。  
  
```  
<TestCase testName="Test_LoadGen">  
   <TestSetup>  
   </TestSetup>  
   <TestExecution>  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>..\..\..\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
   </TestExecution>  
   <!-- Test cleanup: test cases should always leave the system in the state they found it -->  
   <TestCleanup>  
   </TestCleanup>  
</TestCase>  
```  
  
 本主题的其余部分介绍自动执行性能测试与 LoadGen BizUnit 测试用例的配置文件。  
  
> [!NOTE]  
>  此配置文件可以为模板，用于快速将 BizUnit 和 LoadGen 作为你性能测试的一部分的集成。 在运行之前此测试用例，你将需要自定义你的环境的配置文件。 相应地指示必须进行自定义配置文件部分。  
  
 开始时，指定的值**测试名称**适合于 BizTalk 解决方案的参数。  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
```  
  
 然后上下文将变量添加到**TestSetup**阶段。 将在测试用例的持续时间整个中引用这些上下文变量。 若要使用此配置文件，修改为指定的值**TestCaseResultsDir** (C:\Dev Work\Perf 指南 Demos\PerfResults\\) 和**机**(BIZTALKADMIN01) 以匹配你环境。  
  
```  
<TestSetup>  
   <!-- Context property: name of test run -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestRunName">  
         <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
         <ItemTest>_%DateTime%</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: name of test directory to store results -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestCaseResultsDir">  
         <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
         <ItemTest takeFromCtx="TestRunName"></ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: perfmon log file -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="PerfMonFilePath">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest>\PerfCounters.blg</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: destintation for app event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="DestPath- BIZTALKADMIN01-AppEventLog">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest> BIZTALKADMIN01_ApplicationLog.evt</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Clear the application event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
      <Machine>BIZTALKADMIN01</Machine>  
      <EventLog>Application</EventLog>  
   </TestStep>  
   <!-- Create the directory to save all the test results -->  
   <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
      <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
   </TestStep>  
</TestSetup>  
```  
  
 完成后**TestSetup**阶段中，我们输入**TestExecution**阶段。 第一步是停止 BizTalk 主机实例。 单独**BizUnit.HostConductorStep**必须为每个不同的主机实例将增加一节。 如果你的环境中使用此配置文件，你还需要输入的相应值**HostInstanceName**，**服务器**，**登录**，和**密码**。  
  
```  
<TestExecution>  
   <!-- Step 1: Stop BizTalk Hosts -->  
   <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
      <Action>stop</Action>  
      <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
      <Server>BizTalkAdmin01</Server>  
      <Logon>ServerName\Administrator</Logon>  
      <PassWord>Pass@word1</PassWord>  
      <GrantLogOnAsService>true</GrantLogOnAsService>  
   </TestStep>  
```  
  
 停止后的所有主机实例，我们使用 bts_CleanupMsgBox BizTalk MessageBox 数据库清理都存储过程。 若要使用此步骤必须修改的值**ConnectionString**以匹配你的环境。  
  
```  
<!-- Step 2: Clean Up MessageBox -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
   </SQLQuery>  
</TestStep>  
```  
  
 第 3 步**TestExecution**阶段启动模板文件中指定的性能监视器 (PerfMon) 计数器。 示例模板文件下列出示例**BizUnit.PerfmonCountersStep**下面。 若要使用的模板文件，你必须修改为指定的值**CountersListFilePath**以匹配你的环境。 修改示例性能监视器计数器模板文件，以包括你想要监视或删除任何不与你的方案相关的任何 PerfMon 计数器。  
  
```  
<!-- Step 3: Start Perfmon counters -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
   <PerfmonAction>Start</PerfmonAction>  
   <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
   <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
   <SampleInterval>5</SampleInterval>  
   <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
</TestStep>  
```  
  
 **示例性能监视器计数器模板文件 (Test_06_PerfCounters.txt BizUnit.PerfmonCountersStep 引用):**  
  
```  
\Processor(*)\*  
\Process(*)\*  
\Memory\*  
\PhysicalDisk(*)\*  
\System\Context Switches/sec  
\System\Processor Queue Length  
\BizTalk:FILE Receive Adapter(*)\*  
\BizTalk:File Send Adapter(*)\*  
\BizTalk:FTP Receive Adapter(*)\*  
\BizTalk:FTP Send Adapter(*)\*  
\BizTalk:HTTP Receive Adapter(*)\*  
\BizTalk:HTTP Send Adapter(*)\*  
\BizTalk:Message Agent(*)\*  
\BizTalk:Messaging(*)\*  
\BizTalk:Message Box:General Counters(*)\*  
\BizTalk:Message Box:Host Counters(*)\*  
\BizTalk:Messaging Latency(*)\*  
\BizTalk:SOAP Receive Adapter(*)\*  
\BizTalk:SOAP Send Adapter(*)\*  
\BizTalk:TDDS(*)\*  
\XLANG/s Orchestrations(*)\*  
```  
  
 现在我们启动 BizTalk Server 主机实例。 单独**BizUnit.HostConductorStep**部分必须添加为每个不同的主机实例 （不同包括多个实例的主机在服务器之间）。 如果你的环境中使用此配置文件，你还需要输入的相应值**HostInstanceName**，**服务器**，**登录**，和**密码**。  
  
```  
<!-- Step 4: Start BizTalk Hosts -->  
<TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <Action>start</Action>  
   <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <Logon>ServerName\Administrator</Logon>  
   <PassWord>Pass@word1</PassWord>  
   <GrantLogOnAsService>true</GrantLogOnAsService>  
</TestStep>  
```  
  
 步骤 5"primes"系统通过将一些消息发送到 BizTalk Server 使用**BizUnit.LoadGenExecuteStep**; 的值更改**LoadGenTestConfig**参数以匹配你的环境。  
  
```  
<!-- Step 5: Send Priming messages -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
```  
  
 步骤 6 LoadGen 配置文件将写入内存，以便它可以然后写入测试结果数据库完成测试时。  
  
```  
  
      <!-- Step 6: Read loadgen file into context variable -->  
<TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
   <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
   <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
</TestStep>  
```  
  
 现在我们可以测试开始时间写入测试结果数据库。 修改**ConnectionString**和**RawSQLQuery**参数以匹配你的环境。  
  
```  
<!-- Step 7: Update test results DB with test start time -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
      <SQLQueryParams>  
         <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
      </SQLQueryParams>  
   </SQLQuery>  
</TestStep>  
```  
  
 步骤 8 是其中的实际性能测试是使用启动**BizUnit.LoadGenExecuteStep**。 此步骤指定在步骤 5，已使用的相同 LoadGen 配置文件，但你可以指定任何有效 LoadGen 配置文件此处。 **BizUnit.DelayStep**在步骤 9 中用于在施加了 5 秒钟的延迟时间进行启动流经系统的消息。 使用计算主机队列长度**BizUnit.PerMonCounterMonitorStep**。 当此参数达到 1，因为在步骤 10 中指定一个值时，被结论的测试。 更改的值**InstanceName**和**服务器**参数以匹配的主机实例和你想要监视您的环境中的服务器的名称。  
  
```  
<!-- Step 8: LoadGen: Load actual perf test -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
<!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
<TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
   <Delay>5000</Delay>  
</TestStep>  
<!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
   <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
   <CounterName>Host Queue - Length</CounterName>  
   <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <CounterTargetValue>1</CounterTargetValue>  
</TestStep>  
```  
  
 在测试结束我们使用**BizUnit.DBExecuteNonQueryStep**更新测试结果数据库。 完成此步骤结束所述，则表示测试执行阶段，末尾\</TestExecution\>标记。 同样，你必须修改**ConnectionString**和**RawSQLQuery**参数以匹配你的环境。  
  
```  
   <!-- Step 11: Update test results DB with test stop time -->  
   <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
      <DelayBeforeExecution>1</DelayBeforeExecution>  
      <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
      <SQLQuery>  
         <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
         <SQLQueryParams>  
            <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         </SQLQueryParams>  
      </SQLQuery>  
   </TestStep>  
</TestExecution>  
```  
  
 在结束执行阶段中，我们将输入的测试清理阶段。 此阶段将使用**BizUnit.PerfmonCountersStep**停止以前 （在步骤 3) 启动性能监视器计数器。  
  
```  
<TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
 此示例说明如何 BizUnit 可以与结合使用 LoadGen 来自动执行性能测试。 在与功能测试相同的方式，可以从 Visual Studio 测试工具执行 BizUnit 配置文件所述的负载测试。 采用此方法可用于集中管理、 管理和收集的性能测试的数据。  
  
 通过在自动的方法中使用 BizUnit 和 LoadGen，它是非常轻松地计划要关闭小时数，此过程中将提供充足的测试结果以进行分析正常工作时间期间可能出现的多个测试运行。 时自动执行性能测试，请考虑的预期的生产消息卷的使用 LoadGen 脚本，通过系统模型不同的负载，例如你可能希望模拟不同程度 （75%、 100%和 125%）。 在执行负载测试时，它是特别重要，若要测试的重载或"错误 day"方案。 投入生产系统之前, 应了解在 BizTalk Server 环境中每个测试用例的最大可持续吞吐量 (MST) 是什么。 有关最大可持续性能的详细信息，请参阅[什么是可持续的性能？](http://go.microsoft.com/fwlink/?LinkID=132304) (http://go.microsoft.com/fwlink/?LinkID=132304) BizTalk Server 2009 文档中。  
  
### <a name="the-complete-bizunit-loadgen-sample-configuration-file"></a>完成 BizUnit LoadGen 示例配置文件  
 以下列表包含前面引用的 BizUnit 配置文件的全部内容。  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
   <TestSetup>  
      <!-- Context property: name of test run -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestRunName">  
            <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
            <ItemTest>_%DateTime%</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: name of test directory to store results -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestCaseResultsDir">  
            <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
            <ItemTest takeFromCtx="TestRunName"></ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: perfmon log file -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="PerfMonFilePath">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>\PerfCounters.blg</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: destintation for app event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="DestPath-BTSSVR-001-AppEventLog">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>BTSSVR-001_ApplicationLog.evt</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Clear the application event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
         <Machine>BIZTALKADMIN01</Machine>  
         <EventLog>Application</EventLog>  
      </TestStep>  
      <!-- Create the directory to save all the test results -->  
      <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
         <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
      </TestStep>  
   </TestSetup>  
  
   <TestExecution>  
      <!-- Step 1: Stop BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
         <Action>stop</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 2: Clean Up MessageBox -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 3: Start Perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
         <PerfmonAction>Start</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
         <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
         <SampleInterval>5</SampleInterval>  
         <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
      </TestStep>  
      <!-- Step 4: Start BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
         <Action>start</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 5: Send Priming messages -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 6: Read loadgen file into context variable -->  
      <TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
         <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
         <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
      </TestStep>  
      <!-- Step 7: Update test results DB with test start time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
               <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 8: LoadGen: Load actual perf test -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
        <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
      <TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
         <Delay>5000</Delay>  
      </TestStep>  
      <!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
         <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
         <CounterName>Host Queue - Length</CounterName>  
         <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <CounterTargetValue>1</CounterTargetValue>  
      </TestStep>  
      <!-- Step 11: Update test results DB with test stop time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
   </TestExecution>  
  
   <TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizUnit 优化自动测试](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)