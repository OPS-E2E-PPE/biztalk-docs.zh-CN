---
title: 阶段 3:评估准备 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9df65cbac6b612db6faa979cd2ff57d1a53bd83f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399591"
---
# <a name="phase-3-preparing-for-the-assessment"></a><span data-ttu-id="caeba-102">阶段 3:评估准备</span><span class="sxs-lookup"><span data-stu-id="caeba-102">Phase 3: Preparing for the Assessment</span></span>
<span data-ttu-id="caeba-103">准备性能评估阶段可以认为的"如何"审视阶段的"what"和计划阶段的"when"。</span><span class="sxs-lookup"><span data-stu-id="caeba-103">The Prepare phase of a performance assessment can be thought of as the “how” to the Scope phase’s “what” and the Plan phase’s “when.”</span></span> <span data-ttu-id="caeba-104">此时在性能评估中，所有利益相关者应具有达成一致后执行实验室 engagement 和计划的范围。</span><span class="sxs-lookup"><span data-stu-id="caeba-104">At this point in the performance assessment, all stakeholders should have agreed upon the scope of the engagement and the plans for conducting the lab.</span></span> <span data-ttu-id="caeba-105">它是在其中执行计划并采取步骤来获取已准备好的性能实验室执行的性能评估的准备阶段。</span><span class="sxs-lookup"><span data-stu-id="caeba-105">It is in the Prepare phase of the performance assessment where the plans are executed and steps are taken to get ready for execution of the performance lab.</span></span>  
  
 <span data-ttu-id="caeba-106">本主题介绍 BizTalk Server 性能评估的准备阶段的各个方面。</span><span class="sxs-lookup"><span data-stu-id="caeba-106">This topic describes the various aspects of the Prepare phase of a BizTalk Server performance assessment.</span></span>  
  
## <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="caeba-107">解决方案平台的详细的设计</span><span class="sxs-lookup"><span data-stu-id="caeba-107">Detailed design of the solution platform</span></span>  
 <span data-ttu-id="caeba-108">详细的解决方案设计便于通信，并避免假设，从而提高灵活性和所有活动的有效性。</span><span class="sxs-lookup"><span data-stu-id="caeba-108">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="caeba-109">你应完全记录以下元素：</span><span class="sxs-lookup"><span data-stu-id="caeba-109">You should fully document the following elements:</span></span>  
  
