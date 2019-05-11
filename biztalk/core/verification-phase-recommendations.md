---
title: 验证阶段的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00663354-ce5d-4391-b835-89940c92c1ce
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48f7c28edd87ff0f1c9f780a5999be542eaaa398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292591"
---
# <a name="verification-phase-recommendations"></a><span data-ttu-id="71d06-102">验证阶段的建议</span><span class="sxs-lookup"><span data-stu-id="71d06-102">Verification Phase Recommendations</span></span>
<span data-ttu-id="71d06-103">系统代码编写完成后，它已准备好进行稳定和可验证的发布条件。</span><span class="sxs-lookup"><span data-stu-id="71d06-103">After the system is code complete, it is ready to be fully stabilized and the release criteria can be verified.</span></span> <span data-ttu-id="71d06-104">此阶段通常称为稳定阶段。</span><span class="sxs-lookup"><span data-stu-id="71d06-104">This phase is often referred to as the stabilization phase.</span></span> <span data-ttu-id="71d06-105">此阶段的最终目标是识别并修复 bug，并证明系统准备好进行生产。</span><span class="sxs-lookup"><span data-stu-id="71d06-105">The ultimate goal of this phase is to identify and fix bugs and prove that the system is ready for production.</span></span> <span data-ttu-id="71d06-106">此阶段中，因此，涉及到系统的候选发布版本上测试最后一的轮。</span><span class="sxs-lookup"><span data-stu-id="71d06-106">This phase, therefore, involves a final round of testing on a release candidate of the system.</span></span>  
  
 <span data-ttu-id="71d06-107">候选发布版本是版本 （通常是最新） 被视为完整的系统，稳定，足以成为发布的版本验证测试全部通过。</span><span class="sxs-lookup"><span data-stu-id="71d06-107">A release candidate is a version of the system (usually the most recent) that is deemed complete and stable enough to become the released version should the verification test all pass.</span></span> <span data-ttu-id="71d06-108">这经验证的方法是成功完成一系列功能、 性能和压力测试，以验证它确实已准备。</span><span class="sxs-lookup"><span data-stu-id="71d06-108">The way this is proven is by successful completion of a bank of functional, performance, and stress tests that verify it is indeed ready.</span></span>  
  
## <a name="test-to-verify-sustainable-throughput-and-latency"></a><span data-ttu-id="71d06-109">测试以验证可持续吞吐量和延迟</span><span class="sxs-lookup"><span data-stu-id="71d06-109">Test to Verify Sustainable Throughput and Latency</span></span>  
 <span data-ttu-id="71d06-110">验证测试的性能与实施阶段并行启动，但需要最终确定已被证实将成功地承受发布标准测试的完整集的候选发布版本。</span><span class="sxs-lookup"><span data-stu-id="71d06-110">Verification testing for performance was started in parallel with the implementation phase, but needs to be finalized on a release candidate that has been shown to successfully withstand the full set of release criteria testing.</span></span> <span data-ttu-id="71d06-111">理想情况下，到候选发布版的任何更改不会在最终测试阶段，以便置信度较高尚未引入回归。</span><span class="sxs-lookup"><span data-stu-id="71d06-111">Optimally, no changes to the release candidate are taken during the final test pass so that confidence is high that regressions have not been introduced.</span></span> <span data-ttu-id="71d06-112">在实践中，这是非常困难并更改已签入生成，因为必须返工回归的风险进行评估。</span><span class="sxs-lookup"><span data-stu-id="71d06-112">In practice, this is quite difficult and, as changes are checked into the build, evaluations must be made as to the risk of regression.</span></span>  
  
 <span data-ttu-id="71d06-113">例如，如果引入管道或业务流程等系统项目的基础更改，性能测试可能需要按顺序重新运行验证新的候选。</span><span class="sxs-lookup"><span data-stu-id="71d06-113">For example, if a fundamental change to a system artifact such as a pipeline or orchestration is introduced, performance tests will likely need to be re-run in order validate this new release candidate.</span></span>  
  
 <span data-ttu-id="71d06-114">若要确保系统准备好进行生产，必须验证以可持续的方式端到端上已经过测试。</span><span class="sxs-lookup"><span data-stu-id="71d06-114">To ensure that the system is ready for production, you must verify that it has been tested in a sustainable fashion end to end.</span></span> <span data-ttu-id="71d06-115">这意味着所有操作活动，如都数据库维护、 操作查询和计划内和计划外的停机必须进行测试，如本主题中所定义[可承受性能？](../core/what-is-sustainable-performance.md)</span><span class="sxs-lookup"><span data-stu-id="71d06-115">This means that all operations activities such as database maintenance, operations querying, and planned and unplanned outages must be tested, as defined in the topic [What Is Sustainable Performance?](../core/what-is-sustainable-performance.md)</span></span> <span data-ttu-id="71d06-116">这是最后一次机会来验证对系统的准备情况，所以务必要合并的最终测试过程中可持续性能测试的完整套件。</span><span class="sxs-lookup"><span data-stu-id="71d06-116">This is the last chance to certify readiness for the system, so it is important to combine the full suite of sustainable performance tests in the final test pass.</span></span>  
  
