---
title: "步骤 1： 部署项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: "44"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4262b2bb424a339f866f3b4a14ae03c2e507f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-deploy-the-projects"></a><span data-ttu-id="3e746-102">步骤 1：部署项目</span><span class="sxs-lookup"><span data-stu-id="3e746-102">Step 1: Deploy the Projects</span></span>
<span data-ttu-id="3e746-103">![步骤 1，共 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="3e746-103">![Step 1 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="3e746-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="3e746-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="3e746-105">**目标：**在此步骤中，你将部署在 EAISchemas 和 EAIOrchestration 项目。</span><span class="sxs-lookup"><span data-stu-id="3e746-105">**Objective:** In this step, you deploy the EAISchemas and EAIOrchestration projects.</span></span>  
  
 <span data-ttu-id="3e746-106">**用途：**在部署项目或 Visual Studio 中的解决方案时，程序集是自动生成并部署到指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e746-106">**Purpose:** When you deploy a project or solution in Visual Studio, the assemblies are automatically built and deployed into the specified application.</span></span> <span data-ttu-id="3e746-107">在此过程中，程序集连同它所包含的业务流程、架构和映射（称为“项目”）将导入本地 BizTalk 管理数据库，并在该数据库中与指定的应用程序建立关联。</span><span class="sxs-lookup"><span data-stu-id="3e746-107">As part of this process, the assembly along with the orchestrations, schemas, and maps that it contains (called "artifacts") are imported into the local BizTalk Management database and associated in the database with the specified application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e746-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="3e746-108">Prerequisites</span></span>  
 <span data-ttu-id="3e746-109">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="3e746-109">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="3e746-110">在开始此步骤之前，必须完成以下课程：</span><span class="sxs-lookup"><span data-stu-id="3e746-110">Before you begin this step you must complete the following lessons:</span></span>  
  
    -   [<span data-ttu-id="3e746-111">第 1 课： 定义架构和映射</span><span class="sxs-lookup"><span data-stu-id="3e746-111">Lesson 1: Define Schemas and a Map</span></span>](../core/lesson-1-define-schemas-and-a-map.md)  
  
    -   [<span data-ttu-id="3e746-112">第 2 课： 定义的业务流程</span><span class="sxs-lookup"><span data-stu-id="3e746-112">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)  
  
-   <span data-ttu-id="3e746-113">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3e746-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
-   <span data-ttu-id="3e746-114">在支持用户帐户控制 (UAC) 的系统上，必须使用管理权限运行 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="3e746-114">On a system that supports User Account Control (UAC), you must run Visual Studio with Administrative privileges.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="3e746-115">过程</span><span class="sxs-lookup"><span data-stu-id="3e746-115">Procedures</span></span>  
 <span data-ttu-id="3e746-116">若要使用 Visual Studio 部署应用程序，你必须以 BizTalk Server Administrators 组成员身份登录 Windows，并以管理员身份运行 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="3e746-116">To deploy the application using Visual Studio, you must log on Windows as a member of the BizTalk Server Administrators group and run Visual Studio as administrator.</span></span>  <span data-ttu-id="3e746-117">否则，将收到“访问被拒绝”错误。</span><span class="sxs-lookup"><span data-stu-id="3e746-117">Otherwise you will get the “Access is denied” error.</span></span>  
  
#### <a name="to-open-the-solution-with-administrative-privileges"></a><span data-ttu-id="3e746-118">使用管理权限打开解决方案</span><span class="sxs-lookup"><span data-stu-id="3e746-118">To open the solution with administrative privileges</span></span>  
  
1.  <span data-ttu-id="3e746-119">以 BizTalk Server Administrators 组成员身份登录 Windows。</span><span class="sxs-lookup"><span data-stu-id="3e746-119">Log on Windows as a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="3e746-120">启动**Microsoft Visual Studio**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="3e746-120">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
3.  <span data-ttu-id="3e746-121">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="3e746-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="3e746-122">在**打开项目**对话框中，浏览到**EAISolution.sln**项目解决方案文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="3e746-122">In the **Open Project** dialog box, browse to the **EAISolution.sln** project solution file, and then click **Open**.</span></span>  
  
 <span data-ttu-id="3e746-123">部署过程要求程序集是强签名的。</span><span class="sxs-lookup"><span data-stu-id="3e746-123">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="3e746-124">必须通过将该项目与一个强名称程序集密钥文件相关联来签名你的程序集。</span><span class="sxs-lookup"><span data-stu-id="3e746-124">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  <span data-ttu-id="3e746-125">此文件由教程文件提供。</span><span class="sxs-lookup"><span data-stu-id="3e746-125">This file is provided by the tutorial files.</span></span>  
  
 <span data-ttu-id="3e746-126">BizTalk 应用程序是 BizTalk Server 的一项功能，可使你更快、更轻松地对 BizTalk Server 业务解决方案进行部署、管理和故障排除。</span><span class="sxs-lookup"><span data-stu-id="3e746-126">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="3e746-127">BizTalk 应用程序是 BizTalk Server 业务解决方案中使用的项（称为“项目”）的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="3e746-127">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span> <span data-ttu-id="3e746-128">可为项目指定应用程序名。</span><span class="sxs-lookup"><span data-stu-id="3e746-128">We can specify an application name for a project.</span></span>  <span data-ttu-id="3e746-129">部署过程将自动创建具有指定名称的新应用程序（如果该应用程序不存在）。</span><span class="sxs-lookup"><span data-stu-id="3e746-129">The deployment process will automatically create a new application having the specified name if it doesn’t exist.</span></span>  
  
#### <a name="to-configure-and-deploy-the-projects"></a><span data-ttu-id="3e746-130">配置和部署项目</span><span class="sxs-lookup"><span data-stu-id="3e746-130">To configure and deploy the projects</span></span>  
  
1.  <span data-ttu-id="3e746-131">在解决方案资源管理器，右键单击**EAISchemas**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3e746-131">In Solution Explorer, right-click the **EAISchemas** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3e746-132">单击**签名**选项卡上，选择**对程序集签名**。</span><span class="sxs-lookup"><span data-stu-id="3e746-132">Click the **Signing** tab, select **Sign the assembly**.</span></span>  
  
3.  <span data-ttu-id="3e746-133">从下拉列表中**选择强名称密钥文件**框中，选择**\<浏览 … >**。</span><span class="sxs-lookup"><span data-stu-id="3e746-133">From the drop-down list in the **Choose a strong name key file** box, select **\<Browse…>**.</span></span>  
  
4.  <span data-ttu-id="3e746-134">在**选择文件**对话框框中，导航到**C:\BTStutorials**，单击**btsTutorials.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="3e746-134">In the **Select File** dialog box, navigate to **C:\BTStutorials**, click **btsTutorials.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="3e746-135">单击**部署**选项卡上，在右侧的框中**应用程序名称**，类型`EAISolution`。</span><span class="sxs-lookup"><span data-stu-id="3e746-135">Click the **Deployment** tab, in the box to the right of **Application Name**, type `EAISolution`.</span></span>  
  
6.  <span data-ttu-id="3e746-136">从下拉列表中的右侧的框**重新部署**，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="3e746-136">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
7.  <span data-ttu-id="3e746-137">在解决方案资源管理器，右键单击**EAISchemas**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="3e746-137">In Solution Explorer, right-click **EAISchemas**, and then click **Deploy**.</span></span>  <span data-ttu-id="3e746-138">“输出”窗口应显示：</span><span class="sxs-lookup"><span data-stu-id="3e746-138">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  <span data-ttu-id="3e746-139">重复步骤 1 到 7 以部署 EAIOrchestration 项目。</span><span class="sxs-lookup"><span data-stu-id="3e746-139">Repeat step 1 through 7 to deploy the EAIOrchestration project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="3e746-140">内容回顾</span><span class="sxs-lookup"><span data-stu-id="3e746-140">What did I just do?</span></span>  
 <span data-ttu-id="3e746-141">在此步骤中，你已部署了 EAISchemas 和 EAIOrchestration 项目。</span><span class="sxs-lookup"><span data-stu-id="3e746-141">In this step, you deployed the EAISchemas and EAIOrchestration projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3e746-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3e746-142">Next Steps</span></span>  
 <span data-ttu-id="3e746-143">创建物理端口，然后将其绑定到业务流程的逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="3e746-143">You create the physical ports, and bind them to the logical ports of the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e746-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e746-144">See Also</span></span>  
 <span data-ttu-id="3e746-145">[步骤 2： 配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md) </span><span class="sxs-lookup"><span data-stu-id="3e746-145">[Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md) </span></span>  
 [<span data-ttu-id="3e746-146">步骤 3： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="3e746-146">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)