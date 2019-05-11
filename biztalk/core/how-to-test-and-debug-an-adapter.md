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
ms.openlocfilehash: c6d3806dc78fa09031339ab548d64149202d6dc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383739"
---
# <a name="how-to-test-and-debug-an-adapter"></a><span data-ttu-id="d46d3-102">如何测试和调试适配器</span><span class="sxs-lookup"><span data-stu-id="d46d3-102">How to Test and Debug an Adapter</span></span>
<span data-ttu-id="d46d3-103">调试运行时问题通常需要综合的解决方法。</span><span class="sxs-lookup"><span data-stu-id="d46d3-103">Debugging run-time problems often requires a multifaceted approach.</span></span> <span data-ttu-id="d46d3-104">必须从例如软件跟踪、 性能计数器、 事件日志条目、 Windows Management Instrumentation (WMI) 事件和调试源代码，以确定问题或软件错误的原因的多个源收集数据。</span><span class="sxs-lookup"><span data-stu-id="d46d3-104">Data must be gathered from multiple sources such as software tracing, performance counters, event log entries, Windows Management Instrumentation (WMI) events, and debugging source code to determine the cause of problems or software bugs.</span></span>  
  
 <span data-ttu-id="d46d3-105">因为接收和发送适配器需要将调试器附加到 BtsNtSvc.exe 进程，以调试适配器的 BizTalk 服务的地址空间中运行。</span><span class="sxs-lookup"><span data-stu-id="d46d3-105">Because receive and send adapters run in the address space of the BizTalk service the debugger needs to be attached to the BtsNtSvc.exe process to debug an adapter.</span></span> <span data-ttu-id="d46d3-106">但是对于独立接收适配器，需要将调试器附加到承载适配器的进程。</span><span class="sxs-lookup"><span data-stu-id="d46d3-106">However for isolated receive adapters, the debugger needs to be attached to the process that hosts the adapter.</span></span>  
  
 <span data-ttu-id="d46d3-107">应使用跟踪以捕获运行时诊断进行故障排除的代码检测适配器运行时代码。</span><span class="sxs-lookup"><span data-stu-id="d46d3-107">The adapter run-time code should be instrumented with tracing code to capture run-time diagnostics for troubleshooting.</span></span> <span data-ttu-id="d46d3-108">可以使用 Microsoft Enterprise Instrumentation Framework (EIF) 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d46d3-108">You can do this by using the Microsoft Enterprise Instrumentation Framework (EIF).</span></span> <span data-ttu-id="d46d3-109">通常最好添加跟踪语句的不同级别的严重性，例如，跟踪仅错误情况、 跟踪错误和警告，以及跟踪错误、 警告和信息性语句。</span><span class="sxs-lookup"><span data-stu-id="d46d3-109">Typically it is useful to add trace statements for different levels of severity, for example, tracing for error conditions only, tracing for errors and warnings, and finally tracing for errors, warnings, and informational statements.</span></span> <span data-ttu-id="d46d3-110">此外，更复杂的适配器可能有独立的子系统需要跟踪在彼此隔离。</span><span class="sxs-lookup"><span data-stu-id="d46d3-110">Further, more complex adapters may have separate subsystems that need to be traced in isolation from each other.</span></span> <span data-ttu-id="d46d3-111">例如，适配器可能有网络子系统和一个核心子系统;为所有子系统启用跟踪可能会在某些情况下生成过多的"噪声"。</span><span class="sxs-lookup"><span data-stu-id="d46d3-111">For example, an adapter may have a network subsubsystem and a core subsystem; enabling tracing for all subsystems may generate an excessive amount of "noise" in some scenarios.</span></span>  
  
 <span data-ttu-id="d46d3-112">应添加性能计数器，以在运行时能够在运行时行为的适配器的详细信息捕获速率和值。</span><span class="sxs-lookup"><span data-stu-id="d46d3-112">Performance counters should be added to capture rates and values at run time to give more information about the run-time behavior of the adapter.</span></span> <span data-ttu-id="d46d3-113">例如，适配器可以发布有关在每个终结点的基础，以及每秒发送的消息的速率发送的消息的原始数字的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="d46d3-113">For example, an adapter might publish performance counters for the raw numbers of messages sent on a per-endpoint basis as well as the rate of messages sent per second.</span></span>  
  
 <span data-ttu-id="d46d3-114">WMI 事件也可能适用于某些严重错误方案。</span><span class="sxs-lookup"><span data-stu-id="d46d3-114">WMI events may also be useful for some critical error scenarios.</span></span>  <span data-ttu-id="d46d3-115">例如，如果适配器遇到严重错误，导致其关闭接收位置，触发 WMI 事件允许管理员能够侦听该事件并采取相应的措施。</span><span class="sxs-lookup"><span data-stu-id="d46d3-115">For instance if an adapter hits a critical error that causes it to shut down a receive location, firing a WMI event allows an administrator to listen on that event and take appropriate action.</span></span>  
  
