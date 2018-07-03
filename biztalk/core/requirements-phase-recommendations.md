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
ms.openlocfilehash: 6bb12022811aceb3c5a5311a6f44914ec60dbae0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004566"
---
# <a name="requirements-phase-recommendations"></a><span data-ttu-id="d24db-102">需求阶段的建议</span><span class="sxs-lookup"><span data-stu-id="d24db-102">Requirements Phase Recommendations</span></span>
<span data-ttu-id="d24db-103">与需求阶段相关的主要可交付成果是需求规范，即包括诸如性能目标等要求的功能规范。</span><span class="sxs-lookup"><span data-stu-id="d24db-103">The primary deliverable associated with the requirements phase is a requirements specification, or a functional specification that includes requirements including performance goals.</span></span> <span data-ttu-id="d24db-104">务必让使用该系统的最终用户和业务所有者参与确定这些目标，以确保了解准确的性能状况。</span><span class="sxs-lookup"><span data-stu-id="d24db-104">It is very important to involve the end-users and business owners of the system when determining these goals to assure that an accurate profile for performance is derived.</span></span>  
  
## <a name="establish-performance-criteria"></a><span data-ttu-id="d24db-105">建立性能标准</span><span class="sxs-lookup"><span data-stu-id="d24db-105">Establish Performance Criteria</span></span>  
 <span data-ttu-id="d24db-106">从性能角度看，在此阶段中创建功能规范的最重要部分是项目的详细的性能目标的定义和建立性能发布标准。</span><span class="sxs-lookup"><span data-stu-id="d24db-106">From a performance perspective, the most important part of the functional specification that is created during this phase is the definition of detailed performance goals for the project and the establishment of performance release criteria.</span></span> <span data-ttu-id="d24db-107">定义性能标准有以下三个关键部分：</span><span class="sxs-lookup"><span data-stu-id="d24db-107">There are three critical components to defining performance criteria:</span></span>  
  
- <span data-ttu-id="d24db-108">将性能定义为时间的函数的曲线。</span><span class="sxs-lookup"><span data-stu-id="d24db-108">A curve that defines performance as a function of time.</span></span>  
  
- <span data-ttu-id="d24db-109">与性能函数相关联的性能要求。</span><span class="sxs-lookup"><span data-stu-id="d24db-109">A performance requirement associated with the performance function.</span></span>  
  
- <span data-ttu-id="d24db-110">文件大小和类型的分布。</span><span class="sxs-lookup"><span data-stu-id="d24db-110">A distribution of file sizes and types.</span></span>  
  
  <span data-ttu-id="d24db-111">这些条件中讨论了[可承受性能？](../core/what-is-sustainable-performance.md)</span><span class="sxs-lookup"><span data-stu-id="d24db-111">These criteria are discussed in [What Is Sustainable Performance?](../core/what-is-sustainable-performance.md)</span></span>  
  
  <span data-ttu-id="d24db-112">您可以从性能目标派生出应用程序的性能发布标准。</span><span class="sxs-lookup"><span data-stu-id="d24db-112">You derive the performance release criteria for an application from the performance goals.</span></span> <span data-ttu-id="d24db-113">这些标准包含可实现和可评估的行为，这些行为可以通过测试来证明。</span><span class="sxs-lookup"><span data-stu-id="d24db-113">These criteria embody an achievable and measurable behavior that you can prove via testing.</span></span> <span data-ttu-id="d24db-114">应用程序将不会发布，除非它已经满足所有的发布标准或被标识为发布标准的例外情况（如果不可实现）。</span><span class="sxs-lookup"><span data-stu-id="d24db-114">The application will not move into release unless and until all release criteria have been met or, if not achievable, identified as exceptions to the release criteria.</span></span>  
  
  <span data-ttu-id="d24db-115">务必在产品周期的早期阶段设置发布标准。</span><span class="sxs-lookup"><span data-stu-id="d24db-115">It is very important to set the release criteria during the early phases of the product cycle.</span></span> <span data-ttu-id="d24db-116">这意味着在设计和实现结束之前涉及到的每个人都知道目标是什么以及没有达到目标的后果。</span><span class="sxs-lookup"><span data-stu-id="d24db-116">Doing so means everyone involved knows what the goals are and the consequences of not reaching them before design and implementation are signed off.</span></span>  
  
  <span data-ttu-id="d24db-117">另外，性能测试用例将会基于发布标准的评估方式，因此必须详细介绍标准以避免混淆。</span><span class="sxs-lookup"><span data-stu-id="d24db-117">In addition, performance test cases will be based on how the release criteria are to be measured, so the criteria must be detailed enough to avoid confusion.</span></span> <span data-ttu-id="d24db-118">例如，当说明要达到的特定吞吐量时，应包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="d24db-118">For example, when stating a specific throughput is to be achieved, it should include:</span></span>  
  
