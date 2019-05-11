---
title: 需求阶段的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b510313-c3a7-42bc-9c9b-336c927a5d4a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b0f78179d57085dd1a9dc97aedb2b424d306638
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322130"
---
# <a name="requirements-phase-recommendations"></a><span data-ttu-id="26697-102">需求阶段的建议</span><span class="sxs-lookup"><span data-stu-id="26697-102">Requirements Phase Recommendations</span></span>
<span data-ttu-id="26697-103">与需求阶段相关联主要可交付成果是需求规范或包括要求包括性能目标的功能规范。</span><span class="sxs-lookup"><span data-stu-id="26697-103">The primary deliverable associated with the requirements phase is a requirements specification, or a functional specification that includes requirements including performance goals.</span></span> <span data-ttu-id="26697-104">它是非常重要，以确定这些目标，以确保性能的准确配置文件派生时涉及的最终用户和系统的业务所有者。</span><span class="sxs-lookup"><span data-stu-id="26697-104">It is very important to involve the end-users and business owners of the system when determining these goals to assure that an accurate profile for performance is derived.</span></span>  
  
## <a name="establish-performance-criteria"></a><span data-ttu-id="26697-105">建立性能标准</span><span class="sxs-lookup"><span data-stu-id="26697-105">Establish Performance Criteria</span></span>  
 <span data-ttu-id="26697-106">从性能角度看，在此阶段中创建功能规范的最重要部分是项目的详细的性能目标的定义和建立性能发布标准。</span><span class="sxs-lookup"><span data-stu-id="26697-106">From a performance perspective, the most important part of the functional specification that is created during this phase is the definition of detailed performance goals for the project and the establishment of performance release criteria.</span></span> <span data-ttu-id="26697-107">有三个关键组件定义性能标准：</span><span class="sxs-lookup"><span data-stu-id="26697-107">There are three critical components to defining performance criteria:</span></span>  
  
- <span data-ttu-id="26697-108">将性能定义的函数的时间为一条曲线。</span><span class="sxs-lookup"><span data-stu-id="26697-108">A curve that defines performance as a function of time.</span></span>  
  
- <span data-ttu-id="26697-109">性能要求，与性能函数相关联。</span><span class="sxs-lookup"><span data-stu-id="26697-109">A performance requirement associated with the performance function.</span></span>  
  
- <span data-ttu-id="26697-110">文件大小和类型的分布。</span><span class="sxs-lookup"><span data-stu-id="26697-110">A distribution of file sizes and types.</span></span>  
  
  <span data-ttu-id="26697-111">这些条件中讨论了[可承受性能？](../core/what-is-sustainable-performance.md)</span><span class="sxs-lookup"><span data-stu-id="26697-111">These criteria are discussed in [What Is Sustainable Performance?](../core/what-is-sustainable-performance.md)</span></span>  
  
  <span data-ttu-id="26697-112">中的性能目标的应用程序的性能发布标准，则派生。</span><span class="sxs-lookup"><span data-stu-id="26697-112">You derive the performance release criteria for an application from the performance goals.</span></span> <span data-ttu-id="26697-113">这些标准包含可实现的、 可衡量的行为，您可以通过测试来证明。</span><span class="sxs-lookup"><span data-stu-id="26697-113">These criteria embody an achievable and measurable behavior that you can prove via testing.</span></span> <span data-ttu-id="26697-114">应用程序不会移动到版本中，除非之前所有的发布条件已满足或，如果不可实现标识为发布标准的例外情况。</span><span class="sxs-lookup"><span data-stu-id="26697-114">The application will not move into release unless and until all release criteria have been met or, if not achievable, identified as exceptions to the release criteria.</span></span>  
  
  <span data-ttu-id="26697-115">它是产品周期的早期阶段设置发布标准非常重要。</span><span class="sxs-lookup"><span data-stu-id="26697-115">It is very important to set the release criteria during the early phases of the product cycle.</span></span> <span data-ttu-id="26697-116">所涉及的每个人都这么做意味着知道的目标是，并且没有达到之前设计和实现已注销的后果。</span><span class="sxs-lookup"><span data-stu-id="26697-116">Doing so means everyone involved knows what the goals are and the consequences of not reaching them before design and implementation are signed off.</span></span>  
  
  <span data-ttu-id="26697-117">此外，性能测试用例将基于如何发布条件的评估，因此条件必须为详细，不足以避免混淆。</span><span class="sxs-lookup"><span data-stu-id="26697-117">In addition, performance test cases will be based on how the release criteria are to be measured, so the criteria must be detailed enough to avoid confusion.</span></span> <span data-ttu-id="26697-118">例如，当声明的特定吞吐量来实现时，它应包括：</span><span class="sxs-lookup"><span data-stu-id="26697-118">For example, when stating a specific throughput is to be achieved, it should include:</span></span>  
  
