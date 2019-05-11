---
title: 维护性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7e63ed-4e28-45b1-ab00-be9f9488a2e6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44beb0700d1c5de5a606708e5a6dbc343db128b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396264"
---
# <a name="maintaining-performance"></a><span data-ttu-id="66620-102">维护性能</span><span class="sxs-lookup"><span data-stu-id="66620-102">Maintaining Performance</span></span>
<span data-ttu-id="66620-103">本部分提供了旨在帮助您解决在日常维护检查过程发现性能问题的信息。</span><span class="sxs-lookup"><span data-stu-id="66620-103">This section provides information that is intended to help you resolve performance issues discovered during your routine maintenance checks.</span></span> <span data-ttu-id="66620-104">此外可以使用的工具和技术此处所述主动，关键问题之前找出潜在问题。</span><span class="sxs-lookup"><span data-stu-id="66620-104">You can also use the tools and techniques described here proactively, to identify potential problems before they become critical issues.</span></span>  

 <span data-ttu-id="66620-105">通常需要作为依据来评估当前的系统性能的标准建立性能基线。</span><span class="sxs-lookup"><span data-stu-id="66620-105">You will generally need to establish a performance baseline as a standard against which to assess current system performance.</span></span>  

 <span data-ttu-id="66620-106">除了此部分中的主题，本文档中的其他主题解决性能问题。</span><span class="sxs-lookup"><span data-stu-id="66620-106">In addition to the topics in this section, other topics in this document address performance issues.</span></span> <span data-ttu-id="66620-107">以下相关各节列出了这些主题。</span><span class="sxs-lookup"><span data-stu-id="66620-107">These topics are listed in Related Sections below.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="66620-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="66620-108">In This Section</span></span>  

-   [<span data-ttu-id="66620-109">维护性能的最佳做法</span><span class="sxs-lookup"><span data-stu-id="66620-109">Best Practices for Maintaining Performance</span></span>](../technical-guides/best-practices-for-maintaining-performance.md)  

-   [<span data-ttu-id="66620-110">配置批处理以优化适配器性能</span><span class="sxs-lookup"><span data-stu-id="66620-110">Configuring Batching to Improve Adapter Performance</span></span>](../technical-guides/configuring-batching-to-improve-adapter-performance.md)  

-   [<span data-ttu-id="66620-111">如何调整高速缓存刷新的间隔配置</span><span class="sxs-lookup"><span data-stu-id="66620-111">How to Adjust the Configuration Cache Refresh Interval</span></span>](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)  

-   [<span data-ttu-id="66620-112">如何禁用跟踪</span><span class="sxs-lookup"><span data-stu-id="66620-112">How to Disable Tracking</span></span>](../technical-guides/how-to-disable-tracking.md)  

-   [<span data-ttu-id="66620-113">故障排除性能 Issues3</span><span class="sxs-lookup"><span data-stu-id="66620-113">Troubleshooting Performance Issues3</span></span>](../technical-guides/troubleshooting-performance-issues3.md)  

## <a name="related-sections"></a><span data-ttu-id="66620-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="66620-114">Related Sections</span></span>  

