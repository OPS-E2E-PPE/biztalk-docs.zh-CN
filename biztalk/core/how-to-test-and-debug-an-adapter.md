---
title: 如何测试和调试适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6563ea-b4ea-4617-b3da-d31250d002ab
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d0c28247b432e69e2501322ccc700033b5aa254
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004030"
---
# <a name="how-to-test-and-debug-an-adapter"></a><span data-ttu-id="d505b-102">如何测试和调试适配器</span><span class="sxs-lookup"><span data-stu-id="d505b-102">How to Test and Debug an Adapter</span></span>
<span data-ttu-id="d505b-103">调试运行时问题通常需要综合的解决方法。</span><span class="sxs-lookup"><span data-stu-id="d505b-103">Debugging run-time problems often requires a multifaceted approach.</span></span> <span data-ttu-id="d505b-104">必须从多个数据源收集数据，例如软件跟踪、性能计数器、事件日志条目、Windows 管理规范 (WMI) 事件和调试源代码，以确定问题或软件错误的根源。</span><span class="sxs-lookup"><span data-stu-id="d505b-104">Data must be gathered from multiple sources such as software tracing, performance counters, event log entries, Windows Management Instrumentation (WMI) events, and debugging source code to determine the cause of problems or software bugs.</span></span>  
  
 <span data-ttu-id="d505b-105">由于接收适配器和发送适配器运行在 BizTalk 服务的地址空间中，因此需要将调试器连接到 BtsNtSvc.exe 进程，以调试适配器。</span><span class="sxs-lookup"><span data-stu-id="d505b-105">Because receive and send adapters run in the address space of the BizTalk service the debugger needs to be attached to the BtsNtSvc.exe process to debug an adapter.</span></span> <span data-ttu-id="d505b-106">但对于独立接收适配器，需要将调试器连接到该适配器所在的进程。</span><span class="sxs-lookup"><span data-stu-id="d505b-106">However for isolated receive adapters, the debugger needs to be attached to the process that hosts the adapter.</span></span>  
  
 <span data-ttu-id="d505b-107">应使用跟踪代码检测适配器运行时代码，以捕获运行时诊断信息，从而排除故障。</span><span class="sxs-lookup"><span data-stu-id="d505b-107">The adapter run-time code should be instrumented with tracing code to capture run-time diagnostics for troubleshooting.</span></span> <span data-ttu-id="d505b-108">使用 Microsoft Enterprise Instrumentation Framework (EIF) 可实现这一目的。</span><span class="sxs-lookup"><span data-stu-id="d505b-108">You can do this by using the Microsoft Enterprise Instrumentation Framework (EIF).</span></span> <span data-ttu-id="d505b-109">通常，按照不同的严重度级别添加跟踪语句是很有用的，例如，仅跟踪错误情况、跟踪错误和警告、跟踪错误、警告和信息的语句。</span><span class="sxs-lookup"><span data-stu-id="d505b-109">Typically it is useful to add trace statements for different levels of severity, for example, tracing for error conditions only, tracing for errors and warnings, and finally tracing for errors, warnings, and informational statements.</span></span> <span data-ttu-id="d505b-110">而且，更为复杂的适配器可能有独立的子系统，对这些子系统需要进行互不影响的跟踪。</span><span class="sxs-lookup"><span data-stu-id="d505b-110">Further, more complex adapters may have separate subsystems that need to be traced in isolation from each other.</span></span> <span data-ttu-id="d505b-111">例如，对于有一个网络子系统和一个核心子系统的适配器，在某些情况下，如果对其全部子系统进行跟踪，可能会产生过量的“噪音”。</span><span class="sxs-lookup"><span data-stu-id="d505b-111">For example, an adapter may have a network subsubsystem and a core subsystem; enabling tracing for all subsystems may generate an excessive amount of "noise" in some scenarios.</span></span>  
  
 <span data-ttu-id="d505b-112">为了在运行时捕获速率和值，从而获得适配器运行时行为的更多信息，还应添加性能计数器。</span><span class="sxs-lookup"><span data-stu-id="d505b-112">Performance counters should be added to capture rates and values at run time to give more information about the run-time behavior of the adapter.</span></span> <span data-ttu-id="d505b-113">例如，适配器可以发布每个终结点所发送的原始消息数的性能计数器和每秒发送消息速率的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="d505b-113">For example, an adapter might publish performance counters for the raw numbers of messages sent on a per-endpoint basis as well as the rate of messages sent per second.</span></span>  
  
 <span data-ttu-id="d505b-114">对于某些严重错误，WMI 事件可能也会很有用。</span><span class="sxs-lookup"><span data-stu-id="d505b-114">WMI events may also be useful for some critical error scenarios.</span></span>  <span data-ttu-id="d505b-115">例如，如果适配器遇到严重错误，导致其关闭某个接收位置，则触发 WMI 事件可以使管理员能够侦听该事件并采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="d505b-115">For instance if an adapter hits a critical error that causes it to shut down a receive location, firing a WMI event allows an administrator to listen on that event and take appropriate action.</span></span>  
  
