---
title: "验证阶段建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00663354-ce5d-4391-b835-89940c92c1ce
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25344eafc37f492474b3f0bb36318afaf566829a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="verification-phase-recommendations"></a><span data-ttu-id="0f98a-102">验证阶段的建议</span><span class="sxs-lookup"><span data-stu-id="0f98a-102">Verification Phase Recommendations</span></span>
<span data-ttu-id="0f98a-103">系统代码编写完成后，即准备好进行稳定工作并验证发布标准。</span><span class="sxs-lookup"><span data-stu-id="0f98a-103">After the system is code complete, it is ready to be fully stabilized and the release criteria can be verified.</span></span> <span data-ttu-id="0f98a-104">此阶段通常称为稳定阶段。</span><span class="sxs-lookup"><span data-stu-id="0f98a-104">This phase is often referred to as the stabilization phase.</span></span> <span data-ttu-id="0f98a-105">此阶段的最终目的是发现并修复错误，以及验证系统是否已准备就绪可以投入生产。</span><span class="sxs-lookup"><span data-stu-id="0f98a-105">The ultimate goal of this phase is to identify and fix bugs and prove that the system is ready for production.</span></span> <span data-ttu-id="0f98a-106">因此，此阶段涉及系统候选版本的最终测试步骤。</span><span class="sxs-lookup"><span data-stu-id="0f98a-106">This phase, therefore, involves a final round of testing on a release candidate of the system.</span></span>  
  
 <span data-ttu-id="0f98a-107">候选版本是一种系统版本（通常是最新的）；如果所有验证测试全部通过，则它将被认为是足够完整和稳定的并可以成为发行版本。</span><span class="sxs-lookup"><span data-stu-id="0f98a-107">A release candidate is a version of the system (usually the most recent) that is deemed complete and stable enough to become the released version should the verification test all pass.</span></span> <span data-ttu-id="0f98a-108">为此，需要成功完成一系列功能、性能和压力测试，以验证它是否确实已准备完毕。</span><span class="sxs-lookup"><span data-stu-id="0f98a-108">The way this is proven is by successful completion of a bank of functional, performance, and stress tests that verify it is indeed ready.</span></span>  
  
## <a name="test-to-verify-sustainable-throughput-and-latency"></a><span data-ttu-id="0f98a-109">测试以验证可持续吞吐量和延迟</span><span class="sxs-lookup"><span data-stu-id="0f98a-109">Test to Verify Sustainable Throughput and Latency</span></span>  
 <span data-ttu-id="0f98a-110">性能的验证测试与实施阶段并行启动，但是需要最终确定一个已成功通过一整套发布标准测试的候选版本。</span><span class="sxs-lookup"><span data-stu-id="0f98a-110">Verification testing for performance was started in parallel with the implementation phase, but needs to be finalized on a release candidate that has been shown to successfully withstand the full set of release criteria testing.</span></span> <span data-ttu-id="0f98a-111">理想情况下，在最终测试期间对候选版本没有进行任何更改，这样就会有信心不会出现返工。</span><span class="sxs-lookup"><span data-stu-id="0f98a-111">Optimally, no changes to the release candidate are taken during the final test pass so that confidence is high that regressions have not been introduced.</span></span> <span data-ttu-id="0f98a-112">实际上这是非常困难的，随着对内部版本进行不断更改，必须对返工的风险进行评估。</span><span class="sxs-lookup"><span data-stu-id="0f98a-112">In practice, this is quite difficult and, as changes are checked into the build, evaluations must be made as to the risk of regression.</span></span>  
  
 <span data-ttu-id="0f98a-113">例如，如果对系统项目（如管道或业务流程）进行了重大的更改，则很可能需要重新运行性能测试以验证新的候选版本。</span><span class="sxs-lookup"><span data-stu-id="0f98a-113">For example, if a fundamental change to a system artifact such as a pipeline or orchestration is introduced, performance tests will likely need to be re-run in order validate this new release candidate.</span></span>  
  
 <span data-ttu-id="0f98a-114">为了确保系统已准备就绪可以投入生产，必须验证是否已经以可持续的方式对它进行了端对端测试。</span><span class="sxs-lookup"><span data-stu-id="0f98a-114">To ensure that the system is ready for production, you must verify that it has been tested in a sustainable fashion end to end.</span></span> <span data-ttu-id="0f98a-115">这意味着所有的操作活动，如数据库维护、 查询和计划的操作和计划外的停机必须进行测试，在主题中定义[什么是可持续的性能？](../core/what-is-sustainable-performance.md)</span><span class="sxs-lookup"><span data-stu-id="0f98a-115">This means that all operations activities such as database maintenance, operations querying, and planned and unplanned outages must be tested, as defined in the topic [What Is Sustainable Performance?](../core/what-is-sustainable-performance.md)</span></span> <span data-ttu-id="0f98a-116">这是最后一次的机会，若要验证对系统的准备情况，所以务必要组合可持续的性能测试中的最终测试传递的完整套件。</span><span class="sxs-lookup"><span data-stu-id="0f98a-116">This is the last chance to certify readiness for the system, so it is important to combine the full suite of sustainable performance tests in the final test pass.</span></span>  
  
