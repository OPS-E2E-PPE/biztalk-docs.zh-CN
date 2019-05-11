---
title: 规划 BizTalk 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8579726d4e97d7bce91dce2a27687528e6064794
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397039"
---
# <a name="plan-for-your-biztalk-solution"></a><span data-ttu-id="7d50a-102">规划您的 BizTalk 解决方案</span><span class="sxs-lookup"><span data-stu-id="7d50a-102">Plan for your BizTalk Solution</span></span>
<span data-ttu-id="7d50a-103">主要设计目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是为了适应尽可能多的处理方案提供最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="7d50a-103">One of the primary design goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="7d50a-104">由于此极大的灵活性，BizTalk 解决方案的开发人员所面临的主要挑战之一是确定如何在中提供的功能的最佳使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以最好地满足其业务需要。</span><span class="sxs-lookup"><span data-stu-id="7d50a-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to best meet their business needs.</span></span> <span data-ttu-id="7d50a-105">规划[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以分解为不同的阶段下面进行了汇总。</span><span class="sxs-lookup"><span data-stu-id="7d50a-105">Planning the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be broken down into distinct phases which are summarized below.</span></span>  
  
## <a name="scoping-the-solution"></a><span data-ttu-id="7d50a-106">范围解决方案</span><span class="sxs-lookup"><span data-stu-id="7d50a-106">Scoping the Solution</span></span>  
  
### <a name="performance-considerations"></a><span data-ttu-id="7d50a-107">性能注意事项</span><span class="sxs-lookup"><span data-stu-id="7d50a-107">Performance Considerations</span></span>  
 <span data-ttu-id="7d50a-108">范围在 BizTalk 解决方案时，请考虑以下：</span><span class="sxs-lookup"><span data-stu-id="7d50a-108">Consider the following when scoping your BizTalk solution:</span></span>  
  
- <span data-ttu-id="7d50a-109">需要哪些适配器和/或加速器？</span><span class="sxs-lookup"><span data-stu-id="7d50a-109">Which adapters and/or accelerators are required?</span></span>  
  
- <span data-ttu-id="7d50a-110">在解决方案中实现业务流程要求是什么？</span><span class="sxs-lookup"><span data-stu-id="7d50a-110">What are the requirements for implementing orchestrations in the solution?</span></span>  
  
- <span data-ttu-id="7d50a-111">文档的吞吐量要求：该解决方案的最大可承受吞吐量要求有哪些？</span><span class="sxs-lookup"><span data-stu-id="7d50a-111">Document throughput requirements: What are the maximum sustainable throughput requirements for the solution?</span></span>  
  
- <span data-ttu-id="7d50a-112">延迟要求：响应能力如何解决方案需要求-响应和请求-响应方案？</span><span class="sxs-lookup"><span data-stu-id="7d50a-112">Latency requirements: How responsive does the solution need to be for solicit-response and request-response scenarios?</span></span>  
  
- <span data-ttu-id="7d50a-113">如何从文档负载高峰期期间恢复解决方案？</span><span class="sxs-lookup"><span data-stu-id="7d50a-113">How well does the solution recover from periods of peak document load?</span></span>  
  
- <span data-ttu-id="7d50a-114">该解决方案的高可用性要求是什么？</span><span class="sxs-lookup"><span data-stu-id="7d50a-114">What are the high availability requirements of the solution?</span></span>  
  
- <span data-ttu-id="7d50a-115">该解决方案的文档跟踪要求是什么？</span><span class="sxs-lookup"><span data-stu-id="7d50a-115">What are the document tracking requirements of the solution?</span></span>  
  
- <span data-ttu-id="7d50a-116">任何依赖的应用程序，如远程 Web 服务或其他系统的性能特征是什么？</span><span class="sxs-lookup"><span data-stu-id="7d50a-116">What are the performance characteristics of any dependent applications such as a remote Web service or other system?</span></span> <span data-ttu-id="7d50a-117">如果依赖的应用程序无法满足所需的负载与然后将相应地降级，总体系统性能。</span><span class="sxs-lookup"><span data-stu-id="7d50a-117">If dependent applications do not keep up with the required load then the overall system performance will be degraded accordingly.</span></span>  
  