- <span data-ttu-id="d24db-119">所需的硬件，例如服务器的数量和类型，磁盘速度/类型等</span><span class="sxs-lookup"><span data-stu-id="d24db-119">The hardware on which it must run, for example, the number and type of servers, disk speed/type, etc.</span></span>  
  
- <span data-ttu-id="d24db-120">要测试的方案，例如消息通过应用程序的路径</span><span class="sxs-lookup"><span data-stu-id="d24db-120">What scenario is to be tested, for example, what path messages will take through the application</span></span>  
  
- <span data-ttu-id="d24db-121">评估的方式，例如性能计数器、自定义代码、测量消息到达共享的次数等</span><span class="sxs-lookup"><span data-stu-id="d24db-121">How it is to be measured, for example, performance counters, custom code, measuring times messages arrive in a share, etc.</span></span>  
  
  <span data-ttu-id="d24db-122">若要判断发布标准是否合适，所有人都应能够查看发布标准文档，并了解如何生成测试用例来证明该标准。</span><span class="sxs-lookup"><span data-stu-id="d24db-122">To judge how well formed a release criteria is, anyone should be able look at the release criteria as documented and understand how to build a test case to prove the criteria.</span></span>  
  
## <a name="identify-performance-risks"></a><span data-ttu-id="d24db-123">确定性能风险</span><span class="sxs-lookup"><span data-stu-id="d24db-123">Identify Performance Risks</span></span>  
 <span data-ttu-id="d24db-124">在充分地介绍了性能发布目标和标准后，就可以执行性能风险区域的初始评估了。</span><span class="sxs-lookup"><span data-stu-id="d24db-124">After the performance release goals and criteria have been sufficiently detailed, an initial assessment of performance risk areas can be performed.</span></span> <span data-ttu-id="d24db-125">此分析的目的是为了确定在设计应用程序时需要特别关注的部分、需要备选解决方案的部分或需要去除的部分，以便达到所需标准。</span><span class="sxs-lookup"><span data-stu-id="d24db-125">The purpose of this analysis is to identify parts of the application that may need special design attention, work-around alternatives or elimination in order to reach the desired criteria.</span></span>  
  
 <span data-ttu-id="d24db-126">例如，每个传输适配器类型都有自己的性能和扩展特性。</span><span class="sxs-lookup"><span data-stu-id="d24db-126">For example, each transport adapter type has its own performance and scale characteristics.</span></span> <span data-ttu-id="d24db-127">如果所需的吞吐量超出了一个或多个适配器类型（即接收或发送）的能力，则需要调查适配器的替代扩展方案。</span><span class="sxs-lookup"><span data-stu-id="d24db-127">If the desired throughput exceeds the ability of one or more of the adapter types (either receive or send), then alternatives for scaling the adapter may need to be investigated.</span></span>  
  
