---
title: 什么是可持续的性能？ |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- reliability, sustainable performance
- performance, goals
- performance, sustainable performance
- planning, performance
- performance, planning
- sustainable performance
ms.assetid: 4b18b976-7714-431f-8976-f40a1016d5f3
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 276ce104d8667166d020b33b2f1fb4e7bfb98dbc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="what-is-sustainable-performance"></a><span data-ttu-id="ee5db-103">什么是可持续的性能？</span><span class="sxs-lookup"><span data-stu-id="ee5db-103">What Is Sustainable Performance?</span></span>
<span data-ttu-id="ee5db-104">在规划和估计系统可持续性，考虑长远来看的可持续性至关重要。</span><span class="sxs-lookup"><span data-stu-id="ee5db-104">When planning for and estimating system sustainability, it is critical to think in terms of sustainability over the long term.</span></span> <span data-ttu-id="ee5db-105">主要考虑包括︰</span><span class="sxs-lookup"><span data-stu-id="ee5db-105">The primary considerations are:</span></span>  
  
-   <span data-ttu-id="ee5db-106">**加载配置文件和性能目标**︰ 时加载配置文件和性能目标，不能有太多的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ee5db-106">**Load Profiles and Performance Goals**: You can't have too much detail when it comes to load profiles and performance goals.</span></span> <span data-ttu-id="ee5db-107">测试和准备情况的证书颁发将基于能够处理这些加载从长远来看。</span><span class="sxs-lookup"><span data-stu-id="ee5db-107">Testing and readiness certification will be based on being able to handle these loads long term.</span></span>  
  
-   <span data-ttu-id="ee5db-108">**其他活动和争用服务器资源的进程**︰ 并不只是关于消息负载。</span><span class="sxs-lookup"><span data-stu-id="ee5db-108">**Other Activities and Processes that Compete for Server Resources**: It isn’t just about the message load.</span></span> <span data-ttu-id="ee5db-109">有其他进程和对等数据库维护 MessageBox 查询的性能影响的服务器上发生的活动。</span><span class="sxs-lookup"><span data-stu-id="ee5db-109">There are other processes and activities taking place on the servers that affect performance such as database maintenance and MessageBox queries.</span></span>  
  
-   <span data-ttu-id="ee5db-110">**计划和非计划的系统服务中断和停机时间**: Floodgate 事件和积压工作可以更改的有效负载配置文件的消息。</span><span class="sxs-lookup"><span data-stu-id="ee5db-110">**Planned and Unplanned System Outages and Downtime**: Floodgate events and message backlog can change the effective load profile.</span></span>  
  
 <span data-ttu-id="ee5db-111">在考虑生成可持续系统并执行测试以验证它们，请务必考虑以下因素帐户和它们的计划。</span><span class="sxs-lookup"><span data-stu-id="ee5db-111">When thinking about building sustainable systems and the tests to certify them, be sure to take these factors into account and plan for them.</span></span>  
  
## <a name="is-your-performance-sustainable"></a><span data-ttu-id="ee5db-112">是你的性能可持续？</span><span class="sxs-lookup"><span data-stu-id="ee5db-112">Is Your Performance Sustainable?</span></span>  
 <span data-ttu-id="ee5db-113">当讨论性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，我们定义最大可持续的性能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee5db-113">When discussing performance for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], we define maximum sustainable performance as follows:</span></span>  
  
-   <span data-ttu-id="ee5db-114">系统可以无限期地处理在生产环境中的消息流量最高负载。</span><span class="sxs-lookup"><span data-stu-id="ee5db-114">The highest load of message traffic that a system can handle indefinitely in a production environment.</span></span>  
  
 <span data-ttu-id="ee5db-115">尽管这看起来简单，有许多评估-一组特定的硬件上运行的解决方案将能够支持解决方案投入生产后遇到一天而且每天在加载时必须考虑的因素。</span><span class="sxs-lookup"><span data-stu-id="ee5db-115">While this seems simple, there are many factors that you must consider when evaluating whether or not a solution - running on a particular set of hardware - will be able to support the loads experienced day in and day out after you put the solution into production.</span></span>  
  
 <span data-ttu-id="ee5db-116">在将解决方案投入生产前，请考虑以下因素以评估该解决方案是否可无限制处理最高消息通信负载：</span><span class="sxs-lookup"><span data-stu-id="ee5db-116">Before you put your solution into production, consider the following factors to evaluate whether the solution can handle the highest load of message traffic indefinitely:</span></span>  
  