## <a name="adapter-testing"></a><span data-ttu-id="d505b-116">适配器测试</span><span class="sxs-lookup"><span data-stu-id="d505b-116">Adapter Testing</span></span>  
 <span data-ttu-id="d505b-117">开发自定义 BizTalk Server 适配器时，请记住应按照企业软件质量标准来开发。</span><span class="sxs-lookup"><span data-stu-id="d505b-117">When you develop a custom adapter for BizTalk Server, remember that it should be developed to enterprise software quality.</span></span> <span data-ttu-id="d505b-118">这意味着在交付前，您需要对该适配器进行彻底的测试。</span><span class="sxs-lookup"><span data-stu-id="d505b-118">This means that you need to test the adapter thoroughly before shipping it.</span></span> <span data-ttu-id="d505b-119">虽然不能详细完整地说明应如何测试适配器，但本部分会概述需要测试的内容。</span><span class="sxs-lookup"><span data-stu-id="d505b-119">While it does not completely detail how adapters should be tested, this section gives an idea of what needs to be done.</span></span> <span data-ttu-id="d505b-120">一般情况下测试适配器等的运行时代码应包含三大类： 功能测试、 压力测试和性能测试。</span><span class="sxs-lookup"><span data-stu-id="d505b-120">In general the testing of run-time code such as adapters should cover three broad categories: functional testing, stress testing, and performance testing.</span></span>  
  
### <a name="function-testing"></a><span data-ttu-id="d505b-121">功能测试</span><span class="sxs-lookup"><span data-stu-id="d505b-121">Function Testing</span></span>  
 <span data-ttu-id="d505b-122">应对适配器功能的所有可能情况进行测试，包括正向测试和反向测试。</span><span class="sxs-lookup"><span data-stu-id="d505b-122">The adapter should be tested for all permutations of its functionality, including both positive tests and negative tests.</span></span> <span data-ttu-id="d505b-123">正向测试应包括以下方面，但不局限于这些方面：</span><span class="sxs-lookup"><span data-stu-id="d505b-123">Positive tests should include but not be limited to the following scenarios:</span></span>  
  
- <span data-ttu-id="d505b-124">接收消息</span><span class="sxs-lookup"><span data-stu-id="d505b-124">Receive a message(s)</span></span>  
  
- <span data-ttu-id="d505b-125">传输消息</span><span class="sxs-lookup"><span data-stu-id="d505b-125">Transmit a message(s)</span></span>  
  
- <span data-ttu-id="d505b-126">使用动态端口传输消息</span><span class="sxs-lookup"><span data-stu-id="d505b-126">Transmit a message using a dynamic port</span></span>  
  
- <span data-ttu-id="d505b-127">禁用接收位置</span><span class="sxs-lookup"><span data-stu-id="d505b-127">Disable receive locations</span></span>  
  
- <span data-ttu-id="d505b-128">更新配置</span><span class="sxs-lookup"><span data-stu-id="d505b-128">Update configuration</span></span>  
  
- <span data-ttu-id="d505b-129">确保接收适配器和发送适配器在服务时段内都有效</span><span class="sxs-lookup"><span data-stu-id="d505b-129">Ensure service windows are working for both receive and send adapters</span></span>  
  
- <span data-ttu-id="d505b-130">确保事务性适配器的事务完整性</span><span class="sxs-lookup"><span data-stu-id="d505b-130">Ensure transactional integrity for transacted adapters</span></span>  
  
  <span data-ttu-id="d505b-131">反向测试应包括以下方面，但不局限于这些方面：</span><span class="sxs-lookup"><span data-stu-id="d505b-131">Negative tests should include but not be limited to:</span></span>  
  
