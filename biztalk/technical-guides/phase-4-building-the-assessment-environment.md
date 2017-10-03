---
title: "阶段 4： 构建评估环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8246ccd34d36f42bf9d8013baf8b73d557fae6eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="phase-4-building-the-assessment-environment"></a><span data-ttu-id="1071f-102">阶段 4： 构建评估环境</span><span class="sxs-lookup"><span data-stu-id="1071f-102">Phase 4: Building the Assessment Environment</span></span>
<span data-ttu-id="1071f-103">性能评估的生成实验室阶段用于安装的硬件和软件的环境中符合在前几个阶段中做出的设计决策。</span><span class="sxs-lookup"><span data-stu-id="1071f-103">The Build lab phase of a performance assessment is used to install the hardware and software for the environment in conformance to the design decisions made in previous phases.</span></span> <span data-ttu-id="1071f-104">在生成实验室阶段可能会非常耗时，因为它不是异常这一阶段重叠早期阶段。</span><span class="sxs-lookup"><span data-stu-id="1071f-104">Because the Build lab phase can be time consuming, it is not unusual for this phase to overlap earlier phases.</span></span> <span data-ttu-id="1071f-105">在许多情况下，硬件和操作系统可能安装之前应用程序体系结构并做出最终的决策。</span><span class="sxs-lookup"><span data-stu-id="1071f-105">In many scenarios, the hardware and operating system may be installed before a final decision has been made as to the application architecture.</span></span> <span data-ttu-id="1071f-106">性能评估的生成实验室阶段通常包括本主题中讨论的任务。</span><span class="sxs-lookup"><span data-stu-id="1071f-106">The Build lab phase of a performance assessment typically includes the tasks discussed in this topic.</span></span>  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a><span data-ttu-id="1071f-107">获取实验室开始日期之前至少一周的所有生成实验室基础设施</span><span class="sxs-lookup"><span data-stu-id="1071f-107">Obtain all build-lab infrastructure at least a week in advance of the lab start date</span></span>  
 <span data-ttu-id="1071f-108">实验室开始日期一周至少具有可用的所需的硬件和软件的所有计划。</span><span class="sxs-lookup"><span data-stu-id="1071f-108">Plan to have available all of the required hardware and software at least a week before the lab start date.</span></span> <span data-ttu-id="1071f-109">这将确保不会进行必需的基础结构的浪费有价值的实验室时间。</span><span class="sxs-lookup"><span data-stu-id="1071f-109">This will ensure that valuable lab time is not wasted for want of the required infrastructure.</span></span>  
  
