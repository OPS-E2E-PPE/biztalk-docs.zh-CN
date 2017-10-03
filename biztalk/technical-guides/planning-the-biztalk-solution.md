---
title: "规划 BizTalk 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74b7cbe23a6fc818428478859ea021d4fbf38546
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-the-biztalk-solution"></a><span data-ttu-id="3789e-102">规划 BizTalk 解决方案</span><span class="sxs-lookup"><span data-stu-id="3789e-102">Planning the BizTalk Solution</span></span>
<span data-ttu-id="3789e-103">主要设计目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是尽可能容纳尽可能多的处理方案提供最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="3789e-103">One of the primary design goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="3789e-104">由于此极大的灵活性，面对的 BizTalk 解决方案的开发人员的主要挑战之一是确定如何在中提供的功能的最佳使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为了最好地满足其业务需求。</span><span class="sxs-lookup"><span data-stu-id="3789e-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to best meet their business needs.</span></span> <span data-ttu-id="3789e-105">规划[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以分解到不同的阶段下面概括了这些阶段。</span><span class="sxs-lookup"><span data-stu-id="3789e-105">Planning the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be broken down into distinct phases which are summarized below.</span></span>  
  
## <a name="scoping-the-solution"></a><span data-ttu-id="3789e-106">作用域解决方案</span><span class="sxs-lookup"><span data-stu-id="3789e-106">Scoping the Solution</span></span>  
  
### <a name="performance-considerations"></a><span data-ttu-id="3789e-107">性能注意事项</span><span class="sxs-lookup"><span data-stu-id="3789e-107">Performance Considerations</span></span>  
 <span data-ttu-id="3789e-108">作用域 BizTalk 解决方案时考虑以下方面：</span><span class="sxs-lookup"><span data-stu-id="3789e-108">Consider the following when scoping your BizTalk solution:</span></span>  
  
-   <span data-ttu-id="3789e-109">需要哪些适配器和/或快捷键？</span><span class="sxs-lookup"><span data-stu-id="3789e-109">Which adapters and/or accelerators are required?</span></span>  
  
-   <span data-ttu-id="3789e-110">在解决方案中实现业务流程的要求有哪些？</span><span class="sxs-lookup"><span data-stu-id="3789e-110">What are the requirements for implementing orchestrations in the solution?</span></span>  
  
-   <span data-ttu-id="3789e-111">文档吞吐量要求： 解决方案的最大可持续吞吐量要求是什么？</span><span class="sxs-lookup"><span data-stu-id="3789e-111">Document throughput requirements: What are the maximum sustainable throughput requirements for the solution?</span></span>  
  
-   <span data-ttu-id="3789e-112">延迟要求： 如何响应解决方案需要请求作出响应和请求-响应方案？</span><span class="sxs-lookup"><span data-stu-id="3789e-112">Latency requirements: How responsive does the solution need to be for solicit-response and request-response scenarios?</span></span>  
  
-   <span data-ttu-id="3789e-113">从文档负载高峰期的时间段未程度恢复解决方案？</span><span class="sxs-lookup"><span data-stu-id="3789e-113">How well does the solution recover from periods of peak document load?</span></span>  
  
-   <span data-ttu-id="3789e-114">解决方案的高可用性要求是什么？</span><span class="sxs-lookup"><span data-stu-id="3789e-114">What are the high availability requirements of the solution?</span></span>  
  
-   <span data-ttu-id="3789e-115">文档跟踪要求的解决方案有哪些？</span><span class="sxs-lookup"><span data-stu-id="3789e-115">What are the document tracking requirements of the solution?</span></span>  
  
-   <span data-ttu-id="3789e-116">任何依赖的应用程序，如远程 Web 服务或其他系统的性能特征有哪些？</span><span class="sxs-lookup"><span data-stu-id="3789e-116">What are the performance characteristics of any dependent applications such as a remote Web service or other system?</span></span> <span data-ttu-id="3789e-117">如果依赖的应用程序执行不保留与所需的负载然后将相应地降低总体系统性能。</span><span class="sxs-lookup"><span data-stu-id="3789e-117">If dependent applications do not keep up with the required load then the overall system performance will be degraded accordingly.</span></span>  
  
