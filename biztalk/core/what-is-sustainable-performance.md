---
title: 什么是可维持性能？ | Microsoft Docs
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a15c0d8d58e263d6c78b8b7f899a00296f70bad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250205"
---
# <a name="what-is-sustainable-performance"></a><span data-ttu-id="c1715-103">什么是可维持性能？</span><span class="sxs-lookup"><span data-stu-id="c1715-103">What Is Sustainable Performance?</span></span>
<span data-ttu-id="c1715-104">在规划和估计系统可持续发展，从长远来说会想到可持续发展至关重要。</span><span class="sxs-lookup"><span data-stu-id="c1715-104">When planning for and estimating system sustainability, it is critical to think in terms of sustainability over the long term.</span></span> <span data-ttu-id="c1715-105">主要考虑因素是：</span><span class="sxs-lookup"><span data-stu-id="c1715-105">The primary considerations are:</span></span>  
  
- <span data-ttu-id="c1715-106">**负载状况和性能目标**:对于负载状况和性能目标时，不能具有过多的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1715-106">**Load Profiles and Performance Goals**: You can't have too much detail when it comes to load profiles and performance goals.</span></span> <span data-ttu-id="c1715-107">能够处理这些负载从长远来看，将基于测试和准备情况认证。</span><span class="sxs-lookup"><span data-stu-id="c1715-107">Testing and readiness certification will be based on being able to handle these loads long term.</span></span>  
  
- <span data-ttu-id="c1715-108">**其他活动和争用系统资源的进程**:它不是几乎消息负载。</span><span class="sxs-lookup"><span data-stu-id="c1715-108">**Other Activities and Processes that Compete for Server Resources**: It isn’t just about the message load.</span></span> <span data-ttu-id="c1715-109">有其他进程，如数据库维护和 MessageBox 查询的性能影响的服务器上发生的活动。</span><span class="sxs-lookup"><span data-stu-id="c1715-109">There are other processes and activities taking place on the servers that affect performance such as database maintenance and MessageBox queries.</span></span>  
  
- <span data-ttu-id="c1715-110">**计划内和计划外的系统服务中断和停机时间**:水闸事件和消息积压工作可以更改的有效负载配置文件。</span><span class="sxs-lookup"><span data-stu-id="c1715-110">**Planned and Unplanned System Outages and Downtime**: Floodgate events and message backlog can change the effective load profile.</span></span>  
  
  <span data-ttu-id="c1715-111">时考虑构建可承受的系统并执行测试以验证它们，请务必考虑以下因素帐户并为它们的计划。</span><span class="sxs-lookup"><span data-stu-id="c1715-111">When thinking about building sustainable systems and the tests to certify them, be sure to take these factors into account and plan for them.</span></span>  
  
## <a name="is-your-performance-sustainable"></a><span data-ttu-id="c1715-112">是可承受性能？</span><span class="sxs-lookup"><span data-stu-id="c1715-112">Is Your Performance Sustainable?</span></span>  
 <span data-ttu-id="c1715-113">在讨论的性能时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，我们定义最大可承受性能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c1715-113">When discussing performance for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], we define maximum sustainable performance as follows:</span></span>  
  
- <span data-ttu-id="c1715-114">最高的系统可以无限期地处理在生产环境中的消息通信负载。</span><span class="sxs-lookup"><span data-stu-id="c1715-114">The highest load of message traffic that a system can handle indefinitely in a production environment.</span></span>  
  
  <span data-ttu-id="c1715-115">这种方法看似简单，有许多评估-一组特定的硬件上运行的解决方案将能够支持解决方案投入生产后遇到一天中的而且每天在加载时必须考虑的因素。</span><span class="sxs-lookup"><span data-stu-id="c1715-115">While this seems simple, there are many factors that you must consider when evaluating whether or not a solution - running on a particular set of hardware - will be able to support the loads experienced day in and day out after you put the solution into production.</span></span>  
  
  <span data-ttu-id="c1715-116">你的解决方案投入生产之前，请考虑以下因素以评估是否在该解决方案可无限制处理最高消息通信负载：</span><span class="sxs-lookup"><span data-stu-id="c1715-116">Before you put your solution into production, consider the following factors to evaluate whether the solution can handle the highest load of message traffic indefinitely:</span></span>  
  
