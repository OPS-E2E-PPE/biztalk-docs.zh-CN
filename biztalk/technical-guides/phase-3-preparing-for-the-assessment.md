---
title: "阶段 3： 准备评估 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 890047f6a13352d89d33d9514883dc20eacd4001
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="phase-3-preparing-for-the-assessment"></a><span data-ttu-id="42eca-102">阶段 3： 准备评估</span><span class="sxs-lookup"><span data-stu-id="42eca-102">Phase 3: Preparing for the Assessment</span></span>
<span data-ttu-id="42eca-103">性能评估阶段可以被想象成审视阶段的"如何""怎么"和计划阶段的准备工作的"何时。"</span><span class="sxs-lookup"><span data-stu-id="42eca-103">The Prepare phase of a performance assessment can be thought of as the “how” to the Scope phase’s “what” and the Plan phase’s “when.”</span></span> <span data-ttu-id="42eca-104">此时在性能评估中，所有利益干系人应具有达成一致后用户参与策略和计划的范围进行试验室。</span><span class="sxs-lookup"><span data-stu-id="42eca-104">At this point in the performance assessment, all stakeholders should have agreed upon the scope of the engagement and the plans for conducting the lab.</span></span> <span data-ttu-id="42eca-105">它是在其中执行计划和执行任何步骤以获取已准备好的性能实验室的执行性能评估的准备阶段。</span><span class="sxs-lookup"><span data-stu-id="42eca-105">It is in the Prepare phase of the performance assessment where the plans are executed and steps are taken to get ready for execution of the performance lab.</span></span>  
  
 <span data-ttu-id="42eca-106">本主题介绍将 BizTalk Server 性能评估的准备阶段的各个方面。</span><span class="sxs-lookup"><span data-stu-id="42eca-106">This topic describes the various aspects of the Prepare phase of a BizTalk Server performance assessment.</span></span>  
  
## <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="42eca-107">详细的解决方案平台的设计</span><span class="sxs-lookup"><span data-stu-id="42eca-107">Detailed design of the solution platform</span></span>  
 <span data-ttu-id="42eca-108">详细的解决方案设计便于通信，并避免假设，从而提高灵活性和的所有活动的有效性。</span><span class="sxs-lookup"><span data-stu-id="42eca-108">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="42eca-109">你应完全记录以下元素：</span><span class="sxs-lookup"><span data-stu-id="42eca-109">You should fully document the following elements:</span></span>  
  
