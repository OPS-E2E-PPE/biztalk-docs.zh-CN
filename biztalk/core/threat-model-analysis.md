---
title: 威胁模型分析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TMA, about TMA
- TMA
- TMA, procedure steps
ms.assetid: dfbf46aa-0a35-4925-8718-df8591efc279
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e16ae71495980e3897ab1e847600222b1c276d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399986"
---
# <a name="threat-model-analysis"></a><span data-ttu-id="72536-102">威胁模型分析</span><span class="sxs-lookup"><span data-stu-id="72536-102">Threat Model Analysis</span></span>
<span data-ttu-id="72536-103">威胁模型分析 (TMA) 是可以帮助您确定对产品、 应用程序、 网络或环境中，带来安全风险分析和攻击可以出现。</span><span class="sxs-lookup"><span data-stu-id="72536-103">A threat model analysis (TMA) is an analysis that helps determine the security risks posed to a product, application, network, or environment, and how attacks can show up.</span></span> <span data-ttu-id="72536-104">目标是确定哪些威胁需要迁移以及如何缓解这些问题。</span><span class="sxs-lookup"><span data-stu-id="72536-104">The goal is to determine which threats require mitigation and how to mitigate them.</span></span>  
  
 <span data-ttu-id="72536-105">本部分提供有关 TMA 过程的高级信息。</span><span class="sxs-lookup"><span data-stu-id="72536-105">This section provides high-level information about the TMA process.</span></span> <span data-ttu-id="72536-106">有关详细信息，请参阅的第 4 章*Writing Secure Code，Second edition*，作者为 Michael Howard 和 David LeBlanc。</span><span class="sxs-lookup"><span data-stu-id="72536-106">For more information, see Chapter 4 of *Writing Secure Code, Second edition*, by Michael Howard and David LeBlanc.</span></span>  
  
 <span data-ttu-id="72536-107">下面是一些 TMA 的好处：</span><span class="sxs-lookup"><span data-stu-id="72536-107">Some of the benefits of a TMA are:</span></span>  
  
- <span data-ttu-id="72536-108">提供了更好地了解你的应用程序</span><span class="sxs-lookup"><span data-stu-id="72536-108">Provides a better understanding of your application</span></span>  
  
- <span data-ttu-id="72536-109">可帮助你发现 bug</span><span class="sxs-lookup"><span data-stu-id="72536-109">Helps you find bugs</span></span>  
  
- <span data-ttu-id="72536-110">可帮助了解详细信息中的应用程序的新团队成员</span><span class="sxs-lookup"><span data-stu-id="72536-110">Can help new team members understand the application in detail</span></span>  
  
- <span data-ttu-id="72536-111">包含在你的应用程序上生成的其他团队的重要信息</span><span class="sxs-lookup"><span data-stu-id="72536-111">Contains important information for other teams that build on your application</span></span>  
  
- <span data-ttu-id="72536-112">适用于测试人员</span><span class="sxs-lookup"><span data-stu-id="72536-112">Useful for testers</span></span>  
  
  <span data-ttu-id="72536-113">若要执行 TMA 的高级步骤有：</span><span class="sxs-lookup"><span data-stu-id="72536-113">The high-level steps to perform a TMA are:</span></span>  
  
- <span data-ttu-id="72536-114">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="72536-114">Step 1.</span></span> <span data-ttu-id="72536-115">收集背景信息</span><span class="sxs-lookup"><span data-stu-id="72536-115">Collect Background Information</span></span>  
  
- <span data-ttu-id="72536-116">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="72536-116">Step 2.</span></span> <span data-ttu-id="72536-117">创建和分析威胁模型</span><span class="sxs-lookup"><span data-stu-id="72536-117">Create and Analyze the Threat Model</span></span>  
  
- <span data-ttu-id="72536-118">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="72536-118">Step 3.</span></span> <span data-ttu-id="72536-119">查看威胁</span><span class="sxs-lookup"><span data-stu-id="72536-119">Review Threats</span></span>  
  
- <span data-ttu-id="72536-120">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="72536-120">Step 4.</span></span> <span data-ttu-id="72536-121">确定缓解措施</span><span class="sxs-lookup"><span data-stu-id="72536-121">Identify Mitigation Techniques and Technologies</span></span>  
  
