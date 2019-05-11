---
title: 步骤 4：生成 EAIOrchestration 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66e4b161-c5ac-404c-9ee5-4c0322fc40f3
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7c380d5aa68daeb6f7f05ca0846c00f1999b976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392628"
---
# <a name="step-4-build-the-eaiorchestration-project"></a><span data-ttu-id="09a14-102">步骤 4：生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="09a14-102">Step 4: Build the EAIOrchestration Project</span></span>
<span data-ttu-id="09a14-103">![步骤 4 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="09a14-103">![Step 4 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="09a14-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="09a14-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="09a14-105">**目标：** 在此步骤中，您将 EAIOrchestration 项目编译为程序集。</span><span class="sxs-lookup"><span data-stu-id="09a14-105">**Objective:** In this step, you compile the EAIOrchestration project into an assembly.</span></span>  
  
 <span data-ttu-id="09a14-106">**目的：** BizTalk Server 要求将所有项目编译为.NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="09a14-106">**Purpose:** BizTalk Server requires all the artifacts to be compiled into .NET assemblies.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="09a14-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="09a14-107">Prerequisites</span></span>  
 <span data-ttu-id="09a14-108">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="09a14-108">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="09a14-109">开始此步骤之前，必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="09a14-109">Before you begin this step you must complete the following steps:</span></span>  
  
    -   [<span data-ttu-id="09a14-110">步骤 1：向解决方案中添加 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="09a14-110">Step 1: Add EAIOrchestration Project to the Solution</span></span>](../core/step-1-add-eaiorchestration-project-to-the-solution.md)  
  
    -   [<span data-ttu-id="09a14-111">步骤 2：定义业务流程</span><span class="sxs-lookup"><span data-stu-id="09a14-111">Step 2: Define the Business Process</span></span>](../core/step-2-define-the-business-process.md)  
  
    -   [<span data-ttu-id="09a14-112">步骤 3：向业务流程添加端口</span><span class="sxs-lookup"><span data-stu-id="09a14-112">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)  
  
## <a name="procedures"></a><span data-ttu-id="09a14-113">过程</span><span class="sxs-lookup"><span data-stu-id="09a14-113">Procedures</span></span>  
  
#### <a name="to-build-the-eaiorchestration-project"></a><span data-ttu-id="09a14-114">若要生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="09a14-114">To build the EAIOrchestration project</span></span>  
  
-   <span data-ttu-id="09a14-115">在解决方案资源管理器中右键单击**EAIOrchestration**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="09a14-115">In Solution Explorer, right-click **EAIOrchestration**, and then click **Build**.</span></span>  
  
     <span data-ttu-id="09a14-116">在屏幕底部应显示：</span><span class="sxs-lookup"><span data-stu-id="09a14-116">The bottom of the screen should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="09a14-117">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="09a14-117">What did I just do?</span></span>  
 <span data-ttu-id="09a14-118">在此步骤中，您编译 EAIOrchestration 项目。</span><span class="sxs-lookup"><span data-stu-id="09a14-118">In this step, you compiled the EAIOrchestration project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="09a14-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="09a14-119">Next steps</span></span>  
 <span data-ttu-id="09a14-120">部署 EAISolution 解决方案中的[第 3 课：部署解决方案](../core/lesson-3-deploy-the-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="09a14-120">You deploy the EAISolution solution in [Lesson 3: Deploy the Solution](../core/lesson-3-deploy-the-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a14-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="09a14-121">See Also</span></span>  
 <span data-ttu-id="09a14-122">[步骤 1：向解决方案中添加 EAIOrchestration 项目](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="09a14-122">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="09a14-123">[步骤 2：定义业务流程](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="09a14-123">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="09a14-124">步骤 3：向业务流程添加端口</span><span class="sxs-lookup"><span data-stu-id="09a14-124">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)