## <a name="adapter-testing"></a><span data-ttu-id="d46d3-116">适配器测试</span><span class="sxs-lookup"><span data-stu-id="d46d3-116">Adapter Testing</span></span>  
 <span data-ttu-id="d46d3-117">当 BizTalk server 开发的自定义适配器时，请记住应开发企业软件质量标准。</span><span class="sxs-lookup"><span data-stu-id="d46d3-117">When you develop a custom adapter for BizTalk Server, remember that it should be developed to enterprise software quality.</span></span> <span data-ttu-id="d46d3-118">这意味着您需要交付之前彻底测试适配器。</span><span class="sxs-lookup"><span data-stu-id="d46d3-118">This means that you need to test the adapter thoroughly before shipping it.</span></span> <span data-ttu-id="d46d3-119">虽然它不完全详细说明应如何测试适配器，此部分可为需要完成的想法。</span><span class="sxs-lookup"><span data-stu-id="d46d3-119">While it does not completely detail how adapters should be tested, this section gives an idea of what needs to be done.</span></span> <span data-ttu-id="d46d3-120">一般情况下测试适配器等的运行时代码应包含三大类： 功能测试、 压力测试和性能测试。</span><span class="sxs-lookup"><span data-stu-id="d46d3-120">In general the testing of run-time code such as adapters should cover three broad categories: functional testing, stress testing, and performance testing.</span></span>  
  
### <a name="function-testing"></a><span data-ttu-id="d46d3-121">功能测试</span><span class="sxs-lookup"><span data-stu-id="d46d3-121">Function Testing</span></span>  
 <span data-ttu-id="d46d3-122">适配器应测试其功能，包括正向测试和反向测试的所有可能情况。</span><span class="sxs-lookup"><span data-stu-id="d46d3-122">The adapter should be tested for all permutations of its functionality, including both positive tests and negative tests.</span></span> <span data-ttu-id="d46d3-123">正向测试应包括但不是限于以下方案：</span><span class="sxs-lookup"><span data-stu-id="d46d3-123">Positive tests should include but not be limited to the following scenarios:</span></span>  
  
- <span data-ttu-id="d46d3-124">接收消息</span><span class="sxs-lookup"><span data-stu-id="d46d3-124">Receive a message(s)</span></span>  
  
- <span data-ttu-id="d46d3-125">传输消息</span><span class="sxs-lookup"><span data-stu-id="d46d3-125">Transmit a message(s)</span></span>  
  
- <span data-ttu-id="d46d3-126">使用动态端口将消息传送</span><span class="sxs-lookup"><span data-stu-id="d46d3-126">Transmit a message using a dynamic port</span></span>  
  
- <span data-ttu-id="d46d3-127">禁用接收位置</span><span class="sxs-lookup"><span data-stu-id="d46d3-127">Disable receive locations</span></span>  
  
- <span data-ttu-id="d46d3-128">更新配置</span><span class="sxs-lookup"><span data-stu-id="d46d3-128">Update configuration</span></span>  
  
- <span data-ttu-id="d46d3-129">请确保接收和发送适配器均使用服务时段</span><span class="sxs-lookup"><span data-stu-id="d46d3-129">Ensure service windows are working for both receive and send adapters</span></span>  
  
- <span data-ttu-id="d46d3-130">确保事务性适配器的事务完整性</span><span class="sxs-lookup"><span data-stu-id="d46d3-130">Ensure transactional integrity for transacted adapters</span></span>  
  
  <span data-ttu-id="d46d3-131">反向测试应包括但不是限于：</span><span class="sxs-lookup"><span data-stu-id="d46d3-131">Negative tests should include but not be limited to:</span></span>  
  
- <span data-ttu-id="d46d3-132">收到错误消息</span><span class="sxs-lookup"><span data-stu-id="d46d3-132">Receive a bad message(s)</span></span>  
  