-   <span data-ttu-id="42eca-110">**BizTalk Server 数据库以及它们如何分布跨计算机**-SQL Server 性能是整体 BizTalk Server 性能的关键因素之一。</span><span class="sxs-lookup"><span data-stu-id="42eca-110">**BizTalk Server databases and how they will be distributed across computers** - SQL Server performance is one of the key factors in overall BizTalk Server performance.</span></span> <span data-ttu-id="42eca-111">如果 SQL Server 遇到资源约束，这将影响的 BizTalk Server 来处理消息的能力。</span><span class="sxs-lookup"><span data-stu-id="42eca-111">If SQL Server is experiencing resource constraints, this will impact the ability of BizTalk Server to process messages.</span></span> <span data-ttu-id="42eca-112">影响 BizTalk 数据库性能的主要因素是磁盘上托管的速度。</span><span class="sxs-lookup"><span data-stu-id="42eca-112">The main factor that influences BizTalk database performance is the speed of disks that they are hosted on.</span></span> <span data-ttu-id="42eca-113">为每个 BizTalk 分隔的事务日志和数据库文件已对数据库分别放在不同的驱动器或 SAN LUN 被证实将大大提高 BizTalk Server 的整体性能。</span><span class="sxs-lookup"><span data-stu-id="42eca-113">Separating the transaction log and database files for each BizTalk database onto separate drives or SAN LUN’s has been shown to remarkably improve the overall performance of BizTalk Server.</span></span> <span data-ttu-id="42eca-114">因此，很重要，可以轻松进行访问的方式记录此信息。</span><span class="sxs-lookup"><span data-stu-id="42eca-114">Therefore, it is important that this information be recorded in an easily accessible manner.</span></span> <span data-ttu-id="42eca-115">将在生产环境中使用的值应记录详细的解决方案设计中。</span><span class="sxs-lookup"><span data-stu-id="42eca-115">The values that will be used in the production environment should be documented in the detailed solution design.</span></span> <span data-ttu-id="42eca-116">下表提供了如何完成此操作的示例。</span><span class="sxs-lookup"><span data-stu-id="42eca-116">The following table provides an example of how this can be done.</span></span>  
  
    |<span data-ttu-id="42eca-117">BizTalk 数据库</span><span class="sxs-lookup"><span data-stu-id="42eca-117">BizTalk Database</span></span>|<span data-ttu-id="42eca-118">卷名</span><span class="sxs-lookup"><span data-stu-id="42eca-118">Volume Name</span></span>|<span data-ttu-id="42eca-119">文件</span><span class="sxs-lookup"><span data-stu-id="42eca-119">Files</span></span>|<span data-ttu-id="42eca-120">LUN # 或 ML_ #</span><span class="sxs-lookup"><span data-stu-id="42eca-120">LUN# or ML_#</span></span>|<span data-ttu-id="42eca-121">物理 LUN 的大小 (GB)</span><span class="sxs-lookup"><span data-stu-id="42eca-121">Physical LUN Size (GB)</span></span>|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |<span data-ttu-id="42eca-122">MessageBox</span><span class="sxs-lookup"><span data-stu-id="42eca-122">MessageBox</span></span>|<span data-ttu-id="42eca-123">Data_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="42eca-123">Data_TempDb_1</span></span>|<span data-ttu-id="42eca-124">TEMPDB、 MASTER 和 MSDB 数据文件</span><span class="sxs-lookup"><span data-stu-id="42eca-124">TEMPDB,  MASTER, and MSDB data files</span></span>|<span data-ttu-id="42eca-125">1</span><span class="sxs-lookup"><span data-stu-id="42eca-125">1</span></span>|<span data-ttu-id="42eca-126">134</span><span class="sxs-lookup"><span data-stu-id="42eca-126">134</span></span>|  
    ||<span data-ttu-id="42eca-127">Logs_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="42eca-127">Logs_TempDb_1</span></span>|<span data-ttu-id="42eca-128">TEMPDB、 MASTER 和 MSDB 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="42eca-128">TEMPDB,  MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="42eca-129">2</span><span class="sxs-lookup"><span data-stu-id="42eca-129">2</span></span>|<span data-ttu-id="42eca-130">134</span><span class="sxs-lookup"><span data-stu-id="42eca-130">134</span></span>|  
    ||<span data-ttu-id="42eca-131">Data_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="42eca-131">Data_BtsMsgBox</span></span>|<span data-ttu-id="42eca-132">BizTalkMsgBoxDb 数据文件</span><span class="sxs-lookup"><span data-stu-id="42eca-132">BizTalkMsgBoxDb data file</span></span>|<span data-ttu-id="42eca-133">3</span><span class="sxs-lookup"><span data-stu-id="42eca-133">3</span></span>|<span data-ttu-id="42eca-134">134</span><span class="sxs-lookup"><span data-stu-id="42eca-134">134</span></span>|  
    ||<span data-ttu-id="42eca-135">Logs_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="42eca-135">Logs_BtsMsgBox</span></span>|<span data-ttu-id="42eca-136">BizTalkMsgBoxDb 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="42eca-136">BizTalkMsgBoxDb transaction log file</span></span>|<span data-ttu-id="42eca-137">4</span><span class="sxs-lookup"><span data-stu-id="42eca-137">4</span></span>|<span data-ttu-id="42eca-138">134</span><span class="sxs-lookup"><span data-stu-id="42eca-138">134</span></span>|  
    |<span data-ttu-id="42eca-139">BAM</span><span class="sxs-lookup"><span data-stu-id="42eca-139">BAM</span></span>|<span data-ttu-id="42eca-140">Data_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="42eca-140">Data_TempDb_2</span></span>|<span data-ttu-id="42eca-141">TEMPDB、 MASTER 和 MSDB 数据文件</span><span class="sxs-lookup"><span data-stu-id="42eca-141">TEMPDB, MASTER, and MSDB data files</span></span>|<span data-ttu-id="42eca-142">5</span><span class="sxs-lookup"><span data-stu-id="42eca-142">5</span></span>|<span data-ttu-id="42eca-143">67</span><span class="sxs-lookup"><span data-stu-id="42eca-143">67</span></span>|  
    ||<span data-ttu-id="42eca-144">Logs_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="42eca-144">Logs_TempDb_2</span></span>|<span data-ttu-id="42eca-145">TEMPDB、 MASTER 和 MSDB 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="42eca-145">TEMPDB, MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="42eca-146">6</span><span class="sxs-lookup"><span data-stu-id="42eca-146">6</span></span>|<span data-ttu-id="42eca-147">67</span><span class="sxs-lookup"><span data-stu-id="42eca-147">67</span></span>|  
    ||<span data-ttu-id="42eca-148">Data_BAM</span><span class="sxs-lookup"><span data-stu-id="42eca-148">Data_BAM</span></span>|<span data-ttu-id="42eca-149">BAMPrimaryImport 数据文件</span><span class="sxs-lookup"><span data-stu-id="42eca-149">BAMPrimaryImport data file</span></span>|<span data-ttu-id="42eca-150">7</span><span class="sxs-lookup"><span data-stu-id="42eca-150">7</span></span>|<span data-ttu-id="42eca-151">134</span><span class="sxs-lookup"><span data-stu-id="42eca-151">134</span></span>|  
    ||<span data-ttu-id="42eca-152">Logs_BAM</span><span class="sxs-lookup"><span data-stu-id="42eca-152">Logs_BAM</span></span>|<span data-ttu-id="42eca-153">BAMPrimaryImport 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="42eca-153">BAMPrimaryImport transaction log file</span></span>|<span data-ttu-id="42eca-154">8</span><span class="sxs-lookup"><span data-stu-id="42eca-154">8</span></span>|<span data-ttu-id="42eca-155">134</span><span class="sxs-lookup"><span data-stu-id="42eca-155">134</span></span>|  
    |<span data-ttu-id="42eca-156">BizTalk 跟踪、 管理、 单一登录，和规则引擎的数据库</span><span class="sxs-lookup"><span data-stu-id="42eca-156">BizTalk Tracking, Management, Single Sign-On, and Rule Engine databases</span></span>|<span data-ttu-id="42eca-157">Data_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="42eca-157">Data_TempDb_3</span></span>|<span data-ttu-id="42eca-158">TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 数据文件</span><span class="sxs-lookup"><span data-stu-id="42eca-158">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb data files</span></span>|<span data-ttu-id="42eca-159">9</span><span class="sxs-lookup"><span data-stu-id="42eca-159">9</span></span>|<span data-ttu-id="42eca-160">67</span><span class="sxs-lookup"><span data-stu-id="42eca-160">67</span></span>|  
    ||<span data-ttu-id="42eca-161">Logs_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="42eca-161">Logs_TempDb_3</span></span>|<span data-ttu-id="42eca-162">TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="42eca-162">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb transaction log files</span></span>|<span data-ttu-id="42eca-163">10</span><span class="sxs-lookup"><span data-stu-id="42eca-163">10</span></span>|<span data-ttu-id="42eca-164">67</span><span class="sxs-lookup"><span data-stu-id="42eca-164">67</span></span>|  
  