- <span data-ttu-id="26697-119">在其它必须运行硬件，例如的数量和类型的服务器、 磁盘速度/类型等。</span><span class="sxs-lookup"><span data-stu-id="26697-119">The hardware on which it must run, for example, the number and type of servers, disk speed/type, etc.</span></span>  
  
- <span data-ttu-id="26697-120">哪些方案是进行测试，例如，路径消息将引导完成应用程序</span><span class="sxs-lookup"><span data-stu-id="26697-120">What scenario is to be tested, for example, what path messages will take through the application</span></span>  
  
- <span data-ttu-id="26697-121">方式进行度量，例如，自定义代码的性能计数器测量消息到达共享等的时间。</span><span class="sxs-lookup"><span data-stu-id="26697-121">How it is to be measured, for example, performance counters, custom code, measuring times messages arrive in a share, etc.</span></span>  
  
  <span data-ttu-id="26697-122">若要判断如何正确发布条件是，任何人都应能够查看发布标准所述并了解如何生成测试用例来证明该标准。</span><span class="sxs-lookup"><span data-stu-id="26697-122">To judge how well formed a release criteria is, anyone should be able look at the release criteria as documented and understand how to build a test case to prove the criteria.</span></span>  
  
## <a name="identify-performance-risks"></a><span data-ttu-id="26697-123">确定性能风险</span><span class="sxs-lookup"><span data-stu-id="26697-123">Identify Performance Risks</span></span>  
 <span data-ttu-id="26697-124">性能发布目标和条件在充分地介绍具有后，可以执行性能风险区域的初始评估。</span><span class="sxs-lookup"><span data-stu-id="26697-124">After the performance release goals and criteria have been sufficiently detailed, an initial assessment of performance risk areas can be performed.</span></span> <span data-ttu-id="26697-125">此分析的目的是确定应用程序可能需要特殊的设计关注，解决替代方案或消除以达到所需的条件的部分。</span><span class="sxs-lookup"><span data-stu-id="26697-125">The purpose of this analysis is to identify parts of the application that may need special design attention, work-around alternatives or elimination in order to reach the desired criteria.</span></span>  
  
 <span data-ttu-id="26697-126">例如，每个传输适配器类型都有其自己的性能和缩放特征。</span><span class="sxs-lookup"><span data-stu-id="26697-126">For example, each transport adapter type has its own performance and scale characteristics.</span></span> <span data-ttu-id="26697-127">如果所需的吞吐量超出一个或多个适配器类型的功能 （接收或发送），然后替代扩展适配器方案可能需要进行调查。</span><span class="sxs-lookup"><span data-stu-id="26697-127">If the desired throughput exceeds the ability of one or more of the adapter types (either receive or send), then alternatives for scaling the adapter may need to be investigated.</span></span>  
  
