---
title: 监视运行状况和性能使用内置工具 |Microsoft Docs
description: 可用性、 运行状况和性能监视中 BizTalk Server 和监视 SQL 代理作业
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
ms.openlocfilehash: c1fe69e9d1b63516a51230335aaf109e2de35f1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394391"
---
# <a name="monitoring-biztalk-server"></a><span data-ttu-id="f97ee-103">监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f97ee-103">Monitoring BizTalk Server</span></span>
<span data-ttu-id="f97ee-104">监视 BizTalk Server 应用程序和定期的基础结构和解决您发现任何问题有助于使 BizTalk Server 应用程序保持在用户访问的。</span><span class="sxs-lookup"><span data-stu-id="f97ee-104">Monitoring your BizTalk Server applications and infrastructure on a regular basis and resolving any issues that you find helps to keep your BizTalk Server applications accessible to your users.</span></span> <span data-ttu-id="f97ee-105">监视的目的是时间的最小化的异常存在未检测到，因此，未解决量。</span><span class="sxs-lookup"><span data-stu-id="f97ee-105">The goal of monitoring is to minimize the amount of time that an exception goes undetected and, therefore, unresolved.</span></span> <span data-ttu-id="f97ee-106">此外，您可以使用监视来帮助检测可能会导致异常的情况。</span><span class="sxs-lookup"><span data-stu-id="f97ee-106">Additionally, you can use monitoring to help detect situations that might cause an exception.</span></span>  
  
 <span data-ttu-id="f97ee-107">当监视 BizTalk Server，您应查找任何意外或异常行为。</span><span class="sxs-lookup"><span data-stu-id="f97ee-107">When monitoring BizTalk Server, you should look for any unexpected or anomalous behavior.</span></span> <span data-ttu-id="f97ee-108">监视可以手动或自动过程。</span><span class="sxs-lookup"><span data-stu-id="f97ee-108">Monitoring can be either a manual or automatic process.</span></span> <span data-ttu-id="f97ee-109">你可以监视使用 BizTalk Server 基础结构使用 BizTalk Server 管理控制台的运行状况。</span><span class="sxs-lookup"><span data-stu-id="f97ee-109">You can monitor use the health of your BizTalk Server infrastructure using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="f97ee-110">可以使用 BizTalk Server 管理控制台监视 BizTalk Server 应用程序的运行状况并执行根本原因分析，以确定任何问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="f97ee-110">You can use the BizTalk Server Administration Console to monitor the health of your BizTalk Server applications and perform root-cause analysis to identify the underlying cause of any problems.</span></span> <span data-ttu-id="f97ee-111">.</span><span class="sxs-lookup"><span data-stu-id="f97ee-111">.</span></span> <span data-ttu-id="f97ee-112">当监视 BizTalk Server，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="f97ee-112">When monitoring BizTalk Server, keep these points in mind:</span></span>  
  
- <span data-ttu-id="f97ee-113">你的基础结构可能处于正常状态，但可能不是您的应用程序 （例如，它们正在接收无效消息和无法处理它们）。</span><span class="sxs-lookup"><span data-stu-id="f97ee-113">Your infrastructure could be healthy, but your applications might not be (for example, they are receiving invalid messages and are unable to process them).</span></span>  
  
- <span data-ttu-id="f97ee-114">你的基础结构可能并不正常，但您的应用程序可能正在正常运行 （例如，如果服务器已关闭，但有足够的服务器分配给主机来接管负载）。</span><span class="sxs-lookup"><span data-stu-id="f97ee-114">Your infrastructure could be unhealthy, but your applications might be running fine (for example, if a server is down, but there are enough servers assigned to the host to take over the load).</span></span>  
  
- <span data-ttu-id="f97ee-115">基础结构问题可能表现为应用程序问题 （例如，不处理消息速度不够快因为服务器已关闭）。</span><span class="sxs-lookup"><span data-stu-id="f97ee-115">An infrastructure problem could surface as an application problem (for example, messages are not being processed fast enough because a server is down).</span></span>  
  
  <span data-ttu-id="f97ee-116">监视 BizTalk Server 和应用程序划分为三个主要类别：</span><span class="sxs-lookup"><span data-stu-id="f97ee-116">Monitoring your BizTalk Server and Applications falls into three main categories:</span></span>  
  