## <a name="estimate-sizing"></a><span data-ttu-id="d24db-128">估算大小</span><span class="sxs-lookup"><span data-stu-id="d24db-128">Estimate Sizing</span></span>  
 <span data-ttu-id="d24db-129">根据已建立的目标和标准，应尽早开始估算为达到目标所需的硬件大小。</span><span class="sxs-lookup"><span data-stu-id="d24db-129">Based on the established goals and criteria, it is never too early to begin the process of estimating the hardware sizing that will be required to meet the goals.</span></span> <span data-ttu-id="d24db-130">与估算任何大小的情形一样，必须根据实际的测试结果进行估算。</span><span class="sxs-lookup"><span data-stu-id="d24db-130">As with any sizing estimation efforts, one must base the estimates on actual test results.</span></span> <span data-ttu-id="d24db-131">在项目的早期阶段，这些结果必定来自外部源。</span><span class="sxs-lookup"><span data-stu-id="d24db-131">During the early phases of a project, those results must come from external sources.</span></span> <span data-ttu-id="d24db-132">您可以光临在 BizTalk Server 开发人员中心，案例研究[ http://go.microsoft.com/fwlink/?LinkId=49339 ](http://go.microsoft.com/fwlink/?LinkId=49339)。</span><span class="sxs-lookup"><span data-stu-id="d24db-132">You can read case studies at BizTalk Server Developer Center, at [http://go.microsoft.com/fwlink/?LinkId=49339](http://go.microsoft.com/fwlink/?LinkId=49339).</span></span> <span data-ttu-id="d24db-133">这些案例研究提供有关测试的方案、执行测试的硬件以及测试的配置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d24db-133">The case studies provide details about the scenarios tested, the hardware on which testing was done, and the configuration for the tests.</span></span> <span data-ttu-id="d24db-134">您可以从这些测试用例已实现的性能来推算出您的系统的初始大小估计值。</span><span class="sxs-lookup"><span data-stu-id="d24db-134">You can extrapolate from the performance achieved for these test cases to get an initial sizing estimate for your system.</span></span>  
  
 <span data-ttu-id="d24db-135">请记住，没有任何预测模型或模拟准确预测系统大小上运行的任意应用程序的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d24db-135">Keep in mind that there is no predictive model or simulation that accurately predicts system size for any arbitrary application running on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d24db-136"> 是一个平台在其可以部署多种应用程序解决方案，每个都有其自己的性能行为。</span><span class="sxs-lookup"><span data-stu-id="d24db-136"> is a platform on which a large variety of application solutions can be deployed, each with its own performance behavior.</span></span> <span data-ttu-id="d24db-137">因此，尽管使用现有的案例研究结果可以为规划目的提供良好的开端，不过，即使对于最简单的应用程序结构，其系统的最终大小也很可能需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="d24db-137">So, while an estimate derived using existing case study results will provide a good starting point for planning purposes, the final size of the system will most certainly need to be adjusted for all but the simplest application architectures.</span></span>  
  
## <a name="plan-for-sufficient-testing"></a><span data-ttu-id="d24db-138">计划充分的测试</span><span class="sxs-lookup"><span data-stu-id="d24db-138">Plan for Sufficient Testing</span></span>  
 <span data-ttu-id="d24db-139">如上所述，目前没有模型或模拟能够准确预测为满足性能目标所需的硬件。</span><span class="sxs-lookup"><span data-stu-id="d24db-139">As stated above, there is currently no model or simulation that will accurately predict the hardware required to meet performance goals.</span></span> <span data-ttu-id="d24db-140">这表示只有在生产级别的硬件中对系统进行测试才能真正证明该系统是否可以满足目标。</span><span class="sxs-lookup"><span data-stu-id="d24db-140">This means that the only way to actually prove a system is capable of reaching goals is to test it on production-level hardware.</span></span> <span data-ttu-id="d24db-141">即，在与生产设置尽可能接近的硬件中执行测试用例。</span><span class="sxs-lookup"><span data-stu-id="d24db-141">That is, to conduct test cases on hardware that is as close to the production setup as possible.</span></span>  
  
 <span data-ttu-id="d24db-142">这部分规划是很关键的，它将可持续性能的原则、详细了解吞吐量状况以及性能发布标准组合在一起。</span><span class="sxs-lookup"><span data-stu-id="d24db-142">This part of the planning is critical and pulls together the principles of sustainable performance, understanding throughput profiles in detail, and the performance release criteria.</span></span> <span data-ttu-id="d24db-143">使用从现有数据推出的吞吐量状况，必须派生能够一致地评估发布标准的测试用例。</span><span class="sxs-lookup"><span data-stu-id="d24db-143">Using the throughput profiles obtained by extrapolating from existing data, test cases must be derived that will consistently measure the release criteria.</span></span> <span data-ttu-id="d24db-144">请注意，测试用例必须以可持续的方式运行。</span><span class="sxs-lookup"><span data-stu-id="d24db-144">The test cases must be run with sustainability in mind.</span></span> <span data-ttu-id="d24db-145">有关可持续测试的示例，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="d24db-145">For examples of sustainable testing, see the following topics:</span></span>  
  
-   [<span data-ttu-id="d24db-146">测量最大可承受引擎吞吐量</span><span class="sxs-lookup"><span data-stu-id="d24db-146">Measuring Maximum Sustainable Engine Throughput</span></span>](../core/measuring-maximum-sustainable-engine-throughput.md)  
  
-   [<span data-ttu-id="d24db-147">测量最大可承受跟踪吞吐量</span><span class="sxs-lookup"><span data-stu-id="d24db-147">Measuring Maximum Sustainable Tracking Throughput</span></span>](../core/measuring-maximum-sustainable-tracking-throughput.md)  
  
## <a name="see-also"></a><span data-ttu-id="d24db-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="d24db-148">See Also</span></span>  
 <span data-ttu-id="d24db-149">[分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="d24db-149">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="d24db-150">[设计阶段的建议](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="d24db-150">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="d24db-151">[实现阶段的建议](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="d24db-151">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 <span data-ttu-id="d24db-152">[验证阶段的建议](../core/verification-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="d24db-152">[Verification Phase Recommendations](../core/verification-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="d24db-153">发行阶段的建议</span><span class="sxs-lookup"><span data-stu-id="d24db-153">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)