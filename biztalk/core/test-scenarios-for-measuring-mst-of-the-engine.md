---
title: "测试方案，用于测量引擎 MST |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sustainable load test
- maximum sustainable throughput (MST), testing
- LoadGen tool
- LoadGen tool, downloading
- testing, engine maximum sustainable throughput
ms.assetid: e54667b9-7262-43c8-a013-9242eb062daf
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df522748a2d4522e691fb4f579c3fdd26c788e4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="test-scenarios-for-measuring-mst-of-the-engine"></a><span data-ttu-id="59c3a-102">测量引擎的 MST 的测试方案</span><span class="sxs-lookup"><span data-stu-id="59c3a-102">Test Scenarios for Measuring MST of the Engine</span></span>
<span data-ttu-id="59c3a-103">本部分介绍的测试方案用于度量在三个不同负载级别上驱动 BizTalk 系统的效果：</span><span class="sxs-lookup"><span data-stu-id="59c3a-103">This section describes a test scenario that was implemented to measure the effect of driving a BizTalk system at three different levels of load:</span></span>  
  
-   <span data-ttu-id="59c3a-104">[可持续的负载测试](../core/sustainable-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-104">[Sustainable Load Test](../core/sustainable-load-test.md).</span></span> <span data-ttu-id="59c3a-105">对于这些测试，可持续负载主题中所述[什么是可持续的性能？](../core/what-is-sustainable-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-105">For purposes of these tests, sustainable load is described in the topic [What Is Sustainable Performance?](../core/what-is-sustainable-performance.md).</span></span>  
  
-   <span data-ttu-id="59c3a-106">[据负载测试以加快](../core/overdrive-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-106">[Overdrive Load Test](../core/overdrive-load-test.md).</span></span> <span data-ttu-id="59c3a-107">Overdrive 负载定义为超过 MST 一致负载。</span><span class="sxs-lookup"><span data-stu-id="59c3a-107">Overdrive load is defined as a consistent load that exceeds MST.</span></span>  
  
-   <span data-ttu-id="59c3a-108">[Floodgate 负载测试](../core/floodgate-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-108">[Floodgate Load Test](../core/floodgate-load-test.md).</span></span> <span data-ttu-id="59c3a-109">Floodgate 负载被指使用的负荷间歇性超过 MST 的峰值低负载。</span><span class="sxs-lookup"><span data-stu-id="59c3a-109">Floodgate load is defined as low load with intermittent peaks of load that exceed MST.</span></span>  
  
 <span data-ttu-id="59c3a-110">本主题介绍了测试硬件配置、测试方案，并讨论了所有这些测试的结果。</span><span class="sxs-lookup"><span data-stu-id="59c3a-110">This topic describes the test hardware configuration, the test scenarios, and discusses the findings of each of these tests.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59c3a-111">读者应了解本部分所包含的信息代表了 Microsoft 对讨论的数据发布问题的当前观点。</span><span class="sxs-lookup"><span data-stu-id="59c3a-111">Readers should be aware that the information contained in this section represents the current view of Microsoft on the issues discussed as of the date of publication.</span></span> <span data-ttu-id="59c3a-112">由于我们必须对市场条件和技术的更改作出响应，所以 Microsoft 无法确保数据发布后的所有信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="59c3a-112">Because we must respond to changing market conditions and technologies, Microsoft cannot guarantee the accuracy of any information presented after the date of publication.</span></span>  
  
## <a name="test-system-configuration"></a><span data-ttu-id="59c3a-113">测试系统配置</span><span class="sxs-lookup"><span data-stu-id="59c3a-113">Test System Configuration</span></span>  
 <span data-ttu-id="59c3a-114">以下硬件将用于此测试方案：</span><span class="sxs-lookup"><span data-stu-id="59c3a-114">The following hardware was used for this test scenario:</span></span>  
  
-   <span data-ttu-id="59c3a-115">**六个 BizTalk 服务器**。</span><span class="sxs-lookup"><span data-stu-id="59c3a-115">**Six BizTalk Servers**.</span></span> <span data-ttu-id="59c3a-116">每台均配备有双 3GHz 处理器和 2GB RAM。</span><span class="sxs-lookup"><span data-stu-id="59c3a-116">Each equipped with dual 3GHz processors and 2GB of RAM.</span></span> <span data-ttu-id="59c3a-117">每台服务器均使用本地磁盘。</span><span class="sxs-lookup"><span data-stu-id="59c3a-117">Each server is using local disks.</span></span> <span data-ttu-id="59c3a-118">两台配置了接收主机实例的 BizTalk Server 服务器、两台配置了发送主机实例的 BizTalk Server 服务器、以及两台配置了用于处理业务流程的主机实例的 BizTalk Server 服务器。</span><span class="sxs-lookup"><span data-stu-id="59c3a-118">Two of the BizTalk Servers are configured with an instance of the receiving host, two are configured with an instance of the sending host, and two are configured with an instance of the host used for processing orchestrations.</span></span>  
  
-   <span data-ttu-id="59c3a-119">**一台 SQL 服务器的 master MessageBox 数据库和非 MessageBox 数据库**。</span><span class="sxs-lookup"><span data-stu-id="59c3a-119">**One SQL Server for the master MessageBox database and the non-MessageBox databases**.</span></span> <span data-ttu-id="59c3a-120">配备有八个 2GHz 处理器和 4 GB RAM。</span><span class="sxs-lookup"><span data-stu-id="59c3a-120">Equipped with eight 2GHz processors and 4 GB of RAM.</span></span> <span data-ttu-id="59c3a-121">此服务器通过光纤连接到快速 SAN 磁盘子系统。</span><span class="sxs-lookup"><span data-stu-id="59c3a-121">This server is connected to a fast SAN disk subsystem via fiber.</span></span> <span data-ttu-id="59c3a-122">禁用消息发布。</span><span class="sxs-lookup"><span data-stu-id="59c3a-122">Message publication is disabled.</span></span>  
  
-   <span data-ttu-id="59c3a-123">**正在发布到 Messagebox 数据库的三个 SQL 服务器**。</span><span class="sxs-lookup"><span data-stu-id="59c3a-123">**Three SQL Servers for the Messagebox databases that are being published to**.</span></span> <span data-ttu-id="59c3a-124">配备有四个 2GHz 处理器和 4GB RAM。</span><span class="sxs-lookup"><span data-stu-id="59c3a-124">Equipped with four 2GHz processors and 4GB of RAM.</span></span> <span data-ttu-id="59c3a-125">这些服务器全部通过光纤连接到快速 SAN 磁盘子系统。</span><span class="sxs-lookup"><span data-stu-id="59c3a-125">These servers are each connected to a fast SAN disk subsystem via fiber.</span></span> <span data-ttu-id="59c3a-126">MessageBox 数据库的数据和事务日志文件位于单独的存储区域网络 (SAN) 逻辑单位号 (LUN) 上。</span><span class="sxs-lookup"><span data-stu-id="59c3a-126">The data and transaction log files for the MessageBox database are on separate storage area network (SAN) logical unit numbers (LUNs).</span></span>  
  
-   <span data-ttu-id="59c3a-127">**加载驱动程序客户端计算机**。</span><span class="sxs-lookup"><span data-stu-id="59c3a-127">**Load driver client machine**.</span></span> <span data-ttu-id="59c3a-128">配备有双 3GHz 处理器和 2GB RAM。</span><span class="sxs-lookup"><span data-stu-id="59c3a-128">Equipped with dual 3GHz processors and 2GB of RAM.</span></span> <span data-ttu-id="59c3a-129">此服务器用于生成测试 BizTalk 系统的负载。</span><span class="sxs-lookup"><span data-stu-id="59c3a-129">This server was used to generate the load for testing the BizTalk system.</span></span>  
  
 <span data-ttu-id="59c3a-130">下面是用于负载测试的拓扑。</span><span class="sxs-lookup"><span data-stu-id="59c3a-130">The topology used for the load tests is illustrated below.</span></span>  
  
 <span data-ttu-id="59c3a-131">**用于负载测试的拓扑**</span><span class="sxs-lookup"><span data-stu-id="59c3a-131">**Topology used for load tests**</span></span>  
  
 <span data-ttu-id="59c3a-132">![为 BizTalk Server 负载测试的硬件拓扑](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")</span><span class="sxs-lookup"><span data-stu-id="59c3a-132">![Hardware topology for BizTalk Server load testing](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")</span></span>  
  
## <a name="the-test-scenario"></a><span data-ttu-id="59c3a-133">测试方案</span><span class="sxs-lookup"><span data-stu-id="59c3a-133">The Test Scenario</span></span>  
 <span data-ttu-id="59c3a-134">测试方案非常简单。</span><span class="sxs-lookup"><span data-stu-id="59c3a-134">The test scenario is very simple.</span></span> <span data-ttu-id="59c3a-135">负载生成工具 LoadGen 2007 安装在负载驱动程序服务器上，并用于向文件适配器监视的共享位置发送文件副本。</span><span class="sxs-lookup"><span data-stu-id="59c3a-135">The load generation tool, LoadGen 2007, was installed on the load driver server and was used to send copies of a file to shares monitored by the file adapter.</span></span> <span data-ttu-id="59c3a-136">负载生成工具在各个文件共享位置之间均衡地分发输入文件实例的副本。</span><span class="sxs-lookup"><span data-stu-id="59c3a-136">The load generation tool distributes copies of the input file instance evenly across the file shares.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59c3a-137">LoadGen 2007 工具是可在下载[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-137">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span> <span data-ttu-id="59c3a-138">此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-138">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span> <span data-ttu-id="59c3a-139">有关使用 MSMQ 适配器 LoadGen 的信息的信息，请参阅[使用 MSMQ LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-139">For information about using LoadGen with the MSMQ adapter, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
 <span data-ttu-id="59c3a-140">BizTalk 文件适配器配置为监视文件共享，并将消息发布到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="59c3a-140">The BizTalk File adapter is configured to monitor the file shares and publish the messages into the MessageBox.</span></span> <span data-ttu-id="59c3a-141">只包含一个接收形状和一个发送形状的简单业务流程将订阅所发布的消息。</span><span class="sxs-lookup"><span data-stu-id="59c3a-141">A simple orchestration that contains only a receive shape and a send shape subscribes to the published message.</span></span> <span data-ttu-id="59c3a-142">由业务流程发布回 MessageBox 中的消息将由文件发送端口提取出来，并发送到 SAN 上定义的公用共享位置。</span><span class="sxs-lookup"><span data-stu-id="59c3a-142">Messages that are published back into the MessageBox by the orchestration are picked up by a file send port and sent to a common share, defined on the SAN.</span></span> <span data-ttu-id="59c3a-143">到达输出 SAN 共享位置的文件将立即删除，这是为了避免在长期运行测试期间，文件在该共享位置发生累积。</span><span class="sxs-lookup"><span data-stu-id="59c3a-143">Files arriving on the output SAN share are immediately deleted in order to avoid file buildup on that share during long test runs.</span></span>  
  
 <span data-ttu-id="59c3a-144">该方案定义了四个主机，一个用于接收位置，一个用于业务流程，一个用于发送端口，一个用于跟踪。</span><span class="sxs-lookup"><span data-stu-id="59c3a-144">Four hosts were defined for the scenario, one each for the receive location, the orchestrations, the send port, and for tracking.</span></span> <span data-ttu-id="59c3a-145">为了观察引擎积压行为，在测试运行期间将完全关闭跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="59c3a-145">For the purposes of observing engine backlog behavior, tracking is completely turned off during the test runs.</span></span> <span data-ttu-id="59c3a-146">默认情况下，只对管道和业务流程启用跟踪功能，因此对于所使用的业务流程和管道，需要在 BizTalk 管理器中将跟踪显式关闭。</span><span class="sxs-lookup"><span data-stu-id="59c3a-146">Tracking is only enabled for pipelines and orchestrations by default so tracking was explicitly turned off in the BizTalk Administrator for the orchestration and pipeline that was used.</span></span>  
  
 <span data-ttu-id="59c3a-147">由于关闭了跟踪功能以对这些测试隔离核心 MessageBox 行为，因此没有创建任何跟踪主机实例。</span><span class="sxs-lookup"><span data-stu-id="59c3a-147">No instances of the tracking host were created since tracking was turned off to isolate core MessageBox behavior for these tests.</span></span>  
  
 <span data-ttu-id="59c3a-148">使用简单架构，并且用于测试的实例文件的大小均为 10KB。</span><span class="sxs-lookup"><span data-stu-id="59c3a-148">A simple schema was used and the instance files used for the test were all 10KB in size.</span></span> <span data-ttu-id="59c3a-149">XMLReceive 管道用于入站文档，并且没有使用任何映射组件或出站组件，以便保持测试方案的简单性和着重观察 MessageBox 的行为。</span><span class="sxs-lookup"><span data-stu-id="59c3a-149">The XMLReceive pipeline was used for inbound documents and no mapping components or outbound components were used in order to keep the test scenario simple and focus observations on the behavior of the MessageBox.</span></span>  
  
## <a name="parameters-measured-in-the-test"></a><span data-ttu-id="59c3a-150">测试中度量的参数</span><span class="sxs-lookup"><span data-stu-id="59c3a-150">Parameters Measured in the Test</span></span>  
 <span data-ttu-id="59c3a-151">下面是在此测试中度量的参数：</span><span class="sxs-lookup"><span data-stu-id="59c3a-151">The parameters measured in this test are as follows:</span></span>  
  
 <span data-ttu-id="59c3a-152">**测量的主测试参数**</span><span class="sxs-lookup"><span data-stu-id="59c3a-152">**Primary test parameters measured**</span></span>  
  
 <span data-ttu-id="59c3a-153">以下参数是度量 MST 时使用的主要指标：</span><span class="sxs-lookup"><span data-stu-id="59c3a-153">The following parameters are the primary indicators used when measuring MST:</span></span>  
  
-   <span data-ttu-id="59c3a-154">测量的 MessageBox 积压**假脱机大小**，同时提供的计数器**BizTalk:MessageBox:General 计数器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="59c3a-154">The MessageBox backlog as measured by the **Spool Size** counter that is available with the **BizTalk:MessageBox:General Counters** performance object.</span></span> <span data-ttu-id="59c3a-155">Messagebox 积压是可维持性的关键指标。</span><span class="sxs-lookup"><span data-stu-id="59c3a-155">Messagebox backlog is a key indicator of sustainability.</span></span> <span data-ttu-id="59c3a-156">显然，如果最后未出现问题，则 MessageBox 积压将不会继续无限地增长。</span><span class="sxs-lookup"><span data-stu-id="59c3a-156">Clearly, MessageBox backlog cannot continue to grow indefinitely without eventually running into problems.</span></span> <span data-ttu-id="59c3a-157">因此，MessageBox 数据库积压的深度（随时间进行监视）可用于计算可维持性。</span><span class="sxs-lookup"><span data-stu-id="59c3a-157">So, the depth of the MessageBox database backlog, monitored over time, is used to evaluate sustainability.</span></span>  
  
     <span data-ttu-id="59c3a-158">名为的 MessageBox 表**假脱机**包含系统中的每个消息的记录 (活动或等待进行垃圾收集)。</span><span class="sxs-lookup"><span data-stu-id="59c3a-158">The MessageBox table named **spool** contains a record for each message in the system (active or waiting to be garbage collected).</span></span> <span data-ttu-id="59c3a-159">通过在系统负载增加的同时对此表中的行数以及每秒收到的消息数进行监视，可以很容易地对最大可承受吞吐量进行度量。</span><span class="sxs-lookup"><span data-stu-id="59c3a-159">Monitoring the number of rows in this table, and the number of messages received per second, while increasing system load provides an easy way to measure the maximum sustainable throughput.</span></span> <span data-ttu-id="59c3a-160">此测量值也称为**假脱机表深度**或**假脱机深度**。</span><span class="sxs-lookup"><span data-stu-id="59c3a-160">This measurement is also referred to as the **spool table depth** or **spool depth**.</span></span>  
  
-   <span data-ttu-id="59c3a-161">每秒为单位，由接收的文档数**文档 received/Sec** ，同时提供的计数器**BizTalk： 消息传送**性能对象。</span><span class="sxs-lookup"><span data-stu-id="59c3a-161">The number of documents received per second as measured by the **Documents received/Sec** counter that is available with the **BizTalk:Messaging** performance object.</span></span>  
  
 <span data-ttu-id="59c3a-162">**测量的辅助测试参数**</span><span class="sxs-lookup"><span data-stu-id="59c3a-162">**Secondary test parameters measured**</span></span>  
  
 <span data-ttu-id="59c3a-163">以下参数是可在度量 MST 时计算的辅助指标。</span><span class="sxs-lookup"><span data-stu-id="59c3a-163">The following parameters are secondary indicators that can be evaluated when measuring MST.</span></span> <span data-ttu-id="59c3a-164">这些参数可能会影响后台处理深度的主要指标，以及每秒收到的文档数。</span><span class="sxs-lookup"><span data-stu-id="59c3a-164">These parameters may impact the primary indicators of spool depth and the number of documents received per second.</span></span>  
  
-   <span data-ttu-id="59c3a-165">物理磁盘空闲时间 MessageBox 数据和事务文件磁盘测量**%空闲时间**计数器适用于**逻辑磁盘使用情况**性能对象。</span><span class="sxs-lookup"><span data-stu-id="59c3a-165">The physical disk idle time for the MessageBox data and transaction file disk as measured by the **%Idle Time** counter available with the **LogicalDisk** performance object.</span></span>  
  
-   <span data-ttu-id="59c3a-166">MessageBox 服务器测量的 CPU 使用率 （%） **%Processor Time**计数器适用于**处理器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="59c3a-166">The CPU utilization (%) for the MessageBox server as measured by the **%Processor Time** counter available with the **Processor** performance object.</span></span>  
  
-   <span data-ttu-id="59c3a-167">每秒锁超时消息框上的数据库测量**Lock Timeouts/sec**计数器适用于**sqlserver: Locks**性能对象。</span><span class="sxs-lookup"><span data-stu-id="59c3a-167">The lock timeouts per second on the MessageBox database as measured by the **Lock Timeouts/sec** counter available with the **SQLServer:Locks** performance object.</span></span>  
  
-   <span data-ttu-id="59c3a-168">最近运行 SQL 代理作业的时间（秒），该作业用于清除与删除的消息关联的 MessageBox 表。</span><span class="sxs-lookup"><span data-stu-id="59c3a-168">The time in seconds for the most recent run of the SQL agent job that cleans up message box tables associated with removed messages.</span></span> <span data-ttu-id="59c3a-169">这通过测量**MsgBox 消息 Cleanup(Purge Jobs)**计数器适用于**BizTalk:MessageBox:General 计数器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="59c3a-169">This is measured by the **MsgBox Msg Cleanup(Purge Jobs)** counter available with the **BizTalk:MessageBox:General Counters** performance object.</span></span>  
  
-   <span data-ttu-id="59c3a-170">最近运行 SQL 代理作业的时间（秒），该作业用于清除与删除消息的各部分关联的 MessageBox 表。</span><span class="sxs-lookup"><span data-stu-id="59c3a-170">The time in seconds for the most recent run of the SQL agent job which cleans up message box tables associated with removed message parts.</span></span> <span data-ttu-id="59c3a-171">这通过测量**MsgBox 部件 Cleanup(Purge Jobs)**计数器适用于**BizTalk:MessageBox:General 计数器**性能对象。</span><span class="sxs-lookup"><span data-stu-id="59c3a-171">This is measured by the **MsgBox Parts Cleanup(Purge Jobs)** counter available with the **BizTalk:MessageBox:General Counters** performance object.</span></span>  
  
 <span data-ttu-id="59c3a-172">在测试以确定最大可承受吞吐量时，输入负载将增大到后台处理表开始无限增长的点上。</span><span class="sxs-lookup"><span data-stu-id="59c3a-172">When testing to determine the maximum sustainable throughput, input load was increased up to the point that the spool table started to grow indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59c3a-173">如果无法生成足够大的负载以导致后台处理表无限增长，则只表示系统的最缓慢部分在接收端，而不是在处理/发送端。</span><span class="sxs-lookup"><span data-stu-id="59c3a-173">If you are unable to generate enough load to cause the spool table to grow indefinitely, it simply means that the slowest part of your system is on the receive side, rather than the processing/send side.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59c3a-174">SQL Server 2000 用于进行可承受负载测试和过载测试，而 SQL Server 2005 用于进行突发高负载测试。</span><span class="sxs-lookup"><span data-stu-id="59c3a-174">SQL Server 2000 was used for the sustainable load test and the Overdrive load test, SQL Server 2005 was used for the floodgate load test.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59c3a-175">本节内容</span><span class="sxs-lookup"><span data-stu-id="59c3a-175">In This Section</span></span>  
  
-   [<span data-ttu-id="59c3a-176">使用 Microsoft BizTalk LoadGen 2007 工具</span><span class="sxs-lookup"><span data-stu-id="59c3a-176">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)  
  
-   [<span data-ttu-id="59c3a-177">可持续的负载测试</span><span class="sxs-lookup"><span data-stu-id="59c3a-177">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)  
  
-   [<span data-ttu-id="59c3a-178">Overdrive 负载测试</span><span class="sxs-lookup"><span data-stu-id="59c3a-178">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)  
  
-   [<span data-ttu-id="59c3a-179">Floodgate 负载测试</span><span class="sxs-lookup"><span data-stu-id="59c3a-179">Floodgate Load Test</span></span>](../core/floodgate-load-test.md)