- <span data-ttu-id="f97ee-117">可用性监视</span><span class="sxs-lookup"><span data-stu-id="f97ee-117">Availability monitoring</span></span>  
  
- <span data-ttu-id="f97ee-118">运行状况监视</span><span class="sxs-lookup"><span data-stu-id="f97ee-118">Health monitoring</span></span>  
  
- <span data-ttu-id="f97ee-119">性能监视</span><span class="sxs-lookup"><span data-stu-id="f97ee-119">Performance monitoring</span></span>  
  
## <a name="availability-monitoring"></a><span data-ttu-id="f97ee-120">可用性监视</span><span class="sxs-lookup"><span data-stu-id="f97ee-120">Availability Monitoring</span></span>  
 <span data-ttu-id="f97ee-121">可用性监视回答的问题"是阻止您以最佳方式运行的 BizTalk Server 应用程序的系统或应用程序资源不可用导致？"</span><span class="sxs-lookup"><span data-stu-id="f97ee-121">Availability monitoring answers the question "Is the inavailability of a system or application resource preventing your BizTalk Server applications from running optimally?"</span></span> <span data-ttu-id="f97ee-122">这些问题是几乎专用系统级别，如服务和连接的可用性。</span><span class="sxs-lookup"><span data-stu-id="f97ee-122">These issues are almost exclusively system-level, such as availability of services and connections.</span></span> <span data-ttu-id="f97ee-123">例如，如果适配器失败，因为企业单一登录服务已停止，这是一个可用性问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-123">For example, if an adapter is failing because the Enterprise Single Sign-On service is stopped, this is an availability issue.</span></span> <span data-ttu-id="f97ee-124">如果其中一个分配给主机的服务器出现故障，并且你的应用程序落后在处理消息，您遇到了可用性问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-124">If one of the servers assigned to a host has failed and your application is falling behind on processing messages, you have an availability issue.</span></span> <span data-ttu-id="f97ee-125">同样，如果应用程序已停止，且无法处理消息，则您遇到了可用性问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-125">Likewise, if an application is stopped and is unable to process messages, you have an availability issue.</span></span> <span data-ttu-id="f97ee-126">下表显示了监视工具的可用性。</span><span class="sxs-lookup"><span data-stu-id="f97ee-126">The following table shows availability monitoring tools.</span></span>  
  
|<span data-ttu-id="f97ee-127">Tool</span><span class="sxs-lookup"><span data-stu-id="f97ee-127">Tool</span></span>|<span data-ttu-id="f97ee-128">任务</span><span class="sxs-lookup"><span data-stu-id="f97ee-128">Task</span></span>|  
|----------|----------|  
|<span data-ttu-id="f97ee-129">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="f97ee-129">BizTalk Server Administration Console</span></span>|<span data-ttu-id="f97ee-130">您应查看 BizTalk Server 管理控制台以查看已停止应用程序或其组件 （端口/业务流程） 中的组中心页。</span><span class="sxs-lookup"><span data-stu-id="f97ee-130">You should look at the Group Hub page in the BizTalk Server Administration Console to see if applications or their components (ports/orchestrations) are stopped.</span></span>|  
|<span data-ttu-id="f97ee-131">事件查看器</span><span class="sxs-lookup"><span data-stu-id="f97ee-131">Event Viewer</span></span>|<span data-ttu-id="f97ee-132">查找适配器连接问题、 已停止的服务，等等。</span><span class="sxs-lookup"><span data-stu-id="f97ee-132">Look for adapter connection issues, stopped services, and so on.</span></span>|  
  
