---
title: 性能评估阶段 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 120706f9-9fa1-4f41-bd89-3b9eada940ad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32d3c32158bc5a334aa614f03aa1a86afd6fffd9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301885"
---
# <a name="phases-of-a-performance-assessment"></a><span data-ttu-id="5bfa8-102">性能评估阶段</span><span class="sxs-lookup"><span data-stu-id="5bfa8-102">Phases of a Performance Assessment</span></span>
<span data-ttu-id="5bfa8-103">主要目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是尽可能容纳尽可能多的处理方案提供最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-103">One of the primary goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="5bfa8-104">由于此极大的灵活性，面对的 BizTalk 解决方案的开发人员的主要挑战之一是确定如何在中提供的功能的最佳使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为了满足其业务需求。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to meet their business needs.</span></span> <span data-ttu-id="5bfa8-105">优化 BizTalk Server 解决方案的性能时，这种灵活性也带来一个挑战。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-105">This flexibility also poses a challenge when optimizing the performance of a BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="5bfa8-106">本部分介绍的方法，用于通过参与 BizTalk Server 性能评估优化 BizTalk Server 解决方案的性能。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-106">This section describes the methodology that should be used to optimize the performance of a BizTalk Server solution by engaging in a BizTalk Server performance assessment.</span></span> <span data-ttu-id="5bfa8-107">BizTalk Server 性能评估用于最大化特定的 BizTalk Server 解决方案的性能。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-107">A BizTalk Server performance assessment is used to maximize the performance of a particular BizTalk Server solution.</span></span> <span data-ttu-id="5bfa8-108">为了获得 BizTalk Server 性能评估的最大好处，性能评估应该被划分为以下五个不同步骤/的阶段：</span><span class="sxs-lookup"><span data-stu-id="5bfa8-108">In order to gain the maximum benefit from a BizTalk Server performance assessment, the performance assessment should be divided into the following five distinct steps/phases:</span></span>  
  
1.  <span data-ttu-id="5bfa8-109">范围</span><span class="sxs-lookup"><span data-stu-id="5bfa8-109">Scope</span></span>  
  
2.  <span data-ttu-id="5bfa8-110">计划</span><span class="sxs-lookup"><span data-stu-id="5bfa8-110">Plan</span></span>  
  
3.  <span data-ttu-id="5bfa8-111">准备</span><span class="sxs-lookup"><span data-stu-id="5bfa8-111">Prepare</span></span>  
  
4.  <span data-ttu-id="5bfa8-112">生成实验室</span><span class="sxs-lookup"><span data-stu-id="5bfa8-112">Build lab</span></span>  
  
5.  <span data-ttu-id="5bfa8-113">Execute</span><span class="sxs-lookup"><span data-stu-id="5bfa8-113">Execute</span></span>  
  
 <span data-ttu-id="5bfa8-114">本主题介绍每个更详细介绍这些阶段。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-114">This topic describes each of these phases in greater detail.</span></span>  
  
 <span data-ttu-id="5bfa8-115">![性能评估流程阶段](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span><span class="sxs-lookup"><span data-stu-id="5bfa8-115">![Phases of a performance assessment process](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span></span>  
<span data-ttu-id="5bfa8-116">BizTalk Server 性能评估的阶段</span><span class="sxs-lookup"><span data-stu-id="5bfa8-116">Phases of a BizTalk Server performance assessment</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bfa8-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="5bfa8-117">In This Section</span></span>  
  
-   <span data-ttu-id="5bfa8-118">[阶段 1： 范围评估](../technical-guides/phase-1-scoping-the-assessment.md)-介绍建立性能评估的作用域时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-118">[Phase 1: Scoping the Assessment](../technical-guides/phase-1-scoping-the-assessment.md) - Describes the steps that should be followed when establishing the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="5bfa8-119">[阶段 2： 规划评估](../technical-guides/phase-2-planning-the-assessment.md)– 介绍如何创建解决方案里程碑时间线。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-119">[Phase 2: Planning the Assessment](../technical-guides/phase-2-planning-the-assessment.md) – Describes how to create a solution milestones timeline.</span></span> <span data-ttu-id="5bfa8-120">使用这种方式主计划以清楚地说明时应满足进行测试解决方案的预期的目标。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-120">This is used as a master plan to clearly document when expected goals for the testing of the solution should be met.</span></span>  
  
-   <span data-ttu-id="5bfa8-121">[阶段 3： 准备评估](../technical-guides/phase-3-preparing-for-the-assessment.md)– 介绍如何提供详细的体系结构关系图的解决方案和解决方案所使用的硬件配置的特定方面。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-121">[Phase 3: Preparing for the Assessment](../technical-guides/phase-3-preparing-for-the-assessment.md) – Describes how to provide a detailed architectural diagram of the solution and specific aspects of the hardware configuration used by the solution.</span></span>  
  
-   <span data-ttu-id="5bfa8-122">[阶段 4： 构建评估环境](../technical-guides/phase-4-building-the-assessment-environment.md)– 描述的硬件和根据详细的设计与以前已建立的解决方案平台的应用程序的安装。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-122">[Phase 4: Building the Assessment Environment](../technical-guides/phase-4-building-the-assessment-environment.md) – Describes installation of hardware and applications according to the detailed design of the solution platform that was established previously.</span></span>  
  
-   <span data-ttu-id="5bfa8-123">[阶段 5： 执行评估](../technical-guides/phase-5-executing-the-assessment.md)– 提供有关生成通过自动的负载测试和如何检测并消除解决方案中的任何瓶颈的性能数据的信息。</span><span class="sxs-lookup"><span data-stu-id="5bfa8-123">[Phase 5: Executing the Assessment](../technical-guides/phase-5-executing-the-assessment.md) – Provides information about generating performance data via automated load testing and how to detect and eliminate any bottlenecks in the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bfa8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bfa8-124">See Also</span></span>  
 [<span data-ttu-id="5bfa8-125">BizTalk Server 性能测试方法</span><span class="sxs-lookup"><span data-stu-id="5bfa8-125">BizTalk Server Performance Testing Methodology</span></span>](../technical-guides/biztalk-server-performance-testing-methodology.md)