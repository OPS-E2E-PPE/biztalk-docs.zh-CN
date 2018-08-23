---
title: 步骤 1： 向解决方案中添加 EAIOrchestration 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: 9b93ee2a019bef8d482626cf5525a6b95509b135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22276861"
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a><span data-ttu-id="80494-102">步骤 1：向解决方案中添加 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="80494-102">Step 1: Add EAIOrchestration Project to the Solution</span></span>
<span data-ttu-id="80494-103">![步骤 1，共 4 步](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="80494-103">![Step 1 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="80494-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="80494-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="80494-105">**目标：** 向 EAI 解决方案在此步骤中，添加第二个项目。</span><span class="sxs-lookup"><span data-stu-id="80494-105">**Objective:** In this step, you add a second project to the EAI solution.</span></span> <span data-ttu-id="80494-106">然后再向该新项目添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="80494-106">Then you add an orchestration to the new project.</span></span>  
  
 <span data-ttu-id="80494-107">**目的：** 创建业务流程的一个单独的项目。</span><span class="sxs-lookup"><span data-stu-id="80494-107">**Purpose:** You create a separate project for the orchestration.</span></span> <span data-ttu-id="80494-108">当多个人员使用一个解决方案时，这样做很有帮助。</span><span class="sxs-lookup"><span data-stu-id="80494-108">This is helpful when you have several different people working on one solution.</span></span> <span data-ttu-id="80494-109">您可以使用该新业务流程自动执行本课中的业务程序。</span><span class="sxs-lookup"><span data-stu-id="80494-109">You use the new orchestration to automate the business process in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="80494-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="80494-110">Prerequisites</span></span>  
 <span data-ttu-id="80494-111">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="80494-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="80494-112">在开始此步骤之前，必须完成[第 1 课： 定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="80494-112">Before you begin this step you must complete [Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="80494-113">过程</span><span class="sxs-lookup"><span data-stu-id="80494-113">Procedures</span></span>  
 <span data-ttu-id="80494-114">如果已关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口中，按照中的"打开 Visual Studio 项目"过程[第 2 步： 创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)以将其打开。</span><span class="sxs-lookup"><span data-stu-id="80494-114">If you have closed the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, follow the procedure “To open the Visual Studio project” in [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) to open it.</span></span>  
  
#### <a name="to-add-another-project-to-your-solution"></a><span data-ttu-id="80494-115">向解决方案添加另一项目</span><span class="sxs-lookup"><span data-stu-id="80494-115">To add another project to your solution</span></span>  
  
1.  <span data-ttu-id="80494-116">Visual Studio 中，从上**文件**菜单，依次指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="80494-116">From Visual Studio, on the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="80494-117">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="80494-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="80494-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="80494-118">Use this</span></span>|<span data-ttu-id="80494-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="80494-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="80494-120">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="80494-120">**Installed Templates**</span></span>|<span data-ttu-id="80494-121">单击**BizTalk 项目**，然后单击**空的 BizTalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="80494-121">Click **BizTalk Projects**, and then click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="80494-122">**名称**</span><span class="sxs-lookup"><span data-stu-id="80494-122">**Name**</span></span>|<span data-ttu-id="80494-123">键入 `EAIOrchestration`。</span><span class="sxs-lookup"><span data-stu-id="80494-123">Type `EAIOrchestration`.</span></span>|  
    |<span data-ttu-id="80494-124">**位置**</span><span class="sxs-lookup"><span data-stu-id="80494-124">**Location**</span></span>|<span data-ttu-id="80494-125">键入 `C:\BTSTutorials\EAISolution`。</span><span class="sxs-lookup"><span data-stu-id="80494-125">Type `C:\BTSTutorials\EAISolution`.</span></span>|  
  
3.  <span data-ttu-id="80494-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="80494-126">Click **OK**.</span></span>  
  
#### <a name="to-add-an-orchestration"></a><span data-ttu-id="80494-127">添加业务流程</span><span class="sxs-lookup"><span data-stu-id="80494-127">To add an orchestration</span></span>  
  
1.  <span data-ttu-id="80494-128">在解决方案资源管理器中右键单击**EAIOrchestration**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="80494-128">In Solution Explorer, right-click **EAIOrchestration**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="80494-129">在中**添加新项-EAIOrchestration**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="80494-129">In the **Add New Item - EAIOrchestration** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="80494-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="80494-130">Use this</span></span>|<span data-ttu-id="80494-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="80494-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="80494-132">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="80494-132">**Installed Templates**</span></span>|<span data-ttu-id="80494-133">单击**业务流程文件**，然后单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="80494-133">Click **Orchestration Files**, and then click **BizTalk Orchestration**.</span></span>|  
    |<span data-ttu-id="80494-134">**名称**</span><span class="sxs-lookup"><span data-stu-id="80494-134">**Name**</span></span>|<span data-ttu-id="80494-135">类型**EAIProcess.odx**。</span><span class="sxs-lookup"><span data-stu-id="80494-135">Type **EAIProcess.odx**.</span></span>|  
  
3.  <span data-ttu-id="80494-136">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="80494-136">Click **Add**.</span></span>  
  
     <span data-ttu-id="80494-137">此时，将打开业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="80494-137">Orchestration Designer opens.</span></span> <span data-ttu-id="80494-138">下图显示了包含 EAIProcess 业务流程的业务流程设计器：</span><span class="sxs-lookup"><span data-stu-id="80494-138">The following figure shows Orchestration Designer with the EAIProcess orchestration.</span></span>  
  
     <span data-ttu-id="80494-139">![新的业务流程](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="80494-139">![New orchestration](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="80494-140">内容回顾</span><span class="sxs-lookup"><span data-stu-id="80494-140">What did I just do?</span></span>  
 <span data-ttu-id="80494-141">在此步骤中，您向 EAI 解决方案添加了另一项目。</span><span class="sxs-lookup"><span data-stu-id="80494-141">In this step, you added a second project to the EAI solution.</span></span> <span data-ttu-id="80494-142">然后又向该新项目添加了业务流程。</span><span class="sxs-lookup"><span data-stu-id="80494-142">Then you added an orchestration to the new project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="80494-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="80494-143">Next Steps</span></span>  
 <span data-ttu-id="80494-144">定义在业务流程[步骤 2： 定义业务流程](../core/step-2-define-the-business-process.md)。</span><span class="sxs-lookup"><span data-stu-id="80494-144">You define the business process in [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80494-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="80494-145">See Also</span></span>  
 <span data-ttu-id="80494-146">[步骤 2： 定义业务流程](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="80494-146">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 <span data-ttu-id="80494-147">[步骤 3： 将端口添加到业务流程](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="80494-147">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="80494-148">第 4 步：生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="80494-148">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)