---
title: 使用 BizUnit 和 LoadGen 来自动执行性能和稳定性测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73c2a97a-6256-4010-8374-433017cb15d4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e84fcd29af6b698713623fbca556d988e037d8c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976275"
---
# <a name="using-bizunit-and-loadgen-to-automate-performance-and-stability-testing"></a><span data-ttu-id="a774e-102">使用 BizUnit 和 LoadGen 来自动执行性能和稳定性测试</span><span class="sxs-lookup"><span data-stu-id="a774e-102">Using BizUnit and LoadGen to Automate Performance and Stability Testing</span></span>
<span data-ttu-id="a774e-103">本主题提供有关如何使用 Microsoft BizTalk LoadGen 2007 工具和 BizUnit 来自动执行性能和稳定性测试 BizTalk Server 解决方案的信息。</span><span class="sxs-lookup"><span data-stu-id="a774e-103">This topic provides information about how to use the Microsoft BizTalk LoadGen 2007 tool with BizUnit to automate performance and stability testing of a BizTalk Server solution.</span></span>  
  
## <a name="biztalk-server-performance-testing-step-by-step"></a><span data-ttu-id="a774e-104">BizTalk Server 性能测试的分步</span><span class="sxs-lookup"><span data-stu-id="a774e-104">BizTalk Server performance testing, step-by-step</span></span>  
 <span data-ttu-id="a774e-105">调查如何自动执行 BizTalk Server 性能测试之前, 是有助于你了解通常在性能测试中执行哪些步骤。</span><span class="sxs-lookup"><span data-stu-id="a774e-105">Before investigating how to automate BizTalk Server performance testing, it is useful to know what steps are typically performed in a performance test.</span></span> <span data-ttu-id="a774e-106">以下步骤是代表"典型"BizTalk Server 性能测试过程：</span><span class="sxs-lookup"><span data-stu-id="a774e-106">The following steps are representative of a “typical” BizTalk Server performance testing process:</span></span>  
  
1.  <span data-ttu-id="a774e-107">创建一个测试结果目录来存储结果和数据收集，例如，事件日志、 跟踪日志，性能监视器数据。</span><span class="sxs-lookup"><span data-stu-id="a774e-107">Create a test results directory to store results and data collected, for example, event logs, trace logs, Performance Monitor data.</span></span>  
  
2.  <span data-ttu-id="a774e-108">清除测试环境内的所有服务器上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="a774e-108">Clear the event logs on all servers within the test environment.</span></span>  
  
3.  <span data-ttu-id="a774e-109">停止所有 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="a774e-109">Stop all BizTalk host instances.</span></span>  
  
4.  <span data-ttu-id="a774e-110">停止正在运行独立的 BizTalk 主机，如 SOAP 和 HTTP 接收适配器处理程序的任何 IIS 实例。</span><span class="sxs-lookup"><span data-stu-id="a774e-110">Stop any IIS instances that are running isolated BizTalk hosts such as the SOAP and HTTP receive adapter handlers.</span></span>  
  
5.  <span data-ttu-id="a774e-111">重新启动计算机运行 BizTalk Server 使用的 SQL Server 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="a774e-111">Restart all instances of SQL Server used by the computers running BizTalk Server.</span></span>  
  
6.  <span data-ttu-id="a774e-112">清理 MessageBox 数据库，以确保没有剩余数据来自以前的测试运行。</span><span class="sxs-lookup"><span data-stu-id="a774e-112">Clean up the MessageBox database to ensure that there is no leftover data from previous tests runs.</span></span> <span data-ttu-id="a774e-113">这非常重要，因为任何剩余的数据无法使测试结果产生偏差。</span><span class="sxs-lookup"><span data-stu-id="a774e-113">This is important because any leftover data could skew test results.</span></span>  
  
7.  <span data-ttu-id="a774e-114">启动 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="a774e-114">Start the BizTalk host instances.</span></span>  
  
8.  <span data-ttu-id="a774e-115">在测试环境中的所有服务器上启动相关的性能监视器计数器。</span><span class="sxs-lookup"><span data-stu-id="a774e-115">Start the relevant Performance Monitor counters on all servers in the test environment.</span></span>  
  
9. <span data-ttu-id="a774e-116">"需要"通过发送邮件系统初始化系统缓存。</span><span class="sxs-lookup"><span data-stu-id="a774e-116">Send “priming” messages through the system to initialize the system caches.</span></span>  
  
10. <span data-ttu-id="a774e-117">处理需要消息后，跟踪 SQL Server 测试结果数据库中的测试开始时间。</span><span class="sxs-lookup"><span data-stu-id="a774e-117">After the priming messages have been processed, track the test start time in a SQL Server test results database.</span></span>  
  
11. <span data-ttu-id="a774e-118">通过启动 LoadGen 测试代理的所有启动的性能测试。</span><span class="sxs-lookup"><span data-stu-id="a774e-118">Start the performance test by starting all of the LoadGen test agents.</span></span>  
  
