---
title: 阶段 4:构建评估环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b9829591af749f5e253cc7873af4ab114af542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249647"
---
# <a name="phase-4-building-the-assessment-environment"></a><span data-ttu-id="ec007-102">阶段 4:构建评估环境</span><span class="sxs-lookup"><span data-stu-id="ec007-102">Phase 4: Building the Assessment Environment</span></span>
<span data-ttu-id="ec007-103">性能评估的生成实验室阶段用于安装的硬件和软件环境中符合在前几个阶段中所做的设计决策。</span><span class="sxs-lookup"><span data-stu-id="ec007-103">The Build lab phase of a performance assessment is used to install the hardware and software for the environment in conformance to the design decisions made in previous phases.</span></span> <span data-ttu-id="ec007-104">生成实验室阶段可能会非常耗时，因为它不是异常这一阶段重叠较早阶段。</span><span class="sxs-lookup"><span data-stu-id="ec007-104">Because the Build lab phase can be time consuming, it is not unusual for this phase to overlap earlier phases.</span></span> <span data-ttu-id="ec007-105">在许多情况下，硬件和操作系统可能会安装之前的最终决策进行有关应用程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="ec007-105">In many scenarios, the hardware and operating system may be installed before a final decision has been made as to the application architecture.</span></span> <span data-ttu-id="ec007-106">性能评估的生成实验室阶段通常包括本主题中讨论的任务。</span><span class="sxs-lookup"><span data-stu-id="ec007-106">The Build lab phase of a performance assessment typically includes the tasks discussed in this topic.</span></span>  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a><span data-ttu-id="ec007-107">获取实验室开始日期之前至少一周的所有生成实验室基础结构</span><span class="sxs-lookup"><span data-stu-id="ec007-107">Obtain all build-lab infrastructure at least a week in advance of the lab start date</span></span>  
 <span data-ttu-id="ec007-108">实验室开始日期之前一周至少具有可用的所需的硬件和软件的所有计划。</span><span class="sxs-lookup"><span data-stu-id="ec007-108">Plan to have available all of the required hardware and software at least a week before the lab start date.</span></span> <span data-ttu-id="ec007-109">这将确保不浪费宝贵的实验室时间而进行的所需基础结构。</span><span class="sxs-lookup"><span data-stu-id="ec007-109">This will ensure that valuable lab time is not wasted for want of the required infrastructure.</span></span>  
  
