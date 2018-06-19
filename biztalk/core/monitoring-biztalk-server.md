---
title: 监视的运行状况和性能使用内置的工具 |Microsoft 文档
description: 可用性、 运行状况和性能监视在 BizTalk Server 中和监视 SQL 代理作业
ms.custom: ''
ms.date: 01/14/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96e244dc-b826-4a9f-a4e1-6dabc41eb144
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6652c962d8ef522128dfb4c9febeca55ce42669
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22265357"
---
# <a name="monitoring-biztalk-server"></a><span data-ttu-id="ebbdd-103">监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ebbdd-103">Monitoring BizTalk Server</span></span>
<span data-ttu-id="ebbdd-104">定期监视 BizTalk Server 应用程序和基础结构并解决发现的任何问题，有助于使用户保持对 BizTalk Server 应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-104">Monitoring your BizTalk Server applications and infrastructure on a regular basis and resolving any issues that you find helps to keep your BizTalk Server applications accessible to your users.</span></span> <span data-ttu-id="ebbdd-105">监视的目的在于最大限度地减少未检测到（并因此导致未解决）的异常存在的时间。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-105">The goal of monitoring is to minimize the amount of time that an exception goes undetected and, therefore, unresolved.</span></span> <span data-ttu-id="ebbdd-106">此外，还可以使用监视来帮助检测可能导致异常的情形。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-106">Additionally, you can use monitoring to help detect situations that might cause an exception.</span></span>  
  
 <span data-ttu-id="ebbdd-107">当监视 BizTalk Server 时，您应查找任何意外或异常行为。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-107">When monitoring BizTalk Server, you should look for any unexpected or anomalous behavior.</span></span> <span data-ttu-id="ebbdd-108">监视既可以是手动过程，也可以是自动过程。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-108">Monitoring can be either a manual or automatic process.</span></span> <span data-ttu-id="ebbdd-109">您可以使用 BizTalk Server 管理控制台监视 BizTalk Server 基础结构的运行状况。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-109">You can monitor use the health of your BizTalk Server infrastructure using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="ebbdd-110">您可以使用 BizTalk Server 管理控制台监视 BizTalk Server 应用程序的运行状况，执行根源分析以确定任何问题的基本原因。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-110">You can use the BizTalk Server Administration Console to monitor the health of your BizTalk Server applications and perform root-cause analysis to identify the underlying cause of any problems.</span></span> <span data-ttu-id="ebbdd-111">。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-111">.</span></span> <span data-ttu-id="ebbdd-112">监视 BizTalk Server 时，请谨记以下几点：</span><span class="sxs-lookup"><span data-stu-id="ebbdd-112">When monitoring BizTalk Server, keep these points in mind:</span></span>  
  
-   <span data-ttu-id="ebbdd-113">基础结构的运行状况可能处于正常状态，但应用程序则未必（例如，它们正在接收无效消息，但无法处理这些消息）。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-113">Your infrastructure could be healthy, but your applications might not be (for example, they are receiving invalid messages and are unable to process them).</span></span>  
  
-   <span data-ttu-id="ebbdd-114">基础结构的运行状况可能并不正常，但应用程序可能正在正常运行（例如，如果服务器停机，但向主机分配了足够的服务器来接管负载）。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-114">Your infrastructure could be unhealthy, but your applications might be running fine (for example, if a server is down, but there are enough servers assigned to the host to take over the load).</span></span>  
  
-   <span data-ttu-id="ebbdd-115">基础结构问题可能表现为应用程序问题（例如，由于服务器停机，导致处理消息的速度不够快）。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-115">An infrastructure problem could surface as an application problem (for example, messages are not being processed fast enough because a server is down).</span></span>  
  
 <span data-ttu-id="ebbdd-116">对 BizTalk Server 和应用程序的监视归为以下三个主要类别：</span><span class="sxs-lookup"><span data-stu-id="ebbdd-116">Monitoring your BizTalk Server and Applications falls into three main categories:</span></span>  
  
-   <span data-ttu-id="ebbdd-117">可用性监视</span><span class="sxs-lookup"><span data-stu-id="ebbdd-117">Availability monitoring</span></span>  
  
-   <span data-ttu-id="ebbdd-118">运行状况监视</span><span class="sxs-lookup"><span data-stu-id="ebbdd-118">Health monitoring</span></span>  
  
-   <span data-ttu-id="ebbdd-119">性能监视</span><span class="sxs-lookup"><span data-stu-id="ebbdd-119">Performance monitoring</span></span>  
  