- <span data-ttu-id="72536-122">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="72536-122">Step 5.</span></span> <span data-ttu-id="72536-123">文档安全模型和部署注意事项</span><span class="sxs-lookup"><span data-stu-id="72536-123">Document Security Model and Deployment Considerations</span></span>  
  
- <span data-ttu-id="72536-124">步骤 6.</span><span class="sxs-lookup"><span data-stu-id="72536-124">Step 6.</span></span> <span data-ttu-id="72536-125">实现和测试缓解措施</span><span class="sxs-lookup"><span data-stu-id="72536-125">Implement and Test Mitigations</span></span>  
  
- <span data-ttu-id="72536-126">步骤 7.</span><span class="sxs-lookup"><span data-stu-id="72536-126">Step 7.</span></span> <span data-ttu-id="72536-127">使威胁模型与设计保持同步</span><span class="sxs-lookup"><span data-stu-id="72536-127">Keep the Threat Model in Sync with Design</span></span>  
  
## <a name="step-1-collect-background-information"></a><span data-ttu-id="72536-128">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="72536-128">Step 1.</span></span> <span data-ttu-id="72536-129">收集背景信息</span><span class="sxs-lookup"><span data-stu-id="72536-129">Collect Background Information</span></span>  
 <span data-ttu-id="72536-130">若要准备成功 TMA，必须收集一些背景信息。</span><span class="sxs-lookup"><span data-stu-id="72536-130">To prepare for a successful TMA, you have to collect some background information.</span></span> <span data-ttu-id="72536-131">它可用于分析目标环境 （应用程序、 程序或整个基础结构），如下所示：</span><span class="sxs-lookup"><span data-stu-id="72536-131">It is useful to analyze your target environment (an application, program, or the whole infrastructure) as follows:</span></span>  
  
-   <span data-ttu-id="72536-132">确定用例场景。</span><span class="sxs-lookup"><span data-stu-id="72536-132">Identify use-case scenarios.</span></span> <span data-ttu-id="72536-133">每个用例方案的目标环境，识别期望在目标环境中使用目标环境中，任何限制你公司的方式。</span><span class="sxs-lookup"><span data-stu-id="72536-133">For each use-case scenario for your target environment, identify how you expect your company to use the target environment, and any limitations or restrictions on the target environment.</span></span> <span data-ttu-id="72536-134">此信息可帮助定义的作用域的威胁模型讨论，并提供对资产 （任何类型的值与你的公司，如数据和计算机） 和入口点的指针。</span><span class="sxs-lookup"><span data-stu-id="72536-134">This information helps define the scope of the threat model discussion, and provides pointers to assets (anything of value to your company, such as data and computers) and entry points.</span></span>  
  
-   <span data-ttu-id="72536-135">创建每个方案的数据数据流关系图 (DFD)。</span><span class="sxs-lookup"><span data-stu-id="72536-135">Create a data flow diagram (DFD) for each scenario.</span></span> <span data-ttu-id="72536-136">请确保你在转足够深入，若要了解您的威胁。</span><span class="sxs-lookup"><span data-stu-id="72536-136">Make sure that you go deep enough to understand your threats.</span></span>  
  
-   <span data-ttu-id="72536-137">确定边界和目标环境的范围。</span><span class="sxs-lookup"><span data-stu-id="72536-137">Determine the boundaries and scope of the target environment.</span></span>  
  
-   <span data-ttu-id="72536-138">了解受信任和不受信任的组件之间的边界。</span><span class="sxs-lookup"><span data-stu-id="72536-138">Understand the boundaries between trusted and untrusted components.</span></span>  
  
-   <span data-ttu-id="72536-139">了解每个组件的配置和管理模型。</span><span class="sxs-lookup"><span data-stu-id="72536-139">Understand the configuration and administration model for each component.</span></span>  
  
-   <span data-ttu-id="72536-140">创建外部依赖关系的列表。</span><span class="sxs-lookup"><span data-stu-id="72536-140">Create a list of external dependencies.</span></span>  
  
