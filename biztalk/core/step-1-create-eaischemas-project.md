---
title: 步骤 1： 创建 EAISchemas 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a14ee61-fa27-4f03-997e-42c34a77afee
caps.latest.revision: 55
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb51c936edfcc20009048abcb90bb8ead72fd11c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974454"
---
# <a name="step-1-create-eaischemas-project"></a><span data-ttu-id="22818-102">步骤 1：创建 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="22818-102">Step 1: Create EAISchemas Project</span></span>
<span data-ttu-id="22818-103">![5 的第 1 步](../core/media/step-1of5.gif "Step_1of5")</span><span class="sxs-lookup"><span data-stu-id="22818-103">![Step 1 of 5](../core/media/step-1of5.gif "Step_1of5")</span></span>  

 <span data-ttu-id="22818-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="22818-104">**Time to complete:** 5 minutes</span></span>  

 <span data-ttu-id="22818-105">**目标：** 在此步骤中，您创建一个新[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案和项目。</span><span class="sxs-lookup"><span data-stu-id="22818-105">**Objective:** In this step, you create a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution and a project.</span></span>  

 <span data-ttu-id="22818-106">**目的：** 使用 BizTalk 项目系统创建部分或全部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]应用程序或业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="22818-106">**Purpose:** You use the BizTalk project system to create part or all of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] application or business solution.</span></span> <span data-ttu-id="22818-107">这些解决方案的核心元素是 BizTalk 项目，它是可在部署程序集之前构建并生成到该程序集中的项（例如架构、业务流程、Web 消息类型、类、管道、映射和引用）的集合。</span><span class="sxs-lookup"><span data-stu-id="22818-107">The core element of any such solution is a BizTalk project—a collection of items, such as schemas, orchestrations, Web message types, classes, pipelines, maps, and references that you can build and generate into an assembly before deploying it.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="22818-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="22818-108">Prerequisites</span></span>  
 <span data-ttu-id="22818-109">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="22818-109">Note the following requirements before you begin this step:</span></span>  

-   <span data-ttu-id="22818-110">开始此步骤之前，必须完成中的步骤[在开始本教程之前](../core/before-you-begin-the-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="22818-110">Before you begin this step you must complete the steps in [Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md).</span></span>  

## <a name="procedures"></a><span data-ttu-id="22818-111">过程</span><span class="sxs-lookup"><span data-stu-id="22818-111">Procedures</span></span>  

#### <a name="to-create-a-new-visual-studio-solutionproject"></a><span data-ttu-id="22818-112">创建新的 Visual Studio 解决方案/项目</span><span class="sxs-lookup"><span data-stu-id="22818-112">To create a new Visual Studio solution/project</span></span>  

1. <span data-ttu-id="22818-113">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="22818-113">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="22818-114">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="22818-114">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="22818-115">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22818-115">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="22818-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="22818-116">Use this</span></span>              |                                <span data-ttu-id="22818-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="22818-117">To do this</span></span>                                |
   |-----------------------------------|--------------------------------------------------------------------------|
   |      <span data-ttu-id="22818-118">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="22818-118">**Installed Templates**</span></span>      | <span data-ttu-id="22818-119">单击**BizTalk 项目**，然后单击**空的 BizTalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="22818-119">Click **BizTalk Projects**, then click **Empty BizTalk Server Project**.</span></span> |
   |             <span data-ttu-id="22818-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="22818-120">**Name**</span></span>              |                           <span data-ttu-id="22818-121">类型**EAISchemas**。</span><span class="sxs-lookup"><span data-stu-id="22818-121">Type **EAISchemas**.</span></span>                           |
   |           <span data-ttu-id="22818-122">**位置**</span><span class="sxs-lookup"><span data-stu-id="22818-122">**Location**</span></span>            |                      <span data-ttu-id="22818-123">类型**C:\tutorial\Lessons**。</span><span class="sxs-lookup"><span data-stu-id="22818-123">Type **C:\tutorial\Lessons**.</span></span>                       |
   |         <span data-ttu-id="22818-124">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="22818-124">**Solution Name**</span></span>         |                          <span data-ttu-id="22818-125">类型**EAISolution**。</span><span class="sxs-lookup"><span data-stu-id="22818-125">Type **EAISolution**.</span></span>                           |
   | <span data-ttu-id="22818-126">**创建解决方案的目录**</span><span class="sxs-lookup"><span data-stu-id="22818-126">**Create directory for solution**</span></span> |                                <span data-ttu-id="22818-127">（已选中）</span><span class="sxs-lookup"><span data-stu-id="22818-127">(selected)</span></span>                                |


4. <span data-ttu-id="22818-128">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="22818-128">Click **OK**.</span></span>  

5. <span data-ttu-id="22818-129">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="22818-129">On the **File** menu, click **Save All**.</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="22818-130">内容回顾</span><span class="sxs-lookup"><span data-stu-id="22818-130">What did I just do?</span></span>  
 <span data-ttu-id="22818-131">在此步骤中，你在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中打开了新项目和 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 解决方案。</span><span class="sxs-lookup"><span data-stu-id="22818-131">In this step, you opened a new project and a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="22818-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22818-132">Next Steps</span></span>  
 <span data-ttu-id="22818-133">为库存补货请求消息创建架构。</span><span class="sxs-lookup"><span data-stu-id="22818-133">You create the schema for the inventory replenishment request message.</span></span>  

## <a name="see-also"></a><span data-ttu-id="22818-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="22818-134">See Also</span></span>  
 <span data-ttu-id="22818-135">[开始本教程之前](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="22818-135">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="22818-136">[步骤 2： 创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="22818-136">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="22818-137">[步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="22818-137">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="22818-138">[步骤 4： 创建映射](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="22818-138">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="22818-139">[步骤 5： 生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="22818-139">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="22818-140">[开发人员工具](../core/developer-tools.md) </span><span class="sxs-lookup"><span data-stu-id="22818-140">[Developer Tools](../core/developer-tools.md) </span></span>  
 [<span data-ttu-id="22818-141">处理 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="22818-141">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)