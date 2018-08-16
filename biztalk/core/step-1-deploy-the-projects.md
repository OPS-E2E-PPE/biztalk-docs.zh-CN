---
title: 步骤 1： 部署项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b25af8ee1095a5365fabd955f7185acbc79254db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007550"
---
# <a name="step-1-deploy-the-projects"></a><span data-ttu-id="675cb-102">步骤 1：部署项目</span><span class="sxs-lookup"><span data-stu-id="675cb-102">Step 1: Deploy the Projects</span></span>
<span data-ttu-id="675cb-103">![3 的第 1 步](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="675cb-103">![Step 1 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="675cb-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="675cb-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="675cb-105">**目标：** 在此步骤中，部署了 EAISchemas 和 EAIOrchestration 项目。</span><span class="sxs-lookup"><span data-stu-id="675cb-105">**Objective:** In this step, you deploy the EAISchemas and EAIOrchestration projects.</span></span>  
  
 <span data-ttu-id="675cb-106">**目的：** 时部署项目或解决方案在 Visual Studio 中的，程序集是自动生成并部署到指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="675cb-106">**Purpose:** When you deploy a project or solution in Visual Studio, the assemblies are automatically built and deployed into the specified application.</span></span> <span data-ttu-id="675cb-107">在此过程中，程序集连同它所包含的业务流程、架构和映射（称为“项目”）将导入本地 BizTalk 管理数据库，并在该数据库中与指定的应用程序建立关联。</span><span class="sxs-lookup"><span data-stu-id="675cb-107">As part of this process, the assembly along with the orchestrations, schemas, and maps that it contains (called "artifacts") are imported into the local BizTalk Management database and associated in the database with the specified application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="675cb-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="675cb-108">Prerequisites</span></span>  
  
- [<span data-ttu-id="675cb-109">第 1 课：定义架构和映射</span><span class="sxs-lookup"><span data-stu-id="675cb-109">Lesson 1: Define Schemas and a Map</span></span>](../core/lesson-1-define-schemas-and-a-map.md)  
  
- [<span data-ttu-id="675cb-110">第 2 课：定义业务流程</span><span class="sxs-lookup"><span data-stu-id="675cb-110">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)  
  
- <span data-ttu-id="675cb-111">以的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组</span><span class="sxs-lookup"><span data-stu-id="675cb-111">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group</span></span>

- <span data-ttu-id="675cb-112">使用管理权限运行 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="675cb-112">Run Visual Studio with Administrative privileges</span></span>

> [!TIP]
> <span data-ttu-id="675cb-113">您可以下载所需的教程文件位于[教程 1： 企业应用程序集成](https://www.microsoft.com/download/details.aspx?id=22793)。</span><span class="sxs-lookup"><span data-stu-id="675cb-113">You can download the required tutorial files at [Tutorial 1: Enterprise Application Integration](https://www.microsoft.com/download/details.aspx?id=22793).</span></span>

## <a name="open-the-solution-with-administrative-rights"></a><span data-ttu-id="675cb-114">使用管理权限打开的解决方案</span><span class="sxs-lookup"><span data-stu-id="675cb-114">Open the solution with administrative rights</span></span>  
  
1. <span data-ttu-id="675cb-115">BizTalk Server Administrators 组的成员身份登录到 Windows。</span><span class="sxs-lookup"><span data-stu-id="675cb-115">Sign in to Windows as a member of the BizTalk Server Administrators group.</span></span>  
  
2. <span data-ttu-id="675cb-116">启动**Microsoft Visual Studio**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="675cb-116">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
3. <span data-ttu-id="675cb-117">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="675cb-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
4. <span data-ttu-id="675cb-118">在中**打开项目**对话框中，浏览到**EAISolution.sln**项目解决方案文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="675cb-118">In the **Open Project** dialog box, browse to the **EAISolution.sln** project solution file, and then click **Open**.</span></span>  
  
   <span data-ttu-id="675cb-119">部署过程要求程序集是强签名的。</span><span class="sxs-lookup"><span data-stu-id="675cb-119">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="675cb-120">必须通过将该项目与一个强名称程序集密钥文件相关联来签名你的程序集。</span><span class="sxs-lookup"><span data-stu-id="675cb-120">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  <span data-ttu-id="675cb-121">此文件包含在教程文件中。</span><span class="sxs-lookup"><span data-stu-id="675cb-121">This file is included in the tutorial files.</span></span>  
  
   <span data-ttu-id="675cb-122">BizTalk 应用程序是 BizTalk Server 的一项功能，可使你更快、更轻松地对 BizTalk Server 业务解决方案进行部署、管理和故障排除。</span><span class="sxs-lookup"><span data-stu-id="675cb-122">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="675cb-123">BizTalk 应用程序是 BizTalk Server 业务解决方案中使用的项（称为“项目”）的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="675cb-123">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span> <span data-ttu-id="675cb-124">可为项目指定应用程序名。</span><span class="sxs-lookup"><span data-stu-id="675cb-124">We can specify an application name for a project.</span></span>  <span data-ttu-id="675cb-125">部署过程会自动创建新的应用程序如果不存在具有指定的名称。</span><span class="sxs-lookup"><span data-stu-id="675cb-125">The deployment process automatically creates a new application having the specified name if it doesn’t exist.</span></span>  
  
## <a name="configure-and-deploy-the-projects"></a><span data-ttu-id="675cb-126">配置和部署项目</span><span class="sxs-lookup"><span data-stu-id="675cb-126">Configure and deploy the projects</span></span>  
  
1.  <span data-ttu-id="675cb-127">在解决方案资源管理器中右键单击**EAISchemas**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="675cb-127">In Solution Explorer, right-click the **EAISchemas** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="675cb-128">单击**签名**选项卡上，选择**程序集签名**。</span><span class="sxs-lookup"><span data-stu-id="675cb-128">Click the **Signing** tab, select **Sign the assembly**.</span></span>  
  
3.  <span data-ttu-id="675cb-129">从下拉列表中**选择强名称密钥文件**框中，选择**\<浏览...\>**.</span><span class="sxs-lookup"><span data-stu-id="675cb-129">From the drop-down list in the **Choose a strong name key file** box, select **\<Browse…\>**.</span></span>  
  
4.  <span data-ttu-id="675cb-130">在中**选择文件**对话框框中，导航到**C:\BTStutorials**，单击**btsTutorials.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="675cb-130">In the **Select File** dialog box, navigate to **C:\BTStutorials**, click **btsTutorials.snk**, and then click **Open**.</span></span> 
  
5.  <span data-ttu-id="675cb-131">单击**部署**选项卡上，在右侧的框中**应用程序名称**，类型`EAISolution`。</span><span class="sxs-lookup"><span data-stu-id="675cb-131">Click the **Deployment** tab, in the box to the right of **Application Name**, type `EAISolution`.</span></span>  
  
6.  <span data-ttu-id="675cb-132">从下拉列表右侧的框中**重新部署**，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="675cb-132">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
7.  <span data-ttu-id="675cb-133">在解决方案资源管理器中右键单击**EAISchemas**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="675cb-133">In Solution Explorer, right-click **EAISchemas**, and then click **Deploy**.</span></span>  <span data-ttu-id="675cb-134">“输出”窗口应显示：</span><span class="sxs-lookup"><span data-stu-id="675cb-134">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  <span data-ttu-id="675cb-135">重复步骤 1 至 7 以部署 EAIOrchestration 项目。</span><span class="sxs-lookup"><span data-stu-id="675cb-135">Repeat steps 1 through 7 to deploy the EAIOrchestration project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="675cb-136">内容回顾</span><span class="sxs-lookup"><span data-stu-id="675cb-136">What did I just do?</span></span>  
 <span data-ttu-id="675cb-137">在此步骤中，你已部署了 EAISchemas 和 EAIOrchestration 项目。</span><span class="sxs-lookup"><span data-stu-id="675cb-137">In this step, you deployed the EAISchemas and EAIOrchestration projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="675cb-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="675cb-138">Next Steps</span></span>  
 <span data-ttu-id="675cb-139">创建物理端口，然后将其绑定到业务流程的逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="675cb-139">You create the physical ports, and bind them to the logical ports of the orchestration.</span></span>  
  
 <span data-ttu-id="675cb-140">[步骤 2： 配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md) </span><span class="sxs-lookup"><span data-stu-id="675cb-140">[Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md) </span></span>  
 [<span data-ttu-id="675cb-141">步骤 3：测试解决方案</span><span class="sxs-lookup"><span data-stu-id="675cb-141">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)