-   <span data-ttu-id="ee5db-117">预期的性能目标和吞吐量/延迟状况。</span><span class="sxs-lookup"><span data-stu-id="ee5db-117">Desired Performance Goals and Throughput/Latency profiles.</span></span>  
  
-   <span data-ttu-id="ee5db-118">在同一硬件上运行的其他进程，例如：</span><span class="sxs-lookup"><span data-stu-id="ee5db-118">Other Processes Running on the Same Hardware such as:</span></span>  
  
    -   <span data-ttu-id="ee5db-119">常规监视和故障排除</span><span class="sxs-lookup"><span data-stu-id="ee5db-119">Normal Monitoring and Troubleshooting</span></span>  
  
    -   <span data-ttu-id="ee5db-120">操作数据库维护，例如日志传送、备份、清除、索引维护和统计信息更新。</span><span class="sxs-lookup"><span data-stu-id="ee5db-120">Operational database maintenance such as log shipping, backup, purging, index maintenance, and statistics updates.</span></span>  
  
    -   <span data-ttu-id="ee5db-121">其他应用程序</span><span class="sxs-lookup"><span data-stu-id="ee5db-121">Other Applications</span></span>  
  
-   <span data-ttu-id="ee5db-122">计划内和计划外的系统停用，例如：</span><span class="sxs-lookup"><span data-stu-id="ee5db-122">Planned and Unplanned System Outages such as:</span></span>  
  
    -   <span data-ttu-id="ee5db-123">合作伙伴站点中断，阻止发送或接收消息</span><span class="sxs-lookup"><span data-stu-id="ee5db-123">Partner sites down which blocks sending or receiving messages</span></span>  
  
    -   <span data-ttu-id="ee5db-124">常规系统维护停机时间</span><span class="sxs-lookup"><span data-stu-id="ee5db-124">Regular system maintenance down time</span></span>  
  
## <a name="know-your-performance-goals"></a><span data-ttu-id="ee5db-125">了解您的性能目标</span><span class="sxs-lookup"><span data-stu-id="ee5db-125">Know Your Performance Goals</span></span>  
 <span data-ttu-id="ee5db-126">您必须首先详细了解生产期望目标，然后才能评估解决方案的可维持性。</span><span class="sxs-lookup"><span data-stu-id="ee5db-126">Before you can evaluate your solution for sustainability, you must have a detailed understanding of the expected production loads.</span></span> <span data-ttu-id="ee5db-127">如果没有明确的目标，则无法评估准备情况。</span><span class="sxs-lookup"><span data-stu-id="ee5db-127">Without a well understood goal, you can't evaluate readiness.</span></span> <span data-ttu-id="ee5db-128">一组设计良好的性能目标很关键，因为它能使您的策略以系统测试和系统证书为中心。</span><span class="sxs-lookup"><span data-stu-id="ee5db-128">A well formed set of performance goals is critical as it will drive your strategies around system testing and certification.</span></span> <span data-ttu-id="ee5db-129">您的性能目标应包含以下要素：</span><span class="sxs-lookup"><span data-stu-id="ee5db-129">Your performance goals should have the following elements:</span></span>  
  
-   <span data-ttu-id="ee5db-130">将性能定义为时间的函数的曲线。</span><span class="sxs-lookup"><span data-stu-id="ee5db-130">A curve that defines performance as a function of time.</span></span> <span data-ttu-id="ee5db-131">这些函数可以非常简单，也可以非常复杂。</span><span class="sxs-lookup"><span data-stu-id="ee5db-131">These functions can range from extremely simple to very complex.</span></span>  
  
-   <span data-ttu-id="ee5db-132">与性能函数相关联的性能要求。</span><span class="sxs-lookup"><span data-stu-id="ee5db-132">A performance requirement associated with the performance function.</span></span>  
  
