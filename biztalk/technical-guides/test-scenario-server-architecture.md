---
title: "测试方案服务器体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49a51244b7033c6cebc978a39ad37dd5732fa38d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="test-scenario-server-architecture"></a><span data-ttu-id="68f53-102">测试方案服务器体系结构</span><span class="sxs-lookup"><span data-stu-id="68f53-102">Test Scenario Server Architecture</span></span>
<span data-ttu-id="68f53-103">本主题概述了在负载测试期间的服务器和对其执行负载测试的不同服务器体系结构之间的消息流。</span><span class="sxs-lookup"><span data-stu-id="68f53-103">This topic provides an overview of the flow of messages between servers during load testing and the distinct server architectures against which the load test was performed.</span></span>  
  
## <a name="overview-of-message-flow-during-load-testing"></a><span data-ttu-id="68f53-104">在负载测试期间的消息流的概述</span><span class="sxs-lookup"><span data-stu-id="68f53-104">Overview of Message Flow During Load Testing</span></span>  
 <span data-ttu-id="68f53-105">下图提供了用于所有方案中测试和负载测试期间的服务器之间的消息流的服务器体系结构的泛型概述。</span><span class="sxs-lookup"><span data-stu-id="68f53-105">The following diagram provides a generic overview of the server architecture used for all test scenarios and the flow of messages between servers during a load test.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68f53-106">本节介绍测试了每个不同的服务器体系结构**基线服务器体系结构**。</span><span class="sxs-lookup"><span data-stu-id="68f53-106">Each distinct server architecture that was tested is described in the section **Baseline Server Architecture**.</span></span>  
  
 <span data-ttu-id="68f53-107">下图提供消息流的概述。</span><span class="sxs-lookup"><span data-stu-id="68f53-107">The following figure provides an overview of the message flow.</span></span> <span data-ttu-id="68f53-108">图中的数字对应于图下方列出的步骤。</span><span class="sxs-lookup"><span data-stu-id="68f53-108">The numbers in the figure correspond to the steps listed below the figure.</span></span>  
  
 <span data-ttu-id="68f53-109">![消息流概述](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")</span><span class="sxs-lookup"><span data-stu-id="68f53-109">![Message Flow Overview](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")</span></span>  
<span data-ttu-id="68f53-110">“消息流”概述</span><span class="sxs-lookup"><span data-stu-id="68f53-110">Message Flow Overview</span></span>  
  
1.  <span data-ttu-id="68f53-111">负载测试可由负载代理控制器计算机**VSTS_TestController**:</span><span class="sxs-lookup"><span data-stu-id="68f53-111">Load testing is initiated by the Load Agent Controller computer **VSTS_TestController**:</span></span>  
  
    -   <span data-ttu-id="68f53-112">上的 Visual Studio 2008 项目**VSTS_TestController**执行。</span><span class="sxs-lookup"><span data-stu-id="68f53-112">A Visual Studio 2008 project on **VSTS_TestController** is executed.</span></span> <span data-ttu-id="68f53-113">项目加载 BizUnit 类的实例，加载指定的 BizUnit XML 配置文件，并开始执行 BizUnit 配置文件中定义的步骤。</span><span class="sxs-lookup"><span data-stu-id="68f53-113">The project loads an instance of the BizUnit class, loads the specified BizUnit XML configuration file, and begins executing the steps defined in the BizUnit configuration file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="68f53-114">有关使用 BizUnit 的 XML 配置文件的详细信息，请参阅主题"定义测试使用 XML 配置文件"在[http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432)。</span><span class="sxs-lookup"><span data-stu-id="68f53-114">For more information about the XML configuration file used by BizUnit, see the topic “Defining Tests Using an XML Configuration File” at [http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432).</span></span>  
  
    -   <span data-ttu-id="68f53-115">完成测试安装步骤后，一个 BizUnit 项目中的步骤执行用于显示一个对话框，通过该对话框提示您以启动"需要"的测试运行以提交到需要消息的命令[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="68f53-115">After completing the Test Setup steps, one of the steps in the BizUnit project executes a command that displays a dialog box which prompts you to start a “priming” test run to submit priming messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
    -   <span data-ttu-id="68f53-116">需要消息的单独的 Visual Studio 2008 测试项目中提交的**VSTS_TestController**。</span><span class="sxs-lookup"><span data-stu-id="68f53-116">Priming messages are submitted from a separate Visual Studio 2008 Test project on **VSTS_TestController**.</span></span> <span data-ttu-id="68f53-117">需要消息将发送"预热"的测试环境初始化系统缓存。</span><span class="sxs-lookup"><span data-stu-id="68f53-117">Priming messages are sent to “warm up” the test environment by initializing system caches.</span></span>  
  
    -   <span data-ttu-id="68f53-118">处理完所有需要消息; 之后BizUnit 实例加载在主要的测试运行中进行测试的所有计算机的性能监视器计数器，并执行命令以显示一个对话框，通过该对话框提示您提交主测试运行的消息。</span><span class="sxs-lookup"><span data-stu-id="68f53-118">After all priming messages have been processed; the BizUnit instance loads Performance Monitor counters for all computers being tested in the main test run and executes a command to display a dialog box which prompts you to submit messages for the main test run.</span></span>  
  
    -   <span data-ttu-id="68f53-119">上的 Visual Studio 2008 负载测试项目**VSTS_TestController**指示要提交邮件用于主测试运行的负载测试代理计算机。</span><span class="sxs-lookup"><span data-stu-id="68f53-119">The Visual Studio 2008 Load Test project on **VSTS_TestController** directs the Load Test Agent computers to submit messages for the main test run.</span></span>  
  
2.  <span data-ttu-id="68f53-120">负载测试代理计算机提交测试消息都传送到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]负载测试控制器计算机上 Visual Studio 2008 负载测试项目的 app.config 文件中指定的计算机 (**VSTS_TestController**)。</span><span class="sxs-lookup"><span data-stu-id="68f53-120">The Load Test Agent computers submit test messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers specified in the app.config file of the Visual Studio 2008 Load Test project on the Load Test Controller computer (**VSTS_TestController**).</span></span>  
  