- <span data-ttu-id="66620-115">详细了解性能问题一般情况下，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南，网址[ http://go.microsoft.com/fwlink/?LinkID=150492 ](http://go.microsoft.com/fwlink/?LinkID=150492)。</span><span class="sxs-lookup"><span data-stu-id="66620-115">For more information about performance issues in general, see [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Performance Optimization Guide at [http://go.microsoft.com/fwlink/?LinkID=150492](http://go.microsoft.com/fwlink/?LinkID=150492).</span></span>  

- <span data-ttu-id="66620-116">有关分析针对基线和阈值的每周性能监视器日志的信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)，"查找并消除瓶颈"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南[ http://go.microsoft.com/fwlink/?LinkId=154675 ](http://go.microsoft.com/fwlink/?LinkId=154675)，和[故障排除性能 Issues3](../technical-guides/troubleshooting-performance-issues3.md)。</span><span class="sxs-lookup"><span data-stu-id="66620-116">For information about analyzing weekly performance monitor logs against baseline and thresholds, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md), "Finding and Eliminating Bottlenecks" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Performance Optimization Guide at [http://go.microsoft.com/fwlink/?LinkId=154675](http://go.microsoft.com/fwlink/?LinkId=154675), and [Troubleshooting Performance Issues3](../technical-guides/troubleshooting-performance-issues3.md).</span></span>  

- <span data-ttu-id="66620-117">确保系统不出现频繁地自动增长的有关信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[定义数据库的自动增长设置](../technical-guides/defining-auto-growth-settings-for-databases.md)，"跟踪数据库大小调整指南"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154677 ](http://go.microsoft.com/fwlink/?LinkId=154677)，并在的"标识数据库层的瓶颈"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154678 ](http://go.microsoft.com/fwlink/?LinkId=154678)。</span><span class="sxs-lookup"><span data-stu-id="66620-117">For information about ensuring that the system is not experiencing frequent auto-growth of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Defining Auto-Growth Settings for Databases](../technical-guides/defining-auto-growth-settings-for-databases.md), "Tracking Database Sizing Guidelines" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677), and "Identifying Bottlenecks in the Database Tier" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678).</span></span>  

- <span data-ttu-id="66620-118">有关维护 SQL Server 信息[执行 SQL Server 维护过程](~/technical-guides/checklist-configuring-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="66620-118">For information about maintaining SQL Server, [Performing SQL Server Maintenance Procedures](~/technical-guides/checklist-configuring-sql-server.md).</span></span>  

- <span data-ttu-id="66620-119">有关在高负载，以检查长时间响应时间和高资源使用率期间运行 SQL Server Profiler 的信息，请参阅"使用 SQL Server Profiler"SQL Server 帮助中在[ http://go.microsoft.com/fwlink/?LinkID=106720 ](http://go.microsoft.com/fwlink/?LinkID=106720)。</span><span class="sxs-lookup"><span data-stu-id="66620-119">For information about running SQL Server Profiler during high load to check for long response times and high resource usage, see "Using SQL Server Profiler" in SQL Server Help at [http://go.microsoft.com/fwlink/?LinkID=106720](http://go.microsoft.com/fwlink/?LinkID=106720).</span></span>  

- <span data-ttu-id="66620-120">有关确保用于所有适配器的消息批处理适用于资源消耗或延迟的信息，请参阅[提高适配器性能配置批处理](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="66620-120">For information about ensuring that message batching for all adapters is appropriate for resource consumption or latency, see [Configuring Batching to Improve Adapter Performance](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span></span>  

- <span data-ttu-id="66620-121">有关增加 BizTalk Server 缓存刷新间隔的信息，请参阅[如何调整配置缓存刷新间隔](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)。</span><span class="sxs-lookup"><span data-stu-id="66620-121">For information about increasing the BizTalk Server cache refresh interval, see [How to Adjust the Configuration Cache Refresh Interval](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md).</span></span>  

- <span data-ttu-id="66620-122">入站和出站主机阻止有关的信息，请参阅"什么是主机限制？"</span><span class="sxs-lookup"><span data-stu-id="66620-122">For information about inbound and outbound host throttling, see "What is Host Throttling?"</span></span> <span data-ttu-id="66620-123">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154694 ](http://go.microsoft.com/fwlink/?LinkId=154694)。</span><span class="sxs-lookup"><span data-stu-id="66620-123">in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=154694](http://go.microsoft.com/fwlink/?LinkId=154694).</span></span> <span data-ttu-id="66620-124">有关触发器、 操作和缓解策略的入站和出站阻止功能的信息，请参阅"限制条件触发器、 操作和缓解策略"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154695 ](http://go.microsoft.com/fwlink/?LinkId=154695)。</span><span class="sxs-lookup"><span data-stu-id="66620-124">For information about triggers, actions, and mitigation strategies for inbound and outbound throttling, see "Throttling condition triggers, actions, and mitigation strategies" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=154695](http://go.microsoft.com/fwlink/?LinkId=154695).</span></span>  

- <span data-ttu-id="66620-125">将直通发送管道而不是默认 XML 发送管道，请参阅"管理发送端口使用 BizTalk 浏览器"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154696 ](http://go.microsoft.com/fwlink/?LinkID=154696)。</span><span class="sxs-lookup"><span data-stu-id="66620-125">To use a PassThrough send pipeline instead of the default XML send pipeline, see "Managing Send Ports Using BizTalk Explorer" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154696](http://go.microsoft.com/fwlink/?LinkID=154696).</span></span>  

- <span data-ttu-id="66620-126">有关调整跟踪数据库大小的信息，请参阅"跟踪数据库大小调整指南"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154677 ](http://go.microsoft.com/fwlink/?LinkId=154677)。</span><span class="sxs-lookup"><span data-stu-id="66620-126">For information about sizing the tracking database, see "Tracking Database Sizing Guidelines" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677).</span></span>  

- <span data-ttu-id="66620-127">有关大小调整 MessageBox 和 BizTalkDTADb、 BAMPrimaryImport 数据库的信息，请参阅"中的数据库层确定瓶颈"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154678 ](http://go.microsoft.com/fwlink/?LinkId=154678)。</span><span class="sxs-lookup"><span data-stu-id="66620-127">For information about sizing the MessageBox, BizTalkDTADb, and BAMPrimaryImport databases, see "Identifying Bottlenecks in the Database Tier" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678).</span></span>  

- <span data-ttu-id="66620-128">有关如何避免争用 MessageBox 数据库中的信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南。</span><span class="sxs-lookup"><span data-stu-id="66620-128">For information about avoiding contention in the MessageBox database, see [How to Avoid Disk Contention](http://go.microsoft.com/fwlink/?LinkId=158809) ([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Performance Optimization Guide.</span></span>