-   <span data-ttu-id="ee5db-133">文件大小和类型的分布。</span><span class="sxs-lookup"><span data-stu-id="ee5db-133">A distribution of file sizes and types.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="ee5db-134">示例 1</span><span class="sxs-lookup"><span data-stu-id="ee5db-134">Example 1</span></span>  
  
-   <span data-ttu-id="ee5db-135">每天，消息从早上 8:00 的每秒 0 条消息逐渐增加到中午的每秒 80 条消息，然后在晚上 9:00 又回落到每秒 0 条消息，大体上为钟形曲线的形式。</span><span class="sxs-lookup"><span data-stu-id="ee5db-135">Each day, messages build up from 0 msgs/sec at 8:00AM to 80 msgs/sec at noon and then back down to 0 msgs/sec at 9:00PM, roughly in the form of a bell curve.</span></span>  
  
-   <span data-ttu-id="ee5db-136">系统对每个消息没有具体的延迟要求，但它必须能够处理此负载，以及在不延期的情况下处理前一天的所有消息负载（例如，在发生 24 小时系统停用的情况下）。</span><span class="sxs-lookup"><span data-stu-id="ee5db-136">The system has no specific latency requirement for each message, but it must be able to process this load, plus all of the previous day’s message load (for example, in the event of a 24 hour system outage) without getting behind.</span></span>  
  
-   <span data-ttu-id="ee5db-137">有三种文档类型：销售篮、延期交货订单和库存请求。</span><span class="sxs-lookup"><span data-stu-id="ee5db-137">There are three document types: Sales Basket, Back Order, and Stock Request.</span></span> <span data-ttu-id="ee5db-138">销售篮文档的大小介于 2 到 10 KB 之间，并且在任何给定时间都占消息数的 75%。</span><span class="sxs-lookup"><span data-stu-id="ee5db-138">Sales Basket documents range in size between 2 and 10 kilobytes and make up 75% of the message counts at any given time.</span></span> <span data-ttu-id="ee5db-139">延期交货订单文档和库存请求文档的大小都始终在 1 KB 左右，在任何给定时间分别占剩余消息数的 10% 和 15%。</span><span class="sxs-lookup"><span data-stu-id="ee5db-139">Back Order and Stock Request documents are always close to 1 Kilobyte in size and make up the remaining, 10% and 15% of the message count at any given time, respectively.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="ee5db-140">示例 2</span><span class="sxs-lookup"><span data-stu-id="ee5db-140">Example 2</span></span>  
  
-   <span data-ttu-id="ee5db-141">每日午夜，一批 500,000 消息在到达进行处理。</span><span class="sxs-lookup"><span data-stu-id="ee5db-141">Every night at midnight, a batch of 500,000 messages arrive for processing.</span></span>  
  
-   <span data-ttu-id="ee5db-142">必须为 8 小时内完成处理批处理中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="ee5db-142">All messages in the batch must be processed to completion in 8 hours.</span></span>  
  
-   <span data-ttu-id="ee5db-143">所有消息均为相同类型和 10 到 50 千字节为单位，（含） 之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="ee5db-143">All messages are of the same type and are evenly distributed between 10 and 50 Kilobytes, inclusive.</span></span> <span data-ttu-id="ee5db-144">此外，批处理始终包含 10 目录类型条消息，会 10 兆字节每个必须细分为单独的目录条目进行处理。</span><span class="sxs-lookup"><span data-stu-id="ee5db-144">In addition, the batch always contains 10 catalog type messages that are 10 megabytes each and must be subdivided into individual catalog entries for processing.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="ee5db-145">示例 3</span><span class="sxs-lookup"><span data-stu-id="ee5db-145">Example 3</span></span>  
  
-   <span data-ttu-id="ee5db-146">在上午 8:00，每天早上 4000 客户服务代表登录到交互式系统和执行，一般情况下，每分钟至下午 5:00，每周 7 天的结束时间的代表每 4 的查询。</span><span class="sxs-lookup"><span data-stu-id="ee5db-146">Every morning at 8:00AM, 4000 customer service representatives log on to the interactive system and perform, on average, 4 inquiries per representative per minute until closing time at 5:00PM, 7 days per week.</span></span>  
  