-   <span data-ttu-id="caeba-110">**BizTalk Server 数据库和它们如何分布在计算机**-SQL Server 的性能是在 BizTalk 服务器的总体性能的关键因素之一。</span><span class="sxs-lookup"><span data-stu-id="caeba-110">**BizTalk Server databases and how they will be distributed across computers** - SQL Server performance is one of the key factors in overall BizTalk Server performance.</span></span> <span data-ttu-id="caeba-111">如果 SQL Server 遇到资源限制，这会影响 BizTalk server 处理消息的功能。</span><span class="sxs-lookup"><span data-stu-id="caeba-111">If SQL Server is experiencing resource constraints, this will impact the ability of BizTalk Server to process messages.</span></span> <span data-ttu-id="caeba-112">会影响 BizTalk 数据库性能的主要因素是托管的磁盘的速度。</span><span class="sxs-lookup"><span data-stu-id="caeba-112">The main factor that influences BizTalk database performance is the speed of disks that they are hosted on.</span></span> <span data-ttu-id="caeba-113">将事务日志和数据库文件分开的每个 BizTalk 数据库分别放在不同的驱动器或 SAN LUN 已证实非常改进 BizTalk Server 的整体性能。</span><span class="sxs-lookup"><span data-stu-id="caeba-113">Separating the transaction log and database files for each BizTalk database onto separate drives or SAN LUN’s has been shown to remarkably improve the overall performance of BizTalk Server.</span></span> <span data-ttu-id="caeba-114">因此，很重要，可以轻松进行访问的方式记录此信息。</span><span class="sxs-lookup"><span data-stu-id="caeba-114">Therefore, it is important that this information be recorded in an easily accessible manner.</span></span> <span data-ttu-id="caeba-115">将在生产环境中使用的值应记录在详细的解决方案设计。</span><span class="sxs-lookup"><span data-stu-id="caeba-115">The values that will be used in the production environment should be documented in the detailed solution design.</span></span> <span data-ttu-id="caeba-116">下表提供了如何执行此操作的示例。</span><span class="sxs-lookup"><span data-stu-id="caeba-116">The following table provides an example of how this can be done.</span></span>  
  
    |<span data-ttu-id="caeba-117">BizTalk 数据库</span><span class="sxs-lookup"><span data-stu-id="caeba-117">BizTalk Database</span></span>|<span data-ttu-id="caeba-118">卷名</span><span class="sxs-lookup"><span data-stu-id="caeba-118">Volume Name</span></span>|<span data-ttu-id="caeba-119">文件</span><span class="sxs-lookup"><span data-stu-id="caeba-119">Files</span></span>|<span data-ttu-id="caeba-120">LUN # 或 ML_ #</span><span class="sxs-lookup"><span data-stu-id="caeba-120">LUN# or ML_#</span></span>|<span data-ttu-id="caeba-121">物理 LUN 的大小 (GB)</span><span class="sxs-lookup"><span data-stu-id="caeba-121">Physical LUN Size (GB)</span></span>|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |<span data-ttu-id="caeba-122">MessageBox</span><span class="sxs-lookup"><span data-stu-id="caeba-122">MessageBox</span></span>|<span data-ttu-id="caeba-123">Data_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="caeba-123">Data_TempDb_1</span></span>|<span data-ttu-id="caeba-124">TEMPDB 和 MASTER、 MSDB 数据文件</span><span class="sxs-lookup"><span data-stu-id="caeba-124">TEMPDB,  MASTER, and MSDB data files</span></span>|<span data-ttu-id="caeba-125">1</span><span class="sxs-lookup"><span data-stu-id="caeba-125">1</span></span>|<span data-ttu-id="caeba-126">134</span><span class="sxs-lookup"><span data-stu-id="caeba-126">134</span></span>|  
    ||<span data-ttu-id="caeba-127">Logs_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="caeba-127">Logs_TempDb_1</span></span>|<span data-ttu-id="caeba-128">TEMPDB、 MASTER 和 MSDB 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="caeba-128">TEMPDB,  MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="caeba-129">2</span><span class="sxs-lookup"><span data-stu-id="caeba-129">2</span></span>|<span data-ttu-id="caeba-130">134</span><span class="sxs-lookup"><span data-stu-id="caeba-130">134</span></span>|  
    ||<span data-ttu-id="caeba-131">Data_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="caeba-131">Data_BtsMsgBox</span></span>|<span data-ttu-id="caeba-132">BizTalkMsgBoxDb 数据文件</span><span class="sxs-lookup"><span data-stu-id="caeba-132">BizTalkMsgBoxDb data file</span></span>|<span data-ttu-id="caeba-133">3</span><span class="sxs-lookup"><span data-stu-id="caeba-133">3</span></span>|<span data-ttu-id="caeba-134">134</span><span class="sxs-lookup"><span data-stu-id="caeba-134">134</span></span>|  
    ||<span data-ttu-id="caeba-135">Logs_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="caeba-135">Logs_BtsMsgBox</span></span>|<span data-ttu-id="caeba-136">BizTalkMsgBoxDb 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="caeba-136">BizTalkMsgBoxDb transaction log file</span></span>|<span data-ttu-id="caeba-137">4</span><span class="sxs-lookup"><span data-stu-id="caeba-137">4</span></span>|<span data-ttu-id="caeba-138">134</span><span class="sxs-lookup"><span data-stu-id="caeba-138">134</span></span>|  
    |<span data-ttu-id="caeba-139">BAM</span><span class="sxs-lookup"><span data-stu-id="caeba-139">BAM</span></span>|<span data-ttu-id="caeba-140">Data_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="caeba-140">Data_TempDb_2</span></span>|<span data-ttu-id="caeba-141">TEMPDB 和 MASTER、 MSDB 数据文件</span><span class="sxs-lookup"><span data-stu-id="caeba-141">TEMPDB, MASTER, and MSDB data files</span></span>|<span data-ttu-id="caeba-142">5</span><span class="sxs-lookup"><span data-stu-id="caeba-142">5</span></span>|<span data-ttu-id="caeba-143">67</span><span class="sxs-lookup"><span data-stu-id="caeba-143">67</span></span>|  
    ||<span data-ttu-id="caeba-144">Logs_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="caeba-144">Logs_TempDb_2</span></span>|<span data-ttu-id="caeba-145">TEMPDB、 MASTER 和 MSDB 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="caeba-145">TEMPDB, MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="caeba-146">6</span><span class="sxs-lookup"><span data-stu-id="caeba-146">6</span></span>|<span data-ttu-id="caeba-147">67</span><span class="sxs-lookup"><span data-stu-id="caeba-147">67</span></span>|  
    ||<span data-ttu-id="caeba-148">Data_BAM</span><span class="sxs-lookup"><span data-stu-id="caeba-148">Data_BAM</span></span>|<span data-ttu-id="caeba-149">BAMPrimaryImport 数据文件</span><span class="sxs-lookup"><span data-stu-id="caeba-149">BAMPrimaryImport data file</span></span>|<span data-ttu-id="caeba-150">7</span><span class="sxs-lookup"><span data-stu-id="caeba-150">7</span></span>|<span data-ttu-id="caeba-151">134</span><span class="sxs-lookup"><span data-stu-id="caeba-151">134</span></span>|  
    ||<span data-ttu-id="caeba-152">Logs_BAM</span><span class="sxs-lookup"><span data-stu-id="caeba-152">Logs_BAM</span></span>|<span data-ttu-id="caeba-153">BAMPrimaryImport 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="caeba-153">BAMPrimaryImport transaction log file</span></span>|<span data-ttu-id="caeba-154">8</span><span class="sxs-lookup"><span data-stu-id="caeba-154">8</span></span>|<span data-ttu-id="caeba-155">134</span><span class="sxs-lookup"><span data-stu-id="caeba-155">134</span></span>|  
    |<span data-ttu-id="caeba-156">BizTalk 跟踪、 管理、 单一登录，和规则引擎数据库</span><span class="sxs-lookup"><span data-stu-id="caeba-156">BizTalk Tracking, Management, Single Sign-On, and Rule Engine databases</span></span>|<span data-ttu-id="caeba-157">Data_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="caeba-157">Data_TempDb_3</span></span>|<span data-ttu-id="caeba-158">TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 数据文件</span><span class="sxs-lookup"><span data-stu-id="caeba-158">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb data files</span></span>|<span data-ttu-id="caeba-159">9</span><span class="sxs-lookup"><span data-stu-id="caeba-159">9</span></span>|<span data-ttu-id="caeba-160">67</span><span class="sxs-lookup"><span data-stu-id="caeba-160">67</span></span>|  
    ||<span data-ttu-id="caeba-161">Logs_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="caeba-161">Logs_TempDb_3</span></span>|<span data-ttu-id="caeba-162">TEMPDB、 MASTER、 MSDB、 BizTalkDTADb、 BizTalkMgmtDb、 ENTSSO 和 BizTalkRuleEngineDb 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="caeba-162">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb transaction log files</span></span>|<span data-ttu-id="caeba-163">10</span><span class="sxs-lookup"><span data-stu-id="caeba-163">10</span></span>|<span data-ttu-id="caeba-164">67</span><span class="sxs-lookup"><span data-stu-id="caeba-164">67</span></span>|  
  