## <a name="health-monitoring"></a><span data-ttu-id="f97ee-133">运行状况监视</span><span class="sxs-lookup"><span data-stu-id="f97ee-133">Health Monitoring</span></span>  
 <span data-ttu-id="f97ee-134">运行状况监视有助于回答问题，"在我的应用程序或资源的任何错误运行状况中？"</span><span class="sxs-lookup"><span data-stu-id="f97ee-134">Health monitoring helps you answer the question, "Are any of my applications or resources in bad health?"</span></span> <span data-ttu-id="f97ee-135">例如，是我的应用程序或其构成项目的任何当前遇到异常条件？</span><span class="sxs-lookup"><span data-stu-id="f97ee-135">For example, are any of my applications or their constituent artifacts currently experiencing exception conditions?</span></span> <span data-ttu-id="f97ee-136">或者，由于消息负载中的数据无效而挂起的消息？</span><span class="sxs-lookup"><span data-stu-id="f97ee-136">Or, are messages suspended because of invalid data in the message payload?</span></span> <span data-ttu-id="f97ee-137">下表显示了运行状况监视工具。</span><span class="sxs-lookup"><span data-stu-id="f97ee-137">The following table shows health-monitoring tools.</span></span>  
  
|<span data-ttu-id="f97ee-138">Tool</span><span class="sxs-lookup"><span data-stu-id="f97ee-138">Tool</span></span>|<span data-ttu-id="f97ee-139">任务</span><span class="sxs-lookup"><span data-stu-id="f97ee-139">Task</span></span>|  
|----------|----------|  
|<span data-ttu-id="f97ee-140">BizTalk 运行状况监视器 (BHM) 工具</span><span class="sxs-lookup"><span data-stu-id="f97ee-140">BizTalk Health Monitor tool (BHM)</span></span>|<span data-ttu-id="f97ee-141">用户可以监视 BizTalk Server 环境的运行状况 mmc 管理单元检测关键和非关键问题，并执行维护任务。</span><span class="sxs-lookup"><span data-stu-id="f97ee-141">An MMC snap-in for users to monitor the health of BizTalk Server environments, detect critical and non-critical issues, and execute maintenance tasks.</span></span>  <span data-ttu-id="f97ee-142">[下载 BizTalk 运行状况监视器](https://www.microsoft.com/download/details.aspx?id=43716)。</span><span class="sxs-lookup"><span data-stu-id="f97ee-142">[Download BizTalk Health Monitor](https://www.microsoft.com/download/details.aspx?id=43716).</span></span>|  
|<span data-ttu-id="f97ee-143">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="f97ee-143">BizTalk Server Administration Console</span></span>|<span data-ttu-id="f97ee-144">您将使用的组中心页和查询页在 BizTalk Server 管理控制台中，识别应用程序运行状况问题和分析问题原因。</span><span class="sxs-lookup"><span data-stu-id="f97ee-144">You will use the Group Hub page and query pages in the BizTalk Server Administration Console to identify application health problems and analyze their cause(s).</span></span>|  
|<span data-ttu-id="f97ee-145">事件查看器</span><span class="sxs-lookup"><span data-stu-id="f97ee-145">Event Viewer</span></span>|<span data-ttu-id="f97ee-146">检测到的消息和业务流程处理过程中出现的问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-146">Detect problems that occur during the processing of messages and orchestrations.</span></span>|  
  
## <a name="performance-monitoring"></a><span data-ttu-id="f97ee-147">性能监视</span><span class="sxs-lookup"><span data-stu-id="f97ee-147">Performance Monitoring</span></span>  
 <span data-ttu-id="f97ee-148">性能监视回答的问题，"如何有效地为系统执行其工作的？"</span><span class="sxs-lookup"><span data-stu-id="f97ee-148">Performance monitoring answers the question, "How efficiently is the system performing its work?"</span></span> <span data-ttu-id="f97ee-149">这种监视主要关注物理资源上的负载，如数据库和磁盘。</span><span class="sxs-lookup"><span data-stu-id="f97ee-149">This kind of monitoring focuses primarily on the load on physical resources like databases and disks.</span></span> <span data-ttu-id="f97ee-150">例如，如果 CPU 使用率一致地为 90 到 100%且造成消息积压，这是在计算机级别的性能问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-150">For example, if the CPU utilization is consistently at 90 to 100 percent and a backlog of messages is forming, this is a performance issue at the computer level.</span></span> <span data-ttu-id="f97ee-151">下表显示了性能监视工具。</span><span class="sxs-lookup"><span data-stu-id="f97ee-151">The following table shows performance-monitoring tools.</span></span>  
  
|<span data-ttu-id="f97ee-152">Tool</span><span class="sxs-lookup"><span data-stu-id="f97ee-152">Tool</span></span>|<span data-ttu-id="f97ee-153">任务</span><span class="sxs-lookup"><span data-stu-id="f97ee-153">Task</span></span>|  
|----------|----------|  
|<span data-ttu-id="f97ee-154">SQL 查询分析器</span><span class="sxs-lookup"><span data-stu-id="f97ee-154">SQL Query Analyzer</span></span>|<span data-ttu-id="f97ee-155">监视数据库大小和内容，以诊断系统问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-155">Monitor database size and content to diagnose system problems.</span></span>|  
|<span data-ttu-id="f97ee-156">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="f97ee-156">BizTalk Server Administration Console</span></span>|<span data-ttu-id="f97ee-157">组中心页显示关键性能指标，如服务实例数，当前处于活动状态、 已冻结，您可以随时运行、 计划、 挂起、 等。 在 BizTalk Server 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="f97ee-157">The Group Hub Page shows key performance metrics such as the number of service instances currently active, dehydrated, ready to run, scheduled, suspended, etc. in your BizTalk Server applications.</span></span>|  
|<span data-ttu-id="f97ee-158">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="f97ee-158">Business Activity Monitoring (BAM)</span></span>|<span data-ttu-id="f97ee-159">你想要跟踪与业务应用程序无关的关键性能指标在业务流程中，可以指定特定阶段。</span><span class="sxs-lookup"><span data-stu-id="f97ee-159">You can specify specific stages in your business process for which you want to track key performance indicators pertinent to your business application.</span></span>|  
  
## <a name="biztalk-server-monitoring"></a><span data-ttu-id="f97ee-160">BizTalk 服务器监视</span><span class="sxs-lookup"><span data-stu-id="f97ee-160">BizTalk Server Monitoring</span></span>  
 <span data-ttu-id="f97ee-161">你可以运行**监视 BizTalk Server** SQL 代理作业，以标识管理、 消息框中或 DTA 数据库中的任何已知的问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-161">You can run the **Monitor BizTalk Server** SQL Agent job to identify any known issues in Management, Message Box, or DTA databases.</span></span> <span data-ttu-id="f97ee-162">在 BizTalk Server 管理控制台中配置 BizTalk 组或从早期版本升级 BizTalk 时创建作业。</span><span class="sxs-lookup"><span data-stu-id="f97ee-162">The job is created when you configure a BizTalk group in BizTalk Server Administration console or upgrade BizTalk from the previous version.</span></span>  
  
 <span data-ttu-id="f97ee-163">监视 BizTalk Server 作业扫描管理、 消息框和 DTA 数据库中的以下问题：</span><span class="sxs-lookup"><span data-stu-id="f97ee-163">The Monitor BizTalk Server job scans for the following issues in Management, Message Box, and DTA databases:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f97ee-164">监视 BizTalk Server 作业仅扫描问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-164">The Monitor BizTalk Server job only scans for issues.</span></span> <span data-ttu-id="f97ee-165">它不能解决发现的问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-165">It does not fix the issues found.</span></span>  
  
- <span data-ttu-id="f97ee-166">没有任何引用的消息</span><span class="sxs-lookup"><span data-stu-id="f97ee-166">Messages without any references</span></span>  
  
- <span data-ttu-id="f97ee-167">没有引用计数的消息</span><span class="sxs-lookup"><span data-stu-id="f97ee-167">Messages without reference counts</span></span>  
  
- <span data-ttu-id="f97ee-168">具有引用计数小于 0 的消息</span><span class="sxs-lookup"><span data-stu-id="f97ee-168">Messages with reference count less than 0</span></span>  
  
- <span data-ttu-id="f97ee-169">无后台行的消息引用</span><span class="sxs-lookup"><span data-stu-id="f97ee-169">Message references without spool rows</span></span>  
  
- <span data-ttu-id="f97ee-170">没有实例的消息引用</span><span class="sxs-lookup"><span data-stu-id="f97ee-170">Message references without instances</span></span>  
  
- <span data-ttu-id="f97ee-171">没有实例的实例状态</span><span class="sxs-lookup"><span data-stu-id="f97ee-171">Instance state without instances</span></span>  
  
- <span data-ttu-id="f97ee-172">没有相应的实例的实例订阅</span><span class="sxs-lookup"><span data-stu-id="f97ee-172">Instance subscriptions without corresponding instances</span></span>  
  
- <span data-ttu-id="f97ee-173">孤立的 DTA 服务实例</span><span class="sxs-lookup"><span data-stu-id="f97ee-173">Orphaned DTA service instances</span></span>  
  
- <span data-ttu-id="f97ee-174">孤立的 DTA 服务实例异常</span><span class="sxs-lookup"><span data-stu-id="f97ee-174">Orphaned DTA service instance exceptions</span></span>  
  
- <span data-ttu-id="f97ee-175">TDDS 未运行任何主机实例上启用全局跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="f97ee-175">TDDS is not running on any host instance when global tracking option is enabled.</span></span>  
  
  <span data-ttu-id="f97ee-176">监视 BizTalk Server 作业配置和自动运行一次在一周内。</span><span class="sxs-lookup"><span data-stu-id="f97ee-176">The Monitor BizTalk Server job is configured and automated to run once in a week.</span></span> <span data-ttu-id="f97ee-177">由于是计算密集型作业，我们建议您计划在停机/低流量期间。</span><span class="sxs-lookup"><span data-stu-id="f97ee-177">Since the job is computationally intensive, we recommended you to schedule it during downtime/low traffic.</span></span>  
  
  <span data-ttu-id="f97ee-178">作业失败时如果遇到任何问题;错误字符串包含找到的问题数。</span><span class="sxs-lookup"><span data-stu-id="f97ee-178">The job fails if it encounters any issues; error string contains the number of issues found.</span></span> <span data-ttu-id="f97ee-179">否则，它将成功运行。</span><span class="sxs-lookup"><span data-stu-id="f97ee-179">Else, it runs successfully.</span></span> <span data-ttu-id="f97ee-180">您可以看到作业历史记录中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f97ee-180">You can see the details in the job history.</span></span> <span data-ttu-id="f97ee-181">如果使用管理员特权运行该作业，错误字符串将会记录到事件查看器还 （以及作业历史记录）。</span><span class="sxs-lookup"><span data-stu-id="f97ee-181">If you run the job with Administrator privileges, error string will be logged to Event Viewer also (along with the job history).</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f97ee-182">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f97ee-182">Troubleshooting</span></span>  
 <span data-ttu-id="f97ee-183">注意与 BizTalk Server 应用程序 （而不是基础结构） 的运行状况问题后，你可以使用组中心页和查询页在 BizTalk Server 管理控制台来分析此问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-183">Once you are aware of a health problem with your BizTalk Server applications (not infrastructure), you can use the Group Hub page and Query pages in the BizTalk Server Administration Console to analyze the problem.</span></span> <span data-ttu-id="f97ee-184">在 BizTalk Server 管理控制台提供了集成的配置、 部署和疑难解答体验，并可以修复配置和部署后当您在查明它们相关的管理控制台中的问题。</span><span class="sxs-lookup"><span data-stu-id="f97ee-184">The BizTalk Server Administration Console provides an integrated configuration, deployment and troubleshooting experience, and you can fix configuration and deployment related problems within the Administration Console after you have pinpointed them.</span></span> <span data-ttu-id="f97ee-185">通常情况下，大多数应用程序问题由于消息未获得按预期方式 (这可能表现为挂起的服务实例，或重试端口或尚未重新激活的已冻结的实例，等等。)</span><span class="sxs-lookup"><span data-stu-id="f97ee-185">Typically, most application problems are due to messages not getting through as expected (this can manifest as suspended service instances, or retrying ports, or dehydrated instances that have not been reactivated, etc.)</span></span>  
  
 <span data-ttu-id="f97ee-186">可以使用组中心页和查询页服务实例进行分组 (它们处于任何状态： 运行、 挂起、 已冻结，等等) 的应用程序，错误的类型、 服务类型、 主机等，来隔离不同错误、 逐个进行，调查和修复它们。</span><span class="sxs-lookup"><span data-stu-id="f97ee-186">You can use the Group Hub page and Query pages to group your service instances (whatever state they are in: running, suspended, dehydrated, etc) by Application, Error type, Service Type, Host, etc, to isolate the different errors, investigate them one by one, and fix them.</span></span> <span data-ttu-id="f97ee-187">你还可以监视 BizTalk Server 管理控制台中，以调查消息流的历史记录中的跟踪数据或业务流程或规则的执行历史记录设置。</span><span class="sxs-lookup"><span data-stu-id="f97ee-187">You can also monitor tracking data from within the BizTalk Server Administration Console, to investigate the history of a message flow, or the history of execution of an orchestration or rule set.</span></span> <span data-ttu-id="f97ee-188">此跟踪数据包含有关 BizTalk Server 应用程序的历史数据。</span><span class="sxs-lookup"><span data-stu-id="f97ee-188">This tracking data contains historical data about your BizTalk Server applications.</span></span>  
  
 <span data-ttu-id="f97ee-189">如果已启用跟踪 BizTalk 管理控制台中的，可以使用跟踪来查找消息流和服务实例使用的查询。</span><span class="sxs-lookup"><span data-stu-id="f97ee-189">If you have enabled tracking in the BizTalk Administration Console, you can use tracking to locate message flow and service instances using a query.</span></span> <span data-ttu-id="f97ee-190">如果想要查找的消息并知道，例如，消息类型 （架构）、 一个属性及其值 （例如，客户名称）、 等，这很有用。</span><span class="sxs-lookup"><span data-stu-id="f97ee-190">This is useful when you want to locate a message and know only, for example, the message type (schema), a property and its value (for example, customer name), etc.</span></span>  
  
 <span data-ttu-id="f97ee-191">以下主题讨论如何监视和使用 BizTalk Server 管理控制台中，组中心页上，进行故障排除和查询页。</span><span class="sxs-lookup"><span data-stu-id="f97ee-191">The following topics discuss monitoring and troubleshooting using the BizTalk Server Administration Console, Group Hub page, and Query pages.</span></span> <span data-ttu-id="f97ee-192">本部分还讨论了跟踪，可以使用疑难解答和根本原因分析提供帮助。</span><span class="sxs-lookup"><span data-stu-id="f97ee-192">This section also discusses tracking, which you can use as an aid in troubleshooting and root-cause analysis.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="f97ee-193">更多有用资料</span><span class="sxs-lookup"><span data-stu-id="f97ee-193">More good stuff</span></span>  
  
-   [<span data-ttu-id="f97ee-194">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="f97ee-194">Using the BizTalk Server Administration Console</span></span>](../core/using-the-biztalk-server-administration-console.md)  
  
-   [<span data-ttu-id="f97ee-195">查看跟踪的消息和实例数据</span><span class="sxs-lookup"><span data-stu-id="f97ee-195">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [<span data-ttu-id="f97ee-196">监视 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="f97ee-196">Monitoring EDI and AS2 Solutions</span></span>](../core/monitoring-edi-and-as2-solutions.md)  
  
-   [<span data-ttu-id="f97ee-197">跟踪 BizTalk Server 应用程序中的项目之间的依赖关系</span><span class="sxs-lookup"><span data-stu-id="f97ee-197">Tracking Dependencies Between Artifacts in a BizTalk Server Application</span></span>](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md)

- [<span data-ttu-id="f97ee-198">性能计数器</span><span class="sxs-lookup"><span data-stu-id="f97ee-198">Performance Counters</span></span>](performance-counters.md)