- <span data-ttu-id="7d50a-118">将 BizTalk 应用程序正在消耗与不相关的数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]？</span><span class="sxs-lookup"><span data-stu-id="7d50a-118">Would the BizTalk application be consuming databases not related to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]?</span></span> <span data-ttu-id="7d50a-119">例如，如果 BizTalk 应用程序过多占用 SQL Server 数据库使用 SQL 适配器中的表，表有效地配置？</span><span class="sxs-lookup"><span data-stu-id="7d50a-119">For example, if the BizTalk application is consuming tables in a SQL Server database using the SQL adapter, are the tables efficiently configured?</span></span>  
  
### <a name="hardware-considerations"></a><span data-ttu-id="7d50a-120">硬件注意事项</span><span class="sxs-lookup"><span data-stu-id="7d50a-120">Hardware Considerations</span></span>  
 <span data-ttu-id="7d50a-121">范围解决方案时创建的高级硬件关系图，包括以下：</span><span class="sxs-lookup"><span data-stu-id="7d50a-121">When scoping the solution, create a high-level hardware diagram that includes the following:</span></span>  
  
-   <span data-ttu-id="7d50a-122">计算机体系结构 （如 x86、 x64 和 IA64）</span><span class="sxs-lookup"><span data-stu-id="7d50a-122">Computer architecture (such as x86, x64, and IA64)</span></span>  
  
-   <span data-ttu-id="7d50a-123">CPU 要求 （如类型、 速度、 数量、 内核数和使用超线程）</span><span class="sxs-lookup"><span data-stu-id="7d50a-123">CPU requirements (such as type, speed, number, cores, and use of hyperthreading)</span></span>  
  
-   <span data-ttu-id="7d50a-124">每台计算机的 RAM 要求</span><span class="sxs-lookup"><span data-stu-id="7d50a-124">RAM requirements for each computer</span></span>  
  
-   <span data-ttu-id="7d50a-125">本地磁盘存储 （类型、 大小、 速度）</span><span class="sxs-lookup"><span data-stu-id="7d50a-125">Local disk storage (type, size, speed)</span></span>  
  