-   <span data-ttu-id="72536-141">创建一系列有关每个组件所依赖的其他组件的假设。</span><span class="sxs-lookup"><span data-stu-id="72536-141">Create a list of assumptions about other components on which each component depends.</span></span> <span data-ttu-id="72536-142">这有助于验证跨组件假设、 操作项和与其他团队的后续项。</span><span class="sxs-lookup"><span data-stu-id="72536-142">This helps validate cross-component assumptions, action items, and follow-up items with other teams.</span></span>  
  
## <a name="step-2-create-and-analyze-the-threat-model"></a><span data-ttu-id="72536-143">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="72536-143">Step 2.</span></span> <span data-ttu-id="72536-144">创建和分析威胁模型</span><span class="sxs-lookup"><span data-stu-id="72536-144">Create and Analyze the Threat Model</span></span>  
 <span data-ttu-id="72536-145">收集背景信息后，应具有威胁模型会议。</span><span class="sxs-lookup"><span data-stu-id="72536-145">After you collect the background information, you should have a threat model meeting or meetings.</span></span> <span data-ttu-id="72536-146">请确保每个开发部门 （例如，项目经理、 开发人员和测试人员） 的至少一个成员是在会议上。</span><span class="sxs-lookup"><span data-stu-id="72536-146">Make sure that at least one member of each development discipline (for example, program managers, developers, and testers) is at the meeting.</span></span> <span data-ttu-id="72536-147">请确保，提醒与会者会议旨在找出威胁，不希望修复问题。</span><span class="sxs-lookup"><span data-stu-id="72536-147">Make sure that you remind the attendees that the goal of the meeting is to find threats, not to fix them.</span></span> <span data-ttu-id="72536-148">在威胁模型会议中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="72536-148">During the threat model meeting, do the following:</span></span>  
  
-   <span data-ttu-id="72536-149">检查每个用例的 dfd:。</span><span class="sxs-lookup"><span data-stu-id="72536-149">Examine the DFD for each use case.</span></span> <span data-ttu-id="72536-150">对于每个用例确定：</span><span class="sxs-lookup"><span data-stu-id="72536-150">For each use case identify:</span></span>  
  
    -   <span data-ttu-id="72536-151">入口点</span><span class="sxs-lookup"><span data-stu-id="72536-151">Entry points</span></span>  
  
    -   <span data-ttu-id="72536-152">信任边界</span><span class="sxs-lookup"><span data-stu-id="72536-152">Trust boundaries</span></span>  
  
    -   <span data-ttu-id="72536-153">将数据从入口点到最终静止的位置 （和后端） 的流</span><span class="sxs-lookup"><span data-stu-id="72536-153">Flow of data from entry point to final resting location (and back)</span></span>  
  
-   <span data-ttu-id="72536-154">请注意所涉及的资产。</span><span class="sxs-lookup"><span data-stu-id="72536-154">Note the assets involved.</span></span>  
  
-   <span data-ttu-id="72536-155">讨论每个 DFD 和威胁的 DFD 中的所有条目的以下类别中查找：**S**poofing 标识，请**T**篡改数据， **R**epudiation，**我**表示信息泄露**D**表示拒绝服务，并**E**表示特权提升。</span><span class="sxs-lookup"><span data-stu-id="72536-155">Discuss each DFD, and look for threats in the following categories for all entries in the DFD: **S**poofing identify, **T**ampering with data, **R**epudiation, **I**nformation disclosure, **D**enial of service, and **E**levation of privileges.</span></span>  
  
-   <span data-ttu-id="72536-156">创建威胁分类列表。</span><span class="sxs-lookup"><span data-stu-id="72536-156">Create a list of the identified threats.</span></span> <span data-ttu-id="72536-157">我们建议，此列表包括以下： 标题、 简要说明 （包括威胁树）、 资产 （资产）、 impact(s)、 风险、 缓解措施，缓解状态和 bug 数。</span><span class="sxs-lookup"><span data-stu-id="72536-157">We recommend that this list include the following: title, brief description (including threat trees), asset (asset), impact(s), risk, mitigation techniques, mitigation status, and a bug number.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72536-158">查看威胁，可以添加风险、 缓解措施和缓解状态。</span><span class="sxs-lookup"><span data-stu-id="72536-158">You can add risk, mitigation techniques, and mitigation status as you review the threats.</span></span> <span data-ttu-id="72536-159">不占用太多时间在这些领域在威胁模型会议。</span><span class="sxs-lookup"><span data-stu-id="72536-159">Do not spend too much time in these areas during the threat model meeting.</span></span>  
  
