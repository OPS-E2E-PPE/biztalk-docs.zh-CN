---
title: "威胁模型分析 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TMA, about TMA
- TMA
- TMA, procedure steps
ms.assetid: dfbf46aa-0a35-4925-8718-df8591efc279
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06f5de73434d2c3a7bf67e659c6566b530b38aeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="threat-model-analysis"></a><span data-ttu-id="483ae-102">威胁模型分析</span><span class="sxs-lookup"><span data-stu-id="483ae-102">Threat Model Analysis</span></span>
<span data-ttu-id="483ae-103">威胁模型分析 (TMA) 进行分析可帮助确定到产品、 应用程序、 网络或环境中，所带来安全风险和攻击的显示方式。</span><span class="sxs-lookup"><span data-stu-id="483ae-103">A threat model analysis (TMA) is an analysis that helps determine the security risks posed to a product, application, network, or environment, and how attacks can show up.</span></span> <span data-ttu-id="483ae-104">目标是确定哪些威胁需要缓解以及如何缓解的方式。</span><span class="sxs-lookup"><span data-stu-id="483ae-104">The goal is to determine which threats require mitigation and how to mitigate them.</span></span>  
  
 <span data-ttu-id="483ae-105">本部分提供有关 TMA 过程的高级信息。</span><span class="sxs-lookup"><span data-stu-id="483ae-105">This section provides high-level information about the TMA process.</span></span> <span data-ttu-id="483ae-106">有关详细信息，请参阅的第 4 章*编写安全代码，第二版*、 Michael Howard 和 David LeBlanc 编著。</span><span class="sxs-lookup"><span data-stu-id="483ae-106">For more information, see Chapter 4 of *Writing Secure Code, Second edition*, by Michael Howard and David LeBlanc.</span></span>  
  
 <span data-ttu-id="483ae-107">下面是一些 TMA 的好处：</span><span class="sxs-lookup"><span data-stu-id="483ae-107">Some of the benefits of a TMA are:</span></span>  
  
-   <span data-ttu-id="483ae-108">提供更好地了解你的应用程序</span><span class="sxs-lookup"><span data-stu-id="483ae-108">Provides a better understanding of your application</span></span>  
  
-   <span data-ttu-id="483ae-109">可帮助你找到 bug</span><span class="sxs-lookup"><span data-stu-id="483ae-109">Helps you find bugs</span></span>  
  
-   <span data-ttu-id="483ae-110">可帮助了解详细信息中的应用程序的新团队成员</span><span class="sxs-lookup"><span data-stu-id="483ae-110">Can help new team members understand the application in detail</span></span>  
  
-   <span data-ttu-id="483ae-111">包含在你的应用程序生成其他团队的重要信息</span><span class="sxs-lookup"><span data-stu-id="483ae-111">Contains important information for other teams that build on your application</span></span>  
  
-   <span data-ttu-id="483ae-112">用于测试人员</span><span class="sxs-lookup"><span data-stu-id="483ae-112">Useful for testers</span></span>  
  
 <span data-ttu-id="483ae-113">若要执行 TMA 的高级步骤有：</span><span class="sxs-lookup"><span data-stu-id="483ae-113">The high-level steps to perform a TMA are:</span></span>  
  
-   <span data-ttu-id="483ae-114">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="483ae-114">Step 1.</span></span> <span data-ttu-id="483ae-115">收集的背景信息</span><span class="sxs-lookup"><span data-stu-id="483ae-115">Collect Background Information</span></span>  
  
-   <span data-ttu-id="483ae-116">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="483ae-116">Step 2.</span></span> <span data-ttu-id="483ae-117">创建和分析的威胁模型</span><span class="sxs-lookup"><span data-stu-id="483ae-117">Create and Analyze the Threat Model</span></span>  
  
-   <span data-ttu-id="483ae-118">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="483ae-118">Step 3.</span></span> <span data-ttu-id="483ae-119">查看威胁</span><span class="sxs-lookup"><span data-stu-id="483ae-119">Review Threats</span></span>  
  
-   <span data-ttu-id="483ae-120">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="483ae-120">Step 4.</span></span> <span data-ttu-id="483ae-121">标识缓解技术和技术</span><span class="sxs-lookup"><span data-stu-id="483ae-121">Identify Mitigation Techniques and Technologies</span></span>  
  
