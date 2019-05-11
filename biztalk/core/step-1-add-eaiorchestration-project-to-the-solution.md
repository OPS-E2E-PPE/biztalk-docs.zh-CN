---
title: 第 1 步：向解决方案中添加 EAIOrchestration 项目 |Microsoft Docs
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
ms.openlocfilehash: df384829c19f24b71bec1726a260f185ea583463
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392943"
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a><span data-ttu-id="78706-102">第 1 步：向解决方案中添加 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="78706-102">Step 1: Add EAIOrchestration Project to the Solution</span></span>
<span data-ttu-id="78706-103">![步骤 1，共 4 步](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="78706-103">![Step 1 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="78706-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="78706-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="78706-105">**目标：** 在此步骤中，您向 EAI 解决方案添加第二个项目。</span><span class="sxs-lookup"><span data-stu-id="78706-105">**Objective:** In this step, you add a second project to the EAI solution.</span></span> <span data-ttu-id="78706-106">然后，将业务流程添加到新的项目。</span><span class="sxs-lookup"><span data-stu-id="78706-106">Then you add an orchestration to the new project.</span></span>  
  
 <span data-ttu-id="78706-107">**目的：** 创建一个单独的项目的业务流程。</span><span class="sxs-lookup"><span data-stu-id="78706-107">**Purpose:** You create a separate project for the orchestration.</span></span> <span data-ttu-id="78706-108">当有多个人员使用一种解决方案时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="78706-108">This is helpful when you have several different people working on one solution.</span></span> <span data-ttu-id="78706-109">使用新的业务流程自动业务流程执行本课程中。</span><span class="sxs-lookup"><span data-stu-id="78706-109">You use the new orchestration to automate the business process in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="78706-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="78706-110">Prerequisites</span></span>  
 <span data-ttu-id="78706-111">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="78706-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="78706-112">在开始此步骤之前，必须完成[第 1 课：定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="78706-112">Before you begin this step you must complete [Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="78706-113">过程</span><span class="sxs-lookup"><span data-stu-id="78706-113">Procedures</span></span>  
 <span data-ttu-id="78706-114">如果已关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口中，按照中的"打开 Visual Studio 项目"过程[步骤 2:创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)以将其打开。</span><span class="sxs-lookup"><span data-stu-id="78706-114">If you have closed the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, follow the procedure “To open the Visual Studio project” in [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) to open it.</span></span>  
  
#### <a name="to-add-another-project-to-your-solution"></a><span data-ttu-id="78706-115">若要将另一个项目添加到你的解决方案</span><span class="sxs-lookup"><span data-stu-id="78706-115">To add another project to your solution</span></span>  
  
1.  <span data-ttu-id="78706-116">Visual Studio 中，从上**文件**菜单，依次指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="78706-116">From Visual Studio, on the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="78706-117">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78706-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="78706-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="78706-118">Use this</span></span>|<span data-ttu-id="78706-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="78706-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="78706-120">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="78706-120">**Installed Templates**</span></span>|<span data-ttu-id="78706-121">单击**BizTalk 项目**，然后单击**空的 BizTalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="78706-121">Click **BizTalk Projects**, and then click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="78706-122">**名称**</span><span class="sxs-lookup"><span data-stu-id="78706-122">**Name**</span></span>|<span data-ttu-id="78706-123">键入 `EAIOrchestration`。</span><span class="sxs-lookup"><span data-stu-id="78706-123">Type `EAIOrchestration`.</span></span>|  
    |<span data-ttu-id="78706-124">**位置**</span><span class="sxs-lookup"><span data-stu-id="78706-124">**Location**</span></span>|<span data-ttu-id="78706-125">键入 `C:\BTSTutorials\EAISolution`。</span><span class="sxs-lookup"><span data-stu-id="78706-125">Type `C:\BTSTutorials\EAISolution`.</span></span>|  
  
3.  <span data-ttu-id="78706-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="78706-126">Click **OK**.</span></span>  
  
#### <a name="to-add-an-orchestration"></a><span data-ttu-id="78706-127">若要添加业务流程</span><span class="sxs-lookup"><span data-stu-id="78706-127">To add an orchestration</span></span>  
  
1.  <span data-ttu-id="78706-128">在解决方案资源管理器中右键单击**EAIOrchestration**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="78706-128">In Solution Explorer, right-click **EAIOrchestration**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="78706-129">在中**添加新项-EAIOrchestration**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78706-129">In the **Add New Item - EAIOrchestration** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="78706-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="78706-130">Use this</span></span>|<span data-ttu-id="78706-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="78706-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="78706-132">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="78706-132">**Installed Templates**</span></span>|<span data-ttu-id="78706-133">单击**业务流程文件**，然后单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="78706-133">Click **Orchestration Files**, and then click **BizTalk Orchestration**.</span></span>|  
    |<span data-ttu-id="78706-134">**名称**</span><span class="sxs-lookup"><span data-stu-id="78706-134">**Name**</span></span>|<span data-ttu-id="78706-135">类型**EAIProcess.odx**。</span><span class="sxs-lookup"><span data-stu-id="78706-135">Type **EAIProcess.odx**.</span></span>|  
  
3.  <span data-ttu-id="78706-136">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="78706-136">Click **Add**.</span></span>  
  
     <span data-ttu-id="78706-137">业务流程设计器随即打开。</span><span class="sxs-lookup"><span data-stu-id="78706-137">Orchestration Designer opens.</span></span> <span data-ttu-id="78706-138">下图显示了包含 EAIProcess 业务流程的业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="78706-138">The following figure shows Orchestration Designer with the EAIProcess orchestration.</span></span>  
  
     <span data-ttu-id="78706-139">![新的业务流程](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="78706-139">![New orchestration](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="78706-140">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="78706-140">What did I just do?</span></span>  
 <span data-ttu-id="78706-141">在此步骤中，您向 EAI 解决方案添加第二个项目。</span><span class="sxs-lookup"><span data-stu-id="78706-141">In this step, you added a second project to the EAI solution.</span></span> <span data-ttu-id="78706-142">然后向该新项目添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="78706-142">Then you added an orchestration to the new project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="78706-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="78706-143">Next Steps</span></span>  
 <span data-ttu-id="78706-144">定义业务流程中的[步骤 2:定义业务流程](../core/step-2-define-the-business-process.md)。</span><span class="sxs-lookup"><span data-stu-id="78706-144">You define the business process in [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78706-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="78706-145">See Also</span></span>  
 <span data-ttu-id="78706-146">[步骤 2：定义业务流程](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="78706-146">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 <span data-ttu-id="78706-147">[步骤 3：向业务流程添加端口](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="78706-147">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="78706-148">步骤 4：生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="78706-148">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)