## <a name="identify-bottlenecks-and-adjust-hardware-or-solution-to-remove-goal-blockers"></a><span data-ttu-id="0f98a-117">确认瓶颈并调整硬件或解决方案以排除障碍</span><span class="sxs-lookup"><span data-stu-id="0f98a-117">Identify Bottlenecks and Adjust Hardware or Solution to Remove Goal-Blockers</span></span>  
 <span data-ttu-id="0f98a-118">在实践中，很普遍最终测试通过的测试平台上为更接近于生产与硬件测试台的开发比。</span><span class="sxs-lookup"><span data-stu-id="0f98a-118">In practice, it is common that the test bed for the final test pass is closer to production with respect to hardware than the development of test beds.</span></span>  <span data-ttu-id="0f98a-119">很重要，因此，若要使用的最终测试传递过程的机会来标识系统中的任何新的或现有的瓶颈，并确定它们是否足够大，需要调整硬件中。</span><span class="sxs-lookup"><span data-stu-id="0f98a-119">It is important, therefore, to use the opportunity during the final test pass to identify any new or existing bottlenecks in the system and decide if they are of sufficient magnitude to require adjustments in hardware.</span></span> <span data-ttu-id="0f98a-120">即使不需要立即对硬件进行调整，找出最普遍的系统瓶颈也将提供宝贵的计划和操作信息。</span><span class="sxs-lookup"><span data-stu-id="0f98a-120">Even if hardware doesn’t need to be adjusted immediately, identifying the most prevalent system bottlenecks will provide valuable planning and operations information.</span></span>  
  
 <span data-ttu-id="0f98a-121">例如，如果系统通过生产负载测试，但是观测到 MessageBox 服务器物理磁盘的空闲时间很低（例如，低于 20%），则在生产期间监视此磁盘将被视为一项关键的运行状况指标。</span><span class="sxs-lookup"><span data-stu-id="0f98a-121">For example, if the system sustains the production load profile, but it is observed that the physical disk idle time on the MessageBox server is low (for example, below 20%), then monitoring this disk during production can be identified as a key health indicator.</span></span> <span data-ttu-id="0f98a-122">另外，在此阶段制定增加系统负载能力的所有计划时，应认识到需要对磁盘子系统进行改善。</span><span class="sxs-lookup"><span data-stu-id="0f98a-122">In addition, any plans for increasing the load capability of the system can now include knowledge that the disk subsystem will need to be improved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f98a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f98a-123">See Also</span></span>  
 <span data-ttu-id="0f98a-124">[项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="0f98a-124">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="0f98a-125">[要求阶段建议](../core/requirements-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="0f98a-125">[Requirements Phase Recommendations](../core/requirements-phase-recommendations.md) </span></span>  
 <span data-ttu-id="0f98a-126">[设计阶段建议](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="0f98a-126">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="0f98a-127">[实现阶段建议](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="0f98a-127">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="0f98a-128">发布阶段建议</span><span class="sxs-lookup"><span data-stu-id="0f98a-128">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)