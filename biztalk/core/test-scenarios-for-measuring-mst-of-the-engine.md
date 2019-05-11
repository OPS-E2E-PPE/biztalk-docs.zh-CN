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
# <a name="test-scenarios-for-measuring-mst-of-the-engine"></a><span data-ttu-id="bc285-102">测量引擎的 MST 的测试方案</span><span class="sxs-lookup"><span data-stu-id="bc285-102">Test Scenarios for Measuring MST of the Engine</span></span>
<span data-ttu-id="bc285-103">本部分介绍用于度量在三个不同的负载级别驱动 BizTalk 系统的影响的测试方案：</span><span class="sxs-lookup"><span data-stu-id="bc285-103">This section describes a test scenario that was implemented to measure the effect of driving a BizTalk system at three different levels of load:</span></span>  
  
- <span data-ttu-id="bc285-104">[可承受负载测试](../core/sustainable-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="bc285-104">[Sustainable Load Test](../core/sustainable-load-test.md).</span></span> <span data-ttu-id="bc285-105">对于这些测试，可承受负载本主题中所述[可承受性能？](../core/what-is-sustainable-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="bc285-105">For purposes of these tests, sustainable load is described in the topic [What Is Sustainable Performance?](../core/what-is-sustainable-performance.md).</span></span>  
  
- <span data-ttu-id="bc285-106">[据以加快负载测试](../core/overdrive-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="bc285-106">[Overdrive Load Test](../core/overdrive-load-test.md).</span></span> <span data-ttu-id="bc285-107">Overdrive 负载定义为超过 MST 的一致负载。</span><span class="sxs-lookup"><span data-stu-id="bc285-107">Overdrive load is defined as a consistent load that exceeds MST.</span></span>  
  
- <span data-ttu-id="bc285-108">[突发高负载测试](../core/floodgate-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="bc285-108">[Floodgate Load Test](../core/floodgate-load-test.md).</span></span> <span data-ttu-id="bc285-109">突发高负载定义为低负载超过 MST 的间歇峰值的负载。</span><span class="sxs-lookup"><span data-stu-id="bc285-109">Floodgate load is defined as low load with intermittent peaks of load that exceed MST.</span></span>  
  
  <span data-ttu-id="bc285-110">本主题介绍测试硬件配置、 测试方案中，并讨论了每个测试的发现结果。</span><span class="sxs-lookup"><span data-stu-id="bc285-110">This topic describes the test hardware configuration, the test scenarios, and discusses the findings of each of these tests.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bc285-111">读者应了解在本部分中包含的信息代表 Microsoft 对截至发布日期所讨论问题的当前观点。</span><span class="sxs-lookup"><span data-stu-id="bc285-111">Readers should be aware that the information contained in this section represents the current view of Microsoft on the issues discussed as of the date of publication.</span></span> <span data-ttu-id="bc285-112">因为我们必须应对不断变化的市场条件和技术，Microsoft 无法保证发布日期之后所提供的任何信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="bc285-112">Because we must respond to changing market conditions and technologies, Microsoft cannot guarantee the accuracy of any information presented after the date of publication.</span></span>  
  
## <a name="test-system-configuration"></a><span data-ttu-id="bc285-113">测试系统配置</span><span class="sxs-lookup"><span data-stu-id="bc285-113">Test System Configuration</span></span>  
 <span data-ttu-id="bc285-114">以下硬件用于此测试方案：</span><span class="sxs-lookup"><span data-stu-id="bc285-114">The following hardware was used for this test scenario:</span></span>  
  
- <span data-ttu-id="bc285-115">**六台 BizTalk 服务器**。</span><span class="sxs-lookup"><span data-stu-id="bc285-115">**Six BizTalk Servers**.</span></span> <span data-ttu-id="bc285-116">每台均配备有双 3ghz 处理器和 2 GB 的 RAM。</span><span class="sxs-lookup"><span data-stu-id="bc285-116">Each equipped with dual 3GHz processors and 2GB of RAM.</span></span> <span data-ttu-id="bc285-117">每个服务器均使用本地磁盘。</span><span class="sxs-lookup"><span data-stu-id="bc285-117">Each server is using local disks.</span></span> <span data-ttu-id="bc285-118">两台 BizTalk 服务器配置的接收主机实例、 两台配置的发送主机实例和两个配置了用于处理业务流程的主机的实例。</span><span class="sxs-lookup"><span data-stu-id="bc285-118">Two of the BizTalk Servers are configured with an instance of the receiving host, two are configured with an instance of the sending host, and two are configured with an instance of the host used for processing orchestrations.</span></span>  
  
- <span data-ttu-id="bc285-119">**一个用于主 MessageBox 数据库和非 MessageBox 数据库的 SQL Server**。</span><span class="sxs-lookup"><span data-stu-id="bc285-119">**One SQL Server for the master MessageBox database and the non-MessageBox databases**.</span></span> <span data-ttu-id="bc285-120">配备有八个 2ghz 处理器和 4 GB 的 RAM。</span><span class="sxs-lookup"><span data-stu-id="bc285-120">Equipped with eight 2GHz processors and 4 GB of RAM.</span></span> <span data-ttu-id="bc285-121">此服务器连接到通过光纤快速 SAN 磁盘子系统。</span><span class="sxs-lookup"><span data-stu-id="bc285-121">This server is connected to a fast SAN disk subsystem via fiber.</span></span> <span data-ttu-id="bc285-122">禁用消息发布。</span><span class="sxs-lookup"><span data-stu-id="bc285-122">Message publication is disabled.</span></span>  
  
- <span data-ttu-id="bc285-123">**正在发布到 Messagebox 数据库的三个 SQL Server**。</span><span class="sxs-lookup"><span data-stu-id="bc285-123">**Three SQL Servers for the Messagebox databases that are being published to**.</span></span> <span data-ttu-id="bc285-124">配备有四个 2ghz 处理器和 4 GB 的 RAM。</span><span class="sxs-lookup"><span data-stu-id="bc285-124">Equipped with four 2GHz processors and 4GB of RAM.</span></span> <span data-ttu-id="bc285-125">这些服务器每个到快速 SAN 磁盘子系统通过光纤连接。</span><span class="sxs-lookup"><span data-stu-id="bc285-125">These servers are each connected to a fast SAN disk subsystem via fiber.</span></span> <span data-ttu-id="bc285-126">MessageBox 数据库的数据和事务日志文件位于单独的存储区域网络 (SAN) 逻辑单元号 (Lun)。</span><span class="sxs-lookup"><span data-stu-id="bc285-126">The data and transaction log files for the MessageBox database are on separate storage area network (SAN) logical unit numbers (LUNs).</span></span>  
  
- <span data-ttu-id="bc285-127">**负载驱动程序客户端计算机**。</span><span class="sxs-lookup"><span data-stu-id="bc285-127">**Load driver client machine**.</span></span> <span data-ttu-id="bc285-128">配备有双 3ghz 处理器和 2 GB 的 RAM。</span><span class="sxs-lookup"><span data-stu-id="bc285-128">Equipped with dual 3GHz processors and 2GB of RAM.</span></span> <span data-ttu-id="bc285-129">此服务器用于生成测试 BizTalk 系统的负载。</span><span class="sxs-lookup"><span data-stu-id="bc285-129">This server was used to generate the load for testing the BizTalk system.</span></span>  
  
  <span data-ttu-id="bc285-130">用于负载测试的拓扑如下图所示。</span><span class="sxs-lookup"><span data-stu-id="bc285-130">The topology used for the load tests is illustrated below.</span></span>  
  
  <span data-ttu-id="bc285-131">**用于负载测试的拓扑**</span><span class="sxs-lookup"><span data-stu-id="bc285-131">**Topology used for load tests**</span></span>  
  
  <span data-ttu-id="bc285-132">![为 BizTalk Server 负载测试的硬件拓扑](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")</span><span class="sxs-lookup"><span data-stu-id="bc285-132">![Hardware topology for BizTalk Server load testing](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")</span></span>  
  
## <a name="the-test-scenario"></a><span data-ttu-id="bc285-133">测试方案</span><span class="sxs-lookup"><span data-stu-id="bc285-133">The Test Scenario</span></span>  
 <span data-ttu-id="bc285-134">测试方案是非常简单。</span><span class="sxs-lookup"><span data-stu-id="bc285-134">The test scenario is very simple.</span></span> <span data-ttu-id="bc285-135">负载生成工具 LoadGen 2007 已安装在负载驱动程序服务器上，并用于将文件的副本发送到文件适配器监视的共享。</span><span class="sxs-lookup"><span data-stu-id="bc285-135">The load generation tool, LoadGen 2007, was installed on the load driver server and was used to send copies of a file to shares monitored by the file adapter.</span></span> <span data-ttu-id="bc285-136">负载生成工具在文件共享之间均匀地分发输入的文件实例的副本。</span><span class="sxs-lookup"><span data-stu-id="bc285-136">The load generation tool distributes copies of the input file instance evenly across the file shares.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc285-137">下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。</span><span class="sxs-lookup"><span data-stu-id="bc285-137">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> <span data-ttu-id="bc285-138">此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[ http://go.microsoft.com/fwlink/?linkid=108999 ](http://go.microsoft.com/fwlink/?linkid=108999)。</span><span class="sxs-lookup"><span data-stu-id="bc285-138">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span> <span data-ttu-id="bc285-139">有关将 LoadGen 与 MSMQ 适配器的信息，请参阅[与 MSMQ 将 LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)。</span><span class="sxs-lookup"><span data-stu-id="bc285-139">For information about using LoadGen with the MSMQ adapter, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
 <span data-ttu-id="bc285-140">BizTalk 文件适配器配置为监视文件共享并将消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="bc285-140">The BizTalk File adapter is configured to monitor the file shares and publish the messages into the MessageBox.</span></span> <span data-ttu-id="bc285-141">包含接收形状和发送形状的简单业务流程订阅已发布的消息。</span><span class="sxs-lookup"><span data-stu-id="bc285-141">A simple orchestration that contains only a receive shape and a send shape subscribes to the published message.</span></span> <span data-ttu-id="bc285-142">文件发送端口提取和发送到公共共享，在 SAN 上定义的业务流程发布回 MessageBox 的消息。</span><span class="sxs-lookup"><span data-stu-id="bc285-142">Messages that are published back into the MessageBox by the orchestration are picked up by a file send port and sent to a common share, defined on the SAN.</span></span> <span data-ttu-id="bc285-143">到达的输出 SAN 共享的文件将立即删除以避免在很长的测试运行期间在该共享的文件累积。</span><span class="sxs-lookup"><span data-stu-id="bc285-143">Files arriving on the output SAN share are immediately deleted in order to avoid file buildup on that share during long test runs.</span></span>  
  
 <span data-ttu-id="bc285-144">对于该方案，其中一个每个接收位置、 业务流程、 发送端口，以及跟踪定义了四个主机。</span><span class="sxs-lookup"><span data-stu-id="bc285-144">Four hosts were defined for the scenario, one each for the receive location, the orchestrations, the send port, and for tracking.</span></span> <span data-ttu-id="bc285-145">为了观察引擎积压行为，跟踪是在中彻底关闭测试运行。</span><span class="sxs-lookup"><span data-stu-id="bc285-145">For the purposes of observing engine backlog behavior, tracking is completely turned off during the test runs.</span></span> <span data-ttu-id="bc285-146">跟踪仅可用于管道和业务流程默认情况下使跟踪被显式关闭 BizTalk 管理员中的业务流程和使用的管道。</span><span class="sxs-lookup"><span data-stu-id="bc285-146">Tracking is only enabled for pipelines and orchestrations by default so tracking was explicitly turned off in the BizTalk Administrator for the orchestration and pipeline that was used.</span></span>  
  
 <span data-ttu-id="bc285-147">由于关闭了跟踪功能来隔离核心 MessageBox 行为对于这些测试，已不创建跟踪主机的任何实例。</span><span class="sxs-lookup"><span data-stu-id="bc285-147">No instances of the tracking host were created since tracking was turned off to isolate core MessageBox behavior for these tests.</span></span>  
  
 <span data-ttu-id="bc285-148">用一个简单的架构，并且用于测试的实例文件是所有 10 KB 大小。</span><span class="sxs-lookup"><span data-stu-id="bc285-148">A simple schema was used and the instance files used for the test were all 10KB in size.</span></span> <span data-ttu-id="bc285-149">XMLReceive 管道用于入站文档和没有映射组件或出站组件使用以保持测试方案的简单和着重观察 MessageBox 的行为。</span><span class="sxs-lookup"><span data-stu-id="bc285-149">The XMLReceive pipeline was used for inbound documents and no mapping components or outbound components were used in order to keep the test scenario simple and focus observations on the behavior of the MessageBox.</span></span>  
  
## <a name="parameters-measured-in-the-test"></a><span data-ttu-id="bc285-150">在测试中度量的参数</span><span class="sxs-lookup"><span data-stu-id="bc285-150">Parameters Measured in the Test</span></span>  
 <span data-ttu-id="bc285-151">在此测试中度量的参数如下所示：</span><span class="sxs-lookup"><span data-stu-id="bc285-151">The parameters measured in this test are as follows:</span></span>  
  
 <span data-ttu-id="bc285-152">**度量的主要测试参数**</span><span class="sxs-lookup"><span data-stu-id="bc285-152">**Primary test parameters measured**</span></span>  
  
 <span data-ttu-id="bc285-153">以下参数是度量 MST 时使用的主要指标：</span><span class="sxs-lookup"><span data-stu-id="bc285-153">The following parameters are the primary indicators used when measuring MST:</span></span>  
  
- <span data-ttu-id="bc285-154">MessageBox 积压工作由度量**后台处理大小**随附的计数器**此计数器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="bc285-154">The MessageBox backlog as measured by the **Spool Size** counter that is available with the **BizTalk:MessageBox:General Counters** performance object.</span></span> <span data-ttu-id="bc285-155">Messagebox 积压是可维持性的关键指标。</span><span class="sxs-lookup"><span data-stu-id="bc285-155">Messagebox backlog is a key indicator of sustainability.</span></span> <span data-ttu-id="bc285-156">很明显，无法继续 MessageBox 积压无限增长，如果最后未出现问题。</span><span class="sxs-lookup"><span data-stu-id="bc285-156">Clearly, MessageBox backlog cannot continue to grow indefinitely without eventually running into problems.</span></span> <span data-ttu-id="bc285-157">因此，随着时间推移，监视在 MessageBox 数据库积压的深度用于计算可维持性。</span><span class="sxs-lookup"><span data-stu-id="bc285-157">So, the depth of the MessageBox database backlog, monitored over time, is used to evaluate sustainability.</span></span>  
  
   <span data-ttu-id="bc285-158">名为的 MessageBox 表**spool**包含系统中的每个消息的记录 (活动或等待进行垃圾收集)。</span><span class="sxs-lookup"><span data-stu-id="bc285-158">The MessageBox table named **spool** contains a record for each message in the system (active or waiting to be garbage collected).</span></span> <span data-ttu-id="bc285-159">监视此表中的行数和虽然系统负载增加提供了方便地测量的最大可承受吞吐量每秒接收的消息数。</span><span class="sxs-lookup"><span data-stu-id="bc285-159">Monitoring the number of rows in this table, and the number of messages received per second, while increasing system load provides an easy way to measure the maximum sustainable throughput.</span></span> <span data-ttu-id="bc285-160">此度量也称为**后台处理表深度**或**后台处理深度**。</span><span class="sxs-lookup"><span data-stu-id="bc285-160">This measurement is also referred to as the **spool table depth** or **spool depth**.</span></span>  
  
- <span data-ttu-id="bc285-161">每秒由度量收到的文档数**记录了 received/Sec**随附的计数器**BizTalk： 消息传送**性能对象。</span><span class="sxs-lookup"><span data-stu-id="bc285-161">The number of documents received per second as measured by the **Documents received/Sec** counter that is available with the **BizTalk:Messaging** performance object.</span></span>  
  
  <span data-ttu-id="bc285-162">**度量的辅助测试参数**</span><span class="sxs-lookup"><span data-stu-id="bc285-162">**Secondary test parameters measured**</span></span>  
  
  <span data-ttu-id="bc285-163">以下参数是可以度量 MST 时计算的辅助指标。</span><span class="sxs-lookup"><span data-stu-id="bc285-163">The following parameters are secondary indicators that can be evaluated when measuring MST.</span></span> <span data-ttu-id="bc285-164">这些参数可能会影响后台处理深度和每秒收到的文档数的主要指标。</span><span class="sxs-lookup"><span data-stu-id="bc285-164">These parameters may impact the primary indicators of spool depth and the number of documents received per second.</span></span>  
  
- <span data-ttu-id="bc285-165">物理磁盘空闲时间的 MessageBox 数据和事务文件磁盘由度量 **%空闲时间**计数器适用于**逻辑磁盘使用情况**性能对象。</span><span class="sxs-lookup"><span data-stu-id="bc285-165">The physical disk idle time for the MessageBox data and transaction file disk as measured by the **%Idle Time** counter available with the **LogicalDisk** performance object.</span></span>  
  
- <span data-ttu-id="bc285-166">CPU 使用率 （%）MessageBox 服务器由度量 **%Processor Time**计数器适用于**处理器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="bc285-166">The CPU utilization (%) for the MessageBox server as measured by the **%Processor Time** counter available with the **Processor** performance object.</span></span>  
  
- <span data-ttu-id="bc285-167">每秒锁超时在 MessageBox 数据库由度量**Lock Timeouts/sec**计数器适用于**sqlserver: Locks**性能对象。</span><span class="sxs-lookup"><span data-stu-id="bc285-167">The lock timeouts per second on the MessageBox database as measured by the **Lock Timeouts/sec** counter available with the **SQLServer:Locks** performance object.</span></span>  
  
- <span data-ttu-id="bc285-168">清除与删除的消息关联的 messagebox 表的 SQL 代理作业运行的时间以秒为单位的最新。</span><span class="sxs-lookup"><span data-stu-id="bc285-168">The time in seconds for the most recent run of the SQL agent job that cleans up message box tables associated with removed messages.</span></span> <span data-ttu-id="bc285-169">这通过测量**MsgBox Msg Cleanup(Purge Jobs)** 计数器适用于**此计数器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="bc285-169">This is measured by the **MsgBox Msg Cleanup(Purge Jobs)** counter available with the **BizTalk:MessageBox:General Counters** performance object.</span></span>  
  
- <span data-ttu-id="bc285-170">以秒为单位的最新的时间运行的 SQL 代理作业用于清除与已删除的消息部分关联的 messagebox 表。</span><span class="sxs-lookup"><span data-stu-id="bc285-170">The time in seconds for the most recent run of the SQL agent job which cleans up message box tables associated with removed message parts.</span></span> <span data-ttu-id="bc285-171">这通过测量**MsgBox 部件 Cleanup(Purge Jobs)** 计数器适用于**此计数器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="bc285-171">This is measured by the **MsgBox Parts Cleanup(Purge Jobs)** counter available with the **BizTalk:MessageBox:General Counters** performance object.</span></span>  
  
  <span data-ttu-id="bc285-172">在测试以确定最大可承受吞吐量，输入的负载将增大到点的后台处理表开始无限增长。</span><span class="sxs-lookup"><span data-stu-id="bc285-172">When testing to determine the maximum sustainable throughput, input load was increased up to the point that the spool table started to grow indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc285-173">如果你不能生成足够的负载以导致后台处理表无限增长，这只是意味着您的系统的最缓慢部分位于接收端，而不是处理/发送端。</span><span class="sxs-lookup"><span data-stu-id="bc285-173">If you are unable to generate enough load to cause the spool table to grow indefinitely, it simply means that the slowest part of your system is on the receive side, rather than the processing/send side.</span></span>  
  

## <a name="next"></a><span data-ttu-id="bc285-174">Next</span><span class="sxs-lookup"><span data-stu-id="bc285-174">Next</span></span>
  
-   [<span data-ttu-id="bc285-175">使用 Microsoft BizTalk LoadGen 2007 工具</span><span class="sxs-lookup"><span data-stu-id="bc285-175">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)  
  
-   [<span data-ttu-id="bc285-176">可承受负载测试</span><span class="sxs-lookup"><span data-stu-id="bc285-176">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)  
  
-   [<span data-ttu-id="bc285-177">过载测试</span><span class="sxs-lookup"><span data-stu-id="bc285-177">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)  
  
-   [<span data-ttu-id="bc285-178">突发高负载测试</span><span class="sxs-lookup"><span data-stu-id="bc285-178">Floodgate Load Test</span></span>](../core/floodgate-load-test.md)