3.  <span data-ttu-id="68f53-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机接收提交的负载测试代理计算机的消息，则为两种方式接收的消息已此负载测试请求-响应接收位置。</span><span class="sxs-lookup"><span data-stu-id="68f53-121">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers receive the messages submitted by the Load Test Agent computers, for this load test the messages were received by a two way request-response receive location.</span></span>  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="68f53-122">将消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="68f53-122"> publishes the message to the MessageBox database.</span></span>  
  
    -   <span data-ttu-id="68f53-123">消息被使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="68f53-123">The messages are consumed by an orchestration.</span></span>  
  
    -   <span data-ttu-id="68f53-124">业务流程所绑定到为双向请求作出响应发送调用下游计算器服务的端口。</span><span class="sxs-lookup"><span data-stu-id="68f53-124">The orchestration is bound to a two way solicit-response send port which invokes the downstream calculator service.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68f53-125">下游计算器服务基于 Windows Communication Foundation 示例中所述[http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762)。</span><span class="sxs-lookup"><span data-stu-id="68f53-125">The downstream calculator service is based upon Windows Communication Foundation samples described at [http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762).</span></span> <span data-ttu-id="68f53-126">Windows Communication Foundation 示例将可供在下载[http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352)。</span><span class="sxs-lookup"><span data-stu-id="68f53-126">The Windows Communication Foundation samples are available for download at [http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352).</span></span>  
  
