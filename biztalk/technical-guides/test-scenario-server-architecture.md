---
title: 测试方案服务器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 369286ea2c5c42a53a8e22a7e0b03ac5701db0d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981262"
---
# <a name="test-scenario-server-architecture"></a><span data-ttu-id="e70f1-102">测试方案服务器体系结构</span><span class="sxs-lookup"><span data-stu-id="e70f1-102">Test Scenario Server Architecture</span></span>
<span data-ttu-id="e70f1-103">本主题提供了在负载测试期间的服务器和对其执行负载测试的不同的服务器体系结构之间的消息流的概览。</span><span class="sxs-lookup"><span data-stu-id="e70f1-103">This topic provides an overview of the flow of messages between servers during load testing and the distinct server architectures against which the load test was performed.</span></span>  
  
## <a name="overview-of-message-flow-during-load-testing"></a><span data-ttu-id="e70f1-104">在负载测试期间的消息流的概览</span><span class="sxs-lookup"><span data-stu-id="e70f1-104">Overview of Message Flow During Load Testing</span></span>  
 <span data-ttu-id="e70f1-105">下图提供了用于所有测试方案和负载测试期间的服务器之间的消息流的服务器体系结构的一般概述。</span><span class="sxs-lookup"><span data-stu-id="e70f1-105">The following diagram provides a generic overview of the server architecture used for all test scenarios and the flow of messages between servers during a load test.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70f1-106">部分中描述进行了测试每个不同的服务器体系结构**基线服务器体系结构**。</span><span class="sxs-lookup"><span data-stu-id="e70f1-106">Each distinct server architecture that was tested is described in the section **Baseline Server Architecture**.</span></span>  
  
 <span data-ttu-id="e70f1-107">下图提供消息流的概述。</span><span class="sxs-lookup"><span data-stu-id="e70f1-107">The following figure provides an overview of the message flow.</span></span> <span data-ttu-id="e70f1-108">在图中的数字对应于图下方列出的步骤。</span><span class="sxs-lookup"><span data-stu-id="e70f1-108">The numbers in the figure correspond to the steps listed below the figure.</span></span>  
  
 <span data-ttu-id="e70f1-109">![消息流概述](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")</span><span class="sxs-lookup"><span data-stu-id="e70f1-109">![Message Flow Overview](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")</span></span>  
<span data-ttu-id="e70f1-110">“消息流”概述</span><span class="sxs-lookup"><span data-stu-id="e70f1-110">Message Flow Overview</span></span>  
  
1. <span data-ttu-id="e70f1-111">负载测试的负载代理控制器计算机启动**VSTS_TestController**:</span><span class="sxs-lookup"><span data-stu-id="e70f1-111">Load testing is initiated by the Load Agent Controller computer **VSTS_TestController**:</span></span>  
  
   - <span data-ttu-id="e70f1-112">上的 Visual Studio 2008 项目**VSTS_TestController**执行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-112">A Visual Studio 2008 project on **VSTS_TestController** is executed.</span></span> <span data-ttu-id="e70f1-113">项目加载 BizUnit 类的实例、 加载指定的 BizUnit XML 配置文件，并开始执行 BizUnit 配置文件中定义的步骤。</span><span class="sxs-lookup"><span data-stu-id="e70f1-113">The project loads an instance of the BizUnit class, loads the specified BizUnit XML configuration file, and begins executing the steps defined in the BizUnit configuration file.</span></span>  
  
     > [!NOTE]  
     >  <span data-ttu-id="e70f1-114">有关使用 BizUnit 的 XML 配置文件的详细信息，请参见主题"定义测试使用 XML 配置文件"网址[ http://go.microsoft.com/fwlink/?LinkId=143432 ](http://go.microsoft.com/fwlink/?LinkId=143432)。</span><span class="sxs-lookup"><span data-stu-id="e70f1-114">For more information about the XML configuration file used by BizUnit, see the topic “Defining Tests Using an XML Configuration File” at [http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432).</span></span>  
  
   - <span data-ttu-id="e70f1-115">完成测试设置步骤后，BizUnit 项目中的步骤之一执行命令，将显示一个对话框，提示您启动"基本"测试运行需要将消息提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="e70f1-115">After completing the Test Setup steps, one of the steps in the BizUnit project executes a command that displays a dialog box which prompts you to start a “priming” test run to submit priming messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
   - <span data-ttu-id="e70f1-116">基本消息从一个单独的 Visual Studio 2008 测试项目上提交**VSTS_TestController**。</span><span class="sxs-lookup"><span data-stu-id="e70f1-116">Priming messages are submitted from a separate Visual Studio 2008 Test project on **VSTS_TestController**.</span></span> <span data-ttu-id="e70f1-117">基本消息将发送"预热"的测试环境通过初始化系统缓存。</span><span class="sxs-lookup"><span data-stu-id="e70f1-117">Priming messages are sent to “warm up” the test environment by initializing system caches.</span></span>  
  
   - <span data-ttu-id="e70f1-118">处理完所有基本消息; 之后BizUnit 实例加载所测试主要的测试运行中的所有计算机的性能监视器计数器，并执行命令，可以显示一个对话框，提示您将消息提交以主测试运行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-118">After all priming messages have been processed; the BizUnit instance loads Performance Monitor counters for all computers being tested in the main test run and executes a command to display a dialog box which prompts you to submit messages for the main test run.</span></span>  
  
   - <span data-ttu-id="e70f1-119">上的 Visual Studio 2008 负载测试项目**VSTS_TestController**指示要将消息提交以主测试运行的负载测试代理计算机。</span><span class="sxs-lookup"><span data-stu-id="e70f1-119">The Visual Studio 2008 Load Test project on **VSTS_TestController** directs the Load Test Agent computers to submit messages for the main test run.</span></span>  
  
2. <span data-ttu-id="e70f1-120">向负载测试代理计算机提交测试消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]负载测试控制器计算机上 Visual Studio 2008 负载测试项目的 app.config 文件中指定的计算机 (**VSTS_TestController**)。</span><span class="sxs-lookup"><span data-stu-id="e70f1-120">The Load Test Agent computers submit test messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers specified in the app.config file of the Visual Studio 2008 Load Test project on the Load Test Controller computer (**VSTS_TestController**).</span></span>  
  