12. <span data-ttu-id="a774e-119">等待要完成的测试 – 通常可以系统地通过度量如主机队列长度性能监视器计数器的值。</span><span class="sxs-lookup"><span data-stu-id="a774e-119">Wait for the test to complete – often this can be done systematically by measuring the value of a Performance Monitor counter such as host queue length.</span></span>  
  
13. <span data-ttu-id="a774e-120">跟踪测试结束时间，在 SQL 测试结果数据库。</span><span class="sxs-lookup"><span data-stu-id="a774e-120">Track test end time in a SQL test results database.</span></span>  
  
14. <span data-ttu-id="a774e-121">在测试环境中的所有服务器上停止相关的性能监视器计数器。</span><span class="sxs-lookup"><span data-stu-id="a774e-121">Stop the relevant Performance Monitor counters on all servers in the test environment.</span></span>  
  
15. <span data-ttu-id="a774e-122">将测试数据保存到先前创建的测试结果目录。</span><span class="sxs-lookup"><span data-stu-id="a774e-122">Save the test data to the test results directory that was created earlier.</span></span>  
  
16. <span data-ttu-id="a774e-123">下一步的测试运行中执行任何必要的清除。</span><span class="sxs-lookup"><span data-stu-id="a774e-123">Perform any necessary cleanup for the next test run.</span></span>  
  
 <span data-ttu-id="a774e-124">可以使用 BizUnit 自动执行每个只列出的步骤之一。</span><span class="sxs-lookup"><span data-stu-id="a774e-124">Each and every one of the steps just listed can be automated using BizUnit.</span></span> <span data-ttu-id="a774e-125">通过利用 BizUnit 提供的现有测试步骤资产，你可以快速轻松地生成适用于 BizTalk Server 解决方案自动的性能测试。</span><span class="sxs-lookup"><span data-stu-id="a774e-125">By utilizing the existing test step assets that BizUnit provides, you can quickly and easily generate an automated performance test for a BizTalk Server solution.</span></span> <span data-ttu-id="a774e-126">自动化使用 BizUnit 来测试性能的主要优点之一是能够灵活地运行测试夜间 – 这意味着在上午结果已准备好进行分析。</span><span class="sxs-lookup"><span data-stu-id="a774e-126">One of the primary benefits of automating performance testing by using BizUnit is the flexibility to run tests overnight – meaning that the results are ready for analysis in the morning.</span></span> <span data-ttu-id="a774e-127">这会大大减少性能测试的项目团队的负担。</span><span class="sxs-lookup"><span data-stu-id="a774e-127">This greatly reduces the burden of performance testing on a project team.</span></span>  
  
## <a name="the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="a774e-128">Microsoft BizTalk LoadGen 2007 工具</span><span class="sxs-lookup"><span data-stu-id="a774e-128">The Microsoft BizTalk LoadGen 2007 tool</span></span>  
 <span data-ttu-id="a774e-129">BizTalk LoadGen 2007 工具 (LoadGen) 是负载测试由 BizTalk Server 2006 产品组中压力和性能测试的团队开发的工具。</span><span class="sxs-lookup"><span data-stu-id="a774e-129">The BizTalk LoadGen 2007 tool (LoadGen) is a load testing tool that was developed by the Stress and Performance Testing team in the BizTalk Server 2006 product group.</span></span> <span data-ttu-id="a774e-130">LoadGen 旨在快速、 轻松地，可靠地定义的负载测试中模拟生产级别的消息量。</span><span class="sxs-lookup"><span data-stu-id="a774e-130">LoadGen was designed to quickly, easily, and reliably define load tests that simulate production level message volumes.</span></span> <span data-ttu-id="a774e-131">LoadGen 多线程、 配置驱动的并支持多个传输协议。</span><span class="sxs-lookup"><span data-stu-id="a774e-131">LoadGen is multi-threaded, configuration-driven, and supports multiple transports.</span></span> <span data-ttu-id="a774e-132">BizTalk 产品组使用 LoadGen 每天;因此，你可以相信该工具是持久的适合目的，并且能够模拟各种 BizTalk 方案度很高。</span><span class="sxs-lookup"><span data-stu-id="a774e-132">The BizTalk product group uses LoadGen on a daily basis; therefore you can have a high degree of confidence that the tool is durable, fit for the purpose, and able to simulate a wide variety of BizTalk scenarios.</span></span>  
  
 <span data-ttu-id="a774e-133">LoadGen 采用模块化设计的三个层组成：**演示文稿**， **framework**和**组件**。</span><span class="sxs-lookup"><span data-stu-id="a774e-133">LoadGen employs a modular design that consists of three layers: **presentation**, **framework** and **component**.</span></span> <span data-ttu-id="a774e-134">表示层包含，命令行的驱动程序，它负责驱动框架。</span><span class="sxs-lookup"><span data-stu-id="a774e-134">The presentation layer consists of a command-line driver, which is responsible for driving the framework.</span></span> <span data-ttu-id="a774e-135">框架层读取配置文件，然后执行所指定的组件。</span><span class="sxs-lookup"><span data-stu-id="a774e-135">The framework layer reads a configuration file and then executes the components specified therein.</span></span> <span data-ttu-id="a774e-136">组件层包含三种类型的组件：**加载生成器**，**消息创建者**和**限制控制器**。</span><span class="sxs-lookup"><span data-stu-id="a774e-136">The component layer consists of three types of components: **load generators**, **message creators** and **throttle controllers**.</span></span> <span data-ttu-id="a774e-137">每个这些组件是方案的可扩展的的因此你可以创建你自己，然后将其插入 LoadGen 为了满足你。</span><span class="sxs-lookup"><span data-stu-id="a774e-137">Each of these components is extensible, so you can create your own and plug them into LoadGen to address the needs of your scenario.</span></span> <span data-ttu-id="a774e-138">由于 LoadGen 已开发了 BizTalk Server 产品组中，你应查找的现成可用组件将满足大部分负载测试要求。</span><span class="sxs-lookup"><span data-stu-id="a774e-138">Because LoadGen was developed by the BizTalk Server product group, you should find that the out-of-the-box components will fulfill most of your load testing requirements.</span></span> <span data-ttu-id="a774e-139">每个组件是中更详细地此处所述。</span><span class="sxs-lookup"><span data-stu-id="a774e-139">Each of these components is described in greater detail here.</span></span>  
  