- <span data-ttu-id="c1715-117">所需的性能目标和吞吐量/延迟状况。</span><span class="sxs-lookup"><span data-stu-id="c1715-117">Desired Performance Goals and Throughput/Latency profiles.</span></span>  
  
- <span data-ttu-id="c1715-118">如在同一硬件上运行的其他进程：</span><span class="sxs-lookup"><span data-stu-id="c1715-118">Other Processes Running on the Same Hardware such as:</span></span>  
  
  -   <span data-ttu-id="c1715-119">正常的监视和故障排除</span><span class="sxs-lookup"><span data-stu-id="c1715-119">Normal Monitoring and Troubleshooting</span></span>  
  
  -   <span data-ttu-id="c1715-120">操作数据库维护，例如日志传送、 备份、 清除、 索引维护和更新统计信息更新。</span><span class="sxs-lookup"><span data-stu-id="c1715-120">Operational database maintenance such as log shipping, backup, purging, index maintenance, and statistics updates.</span></span>  
  
  -   <span data-ttu-id="c1715-121">其他应用程序</span><span class="sxs-lookup"><span data-stu-id="c1715-121">Other Applications</span></span>  
  
- <span data-ttu-id="c1715-122">计划内和计划外的系统停用，例如：</span><span class="sxs-lookup"><span data-stu-id="c1715-122">Planned and Unplanned System Outages such as:</span></span>  
  
  -   <span data-ttu-id="c1715-123">合作伙伴站点中断，阻止发送或接收消息</span><span class="sxs-lookup"><span data-stu-id="c1715-123">Partner sites down which blocks sending or receiving messages</span></span>  
  
  -   <span data-ttu-id="c1715-124">常规系统维护停机时间</span><span class="sxs-lookup"><span data-stu-id="c1715-124">Regular system maintenance down time</span></span>  
  
## <a name="know-your-performance-goals"></a><span data-ttu-id="c1715-125">知道您的性能目标</span><span class="sxs-lookup"><span data-stu-id="c1715-125">Know Your Performance Goals</span></span>  
 <span data-ttu-id="c1715-126">您可以评估你的解决方案的可维持性之前，必须具有预期的生产负载的详细的知识。</span><span class="sxs-lookup"><span data-stu-id="c1715-126">Before you can evaluate your solution for sustainability, you must have a detailed understanding of the expected production loads.</span></span> <span data-ttu-id="c1715-127">不明确的目标的情况下无法评估准备情况。</span><span class="sxs-lookup"><span data-stu-id="c1715-127">Without a well understood goal, you can't evaluate readiness.</span></span> <span data-ttu-id="c1715-128">一组格式正确的性能目标非常重要，因为它能使您的策略以系统测试和认证。</span><span class="sxs-lookup"><span data-stu-id="c1715-128">A well formed set of performance goals is critical as it will drive your strategies around system testing and certification.</span></span> <span data-ttu-id="c1715-129">性能目标应包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="c1715-129">Your performance goals should have the following elements:</span></span>  
  
-   <span data-ttu-id="c1715-130">将性能定义的函数的时间为一条曲线。</span><span class="sxs-lookup"><span data-stu-id="c1715-130">A curve that defines performance as a function of time.</span></span> <span data-ttu-id="c1715-131">这些函数的范围可以从极其简单到非常复杂。</span><span class="sxs-lookup"><span data-stu-id="c1715-131">These functions can range from extremely simple to very complex.</span></span>  
  
-   <span data-ttu-id="c1715-132">性能要求，与性能函数相关联。</span><span class="sxs-lookup"><span data-stu-id="c1715-132">A performance requirement associated with the performance function.</span></span>  
  
-   <span data-ttu-id="c1715-133">文件大小和类型的分布。</span><span class="sxs-lookup"><span data-stu-id="c1715-133">A distribution of file sizes and types.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="c1715-134">示例 1</span><span class="sxs-lookup"><span data-stu-id="c1715-134">Example 1</span></span>  
  