## <a name="identify-bottlenecks-and-adjust-hardware-or-solution-to-remove-goal-blockers"></a><span data-ttu-id="71d06-117">识别瓶颈并调整硬件或解决方案以排除障碍</span><span class="sxs-lookup"><span data-stu-id="71d06-117">Identify Bottlenecks and Adjust Hardware or Solution to Remove Goal-Blockers</span></span>  
 <span data-ttu-id="71d06-118">在实践中，是常见的最终测试传递测试平台是更接近于生产硬件方面比测试平台的开发。</span><span class="sxs-lookup"><span data-stu-id="71d06-118">In practice, it is common that the test bed for the final test pass is closer to production with respect to hardware than the development of test beds.</span></span>  <span data-ttu-id="71d06-119">它是重要的是，因此，在最终测试阶段利用此机会可以标识系统中的任何新的或现有的瓶颈，并确定它们是否足够大以进行调整。</span><span class="sxs-lookup"><span data-stu-id="71d06-119">It is important, therefore, to use the opportunity during the final test pass to identify any new or existing bottlenecks in the system and decide if they are of sufficient magnitude to require adjustments in hardware.</span></span> <span data-ttu-id="71d06-120">即使硬件无需立即进行调整，发现最普遍的系统瓶颈，将提供宝贵的计划和操作信息。</span><span class="sxs-lookup"><span data-stu-id="71d06-120">Even if hardware doesn’t need to be adjusted immediately, identifying the most prevalent system bottlenecks will provide valuable planning and operations information.</span></span>  
  
 <span data-ttu-id="71d06-121">例如，如果系统通过生产负载状况，但它观察到 MessageBox 服务器上的物理磁盘空闲时间太少 （例如，小于 20%)，然后在生产期间监视此磁盘可以将标识为一个关键的运行状况指示符。</span><span class="sxs-lookup"><span data-stu-id="71d06-121">For example, if the system sustains the production load profile, but it is observed that the physical disk idle time on the MessageBox server is low (for example, below 20%), then monitoring this disk during production can be identified as a key health indicator.</span></span> <span data-ttu-id="71d06-122">此外，增加系统的负载功能的计划现在可以包括磁盘子系统需要改进的知识。</span><span class="sxs-lookup"><span data-stu-id="71d06-122">In addition, any plans for increasing the load capability of the system can now include knowledge that the disk subsystem will need to be improved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d06-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="71d06-123">See Also</span></span>  
 <span data-ttu-id="71d06-124">[分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="71d06-124">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="71d06-125">[需求阶段的建议](../core/requirements-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="71d06-125">[Requirements Phase Recommendations](../core/requirements-phase-recommendations.md) </span></span>  
 <span data-ttu-id="71d06-126">[设计阶段的建议](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="71d06-126">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="71d06-127">[实现阶段的建议](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="71d06-127">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="71d06-128">发行阶段的建议</span><span class="sxs-lookup"><span data-stu-id="71d06-128">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)