## <a name="configure-third-party-software-systems"></a><span data-ttu-id="ec007-110">配置第三方软件系统</span><span class="sxs-lookup"><span data-stu-id="ec007-110">Configure third-party software systems</span></span>  
 <span data-ttu-id="ec007-111">可能需要进行构建和配置实验室可以开始之前的第三方系统。</span><span class="sxs-lookup"><span data-stu-id="ec007-111">There may be third-party systems that need to be built out and configured before the lab can begin.</span></span> <span data-ttu-id="ec007-112">如果主题事项专家 (Sme) 所需的这些系统，请确保计划生成扩展和实验室执行阶段。</span><span class="sxs-lookup"><span data-stu-id="ec007-112">If subject matter experts (SMEs) are required for these systems, be sure they are scheduled during the build-out and lab execution stages.</span></span> <span data-ttu-id="ec007-113">请确保它们详尽地记录其生成扩展过程。</span><span class="sxs-lookup"><span data-stu-id="ec007-113">Ensure that they thoroughly document their build-out procedures.</span></span>  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a><span data-ttu-id="ec007-114">安装和配置 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="ec007-114">Install and configure the BizTalk Server environment</span></span>  
 <span data-ttu-id="ec007-115">中的详细的说明安装 BizTalk Server 和必需的依赖关系软件[安装和升级指南](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="ec007-115">Detailed instructions for installing BizTalk Server and the required dependency software are in the [Installation and Upgrade Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="ec007-116">后已成功安装和配置 BizTalk Server 环境，需要完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="ec007-116">After successfully installing and configuring the BizTalk Server environment, complete the following tasks:</span></span>  
  
-   <span data-ttu-id="ec007-117">请按照中列出的建议[操作准备就绪清单](operational-readiness-checklists.md)</span><span class="sxs-lookup"><span data-stu-id="ec007-117">Follow the recommendations listed in the [Operational Readiness Checklists](operational-readiness-checklists.md)</span></span>
  
-   <span data-ttu-id="ec007-118">请按照中的建议[优化性能](../technical-guides/optimizing-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="ec007-118">Follow the recommendations in [Optimizing Performance](../technical-guides/optimizing-performance.md).</span></span>  
  
-   <span data-ttu-id="ec007-119">请确保正确同步所有计算机的时间。</span><span class="sxs-lookup"><span data-stu-id="ec007-119">Ensure all computer times are properly synchronized.</span></span>  
  
-   <span data-ttu-id="ec007-120">验证在环境中的所有计算机之间的 MSDTC 功能。</span><span class="sxs-lookup"><span data-stu-id="ec007-120">Verify MSDTC functionality between all computers in the environment.</span></span>  
  
-   <span data-ttu-id="ec007-121">请确保任何自定义跟踪/日志记录已禁用，除非绝对必要。</span><span class="sxs-lookup"><span data-stu-id="ec007-121">Ensure any custom tracing/logging is disabled unless absolutely needed.</span></span>  
  
-   <span data-ttu-id="ec007-122">安装 Visual Studio 旗舰版中的负载测试。</span><span class="sxs-lookup"><span data-stu-id="ec007-122">Install the Visual Studio Ultimate edition for load testing.</span></span>  <span data-ttu-id="ec007-123">有关如何执行自动测试使用 Visual Studio 的详细信息，请参阅[促进自动测试使用 Visual Studio](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="ec007-123">For more information about how to perform automated testing using Visual Studio, see [Using Visual Studio to Facilitate Automated Testing](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).</span></span>  
  
-   <span data-ttu-id="ec007-124">根据需要设置性能监视器计数器和日志。</span><span class="sxs-lookup"><span data-stu-id="ec007-124">Setup Performance Monitor counters and logs, as needed.</span></span>  
  
-   <span data-ttu-id="ec007-125">安装程序的调试的计算机，如果性能评估作用域内的代码更改调试解决方案。</span><span class="sxs-lookup"><span data-stu-id="ec007-125">Setup a debugging computer to debug the solution if code changes are within the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="ec007-126">对所有硬盘进行碎片都整理。</span><span class="sxs-lookup"><span data-stu-id="ec007-126">Defragment all hard drives.</span></span>  
  
-   <span data-ttu-id="ec007-127">禁用防病毒实时扫描。</span><span class="sxs-lookup"><span data-stu-id="ec007-127">Disable antivirus real time scanning.</span></span>  
  
-   <span data-ttu-id="ec007-128">备份企业单一登录主密钥。</span><span class="sxs-lookup"><span data-stu-id="ec007-128">Back up the Enterprise Single Sign-On Master Secret.</span></span>  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a><span data-ttu-id="ec007-129">安装 BizTalk Server 应用程序进行测试</span><span class="sxs-lookup"><span data-stu-id="ec007-129">Install the BizTalk Server application to be tested</span></span>  
 <span data-ttu-id="ec007-130">要进行测试的应用程序的安装通常包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ec007-130">Installation of the application to be tested will typically include the following steps:</span></span>  
  
1.  <span data-ttu-id="ec007-131">使用 BizTalk Server 管理控制台来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec007-131">Use the BizTalk Server Administration console to do the following:</span></span>  
  
    -   <span data-ttu-id="ec007-132">创建主机</span><span class="sxs-lookup"><span data-stu-id="ec007-132">Create Hosts</span></span>  
  
    -   <span data-ttu-id="ec007-133">创建发送/接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="ec007-133">Create Send/Receive Handlers.</span></span>  
  
    -   <span data-ttu-id="ec007-134">创建主机实例。</span><span class="sxs-lookup"><span data-stu-id="ec007-134">Create Host instances.</span></span>  
  
    -   <span data-ttu-id="ec007-135">创建 BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec007-135">Create BizTalk Server Applications.</span></span>  
  
2.  <span data-ttu-id="ec007-136">应用程序安装：</span><span class="sxs-lookup"><span data-stu-id="ec007-136">Application installation:</span></span>  
  
    1.  <span data-ttu-id="ec007-137">将 BizTalk Server 二进制文件部署到 BizTalk Server 组。</span><span class="sxs-lookup"><span data-stu-id="ec007-137">Deploy BizTalk Server binaries to the BizTalk Server group.</span></span>  
  
    2.  <span data-ttu-id="ec007-138">绑定导入到 BizTalk Server 组。</span><span class="sxs-lookup"><span data-stu-id="ec007-138">Import bindings to the BizTalk Server group.</span></span>  
  
    3.  <span data-ttu-id="ec007-139">所有框上的 gac 中 BizTalk Server 和 BizTalk Server 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ec007-139">GAC BizTalk Server and non-BizTalk Server binaries on all boxes.</span></span>  
  
    4.  <span data-ttu-id="ec007-140">请确保在所有框上存在依存关系组件。</span><span class="sxs-lookup"><span data-stu-id="ec007-140">Ensure dependency components exist on all boxes.</span></span>  
  
3.  <span data-ttu-id="ec007-141">安装依赖应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec007-141">Install dependency applications.</span></span>  
  
4.  <span data-ttu-id="ec007-142">在 BizTalk Server 管理控制台中配置的传输和物理终结点。</span><span class="sxs-lookup"><span data-stu-id="ec007-142">Configure transports and physical endpoints in the BizTalk Server Administration console.</span></span>  
  
5.  <span data-ttu-id="ec007-143">启动服务。</span><span class="sxs-lookup"><span data-stu-id="ec007-143">Start services.</span></span>  
  
6.  <span data-ttu-id="ec007-144">执行基本冒烟测试-测试你的解决方案的基本功能的端到端功能测试执行冒烟测试。</span><span class="sxs-lookup"><span data-stu-id="ec007-144">Perform basic smoke tests – Smoke tests are end-to-end functional tests that test the basic functionality of your solution.</span></span>  
  
## <a name="implement-automated-build-and-load-testing"></a><span data-ttu-id="ec007-145">实施自动生成和负载测试</span><span class="sxs-lookup"><span data-stu-id="ec007-145">Implement automated build and load testing</span></span>  
 <span data-ttu-id="ec007-146">自动的生成和负载测试过程的实现可以说是 BizTalk Server 性能评估的基础。</span><span class="sxs-lookup"><span data-stu-id="ec007-146">Implementation of an automated build and load testing process is arguably the cornerstone of a BizTalk Server performance assessment.</span></span> <span data-ttu-id="ec007-147">如果性能评估作用域内的代码更改，则应实现自动的生成过程。</span><span class="sxs-lookup"><span data-stu-id="ec007-147">An automated build process should be implemented if code changes are within the scope of the performance assessment.</span></span> <span data-ttu-id="ec007-148">应为所有负载测试方案实现自动化的负载测试。</span><span class="sxs-lookup"><span data-stu-id="ec007-148">Automated load testing should be implemented for all load testing scenarios.</span></span> <span data-ttu-id="ec007-149">若要实现自动的生成和负载测试所需的初始时间投资快速得到了补偿，自动化可容纳的受到人为错误的常见生成/测试任务的快速而精确地重复。</span><span class="sxs-lookup"><span data-stu-id="ec007-149">The initial time investment required to implement automated build and load testing is quickly recouped, automation accommodates rapid and precise repetition of mundane build/testing tasks that are subject to human error.</span></span> <span data-ttu-id="ec007-150">有关实现自动化的生成和测试过程的详细信息，请参阅[实现自动化测试](../technical-guides/implementing-automated-testing.md)本指南中。</span><span class="sxs-lookup"><span data-stu-id="ec007-150">For more information about implementing an automated build and testing process, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md) in this guide.</span></span>  
  
## <a name="configure-performance-monitoring"></a><span data-ttu-id="ec007-151">配置性能监视</span><span class="sxs-lookup"><span data-stu-id="ec007-151">Configure performance monitoring</span></span>  
 <span data-ttu-id="ec007-152">准确的性能监视对性能评估的成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="ec007-152">Accurate performance monitoring is critical to the success of the performance assessment.</span></span> <span data-ttu-id="ec007-153">确定应计算哪些性能度量值根据在审视阶段中定义的吞吐量和延迟目标。</span><span class="sxs-lookup"><span data-stu-id="ec007-153">Determine which performance metrics should be evaluated based on the throughput and latency goals that were defined in the Scope phase.</span></span> <span data-ttu-id="ec007-154">在 BizTalk Server 环境中的每台计算机上，应执行性能监视。</span><span class="sxs-lookup"><span data-stu-id="ec007-154">Performance monitoring should be performed on each computer in the BizTalk Server environment.</span></span> <span data-ttu-id="ec007-155">请参阅[性能计数器](../core/performance-counters.md)。</span><span class="sxs-lookup"><span data-stu-id="ec007-155">See [Performance Counters](../core/performance-counters.md).</span></span> <span data-ttu-id="ec007-156">使用日志的性能分析工具 (PAL) 来生成 HTML 报告，以图形方式图表重要的性能计数器和超出这些计数器的阈值时生成警报。</span><span class="sxs-lookup"><span data-stu-id="ec007-156">Use the Performance Analysis of Logs tool (PAL) to generate HTML reports that graphically chart important performance counters and generate alerts when thresholds for these counters are exceeded.</span></span> <span data-ttu-id="ec007-157">S[性能分析的日志 (PAL) 工具](https://github.com/clinthuffman/PAL)。</span><span class="sxs-lookup"><span data-stu-id="ec007-157">S [Performance Analysis of Logs (PAL) tool](https://github.com/clinthuffman/PAL).</span></span>  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a><span data-ttu-id="ec007-158">建立和记录解决方案的基线性能</span><span class="sxs-lookup"><span data-stu-id="ec007-158">Establish and document the solution’s baseline performance</span></span>  
 <span data-ttu-id="ec007-159">应计算基准性能，以便可以测量性能评估过程中应用的性能优化的效果。</span><span class="sxs-lookup"><span data-stu-id="ec007-159">Baseline performance should be calculated so that the effect of performance optimizations applied during the performance assessment can be measured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec007-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec007-160">See Also</span></span>  
 [<span data-ttu-id="ec007-161">性能评估阶段</span><span class="sxs-lookup"><span data-stu-id="ec007-161">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)