-   <span data-ttu-id="c1715-135">每一天，消息累积 0 的消息数/秒在上午 8:00 到 80 每秒在中午，然后晚上 9:00，大致钟形曲线的形式返回到 0 的消息数/秒。</span><span class="sxs-lookup"><span data-stu-id="c1715-135">Each day, messages build up from 0 msgs/sec at 8:00AM to 80 msgs/sec at noon and then back down to 0 msgs/sec at 9:00PM, roughly in the form of a bell curve.</span></span>  
  
-   <span data-ttu-id="c1715-136">系统具有每个消息没有具体的延迟要求，但它必须能够处理此负载，以及所有前一天的消息负载 （例如，24 小时系统中断时） 而不获取。</span><span class="sxs-lookup"><span data-stu-id="c1715-136">The system has no specific latency requirement for each message, but it must be able to process this load, plus all of the previous day’s message load (for example, in the event of a 24 hour system outage) without getting behind.</span></span>  
  
-   <span data-ttu-id="c1715-137">有三种文档类型：销售篮、 延期交货和库存请求。</span><span class="sxs-lookup"><span data-stu-id="c1715-137">There are three document types: Sales Basket, Back Order, and Stock Request.</span></span> <span data-ttu-id="c1715-138">销售篮文档范围之间 2 到 10 个千字节为单位的大小，构成了在任何给定时间消息数的 75%。</span><span class="sxs-lookup"><span data-stu-id="c1715-138">Sales Basket documents range in size between 2 and 10 kilobytes and make up 75% of the message counts at any given time.</span></span> <span data-ttu-id="c1715-139">后的订单和库存请求文档的大小接近 1 千字节始终是和构成了剩余的 10%和 15%的消息计数在任何给定时间分别。</span><span class="sxs-lookup"><span data-stu-id="c1715-139">Back Order and Stock Request documents are always close to 1 Kilobyte in size and make up the remaining, 10% and 15% of the message count at any given time, respectively.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="c1715-140">示例 2</span><span class="sxs-lookup"><span data-stu-id="c1715-140">Example 2</span></span>  
  
-   <span data-ttu-id="c1715-141">在每天午夜，一批 500,000 条消息到达时进行处理。</span><span class="sxs-lookup"><span data-stu-id="c1715-141">Every night at midnight, a batch of 500,000 messages arrive for processing.</span></span>  
  
-   <span data-ttu-id="c1715-142">必须在 8 小时内完成处理批中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c1715-142">All messages in the batch must be processed to completion in 8 hours.</span></span>  
  
-   <span data-ttu-id="c1715-143">所有消息的相同类型和 10 到 50 个千字节为单位，非独占之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="c1715-143">All messages are of the same type and are evenly distributed between 10 and 50 Kilobytes, inclusive.</span></span> <span data-ttu-id="c1715-144">此外，批处理始终包含 10 个目录类型消息的 10 兆字节每个必须再细分为单独的目录条目进行处理。</span><span class="sxs-lookup"><span data-stu-id="c1715-144">In addition, the batch always contains 10 catalog type messages that are 10 megabytes each and must be subdivided into individual catalog entries for processing.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="c1715-145">示例 3</span><span class="sxs-lookup"><span data-stu-id="c1715-145">Example 3</span></span>  
  
-   <span data-ttu-id="c1715-146">上午 8:00，每天早上 4000 客户服务代表登录的交互式系统并执行，一般情况下，每个代表每分钟到下午 5:00，每周 7 天的结束时间的 4 个查询。</span><span class="sxs-lookup"><span data-stu-id="c1715-146">Every morning at 8:00AM, 4000 customer service representatives log on to the interactive system and perform, on average, 4 inquiries per representative per minute until closing time at 5:00PM, 7 days per week.</span></span>  
  
-   <span data-ttu-id="c1715-147">所有查询必须在 2 秒内都返回的结果。</span><span class="sxs-lookup"><span data-stu-id="c1715-147">All inquiries must return results in less than 2 seconds.</span></span>  
  
-   <span data-ttu-id="c1715-148">所有查询具有相同的类型和大小，非独占 500 到 1000年个字节之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="c1715-148">All inquiries are the same type and are evenly distributed between 500 and 1000 bytes in size, inclusive.</span></span>  
  