-   <span data-ttu-id="7d50a-126">SAN (存储要求： LUN; 的数字SAN 卡类型）</span><span class="sxs-lookup"><span data-stu-id="7d50a-126">SAN (storage requirements: number of LUNS; SAN card type)</span></span>  
  
-   <span data-ttu-id="7d50a-127">网卡 (以每台计算机，100 兆位 (Mbps) 与 1 千兆比特数 (1 Gbps)。)</span><span class="sxs-lookup"><span data-stu-id="7d50a-127">Network cards (number in each computer, 100 megabits (Mbps) versus 1 Gigabit (1 Gbps).)</span></span>  
  
-   <span data-ttu-id="7d50a-128">如何将防火墙部署解决方案中？</span><span class="sxs-lookup"><span data-stu-id="7d50a-128">How will firewalls be deployed in the solution?</span></span>  
  
-   <span data-ttu-id="7d50a-129">将使用网络负载平衡硬件？</span><span class="sxs-lookup"><span data-stu-id="7d50a-129">Will Network Load Balancing hardware be used?</span></span>  
  
-   <span data-ttu-id="7d50a-130">是特定计算机，其可以加入群集？</span><span class="sxs-lookup"><span data-stu-id="7d50a-130">Are specific computers to be clustered?</span></span>  
  
-   <span data-ttu-id="7d50a-131">将会使用虚拟环境涉及 Microsoft HYPER-V Server 或任何其他虚拟化产品？</span><span class="sxs-lookup"><span data-stu-id="7d50a-131">Would you be using a virtual environment involving Microsoft Hyper-V Server or any other virtualization products?</span></span>  
  
## <a name="planning-the-solution"></a><span data-ttu-id="7d50a-132">规划解决方案</span><span class="sxs-lookup"><span data-stu-id="7d50a-132">Planning the Solution</span></span>  
  
### <a name="solution-milestones-timeline"></a><span data-ttu-id="7d50a-133">解决方案里程碑时间线</span><span class="sxs-lookup"><span data-stu-id="7d50a-133">Solution Milestones Timeline</span></span>  
 <span data-ttu-id="7d50a-134">创建具有用于完成您的 BizTalk 解决方案的特定方面的里程碑计划。</span><span class="sxs-lookup"><span data-stu-id="7d50a-134">Create a schedule with milestones for completing specific aspects of your BizTalk solution.</span></span> <span data-ttu-id="7d50a-135">设置特定里程碑会增加解决方案的可能性及时完成。</span><span class="sxs-lookup"><span data-stu-id="7d50a-135">Setting specific milestones will increase the likelihood that the solution will be completed in a timely manner.</span></span>  
  
### <a name="non-microsoft-software-considerations"></a><span data-ttu-id="7d50a-136">非 Microsoft 软件注意事项</span><span class="sxs-lookup"><span data-stu-id="7d50a-136">Non-Microsoft Software Considerations</span></span>  
 <span data-ttu-id="7d50a-137">非 Microsoft 软件将与解决方案一起使用时，请考虑以下方法：</span><span class="sxs-lookup"><span data-stu-id="7d50a-137">Consider the following when non-Microsoft software will be used with the solution:</span></span>  
  
-   <span data-ttu-id="7d50a-138">确定如何软件或硬件配置要求获得。</span><span class="sxs-lookup"><span data-stu-id="7d50a-138">Determine how the software or hardware required be obtained.</span></span>  
  
-   <span data-ttu-id="7d50a-139">规划容量和大小调整，以确保该非 Microsoft 软件不会成为您的解决方案中的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="7d50a-139">Plan for capacity and sizing to ensure that non-Microsoft software does not become a bottleneck in your solution.</span></span>  
  
-   <span data-ttu-id="7d50a-140">确定的计划安装所需的非 Microsoft 软件的操作。</span><span class="sxs-lookup"><span data-stu-id="7d50a-140">Determine a plan of action for installing required non-Microsoft software.</span></span>  
  
-   <span data-ttu-id="7d50a-141">创建用于配置和优化所需的非 Microsoft 软件的操作的计划。</span><span class="sxs-lookup"><span data-stu-id="7d50a-141">Create a plan of action for configuring and optimizing required non-Microsoft software.</span></span>  
  
## <a name="preparing-for-the-solution"></a><span data-ttu-id="7d50a-142">准备解决方案</span><span class="sxs-lookup"><span data-stu-id="7d50a-142">Preparing for the Solution</span></span>  
 <span data-ttu-id="7d50a-143">在准备阶段中包括以下元素：</span><span class="sxs-lookup"><span data-stu-id="7d50a-143">Include the following elements in your preparation phase:</span></span>  
  
### <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="7d50a-144">解决方案平台的详细的设计</span><span class="sxs-lookup"><span data-stu-id="7d50a-144">Detailed Design of the Solution Platform</span></span>  
 <span data-ttu-id="7d50a-145">详细的解决方案设计便于通信，并避免假设，从而提高灵活性和所有活动的有效性。</span><span class="sxs-lookup"><span data-stu-id="7d50a-145">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="7d50a-146">你应完全记录以下元素：</span><span class="sxs-lookup"><span data-stu-id="7d50a-146">You should fully document the following elements:</span></span>  
  
- <span data-ttu-id="7d50a-147">BizTalk Server 数据库以及它们如何分布在计算机上。</span><span class="sxs-lookup"><span data-stu-id="7d50a-147">BizTalk Server databases and how they will be distributed across computers.</span></span>  
  
- <span data-ttu-id="7d50a-148">BizTalk 主机设计和每个主机和其实例的说明。</span><span class="sxs-lookup"><span data-stu-id="7d50a-148">BizTalk Host design and descriptions of each host and their instances.</span></span>  
  
- <span data-ttu-id="7d50a-149">每个业务流程的说明。</span><span class="sxs-lookup"><span data-stu-id="7d50a-149">Description of each orchestration.</span></span>  
  
- <span data-ttu-id="7d50a-150">每个管道的说明。</span><span class="sxs-lookup"><span data-stu-id="7d50a-150">Description of each pipeline.</span></span>  
  
- <span data-ttu-id="7d50a-151">自定义组件，如.NET 程序集和 COM + 组件的说明。</span><span class="sxs-lookup"><span data-stu-id="7d50a-151">Description of custom components such as .NET assemblies and COM+ components.</span></span>  
  
  <span data-ttu-id="7d50a-152">**消息流关系图**</span><span class="sxs-lookup"><span data-stu-id="7d50a-152">**Message Flow Diagrams**</span></span>  
  
  <span data-ttu-id="7d50a-153">创建详细的消息流关系图，以帮助避免出现任何混淆或 false 的假设有关什么是应发生了状况消息处理过程。</span><span class="sxs-lookup"><span data-stu-id="7d50a-153">Create detailed message flow diagrams to help avoid any confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span> <span data-ttu-id="7d50a-154">创建消息流关系图时，应考虑以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="7d50a-154">The following details should be considered when creating the message flow diagrams:</span></span>  
  
- <span data-ttu-id="7d50a-155">介绍了每种类型的消息的时间之前生成的所有消息都发送和已完成所有相关的处理到达的接收位置的生命周期。</span><span class="sxs-lookup"><span data-stu-id="7d50a-155">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
- <span data-ttu-id="7d50a-156">描述如何处理更改的错误情况。</span><span class="sxs-lookup"><span data-stu-id="7d50a-156">Describe how processing changes for error conditions.</span></span>  
  
- <span data-ttu-id="7d50a-157">包括有关相关、 送达通知和确认详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d50a-157">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
- <span data-ttu-id="7d50a-158">包括有关延迟和吞吐量的性能要求信息。</span><span class="sxs-lookup"><span data-stu-id="7d50a-158">Include performance requirement information regarding latency and throughput.</span></span>  
  
  <span data-ttu-id="7d50a-159">**非 Microsoft 软件的详细信息**</span><span class="sxs-lookup"><span data-stu-id="7d50a-159">**Non-Microsoft Software Details**</span></span>  
  
  <span data-ttu-id="7d50a-160">使用的所有非 Microsoft 软件应完整记录详细的解决方案设计的一部分。</span><span class="sxs-lookup"><span data-stu-id="7d50a-160">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
  <span data-ttu-id="7d50a-161">**详细的硬件堆栈**</span><span class="sxs-lookup"><span data-stu-id="7d50a-161">**Detailed Hardware Stack**</span></span>  
  
  <span data-ttu-id="7d50a-162">构建在以前创建的高级别硬件关系图上，下列硬件信息应完整记录：</span><span class="sxs-lookup"><span data-stu-id="7d50a-162">Building on the previously created high level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
- <span data-ttu-id="7d50a-163">Processors</span><span class="sxs-lookup"><span data-stu-id="7d50a-163">Processors</span></span>  
  
  -   <span data-ttu-id="7d50a-164">类型</span><span class="sxs-lookup"><span data-stu-id="7d50a-164">Type</span></span>  
  
  -   <span data-ttu-id="7d50a-165">速度</span><span class="sxs-lookup"><span data-stu-id="7d50a-165">Speed</span></span>  
  
  -   <span data-ttu-id="7d50a-166">核心数</span><span class="sxs-lookup"><span data-stu-id="7d50a-166">Number of cores</span></span>  
  
  -   <span data-ttu-id="7d50a-167">超线程</span><span class="sxs-lookup"><span data-stu-id="7d50a-167">Hyperthreading</span></span>  
  
- <span data-ttu-id="7d50a-168">内存</span><span class="sxs-lookup"><span data-stu-id="7d50a-168">Memory</span></span>  
  
  -   <span data-ttu-id="7d50a-169">Amount</span><span class="sxs-lookup"><span data-stu-id="7d50a-169">Amount</span></span>  
  
  -   <span data-ttu-id="7d50a-170">速度</span><span class="sxs-lookup"><span data-stu-id="7d50a-170">Speed</span></span>  
  
  -   <span data-ttu-id="7d50a-171">奇偶校验</span><span class="sxs-lookup"><span data-stu-id="7d50a-171">Parity</span></span>  
  
- <span data-ttu-id="7d50a-172">网络</span><span class="sxs-lookup"><span data-stu-id="7d50a-172">Network</span></span>  
  
  -   <span data-ttu-id="7d50a-173">网络接口卡 (Nic) 的数量</span><span class="sxs-lookup"><span data-stu-id="7d50a-173">Number of network interface cards (NICs)</span></span>  
  
  -   <span data-ttu-id="7d50a-174">网络的速度</span><span class="sxs-lookup"><span data-stu-id="7d50a-174">Speed of network</span></span>  
  
- <span data-ttu-id="7d50a-175">SAN</span><span class="sxs-lookup"><span data-stu-id="7d50a-175">SAN</span></span>  
  
  -   <span data-ttu-id="7d50a-176">在每台计算机中的 SAN 卡数</span><span class="sxs-lookup"><span data-stu-id="7d50a-176">Number of SAN cards in each computer</span></span>  
  
  -   <span data-ttu-id="7d50a-177">每个计算机和目的，每个 LUN 的逻辑单元号 (Lun) 的数量</span><span class="sxs-lookup"><span data-stu-id="7d50a-177">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
  -   <span data-ttu-id="7d50a-178">速度存储区域网络 (SAN) 卡</span><span class="sxs-lookup"><span data-stu-id="7d50a-178">Speed of storage area network (SAN) Cards</span></span>  
  
  -   <span data-ttu-id="7d50a-179">SAN 卡配置详细信息</span><span class="sxs-lookup"><span data-stu-id="7d50a-179">SAN card configuration details</span></span>  
  
  -   <span data-ttu-id="7d50a-180">SAN 磁盘分配，格式化和分区</span><span class="sxs-lookup"><span data-stu-id="7d50a-180">SAN disk allocation, formatting, and partitioning</span></span>  
  
- <span data-ttu-id="7d50a-181">磁盘</span><span class="sxs-lookup"><span data-stu-id="7d50a-181">Disk</span></span>  
  
  -   <span data-ttu-id="7d50a-182">每台计算机的的本地磁盘详细信息</span><span class="sxs-lookup"><span data-stu-id="7d50a-182">Local disk details for each computer</span></span>  
  
  -   <span data-ttu-id="7d50a-183">格式设置为本地磁盘使用</span><span class="sxs-lookup"><span data-stu-id="7d50a-183">Formatting used for local disks</span></span>  
  
  -   <span data-ttu-id="7d50a-184">分区的本地磁盘的详细信息</span><span class="sxs-lookup"><span data-stu-id="7d50a-184">Partitioning details for local disks</span></span>  
  
- <span data-ttu-id="7d50a-185">Cache</span><span class="sxs-lookup"><span data-stu-id="7d50a-185">Cache</span></span>  
  
  -   <span data-ttu-id="7d50a-186">L2 缓存量</span><span class="sxs-lookup"><span data-stu-id="7d50a-186">L2 Cache amount</span></span>  
  
  -   <span data-ttu-id="7d50a-187">L3 缓存量</span><span class="sxs-lookup"><span data-stu-id="7d50a-187">L3 Cache amount</span></span>  
  
  <span data-ttu-id="7d50a-188">**详细的软件堆栈**</span><span class="sxs-lookup"><span data-stu-id="7d50a-188">**Detailed Software Stack**</span></span>  
  
  <span data-ttu-id="7d50a-189">应记录以下的软件信息：</span><span class="sxs-lookup"><span data-stu-id="7d50a-189">The following software information should be documented:</span></span>  
  
- <span data-ttu-id="7d50a-190">特定操作系统版本、 版本和体系结构</span><span class="sxs-lookup"><span data-stu-id="7d50a-190">Specific operating system versions, editions, and architecture</span></span>  
  
- <span data-ttu-id="7d50a-191">特定的操作系统功能</span><span class="sxs-lookup"><span data-stu-id="7d50a-191">Specific operating system features</span></span>  
  
- <span data-ttu-id="7d50a-192">在每台计算机上安装的特定软件</span><span class="sxs-lookup"><span data-stu-id="7d50a-192">Specific software installed on each computer</span></span>  
  
- <span data-ttu-id="7d50a-193">特定驱动程序</span><span class="sxs-lookup"><span data-stu-id="7d50a-193">Specific drivers</span></span>  
  
- <span data-ttu-id="7d50a-194">Service Pack 和其他更新</span><span class="sxs-lookup"><span data-stu-id="7d50a-194">Service Packs and other updates</span></span>  
  
- <span data-ttu-id="7d50a-195">如果它们不同默认值，则使用的所有软件和操作系统功能的配置值</span><span class="sxs-lookup"><span data-stu-id="7d50a-195">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="building-out-the-environment-for-the-solution"></a><span data-ttu-id="7d50a-196">构建解决方案的环境</span><span class="sxs-lookup"><span data-stu-id="7d50a-196">Building Out the Environment for the Solution</span></span>  
 <span data-ttu-id="7d50a-197">有关安装的详细说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和软件要求处于[BizTalk Server 安装指南](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="7d50a-197">Detailed instructions for installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the software requirements are in the [BizTalk Server Installation Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d50a-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d50a-198">See Also</span></span>  
 [<span data-ttu-id="7d50a-199">规划 BizTalk Server 层</span><span class="sxs-lookup"><span data-stu-id="7d50a-199">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)