## <a name="step-3-review-threats"></a><span data-ttu-id="72536-160">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="72536-160">Step 3.</span></span> <span data-ttu-id="72536-161">查看威胁</span><span class="sxs-lookup"><span data-stu-id="72536-161">Review Threats</span></span>  
 <span data-ttu-id="72536-162">确定对你的环境的威胁后，必须对每个威胁的风险并确定你想要对每个威胁做出响应。</span><span class="sxs-lookup"><span data-stu-id="72536-162">After you have identified the threats to your environment, you must rank the risk of each threat and determine how you want to respond to each threat.</span></span> <span data-ttu-id="72536-163">与其他团队会议或通过电子邮件时，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="72536-163">You can do this with additional team meetings or through e-mail.</span></span> <span data-ttu-id="72536-164">可以使用以下影响类别来计算风险危害：**D**潜在，损害**R**再现， **E**xploitability，**一个**可用户并**D**iscoverability。</span><span class="sxs-lookup"><span data-stu-id="72536-164">You can use the following effect categories to calculate risk exposure: **D**amage potential, **R**eproducibility, **E**xploitability, **A**ffected users, and **D**iscoverability.</span></span>  
  
 <span data-ttu-id="72536-165">对你按风险设置优先级的目标环境的威胁的列表后，您必须确定将如何应对每个威胁。</span><span class="sxs-lookup"><span data-stu-id="72536-165">After you have a list of the threats to your target environment prioritized by risk, you must determine how you will respond to each threat.</span></span> <span data-ttu-id="72536-166">您的响应可以是不执行任何操作 （很少是一个不错的选择）、 有关潜在问题的用户，则发出警告，删除该问题，或解决该问题。</span><span class="sxs-lookup"><span data-stu-id="72536-166">Your response can be to do nothing (rarely a good choice), warn users about the potential problem, remove the problem, or fix the problem.</span></span>  
  
## <a name="step-4-identify-mitigation-techniques-and-technologies"></a><span data-ttu-id="72536-167">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="72536-167">Step 4.</span></span> <span data-ttu-id="72536-168">确定缓解措施</span><span class="sxs-lookup"><span data-stu-id="72536-168">Identify Mitigation Techniques and Technologies</span></span>  
 <span data-ttu-id="72536-169">确定将修复哪些威胁后，您必须确定每种威胁，并减少每个威胁的影响最合适的技术可缓解措施。</span><span class="sxs-lookup"><span data-stu-id="72536-169">After you identify which threats you will fix, you must determine the available mitigation techniques for each threat, and the most appropriate technology to reduce the effect of each threat.</span></span>  
  
 <span data-ttu-id="72536-170">例如，具体取决于你的目标环境的详细信息，可以通过使用授权技术降低数据篡改威胁的影响。</span><span class="sxs-lookup"><span data-stu-id="72536-170">For example, depending on the details of your target environment, you can reduce the effect of data-tamper threats by using authorization techniques.</span></span> <span data-ttu-id="72536-171">您然后必须确定要使用 （如自由访问控制列表 (Dacl) 中，权限或 IP 限制） 的相应授权技术。</span><span class="sxs-lookup"><span data-stu-id="72536-171">You then have to determine the appropriate authorization technology to use (for example, discretionary access control lists (DACLs), permissions, or IP restrictions).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="72536-172">当你评估缓解措施和技术来使用时，必须考虑适合业务的公司和你的公司有可能会影响要选择的缓解技术的任何策略。</span><span class="sxs-lookup"><span data-stu-id="72536-172">When you evaluate mitigation techniques and technologies to use, you must consider what makes business sense for your company, and any policies your company has that might affect the mitigation technique to choose.</span></span>  
  
 <span data-ttu-id="72536-173">完成 TMA 后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72536-173">After you complete the TMA, do the following:</span></span>  
  