- <span data-ttu-id="d46d3-133">接收消息、 一些良好和有错误的混合消息的批</span><span class="sxs-lookup"><span data-stu-id="d46d3-133">Receive a mixed batch of messages, some good and some bad</span></span>  
  
- <span data-ttu-id="d46d3-134">传输失败</span><span class="sxs-lookup"><span data-stu-id="d46d3-134">Transmit failure</span></span>  
  
- <span data-ttu-id="d46d3-135">重试成功</span><span class="sxs-lookup"><span data-stu-id="d46d3-135">Retry successful</span></span>  
  
- <span data-ttu-id="d46d3-136">重试失败，将转到下一个传输成功</span><span class="sxs-lookup"><span data-stu-id="d46d3-136">Retry fails, move to next transport successful</span></span>  
  
- <span data-ttu-id="d46d3-137">转到下一个传输失败，则挂起消息</span><span class="sxs-lookup"><span data-stu-id="d46d3-137">Move to next transport fails, suspend message</span></span>  
  
- <span data-ttu-id="d46d3-138">传输混合的消息批</span><span class="sxs-lookup"><span data-stu-id="d46d3-138">Transmit a mixed batch of messages</span></span>  
  
- <span data-ttu-id="d46d3-139">数据库故障转移</span><span class="sxs-lookup"><span data-stu-id="d46d3-139">Database failover</span></span>  
  
### <a name="stress-testing"></a><span data-ttu-id="d46d3-140">压力测试</span><span class="sxs-lookup"><span data-stu-id="d46d3-140">Stress Testing</span></span>  
 <span data-ttu-id="d46d3-141">适配器是运行时组件和这种情况下应满足运行时软件的严格要求。</span><span class="sxs-lookup"><span data-stu-id="d46d3-141">Adapters are run-time components and as such should meet the stringent requirements for run-time software.</span></span> <span data-ttu-id="d46d3-142">通常执行压力测试的负载下运行的一段时间内扩展。</span><span class="sxs-lookup"><span data-stu-id="d46d3-142">Typically stress testing is carried out by running scenarios under load for a period of time.</span></span> <span data-ttu-id="d46d3-143">进一步高压力下和低压力平均故障时间测试应执行，因此适配器在负载下运行测得的时间段内。</span><span class="sxs-lookup"><span data-stu-id="d46d3-143">Further high-stress and low-stress mean time between failure tests should be performed, whereby the adapter is run under load for a measured time period.</span></span>  
  
 <span data-ttu-id="d46d3-144">对于这些测试一些大致的指南可能在运行该适配器的高压力大约 72 个小时，其中通过适配器的消息数会导致 CPU 使用率达到大约 80 到 90%。</span><span class="sxs-lookup"><span data-stu-id="d46d3-144">Some rough guidelines for these tests might be running the adapter at high stress for around 72 hours, where the number of messages through the adapter causes the CPU utilization to be around of 80 to 90 percent.</span></span> <span data-ttu-id="d46d3-145">对于低压力，CPU 使用率为 30 到 40%左右大约 120 小时。</span><span class="sxs-lookup"><span data-stu-id="d46d3-145">For low stress, the CPU utilization would be around 30 to 40 percent for around 120 hours.</span></span>  
  
### <a name="performance-testing"></a><span data-ttu-id="d46d3-146">性能测试</span><span class="sxs-lookup"><span data-stu-id="d46d3-146">Performance Testing</span></span>  
 <span data-ttu-id="d46d3-147">与性能方面的考虑，应开发适配器。</span><span class="sxs-lookup"><span data-stu-id="d46d3-147">Adapters should be developed with performance in mind.</span></span> <span data-ttu-id="d46d3-148">发布适配器前应验证其性能。</span><span class="sxs-lookup"><span data-stu-id="d46d3-148">Before releasing an adapter you should validate its performance.</span></span> <span data-ttu-id="d46d3-149">务必要确保其性能向上扩展和横向扩展;即，添加更多的 Cpu 会导致性能提升一样添加更多的计算机。</span><span class="sxs-lookup"><span data-stu-id="d46d3-149">It is important to ensure that its performance scales up and scales out; that is, adding more CPUs leads to a performance increase as does adding more computers.</span></span> <span data-ttu-id="d46d3-150">分析代码有助于消除性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="d46d3-150">Profiling the code can help to eliminate performance bottlenecks.</span></span>