#### <a name="a-performance-requirement-associated-with-the-performance-function"></a><span data-ttu-id="c1715-149">与性能函数相关联的性能要求</span><span class="sxs-lookup"><span data-stu-id="c1715-149">A performance requirement associated with the performance function</span></span>  
 <span data-ttu-id="c1715-150">继续上面的示例：</span><span class="sxs-lookup"><span data-stu-id="c1715-150">Continuing with the above examples:</span></span>  
  
-   <span data-ttu-id="c1715-151">**示例 1 （续）**:系统具有每个消息没有具体的延迟要求，但它必须能够处理此负载，以及所有前一天的消息负载 （如 24 小时系统中断时） 而不获取。</span><span class="sxs-lookup"><span data-stu-id="c1715-151">**Example 1 (continued)**:  The system has no specific latency requirement for each message, but it must be able to process this load, plus all of the previous day’s message load (for example,, in the event of a 24 hour system outage) without getting behind.</span></span>  
  
-   <span data-ttu-id="c1715-152">**示例 2 （续）**:必须在 8 小时内完成处理批中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c1715-152">**Example 2 (continued)**:  All messages in the batch must be processed to completion in 8 hours.</span></span>  
  
-   <span data-ttu-id="c1715-153">**示例 3 （续）**:所有查询必须在 2 秒内都返回的结果。</span><span class="sxs-lookup"><span data-stu-id="c1715-153">**Example 3 (continued)**:  All inquiries must return results in less than 2 seconds.</span></span>  
  
#### <a name="a-distribution-of-file-sizes-and-types"></a><span data-ttu-id="c1715-154">文件大小和类型的分发</span><span class="sxs-lookup"><span data-stu-id="c1715-154">A distribution of file sizes and types</span></span>  
  
-   <span data-ttu-id="c1715-155">**示例 1 （续）**:有三种文档类型：销售篮、 延期交货和库存请求。</span><span class="sxs-lookup"><span data-stu-id="c1715-155">**Example 1 (continued)**: There are three document types: Sales Basket, Back Order, and Stock Request.</span></span> <span data-ttu-id="c1715-156">销售篮文档范围之间 2 到 10 个千字节为单位的大小，构成了在任何给定时间消息数的 75%。</span><span class="sxs-lookup"><span data-stu-id="c1715-156">Sales Basket documents range in size between 2 and 10 kilobytes and make up 75% of the message counts at any given time.</span></span> <span data-ttu-id="c1715-157">后的订单和库存请求文档的大小接近 1 千字节始终是和构成了剩余的 10%和 15%的消息计数在任何给定时间分别。</span><span class="sxs-lookup"><span data-stu-id="c1715-157">Back Order and Stock Request documents are always close to 1 Kilobyte in size and make up the remaining, 10% and 15% of the message count at any given time, respectively.</span></span>  
  
-   <span data-ttu-id="c1715-158">**示例 2 （续）**:所有消息的相同类型和 10 到 50 个千字节为单位，非独占之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="c1715-158">**Example 2 (continued)**: All messages are of the same type and are evenly distributed between 10 and 50 Kilobytes, inclusive.</span></span> <span data-ttu-id="c1715-159">此外，批处理始终包含 10 个目录类型消息的 10 兆字节每个必须再细分为单独的目录条目进行处理。</span><span class="sxs-lookup"><span data-stu-id="c1715-159">In addition, the batch always contains 10 catalog type messages that are 10 megabytes each and must be subdivided into individual catalog entries for processing.</span></span>  
  
-   <span data-ttu-id="c1715-160">**示例 3 （续）**:所有查询具有相同的类型和大小，非独占 500 到 1000年个字节之间均匀分布。</span><span class="sxs-lookup"><span data-stu-id="c1715-160">**Example 3 (continued)**: All inquiries are the same type and are evenly distributed between 500 and 1000 bytes in size, inclusive.</span></span>  
  