-   <span data-ttu-id="a774e-140">**加载生成器**负责传输通过特定传输的消息。</span><span class="sxs-lookup"><span data-stu-id="a774e-140">**Load generators** are responsible for transmitting messages via a particular transport.</span></span> <span data-ttu-id="a774e-141">负载生成器提供下列传输：</span><span class="sxs-lookup"><span data-stu-id="a774e-141">Load generators are provided for the following transports:</span></span>  
  
    -   <span data-ttu-id="a774e-142">文件</span><span class="sxs-lookup"><span data-stu-id="a774e-142">File</span></span>  
  
    -   <span data-ttu-id="a774e-143">HTTP</span><span class="sxs-lookup"><span data-stu-id="a774e-143">HTTP</span></span>  
  
    -   <span data-ttu-id="a774e-144">MQSeries</span><span class="sxs-lookup"><span data-stu-id="a774e-144">MQSeries</span></span>  
  
    -   <span data-ttu-id="a774e-145">MSMQLarge</span><span class="sxs-lookup"><span data-stu-id="a774e-145">MSMQLarge</span></span>  
  
    -   <span data-ttu-id="a774e-146">MSMQ</span><span class="sxs-lookup"><span data-stu-id="a774e-146">MSMQ</span></span>  
  
    -   <span data-ttu-id="a774e-147">SOAP</span><span class="sxs-lookup"><span data-stu-id="a774e-147">SOAP</span></span>  
  
    -   <span data-ttu-id="a774e-148">Web Services Enhancements (WSE)</span><span class="sxs-lookup"><span data-stu-id="a774e-148">Web Services Enhancements (WSE)</span></span>  
  
    -   <span data-ttu-id="a774e-149">Windows SharePoint Services (WSS)</span><span class="sxs-lookup"><span data-stu-id="a774e-149">Windows SharePoint Services (WSS)</span></span>  
  
    -   <span data-ttu-id="a774e-150">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="a774e-150">Windows Communication Foundation (WCF)</span></span>  
  
-   <span data-ttu-id="a774e-151">**消息创建者**是一个可选组件，可在你需要生成包含唯一的数据的消息时。</span><span class="sxs-lookup"><span data-stu-id="a774e-151">**Message creators** are an optional component that can be used when you need to generate messages that contain unique data.</span></span> <span data-ttu-id="a774e-152">消息创建者使用两种创建; 模式之一同步和异步。</span><span class="sxs-lookup"><span data-stu-id="a774e-152">Message creators use one of two modes of creation; synchronous and asynchronous.</span></span> <span data-ttu-id="a774e-153">如果指定的同步消息创建模式，则 LoadGen 将使用只有一个线程来创建邮件，以确保每条消息包含唯一的负载。</span><span class="sxs-lookup"><span data-stu-id="a774e-153">If the synchronous message creation mode is specified, LoadGen uses only a single thread to create messages to ensure that each message contains a unique payload.</span></span> <span data-ttu-id="a774e-154">在同步模式下保证每个消息中的唯一数据，此模式还限制可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="a774e-154">While the synchronous mode guarantees unique data within each message, this mode also limits scalability.</span></span> <span data-ttu-id="a774e-155">LoadGen 还提供使用多个执行线程; 的异步消息创建者这使 LoadGen 以满足目标消息速率 （因为它可以只需创建更多的线程）。</span><span class="sxs-lookup"><span data-stu-id="a774e-155">LoadGen also provides asynchronous message creators that use multiple execution threads; this enables LoadGen to meet the target message rate (because it can simply create more threads).</span></span> <span data-ttu-id="a774e-156">在异步模式下，可以配置消息创建者为随机修改每个单独的消息的数据。</span><span class="sxs-lookup"><span data-stu-id="a774e-156">In asynchronous mode, the message creator may be configured to randomly modify data for each individual message.</span></span> <span data-ttu-id="a774e-157">但是，由于它使用多个线程，它不保证在测试期间生成的所有消息将都包含唯一的负载。</span><span class="sxs-lookup"><span data-stu-id="a774e-157">However, because it uses multiple threads, it does not guarantee that all message generated during the test will contain a unique payload.</span></span>  
  