## <a name="availability-monitoring"></a><span data-ttu-id="ebbdd-120">可用性监视</span><span class="sxs-lookup"><span data-stu-id="ebbdd-120">Availability Monitoring</span></span>  
 <span data-ttu-id="ebbdd-121">可用性监视回答的问题是“系统或应用程序资源的不可用是否导致 BizTalk Server 应用程序无法以最佳方式运行？”</span><span class="sxs-lookup"><span data-stu-id="ebbdd-121">Availability monitoring answers the question "Is the inavailability of a system or application resource preventing your BizTalk Server applications from running optimally?"</span></span> <span data-ttu-id="ebbdd-122">这些问题几乎毫无例外都是系统级别的问题，如服务和连接的可用性。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-122">These issues are almost exclusively system-level, such as availability of services and connections.</span></span> <span data-ttu-id="ebbdd-123">例如，如果某个适配器由于停止了企业单一登录服务而失败，这就是一个可用性问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-123">For example, if an adapter is failing because the Enterprise Single Sign-On service is stopped, this is an availability issue.</span></span> <span data-ttu-id="ebbdd-124">如果分配给主机的服务器之一失败且应用程序在处理消息时速度很慢，则您遇到了可用性问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-124">If one of the servers assigned to a host has failed and your application is falling behind on processing messages, you have an availability issue.</span></span> <span data-ttu-id="ebbdd-125">同样，如果应用程序停止而无法处理消息，您也遇到了可用性问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-125">Likewise, if an application is stopped and is unable to process messages, you have an availability issue.</span></span> <span data-ttu-id="ebbdd-126">下表显示了可用性监视工具。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-126">The following table shows availability monitoring tools.</span></span>  
  
|<span data-ttu-id="ebbdd-127">工具</span><span class="sxs-lookup"><span data-stu-id="ebbdd-127">Tool</span></span>|<span data-ttu-id="ebbdd-128">任务</span><span class="sxs-lookup"><span data-stu-id="ebbdd-128">Task</span></span>|  
|----------|----------|  
|<span data-ttu-id="ebbdd-129">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="ebbdd-129">BizTalk Server Administration Console</span></span>|<span data-ttu-id="ebbdd-130">您应查看 BizTalk Server 管理控制台中的“组中心”页，以查看应用程序或其组件（端口/业务流程）是否已停止。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-130">You should look at the Group Hub page in the BizTalk Server Administration Console to see if applications or their components (ports/orchestrations) are stopped.</span></span>|  
|<span data-ttu-id="ebbdd-131">事件查看器</span><span class="sxs-lookup"><span data-stu-id="ebbdd-131">Event Viewer</span></span>|<span data-ttu-id="ebbdd-132">查找适配器连接问题、停止的服务以及其他问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-132">Look for adapter connection issues, stopped services, and so on.</span></span>|  
  
## <a name="health-monitoring"></a><span data-ttu-id="ebbdd-133">运行状况监视</span><span class="sxs-lookup"><span data-stu-id="ebbdd-133">Health Monitoring</span></span>  
 <span data-ttu-id="ebbdd-134">运行状况监视有助于回答问题“某些应用程序或资源的运行状况是否较差？”</span><span class="sxs-lookup"><span data-stu-id="ebbdd-134">Health monitoring helps you answer the question, "Are any of my applications or resources in bad health?"</span></span> <span data-ttu-id="ebbdd-135">例如，是否我的应用程序或其构成项目的任何当前遇到异常条件？</span><span class="sxs-lookup"><span data-stu-id="ebbdd-135">For example, are any of my applications or their constituent artifacts currently experiencing exception conditions?</span></span> <span data-ttu-id="ebbdd-136">或者，由于消息负载中的数据无效消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-136">Or, are messages suspended because of invalid data in the message payload?</span></span> <span data-ttu-id="ebbdd-137">下表显示了运行状况监视工具。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-137">The following table shows health-monitoring tools.</span></span>  
  