## <a name="configure-third-party-software-systems"></a><span data-ttu-id="1071f-110">配置第三方软件系统</span><span class="sxs-lookup"><span data-stu-id="1071f-110">Configure third-party software systems</span></span>  
 <span data-ttu-id="1071f-111">可能需要构建和配置实验室可以开始之前的第三方系统。</span><span class="sxs-lookup"><span data-stu-id="1071f-111">There may be third-party systems that need to be built out and configured before the lab can begin.</span></span> <span data-ttu-id="1071f-112">如果行业专家 (Sme) 所需的这些系统，请确保计划在构建和实验室执行阶段。</span><span class="sxs-lookup"><span data-stu-id="1071f-112">If subject matter experts (SMEs) are required for these systems, be sure they are scheduled during the build-out and lab execution stages.</span></span> <span data-ttu-id="1071f-113">请确保它们全面记录其生成扩展过程。</span><span class="sxs-lookup"><span data-stu-id="1071f-113">Ensure that they thoroughly document their build-out procedures.</span></span>  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a><span data-ttu-id="1071f-114">安装和配置 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="1071f-114">Install and configure the BizTalk Server environment</span></span>  
 <span data-ttu-id="1071f-115">有关安装详细说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和在找不到必需的依赖关系软件[BizTalk Server 2010 安装和升级指南](http://go.microsoft.com/fwlink/?LinkID=191321)(http://go.microsoft.com/fwlink/?LinkID=191321)。</span><span class="sxs-lookup"><span data-stu-id="1071f-115">Detailed instructions for installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the required dependency software can be found in the [BizTalk Server 2010 Installation and Upgrade Guides](http://go.microsoft.com/fwlink/?LinkID=191321) (http://go.microsoft.com/fwlink/?LinkID=191321).</span></span> <span data-ttu-id="1071f-116">已成功安装后，配置 BizTalk Server 环境，完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="1071f-116">After successfully installing and configuring the BizTalk Server environment, complete the following tasks:</span></span>  
  
-   <span data-ttu-id="1071f-117">请遵循中列出的建议[操作的准备情况清单](http://go.microsoft.com/fwlink/?LinkId=160134)(http://go.microsoft.com/fwlink/?LinkId=160134)。</span><span class="sxs-lookup"><span data-stu-id="1071f-117">Follow the recommendations listed in the [Operational Readiness Checklists](http://go.microsoft.com/fwlink/?LinkId=160134)(http://go.microsoft.com/fwlink/?LinkId=160134).</span></span>  
  
-   <span data-ttu-id="1071f-118">请按照中的建议[优化性能](../technical-guides/optimizing-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="1071f-118">Follow the recommendations in [Optimizing Performance](../technical-guides/optimizing-performance.md).</span></span>  
  
-   <span data-ttu-id="1071f-119">确保正确同步所有计算机的时间。</span><span class="sxs-lookup"><span data-stu-id="1071f-119">Ensure all computer times are properly synchronized.</span></span>  
  
-   <span data-ttu-id="1071f-120">验证在环境中的所有计算机之间的 MSDTC 功能。</span><span class="sxs-lookup"><span data-stu-id="1071f-120">Verify MSDTC functionality between all computers in the environment.</span></span>  
  
-   <span data-ttu-id="1071f-121">确保任何自定义跟踪/日志记录已禁用，除非绝对必要。</span><span class="sxs-lookup"><span data-stu-id="1071f-121">Ensure any custom tracing/logging is disabled unless absolutely needed.</span></span>  
  
-   <span data-ttu-id="1071f-122">安装用于负载测试的 Visual Studio 2010 Ultimate 版本。</span><span class="sxs-lookup"><span data-stu-id="1071f-122">Install the Visual Studio 2010 Ultimate edition for load testing.</span></span>  <span data-ttu-id="1071f-123">有关如何执行自动测试使用 Visual Studio 的详细信息，请参阅[促进自动测试使用 Visual Studio](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="1071f-123">For more information about how to perform automated testing using Visual Studio, see [Using Visual Studio to Facilitate Automated Testing](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).</span></span>  
  
-   <span data-ttu-id="1071f-124">根据需要设置性能监视器计数器和日志。</span><span class="sxs-lookup"><span data-stu-id="1071f-124">Setup Performance Monitor counters and logs, as needed.</span></span>  
  
-   <span data-ttu-id="1071f-125">安装程序的调试的计算机，如果代码更改性能评估作用域内调试解决方案。</span><span class="sxs-lookup"><span data-stu-id="1071f-125">Setup a debugging computer to debug the solution if code changes are within the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="1071f-126">对所有硬盘进行碎片都整理。</span><span class="sxs-lookup"><span data-stu-id="1071f-126">Defragment all hard drives.</span></span>  
  
-   <span data-ttu-id="1071f-127">禁用防病毒实时扫描。</span><span class="sxs-lookup"><span data-stu-id="1071f-127">Disable antivirus real time scanning.</span></span>  
  
-   <span data-ttu-id="1071f-128">备份企业单一登录的主密钥。</span><span class="sxs-lookup"><span data-stu-id="1071f-128">Back up the Enterprise Single Sign-On Master Secret.</span></span>  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a><span data-ttu-id="1071f-129">安装 BizTalk Server 应用程序以进行测试</span><span class="sxs-lookup"><span data-stu-id="1071f-129">Install the BizTalk Server application to be tested</span></span>  
 <span data-ttu-id="1071f-130">安装要测试此应用程序通常将包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1071f-130">Installation of the application to be tested will typically include the following steps:</span></span>  
  
1.  <span data-ttu-id="1071f-131">使用 BizTalk Server 管理控制台执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1071f-131">Use the BizTalk Server Administration console to do the following:</span></span>  
  
    -   <span data-ttu-id="1071f-132">创建主机</span><span class="sxs-lookup"><span data-stu-id="1071f-132">Create Hosts</span></span>  
  
    -   <span data-ttu-id="1071f-133">创建发送/接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="1071f-133">Create Send/Receive Handlers.</span></span>  
  
    -   <span data-ttu-id="1071f-134">创建主机实例。</span><span class="sxs-lookup"><span data-stu-id="1071f-134">Create Host instances.</span></span>  
  
    -   <span data-ttu-id="1071f-135">创建 BizTalk 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="1071f-135">Create BizTalk Server Applications.</span></span>  
  
2.  <span data-ttu-id="1071f-136">应用程序安装：</span><span class="sxs-lookup"><span data-stu-id="1071f-136">Application installation:</span></span>  
  
    1.  <span data-ttu-id="1071f-137">将 BizTalk Server 二进制文件部署到 BizTalk Server 组。</span><span class="sxs-lookup"><span data-stu-id="1071f-137">Deploy BizTalk Server binaries to the BizTalk Server group.</span></span>  
  
    2.  <span data-ttu-id="1071f-138">导入的绑定到 BizTalk Server 组。</span><span class="sxs-lookup"><span data-stu-id="1071f-138">Import bindings to the BizTalk Server group.</span></span>  
  
    3.  <span data-ttu-id="1071f-139">在所有框上的 GAC BizTalk Server 和 BizTalk Server 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="1071f-139">GAC BizTalk Server and non-BizTalk Server binaries on all boxes.</span></span>  
  
    4.  <span data-ttu-id="1071f-140">确保在所有框上存在依赖组件。</span><span class="sxs-lookup"><span data-stu-id="1071f-140">Ensure dependency components exist on all boxes.</span></span>  
  
3.  <span data-ttu-id="1071f-141">安装依赖项应用程序。</span><span class="sxs-lookup"><span data-stu-id="1071f-141">Install dependency applications.</span></span>  
  
4.  <span data-ttu-id="1071f-142">BizTalk Server 管理控制台中配置传输和物理终结点。</span><span class="sxs-lookup"><span data-stu-id="1071f-142">Configure transports and physical endpoints in the BizTalk Server Administration console.</span></span>  
  
5.  <span data-ttu-id="1071f-143">启动服务。</span><span class="sxs-lookup"><span data-stu-id="1071f-143">Start services.</span></span>  
  
6.  <span data-ttu-id="1071f-144">执行基本冒烟测试-冒烟测试端到端测试你的解决方案的基本功能的功能测试。</span><span class="sxs-lookup"><span data-stu-id="1071f-144">Perform basic smoke tests – Smoke tests are end-to-end functional tests that test the basic functionality of your solution.</span></span>  
  
## <a name="implement-automated-build-and-load-testing"></a><span data-ttu-id="1071f-145">实现自动生成和负载测试</span><span class="sxs-lookup"><span data-stu-id="1071f-145">Implement automated build and load testing</span></span>  
 <span data-ttu-id="1071f-146">自动的生成和负载测试过程的实现说是将 BizTalk Server 性能评估的基础。</span><span class="sxs-lookup"><span data-stu-id="1071f-146">Implementation of an automated build and load testing process is arguably the cornerstone of a BizTalk Server performance assessment.</span></span> <span data-ttu-id="1071f-147">如果代码更改性能评估作用域内，则应实现自动的生成过程。</span><span class="sxs-lookup"><span data-stu-id="1071f-147">An automated build process should be implemented if code changes are within the scope of the performance assessment.</span></span> <span data-ttu-id="1071f-148">应为所有负载测试方案实现自动化的负载测试。</span><span class="sxs-lookup"><span data-stu-id="1071f-148">Automated load testing should be implemented for all load testing scenarios.</span></span> <span data-ttu-id="1071f-149">实现自动的生成和负载测试所需的初始时间投资快速而得到了弥补，自动化还包含的受到人为错误的繁琐的生成/测试任务的快速而精确地重复。</span><span class="sxs-lookup"><span data-stu-id="1071f-149">The initial time investment required to implement automated build and load testing is quickly recouped, automation accommodates rapid and precise repetition of mundane build/testing tasks that are subject to human error.</span></span> <span data-ttu-id="1071f-150">有关实现自动化的生成和测试过程的详细信息，请参阅[实现自动化测试](../technical-guides/implementing-automated-testing.md)本指南中。</span><span class="sxs-lookup"><span data-stu-id="1071f-150">For more information about implementing an automated build and testing process, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md) in this guide.</span></span>  
  
## <a name="configure-performance-monitoring"></a><span data-ttu-id="1071f-151">配置性能监视</span><span class="sxs-lookup"><span data-stu-id="1071f-151">Configure performance monitoring</span></span>  
 <span data-ttu-id="1071f-152">准确的性能监视对性能评估的成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="1071f-152">Accurate performance monitoring is critical to the success of the performance assessment.</span></span> <span data-ttu-id="1071f-153">确定应计算哪些性能度量值根据在审视阶段中定义的吞吐量和延迟目标。</span><span class="sxs-lookup"><span data-stu-id="1071f-153">Determine which performance metrics should be evaluated based on the throughput and latency goals that were defined in the Scope phase.</span></span> <span data-ttu-id="1071f-154">在 BizTalk Server 环境中的每台计算机上，应执行性能监视。</span><span class="sxs-lookup"><span data-stu-id="1071f-154">Performance monitoring should be performed on each computer in the BizTalk Server environment.</span></span> <span data-ttu-id="1071f-155">有关可用于 BizTalk Server 2010 的性能计数器的详细信息，请参阅[性能计数器](http://go.microsoft.com/fwlink/?LinkID=157269)(http://go.microsoft.com/fwlink/?LinkID=157269) 在 BizTalk Server 2010 帮助中。</span><span class="sxs-lookup"><span data-stu-id="1071f-155">For more information about the performance counters available for BizTalk Server 2010, see [Performance Counters](http://go.microsoft.com/fwlink/?LinkID=157269) (http://go.microsoft.com/fwlink/?LinkID=157269) in the BizTalk Server 2010 Help.</span></span> <span data-ttu-id="1071f-156">使用日志的性能分析工具 (PAL) 生成 HTML 报告，以图形方式图表重要的性能计数器和超出这些计数器的阈值时生成警报。</span><span class="sxs-lookup"><span data-stu-id="1071f-156">Use the Performance Analysis of Logs tool (PAL) to generate HTML reports that graphically chart important performance counters and generate alerts when thresholds for these counters are exceeded.</span></span> <span data-ttu-id="1071f-157">有关详细信息[性能分析的日志 (PAL) 工具](http://go.microsoft.com/fwlink/?LinkID=98098)，请参阅[性能分析的日志 (PAL) 工具](http://go.microsoft.com/fwlink/?LinkID=98098)(http://go.microsoft.com/fwlink/?LinkID=98098)。</span><span class="sxs-lookup"><span data-stu-id="1071f-157">For more information about the [Performance Analysis of Logs (PAL) tool](http://go.microsoft.com/fwlink/?LinkID=98098), see [Performance Analysis of Logs (PAL) tool](http://go.microsoft.com/fwlink/?LinkID=98098) (http://go.microsoft.com/fwlink/?LinkID=98098).</span></span>  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a><span data-ttu-id="1071f-158">建立和记录解决方案的基准性能</span><span class="sxs-lookup"><span data-stu-id="1071f-158">Establish and document the solution’s baseline performance</span></span>  
 <span data-ttu-id="1071f-159">应计算基线性能，以便可以测量性能评估期间应用的性能优化的效果。</span><span class="sxs-lookup"><span data-stu-id="1071f-159">Baseline performance should be calculated so that the effect of performance optimizations applied during the performance assessment can be measured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1071f-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1071f-160">See Also</span></span>  
 [<span data-ttu-id="1071f-161">性能评估阶段</span><span class="sxs-lookup"><span data-stu-id="1071f-161">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)