-   <span data-ttu-id="483ae-122">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="483ae-122">Step 5.</span></span> <span data-ttu-id="483ae-123">文档安全模型和部署注意事项</span><span class="sxs-lookup"><span data-stu-id="483ae-123">Document Security Model and Deployment Considerations</span></span>  
  
-   <span data-ttu-id="483ae-124">步骤 6.</span><span class="sxs-lookup"><span data-stu-id="483ae-124">Step 6.</span></span> <span data-ttu-id="483ae-125">实现和测试缓解措施</span><span class="sxs-lookup"><span data-stu-id="483ae-125">Implement and Test Mitigations</span></span>  
  
-   <span data-ttu-id="483ae-126">步骤 7.</span><span class="sxs-lookup"><span data-stu-id="483ae-126">Step 7.</span></span> <span data-ttu-id="483ae-127">使威胁模型设计与同步</span><span class="sxs-lookup"><span data-stu-id="483ae-127">Keep the Threat Model in Sync with Design</span></span>  
  
## <a name="step-1-collect-background-information"></a><span data-ttu-id="483ae-128">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="483ae-128">Step 1.</span></span> <span data-ttu-id="483ae-129">收集的背景信息</span><span class="sxs-lookup"><span data-stu-id="483ae-129">Collect Background Information</span></span>  
 <span data-ttu-id="483ae-130">要准备成功 TMA，您需要收集一些背景信息。</span><span class="sxs-lookup"><span data-stu-id="483ae-130">To prepare for a successful TMA, you have to collect some background information.</span></span> <span data-ttu-id="483ae-131">它可用于分析你的目标环境 （应用程序、 程序或整个基础结构），如下所示：</span><span class="sxs-lookup"><span data-stu-id="483ae-131">It is useful to analyze your target environment (an application, program, or the whole infrastructure) as follows:</span></span>  
  
-   <span data-ttu-id="483ae-132">标识用例方案。</span><span class="sxs-lookup"><span data-stu-id="483ae-132">Identify use-case scenarios.</span></span> <span data-ttu-id="483ae-133">有关你的目标环境每个用例方案，标识期望你的公司在目标环境上使用目标环境中，任何限制如何。</span><span class="sxs-lookup"><span data-stu-id="483ae-133">For each use-case scenario for your target environment, identify how you expect your company to use the target environment, and any limitations or restrictions on the target environment.</span></span> <span data-ttu-id="483ae-134">此信息可帮助定义的讨论范围之内威胁模型，并提供对资产 （任何类型的值与你的公司，比如数据和计算机） 和入口点的指针。</span><span class="sxs-lookup"><span data-stu-id="483ae-134">This information helps define the scope of the threat model discussion, and provides pointers to assets (anything of value to your company, such as data and computers) and entry points.</span></span>  
  
-   <span data-ttu-id="483ae-135">创建每个方案的数据流关系图 (DFD)。</span><span class="sxs-lookup"><span data-stu-id="483ae-135">Create a data flow diagram (DFD) for each scenario.</span></span> <span data-ttu-id="483ae-136">请确保你在转足够深而无法了解你的威胁。</span><span class="sxs-lookup"><span data-stu-id="483ae-136">Make sure that you go deep enough to understand your threats.</span></span>  
  
-   <span data-ttu-id="483ae-137">确定边界和目标环境的范围。</span><span class="sxs-lookup"><span data-stu-id="483ae-137">Determine the boundaries and scope of the target environment.</span></span>  
  
-   <span data-ttu-id="483ae-138">了解受信任和不受信任的组件之间的边界。</span><span class="sxs-lookup"><span data-stu-id="483ae-138">Understand the boundaries between trusted and untrusted components.</span></span>  
  
-   <span data-ttu-id="483ae-139">了解每个组件的配置和管理模型。</span><span class="sxs-lookup"><span data-stu-id="483ae-139">Understand the configuration and administration model for each component.</span></span>  
  
-   <span data-ttu-id="483ae-140">创建外部依赖项的列表。</span><span class="sxs-lookup"><span data-stu-id="483ae-140">Create a list of external dependencies.</span></span>  
  