-   <span data-ttu-id="72536-174">文档的安全模型和部署注意事项</span><span class="sxs-lookup"><span data-stu-id="72536-174">Document the security model and deployment considerations</span></span>  
  
-   <span data-ttu-id="72536-175">实现和测试的缓解措施</span><span class="sxs-lookup"><span data-stu-id="72536-175">Implement and test mitigations</span></span>  
  
-   <span data-ttu-id="72536-176">保留与设计保持同步的威胁模型</span><span class="sxs-lookup"><span data-stu-id="72536-176">Keep the threat model synchronized with design</span></span>  
  
## <a name="step-5-document-security-model-and-deployment-considerations"></a><span data-ttu-id="72536-177">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="72536-177">Step 5.</span></span> <span data-ttu-id="72536-178">文档安全模型和部署注意事项</span><span class="sxs-lookup"><span data-stu-id="72536-178">Document Security Model and Deployment Considerations</span></span>  
 <span data-ttu-id="72536-179">它是有价值记录期间 TMA 发现和您决定如何降低对你的目标环境的威胁的影响。</span><span class="sxs-lookup"><span data-stu-id="72536-179">It is valuable to document what you discover during the TMA and how you decide to reduce the effect of the threats to your target environment.</span></span> <span data-ttu-id="72536-180">本文档可为质量保证 (QA)、 测试、 支持和运营人员。</span><span class="sxs-lookup"><span data-stu-id="72536-180">This documentation can be useful to quality assurance (QA), test, support, and operations personnel.</span></span> <span data-ttu-id="72536-181">包含有关其他交互的应用程序或使用你的目标环境，以及防火墙和拓扑的建议和要求的接口。</span><span class="sxs-lookup"><span data-stu-id="72536-181">Include information about other applications that interact or interface with your target environment, and the firewall and topology recommendations and requirements.</span></span>  
  
## <a name="step-6-implement-and-test-mitigations"></a><span data-ttu-id="72536-182">步骤 6.</span><span class="sxs-lookup"><span data-stu-id="72536-182">Step 6.</span></span> <span data-ttu-id="72536-183">实现和测试缓解措施</span><span class="sxs-lookup"><span data-stu-id="72536-183">Implement and Test Mitigations</span></span>  
 <span data-ttu-id="72536-184">当你的团队已准备好修复 TMA 期间识别的威胁时，请确保使用开发和部署检查表遵循安全的代码和部署标准，可帮助最大程度减少引入了新的威胁。</span><span class="sxs-lookup"><span data-stu-id="72536-184">When your team is ready to fix threats identified during the TMA, make sure you use development and deployment checklists to follow secure code and deployment standards that will help minimize the introduction of new threats.</span></span>  
  
 <span data-ttu-id="72536-185">实现一种缓解后，请确保测试，以确保它提供的威胁所需的保护级别。</span><span class="sxs-lookup"><span data-stu-id="72536-185">After you implement a mitigation, make sure you test it to make sure it provides the level of protection that you want for the threat.</span></span>  
  
## <a name="step-7-keep-the-threat-model-in-sync-with-design"></a><span data-ttu-id="72536-186">步骤 7.</span><span class="sxs-lookup"><span data-stu-id="72536-186">Step 7.</span></span> <span data-ttu-id="72536-187">使威胁模型与设计保持同步</span><span class="sxs-lookup"><span data-stu-id="72536-187">Keep the Threat Model in Sync with Design</span></span>  
 <span data-ttu-id="72536-188">添加新的应用程序时，服务器和其他元素添加到你的环境，请确保你重新访问了威胁模型分析的发现结果并执行 TMAs 任何新功能。</span><span class="sxs-lookup"><span data-stu-id="72536-188">As you add new applications, servers, and other elements to your environment, make sure that you revisit the findings of the threat model analysis and do TMAs for any new functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72536-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="72536-189">See Also</span></span>  
<span data-ttu-id="72536-190">[对于小型到中型公司的安全性案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="72536-190">[Security Case Studies for Small to Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="72536-191">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="72536-191">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)