## <a name="accounting-for-other-processes"></a><span data-ttu-id="c1715-161">其他进程记帐</span><span class="sxs-lookup"><span data-stu-id="c1715-161">Accounting for Other Processes</span></span>  
 <span data-ttu-id="c1715-162">除了直接通过 BizTalk 引擎传递了负载配置文件，始终有争用资源的相同硬件上的其他进程中。</span><span class="sxs-lookup"><span data-stu-id="c1715-162">In addition to the load profiles that pass directly through the BizTalk engine, there are always other processes that compete for resources on the same hardware.</span></span>  <span data-ttu-id="c1715-163">这些其他进程将减少系统的整体可维持性能功能。</span><span class="sxs-lookup"><span data-stu-id="c1715-163">These other processes will reduce the overall sustainable performance capabilities of the system.</span></span> <span data-ttu-id="c1715-164">数据库维护可能是进程的这种类型的最常见示例。</span><span class="sxs-lookup"><span data-stu-id="c1715-164">Database maintenance is probably the most common example of this type of process.</span></span>  
  
 <span data-ttu-id="c1715-165">每个数据库，大或小，需要定期操作维护，例如日志传送、 备份、 存档和清除。</span><span class="sxs-lookup"><span data-stu-id="c1715-165">Every database, large or small, requires periodic operational maintenance such as log shipping, backup, archive, and purging.</span></span> <span data-ttu-id="c1715-166">监视和故障排除操作必须考虑到帐户时定义和认证的新增可承受的其他示例。</span><span class="sxs-lookup"><span data-stu-id="c1715-166">Monitoring and troubleshooting are other examples of operations that you must take into account when defining and certifying what is sustainable.</span></span> <span data-ttu-id="c1715-167">例如，查询 （例如，通过管理控制台上组中心页） MessageBox，以查看过去 24 小时内已挂起消息数给定类型的要求可能否则使用的 SQL 服务器中的资源处理消息。</span><span class="sxs-lookup"><span data-stu-id="c1715-167">For example, querying the MessageBox (for example, via the administration console Group Hub page) to see how many messages of a given type have been suspended in the last 24 hours requires resources from SQL Server that could otherwise have been used to process messages.</span></span>  
  
 <span data-ttu-id="c1715-168">下面是一系列活动，通常具有很大影响上中的整体可维持性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c1715-168">Following is a list of activities that will typically have the most effect on overall sustainability in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
- <span data-ttu-id="c1715-169">**日志传送和备份**。</span><span class="sxs-lookup"><span data-stu-id="c1715-169">**Log Shipping and Backup**.</span></span> <span data-ttu-id="c1715-170">为大多数灾难恢复的一部分计划涉及 SQL Server，您必须执行日志传送和备份定期的所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组数据库。</span><span class="sxs-lookup"><span data-stu-id="c1715-170">As part of most disaster recovery plans involving SQL Server, you must perform log shipping and backup periodically for all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group databases.</span></span> <span data-ttu-id="c1715-171">有关详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="c1715-171">For more information, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span> <span data-ttu-id="c1715-172">另请参阅[日志传送](../core/log-shipping.md)。</span><span class="sxs-lookup"><span data-stu-id="c1715-172">Also see [Log Shipping](../core/log-shipping.md).</span></span>  
  
- <span data-ttu-id="c1715-173">**存档和清除跟踪数据**。</span><span class="sxs-lookup"><span data-stu-id="c1715-173">**Archiving and Purging Tracking Data**.</span></span> <span data-ttu-id="c1715-174">除了整体日志传送和备份计划，BizTalk 跟踪 (BizTalkDTADb) 数据库具有自己的存档和清除策略;有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。</span><span class="sxs-lookup"><span data-stu-id="c1715-174">In addition to the overall log shipping and backup plan, the BizTalk Tracking (BizTalkDTADb) database has its own archive and purge regimes; for more information, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span> <span data-ttu-id="c1715-175">速度的数据可以存档和清除 BizTalk 跟踪数据库中是因为尤其重要，清除 BizTalk 跟踪数据库的通常是瓶颈跟踪时正在使用中。</span><span class="sxs-lookup"><span data-stu-id="c1715-175">The speed at which data can be archived and purged from the BizTalk Tracking database is especially important since archiving and purging of the BizTalk Tracking database is typically a bottleneck when tracking is in use.</span></span>  
  