-   <span data-ttu-id="483ae-141">创建假设每个组件所依赖的其他组件的列表。</span><span class="sxs-lookup"><span data-stu-id="483ae-141">Create a list of assumptions about other components on which each component depends.</span></span> <span data-ttu-id="483ae-142">这有助于验证跨组件假设、 操作项目和与其他团队的后续项。</span><span class="sxs-lookup"><span data-stu-id="483ae-142">This helps validate cross-component assumptions, action items, and follow-up items with other teams.</span></span>  
  
## <a name="step-2-create-and-analyze-the-threat-model"></a><span data-ttu-id="483ae-143">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="483ae-143">Step 2.</span></span> <span data-ttu-id="483ae-144">创建和分析的威胁模型</span><span class="sxs-lookup"><span data-stu-id="483ae-144">Create and Analyze the Threat Model</span></span>  
 <span data-ttu-id="483ae-145">收集的背景信息后，你应具有威胁模型会议。</span><span class="sxs-lookup"><span data-stu-id="483ae-145">After you collect the background information, you should have a threat model meeting or meetings.</span></span> <span data-ttu-id="483ae-146">请确保每个开发专业 （例如，项目经理、 开发人员和测试人员） 该至少一个成员位于会议。</span><span class="sxs-lookup"><span data-stu-id="483ae-146">Make sure that at least one member of each development discipline (for example, program managers, developers, and testers) is at the meeting.</span></span> <span data-ttu-id="483ae-147">请确保，提醒与会者会议的目标是要查找的威胁，不来修复它们。</span><span class="sxs-lookup"><span data-stu-id="483ae-147">Make sure that you remind the attendees that the goal of the meeting is to find threats, not to fix them.</span></span> <span data-ttu-id="483ae-148">在威胁模型会议中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="483ae-148">During the threat model meeting, do the following:</span></span>  
  
-   <span data-ttu-id="483ae-149">检查每个用例 DFD。</span><span class="sxs-lookup"><span data-stu-id="483ae-149">Examine the DFD for each use case.</span></span> <span data-ttu-id="483ae-150">对于每个用例确定：</span><span class="sxs-lookup"><span data-stu-id="483ae-150">For each use case identify:</span></span>  
  
    -   <span data-ttu-id="483ae-151">入口点</span><span class="sxs-lookup"><span data-stu-id="483ae-151">Entry points</span></span>  
  
    -   <span data-ttu-id="483ae-152">信任边界</span><span class="sxs-lookup"><span data-stu-id="483ae-152">Trust boundaries</span></span>  
  
    -   <span data-ttu-id="483ae-153">从入口点到最终的放置位置 （和后端） 的数据的流</span><span class="sxs-lookup"><span data-stu-id="483ae-153">Flow of data from entry point to final resting location (and back)</span></span>  
  
-   <span data-ttu-id="483ae-154">请注意所涉及的资产。</span><span class="sxs-lookup"><span data-stu-id="483ae-154">Note the assets involved.</span></span>  
  
-   <span data-ttu-id="483ae-155">讨论每个 DFD，并查找以下类别 DFD 中的所有条目中是否有威胁： **S**哄骗标识， **T**篡改数据， **R**epudiation， **我**璝泄露**D**的服务，用以和**E**提升的权限。</span><span class="sxs-lookup"><span data-stu-id="483ae-155">Discuss each DFD, and look for threats in the following categories for all entries in the DFD: **S**poofing identify, **T**ampering with data, **R**epudiation, **I**nformation disclosure, **D**enial of service, and **E**levation of privileges.</span></span>  
  
-   <span data-ttu-id="483ae-156">创建标识的威胁的列表。</span><span class="sxs-lookup"><span data-stu-id="483ae-156">Create a list of the identified threats.</span></span> <span data-ttu-id="483ae-157">我们建议，此列表包括以下： 标题、 （包括威胁树） 的简要说明、 资产 （资产）、 impact(s)、 风险、 缓解技术、 缓解状态和大量 bug。</span><span class="sxs-lookup"><span data-stu-id="483ae-157">We recommend that this list include the following: title, brief description (including threat trees), asset (asset), impact(s), risk, mitigation techniques, mitigation status, and a bug number.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="483ae-158">查看威胁，可以添加风险、 缓解技术和缓解状态。</span><span class="sxs-lookup"><span data-stu-id="483ae-158">You can add risk, mitigation techniques, and mitigation status as you review the threats.</span></span> <span data-ttu-id="483ae-159">不占用太多时间这些区域中在威胁模型会议过程。</span><span class="sxs-lookup"><span data-stu-id="483ae-159">Do not spend too much time in these areas during the threat model meeting.</span></span>  
  