- <span data-ttu-id="d505b-132">收到错误消息</span><span class="sxs-lookup"><span data-stu-id="d505b-132">Receive a bad message(s)</span></span>  
  
- <span data-ttu-id="d505b-133">接收既有正确消息又有错误消息的混合消息批</span><span class="sxs-lookup"><span data-stu-id="d505b-133">Receive a mixed batch of messages, some good and some bad</span></span>  
  
- <span data-ttu-id="d505b-134">传输失败</span><span class="sxs-lookup"><span data-stu-id="d505b-134">Transmit failure</span></span>  
  
- <span data-ttu-id="d505b-135">重试成功</span><span class="sxs-lookup"><span data-stu-id="d505b-135">Retry successful</span></span>  
  
- <span data-ttu-id="d505b-136">重试失败，转至下一个传输成功</span><span class="sxs-lookup"><span data-stu-id="d505b-136">Retry fails, move to next transport successful</span></span>  
  
- <span data-ttu-id="d505b-137">转至下一个传输失败，挂起消息</span><span class="sxs-lookup"><span data-stu-id="d505b-137">Move to next transport fails, suspend message</span></span>  
  
- <span data-ttu-id="d505b-138">传输混合消息批</span><span class="sxs-lookup"><span data-stu-id="d505b-138">Transmit a mixed batch of messages</span></span>  
  
- <span data-ttu-id="d505b-139">数据库故障转移</span><span class="sxs-lookup"><span data-stu-id="d505b-139">Database failover</span></span>  
  
### <a name="stress-testing"></a><span data-ttu-id="d505b-140">压力测试</span><span class="sxs-lookup"><span data-stu-id="d505b-140">Stress Testing</span></span>  
 <span data-ttu-id="d505b-141">适配器是运行时组件，因此应满足运行时软件的严格要求。</span><span class="sxs-lookup"><span data-stu-id="d505b-141">Adapters are run-time components and as such should meet the stringent requirements for run-time software.</span></span> <span data-ttu-id="d505b-142">压力测试通常要求在一定负载下运行一段时间。</span><span class="sxs-lookup"><span data-stu-id="d505b-142">Typically stress testing is carried out by running scenarios under load for a period of time.</span></span> <span data-ttu-id="d505b-143">此外，还应进行高压力下和低压力下的平均无故障时间测试，其中适配器在一定负载下运行一段规定的时间。</span><span class="sxs-lookup"><span data-stu-id="d505b-143">Further high-stress and low-stress mean time between failure tests should be performed, whereby the adapter is run under load for a measured time period.</span></span>  
  
 <span data-ttu-id="d505b-144">大致上，适配器的高压力测试约为 72 小时，通过适配器的消息使 CPU 使用率达到大约 80% 到 90%。</span><span class="sxs-lookup"><span data-stu-id="d505b-144">Some rough guidelines for these tests might be running the adapter at high stress for around 72 hours, where the number of messages through the adapter causes the CPU utilization to be around of 80 to 90 percent.</span></span> <span data-ttu-id="d505b-145">对于低压力测试，CPU 使用率应在 120 小时内维持在大约 30% 到 40% 之间。</span><span class="sxs-lookup"><span data-stu-id="d505b-145">For low stress, the CPU utilization would be around 30 to 40 percent for around 120 hours.</span></span>  
  
### <a name="performance-testing"></a><span data-ttu-id="d505b-146">性能测试</span><span class="sxs-lookup"><span data-stu-id="d505b-146">Performance Testing</span></span>  
 <span data-ttu-id="d505b-147">开发适配器的过程中，始终要考虑其性能。</span><span class="sxs-lookup"><span data-stu-id="d505b-147">Adapters should be developed with performance in mind.</span></span> <span data-ttu-id="d505b-148">发布适配器前，应对其性能进行验证。</span><span class="sxs-lookup"><span data-stu-id="d505b-148">Before releasing an adapter you should validate its performance.</span></span> <span data-ttu-id="d505b-149">确保适配器性能可向上扩展和向外扩展是很重要的；即增加 CPU 数量可改善性能，增加计算机同样也可改善性能。</span><span class="sxs-lookup"><span data-stu-id="d505b-149">It is important to ensure that its performance scales up and scales out; that is, adding more CPUs leads to a performance increase as does adding more computers.</span></span> <span data-ttu-id="d505b-150">分析代码有助于消除性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="d505b-150">Profiling the code can help to eliminate performance bottlenecks.</span></span>