|<span data-ttu-id="ebbdd-138">工具</span><span class="sxs-lookup"><span data-stu-id="ebbdd-138">Tool</span></span>|<span data-ttu-id="ebbdd-139">任务</span><span class="sxs-lookup"><span data-stu-id="ebbdd-139">Task</span></span>|  
|----------|----------|  
|<span data-ttu-id="ebbdd-140">BizTalk 运行状况监视器工具 (BHM)</span><span class="sxs-lookup"><span data-stu-id="ebbdd-140">BizTalk Health Monitor tool (BHM)</span></span>|<span data-ttu-id="ebbdd-141">用户监视 BizTalk Server 环境的运行状况 mmc 管理单元检测关键和非关键问题并执行维护任务。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-141">An MMC snap-in for users to monitor the health of BizTalk Server environments, detect critical and non-critical issues, and execute maintenance tasks.</span></span>  <span data-ttu-id="ebbdd-142">[下载 BizTalk 运行状况监视器](https://www.microsoft.com/download/details.aspx?id=43716)。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-142">[Download BizTalk Health Monitor](https://www.microsoft.com/download/details.aspx?id=43716).</span></span>|  
|<span data-ttu-id="ebbdd-143">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="ebbdd-143">BizTalk Server Administration Console</span></span>|<span data-ttu-id="ebbdd-144">可以使用 BizTalk Server 管理控制台中的“组中心”页和查询页来确定应用程序运行状况问题并分析问题原因。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-144">You will use the Group Hub page and query pages in the BizTalk Server Administration Console to identify application health problems and analyze their cause(s).</span></span>|  
|<span data-ttu-id="ebbdd-145">事件查看器</span><span class="sxs-lookup"><span data-stu-id="ebbdd-145">Event Viewer</span></span>|<span data-ttu-id="ebbdd-146">检测在处理消息和业务流程的过程中出现的问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-146">Detect problems that occur during the processing of messages and orchestrations.</span></span>|  
  
## <a name="performance-monitoring"></a><span data-ttu-id="ebbdd-147">性能监视</span><span class="sxs-lookup"><span data-stu-id="ebbdd-147">Performance Monitoring</span></span>  
 <span data-ttu-id="ebbdd-148">性能监视回答的问题是“系统执行其工作的效率如何？”</span><span class="sxs-lookup"><span data-stu-id="ebbdd-148">Performance monitoring answers the question, "How efficiently is the system performing its work?"</span></span> <span data-ttu-id="ebbdd-149">这种监视主要关注物理资源（如数据库和磁盘）上的负载。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-149">This kind of monitoring focuses primarily on the load on physical resources like databases and disks.</span></span> <span data-ttu-id="ebbdd-150">例如，如果 CPU 利用率始终保持在 90% 到 100% 且造成消息积压，则这是计算机级别的性能问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-150">For example, if the CPU utilization is consistently at 90 to 100 percent and a backlog of messages is forming, this is a performance issue at the computer level.</span></span> <span data-ttu-id="ebbdd-151">下表显示了性能监视工具。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-151">The following table shows performance-monitoring tools.</span></span>  
  
|<span data-ttu-id="ebbdd-152">工具</span><span class="sxs-lookup"><span data-stu-id="ebbdd-152">Tool</span></span>|<span data-ttu-id="ebbdd-153">任务</span><span class="sxs-lookup"><span data-stu-id="ebbdd-153">Task</span></span>|  
|----------|----------|  
|<span data-ttu-id="ebbdd-154">SQL 查询分析器</span><span class="sxs-lookup"><span data-stu-id="ebbdd-154">SQL Query Analyzer</span></span>|<span data-ttu-id="ebbdd-155">监视数据库大小和内容以诊断系统问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-155">Monitor database size and content to diagnose system problems.</span></span>|  
|<span data-ttu-id="ebbdd-156">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="ebbdd-156">BizTalk Server Administration Console</span></span>|<span data-ttu-id="ebbdd-157">“组中心”页显示关键的性能度量，如 BizTalk Server 应用程序中当前活动的、已冻结的、准备运行的、已计划的以及已挂起的服务实例数等。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-157">The Group Hub Page shows key performance metrics such as the number of service instances currently active, dehydrated, ready to run, scheduled, suspended, etc. in your BizTalk Server applications.</span></span>|  
|<span data-ttu-id="ebbdd-158">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="ebbdd-158">Business Activity Monitoring (BAM)</span></span>|<span data-ttu-id="ebbdd-159">您可以指定业务流程中的特定阶段，以便针对其跟踪与业务应用程序相关的关键性能指示器。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-159">You can specify specific stages in your business process for which you want to track key performance indicators pertinent to your business application.</span></span>|  
  
## <a name="biztalk-server-monitoring"></a><span data-ttu-id="ebbdd-160">BizTalk 服务器监视</span><span class="sxs-lookup"><span data-stu-id="ebbdd-160">BizTalk Server Monitoring</span></span>  
 <span data-ttu-id="ebbdd-161">你可以运行 **监视器 BizTalk Server** SQL 代理作业来标识管理、 消息框中或 DTA 数据库中的所有已知的问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-161">You can run the **Monitor BizTalk Server** SQL Agent job to identify any known issues in Management, Message Box, or DTA databases.</span></span> <span data-ttu-id="ebbdd-162">在 BizTalk Server 管理控制台中配置 BizTalk 组或从以前的版本升级 BizTalk 时创建该作业。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-162">The job is created when you configure a BizTalk group in BizTalk Server Administration console or upgrade BizTalk from the previous version.</span></span>  
  
 <span data-ttu-id="ebbdd-163">监视 BizTalk 服务器作业扫描管理、 消息框中，和 DTA 数据库中的以下问题︰</span><span class="sxs-lookup"><span data-stu-id="ebbdd-163">The Monitor BizTalk Server job scans for the following issues in Management, Message Box, and DTA databases:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebbdd-164">监视 BizTalk 服务器作业仅扫描的问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-164">The Monitor BizTalk Server job only scans for issues.</span></span> <span data-ttu-id="ebbdd-165">它不能解决找到的问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-165">It does not fix the issues found.</span></span>  
  
-   <span data-ttu-id="ebbdd-166">没有任何引用的消息</span><span class="sxs-lookup"><span data-stu-id="ebbdd-166">Messages without any references</span></span>  
  
-   <span data-ttu-id="ebbdd-167">而无需引用计数的消息</span><span class="sxs-lookup"><span data-stu-id="ebbdd-167">Messages without reference counts</span></span>  
  
-   <span data-ttu-id="ebbdd-168">引用计数小于 0 的消息</span><span class="sxs-lookup"><span data-stu-id="ebbdd-168">Messages with reference count less than 0</span></span>  
  
-   <span data-ttu-id="ebbdd-169">无后台行的消息引用</span><span class="sxs-lookup"><span data-stu-id="ebbdd-169">Message references without spool rows</span></span>  
  
-   <span data-ttu-id="ebbdd-170">无实例的消息引用</span><span class="sxs-lookup"><span data-stu-id="ebbdd-170">Message references without instances</span></span>  
  
-   <span data-ttu-id="ebbdd-171">不包含实例的实例状态</span><span class="sxs-lookup"><span data-stu-id="ebbdd-171">Instance state without instances</span></span>  
  
-   <span data-ttu-id="ebbdd-172">实例不包含相应的实例的订阅</span><span class="sxs-lookup"><span data-stu-id="ebbdd-172">Instance subscriptions without corresponding instances</span></span>  
  
-   <span data-ttu-id="ebbdd-173">孤立的 DTA 服务实例</span><span class="sxs-lookup"><span data-stu-id="ebbdd-173">Orphaned DTA service instances</span></span>  
  
-   <span data-ttu-id="ebbdd-174">孤立的 DTA 服务实例异常</span><span class="sxs-lookup"><span data-stu-id="ebbdd-174">Orphaned DTA service instance exceptions</span></span>  
  
-   <span data-ttu-id="ebbdd-175">TDDS 未运行任何主机实例上启用全局跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-175">TDDS is not running on any host instance when global tracking option is enabled.</span></span>  
  
 <span data-ttu-id="ebbdd-176">“监视 BizTalk Server”作业已配置为每周自动运行一次。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-176">The Monitor BizTalk Server job is configured and automated to run once in a week.</span></span> <span data-ttu-id="ebbdd-177">因为作业需要大量的计算，所以建议在停机/低流量时安排。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-177">Since the job is computationally intensive, we recommended you to schedule it during downtime/low traffic.</span></span>  
  
 <span data-ttu-id="ebbdd-178">如果遇到任何问题，作业将会失败；错误字符串包含找到的问题数。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-178">The job fails if it encounters any issues; error string contains the number of issues found.</span></span> <span data-ttu-id="ebbdd-179">否则，它将成功运行。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-179">Else, it runs successfully.</span></span> <span data-ttu-id="ebbdd-180">您可以在作业历史中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-180">You can see the details in the job history.</span></span> <span data-ttu-id="ebbdd-181">如果使用管理员权限运行作业，则错误字符串和作业历史还将记录到事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-181">If you run the job with Administrator privileges, error string will be logged to Event Viewer also (along with the job history).</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ebbdd-182">故障排除</span><span class="sxs-lookup"><span data-stu-id="ebbdd-182">Troubleshooting</span></span>  
 <span data-ttu-id="ebbdd-183">在发觉 BizTalk Server 应用程序（而非基础结构）的运行状况问题之后，可以使用 BizTalk Server 管理控制台中的“组中心”页和“查询”页来分析此问题。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-183">Once you are aware of a health problem with your BizTalk Server applications (not infrastructure), you can use the Group Hub page and Query pages in the BizTalk Server Administration Console to analyze the problem.</span></span> <span data-ttu-id="ebbdd-184">BizTalk Server 管理控制台提供了全面的配置、部署和疑难解答体验，当您在查明与配置和部署相关的问题之后，可以在管理控制台内修复它们。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-184">The BizTalk Server Administration Console provides an integrated configuration, deployment and troubleshooting experience, and you can fix configuration and deployment related problems within the Administration Console after you have pinpointed them.</span></span> <span data-ttu-id="ebbdd-185">通常，大多数应用程序问题是由于消息未按预期到达而导致的（这可能表现为已挂起的服务实例、正在重试端口或尚未重新激活的已冻结实例等）。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-185">Typically, most application problems are due to messages not getting through as expected (this can manifest as suspended service instances, or retrying ports, or dehydrated instances that have not been reactivated, etc.)</span></span>  
  
 <span data-ttu-id="ebbdd-186">可以使用“组中心”页和“查询”页按应用程序、错误类型、服务类型、主机等对服务实例进行分组（无论它们处于何种状态：正在运行、已挂起、已冻结等），以隔离不同的错误、逐个调查错误并修复它们。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-186">You can use the Group Hub page and Query pages to group your service instances (whatever state they are in: running, suspended, dehydrated, etc) by Application, Error type, Service Type, Host, etc, to isolate the different errors, investigate them one by one, and fix them.</span></span> <span data-ttu-id="ebbdd-187">还可以从 BizTalk Server 管理控制台中监视跟踪数据，以调查消息流的历史数据或有关业务流程或规则集执行的历史数据。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-187">You can also monitor tracking data from within the BizTalk Server Administration Console, to investigate the history of a message flow, or the history of execution of an orchestration or rule set.</span></span> <span data-ttu-id="ebbdd-188">此跟踪数据包含有关 BizTalk Server 应用程序的历史数据。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-188">This tracking data contains historical data about your BizTalk Server applications.</span></span>  
  
 <span data-ttu-id="ebbdd-189">如果已在 BizTalk 管理控制台中启用跟踪，则可以使用跟踪以通过查询找到消息流和服务。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-189">If you have enabled tracking in the BizTalk Administration Console, you can use tracking to locate message flow and service instances using a query.</span></span> <span data-ttu-id="ebbdd-190">例如，如果您希望找到某条消息，但您只知道消息类型（架构）、某个属性及其值（如客户名称）等，此功能很有用。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-190">This is useful when you want to locate a message and know only, for example, the message type (schema), a property and its value (for example, customer name), etc.</span></span>  
  
 <span data-ttu-id="ebbdd-191">以下主题讨论如何使用 BizTalk Server 管理控制台的“组中心”页和“查询”页来进行监视和疑难解答。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-191">The following topics discuss monitoring and troubleshooting using the BizTalk Server Administration Console, Group Hub page, and Query pages.</span></span> <span data-ttu-id="ebbdd-192">本节还讨论了跟踪，您可以使用它来帮助您进行疑难解答和根源分析。</span><span class="sxs-lookup"><span data-stu-id="ebbdd-192">This section also discusses tracking, which you can use as an aid in troubleshooting and root-cause analysis.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="ebbdd-193">多个很好的内容</span><span class="sxs-lookup"><span data-stu-id="ebbdd-193">More good stuff</span></span>  
  
-   [<span data-ttu-id="ebbdd-194">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="ebbdd-194">Using the BizTalk Server Administration Console</span></span>](../core/using-the-biztalk-server-administration-console.md)  
  
-   [<span data-ttu-id="ebbdd-195">查看跟踪的消息和实例数据</span><span class="sxs-lookup"><span data-stu-id="ebbdd-195">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [<span data-ttu-id="ebbdd-196">监视 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="ebbdd-196">Monitoring EDI and AS2 Solutions</span></span>](../core/monitoring-edi-and-as2-solutions.md)  
  
-   [<span data-ttu-id="ebbdd-197">跟踪 BizTalk Server 应用程序中的项目之间的依赖关系</span><span class="sxs-lookup"><span data-stu-id="ebbdd-197">Tracking Dependencies Between Artifacts in a BizTalk Server Application</span></span>](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md)

- [<span data-ttu-id="ebbdd-198">性能计数器</span><span class="sxs-lookup"><span data-stu-id="ebbdd-198">Performance Counters</span></span>](performance-counters.md)