-   <span data-ttu-id="3789e-118">将 BizTalk 应用程序正在消耗不相关数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]？</span><span class="sxs-lookup"><span data-stu-id="3789e-118">Would the BizTalk application be consuming databases not related to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]?</span></span> <span data-ttu-id="3789e-119">例如，如果 BizTalk 应用程序过多占用 SQL Server 数据库使用 SQL 适配器的表中，表有效地配置？</span><span class="sxs-lookup"><span data-stu-id="3789e-119">For example, if the BizTalk application is consuming tables in a SQL Server database using the SQL adapter, are the tables efficiently configured?</span></span>  
  
### <a name="hardware-considerations"></a><span data-ttu-id="3789e-120">硬件考虑事项</span><span class="sxs-lookup"><span data-stu-id="3789e-120">Hardware Considerations</span></span>  
 <span data-ttu-id="3789e-121">当范围之外解决方案，创建包括以下高级硬件图示：</span><span class="sxs-lookup"><span data-stu-id="3789e-121">When scoping the solution, create a high-level hardware diagram that includes the following:</span></span>  
  
-   <span data-ttu-id="3789e-122">计算机体系结构 （如 x86、 x64 和 IA64）</span><span class="sxs-lookup"><span data-stu-id="3789e-122">Computer architecture (such as x86, x64, and IA64)</span></span>  
  
-   <span data-ttu-id="3789e-123">（如类型、 速度、 数、 核心和使用超线程） 的 CPU 要求</span><span class="sxs-lookup"><span data-stu-id="3789e-123">CPU requirements (such as type, speed, number, cores, and use of hyperthreading)</span></span>  
  
-   <span data-ttu-id="3789e-124">每台计算机的 RAM 要求</span><span class="sxs-lookup"><span data-stu-id="3789e-124">RAM requirements for each computer</span></span>  
  
-   <span data-ttu-id="3789e-125">本地磁盘存储 （类型、 大小、 速度）</span><span class="sxs-lookup"><span data-stu-id="3789e-125">Local disk storage (type, size, speed)</span></span>  
  