-   <span data-ttu-id="ee5db-147">所有查询必须在小于 2 秒内都返回结果。</span><span class="sxs-lookup"><span data-stu-id="ee5db-147">All inquiries must return results in less than 2 seconds.</span></span>  
  
-   <span data-ttu-id="ee5db-148">所有查询都是相同类型和大小，非独占 500 到 1000年个字节之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="ee5db-148">All inquiries are the same type and are evenly distributed between 500 and 1000 bytes in size, inclusive.</span></span>  
  
#### <a name="a-performance-requirement-associated-with-the-performance-function"></a><span data-ttu-id="ee5db-149">性能要求与性能函数相关联</span><span class="sxs-lookup"><span data-stu-id="ee5db-149">A performance requirement associated with the performance function</span></span>  
 <span data-ttu-id="ee5db-150">继续上面的示例︰</span><span class="sxs-lookup"><span data-stu-id="ee5db-150">Continuing with the above examples:</span></span>  
  
-   <span data-ttu-id="ee5db-151">**示例 1 （续）**︰ 系统已为每个消息，没有特定的滞后时间要求，但它必须能够处理此负载，加上前一天的消息的所有加载 （例如、 发生时的 24 小时系统中断），而不获取。</span><span class="sxs-lookup"><span data-stu-id="ee5db-151">**Example 1 (continued)**:  The system has no specific latency requirement for each message, but it must be able to process this load, plus all of the previous day’s message load (for example,, in the event of a 24 hour system outage) without getting behind.</span></span>  
  
-   <span data-ttu-id="ee5db-152">**示例 2 （续）**︰ 批处理中的所有消息必须都处理 8 小时内完成。</span><span class="sxs-lookup"><span data-stu-id="ee5db-152">**Example 2 (continued)**:  All messages in the batch must be processed to completion in 8 hours.</span></span>  
  
-   <span data-ttu-id="ee5db-153">**示例 3 （续）**︰ 所有查询必须在小于 2 秒内都返回结果。</span><span class="sxs-lookup"><span data-stu-id="ee5db-153">**Example 3 (continued)**:  All inquiries must return results in less than 2 seconds.</span></span>  
  
#### <a name="a-distribution-of-file-sizes-and-types"></a><span data-ttu-id="ee5db-154">文件大小和类型的分发</span><span class="sxs-lookup"><span data-stu-id="ee5db-154">A distribution of file sizes and types</span></span>  
  
-   <span data-ttu-id="ee5db-155">**示例 1 （续）**︰ 有三种文档类型︰ 销售购物篮、 返回顺序和 Stock 请求。</span><span class="sxs-lookup"><span data-stu-id="ee5db-155">**Example 1 (continued)**: There are three document types: Sales Basket, Back Order, and Stock Request.</span></span> <span data-ttu-id="ee5db-156">销售篮文档的大小介于 2 到 10 KB 之间，并且在任何给定时间都占消息数的 75%。</span><span class="sxs-lookup"><span data-stu-id="ee5db-156">Sales Basket documents range in size between 2 and 10 kilobytes and make up 75% of the message counts at any given time.</span></span> <span data-ttu-id="ee5db-157">延期交货订单文档和库存请求文档的大小都始终在 1 KB 左右，在任何给定时间分别占剩余消息数的 10% 和 15%。</span><span class="sxs-lookup"><span data-stu-id="ee5db-157">Back Order and Stock Request documents are always close to 1 Kilobyte in size and make up the remaining, 10% and 15% of the message count at any given time, respectively.</span></span>  
  
-   <span data-ttu-id="ee5db-158">**示例 2 （续）**︰ 所有消息均为相同类型和 10 到 50 千字节为单位，（含） 之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="ee5db-158">**Example 2 (continued)**: All messages are of the same type and are evenly distributed between 10 and 50 Kilobytes, inclusive.</span></span> <span data-ttu-id="ee5db-159">此外，批处理始终包含 10 目录类型条消息，会 10 兆字节每个必须细分为单独的目录条目进行处理。</span><span class="sxs-lookup"><span data-stu-id="ee5db-159">In addition, the batch always contains 10 catalog type messages that are 10 megabytes each and must be subdivided into individual catalog entries for processing.</span></span>  
  