-   <span data-ttu-id="caeba-165">**BizTalk 主机设计和每个主机和其实例的说明。**</span><span class="sxs-lookup"><span data-stu-id="caeba-165">**BizTalk Host design and descriptions of each host and their instances.**</span></span>  
  
-   <span data-ttu-id="caeba-166">**每个业务流程的说明。**</span><span class="sxs-lookup"><span data-stu-id="caeba-166">**Description of each orchestration.**</span></span>  
  
-   <span data-ttu-id="caeba-167">**每个管道的说明。**</span><span class="sxs-lookup"><span data-stu-id="caeba-167">**Description of each pipeline.**</span></span>  
  
-   <span data-ttu-id="caeba-168">**自定义组件，如.NET 程序集和 COM + 组件的说明。**</span><span class="sxs-lookup"><span data-stu-id="caeba-168">**Description of custom components such as .NET assemblies and COM+ components.**</span></span>  
  
## <a name="detailed-architecture-diagram"></a><span data-ttu-id="caeba-169">详细的体系结构关系图</span><span class="sxs-lookup"><span data-stu-id="caeba-169">Detailed architecture diagram</span></span>  
 <span data-ttu-id="caeba-170">下图说明了可用于性能评估体系结构关系图。</span><span class="sxs-lookup"><span data-stu-id="caeba-170">The following diagram illustrates an architecture diagram that could be used for a performance assessment.</span></span>  
  
 <span data-ttu-id="caeba-171">![BizTalk 体系结构关系图](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span><span class="sxs-lookup"><span data-stu-id="caeba-171">![BizTalk Architecture Diagram](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span></span>  
<span data-ttu-id="caeba-172">BizTalk 体系结构关系图</span><span class="sxs-lookup"><span data-stu-id="caeba-172">BizTalk Architecture Diagram</span></span>  
  
## <a name="message-flow-diagrams"></a><span data-ttu-id="caeba-173">消息流关系图</span><span class="sxs-lookup"><span data-stu-id="caeba-173">Message flow diagrams</span></span>  
 <span data-ttu-id="caeba-174">创建详细的消息流关系图，以帮助防止混淆或 false 的假设有关什么是应发生了状况消息处理过程。</span><span class="sxs-lookup"><span data-stu-id="caeba-174">Create detailed message flow diagrams to help prevent confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span>  
  
 <span data-ttu-id="caeba-175">时全面考虑 BizTalk 解决方案，我们倾向于将整个系统的消息流。</span><span class="sxs-lookup"><span data-stu-id="caeba-175">When thinking about a BizTalk solution holistically, we tend to think of the message flow through the system.</span></span> <span data-ttu-id="caeba-176">执行性能测试，因为流的所有部分必须都视为潜在的瓶颈时，此消息流角度来看是尤为重要。</span><span class="sxs-lookup"><span data-stu-id="caeba-176">This Message Flow perspective is especially important when doing performance testing because all parts of the flow must be considered as potential bottlenecks.</span></span> <span data-ttu-id="caeba-177">具有消息流关系图是为了防止任何混淆或错误的假设有关什么是应发生了状况消息在每个测试期间运行。</span><span class="sxs-lookup"><span data-stu-id="caeba-177">Having a message flow diagram prevents any confusion or false assumptions regarding what is supposed to be happening to messages during each test run.</span></span>  
  
 <span data-ttu-id="caeba-178">在以下示例中，创建使用简单的 Visio 形状，而不考虑背景项目中的每个人都可以快速了解到系统获取一条消息的方式、 解决方案的哪些部分进行交互并显示消息，以及最后其中消息进入后正在处理。</span><span class="sxs-lookup"><span data-stu-id="caeba-178">In the following example, created using simple Visio shapes, everyone on the project regardless of background can quickly understand how a message gets into the system, what parts of the solutions interact with the message, and finally where the message lands after processing.</span></span>  
  
 <span data-ttu-id="caeba-179">![消息流关系图](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span><span class="sxs-lookup"><span data-stu-id="caeba-179">![Message Flow Diagram](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span></span>  
<span data-ttu-id="caeba-180">消息流关系图</span><span class="sxs-lookup"><span data-stu-id="caeba-180">Message Flow Diagram</span></span>  
  
 <span data-ttu-id="caeba-181">创建消息流关系图时，应考虑以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="caeba-181">The following details should be considered when creating the message flow diagrams:</span></span>  
  
-   <span data-ttu-id="caeba-182">介绍了每种类型的消息的时间之前生成的所有消息都发送和已完成所有相关的处理到达的接收位置的生命周期。</span><span class="sxs-lookup"><span data-stu-id="caeba-182">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
-   <span data-ttu-id="caeba-183">描述如何处理更改的错误情况。</span><span class="sxs-lookup"><span data-stu-id="caeba-183">Describe how processing changes for error conditions.</span></span>  
  
-   <span data-ttu-id="caeba-184">包括有关相关、 送达通知和确认详细信息。</span><span class="sxs-lookup"><span data-stu-id="caeba-184">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
-   <span data-ttu-id="caeba-185">包括有关依赖于外部系统的详细信息。</span><span class="sxs-lookup"><span data-stu-id="caeba-185">Include details about dependence on external systems.</span></span>  
  
-   <span data-ttu-id="caeba-186">包括有关延迟和吞吐量的性能要求信息。</span><span class="sxs-lookup"><span data-stu-id="caeba-186">Include performance requirement information regarding latency and throughput.</span></span>  
  
## <a name="third-party-software-details"></a><span data-ttu-id="caeba-187">第三方软件的详细信息</span><span class="sxs-lookup"><span data-stu-id="caeba-187">Third-party software details</span></span>  
 <span data-ttu-id="caeba-188">使用的所有非 Microsoft 软件应完整记录详细的解决方案设计的一部分。</span><span class="sxs-lookup"><span data-stu-id="caeba-188">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
## <a name="detailed-lab-hardware-stack"></a><span data-ttu-id="caeba-189">详细的实验室硬件堆栈</span><span class="sxs-lookup"><span data-stu-id="caeba-189">Detailed lab hardware stack</span></span>  
 <span data-ttu-id="caeba-190">构建在以前创建的高级硬件关系图上，下列硬件信息应完整记录：</span><span class="sxs-lookup"><span data-stu-id="caeba-190">Building on the previously created high-level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
-   <span data-ttu-id="caeba-191">Processors</span><span class="sxs-lookup"><span data-stu-id="caeba-191">Processors</span></span>  
  
    -   <span data-ttu-id="caeba-192">类型</span><span class="sxs-lookup"><span data-stu-id="caeba-192">Type</span></span>  
  
    -   <span data-ttu-id="caeba-193">速度</span><span class="sxs-lookup"><span data-stu-id="caeba-193">Speed</span></span>  
  
    -   <span data-ttu-id="caeba-194">核心数</span><span class="sxs-lookup"><span data-stu-id="caeba-194">Number of cores</span></span>  
  
    -   <span data-ttu-id="caeba-195">超线程</span><span class="sxs-lookup"><span data-stu-id="caeba-195">Hyperthreading</span></span>  
  
-   <span data-ttu-id="caeba-196">内存</span><span class="sxs-lookup"><span data-stu-id="caeba-196">Memory</span></span>  
  
    -   <span data-ttu-id="caeba-197">Amount</span><span class="sxs-lookup"><span data-stu-id="caeba-197">Amount</span></span>  
  
    -   <span data-ttu-id="caeba-198">速度</span><span class="sxs-lookup"><span data-stu-id="caeba-198">Speed</span></span>  
  
    -   <span data-ttu-id="caeba-199">奇偶校验</span><span class="sxs-lookup"><span data-stu-id="caeba-199">Parity</span></span>  
  
-   <span data-ttu-id="caeba-200">网络</span><span class="sxs-lookup"><span data-stu-id="caeba-200">Network</span></span>  
  
    -   <span data-ttu-id="caeba-201">网络接口卡 (Nic) 的数量</span><span class="sxs-lookup"><span data-stu-id="caeba-201">Number of network interface cards (NICs)</span></span>  
  
    -   <span data-ttu-id="caeba-202">网络的速度</span><span class="sxs-lookup"><span data-stu-id="caeba-202">Speed of network</span></span>  
  
-   <span data-ttu-id="caeba-203">SAN</span><span class="sxs-lookup"><span data-stu-id="caeba-203">SAN</span></span>  
  
    -   <span data-ttu-id="caeba-204">在每台计算机中的 SAN 卡数</span><span class="sxs-lookup"><span data-stu-id="caeba-204">Number of SAN cards in each computer</span></span>  
  
    -   <span data-ttu-id="caeba-205">每个计算机和目的，每个 LUN 的逻辑单元号 (Lun) 的数量</span><span class="sxs-lookup"><span data-stu-id="caeba-205">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
    -   <span data-ttu-id="caeba-206">速度存储区域网络 (SAN) 卡</span><span class="sxs-lookup"><span data-stu-id="caeba-206">Speed of storage area network (SAN) Cards</span></span>  
  
    -   <span data-ttu-id="caeba-207">SAN 卡配置详细信息</span><span class="sxs-lookup"><span data-stu-id="caeba-207">SAN card configuration details</span></span>  
  
    -   <span data-ttu-id="caeba-208">SAN 磁盘分配，格式化和分区</span><span class="sxs-lookup"><span data-stu-id="caeba-208">SAN disk allocation, formatting, and partitioning</span></span>  
  
-   <span data-ttu-id="caeba-209">磁盘</span><span class="sxs-lookup"><span data-stu-id="caeba-209">Disk</span></span>  
  
    -   <span data-ttu-id="caeba-210">每台计算机的的本地磁盘详细信息</span><span class="sxs-lookup"><span data-stu-id="caeba-210">Local disk details for each computer</span></span>  
  
    -   <span data-ttu-id="caeba-211">格式设置为本地磁盘使用</span><span class="sxs-lookup"><span data-stu-id="caeba-211">Formatting used for local disks</span></span>  
  
    -   <span data-ttu-id="caeba-212">分区的本地磁盘的详细信息</span><span class="sxs-lookup"><span data-stu-id="caeba-212">Partitioning details for local disks</span></span>  
  
-   <span data-ttu-id="caeba-213">Cache</span><span class="sxs-lookup"><span data-stu-id="caeba-213">Cache</span></span>  
  
    -   <span data-ttu-id="caeba-214">L2 缓存量</span><span class="sxs-lookup"><span data-stu-id="caeba-214">L2 Cache amount</span></span>  
  
    -   <span data-ttu-id="caeba-215">L3 缓存量</span><span class="sxs-lookup"><span data-stu-id="caeba-215">L3 Cache amount</span></span>  
  
## <a name="detailed-lab-software-stack"></a><span data-ttu-id="caeba-216">详细的实验室软件堆栈</span><span class="sxs-lookup"><span data-stu-id="caeba-216">Detailed lab software stack</span></span>  
 <span data-ttu-id="caeba-217">应记录以下的软件信息：</span><span class="sxs-lookup"><span data-stu-id="caeba-217">The following software information should be documented:</span></span>  
  
-   <span data-ttu-id="caeba-218">特定操作系统版本、 版本和体系结构</span><span class="sxs-lookup"><span data-stu-id="caeba-218">Specific operating system versions, editions, and architecture</span></span>  
  
-   <span data-ttu-id="caeba-219">特定的操作系统功能</span><span class="sxs-lookup"><span data-stu-id="caeba-219">Specific operating system features</span></span>  
  
-   <span data-ttu-id="caeba-220">在每台计算机上安装的特定软件</span><span class="sxs-lookup"><span data-stu-id="caeba-220">Specific software installed on each computer</span></span>  
  
-   <span data-ttu-id="caeba-221">特定驱动程序</span><span class="sxs-lookup"><span data-stu-id="caeba-221">Specific drivers</span></span>  
  
-   <span data-ttu-id="caeba-222">Service Pack 和其他更新</span><span class="sxs-lookup"><span data-stu-id="caeba-222">Service Packs and other updates</span></span>  
  
-   <span data-ttu-id="caeba-223">如果它们不同默认值，则使用的所有软件和操作系统功能的配置值</span><span class="sxs-lookup"><span data-stu-id="caeba-223">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caeba-224">请参阅</span><span class="sxs-lookup"><span data-stu-id="caeba-224">See Also</span></span>  
 [<span data-ttu-id="caeba-225">性能评估阶段</span><span class="sxs-lookup"><span data-stu-id="caeba-225">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)