-   <span data-ttu-id="3789e-126">SAN (存储要求： 数 LUN;SAN 卡类型）</span><span class="sxs-lookup"><span data-stu-id="3789e-126">SAN (storage requirements: number of LUNS; SAN card type)</span></span>  
  
-   <span data-ttu-id="3789e-127">网卡 (数字在每个计算机中，而不是 1 千兆比特的 100 兆位 (Mbps) (1 Gbps)。)</span><span class="sxs-lookup"><span data-stu-id="3789e-127">Network cards (number in each computer, 100 megabits (Mbps) versus 1 Gigabit (1 Gbps).)</span></span>  
  
-   <span data-ttu-id="3789e-128">如何将防火墙部署解决方案中？</span><span class="sxs-lookup"><span data-stu-id="3789e-128">How will firewalls be deployed in the solution?</span></span>  
  
-   <span data-ttu-id="3789e-129">将使用网络负载平衡的硬件？</span><span class="sxs-lookup"><span data-stu-id="3789e-129">Will Network Load Balancing hardware be used?</span></span>  
  
-   <span data-ttu-id="3789e-130">是特定计算机其可以加入群集？</span><span class="sxs-lookup"><span data-stu-id="3789e-130">Are specific computers to be clustered?</span></span>  
  
-   <span data-ttu-id="3789e-131">将会使用虚拟环境涉及 Microsoft HYPER-V Server 或任何其他虚拟化产品？</span><span class="sxs-lookup"><span data-stu-id="3789e-131">Would you be using a virtual environment involving Microsoft Hyper-V Server or any other virtualization products?</span></span>  
  
## <a name="planning-the-solution"></a><span data-ttu-id="3789e-132">规划解决方案</span><span class="sxs-lookup"><span data-stu-id="3789e-132">Planning the Solution</span></span>  
  
### <a name="solution-milestones-timeline"></a><span data-ttu-id="3789e-133">解决方案里程碑时间线</span><span class="sxs-lookup"><span data-stu-id="3789e-133">Solution Milestones Timeline</span></span>  
 <span data-ttu-id="3789e-134">使用用于完成你的 BizTalk 解决方案的特定方面的里程碑创建计划。</span><span class="sxs-lookup"><span data-stu-id="3789e-134">Create a schedule with milestones for completing specific aspects of your BizTalk solution.</span></span> <span data-ttu-id="3789e-135">设置特定的里程碑将解决方案的可能性会增大及时完成。</span><span class="sxs-lookup"><span data-stu-id="3789e-135">Setting specific milestones will increase the likelihood that the solution will be completed in a timely manner.</span></span>  
  
### <a name="non-microsoft-software-considerations"></a><span data-ttu-id="3789e-136">非 Microsoft 软件注意事项</span><span class="sxs-lookup"><span data-stu-id="3789e-136">Non-Microsoft Software Considerations</span></span>  
 <span data-ttu-id="3789e-137">非 Microsoft 软件将与解决方案一起使用时，请考虑以下方法：</span><span class="sxs-lookup"><span data-stu-id="3789e-137">Consider the following when non-Microsoft software will be used with the solution:</span></span>  
  
-   <span data-ttu-id="3789e-138">确定如何软件或硬件配置要求才能获得。</span><span class="sxs-lookup"><span data-stu-id="3789e-138">Determine how the software or hardware required be obtained.</span></span>  
  
-   <span data-ttu-id="3789e-139">规划容量和调整大小以确保该非 Microsoft 软件不会成为你的解决方案中的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="3789e-139">Plan for capacity and sizing to ensure that non-Microsoft software does not become a bottleneck in your solution.</span></span>  
  
-   <span data-ttu-id="3789e-140">确定用于安装所需的非 Microsoft 软件的操作的计划。</span><span class="sxs-lookup"><span data-stu-id="3789e-140">Determine a plan of action for installing required non-Microsoft software.</span></span>  
  
-   <span data-ttu-id="3789e-141">创建配置和优化所需的非 Microsoft 软件的操作的计划。</span><span class="sxs-lookup"><span data-stu-id="3789e-141">Create a plan of action for configuring and optimizing required non-Microsoft software.</span></span>  
  
## <a name="preparing-for-the-solution"></a><span data-ttu-id="3789e-142">准备解决方案</span><span class="sxs-lookup"><span data-stu-id="3789e-142">Preparing for the Solution</span></span>  
 <span data-ttu-id="3789e-143">在准备阶段中包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="3789e-143">Include the following elements in your preparation phase:</span></span>  
  
### <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="3789e-144">详细的解决方案平台的设计</span><span class="sxs-lookup"><span data-stu-id="3789e-144">Detailed Design of the Solution Platform</span></span>  
 <span data-ttu-id="3789e-145">详细的解决方案设计便于通信，并避免假设，从而提高灵活性和的所有活动的有效性。</span><span class="sxs-lookup"><span data-stu-id="3789e-145">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="3789e-146">你应完全记录以下元素：</span><span class="sxs-lookup"><span data-stu-id="3789e-146">You should fully document the following elements:</span></span>  
  
-   <span data-ttu-id="3789e-147">BizTalk Server 数据库和它们如何分布在计算机。</span><span class="sxs-lookup"><span data-stu-id="3789e-147">BizTalk Server databases and how they will be distributed across computers.</span></span>  
  
-   <span data-ttu-id="3789e-148">BizTalk 主机设计和每个主机和其实例的说明。</span><span class="sxs-lookup"><span data-stu-id="3789e-148">BizTalk Host design and descriptions of each host and their instances.</span></span>  
  
-   <span data-ttu-id="3789e-149">每个业务流程的说明。</span><span class="sxs-lookup"><span data-stu-id="3789e-149">Description of each orchestration.</span></span>  
  
-   <span data-ttu-id="3789e-150">每个管道的说明。</span><span class="sxs-lookup"><span data-stu-id="3789e-150">Description of each pipeline.</span></span>  
  
-   <span data-ttu-id="3789e-151">自定义组件，如.NET 程序集和 COM + 组件的说明。</span><span class="sxs-lookup"><span data-stu-id="3789e-151">Description of custom components such as .NET assemblies and COM+ components.</span></span>  
  
 <span data-ttu-id="3789e-152">**消息流关系图**</span><span class="sxs-lookup"><span data-stu-id="3789e-152">**Message Flow Diagrams**</span></span>  
  
 <span data-ttu-id="3789e-153">创建详细的消息流图，以帮助避免出现任何混淆或 false 的假设，有关什么是应该在处理期间不会发生情况的消息。</span><span class="sxs-lookup"><span data-stu-id="3789e-153">Create detailed message flow diagrams to help avoid any confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span> <span data-ttu-id="3789e-154">创建消息流关系图时，应考虑以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3789e-154">The following details should be considered when creating the message flow diagrams:</span></span>  
  
-   <span data-ttu-id="3789e-155">描述了每种类型的消息从时间之前生成的所有消息都发送和完成所有相关的处理到达的接收位置的生命周期。</span><span class="sxs-lookup"><span data-stu-id="3789e-155">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
-   <span data-ttu-id="3789e-156">描述如何处理更改为错误条件。</span><span class="sxs-lookup"><span data-stu-id="3789e-156">Describe how processing changes for error conditions.</span></span>  
  
-   <span data-ttu-id="3789e-157">包括有关相关、 传递通知和确认的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3789e-157">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
-   <span data-ttu-id="3789e-158">包括有关延迟和吞吐量的性能要求信息。</span><span class="sxs-lookup"><span data-stu-id="3789e-158">Include performance requirement information regarding latency and throughput.</span></span>  
  
 <span data-ttu-id="3789e-159">**非 Microsoft 软件详细信息**</span><span class="sxs-lookup"><span data-stu-id="3789e-159">**Non-Microsoft Software Details**</span></span>  
  
 <span data-ttu-id="3789e-160">使用的所有非 Microsoft 软件应完全记录详细的解决方案设计的一部分。</span><span class="sxs-lookup"><span data-stu-id="3789e-160">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
 <span data-ttu-id="3789e-161">**详细的硬件堆栈**</span><span class="sxs-lookup"><span data-stu-id="3789e-161">**Detailed Hardware Stack**</span></span>  
  
 <span data-ttu-id="3789e-162">在以前创建的高级硬件关系图上构建，下列硬件信息应将完全记录：</span><span class="sxs-lookup"><span data-stu-id="3789e-162">Building on the previously created high level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
-   <span data-ttu-id="3789e-163">Processors</span><span class="sxs-lookup"><span data-stu-id="3789e-163">Processors</span></span>  
  
    -   <span data-ttu-id="3789e-164">类型</span><span class="sxs-lookup"><span data-stu-id="3789e-164">Type</span></span>  
  
    -   <span data-ttu-id="3789e-165">速度</span><span class="sxs-lookup"><span data-stu-id="3789e-165">Speed</span></span>  
  
    -   <span data-ttu-id="3789e-166">内核数</span><span class="sxs-lookup"><span data-stu-id="3789e-166">Number of cores</span></span>  
  
    -   <span data-ttu-id="3789e-167">超线程</span><span class="sxs-lookup"><span data-stu-id="3789e-167">Hyperthreading</span></span>  
  
-   <span data-ttu-id="3789e-168">内存</span><span class="sxs-lookup"><span data-stu-id="3789e-168">Memory</span></span>  
  
    -   <span data-ttu-id="3789e-169">Amount</span><span class="sxs-lookup"><span data-stu-id="3789e-169">Amount</span></span>  
  
    -   <span data-ttu-id="3789e-170">速度</span><span class="sxs-lookup"><span data-stu-id="3789e-170">Speed</span></span>  
  
    -   <span data-ttu-id="3789e-171">奇偶校验</span><span class="sxs-lookup"><span data-stu-id="3789e-171">Parity</span></span>  
  
-   <span data-ttu-id="3789e-172">Network</span><span class="sxs-lookup"><span data-stu-id="3789e-172">Network</span></span>  
  
    -   <span data-ttu-id="3789e-173">网络接口卡 (Nic) 数</span><span class="sxs-lookup"><span data-stu-id="3789e-173">Number of network interface cards (NICs)</span></span>  
  
    -   <span data-ttu-id="3789e-174">网络的速度</span><span class="sxs-lookup"><span data-stu-id="3789e-174">Speed of network</span></span>  
  
-   <span data-ttu-id="3789e-175">SAN</span><span class="sxs-lookup"><span data-stu-id="3789e-175">SAN</span></span>  
  
    -   <span data-ttu-id="3789e-176">每台计算机中的 SAN 卡数</span><span class="sxs-lookup"><span data-stu-id="3789e-176">Number of SAN cards in each computer</span></span>  
  
    -   <span data-ttu-id="3789e-177">每台计算机和每个 LUN 的用途的逻辑单元号 (Lun) 数</span><span class="sxs-lookup"><span data-stu-id="3789e-177">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
    -   <span data-ttu-id="3789e-178">速度的存储区域网络 (SAN) 卡</span><span class="sxs-lookup"><span data-stu-id="3789e-178">Speed of storage area network (SAN) Cards</span></span>  
  
    -   <span data-ttu-id="3789e-179">SAN 卡配置详细信息</span><span class="sxs-lookup"><span data-stu-id="3789e-179">SAN card configuration details</span></span>  
  
    -   <span data-ttu-id="3789e-180">SAN 磁盘分配，格式设置，和分区</span><span class="sxs-lookup"><span data-stu-id="3789e-180">SAN disk allocation, formatting, and partitioning</span></span>  
  
-   <span data-ttu-id="3789e-181">磁盘</span><span class="sxs-lookup"><span data-stu-id="3789e-181">Disk</span></span>  
  
    -   <span data-ttu-id="3789e-182">每台计算机的的本地磁盘详细信息</span><span class="sxs-lookup"><span data-stu-id="3789e-182">Local disk details for each computer</span></span>  
  
    -   <span data-ttu-id="3789e-183">格式设置用于本地磁盘</span><span class="sxs-lookup"><span data-stu-id="3789e-183">Formatting used for local disks</span></span>  
  
    -   <span data-ttu-id="3789e-184">分区本地磁盘的详细的信息</span><span class="sxs-lookup"><span data-stu-id="3789e-184">Partitioning details for local disks</span></span>  
  
-   <span data-ttu-id="3789e-185">Cache</span><span class="sxs-lookup"><span data-stu-id="3789e-185">Cache</span></span>  
  
    -   <span data-ttu-id="3789e-186">L2 缓存量</span><span class="sxs-lookup"><span data-stu-id="3789e-186">L2 Cache amount</span></span>  
  
    -   <span data-ttu-id="3789e-187">L3 缓存量</span><span class="sxs-lookup"><span data-stu-id="3789e-187">L3 Cache amount</span></span>  
  
 <span data-ttu-id="3789e-188">**详细的软件堆栈**</span><span class="sxs-lookup"><span data-stu-id="3789e-188">**Detailed Software Stack**</span></span>  
  
 <span data-ttu-id="3789e-189">应记录以下的软件信息：</span><span class="sxs-lookup"><span data-stu-id="3789e-189">The following software information should be documented:</span></span>  
  
-   <span data-ttu-id="3789e-190">特定操作系统版本、 版本以及体系结构</span><span class="sxs-lookup"><span data-stu-id="3789e-190">Specific operating system versions, editions, and architecture</span></span>  
  
-   <span data-ttu-id="3789e-191">特定的操作系统功能</span><span class="sxs-lookup"><span data-stu-id="3789e-191">Specific operating system features</span></span>  
  
-   <span data-ttu-id="3789e-192">每台计算机上安装的特定软件</span><span class="sxs-lookup"><span data-stu-id="3789e-192">Specific software installed on each computer</span></span>  
  
-   <span data-ttu-id="3789e-193">特定驱动程序</span><span class="sxs-lookup"><span data-stu-id="3789e-193">Specific drivers</span></span>  
  
-   <span data-ttu-id="3789e-194">Service Pack 和其他更新</span><span class="sxs-lookup"><span data-stu-id="3789e-194">Service Packs and other updates</span></span>  
  
-   <span data-ttu-id="3789e-195">如果它们会不同于默认值所使用的所有软件和操作系统功能的配置值</span><span class="sxs-lookup"><span data-stu-id="3789e-195">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="building-out-the-environment-for-the-solution"></a><span data-ttu-id="3789e-196">构建解决方案的环境</span><span class="sxs-lookup"><span data-stu-id="3789e-196">Building Out the Environment for the Solution</span></span>  
 <span data-ttu-id="3789e-197">有关安装详细说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和下载的 BizTalk Server 安装指南中找不到必需的依赖关系软件[BizTalk Server 2010 文档](http://go.microsoft.com/fwlink/?LinkId=183138)(http://go.microsoft.com/fwlink/？LinkId = 183138)。</span><span class="sxs-lookup"><span data-stu-id="3789e-197">Detailed instructions for installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the required dependency software can be found in the BizTalk Server Installation Guides available for download at [BizTalk Server 2010 Documentation](http://go.microsoft.com/fwlink/?LinkId=183138) (http://go.microsoft.com/fwlink/?LinkId=183138).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3789e-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3789e-198">See Also</span></span>  
 [<span data-ttu-id="3789e-199">规划 BizTalk 服务器层</span><span class="sxs-lookup"><span data-stu-id="3789e-199">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)