---
title: 分阶段描述的项目规划建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, performance
- performance, planning
ms.assetid: 422f05e3-5ad4-4f47-9be3-c229a20a6ef3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084d24b5b1eb3e3a19ca7a8ee04af268a8f0a91c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395606"
---
# <a name="project-planning-recommendations-by-phase"></a><span data-ttu-id="97d06-102">分阶段描述的项目规划建议</span><span class="sxs-lookup"><span data-stu-id="97d06-102">Project Planning Recommendations by Phase</span></span>
<span data-ttu-id="97d06-103">存在多种软件开发生命周期模型中存在如今，每个都有其自己的方法、 权益和限制。</span><span class="sxs-lookup"><span data-stu-id="97d06-103">There are a number of software development lifecycle models in existence today, each with their own approaches, benefits, and limitations.</span></span> <span data-ttu-id="97d06-104">本部分的目的是提供一组建议，以帮助您成功进行适当规划[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发项目。</span><span class="sxs-lookup"><span data-stu-id="97d06-104">The goal of this section is to provide a set of recommendations that will help you plan appropriately for a successful [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development project.</span></span>  
  
 <span data-ttu-id="97d06-105">在本部分中，我们将使用在 Microsoft 广泛采用的生命周期模型。</span><span class="sxs-lookup"><span data-stu-id="97d06-105">In this section, we use the lifecycle model employed broadly at Microsoft.</span></span> <span data-ttu-id="97d06-106">此模型是一系列迭代和瀑布式生命周期模型。</span><span class="sxs-lookup"><span data-stu-id="97d06-106">This model is a combination of iterative and waterfall lifecycle models.</span></span>  
  
 <span data-ttu-id="97d06-107">在此模型中，有五个阶段，其边界定义一组有序的项目里程碑。</span><span class="sxs-lookup"><span data-stu-id="97d06-107">In this model, there are five phases whose boundaries define a sequential set of milestones for the project.</span></span> <span data-ttu-id="97d06-108">阶段，按顺序执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="97d06-108">The phases, in order of execution, are as follows:</span></span>  
  
- <span data-ttu-id="97d06-109">**要求**。</span><span class="sxs-lookup"><span data-stu-id="97d06-109">**Requirements**.</span></span> <span data-ttu-id="97d06-110">在定义什么是要生成的功能规范中捕获用户需求。</span><span class="sxs-lookup"><span data-stu-id="97d06-110">User requirements are captured in functional specifications that define what is to be built.</span></span>  
  
- <span data-ttu-id="97d06-111">**设计**。</span><span class="sxs-lookup"><span data-stu-id="97d06-111">**Design**.</span></span> <span data-ttu-id="97d06-112">基于功能的要求，创建物理设计规范并构建原型以验证设计思路和研究平台功能。</span><span class="sxs-lookup"><span data-stu-id="97d06-112">Based on the functional requirements, physical design specifications are created and prototyping is conducted to verify design ideas and investigate platform capabilities.</span></span>  
  
- <span data-ttu-id="97d06-113">**实现**。</span><span class="sxs-lookup"><span data-stu-id="97d06-113">**Implementation**.</span></span> <span data-ttu-id="97d06-114">使用设计和功能规范，完成软件编码。</span><span class="sxs-lookup"><span data-stu-id="97d06-114">Using the design and functional specifications, the software coding is done.</span></span>  
  
- <span data-ttu-id="97d06-115">**验证**。</span><span class="sxs-lookup"><span data-stu-id="97d06-115">**Verification**.</span></span> <span data-ttu-id="97d06-116">这是测试软件后，以验证按规范执行的过程。</span><span class="sxs-lookup"><span data-stu-id="97d06-116">This is the process of testing the software to verify that it performs according to the specifications.</span></span>  
  
- <span data-ttu-id="97d06-117">**发布**。</span><span class="sxs-lookup"><span data-stu-id="97d06-117">**Release**.</span></span> <span data-ttu-id="97d06-118">该软件进行全面验证之后，它是打包并准备向用户发布。</span><span class="sxs-lookup"><span data-stu-id="97d06-118">After the software has been fully verified, it is packed and prepared for release to users.</span></span>  
  
  <span data-ttu-id="97d06-119">下图显示了此项目规划周期。</span><span class="sxs-lookup"><span data-stu-id="97d06-119">The following figure shows this project planning cycle.</span></span>  
  
  <span data-ttu-id="97d06-120">![分阶段描述的项目规划建议](../core/media/planningbyphase.gif "PlanningByPhase")</span><span class="sxs-lookup"><span data-stu-id="97d06-120">![Project Planning Recommendations by Phase](../core/media/planningbyphase.gif "PlanningByPhase")</span></span>  
  
  <span data-ttu-id="97d06-121">大多数，如果并非所有这些阶段的时间重叠，并且存在经常反复出现的子阶段。</span><span class="sxs-lookup"><span data-stu-id="97d06-121">Most, if not all, of these phases overlap in time and there are typically iterative sub-phases.</span></span> <span data-ttu-id="97d06-122">例如，往往会完成一部分产品功能的实现，并开始针对该子集的下一步子实现的功能集时验证正在进行。</span><span class="sxs-lookup"><span data-stu-id="97d06-122">For example, it is common to complete implementation of a sub-set of the product features and for verification to begin on that subset while implementation of the next sub set of features is under way.</span></span> <span data-ttu-id="97d06-123">因此，虽然在本部分中的建议与特定阶段相关联，目的是不以表示它们不会发生并行情况下，而不是为提供的建议，应考虑和分解的相对顺序的一些概念到计划。</span><span class="sxs-lookup"><span data-stu-id="97d06-123">Therefore, while the recommendations in this section are associated with certain phases, the intention is not to imply that they cannot happen in parallel, but rather to give some idea of the relative order that the recommendations should be considered and factored into planning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97d06-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="97d06-124">In This Section</span></span>  
  
-   [<span data-ttu-id="97d06-125">需求阶段的建议</span><span class="sxs-lookup"><span data-stu-id="97d06-125">Requirements Phase Recommendations</span></span>](../core/requirements-phase-recommendations.md)  
  
-   [<span data-ttu-id="97d06-126">设计阶段的建议</span><span class="sxs-lookup"><span data-stu-id="97d06-126">Design Phase Recommendations</span></span>](../core/design-phase-recommendations.md)  
  
-   [<span data-ttu-id="97d06-127">实现阶段的建议</span><span class="sxs-lookup"><span data-stu-id="97d06-127">Implementation Phase Recommendations</span></span>](../core/implementation-phase-recommendations.md)  
  
-   [<span data-ttu-id="97d06-128">验证阶段的建议</span><span class="sxs-lookup"><span data-stu-id="97d06-128">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)  
  
-   [<span data-ttu-id="97d06-129">发行阶段的建议</span><span class="sxs-lookup"><span data-stu-id="97d06-129">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)