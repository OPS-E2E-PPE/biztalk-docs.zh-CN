---
title: "步骤 1： 向解决方案添加 EAIOrchestration 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a><span data-ttu-id="adfc3-102">步骤 1：向解决方案中添加 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="adfc3-102">Step 1: Add EAIOrchestration Project to the Solution</span></span>
<span data-ttu-id="adfc3-103">![步骤 1 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="adfc3-103">![Step 1 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="adfc3-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="adfc3-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="adfc3-105">**目标：**在此步骤中，你可以将第二个项目添加到 EAI 解决方案。</span><span class="sxs-lookup"><span data-stu-id="adfc3-105">**Objective:** In this step, you add a second project to the EAI solution.</span></span> <span data-ttu-id="adfc3-106">然后再向该新项目添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="adfc3-106">Then you add an orchestration to the new project.</span></span>  
  
 <span data-ttu-id="adfc3-107">**用途：**创建业务流程单独的项目。</span><span class="sxs-lookup"><span data-stu-id="adfc3-107">**Purpose:** You create a separate project for the orchestration.</span></span> <span data-ttu-id="adfc3-108">当多个人员使用一个解决方案时，这样做很有帮助。</span><span class="sxs-lookup"><span data-stu-id="adfc3-108">This is helpful when you have several different people working on one solution.</span></span> <span data-ttu-id="adfc3-109">您可以使用该新业务流程自动执行本课中的业务程序。</span><span class="sxs-lookup"><span data-stu-id="adfc3-109">You use the new orchestration to automate the business process in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="adfc3-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="adfc3-110">Prerequisites</span></span>  
 <span data-ttu-id="adfc3-111">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="adfc3-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="adfc3-112">在开始此步骤之前必须完成[第 1 课： 定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="adfc3-112">Before you begin this step you must complete [Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="adfc3-113">过程</span><span class="sxs-lookup"><span data-stu-id="adfc3-113">Procedures</span></span>  
 <span data-ttu-id="adfc3-114">如果您关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口中，按照中的过程后，"以打开 Visual Studio 项目"[步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md)以将其打开。</span><span class="sxs-lookup"><span data-stu-id="adfc3-114">If you have closed the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, follow the procedure “To open the Visual Studio project” in [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) to open it.</span></span>  
  
#### <a name="to-add-another-project-to-your-solution"></a><span data-ttu-id="adfc3-115">向解决方案添加另一项目</span><span class="sxs-lookup"><span data-stu-id="adfc3-115">To add another project to your solution</span></span>  
  
1.  <span data-ttu-id="adfc3-116">从 Visual Studio 中，在**文件**菜单上，指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="adfc3-116">From Visual Studio, on the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="adfc3-117">在**新项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adfc3-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="adfc3-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="adfc3-118">Use this</span></span>|<span data-ttu-id="adfc3-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="adfc3-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="adfc3-120">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="adfc3-120">**Installed Templates**</span></span>|<span data-ttu-id="adfc3-121">单击**BizTalk 项目**，然后单击**空 BizTalk 服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="adfc3-121">Click **BizTalk Projects**, and then click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="adfc3-122">**名称**</span><span class="sxs-lookup"><span data-stu-id="adfc3-122">**Name**</span></span>|<span data-ttu-id="adfc3-123">键入 `EAIOrchestration`。</span><span class="sxs-lookup"><span data-stu-id="adfc3-123">Type `EAIOrchestration`.</span></span>|  
    |<span data-ttu-id="adfc3-124">**位置**</span><span class="sxs-lookup"><span data-stu-id="adfc3-124">**Location**</span></span>|<span data-ttu-id="adfc3-125">键入 `C:\BTSTutorials\EAISolution`。</span><span class="sxs-lookup"><span data-stu-id="adfc3-125">Type `C:\BTSTutorials\EAISolution`.</span></span>|  
  
3.  <span data-ttu-id="adfc3-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="adfc3-126">Click **OK**.</span></span>  
  
#### <a name="to-add-an-orchestration"></a><span data-ttu-id="adfc3-127">添加业务流程</span><span class="sxs-lookup"><span data-stu-id="adfc3-127">To add an orchestration</span></span>  
  
1.  <span data-ttu-id="adfc3-128">在解决方案资源管理器，右键单击**EAIOrchestration**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="adfc3-128">In Solution Explorer, right-click **EAIOrchestration**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="adfc3-129">在**添加新项-EAIOrchestration**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adfc3-129">In the **Add New Item - EAIOrchestration** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="adfc3-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="adfc3-130">Use this</span></span>|<span data-ttu-id="adfc3-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="adfc3-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="adfc3-132">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="adfc3-132">**Installed Templates**</span></span>|<span data-ttu-id="adfc3-133">单击**Orchestration 文件**，然后单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="adfc3-133">Click **Orchestration Files**, and then click **BizTalk Orchestration**.</span></span>|  
    |<span data-ttu-id="adfc3-134">**名称**</span><span class="sxs-lookup"><span data-stu-id="adfc3-134">**Name**</span></span>|<span data-ttu-id="adfc3-135">类型**EAIProcess.odx**。</span><span class="sxs-lookup"><span data-stu-id="adfc3-135">Type **EAIProcess.odx**.</span></span>|  
  
3.  <span data-ttu-id="adfc3-136">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="adfc3-136">Click **Add**.</span></span>  
  
     <span data-ttu-id="adfc3-137">此时，将打开业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="adfc3-137">Orchestration Designer opens.</span></span> <span data-ttu-id="adfc3-138">下图显示了包含 EAIProcess 业务流程的业务流程设计器：</span><span class="sxs-lookup"><span data-stu-id="adfc3-138">The following figure shows Orchestration Designer with the EAIProcess orchestration.</span></span>  
  
     <span data-ttu-id="adfc3-139">![新的业务流程](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="adfc3-139">![New orchestration](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="adfc3-140">内容回顾</span><span class="sxs-lookup"><span data-stu-id="adfc3-140">What did I just do?</span></span>  
 <span data-ttu-id="adfc3-141">在此步骤中，您向 EAI 解决方案添加了另一项目。</span><span class="sxs-lookup"><span data-stu-id="adfc3-141">In this step, you added a second project to the EAI solution.</span></span> <span data-ttu-id="adfc3-142">然后又向该新项目添加了业务流程。</span><span class="sxs-lookup"><span data-stu-id="adfc3-142">Then you added an orchestration to the new project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="adfc3-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="adfc3-143">Next Steps</span></span>  
 <span data-ttu-id="adfc3-144">定义中的业务流程[步骤 2： 定义业务流程](../core/step-2-define-the-business-process.md)。</span><span class="sxs-lookup"><span data-stu-id="adfc3-144">You define the business process in [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adfc3-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adfc3-145">See Also</span></span>  
 <span data-ttu-id="adfc3-146">[步骤 2： 定义的业务流程](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="adfc3-146">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 <span data-ttu-id="adfc3-147">[步骤 3： 将端口添加到业务流程](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="adfc3-147">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="adfc3-148">步骤 4： 生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="adfc3-148">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)