-   <span data-ttu-id="a774e-158">**限制控制器**确保在运行测试时控制负载生成器，以恒定速率传输消息。</span><span class="sxs-lookup"><span data-stu-id="a774e-158">**Throttle controllers** ensure that messages are transmitted at a steady rate by governing the load generators while the test is running.</span></span> <span data-ttu-id="a774e-159">LoadGen 还公开自定义的限制，从中可以控制基于条件包括对消息流：</span><span class="sxs-lookup"><span data-stu-id="a774e-159">LoadGen also exposes custom throttling, which enables you to control the flow of messages based on criteria including:</span></span>  
  
    -   <span data-ttu-id="a774e-160">文件夹中的文件数</span><span class="sxs-lookup"><span data-stu-id="a774e-160">Number of files in a folder</span></span>  
  
    -   <span data-ttu-id="a774e-161">数据库表中的行数</span><span class="sxs-lookup"><span data-stu-id="a774e-161">Number of rows in a database table</span></span>  
  
    -   <span data-ttu-id="a774e-162">MSMQ 或 MQSeries 消息队列的深度</span><span class="sxs-lookup"><span data-stu-id="a774e-162">Depth of an MSMQ or MQSeries message queue</span></span>  
  
 <span data-ttu-id="a774e-163">Microsoft [BizTalk LoadGen 2007 工具](http://go.microsoft.com/fwlink/?LinkId=59841)是下载[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841)。</span><span class="sxs-lookup"><span data-stu-id="a774e-163">The Microsoft [BizTalk LoadGen 2007 tool](http://go.microsoft.com/fwlink/?LinkId=59841) is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841).</span></span>  
  
### <a name="sample-loadgen-configuration-file"></a><span data-ttu-id="a774e-164">示例 LoadGen 配置文件</span><span class="sxs-lookup"><span data-stu-id="a774e-164">Sample LoadGen configuration file</span></span>  
 <span data-ttu-id="a774e-165">所有 LoadGen 配置信息都存储在 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="a774e-165">All LoadGen configuration information is stored in an xml file.</span></span> <span data-ttu-id="a774e-166">LoadGen 配置文件包含\<CommonSection\> LoadGen 方案中配置所有 LoadGen 任务的默认设置的元素。</span><span class="sxs-lookup"><span data-stu-id="a774e-166">The LoadGen configuration file contains a \<CommonSection\> element that configures the default settings for all LoadGen tasks in the LoadGen scenario.</span></span> <span data-ttu-id="a774e-167">LoadGen 配置文件还可以包含一个或多个\<部分\>提供特定的 LoadGen 任务的配置设置的元素。</span><span class="sxs-lookup"><span data-stu-id="a774e-167">The LoadGen configuration file can also contain one or more \<Section\> elements that provide configuration settings for a specific LoadGen task.</span></span> <span data-ttu-id="a774e-168">中的条目\<部分\>元素取代中指定任何默认值\<CommonSection\>元素。</span><span class="sxs-lookup"><span data-stu-id="a774e-168">Entries in a \<Section\> element supersede any default values specified in the \<CommonSection\> element.</span></span>  
  
 <span data-ttu-id="a774e-169">下面的示例 LoadGen 配置文件是包含 LoadGen 安装目录的 \ConfigFiles\ConsoleConfigFiles 子目录中的 FileToFileLG.xml 示例配置文件的略有修改的版本。</span><span class="sxs-lookup"><span data-stu-id="a774e-169">The sample LoadGen configuration file that follows is a slightly modified version of the FileToFileLG.xml sample configuration file that is included in the \ConfigFiles\ConsoleConfigFiles subdirectory of the LoadGen installation directory.</span></span> <span data-ttu-id="a774e-170">此测试将发送 25 的消息\<LotSizePerInterval\>每隔 200 毫秒\<SleepInterval\>，每个负载生成器的 5 线程\<NumThreadsperSection\>，并且将停止负载5000 消息之后，测试\<NumFiles\>已发送。</span><span class="sxs-lookup"><span data-stu-id="a774e-170">This test sends 25 messages \<LotSizePerInterval\> every 200 milliseconds \<SleepInterval\>, 5 threads per load generator \<NumThreadsperSection\>and will stop the load test after 5000 messages \<NumFiles\> have been sent.</span></span>  
  
 <span data-ttu-id="a774e-171">中指定的文件限制控制器\<ThrottleController\>部分。</span><span class="sxs-lookup"><span data-stu-id="a774e-171">The file throttle controller is specified in the \<ThrottleController\> section.</span></span> <span data-ttu-id="a774e-172">值\<ThresholdRange\>设置为 1000年-2000，这意味着，如果该文件位置 C:\Scenarios\FileToFile\Receive （参数） 必须小于 1000年或多个 2000年文件，限制控制器将限制该文件根据负载生成器和相应增大/减少。</span><span class="sxs-lookup"><span data-stu-id="a774e-172">The value for \<ThresholdRange\> is set to 1000-2000, which means that if the file location C:\Scenarios\FileToFile\Receive (Parameters) has less than 1000 or more than 2000 files, the throttle controller will throttle the file generator and increase/decrease load as appropriate.</span></span> <span data-ttu-id="a774e-173">中的文件位置的文件数将检查每隔 1000年毫秒\<SleepInterval\>。</span><span class="sxs-lookup"><span data-stu-id="a774e-173">The number of files in the file location will be checked every 1000 milliseconds \<SleepInterval\>.</span></span> <span data-ttu-id="a774e-174">\<FileSection\>元素定义要由负载生成器发送的消息的属性。</span><span class="sxs-lookup"><span data-stu-id="a774e-174">The \<FileSection\> element defines the properties for the messages to be sent by the load generators.</span></span> <span data-ttu-id="a774e-175">FileToFileLG.xml 文件\<SrcFilePath\>将通过 LoadGen 复制到 filedrop C:\Scenarios\FileToFile\Receive \<DstFilePath >。</span><span class="sxs-lookup"><span data-stu-id="a774e-175">The FileToFileLG.xml file \<SrcFilePath\> will be copied by LoadGen to the filedrop C:\Scenarios\FileToFile\Receive \<DstFilePath>.</span></span> <span data-ttu-id="a774e-176">因为这是中指定的默认传输此处使用文件传输\<传输名称\>中的元素\<CommonSection\>元素。</span><span class="sxs-lookup"><span data-stu-id="a774e-176">The file transport is used here because this is the default transport specified in the \<Transport Name\> element within the \<CommonSection\> element.</span></span>  
  
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
  
### <a name="using-bizunit-to-drive-loadgen"></a><span data-ttu-id="a774e-177">使用到驱动器 LoadGen BizUnit</span><span class="sxs-lookup"><span data-stu-id="a774e-177">Using BizUnit to drive LoadGen</span></span>  
 <span data-ttu-id="a774e-178">BizUnit 提供**LoadGenExecuteStep**以方便进行自动完成的性能和稳定性测试。</span><span class="sxs-lookup"><span data-stu-id="a774e-178">BizUnit provides the **LoadGenExecuteStep** to facilitate automated performance and stability testing.</span></span> <span data-ttu-id="a774e-179">**TestExecution**阶段使用的示例 BizUnit 配置文件**LoadGenExecuteStep**中下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="a774e-179">The **TestExecution** stage of a sample BizUnit configuration file that uses **LoadGenExecuteStep** is shown in the following code example.</span></span> <span data-ttu-id="a774e-180">请注意，此步骤将接受一个单一配置参数，它是 LoadGen 配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="a774e-180">Note that this step accepts a single configuration parameter, which is the location of the LoadGen configuration file.</span></span>  
  
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
  
 <span data-ttu-id="a774e-181">本主题的其余部分介绍自动执行性能测试与 LoadGen BizUnit 测试用例的配置文件。</span><span class="sxs-lookup"><span data-stu-id="a774e-181">The remainder of this topic describes the configuration file for a BizUnit test case that automates performance testing with LoadGen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a774e-182">此配置文件可以为模板，用于快速将 BizUnit 和 LoadGen 作为你性能测试的一部分的集成。</span><span class="sxs-lookup"><span data-stu-id="a774e-182">This configuration file can be used as a template to quickly integrate BizUnit and LoadGen as part of your performance testing.</span></span> <span data-ttu-id="a774e-183">在运行之前此测试用例，你将需要自定义你的环境的配置文件。</span><span class="sxs-lookup"><span data-stu-id="a774e-183">Before running this test case, you will need to customize the configuration file for your environment.</span></span> <span data-ttu-id="a774e-184">相应地指示必须进行自定义配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="a774e-184">Sections of the configuration file that must be customized are indicated accordingly.</span></span>  
  
 <span data-ttu-id="a774e-185">开始时，指定的值**测试名称**适合于 BizTalk 解决方案的参数。</span><span class="sxs-lookup"><span data-stu-id="a774e-185">To begin with, specify a value for the **testName** parameter that is appropriate for the BizTalk solution.</span></span>  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
```  
  
 <span data-ttu-id="a774e-186">然后上下文将变量添加到**TestSetup**阶段。</span><span class="sxs-lookup"><span data-stu-id="a774e-186">Then add context variables to the **TestSetup** stage.</span></span> <span data-ttu-id="a774e-187">将在测试用例的持续时间整个中引用这些上下文变量。</span><span class="sxs-lookup"><span data-stu-id="a774e-187">These context variables will be referenced throughout the duration of the test case.</span></span> <span data-ttu-id="a774e-188">若要使用此配置文件，修改为指定的值**TestCaseResultsDir** (C:\Dev Work\Perf 指南 Demos\PerfResults\\) 和**机**(BIZTALKADMIN01) 以匹配你环境。</span><span class="sxs-lookup"><span data-stu-id="a774e-188">To use this configuration file, modify the values specified for **TestCaseResultsDir** (C:\Dev Work\Perf Guide Demos\PerfResults\\) and **Machine** (BIZTALKADMIN01) to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="a774e-189">完成后**TestSetup**阶段中，我们输入**TestExecution**阶段。</span><span class="sxs-lookup"><span data-stu-id="a774e-189">After completing the **TestSetup** stage, we enter the **TestExecution** stage.</span></span> <span data-ttu-id="a774e-190">第一步是停止 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="a774e-190">The first step is to stop the BizTalk host instances.</span></span> <span data-ttu-id="a774e-191">单独**BizUnit.HostConductorStep**必须为每个不同的主机实例将增加一节。</span><span class="sxs-lookup"><span data-stu-id="a774e-191">A separate **BizUnit.HostConductorStep** section must be added for each distinct host instance.</span></span> <span data-ttu-id="a774e-192">如果你的环境中使用此配置文件，你还需要输入的相应值**HostInstanceName**，**服务器**，**登录**，和**密码**。</span><span class="sxs-lookup"><span data-stu-id="a774e-192">If you are using this configuration file in your environment, you will also need to enter the appropriate values for **HostInstanceName**, **Server**, **Logon**, and **Password**.</span></span>  
  
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
  
 <span data-ttu-id="a774e-193">停止后的所有主机实例，我们使用 bts_CleanupMsgBox BizTalk MessageBox 数据库清理都存储过程。</span><span class="sxs-lookup"><span data-stu-id="a774e-193">After stopping all of the host instances, we clean up the BizTalk MessageBox database using the bts_CleanupMsgBox stored procedure.</span></span> <span data-ttu-id="a774e-194">若要使用此步骤必须修改的值**ConnectionString**以匹配你的环境。</span><span class="sxs-lookup"><span data-stu-id="a774e-194">To use this step you must modify the value for **ConnectionString** to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="a774e-195">第 3 步**TestExecution**阶段启动模板文件中指定的性能监视器 (PerfMon) 计数器。</span><span class="sxs-lookup"><span data-stu-id="a774e-195">Step 3 of the **TestExecution** stage starts Performance Monitor (PerfMon) counters that are specified in a template file.</span></span> <span data-ttu-id="a774e-196">示例模板文件下列出示例**BizUnit.PerfmonCountersStep**下面。</span><span class="sxs-lookup"><span data-stu-id="a774e-196">A sample template file is listed underneath the sample **BizUnit.PerfmonCountersStep** below.</span></span> <span data-ttu-id="a774e-197">若要使用的模板文件，你必须修改为指定的值**CountersListFilePath**以匹配你的环境。</span><span class="sxs-lookup"><span data-stu-id="a774e-197">To use the template file, you must modify the value specified for **CountersListFilePath** to match your environment.</span></span> <span data-ttu-id="a774e-198">修改示例性能监视器计数器模板文件，以包括你想要监视或删除任何不与你的方案相关的任何 PerfMon 计数器。</span><span class="sxs-lookup"><span data-stu-id="a774e-198">Modify the sample performance monitor counter template file to include any PerfMon counters that you would like to monitor or remove any that are not relevant to your scenario.</span></span>  
  
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
  
 <span data-ttu-id="a774e-199">**示例性能监视器计数器模板文件 (Test_06_PerfCounters.txt BizUnit.PerfmonCountersStep 引用):**</span><span class="sxs-lookup"><span data-stu-id="a774e-199">**Sample Performance Monitor counter template file (Test_06_PerfCounters.txt referenced by the BizUnit.PerfmonCountersStep):**</span></span>  
  
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
  
 <span data-ttu-id="a774e-200">现在我们启动 BizTalk Server 主机实例。</span><span class="sxs-lookup"><span data-stu-id="a774e-200">Now we start the BizTalk Server host instances.</span></span> <span data-ttu-id="a774e-201">单独**BizUnit.HostConductorStep**部分必须添加为每个不同的主机实例 （不同包括多个实例的主机在服务器之间）。</span><span class="sxs-lookup"><span data-stu-id="a774e-201">A separate **BizUnit.HostConductorStep** section must be added for each distinct host instance (distinct includes multiple instances of a host across servers).</span></span> <span data-ttu-id="a774e-202">如果你的环境中使用此配置文件，你还需要输入的相应值**HostInstanceName**，**服务器**，**登录**，和**密码**。</span><span class="sxs-lookup"><span data-stu-id="a774e-202">If you are using this configuration file in your environment, you will also need to enter the appropriate values for **HostInstanceName**, **Server**, **Logon**, and **Password**.</span></span>  
  
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
  
 <span data-ttu-id="a774e-203">步骤 5"primes"系统通过将一些消息发送到 BizTalk Server 使用**BizUnit.LoadGenExecuteStep**; 的值更改**LoadGenTestConfig**参数以匹配你的环境。</span><span class="sxs-lookup"><span data-stu-id="a774e-203">Step 5 “primes” the system by sending a couple of messages to BizTalk Server using **BizUnit.LoadGenExecuteStep**; change the value of the **LoadGenTestConfig** parameter to match your environment.</span></span>  
  
```  
<!-- Step 5: Send Priming messages -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
```  
  
 <span data-ttu-id="a774e-204">步骤 6 LoadGen 配置文件将写入内存，以便它可以然后写入测试结果数据库完成测试时。</span><span class="sxs-lookup"><span data-stu-id="a774e-204">Step 6 writes the LoadGen configuration file to memory so that it can then be written to the test results database when the test is complete.</span></span>  
  
```  
  
      <!-- Step 6: Read loadgen file into context variable -->  
<TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
   <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
   <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
</TestStep>  
```  
  
 <span data-ttu-id="a774e-205">现在我们可以测试开始时间写入测试结果数据库。</span><span class="sxs-lookup"><span data-stu-id="a774e-205">Now we write the test start time to a test results database.</span></span> <span data-ttu-id="a774e-206">修改**ConnectionString**和**RawSQLQuery**参数以匹配你的环境。</span><span class="sxs-lookup"><span data-stu-id="a774e-206">Modify the **ConnectionString** and **RawSQLQuery** parameters to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="a774e-207">步骤 8 是其中的实际性能测试是使用启动**BizUnit.LoadGenExecuteStep**。</span><span class="sxs-lookup"><span data-stu-id="a774e-207">Step 8 is where the actual performance test is initiated using **BizUnit.LoadGenExecuteStep**.</span></span> <span data-ttu-id="a774e-208">此步骤指定在步骤 5，已使用的相同 LoadGen 配置文件，但你可以指定任何有效 LoadGen 配置文件此处。</span><span class="sxs-lookup"><span data-stu-id="a774e-208">This step specifies the same LoadGen configuration file that was used in step 5, but you can specify any valid LoadGen configuration file here.</span></span> <span data-ttu-id="a774e-209">**BizUnit.DelayStep**在步骤 9 中用于在施加了 5 秒钟的延迟时间进行启动流经系统的消息。</span><span class="sxs-lookup"><span data-stu-id="a774e-209">**BizUnit.DelayStep** is used in step 9 to impose a 5-second delay to allow time for messages to start flowing through the system.</span></span> <span data-ttu-id="a774e-210">使用计算主机队列长度**BizUnit.PerMonCounterMonitorStep**。</span><span class="sxs-lookup"><span data-stu-id="a774e-210">Host queue length is calculated using **BizUnit.PerMonCounterMonitorStep**.</span></span> <span data-ttu-id="a774e-211">当此参数达到 1，因为在步骤 10 中指定一个值时，被结论的测试。</span><span class="sxs-lookup"><span data-stu-id="a774e-211">When this parameter reaches a value of 1 as specified in step 10, the test is concluded.</span></span> <span data-ttu-id="a774e-212">更改的值**InstanceName**和**服务器**参数以匹配的主机实例和你想要监视您的环境中的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="a774e-212">Change the values for the **InstanceName** and **Server** parameters to match the name of the host instance and server that you would like to monitor in your environment.</span></span>  
  
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
  
 <span data-ttu-id="a774e-213">在测试结束我们使用**BizUnit.DBExecuteNonQueryStep**更新测试结果数据库。</span><span class="sxs-lookup"><span data-stu-id="a774e-213">At the conclusion of the test we use **BizUnit.DBExecuteNonQueryStep** to update the test results database.</span></span> <span data-ttu-id="a774e-214">完成此步骤结束所述，则表示测试执行阶段，末尾\</TestExecution\>标记。</span><span class="sxs-lookup"><span data-stu-id="a774e-214">Completion of this step signifies the end of the test execution stage, as indicated by the closing \</TestExecution\> tag.</span></span> <span data-ttu-id="a774e-215">同样，你必须修改**ConnectionString**和**RawSQLQuery**参数以匹配你的环境。</span><span class="sxs-lookup"><span data-stu-id="a774e-215">Again, you must modify the **ConnectionString** and **RawSQLQuery** parameters to match your environment.</span></span>  
  
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
  
 <span data-ttu-id="a774e-216">在结束执行阶段中，我们将输入的测试清理阶段。</span><span class="sxs-lookup"><span data-stu-id="a774e-216">Upon concluding the execution stage we enter the test cleanup stage.</span></span> <span data-ttu-id="a774e-217">此阶段将使用**BizUnit.PerfmonCountersStep**停止以前 （在步骤 3) 启动性能监视器计数器。</span><span class="sxs-lookup"><span data-stu-id="a774e-217">This stage uses **BizUnit.PerfmonCountersStep** to stop the Performance Monitor counters that were started earlier (in Step 3).</span></span>  
  
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
  
 <span data-ttu-id="a774e-218">此示例说明如何 BizUnit 可以与结合使用 LoadGen 来自动执行性能测试。</span><span class="sxs-lookup"><span data-stu-id="a774e-218">This example illustrated how BizUnit can be combined with LoadGen to automate performance testing.</span></span> <span data-ttu-id="a774e-219">在与功能测试相同的方式，可以从 Visual Studio 测试工具执行 BizUnit 配置文件所述的负载测试。</span><span class="sxs-lookup"><span data-stu-id="a774e-219">The load test described by the BizUnit configuration file can be executed from Visual Studio’s testing tools in the same manner as the functional testing.</span></span> <span data-ttu-id="a774e-220">采用此方法可用于集中管理、 管理和收集的性能测试的数据。</span><span class="sxs-lookup"><span data-stu-id="a774e-220">Adopting this approach enables you to centrally manage, administer, and collect data for your performance testing.</span></span>  
  
 <span data-ttu-id="a774e-221">通过在自动的方法中使用 BizUnit 和 LoadGen，它是非常轻松地计划要关闭小时数，此过程中将提供充足的测试结果以进行分析正常工作时间期间可能出现的多个测试运行。</span><span class="sxs-lookup"><span data-stu-id="a774e-221">By using BizUnit and LoadGen in an automated approach, it is very easy to schedule multiple test runs to occur during off hours, which will provide ample test results for analysis during normal working hours.</span></span> <span data-ttu-id="a774e-222">时自动执行性能测试，请考虑的预期的生产消息卷的使用 LoadGen 脚本，通过系统模型不同的负载，例如你可能希望模拟不同程度 （75%、 100%和 125%）。</span><span class="sxs-lookup"><span data-stu-id="a774e-222">When automating performance testing, consider using LoadGen scripts that model different loads through the system, for example you may wish to simulate varying degrees (75%, 100% and 125%) of the expected production message volume.</span></span> <span data-ttu-id="a774e-223">在执行负载测试时，它是特别重要，若要测试的重载或"错误 day"方案。</span><span class="sxs-lookup"><span data-stu-id="a774e-223">When performing load testing, it is especially important to test the overload or “bad day” scenario.</span></span> <span data-ttu-id="a774e-224">投入生产系统之前, 应了解在 BizTalk Server 环境中每个测试用例的最大可持续吞吐量 (MST) 是什么。</span><span class="sxs-lookup"><span data-stu-id="a774e-224">Before placing the system into production, you should know what the maximum sustainable throughput (MST) is for each test case in the BizTalk Server environment.</span></span> <span data-ttu-id="a774e-225">有关最大可持续性能的详细信息，请参阅[什么是可持续的性能？](http://go.microsoft.com/fwlink/?LinkID=132304)</span><span class="sxs-lookup"><span data-stu-id="a774e-225">For more information about maximum sustainable performance, see [What Is Sustainable Performance?](http://go.microsoft.com/fwlink/?LinkID=132304)</span></span> <span data-ttu-id="a774e-226">(http://go.microsoft.com/fwlink/?LinkID=132304) BizTalk Server 2009 文档中。</span><span class="sxs-lookup"><span data-stu-id="a774e-226">(http://go.microsoft.com/fwlink/?LinkID=132304) in the BizTalk Server 2009 documentation.</span></span>  
  
### <a name="the-complete-bizunit-loadgen-sample-configuration-file"></a><span data-ttu-id="a774e-227">完成 BizUnit LoadGen 示例配置文件</span><span class="sxs-lookup"><span data-stu-id="a774e-227">The complete BizUnit LoadGen sample configuration file</span></span>  
 <span data-ttu-id="a774e-228">以下列表包含前面引用的 BizUnit 配置文件的全部内容。</span><span class="sxs-lookup"><span data-stu-id="a774e-228">The following list contains the entire contents of the BizUnit configuration file referenced earlier.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a774e-229">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a774e-229">See Also</span></span>  
 [<span data-ttu-id="a774e-230">使用 BizUnit 优化自动测试</span><span class="sxs-lookup"><span data-stu-id="a774e-230">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)