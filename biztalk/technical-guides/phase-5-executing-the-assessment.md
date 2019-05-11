---
title: 阶段 5:执行评估 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 332073502c1b2cc358e09ce7f50338321eb42bdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393467"
---
# <a name="phase-5-executing-the-assessment"></a><span data-ttu-id="75211-102">阶段 5:执行评估</span><span class="sxs-lookup"><span data-stu-id="75211-102">Phase 5: Executing the Assessment</span></span>
<span data-ttu-id="75211-103">执行阶段是通过自动的负载测试和其中性能瓶颈将发现并解决其中生成性能数据。</span><span class="sxs-lookup"><span data-stu-id="75211-103">The Execute phase is where the performance data is generated through automated load testing and where performance bottlenecks are discovered and addressed.</span></span> <span data-ttu-id="75211-104">此阶段都有一个迭代过程性能瓶颈，减少或消除通过测试，评估性能、 优化和重新测试。</span><span class="sxs-lookup"><span data-stu-id="75211-104">This phase has an iterative process whereby performance bottlenecks are reduced or eliminated by testing, evaluating performance, optimizing, and testing again.</span></span>  
  
 <span data-ttu-id="75211-105">本主题介绍在 BizTalk Server 性能评估的执行阶段期间通常遵循的步骤：</span><span class="sxs-lookup"><span data-stu-id="75211-105">This topic describes the steps that are typically followed during the Execute phase of a BizTalk Server performance assessment:</span></span>  
  
## <a name="step-1-run-automated-tests"></a><span data-ttu-id="75211-106">第 1 步：运行自动的测试</span><span class="sxs-lookup"><span data-stu-id="75211-106">Step 1: Run automated tests</span></span>  
 <span data-ttu-id="75211-107">运行自动的测试来开始执行阶段。</span><span class="sxs-lookup"><span data-stu-id="75211-107">Begin the Execute phase by running automated tests.</span></span> <span data-ttu-id="75211-108">通常，BizTalk Server 性能评估侧重于吞吐量和/或延迟测试，但可能包括生成验证和功能测试。</span><span class="sxs-lookup"><span data-stu-id="75211-108">A BizTalk Server performance assessment typically focuses on throughput and/or latency testing but may include build verification and functional tests.</span></span> <span data-ttu-id="75211-109">运行自动测试的全面信息，请参阅[实现自动化测试](../technical-guides/implementing-automated-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="75211-109">For comprehensive information about running automated testing, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md).</span></span>  
  
## <a name="step-2-document-and-evaluate-test-results"></a><span data-ttu-id="75211-110">第 2 步：记录和评估测试结果</span><span class="sxs-lookup"><span data-stu-id="75211-110">Step 2: Document and evaluate test results</span></span>  
 <span data-ttu-id="75211-111">在每个测试结束时，全面记录测试结果和评估是否满足了规定的性能目标。</span><span class="sxs-lookup"><span data-stu-id="75211-111">At the conclusion of each test, thoroughly document the test results and evaluate whether the stated performance goals have been met.</span></span>  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a><span data-ttu-id="75211-112">步骤 3：修改 BizTalk Server、 第三方系统或解决方案项目要优化的性能基于测试结果的配置</span><span class="sxs-lookup"><span data-stu-id="75211-112">Step 3: Modify the configuration of BizTalk Server, third-party systems, or solution artifacts to tune for performance based on the test results</span></span>  
 <span data-ttu-id="75211-113">使用测试结果来做出有关如何优化环境来访问所述的吞吐量或延迟目标。</span><span class="sxs-lookup"><span data-stu-id="75211-113">Use the test results to make decisions about how to optimize the environment to reach stated throughput or latency goals.</span></span>  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a><span data-ttu-id="75211-114">步骤 4：记录所有对环境所做的更改</span><span class="sxs-lookup"><span data-stu-id="75211-114">Step 4: Record all changes made to the environment</span></span>  
 <span data-ttu-id="75211-115">请确保完整地记录对环境进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="75211-115">Ensure that any changes made to the environment are thoroughly documented.</span></span> <span data-ttu-id="75211-116">所做的更改的记录将允许您轻松地将应用在生产环境中的更改并将容纳操作撤消更改，如果需要。</span><span class="sxs-lookup"><span data-stu-id="75211-116">A record of the changes will allow you to easily apply the changes in the production environment and will accommodate the undoing of changes if need be.</span></span>  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a><span data-ttu-id="75211-117">步骤 5：重复此过程，直到实现目标</span><span class="sxs-lookup"><span data-stu-id="75211-117">Step 5: Repeat this cycle until goals are achieved</span></span>  
 <span data-ttu-id="75211-118">继续测试、 评估和记录结果、 优化的环境和记录对环境的更改，直至达到所需的性能目标的循环。</span><span class="sxs-lookup"><span data-stu-id="75211-118">Continue the cycle of testing, evaluating and documenting results, optimizing the environment, and documenting changes to the environment until the desired performance goals are reached.</span></span>  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a><span data-ttu-id="75211-119">步骤 6：每一天结束时汇总测试结果</span><span class="sxs-lookup"><span data-stu-id="75211-119">Step 6: Summarize test results at the end of each day</span></span>  
 <span data-ttu-id="75211-120">完成"执行摘要"的测试结果和每一天结束时的进度。</span><span class="sxs-lookup"><span data-stu-id="75211-120">Complete an “executive summary” of the test results and progress made at the end of each day.</span></span> <span data-ttu-id="75211-121">编译包含摘要的电子邮件并发送到性能评估中的所有利益干系人以保证所有人知情的正在进行的进度。</span><span class="sxs-lookup"><span data-stu-id="75211-121">Compile an e-mail that contains the summary, and send to all stakeholders in the performance assessment to keep everyone informed of progress that is being made.</span></span>  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a><span data-ttu-id="75211-122">步骤 7：根据时间线目标更新项目计划</span><span class="sxs-lookup"><span data-stu-id="75211-122">Step 7: Update the project plan as timeline goals are met</span></span>  
 <span data-ttu-id="75211-123">在计划阶段中开发的时间线是很好的参考，对于性能评估的整个过程。</span><span class="sxs-lookup"><span data-stu-id="75211-123">The timeline developed in the Plan phase is a good reference for the overall progress of the performance assessment.</span></span> <span data-ttu-id="75211-124">更新此时间线，根据需要向所有利益干系人传达进度。</span><span class="sxs-lookup"><span data-stu-id="75211-124">Update this timeline as necessary to communicate the progress to all stakeholders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75211-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="75211-125">See Also</span></span>  
 [<span data-ttu-id="75211-126">性能评估阶段</span><span class="sxs-lookup"><span data-stu-id="75211-126">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)