4.  <span data-ttu-id="68f53-127">计算器服务使用来自请求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并返回到响应[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请求作出响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="68f53-127">The calculator service consumes the request from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and returns a response to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solicit-response send port.</span></span>  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="68f53-128">处理响应并保存到 MessageBox 数据库响应消息。</span><span class="sxs-lookup"><span data-stu-id="68f53-128"> processes the response and persists the response message to the MessageBox database.</span></span> <span data-ttu-id="68f53-129">然后从 BizTalk 请求-响应端口，MessageBox 数据库检索来自计算器 web 服务的响应消息和响应消息发送回的负载测试代理计算机。</span><span class="sxs-lookup"><span data-stu-id="68f53-129">Then the response message from the Calculator web service is retrieved from the MessageBox database by the BizTalk request-response port, and a response message is delivered back to the Load Test Agent computers.</span></span>  
  
## <a name="baseline-server-architecture"></a><span data-ttu-id="68f53-130">基线服务器体系结构</span><span class="sxs-lookup"><span data-stu-id="68f53-130">Baseline Server Architecture</span></span>  
 <span data-ttu-id="68f53-131">对于基线服务器体系结构，HYPER-V 角色未安装且两[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 安装到主机操作系统。</span><span class="sxs-lookup"><span data-stu-id="68f53-131">For the Baseline Server architecture, the Hyper-V role was not installed and Both [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server were installed on to the host operating system.</span></span> <span data-ttu-id="68f53-132">这样做是为了建立的"基准"性能指标[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案上的物理硬件环境。</span><span class="sxs-lookup"><span data-stu-id="68f53-132">This was done to establish “baseline” performance metrics of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution on a physical hardware environment.</span></span>  
  
 <span data-ttu-id="68f53-133">下图描述了物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 层的基线服务器体系结构。</span><span class="sxs-lookup"><span data-stu-id="68f53-133">The following figure depicts the physical [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server tiers for the Baseline Server Architecture.</span></span>  
  
 <span data-ttu-id="68f53-134">![物理 BizTalk &#47;物理 SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")</span><span class="sxs-lookup"><span data-stu-id="68f53-134">![Physical BizTalk &#47; Physical SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")</span></span>  
<span data-ttu-id="68f53-135">物理 BizTalk Server / 物理 SQL Server （基线）</span><span class="sxs-lookup"><span data-stu-id="68f53-135">Physical BizTalk Server / Physical SQL Server (Baseline)</span></span>  
  
-   <span data-ttu-id="68f53-136">**BizTalk Server** -2，如下所示配置 BizTalk Server 计算机：</span><span class="sxs-lookup"><span data-stu-id="68f53-136">**BizTalk Server** - 2 BizTalk Server computers configured as follows:</span></span>  
  
    -   <span data-ttu-id="68f53-137">一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**6** GB 的 RAM 和**8**处理器内核可用。</span><span class="sxs-lookup"><span data-stu-id="68f53-137">One [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with **6** GB RAM and **8** processor cores available.</span></span>  
  
    -   <span data-ttu-id="68f53-138">一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**3** GB 的 RAM 和**4**处理器内核可用。</span><span class="sxs-lookup"><span data-stu-id="68f53-138">One [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with **3** GB RAM and **4** processor cores available.</span></span>  
  
    -   <span data-ttu-id="68f53-139">总的 6 + 3 = **9**可用 GB RAM 和 8 + 4 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="68f53-139">Total of 6 + 3 = **9** GB RAM available and 8 + 4 = **12** processor cores available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="68f53-140">**SQL Server** -1，如下所示配置的 SQL Server 计算机：</span><span class="sxs-lookup"><span data-stu-id="68f53-140">**SQL Server** - 1 SQL Server computer configured as follows:</span></span>  
  
    -   <span data-ttu-id="68f53-141">**8** GB RAM 可。</span><span class="sxs-lookup"><span data-stu-id="68f53-141">**8** GB RAM available.</span></span>  
  
    -   <span data-ttu-id="68f53-142">**4**处理器内核可用。</span><span class="sxs-lookup"><span data-stu-id="68f53-142">**4** processor cores available.</span></span>  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a><span data-ttu-id="68f53-143">虚拟 BizTalk Server / 物理 SQL Server</span><span class="sxs-lookup"><span data-stu-id="68f53-143">Virtual BizTalk Server / Physical SQL Server</span></span>  
 <span data-ttu-id="68f53-144">下图描述了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]层。</span><span class="sxs-lookup"><span data-stu-id="68f53-144">The following figure depicts the virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and physical [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tiers.</span></span>  
  
 <span data-ttu-id="68f53-145">![虚拟 BizTalk &#47;物理 SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")</span><span class="sxs-lookup"><span data-stu-id="68f53-145">![Virtual BizTalk &#47; Physical SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")</span></span>  
<span data-ttu-id="68f53-146">虚拟 BizTalk Server / 物理 SQL Server</span><span class="sxs-lookup"><span data-stu-id="68f53-146">Virtual BizTalk Server / Physical SQL Server</span></span>  
  
 <span data-ttu-id="68f53-147">对于此方案中，针对执行负载测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机和物理硬件上运行的 SQL Server 上运行。</span><span class="sxs-lookup"><span data-stu-id="68f53-147">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and SQL Server running on physical hardware.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68f53-148">如下所述的 RAM 和处理器内核的分配时相同对于每个非基线方案，唯一的区别是某些计算机是否有运行在 HYPER-V 虚拟机上或在物理硬件上。</span><span class="sxs-lookup"><span data-stu-id="68f53-148">The allocation of RAM and processor cores described below was identical for each non-baseline scenarios, the only difference being whether certain computers are running on a Hyper-V virtual machine or on physical hardware.</span></span>  
  
-   <span data-ttu-id="68f53-149">**BizTalk Server** -3[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的计算机配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="68f53-149">**BizTalk Server** - 3 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s computers configured as follows:</span></span>  
  
    -   <span data-ttu-id="68f53-150">3 GB RAM 分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机具有的 3 x 3 总 = **9** GB RAM 可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="68f53-150">3 GB RAM allocated to each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with a total of 3 x 3 = **9** GB RAM available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="68f53-151">4 个处理器核心分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机具有的 3 x 4 总 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="68f53-151">4 processor cores allocated to each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with a total of 3 x 4 = **12** processor cores available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="68f53-152">**SQL Server** -1，如下所示配置的 SQL Server 计算机：</span><span class="sxs-lookup"><span data-stu-id="68f53-152">**SQL Server** - 1 SQL Server computer configured as follows:</span></span>  
  
    -   <span data-ttu-id="68f53-153">**8** GB RAM 可。</span><span class="sxs-lookup"><span data-stu-id="68f53-153">**8** GB RAM available.</span></span>  
  
    -   <span data-ttu-id="68f53-154">**4**处理器内核可用。</span><span class="sxs-lookup"><span data-stu-id="68f53-154">**4** processor cores available.</span></span>  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a><span data-ttu-id="68f53-155">虚拟 BizTalk Server / 虚拟 SQL Server</span><span class="sxs-lookup"><span data-stu-id="68f53-155">Virtual BizTalk Server / Virtual SQL Server</span></span>  
 <span data-ttu-id="68f53-156">下图描述了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机上单独的 HYPER-V 主机计算机。</span><span class="sxs-lookup"><span data-stu-id="68f53-156">The following figure depicts a virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and a virtual SQL Server computer on separate Hyper-V host computers.</span></span>  
  
 <span data-ttu-id="68f53-157">![虚拟 BizTalk &#47;虚拟 SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")</span><span class="sxs-lookup"><span data-stu-id="68f53-157">![Virtual BizTalk &#47; Virtual SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")</span></span>  
<span data-ttu-id="68f53-158">虚拟 BizTalk Server / 虚拟 SQL Server</span><span class="sxs-lookup"><span data-stu-id="68f53-158">Virtual BizTalk Server / Virtual SQL Server</span></span>  
  
 <span data-ttu-id="68f53-159">对于此方案中，针对执行负载测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机上运行。</span><span class="sxs-lookup"><span data-stu-id="68f53-159">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="68f53-160">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在单独的 HYPER-V 主机计算机上运行 HYPER-V 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="68f53-160">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machine were run on separate Hyper-V host computers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68f53-161">RAM 和处理器内核用于这种情况下分配是相同的分配的内存和处理器内核**虚拟 BizTalk Server / 物理 SQL Server**方案、 唯一的区别是，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]已配置为在 HYPER-V 虚拟机，而不是物理硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="68f53-161">The allocation of RAM and processor cores for this scenario is identical to the allocation of RAM and processor cores for the **Virtual BizTalk Server / Physical SQL Server** scenario, the only difference being that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] was configured to run on a Hyper-V virtual machine rather than physical hardware.</span></span>  
  
## <a name="consolidated-environment"></a><span data-ttu-id="68f53-162">统一的环境</span><span class="sxs-lookup"><span data-stu-id="68f53-162">Consolidated Environment</span></span>  
 <span data-ttu-id="68f53-163">下图描述了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机合并到一台 HYPER-V 主机计算机上。</span><span class="sxs-lookup"><span data-stu-id="68f53-163">The following figure depicts virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers and a virtual SQL Server computer consolidated on one Hyper-V host computer.</span></span>  
  
 <span data-ttu-id="68f53-164">![虚拟 BizTalk &#47;虚拟 SQL &#47;合并](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")</span><span class="sxs-lookup"><span data-stu-id="68f53-164">![Virtual BizTalk &#47; Virtual SQL &#47; Consolidated](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")</span></span>  
<span data-ttu-id="68f53-165">统一的环境</span><span class="sxs-lookup"><span data-stu-id="68f53-165">Consolidated Environment</span></span>  
  
 <span data-ttu-id="68f53-166">对于此方案中，针对执行负载测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机上运行。</span><span class="sxs-lookup"><span data-stu-id="68f53-166">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="68f53-167">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机已在同一个 HYPER-V 主机计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="68f53-167">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machine were all run on the same Hyper-V host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68f53-168">RAM 和处理器内核用于这种情况下分配是相同的分配的内存和处理器内核**虚拟 BizTalk Server / 虚拟 SQL Server**方案、 唯一的区别是，这两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 虚拟机配置为在同一个 HYPER-V 主机计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="68f53-168">The allocation of RAM and processor cores for this scenario is identical to the allocation of RAM and processor cores for the **Virtual BizTalk Server / Virtual SQL Server** scenario, the only difference being that both the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machines were configured to run on the same Hyper-V host computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f53-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68f53-169">See Also</span></span>  
 [<span data-ttu-id="68f53-170">测试方案概述</span><span class="sxs-lookup"><span data-stu-id="68f53-170">Test Scenario Overview</span></span>](../technical-guides/test-scenario-overview.md)