## <a name="step-3-review-threats"></a><span data-ttu-id="483ae-160">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="483ae-160">Step 3.</span></span> <span data-ttu-id="483ae-161">查看威胁</span><span class="sxs-lookup"><span data-stu-id="483ae-161">Review Threats</span></span>  
 <span data-ttu-id="483ae-162">确定威胁到你的环境后，你必须排名每种威胁的风险，并确定你想要对每种威胁做出响应。</span><span class="sxs-lookup"><span data-stu-id="483ae-162">After you have identified the threats to your environment, you must rank the risk of each threat and determine how you want to respond to each threat.</span></span> <span data-ttu-id="483ae-163">与其他团队会议或通过电子邮件时，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="483ae-163">You can do this with additional team meetings or through e-mail.</span></span> <span data-ttu-id="483ae-164">您可以使用以下的效果类别来计算风险暴露程度： **D**amage 潜在， **R**eproducibility， **E**xploitability， ffected 用户和**D**iscoverability。</span><span class="sxs-lookup"><span data-stu-id="483ae-164">You can use the following effect categories to calculate risk exposure: **D**amage potential, **R**eproducibility, **E**xploitability, **A**ffected users, and **D**iscoverability.</span></span>  
  
 <span data-ttu-id="483ae-165">对你按风险设置优先级的目标环境的威胁的列表后，你必须确定将如何响应每种威胁。</span><span class="sxs-lookup"><span data-stu-id="483ae-165">After you have a list of the threats to your target environment prioritized by risk, you must determine how you will respond to each threat.</span></span> <span data-ttu-id="483ae-166">您的响应可以是不执行任何操作 （极少数情况下是一个不错的选择）、 用户有关的潜在问题，则发出警告，删除此问题，或解决此问题。</span><span class="sxs-lookup"><span data-stu-id="483ae-166">Your response can be to do nothing (rarely a good choice), warn users about the potential problem, remove the problem, or fix the problem.</span></span>  
  
## <a name="step-4-identify-mitigation-techniques-and-technologies"></a><span data-ttu-id="483ae-167">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="483ae-167">Step 4.</span></span> <span data-ttu-id="483ae-168">标识缓解技术和技术</span><span class="sxs-lookup"><span data-stu-id="483ae-168">Identify Mitigation Techniques and Technologies</span></span>  
 <span data-ttu-id="483ae-169">确定哪些威胁将修复后，你必须确定用于每种威胁，并最适合的技术降低的每种威胁的影响的可用缓解技术。</span><span class="sxs-lookup"><span data-stu-id="483ae-169">After you identify which threats you will fix, you must determine the available mitigation techniques for each threat, and the most appropriate technology to reduce the effect of each threat.</span></span>  
  
 <span data-ttu-id="483ae-170">例如，具体取决于你的目标环境的详细信息，可以通过使用授权技术来减少数据篡改威胁的效果。</span><span class="sxs-lookup"><span data-stu-id="483ae-170">For example, depending on the details of your target environment, you can reduce the effect of data-tamper threats by using authorization techniques.</span></span> <span data-ttu-id="483ae-171">然后，你需要确定适当的授权技术来使用 （针对示例、 自定义访问控制列表 (Dacl)、 权限或 IP 限制）。</span><span class="sxs-lookup"><span data-stu-id="483ae-171">You then have to determine the appropriate authorization technology to use (for example, discretionary access control lists (DACLs), permissions, or IP restrictions).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="483ae-172">缓解技术和技术以使用计算时，你必须考虑什么合理业务的公司和你的公司有可能会影响缓解技术，若要选择的任何策略。</span><span class="sxs-lookup"><span data-stu-id="483ae-172">When you evaluate mitigation techniques and technologies to use, you must consider what makes business sense for your company, and any policies your company has that might affect the mitigation technique to choose.</span></span>  
  
 <span data-ttu-id="483ae-173">完成 TMA 后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="483ae-173">After you complete the TMA, do the following:</span></span>  
  