3. <span data-ttu-id="e70f1-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机接收提交的负载测试代理计算机的消息，消息通过两种方式接收到此负载测试请求-响应接收位置。</span><span class="sxs-lookup"><span data-stu-id="e70f1-121">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers receive the messages submitted by the Load Test Agent computers, for this load test the messages were received by a two way request-response receive location.</span></span>  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e70f1-122"> 将消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="e70f1-122"> publishes the message to the MessageBox database.</span></span>  
  
   - <span data-ttu-id="e70f1-123">消息被供业务流程。</span><span class="sxs-lookup"><span data-stu-id="e70f1-123">The messages are consumed by an orchestration.</span></span>  
  
   - <span data-ttu-id="e70f1-124">业务流程绑定到双向要求响应发送端口调用下游计算器服务。</span><span class="sxs-lookup"><span data-stu-id="e70f1-124">The orchestration is bound to a two way solicit-response send port which invokes the downstream calculator service.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="e70f1-125">下游计算器服务基于 Windows Communication Foundation 示例中所述[ http://go.microsoft.com/fwlink/?LinkId=141762 ](http://go.microsoft.com/fwlink/?LinkId=141762)。</span><span class="sxs-lookup"><span data-stu-id="e70f1-125">The downstream calculator service is based upon Windows Communication Foundation samples described at [http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762).</span></span> <span data-ttu-id="e70f1-126">Windows Communication Foundation 示例都可在下载[ http://go.microsoft.com/fwlink/?LinkId=87352 ](http://go.microsoft.com/fwlink/?LinkId=87352)。</span><span class="sxs-lookup"><span data-stu-id="e70f1-126">The Windows Communication Foundation samples are available for download at [http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352).</span></span>  
  
4. <span data-ttu-id="e70f1-127">计算器服务消耗的请求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并将响应返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="e70f1-127">The calculator service consumes the request from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and returns a response to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solicit-response send port.</span></span>  
  
5. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e70f1-128"> 处理的响应，并保存到 MessageBox 数据库的响应消息。</span><span class="sxs-lookup"><span data-stu-id="e70f1-128"> processes the response and persists the response message to the MessageBox database.</span></span> <span data-ttu-id="e70f1-129">然后从 BizTalk 请求-响应端口，通过 MessageBox 数据库中检索来自计算器 web 服务的响应消息并将响应的消息传递回的负载测试代理计算机。</span><span class="sxs-lookup"><span data-stu-id="e70f1-129">Then the response message from the Calculator web service is retrieved from the MessageBox database by the BizTalk request-response port, and a response message is delivered back to the Load Test Agent computers.</span></span>  
  
## <a name="baseline-server-architecture"></a><span data-ttu-id="e70f1-130">基本服务器体系结构</span><span class="sxs-lookup"><span data-stu-id="e70f1-130">Baseline Server Architecture</span></span>  
 <span data-ttu-id="e70f1-131">基准服务器体系结构中，HYPER-V 角色未安装且两[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 安装到主机操作系统。</span><span class="sxs-lookup"><span data-stu-id="e70f1-131">For the Baseline Server architecture, the Hyper-V role was not installed and Both [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server were installed on to the host operating system.</span></span> <span data-ttu-id="e70f1-132">这样做是为了建立的"基准"性能指标[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的物理硬件环境的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e70f1-132">This was done to establish “baseline” performance metrics of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution on a physical hardware environment.</span></span>  
  
 <span data-ttu-id="e70f1-133">下图描绘了物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和基线服务器体系结构的 SQL Server 层。</span><span class="sxs-lookup"><span data-stu-id="e70f1-133">The following figure depicts the physical [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server tiers for the Baseline Server Architecture.</span></span>  
  
 <span data-ttu-id="e70f1-134">![物理 BizTalk&#47;物理 SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")</span><span class="sxs-lookup"><span data-stu-id="e70f1-134">![Physical BizTalk &#47; Physical SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")</span></span>  
<span data-ttu-id="e70f1-135">物理 BizTalk 服务器 / 物理 SQL 服务器 （基线）</span><span class="sxs-lookup"><span data-stu-id="e70f1-135">Physical BizTalk Server / Physical SQL Server (Baseline)</span></span>  
  
- <span data-ttu-id="e70f1-136">**BizTalk Server** – 2 个 BizTalk Server 计算机配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e70f1-136">**BizTalk Server** - 2 BizTalk Server computers configured as follows:</span></span>  
  
  - <span data-ttu-id="e70f1-137">一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**6** GB RAM 和**8**可用的处理器内核。</span><span class="sxs-lookup"><span data-stu-id="e70f1-137">One [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with **6** GB RAM and **8** processor cores available.</span></span>  
  
  - <span data-ttu-id="e70f1-138">一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机**3** GB RAM 和**4**可用的处理器内核。</span><span class="sxs-lookup"><span data-stu-id="e70f1-138">One [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with **3** GB RAM and **4** processor cores available.</span></span>  
  
  - <span data-ttu-id="e70f1-139">总数为 6 + 3 = **9**可用 GB RAM 和 8 + 4 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e70f1-139">Total of 6 + 3 = **9** GB RAM available and 8 + 4 = **12** processor cores available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="e70f1-140">**SQL Server** -1，如下所示配置的 SQL Server 计算机：</span><span class="sxs-lookup"><span data-stu-id="e70f1-140">**SQL Server** - 1 SQL Server computer configured as follows:</span></span>  
  
  -   <span data-ttu-id="e70f1-141">**8**可用 GB RAM。</span><span class="sxs-lookup"><span data-stu-id="e70f1-141">**8** GB RAM available.</span></span>  
  
  -   <span data-ttu-id="e70f1-142">**4**可用的处理器内核。</span><span class="sxs-lookup"><span data-stu-id="e70f1-142">**4** processor cores available.</span></span>  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a><span data-ttu-id="e70f1-143">虚拟 BizTalk 服务器 / 物理 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="e70f1-143">Virtual BizTalk Server / Physical SQL Server</span></span>  
 <span data-ttu-id="e70f1-144">下图描绘了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]层。</span><span class="sxs-lookup"><span data-stu-id="e70f1-144">The following figure depicts the virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and physical [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tiers.</span></span>  
  
 <span data-ttu-id="e70f1-145">![虚拟 BizTalk&#47;物理 SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")</span><span class="sxs-lookup"><span data-stu-id="e70f1-145">![Virtual BizTalk &#47; Physical SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")</span></span>  
<span data-ttu-id="e70f1-146">虚拟 BizTalk 服务器 / 物理 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="e70f1-146">Virtual BizTalk Server / Physical SQL Server</span></span>  
  
 <span data-ttu-id="e70f1-147">对于此方案中，负载测试已执行针对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的 HYPER-V 虚拟机和物理硬件上运行的 SQL Server 上运行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-147">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and SQL Server running on physical hardware.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70f1-148">如下所述的 RAM 和处理器核心的分配时完全相同的每个非基线方案中，唯一的差别是某些计算机是否正在运行的 HYPER-V 虚拟机上或在物理硬件上。</span><span class="sxs-lookup"><span data-stu-id="e70f1-148">The allocation of RAM and processor cores described below was identical for each non-baseline scenarios, the only difference being whether certain computers are running on a Hyper-V virtual machine or on physical hardware.</span></span>  
  
- <span data-ttu-id="e70f1-149">**BizTalk Server** -3[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的计算机配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e70f1-149">**BizTalk Server** - 3 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s computers configured as follows:</span></span>  
  
  - <span data-ttu-id="e70f1-150">3GB RAM 分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机总容量为 3 x 3 = **9** GB RAM 可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e70f1-150">3 GB RAM allocated to each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with a total of 3 x 3 = **9** GB RAM available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
  - <span data-ttu-id="e70f1-151">4 个处理器核心分配给每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机总容量为 3 x 4 = **12**处理器内核可用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e70f1-151">4 processor cores allocated to each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with a total of 3 x 4 = **12** processor cores available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="e70f1-152">**SQL Server** -1，如下所示配置的 SQL Server 计算机：</span><span class="sxs-lookup"><span data-stu-id="e70f1-152">**SQL Server** - 1 SQL Server computer configured as follows:</span></span>  
  
  -   <span data-ttu-id="e70f1-153">**8**可用 GB RAM。</span><span class="sxs-lookup"><span data-stu-id="e70f1-153">**8** GB RAM available.</span></span>  
  
  -   <span data-ttu-id="e70f1-154">**4**可用的处理器内核。</span><span class="sxs-lookup"><span data-stu-id="e70f1-154">**4** processor cores available.</span></span>  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a><span data-ttu-id="e70f1-155">虚拟 BizTalk 服务器 / 虚拟 SQL Server</span><span class="sxs-lookup"><span data-stu-id="e70f1-155">Virtual BizTalk Server / Virtual SQL Server</span></span>  
 <span data-ttu-id="e70f1-156">下图描绘了一个虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机上单独的 HYPER-V 主机计算机。</span><span class="sxs-lookup"><span data-stu-id="e70f1-156">The following figure depicts a virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and a virtual SQL Server computer on separate Hyper-V host computers.</span></span>  
  
 <span data-ttu-id="e70f1-157">![虚拟 BizTalk&#47;虚拟 SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")</span><span class="sxs-lookup"><span data-stu-id="e70f1-157">![Virtual BizTalk &#47; Virtual SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")</span></span>  
<span data-ttu-id="e70f1-158">虚拟 BizTalk 服务器 / 虚拟 SQL Server</span><span class="sxs-lookup"><span data-stu-id="e70f1-158">Virtual BizTalk Server / Virtual SQL Server</span></span>  
  
 <span data-ttu-id="e70f1-159">对于此方案中，负载测试已执行针对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机上运行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-159">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="e70f1-160">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]独立的 HYPER-V 主机计算机上运行的 HYPER-V 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="e70f1-160">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machine were run on separate Hyper-V host computers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e70f1-161">分配的 RAM 和处理器核心，以这种情况下是相同的分配的内存和处理器核心**虚拟 BizTalk 服务器 / 物理 SQL Server**方案中，唯一的差别是，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]是配置为在 HYPER-V 虚拟机而非物理硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-161">The allocation of RAM and processor cores for this scenario is identical to the allocation of RAM and processor cores for the **Virtual BizTalk Server / Physical SQL Server** scenario, the only difference being that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] was configured to run on a Hyper-V virtual machine rather than physical hardware.</span></span>  
  
## <a name="consolidated-environment"></a><span data-ttu-id="e70f1-162">统一的环境</span><span class="sxs-lookup"><span data-stu-id="e70f1-162">Consolidated Environment</span></span>  
 <span data-ttu-id="e70f1-163">下图描绘了虚拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和虚拟 SQL Server 计算机合并到一台 HYPER-V 主机计算机上。</span><span class="sxs-lookup"><span data-stu-id="e70f1-163">The following figure depicts virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers and a virtual SQL Server computer consolidated on one Hyper-V host computer.</span></span>  
  
 <span data-ttu-id="e70f1-164">![虚拟 BizTalk&#47;虚拟 SQL&#47;合并](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")</span><span class="sxs-lookup"><span data-stu-id="e70f1-164">![Virtual BizTalk &#47; Virtual SQL &#47; Consolidated](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")</span></span>  
<span data-ttu-id="e70f1-165">统一的环境</span><span class="sxs-lookup"><span data-stu-id="e70f1-165">Consolidated Environment</span></span>  
  
 <span data-ttu-id="e70f1-166">对于此方案中，负载测试已执行针对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机上运行和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机上运行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-166">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="e70f1-167">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机在同一台 HYPER-V 主机计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-167">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machine were all run on the same Hyper-V host computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e70f1-168">分配的 RAM 和处理器核心，以这种情况下是相同的分配的内存和处理器核心**虚拟 BizTalk 服务器 / 虚拟 SQL Server**方案，唯一的差别是，这两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 虚拟机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的 HYPER-V 虚拟机已配置为在同一台 HYPER-V 主机计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="e70f1-168">The allocation of RAM and processor cores for this scenario is identical to the allocation of RAM and processor cores for the **Virtual BizTalk Server / Virtual SQL Server** scenario, the only difference being that both the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machines were configured to run on the same Hyper-V host computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e70f1-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="e70f1-169">See Also</span></span>  
 [<span data-ttu-id="e70f1-170">测试方案概述</span><span class="sxs-lookup"><span data-stu-id="e70f1-170">Test Scenario Overview</span></span>](../technical-guides/test-scenario-overview.md)