-   <span data-ttu-id="ee5db-160">**示例 3 （续）**︰ 所有查询都是相同类型和大小，非独占 500 到 1000年个字节之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="ee5db-160">**Example 3 (continued)**: All inquiries are the same type and are evenly distributed between 500 and 1000 bytes in size, inclusive.</span></span>  
  
## <a name="accounting-for-other-processes"></a><span data-ttu-id="ee5db-161">其他进程的记帐</span><span class="sxs-lookup"><span data-stu-id="ee5db-161">Accounting for Other Processes</span></span>  
 <span data-ttu-id="ee5db-162">除了直接通过 BizTalk 引擎的负载配置文件，始终有争用资源的相同硬件上其他进程中。</span><span class="sxs-lookup"><span data-stu-id="ee5db-162">In addition to the load profiles that pass directly through the BizTalk engine, there are always other processes that compete for resources on the same hardware.</span></span>  <span data-ttu-id="ee5db-163">这些其他进程将减少系统的整体可持续性能功能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-163">These other processes will reduce the overall sustainable performance capabilities of the system.</span></span> <span data-ttu-id="ee5db-164">数据库维护可能是过程的最常见的这种类型的示例。</span><span class="sxs-lookup"><span data-stu-id="ee5db-164">Database maintenance is probably the most common example of this type of process.</span></span>  
  
 <span data-ttu-id="ee5db-165">每个数据库，大或小，如需要操作的定期维护日志传送、 备份、 存档和清除。</span><span class="sxs-lookup"><span data-stu-id="ee5db-165">Every database, large or small, requires periodic operational maintenance such as log shipping, backup, archive, and purging.</span></span> <span data-ttu-id="ee5db-166">监视和故障排除是你必须考虑到在定义并在认证要什么可持续时的操作的其他示例。</span><span class="sxs-lookup"><span data-stu-id="ee5db-166">Monitoring and troubleshooting are other examples of operations that you must take into account when defining and certifying what is sustainable.</span></span> <span data-ttu-id="ee5db-167">例如，查询 （例如，通过管理控制台组中心数据库页） MessageBox 若要查看过去 24 小时内已挂起的给定类型的消息数需要从 SQL Server 中无法否则已用于处理消息的资源。</span><span class="sxs-lookup"><span data-stu-id="ee5db-167">For example, querying the MessageBox (for example, via the administration console Group Hub page) to see how many messages of a given type have been suspended in the last 24 hours requires resources from SQL Server that could otherwise have been used to process messages.</span></span>  
  
 <span data-ttu-id="ee5db-168">下面是通常将具有最大影响总体可持续性中的活动的列表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ee5db-168">Following is a list of activities that will typically have the most effect on overall sustainability in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="ee5db-169">**日志传送和备份**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-169">**Log Shipping and Backup**.</span></span> <span data-ttu-id="ee5db-170">作为涉及 SQL Server 的大多数灾难恢复计划的一部分，您必须为所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组数据库定期执行日志传送和备份。</span><span class="sxs-lookup"><span data-stu-id="ee5db-170">As part of most disaster recovery plans involving SQL Server, you must perform log shipping and backup periodically for all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group databases.</span></span> <span data-ttu-id="ee5db-171">有关详细信息，请参阅 [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-171">For more information, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span> <span data-ttu-id="ee5db-172">另请参阅[日志传送](../core/log-shipping.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-172">Also see [Log Shipping](../core/log-shipping.md).</span></span>  
  
-   <span data-ttu-id="ee5db-173">**存档和清除跟踪数据**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-173">**Archiving and Purging Tracking Data**.</span></span> <span data-ttu-id="ee5db-174">除了整体日志传送和备份计划，BizTalk 跟踪 (BizTalkDTADb) 数据库具有其自己存档和清除 regimes;有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-174">In addition to the overall log shipping and backup plan, the BizTalk Tracking (BizTalkDTADb) database has its own archive and purge regimes; for more information, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span> <span data-ttu-id="ee5db-175">在 BizTalk 跟踪数据库中存档和清除数据的速度尤其重要，因为在使用跟踪功能时这些操作通常会成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="ee5db-175">The speed at which data can be archived and purged from the BizTalk Tracking database is especially important since archiving and purging of the BizTalk Tracking database is typically a bottleneck when tracking is in use.</span></span>  
  
-   <span data-ttu-id="ee5db-176">**系统查询**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-176">**System Queries**.</span></span> <span data-ttu-id="ee5db-177">使用 Api 或 BizTalk Server 管理控制台用户界面对系统中运行各种类型的查询将会影响可持续的性能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-177">Using APIs or the BizTalk Server Administration Console UI to run various types of queries against the system will affect sustainable performance.</span></span>  
  
-   <span data-ttu-id="ee5db-178">**MessageBox 维护**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-178">**MessageBox Maintenance**.</span></span> <span data-ttu-id="ee5db-179">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 核心功能中包含许多 SQL 作业，这些作业通过清除和管理已完成处理的消息和实例，对 MessageBox 数据库进行维护。</span><span class="sxs-lookup"><span data-stu-id="ee5db-179">There are a number of SQL jobs that are part of the core functionality of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that maintain the MessageBox database by cleaning up messages and instances that have finished processing.</span></span> <span data-ttu-id="ee5db-180">作为核心引擎的一部分，完成这些作业的速度是衡量可维持性的重要因素。</span><span class="sxs-lookup"><span data-stu-id="ee5db-180">As part of the core engine, the speed at which these jobs can complete is a key factor in gauging sustainability.</span></span> <span data-ttu-id="ee5db-181">有关这些作业和其角色的详细信息，请参阅[维护 BizTalk Server1](../core/maintaining-biztalk-server1.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-181">For more information about these jobs and their role, see [Maintaining BizTalk Server1](../core/maintaining-biztalk-server1.md).</span></span>  
  
-   <span data-ttu-id="ee5db-182">**解决方案部署活动**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-182">**Solution Deployment Activities**.</span></span> <span data-ttu-id="ee5db-183">在部署、绑定和启动新应用程序或现有应用程序的新版本时，将会增加 BizTalk 的负载，例如对 MessageBox 数据库创建新的订阅。</span><span class="sxs-lookup"><span data-stu-id="ee5db-183">When deploying, binding, and starting new applications or new versions of existing applications, additional load is placed on BizTalk such as the creation of new subscriptions on the MessageBox database(s).</span></span> <span data-ttu-id="ee5db-184">部署应用程序后，正在处理的消息将争用资源，从而会影响现有应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-184">After applications are deployed, the messages being processed will compete for resources and thereby affect the performance of the existing applications.</span></span>  
  
 <span data-ttu-id="ee5db-185">对于上述每个区域中，你需要询问︰ 什么是你的建议，这些活动的影响降至最低？</span><span class="sxs-lookup"><span data-stu-id="ee5db-185">For each of these areas, you need to ask: What is your recommendation to minimize the impact of these activities?</span></span> <span data-ttu-id="ee5db-186">例如，它们应打算凌晨 3 点运行它们？</span><span class="sxs-lookup"><span data-stu-id="ee5db-186">For example, should they plan to run them at 3am?</span></span>  
  
## <a name="considering-planned-and-unplanned-outages"></a><span data-ttu-id="ee5db-187">考虑计划内和计划外中断</span><span class="sxs-lookup"><span data-stu-id="ee5db-187">Considering Planned and Unplanned Outages</span></span>  
 <span data-ttu-id="ee5db-188">中断对系统性能的影响将遇到服务中断，但是最常见的后果是系统而异︰</span><span class="sxs-lookup"><span data-stu-id="ee5db-188">The effects that outages have on the system performance will vary depending on the system experiencing the outage, however the most common consequences are:</span></span>  
  
-   <span data-ttu-id="ee5db-189">**Floodgate 事件**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-189">**Floodgate Events**.</span></span> <span data-ttu-id="ee5db-190">系统关闭后，某些段时间，消息可以建立，然后可以在一次到达，处理后各系统都试功能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-190">When systems are down for some length of time, messages can build up and then arrive all at once for processing once the systems are functional again.</span></span>  <span data-ttu-id="ee5db-191">例如，如果在 BizTalk 上运行的应用程序接收消息通过 MSMQ，并且该应用程序已关闭了一段时间，消息建立队列中等待拾取。</span><span class="sxs-lookup"><span data-stu-id="ee5db-191">For example, if an application running on BizTalk receives messages via MSMQ, and that application is down for some time, messages build up in the queues waiting to be picked up.</span></span> <span data-ttu-id="ee5db-192">再次启动应用程序时，就像大量消息的到达"在一次。"</span><span class="sxs-lookup"><span data-stu-id="ee5db-192">When the application is started up again, it is as if a large number of messages arrived "all at once."</span></span>  
  
-   <span data-ttu-id="ee5db-193">**消息积压工作**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-193">**Message Backlog**.</span></span> <span data-ttu-id="ee5db-194">当消息发送到的系统已关闭，没有通常是重试周期采用使用附加资源。</span><span class="sxs-lookup"><span data-stu-id="ee5db-194">When systems to which messages are sent are down, there is typically a retry cycle that is employed that uses additional resources.</span></span> <span data-ttu-id="ee5db-195">重试后已用尽周期，则消息通常将被挂起。</span><span class="sxs-lookup"><span data-stu-id="ee5db-195">After the retry cycle is exhausted, then messages are typically suspended.</span></span> <span data-ttu-id="ee5db-196">然后关闭的系统返回在行上，一种 floodgate 事件发生大量消息现在可在其中恢复和/或已成功发送。</span><span class="sxs-lookup"><span data-stu-id="ee5db-196">Then the downed systems come back on line, a type of floodgate event occurs where large numbers of messages can now be resumed and/or successfully sent.</span></span>  
  
 <span data-ttu-id="ee5db-197">当然任何计划内的停机 （如定期计划维护） 必须考虑到在设计和验证系统时。</span><span class="sxs-lookup"><span data-stu-id="ee5db-197">Certainly any planned outages such as regularly scheduled maintenance must be taken into consideration when designing and certifying a system.</span></span> <span data-ttu-id="ee5db-198">建议的被认为是计划外的停机和其效果的分析。</span><span class="sxs-lookup"><span data-stu-id="ee5db-198">It is also recommended that an analysis of unplanned outages and their effects be considered.</span></span>  
  
 <span data-ttu-id="ee5db-199">通过标识可能发生的停用类型，按预计风险级别（即，概率乘以严重性）进行排序，并评估具有较高风险的停用情况的持续时间和影响（例如，水闸事件、挂起的消息量、积压等），可以指示发生停用情况时所需的系统性能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-199">Identifying the types of outages that can occur, ranking them by estimated risk level (that is, probability times severity), and estimating the duration and effect (for example, floodgate events, suspended message volume, backlog, etc.) of the higher risk outages will indicate a desired system capability should the outages take place.</span></span> <span data-ttu-id="ee5db-200">任何存储转发、 基于消息的异步系统，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 应设计的将处理"空间"足以应对计划内和计划外停机。</span><span class="sxs-lookup"><span data-stu-id="ee5db-200">Any store-and-forward, messaging-based asynchronous system, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], should be designed will processing "headroom" sufficient to cope with planned and unplanned outages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5db-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee5db-201">See Also</span></span>  
 <span data-ttu-id="ee5db-202">[引擎持久性和持久性](../core/engine-persistence-and-durability.md) </span><span class="sxs-lookup"><span data-stu-id="ee5db-202">[Engine Persistence and Durability](../core/engine-persistence-and-durability.md) </span></span>  
 <span data-ttu-id="ee5db-203">[项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="ee5db-203">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="ee5db-204">[测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="ee5db-204">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="ee5db-205">[测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="ee5db-205">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 <span data-ttu-id="ee5db-206">[缩放您的解决方案](../core/scaling-your-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="ee5db-206">[Scaling Your Solutions](../core/scaling-your-solutions.md) </span></span>  
 <span data-ttu-id="ee5db-207">[识别性能瓶颈](../core/identifying-performance-bottlenecks.md) </span><span class="sxs-lookup"><span data-stu-id="ee5db-207">[Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) </span></span>  
 [<span data-ttu-id="ee5db-208">引擎性能和容量</span><span class="sxs-lookup"><span data-stu-id="ee5db-208">Engine Performance and Capacity</span></span>](../core/engine-performance-and-capacity.md)