- <span data-ttu-id="c1715-176">**系统查询**。</span><span class="sxs-lookup"><span data-stu-id="c1715-176">**System Queries**.</span></span> <span data-ttu-id="c1715-177">使用 Api 或 BizTalk Server 管理控制台 UI 对系统运行各种类型的查询将影响可维持性能。</span><span class="sxs-lookup"><span data-stu-id="c1715-177">Using APIs or the BizTalk Server Administration Console UI to run various types of queries against the system will affect sustainable performance.</span></span>  
  
- <span data-ttu-id="c1715-178">**MessageBox 维护**。</span><span class="sxs-lookup"><span data-stu-id="c1715-178">**MessageBox Maintenance**.</span></span> <span data-ttu-id="c1715-179">有多种一部分的核心功能的 SQL 作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行维护的清理工作消息和实例已完成处理的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="c1715-179">There are a number of SQL jobs that are part of the core functionality of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that maintain the MessageBox database by cleaning up messages and instances that have finished processing.</span></span> <span data-ttu-id="c1715-180">作为核心引擎的一部分，这些作业可完成的速度是衡量可维持性的关键因素。</span><span class="sxs-lookup"><span data-stu-id="c1715-180">As part of the core engine, the speed at which these jobs can complete is a key factor in gauging sustainability.</span></span> <span data-ttu-id="c1715-181">有关这些作业及其角色的详细信息，请参阅[维护 BizTalk Server1](../core/maintaining-biztalk-server1.md)。</span><span class="sxs-lookup"><span data-stu-id="c1715-181">For more information about these jobs and their role, see [Maintaining BizTalk Server1](../core/maintaining-biztalk-server1.md).</span></span>  
  
- <span data-ttu-id="c1715-182">**解决方案部署活动**。</span><span class="sxs-lookup"><span data-stu-id="c1715-182">**Solution Deployment Activities**.</span></span> <span data-ttu-id="c1715-183">在部署时，绑定和启动新的应用程序或新版本的现有应用程序，额外的负载放置 BizTalk 例如对 MessageBox 数据库的新订阅的创建。</span><span class="sxs-lookup"><span data-stu-id="c1715-183">When deploying, binding, and starting new applications or new versions of existing applications, additional load is placed on BizTalk such as the creation of new subscriptions on the MessageBox database(s).</span></span> <span data-ttu-id="c1715-184">应用程序的部署后，正在处理的消息将争用资源，从而会影响现有应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="c1715-184">After applications are deployed, the messages being processed will compete for resources and thereby affect the performance of the existing applications.</span></span>  
  
  <span data-ttu-id="c1715-185">对于每个方面，需要要求：什么是建议这些活动的影响降至最低？</span><span class="sxs-lookup"><span data-stu-id="c1715-185">For each of these areas, you need to ask: What is your recommendation to minimize the impact of these activities?</span></span> <span data-ttu-id="c1715-186">例如，它们应打算在凌晨 3 点运行它们？</span><span class="sxs-lookup"><span data-stu-id="c1715-186">For example, should they plan to run them at 3am?</span></span>  
  
## <a name="considering-planned-and-unplanned-outages"></a><span data-ttu-id="c1715-187">考虑计划内和计划外中断</span><span class="sxs-lookup"><span data-stu-id="c1715-187">Considering Planned and Unplanned Outages</span></span>  
 <span data-ttu-id="c1715-188">对系统性能的服务中断的影响将遇到服务中断，但最常用的后果是系统而异：</span><span class="sxs-lookup"><span data-stu-id="c1715-188">The effects that outages have on the system performance will vary depending on the system experiencing the outage, however the most common consequences are:</span></span>  
  
- <span data-ttu-id="c1715-189">**水闸事件**。</span><span class="sxs-lookup"><span data-stu-id="c1715-189">**Floodgate Events**.</span></span> <span data-ttu-id="c1715-190">当系统中断的某些时间的时间，消息可以构建，然后到达，一次性处理后的系统是再次正常工作。</span><span class="sxs-lookup"><span data-stu-id="c1715-190">When systems are down for some length of time, messages can build up and then arrive all at once for processing once the systems are functional again.</span></span>  <span data-ttu-id="c1715-191">例如，如果在 BizTalk 上运行的应用程序接收消息通过 MSMQ，并且段时间，该应用程序已关闭，消息累积等待选取队列中。</span><span class="sxs-lookup"><span data-stu-id="c1715-191">For example, if an application running on BizTalk receives messages via MSMQ, and that application is down for some time, messages build up in the queues waiting to be picked up.</span></span> <span data-ttu-id="c1715-192">当再次启动该应用程序时，它是像大量消息到达"一次性全部。"</span><span class="sxs-lookup"><span data-stu-id="c1715-192">When the application is started up again, it is as if a large number of messages arrived "all at once."</span></span>  
  
