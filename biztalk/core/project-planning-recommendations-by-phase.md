---
title: "按阶段项目规划的建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- planning, performance
- performance, planning
ms.assetid: 422f05e3-5ad4-4f47-9be3-c229a20a6ef3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8886f3e52d347651630a4cafb716049fdf19fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="project-planning-recommendations-by-phase"></a><span data-ttu-id="312b2-102">分阶段描述的项目规划建议</span><span class="sxs-lookup"><span data-stu-id="312b2-102">Project Planning Recommendations by Phase</span></span>
<span data-ttu-id="312b2-103">目前，存在多种软件开发生命周期模型，每一种模型都有自己的方法、优点和局限性。</span><span class="sxs-lookup"><span data-stu-id="312b2-103">There are a number of software development lifecycle models in existence today, each with their own approaches, benefits, and limitations.</span></span> <span data-ttu-id="312b2-104">本部分的目标是提供一组相关建议，来帮助您恰当地成功规划 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发项目。</span><span class="sxs-lookup"><span data-stu-id="312b2-104">The goal of this section is to provide a set of recommendations that will help you plan appropriately for a successful [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development project.</span></span>  
  
 <span data-ttu-id="312b2-105">在本部分中，我们使用在 Microsoft 广泛采用的生命周期模型。</span><span class="sxs-lookup"><span data-stu-id="312b2-105">In this section, we use the lifecycle model employed broadly at Microsoft.</span></span> <span data-ttu-id="312b2-106">此模型是迭代式和瀑布式生命周期模型的组合。</span><span class="sxs-lookup"><span data-stu-id="312b2-106">This model is a combination of iterative and waterfall lifecycle models.</span></span>  
  
 <span data-ttu-id="312b2-107">此模型包含五个阶段，这些阶段的边界为项目定义了一组连续的里程碑。</span><span class="sxs-lookup"><span data-stu-id="312b2-107">In this model, there are five phases whose boundaries define a sequential set of milestones for the project.</span></span> <span data-ttu-id="312b2-108">这些阶段按执行顺序排列如下：</span><span class="sxs-lookup"><span data-stu-id="312b2-108">The phases, in order of execution, are as follows:</span></span>  
  
-   <span data-ttu-id="312b2-109">**要求**。</span><span class="sxs-lookup"><span data-stu-id="312b2-109">**Requirements**.</span></span> <span data-ttu-id="312b2-110">用户需求在定义要生成的内容的功能规范中进行捕获。</span><span class="sxs-lookup"><span data-stu-id="312b2-110">User requirements are captured in functional specifications that define what is to be built.</span></span>  
  
-   <span data-ttu-id="312b2-111">**设计**。</span><span class="sxs-lookup"><span data-stu-id="312b2-111">**Design**.</span></span> <span data-ttu-id="312b2-112">根据功能需求创建物理设计规范，并构建原型以验证设计思路和研究平台功能。</span><span class="sxs-lookup"><span data-stu-id="312b2-112">Based on the functional requirements, physical design specifications are created and prototyping is conducted to verify design ideas and investigate platform capabilities.</span></span>  
  
-   <span data-ttu-id="312b2-113">**实现**。</span><span class="sxs-lookup"><span data-stu-id="312b2-113">**Implementation**.</span></span> <span data-ttu-id="312b2-114">使用设计和功能规范完成软件编码。</span><span class="sxs-lookup"><span data-stu-id="312b2-114">Using the design and functional specifications, the software coding is done.</span></span>  
  
-   <span data-ttu-id="312b2-115">**验证**。</span><span class="sxs-lookup"><span data-stu-id="312b2-115">**Verification**.</span></span> <span data-ttu-id="312b2-116">此阶段将对软件进行测试，以验证其是否按规范执行。</span><span class="sxs-lookup"><span data-stu-id="312b2-116">This is the process of testing the software to verify that it performs according to the specifications.</span></span>  
  
-   <span data-ttu-id="312b2-117">**版本**。</span><span class="sxs-lookup"><span data-stu-id="312b2-117">**Release**.</span></span> <span data-ttu-id="312b2-118">在对软件进行全面验证之后，对其进行打包并准备向用户发布。</span><span class="sxs-lookup"><span data-stu-id="312b2-118">After the software has been fully verified, it is packed and prepared for release to users.</span></span>  
  
 <span data-ttu-id="312b2-119">下图显示了此项目规划周期；</span><span class="sxs-lookup"><span data-stu-id="312b2-119">The following figure shows this project planning cycle.</span></span>  
  
 <span data-ttu-id="312b2-120">![按阶段项目规划的建议](../core/media/planningbyphase.gif "PlanningByPhase")</span><span class="sxs-lookup"><span data-stu-id="312b2-120">![Project Planning Recommendations by Phase](../core/media/planningbyphase.gif "PlanningByPhase")</span></span>  
  
 <span data-ttu-id="312b2-121">即使不是全部，上述大多数阶段也会在时间上重叠，并且存在经常反复出现的子阶段。</span><span class="sxs-lookup"><span data-stu-id="312b2-121">Most, if not all, of these phases overlap in time and there are typically iterative sub-phases.</span></span> <span data-ttu-id="312b2-122">例如，通常存在以下情况：在完成一部分产品功能的实现并开始验证该部分产品功能的同时，进行下一部分功能的实现。</span><span class="sxs-lookup"><span data-stu-id="312b2-122">For example, it is common to complete implementation of a sub-set of the product features and for verification to begin on that subset while implementation of the next sub set of features is under way.</span></span> <span data-ttu-id="312b2-123">因此，尽管本部分中的建议与特定阶段相关联，但并不意味着它们不能并行发生，这样做只是为了使您能够对考虑建议并将其纳入规划的相对顺序有所了解。</span><span class="sxs-lookup"><span data-stu-id="312b2-123">Therefore, while the recommendations in this section are associated with certain phases, the intention is not to imply that they cannot happen in parallel, but rather to give some idea of the relative order that the recommendations should be considered and factored into planning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="312b2-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="312b2-124">In This Section</span></span>  
  
-   [<span data-ttu-id="312b2-125">要求阶段建议</span><span class="sxs-lookup"><span data-stu-id="312b2-125">Requirements Phase Recommendations</span></span>](../core/requirements-phase-recommendations.md)  
  
-   [<span data-ttu-id="312b2-126">设计阶段建议</span><span class="sxs-lookup"><span data-stu-id="312b2-126">Design Phase Recommendations</span></span>](../core/design-phase-recommendations.md)  
  
-   [<span data-ttu-id="312b2-127">实现阶段建议</span><span class="sxs-lookup"><span data-stu-id="312b2-127">Implementation Phase Recommendations</span></span>](../core/implementation-phase-recommendations.md)  
  
-   [<span data-ttu-id="312b2-128">验证阶段建议</span><span class="sxs-lookup"><span data-stu-id="312b2-128">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)  
  
-   [<span data-ttu-id="312b2-129">发布阶段建议</span><span class="sxs-lookup"><span data-stu-id="312b2-129">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)