-   <span data-ttu-id="483ae-174">文档的安全模型和部署注意事项</span><span class="sxs-lookup"><span data-stu-id="483ae-174">Document the security model and deployment considerations</span></span>  
  
-   <span data-ttu-id="483ae-175">实现和测试的缓解措施</span><span class="sxs-lookup"><span data-stu-id="483ae-175">Implement and test mitigations</span></span>  
  
-   <span data-ttu-id="483ae-176">保留与设计保持同步的威胁模型</span><span class="sxs-lookup"><span data-stu-id="483ae-176">Keep the threat model synchronized with design</span></span>  
  
## <a name="step-5-document-security-model-and-deployment-considerations"></a><span data-ttu-id="483ae-177">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="483ae-177">Step 5.</span></span> <span data-ttu-id="483ae-178">文档安全模型和部署注意事项</span><span class="sxs-lookup"><span data-stu-id="483ae-178">Document Security Model and Deployment Considerations</span></span>  
 <span data-ttu-id="483ae-179">很有价值文档期间 TMA 发现和您决定如何减少对你的目标环境的威胁的效果。</span><span class="sxs-lookup"><span data-stu-id="483ae-179">It is valuable to document what you discover during the TMA and how you decide to reduce the effect of the threats to your target environment.</span></span> <span data-ttu-id="483ae-180">本文档可以是对质量保证 (QA)、 测试、 支持和操作人员有用的。</span><span class="sxs-lookup"><span data-stu-id="483ae-180">This documentation can be useful to quality assurance (QA), test, support, and operations personnel.</span></span> <span data-ttu-id="483ae-181">包含有关其他应用程序进行交互或与你的目标环境，以及防火墙和拓扑的建议和要求的接口。</span><span class="sxs-lookup"><span data-stu-id="483ae-181">Include information about other applications that interact or interface with your target environment, and the firewall and topology recommendations and requirements.</span></span>  
  
## <a name="step-6-implement-and-test-mitigations"></a><span data-ttu-id="483ae-182">步骤 6.</span><span class="sxs-lookup"><span data-stu-id="483ae-182">Step 6.</span></span> <span data-ttu-id="483ae-183">实现和测试缓解措施</span><span class="sxs-lookup"><span data-stu-id="483ae-183">Implement and Test Mitigations</span></span>  
 <span data-ttu-id="483ae-184">时你的团队已准备好修复过程 TMA 中标识的威胁，请确保使用开发和部署清单来遵循安全代码和部署标准，将帮助最大程度减少引入新的威胁。</span><span class="sxs-lookup"><span data-stu-id="483ae-184">When your team is ready to fix threats identified during the TMA, make sure you use development and deployment checklists to follow secure code and deployment standards that will help minimize the introduction of new threats.</span></span>  
  
 <span data-ttu-id="483ae-185">实现一种缓解措施后，请确保测试它以确保它提供的威胁所需的保护级别。</span><span class="sxs-lookup"><span data-stu-id="483ae-185">After you implement a mitigation, make sure you test it to make sure it provides the level of protection that you want for the threat.</span></span>  
  
## <a name="step-7-keep-the-threat-model-in-sync-with-design"></a><span data-ttu-id="483ae-186">步骤 7.</span><span class="sxs-lookup"><span data-stu-id="483ae-186">Step 7.</span></span> <span data-ttu-id="483ae-187">使威胁模型设计与同步</span><span class="sxs-lookup"><span data-stu-id="483ae-187">Keep the Threat Model in Sync with Design</span></span>  
 <span data-ttu-id="483ae-188">当添加新的应用程序时，服务器和其他元素添加到你的环境，请确保你重新访问的威胁模型分析结果，并执行的任何新功能的 TMAs。</span><span class="sxs-lookup"><span data-stu-id="483ae-188">As you add new applications, servers, and other elements to your environment, make sure that you revisit the findings of the threat model analysis and do TMAs for any new functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483ae-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="483ae-189">See Also</span></span>  
<span data-ttu-id="483ae-190">[对于小型到中型公司的安全案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="483ae-190">[Security Case Studies for Small to Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="483ae-191">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="483ae-191">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)