## <a name="estimate-sizing"></a><span data-ttu-id="26697-128">估算大小</span><span class="sxs-lookup"><span data-stu-id="26697-128">Estimate Sizing</span></span>  
 <span data-ttu-id="26697-129">根据已建立的目标和条件，它将永远不会过早地开始估计将需要达到的目标的硬件大小的过程。</span><span class="sxs-lookup"><span data-stu-id="26697-129">Based on the established goals and criteria, it is never too early to begin the process of estimating the hardware sizing that will be required to meet the goals.</span></span> <span data-ttu-id="26697-130">与使用任何调整大小估算，其中一个必须基于这些估计值实际的测试结果。</span><span class="sxs-lookup"><span data-stu-id="26697-130">As with any sizing estimation efforts, one must base the estimates on actual test results.</span></span> <span data-ttu-id="26697-131">在项目早期阶段，这些结果必定来自外部源。</span><span class="sxs-lookup"><span data-stu-id="26697-131">During the early phases of a project, those results must come from external sources.</span></span> <span data-ttu-id="26697-132">您可以光临在 BizTalk Server 开发人员中心，案例研究[ http://go.microsoft.com/fwlink/?LinkId=49339 ](http://go.microsoft.com/fwlink/?LinkId=49339)。</span><span class="sxs-lookup"><span data-stu-id="26697-132">You can read case studies at BizTalk Server Developer Center, at [http://go.microsoft.com/fwlink/?LinkId=49339](http://go.microsoft.com/fwlink/?LinkId=49339).</span></span> <span data-ttu-id="26697-133">案例研究提供有关方案的详细信息进行测试，在其执行测试的硬件和测试的配置。</span><span class="sxs-lookup"><span data-stu-id="26697-133">The case studies provide details about the scenarios tested, the hardware on which testing was done, and the configuration for the tests.</span></span> <span data-ttu-id="26697-134">您可以从这些测试用例，若要获得您的系统的初始大小估计值实现的性能进行推断。</span><span class="sxs-lookup"><span data-stu-id="26697-134">You can extrapolate from the performance achieved for these test cases to get an initial sizing estimate for your system.</span></span>  
  
 <span data-ttu-id="26697-135">请记住，没有任何预测模型或模拟准确预测系统大小上运行的任意应用程序的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="26697-135">Keep in mind that there is no predictive model or simulation that accurately predicts system size for any arbitrary application running on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="26697-136">是一个平台在其可以部署多种应用程序解决方案，每个都有其自己的性能行为。</span><span class="sxs-lookup"><span data-stu-id="26697-136">is a platform on which a large variety of application solutions can be deployed, each with its own performance behavior.</span></span> <span data-ttu-id="26697-137">因此，尽管使用现有的案例研究结果派生估计值将为进行规划提供很好的起点，系统的最终大小极有可能需要调整对于所有的最简单的应用程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="26697-137">So, while an estimate derived using existing case study results will provide a good starting point for planning purposes, the final size of the system will most certainly need to be adjusted for all but the simplest application architectures.</span></span>  
  
## <a name="plan-for-sufficient-testing"></a><span data-ttu-id="26697-138">充分的测试计划</span><span class="sxs-lookup"><span data-stu-id="26697-138">Plan for Sufficient Testing</span></span>  
 <span data-ttu-id="26697-139">如上所述，目前尚没有模型或模拟能够准确预测为满足性能目标所需的硬件。</span><span class="sxs-lookup"><span data-stu-id="26697-139">As stated above, there is currently no model or simulation that will accurately predict the hardware required to meet performance goals.</span></span> <span data-ttu-id="26697-140">这意味着，才能真正证明该系统可以到达目标的唯一方法是测试生产级硬件上。</span><span class="sxs-lookup"><span data-stu-id="26697-140">This means that the only way to actually prove a system is capable of reaching goals is to test it on production-level hardware.</span></span> <span data-ttu-id="26697-141">也就是说，执行测试用例的硬件，尽可能接近生产设置尽可能。</span><span class="sxs-lookup"><span data-stu-id="26697-141">That is, to conduct test cases on hardware that is as close to the production setup as possible.</span></span>  
  
 <span data-ttu-id="26697-142">这一部分的规划至关重要，整合在一起的原则可承受性能、 详细信息，了解吞吐量状况以及性能发布标准。</span><span class="sxs-lookup"><span data-stu-id="26697-142">This part of the planning is critical and pulls together the principles of sustainable performance, understanding throughput profiles in detail, and the performance release criteria.</span></span> <span data-ttu-id="26697-143">使用配置文件从现有数据，测试用例推出必须派生，一致地评估发布标准的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="26697-143">Using the throughput profiles obtained by extrapolating from existing data, test cases must be derived that will consistently measure the release criteria.</span></span> <span data-ttu-id="26697-144">必须记住可持续运行测试用例。</span><span class="sxs-lookup"><span data-stu-id="26697-144">The test cases must be run with sustainability in mind.</span></span> <span data-ttu-id="26697-145">有关可持续测试的示例，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="26697-145">For examples of sustainable testing, see the following topics:</span></span>  
  
-   [<span data-ttu-id="26697-146">测量最大可承受引擎吞吐量</span><span class="sxs-lookup"><span data-stu-id="26697-146">Measuring Maximum Sustainable Engine Throughput</span></span>](../core/measuring-maximum-sustainable-engine-throughput.md)  
  
-   [<span data-ttu-id="26697-147">测量最大可承受跟踪吞吐量</span><span class="sxs-lookup"><span data-stu-id="26697-147">Measuring Maximum Sustainable Tracking Throughput</span></span>](../core/measuring-maximum-sustainable-tracking-throughput.md)  
  
## <a name="see-also"></a><span data-ttu-id="26697-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="26697-148">See Also</span></span>  
 <span data-ttu-id="26697-149">[分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="26697-149">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="26697-150">[设计阶段的建议](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="26697-150">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="26697-151">[实现阶段的建议](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="26697-151">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 <span data-ttu-id="26697-152">[验证阶段的建议](../core/verification-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="26697-152">[Verification Phase Recommendations](../core/verification-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="26697-153">发行阶段的建议</span><span class="sxs-lookup"><span data-stu-id="26697-153">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)