-   <span data-ttu-id="42eca-165">**BizTalk 主机设计和每个主机和其实例的说明。**</span><span class="sxs-lookup"><span data-stu-id="42eca-165">**BizTalk Host design and descriptions of each host and their instances.**</span></span>  
  
-   <span data-ttu-id="42eca-166">**每个业务流程的说明。**</span><span class="sxs-lookup"><span data-stu-id="42eca-166">**Description of each orchestration.**</span></span>  
  
-   <span data-ttu-id="42eca-167">**每个管道的说明。**</span><span class="sxs-lookup"><span data-stu-id="42eca-167">**Description of each pipeline.**</span></span>  
  
-   <span data-ttu-id="42eca-168">**自定义组件，如.NET 程序集和 COM + 组件的说明。**</span><span class="sxs-lookup"><span data-stu-id="42eca-168">**Description of custom components such as .NET assemblies and COM+ components.**</span></span>  
  
## <a name="detailed-architecture-diagram"></a><span data-ttu-id="42eca-169">详细体系结构关系图</span><span class="sxs-lookup"><span data-stu-id="42eca-169">Detailed architecture diagram</span></span>  
 <span data-ttu-id="42eca-170">下图说明了可用于性能评估的体系结构关系图。</span><span class="sxs-lookup"><span data-stu-id="42eca-170">The following diagram illustrates an architecture diagram that could be used for a performance assessment.</span></span>  
  
 <span data-ttu-id="42eca-171">![BizTalk 体系结构关系图](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span><span class="sxs-lookup"><span data-stu-id="42eca-171">![BizTalk Architecture Diagram](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span></span>  
<span data-ttu-id="42eca-172">BizTalk 体系结构关系图</span><span class="sxs-lookup"><span data-stu-id="42eca-172">BizTalk Architecture Diagram</span></span>  
  
## <a name="message-flow-diagrams"></a><span data-ttu-id="42eca-173">消息流关系图</span><span class="sxs-lookup"><span data-stu-id="42eca-173">Message flow diagrams</span></span>  
 <span data-ttu-id="42eca-174">创建详细的消息流图，以帮助防止混淆或 false 的假设，有关什么是应该在处理期间不会发生情况的消息。</span><span class="sxs-lookup"><span data-stu-id="42eca-174">Create detailed message flow diagrams to help prevent confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span>  
  
 <span data-ttu-id="42eca-175">在整体考虑 BizTalk 解决方案，我们通常认为消息流经系统。</span><span class="sxs-lookup"><span data-stu-id="42eca-175">When thinking about a BizTalk solution holistically, we tend to think of the message flow through the system.</span></span> <span data-ttu-id="42eca-176">执行测试，因为流的所有部分都必须被都视为潜在瓶颈的性能时，此消息流透视一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="42eca-176">This Message Flow perspective is especially important when doing performance testing because all parts of the flow must be considered as potential bottlenecks.</span></span> <span data-ttu-id="42eca-177">让消息流图阻止任何混淆或有关什么是应该在每个测试期间不会发生情况的消息错误的假定运行。</span><span class="sxs-lookup"><span data-stu-id="42eca-177">Having a message flow diagram prevents any confusion or false assumptions regarding what is supposed to be happening to messages during each test run.</span></span>  
  
 <span data-ttu-id="42eca-178">在以下示例中，使用简单 Visio 形状，创建与背景无关项目中的每个人都可以快速了解一条消息如何获取到系统、 解决方案的哪些部分消息、 交互和最后消息便之后的位置处理。</span><span class="sxs-lookup"><span data-stu-id="42eca-178">In the following example, created using simple Visio shapes, everyone on the project regardless of background can quickly understand how a message gets into the system, what parts of the solutions interact with the message, and finally where the message lands after processing.</span></span>  
  
 <span data-ttu-id="42eca-179">![消息流图](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span><span class="sxs-lookup"><span data-stu-id="42eca-179">![Message Flow Diagram](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span></span>  
<span data-ttu-id="42eca-180">消息流关系图</span><span class="sxs-lookup"><span data-stu-id="42eca-180">Message Flow Diagram</span></span>  
  
 <span data-ttu-id="42eca-181">创建消息流关系图时，应考虑以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="42eca-181">The following details should be considered when creating the message flow diagrams:</span></span>  
  
-   <span data-ttu-id="42eca-182">描述了每种类型的消息从时间之前生成的所有消息都发送和完成所有相关的处理到达的接收位置的生命周期。</span><span class="sxs-lookup"><span data-stu-id="42eca-182">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
-   <span data-ttu-id="42eca-183">描述如何处理更改为错误条件。</span><span class="sxs-lookup"><span data-stu-id="42eca-183">Describe how processing changes for error conditions.</span></span>  
  
-   <span data-ttu-id="42eca-184">包括有关相关、 传递通知和确认的详细信息。</span><span class="sxs-lookup"><span data-stu-id="42eca-184">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
-   <span data-ttu-id="42eca-185">包括有关依赖于外部系统的详细信息。</span><span class="sxs-lookup"><span data-stu-id="42eca-185">Include details about dependence on external systems.</span></span>  
  
-   <span data-ttu-id="42eca-186">包括有关延迟和吞吐量的性能要求信息。</span><span class="sxs-lookup"><span data-stu-id="42eca-186">Include performance requirement information regarding latency and throughput.</span></span>  
  
## <a name="third-party-software-details"></a><span data-ttu-id="42eca-187">第三方软件详细信息</span><span class="sxs-lookup"><span data-stu-id="42eca-187">Third-party software details</span></span>  
 <span data-ttu-id="42eca-188">使用的所有非 Microsoft 软件应完全记录详细的解决方案设计的一部分。</span><span class="sxs-lookup"><span data-stu-id="42eca-188">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
## <a name="detailed-lab-hardware-stack"></a><span data-ttu-id="42eca-189">详细的实验室硬件堆栈</span><span class="sxs-lookup"><span data-stu-id="42eca-189">Detailed lab hardware stack</span></span>  
 <span data-ttu-id="42eca-190">在以前创建的高级硬件关系图上构建，下列硬件信息应将完全记录：</span><span class="sxs-lookup"><span data-stu-id="42eca-190">Building on the previously created high-level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
-   <span data-ttu-id="42eca-191">Processors</span><span class="sxs-lookup"><span data-stu-id="42eca-191">Processors</span></span>  
  
    -   <span data-ttu-id="42eca-192">类型</span><span class="sxs-lookup"><span data-stu-id="42eca-192">Type</span></span>  
  
    -   <span data-ttu-id="42eca-193">速度</span><span class="sxs-lookup"><span data-stu-id="42eca-193">Speed</span></span>  
  
    -   <span data-ttu-id="42eca-194">内核数</span><span class="sxs-lookup"><span data-stu-id="42eca-194">Number of cores</span></span>  
  
    -   <span data-ttu-id="42eca-195">超线程</span><span class="sxs-lookup"><span data-stu-id="42eca-195">Hyperthreading</span></span>  
  
-   <span data-ttu-id="42eca-196">内存</span><span class="sxs-lookup"><span data-stu-id="42eca-196">Memory</span></span>  
  
    -   <span data-ttu-id="42eca-197">Amount</span><span class="sxs-lookup"><span data-stu-id="42eca-197">Amount</span></span>  
  
    -   <span data-ttu-id="42eca-198">速度</span><span class="sxs-lookup"><span data-stu-id="42eca-198">Speed</span></span>  
  
    -   <span data-ttu-id="42eca-199">奇偶校验</span><span class="sxs-lookup"><span data-stu-id="42eca-199">Parity</span></span>  
  
-   <span data-ttu-id="42eca-200">Network</span><span class="sxs-lookup"><span data-stu-id="42eca-200">Network</span></span>  
  
    -   <span data-ttu-id="42eca-201">网络接口卡 (Nic) 数</span><span class="sxs-lookup"><span data-stu-id="42eca-201">Number of network interface cards (NICs)</span></span>  
  
    -   <span data-ttu-id="42eca-202">网络的速度</span><span class="sxs-lookup"><span data-stu-id="42eca-202">Speed of network</span></span>  
  
-   <span data-ttu-id="42eca-203">SAN</span><span class="sxs-lookup"><span data-stu-id="42eca-203">SAN</span></span>  
  
    -   <span data-ttu-id="42eca-204">每台计算机中的 SAN 卡数</span><span class="sxs-lookup"><span data-stu-id="42eca-204">Number of SAN cards in each computer</span></span>  
  
    -   <span data-ttu-id="42eca-205">每台计算机和每个 LUN 的用途的逻辑单元号 (Lun) 数</span><span class="sxs-lookup"><span data-stu-id="42eca-205">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
    -   <span data-ttu-id="42eca-206">速度的存储区域网络 (SAN) 卡</span><span class="sxs-lookup"><span data-stu-id="42eca-206">Speed of storage area network (SAN) Cards</span></span>  
  
    -   <span data-ttu-id="42eca-207">SAN 卡配置详细信息</span><span class="sxs-lookup"><span data-stu-id="42eca-207">SAN card configuration details</span></span>  
  
    -   <span data-ttu-id="42eca-208">SAN 磁盘分配，格式设置，和分区</span><span class="sxs-lookup"><span data-stu-id="42eca-208">SAN disk allocation, formatting, and partitioning</span></span>  
  
-   <span data-ttu-id="42eca-209">磁盘</span><span class="sxs-lookup"><span data-stu-id="42eca-209">Disk</span></span>  
  
    -   <span data-ttu-id="42eca-210">每台计算机的的本地磁盘详细信息</span><span class="sxs-lookup"><span data-stu-id="42eca-210">Local disk details for each computer</span></span>  
  
    -   <span data-ttu-id="42eca-211">格式设置用于本地磁盘</span><span class="sxs-lookup"><span data-stu-id="42eca-211">Formatting used for local disks</span></span>  
  
    -   <span data-ttu-id="42eca-212">分区本地磁盘的详细的信息</span><span class="sxs-lookup"><span data-stu-id="42eca-212">Partitioning details for local disks</span></span>  
  
-   <span data-ttu-id="42eca-213">Cache</span><span class="sxs-lookup"><span data-stu-id="42eca-213">Cache</span></span>  
  
    -   <span data-ttu-id="42eca-214">L2 缓存量</span><span class="sxs-lookup"><span data-stu-id="42eca-214">L2 Cache amount</span></span>  
  
    -   <span data-ttu-id="42eca-215">L3 缓存量</span><span class="sxs-lookup"><span data-stu-id="42eca-215">L3 Cache amount</span></span>  
  
## <a name="detailed-lab-software-stack"></a><span data-ttu-id="42eca-216">详细的实验室软件堆栈</span><span class="sxs-lookup"><span data-stu-id="42eca-216">Detailed lab software stack</span></span>  
 <span data-ttu-id="42eca-217">应记录以下的软件信息：</span><span class="sxs-lookup"><span data-stu-id="42eca-217">The following software information should be documented:</span></span>  
  
-   <span data-ttu-id="42eca-218">特定操作系统版本、 版本以及体系结构</span><span class="sxs-lookup"><span data-stu-id="42eca-218">Specific operating system versions, editions, and architecture</span></span>  
  
-   <span data-ttu-id="42eca-219">特定的操作系统功能</span><span class="sxs-lookup"><span data-stu-id="42eca-219">Specific operating system features</span></span>  
  
-   <span data-ttu-id="42eca-220">每台计算机上安装的特定软件</span><span class="sxs-lookup"><span data-stu-id="42eca-220">Specific software installed on each computer</span></span>  
  
-   <span data-ttu-id="42eca-221">特定驱动程序</span><span class="sxs-lookup"><span data-stu-id="42eca-221">Specific drivers</span></span>  
  
-   <span data-ttu-id="42eca-222">Service Pack 和其他更新</span><span class="sxs-lookup"><span data-stu-id="42eca-222">Service Packs and other updates</span></span>  
  
-   <span data-ttu-id="42eca-223">如果它们会不同于默认值所使用的所有软件和操作系统功能的配置值</span><span class="sxs-lookup"><span data-stu-id="42eca-223">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42eca-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42eca-224">See Also</span></span>  
 [<span data-ttu-id="42eca-225">性能评估阶段</span><span class="sxs-lookup"><span data-stu-id="42eca-225">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)