- <span data-ttu-id="c1715-193">**消息积压工作**。</span><span class="sxs-lookup"><span data-stu-id="c1715-193">**Message Backlog**.</span></span> <span data-ttu-id="c1715-194">当消息发送到的系统已关闭，没有通常是一个重试周期所采用的使用的其他资源。</span><span class="sxs-lookup"><span data-stu-id="c1715-194">When systems to which messages are sent are down, there is typically a retry cycle that is employed that uses additional resources.</span></span> <span data-ttu-id="c1715-195">后重试周期用尽，则通常会挂起消息。</span><span class="sxs-lookup"><span data-stu-id="c1715-195">After the retry cycle is exhausted, then messages are typically suspended.</span></span> <span data-ttu-id="c1715-196">然后关闭的系统返回在一行，现在可以是大量的消息类型的水闸事件发生恢复和/或已成功发送。</span><span class="sxs-lookup"><span data-stu-id="c1715-196">Then the downed systems come back on line, a type of floodgate event occurs where large numbers of messages can now be resumed and/or successfully sent.</span></span>  
  
  <span data-ttu-id="c1715-197">当然，任何计划的中断，如定期计划维护必须纳入考虑范围设计和认证系统时。</span><span class="sxs-lookup"><span data-stu-id="c1715-197">Certainly any planned outages such as regularly scheduled maintenance must be taken into consideration when designing and certifying a system.</span></span> <span data-ttu-id="c1715-198">此外建议考虑计划外的停机和它们的影响的分析。</span><span class="sxs-lookup"><span data-stu-id="c1715-198">It is also recommended that an analysis of unplanned outages and their effects be considered.</span></span>  
  
  <span data-ttu-id="c1715-199">标识类型的服务中断可能发生的最弱的顺序按预计风险级别 （即，概率乘以严重性），并估计持续时间和更高风险服务中断的影响 （例如，水闸事件、 挂起的消息量、 积压等）将指示所需的系统功能应发生在服务中断的位置。</span><span class="sxs-lookup"><span data-stu-id="c1715-199">Identifying the types of outages that can occur, ranking them by estimated risk level (that is, probability times severity), and estimating the duration and effect (for example, floodgate events, suspended message volume, backlog, etc.) of the higher risk outages will indicate a desired system capability should the outages take place.</span></span> <span data-ttu-id="c1715-200">任何存储转发、 基于消息的异步系统，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，应设计的将处理"余量"足以应对计划内和计划外停机。</span><span class="sxs-lookup"><span data-stu-id="c1715-200">Any store-and-forward, messaging-based asynchronous system, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], should be designed will processing "headroom" sufficient to cope with planned and unplanned outages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1715-201">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1715-201">See Also</span></span>  
 <span data-ttu-id="c1715-202">[引擎持久性和持续性](../core/engine-persistence-and-durability.md) </span><span class="sxs-lookup"><span data-stu-id="c1715-202">[Engine Persistence and Durability](../core/engine-persistence-and-durability.md) </span></span>  
 <span data-ttu-id="c1715-203">[分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="c1715-203">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="c1715-204">[测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="c1715-204">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="c1715-205">[测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="c1715-205">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 <span data-ttu-id="c1715-206">[缩放你的解决方案](../core/scaling-your-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="c1715-206">[Scaling Your Solutions](../core/scaling-your-solutions.md) </span></span>  
 <span data-ttu-id="c1715-207">[确定性能瓶颈](../core/identifying-performance-bottlenecks.md) </span><span class="sxs-lookup"><span data-stu-id="c1715-207">[Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) </span></span>  
 [<span data-ttu-id="c1715-208">引擎性能和容量</span><span class="sxs-lookup"><span data-stu-id="c1715-208">Engine Performance and Capacity</span></span>](../core/engine-performance-and-capacity.md)