---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: 配置 Visual Studio Team Services 部署 BizTalk Server 解决方案或项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2555712a-dfe4-420e-9a61-1d1a6d98c322
caps.latest.revision: 6
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 8b13ef6f56e892bb3598096272d876c5f0a865f3
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826301"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a><span data-ttu-id="3c009-102">配置 Visual Studio Team Services 部署 BizTalk Server 解决方案或项目</span><span class="sxs-lookup"><span data-stu-id="3c009-102">Configure Visual Studio Team Services to deploy BizTalk Server solutions or projects</span></span>
<span data-ttu-id="3c009-103">设置 VSTS 自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="3c009-103">Set up VSTS to automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] projects.</span></span> 

<span data-ttu-id="3c009-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，可以自动生成你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用 Visual Studio Team Services (VSTS) 的解决方案。</span><span class="sxs-lookup"><span data-stu-id="3c009-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically build your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] solutions using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="3c009-105">本主题演示如何设置和配置 Visual Studio Team Service (VSTS) 为 BizTalk 使用自动部署。</span><span class="sxs-lookup"><span data-stu-id="3c009-105">This topic shows you how to set up and configure Visual Studio Team Service (VSTS) to use automatic deployment for BizTalk.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3c009-106">VSTS 代理只能安装一个[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。</span><span class="sxs-lookup"><span data-stu-id="3c009-106">The VSTS agent can only be installed on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3c009-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="3c009-107">Prerequisites</span></span>

* <span data-ttu-id="3c009-108">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c009-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="3c009-109">一些经验和知识并通过创建和使用 VSTS 中的定义。</span><span class="sxs-lookup"><span data-stu-id="3c009-109">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="3c009-110">如果你是新手 VSTS，这些可能是有用的资源：</span><span class="sxs-lookup"><span data-stu-id="3c009-110">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="3c009-111">Visual Studio Team Services 概述</span><span class="sxs-lookup"><span data-stu-id="3c009-111">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="3c009-112">适用于新手的 CI/CD</span><span class="sxs-lookup"><span data-stu-id="3c009-112">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a><span data-ttu-id="3c009-113">创建 VSTS 帐户并创建定义</span><span class="sxs-lookup"><span data-stu-id="3c009-113">Create a VSTS account and create a definition</span></span>

1. <span data-ttu-id="3c009-114">在 web 浏览器中，转到您[Visual Studio online 配置文件](https://app.vsaex.visualstudio.com/go/profile)、 登录，然后选择**创建新帐户**:</span><span class="sxs-lookup"><span data-stu-id="3c009-114">In a web browser, go to your [Visual Studio online profile](https://app.vsaex.visualstudio.com/go/profile), sign in, and select a **Create new account**:</span></span>

    ![创建新帐户](../core/media/create-a-new-account.png)

2. <span data-ttu-id="3c009-116">输入帐户的名称，选择你首选的源代码存储库，并选择**继续**:</span><span class="sxs-lookup"><span data-stu-id="3c009-116">Enter a name for the account, select your preferred source code repository, and select **Continue**:</span></span>

    ![创建新项目](../core/media/create-a-new-project.png)

3. <span data-ttu-id="3c009-118">创建新帐户，和类似于站点`https://YourAccountName.visualstudio.com/MyFirstProject`随即打开。</span><span class="sxs-lookup"><span data-stu-id="3c009-118">Your new account is created, and a site similar to `https://YourAccountName.visualstudio.com/MyFirstProject` opens.</span></span>
    
4. <span data-ttu-id="3c009-119">安装[部署 BizTalk 应用程序服务](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)到刚刚创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="3c009-119">Install the [Deploy BizTalk Application service](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) to the account you just created.</span></span>

    ![生成新的发行版](../core/media/build-new-release.png)

5. <span data-ttu-id="3c009-121">你可能会收到一些提示。</span><span class="sxs-lookup"><span data-stu-id="3c009-121">You may get some prompts.</span></span> <span data-ttu-id="3c009-122">确认后才能继续。</span><span class="sxs-lookup"><span data-stu-id="3c009-122">Confirm to continue.</span></span> <span data-ttu-id="3c009-123">请确保登录到你在 VSTS 中的项目。</span><span class="sxs-lookup"><span data-stu-id="3c009-123">Be sure you're signed in to your project in VSTS.</span></span>

6. <span data-ttu-id="3c009-124">选择**生成和发布**，并创建**新建**生成定义：</span><span class="sxs-lookup"><span data-stu-id="3c009-124">Select **Build and release**, and create a **New** build definition:</span></span>

    ![选择生成和发布](../core/media/select-build-and-release.png)

    > [!TIP]
    > <span data-ttu-id="3c009-126">确保您位于`https://YourAccountName.visualstudio.com/MyFirstProject`。</span><span class="sxs-lookup"><span data-stu-id="3c009-126">Be sure you're at `https://YourAccountName.visualstudio.com/MyFirstProject`.</span></span> <span data-ttu-id="3c009-127">否则为**新建**或**新定义**按钮可能不存在。</span><span class="sxs-lookup"><span data-stu-id="3c009-127">Otherwise, the **New** or **New definition** buttons may not be there.</span></span> 
    
7. <span data-ttu-id="3c009-128">选择**Visual Studio**模板，然后选择**下一步**:</span><span class="sxs-lookup"><span data-stu-id="3c009-128">Select the **Visual Studio** template, and select **Next**:</span></span>

    ![选择 visual studio，然后单击下一步](../core/media/select-visual-studio-and-click-next.png)

8. <span data-ttu-id="3c009-130">查看你的设置，然后选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="3c009-130">Review your settings, and select **Create**.</span></span>

9. <span data-ttu-id="3c009-131">删除不需要的步骤。</span><span class="sxs-lookup"><span data-stu-id="3c009-131">Delete the steps you don't need.</span></span> <span data-ttu-id="3c009-132">对于本教程中，您可以删除以下：</span><span class="sxs-lookup"><span data-stu-id="3c009-132">For this tutorial, you can delete the following:</span></span> 
10. <span data-ttu-id="3c009-133">NuGet 还原</span><span class="sxs-lookup"><span data-stu-id="3c009-133">NuGet Restore</span></span>
11. <span data-ttu-id="3c009-134">测试程序集</span><span class="sxs-lookup"><span data-stu-id="3c009-134">Test assemblies</span></span>
12. <span data-ttu-id="3c009-135">发布符号路径</span><span class="sxs-lookup"><span data-stu-id="3c009-135">Publish symbols path</span></span> 

      ![删除不必要的步骤](../core/media/delete-steps-not-needed.png)

13. <span data-ttu-id="3c009-137">**可选**。</span><span class="sxs-lookup"><span data-stu-id="3c009-137">**Optional**.</span></span> <span data-ttu-id="3c009-138">如果你想要启用持续集成 (CI)，选择**触发器**菜单中，并检查**持续集成 (CI)**。</span><span class="sxs-lookup"><span data-stu-id="3c009-138">If you want to enable Continuous Integration (CI), select **Triggers** in the menu, and check **Continuous integration (CI)**.</span></span>

<span data-ttu-id="3c009-139">接下来，在安装代理应用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3c009-139">Next, install the agent on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="install-the-agent"></a><span data-ttu-id="3c009-140">安装代理</span><span class="sxs-lookup"><span data-stu-id="3c009-140">Install the Agent</span></span>

<span data-ttu-id="3c009-141">对于要使用的解决方案，来启用本地计算机上的专用 Windows 代理。</span><span class="sxs-lookup"><span data-stu-id="3c009-141">For the solution to work, enable a private Windows Agent on your local machine.</span></span> <span data-ttu-id="3c009-142">请记住，**必须在其中安装了代理[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中**。</span><span class="sxs-lookup"><span data-stu-id="3c009-142">Remember, **the agent must be installed on only one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group**.</span></span> 

1. <span data-ttu-id="3c009-143">在定义中，选择**常规**（顶部） 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3c009-143">In your definition, select the **General** tab (at the top).</span></span>
2. <span data-ttu-id="3c009-144">有关**默认代理队列**属性中，选择**默认**从列表中的代理。</span><span class="sxs-lookup"><span data-stu-id="3c009-144">For the **Default agent queue** property, select the **Default** agent from the list.</span></span> 
3. <span data-ttu-id="3c009-145">选择**管理**旁边**默认代理队列**属性。</span><span class="sxs-lookup"><span data-stu-id="3c009-145">Select **Manage** next to the **Default agent queue** property.</span></span> <span data-ttu-id="3c009-146">打开一个新的浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="3c009-146">A new browser tab opens.</span></span>

    ![创建新的管理代理](../core/media/create-new-management-agent.png)

4. <span data-ttu-id="3c009-148">在左窗格中，选择默认的队列。</span><span class="sxs-lookup"><span data-stu-id="3c009-148">In the left pane, the Default queue is selected.</span></span> <span data-ttu-id="3c009-149">如果代理已列出，并处于联机状态，然后完成。</span><span class="sxs-lookup"><span data-stu-id="3c009-149">If an agent is already listed, and online, then you're done.</span></span> <span data-ttu-id="3c009-150">安装代理，安装并运行。</span><span class="sxs-lookup"><span data-stu-id="3c009-150">You have an agent installed, and running.</span></span> 

    <span data-ttu-id="3c009-151">如果未列出代理，然后选择**下载代理**，并在继续进行安装你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3c009-151">If an agent is not listed, then select **Download agent**, and continue with the installation on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3c009-152">**转到[部署 Windows 代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)的完整步骤**安装代理，并启动代理。</span><span class="sxs-lookup"><span data-stu-id="3c009-152">**Go to [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) for the complete steps** to install the agent, and start an agent.</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="3c009-153">请按照在所有步骤[Windows 上部署代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)。</span><span class="sxs-lookup"><span data-stu-id="3c009-153">Follow all the steps at [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows).</span></span> <span data-ttu-id="3c009-154">请勿跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="3c009-154">Do not skip this step.</span></span> 

5. <span data-ttu-id="3c009-155">使用默认代理**联机**，返回**常规**选项卡上，在定义中，并确认**默认**为选择**默认代理队列**.</span><span class="sxs-lookup"><span data-stu-id="3c009-155">With the default agent **Online**, go back to the **General** tab in your definition, and confirm **Default** is selected for the **Default agent queue**.</span></span>
6. <span data-ttu-id="3c009-156">**保存**并**使新生成入队**。</span><span class="sxs-lookup"><span data-stu-id="3c009-156">**Save** and **Queue new build**.</span></span>

<span data-ttu-id="3c009-157">接下来，创建 BizTalk Server 应用程序部署定义。</span><span class="sxs-lookup"><span data-stu-id="3c009-157">Next, create the BizTalk Server Application Deployment definition.</span></span>

## <a name="create-the-biztalk-deployment-definition"></a><span data-ttu-id="3c009-158">创建 BizTalk 部署定义</span><span class="sxs-lookup"><span data-stu-id="3c009-158">Create the BizTalk deployment definition</span></span>

1. <span data-ttu-id="3c009-159">选择**生成**选项卡上，选择**所有定义**，然后选择**新建**:</span><span class="sxs-lookup"><span data-stu-id="3c009-159">Select the **Builds** tab, select **All Definitions**, and select **New**:</span></span>

    ![创建新发布定义](../core/media/create-new-release-definition.png)

2. <span data-ttu-id="3c009-161">选择**空**模板，然后选择**下一步**:</span><span class="sxs-lookup"><span data-stu-id="3c009-161">Select the **Empty** template, and select **Next**:</span></span>

    ![从空白模板创建新的定义](../core/media/create-new-definition-from-an-empty-template.png)

3. <span data-ttu-id="3c009-163">选择你**存储库**源和**分支**有关定义的信息。</span><span class="sxs-lookup"><span data-stu-id="3c009-163">Select your **Repository** source and **Branch** for the definition.</span></span>
4. <span data-ttu-id="3c009-164">**可选**。</span><span class="sxs-lookup"><span data-stu-id="3c009-164">**Optional**.</span></span> <span data-ttu-id="3c009-165">选择**持续集成**。</span><span class="sxs-lookup"><span data-stu-id="3c009-165">Select **Continuous Integration**.</span></span>
5. <span data-ttu-id="3c009-166">选择**默认**代理从队列列表中，然后选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="3c009-166">Select the **Default** agent from the queue list, and select **Create**.</span></span>
6. <span data-ttu-id="3c009-167">**添加生成步骤**，选择**BizTalk Server 应用程序部署**任务，并选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="3c009-167">**Add build step**, select the **BizTalk Server Application Deployment** task, and select **Add**.</span></span> <span data-ttu-id="3c009-168">**关闭**任务目录中。</span><span class="sxs-lookup"><span data-stu-id="3c009-168">**Close** the task catalog.</span></span>

    ![添加新部署定义](../core/media/add-new-deploy-definition.png)

7. <span data-ttu-id="3c009-170">选择**操作名称**你想要使用：</span><span class="sxs-lookup"><span data-stu-id="3c009-170">Select the **Operation Name** you want to use:</span></span>

    * <span data-ttu-id="3c009-171">**创建新的 BizTalk 应用程序**部署新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c009-171">**Create new BizTalk Application** deploys a new application.</span></span> <span data-ttu-id="3c009-172">如果应用程序已存在，它会卸载当前应用程序 （句号），并安装新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c009-172">If the application already exist, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="3c009-173">如果启用持续集成，则它会自动重新部署应用程序在更新存储库中时。</span><span class="sxs-lookup"><span data-stu-id="3c009-173">If continous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span>
    * <span data-ttu-id="3c009-174">**更新现有的 BizTalk 应用程序**附加更改，例如**架构**到已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c009-174">**Update an existing BizTalk Application** appends changes, such as **Schemas** to an already running application.</span></span> <span data-ttu-id="3c009-175">它不需要完全重新部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c009-175">It does not require a full redeploy of the application.</span></span>

8. <span data-ttu-id="3c009-176">输入**应用程序名称**在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="3c009-176">Enter the **Application name** in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>
9. <span data-ttu-id="3c009-177">在中**部署的包路径**，选择你的存储库中的 zip 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="3c009-177">In **Deployment package path**, select the path to the zip file in your repository.</span></span>
10. <span data-ttu-id="3c009-178">选择**触发器**菜单中，启用**持续集成**，并选择正确**分支**生成。</span><span class="sxs-lookup"><span data-stu-id="3c009-178">Select **Triggers** from the menu, enable **Continuous Integration**, and select the correct **Branch** for the build.</span></span>
11. <span data-ttu-id="3c009-179">选择**保存**:</span><span class="sxs-lookup"><span data-stu-id="3c009-179">Select **Save**:</span></span>

    ![保存新的生成定义](../core/media/save-the-new-build-definition.png)

12. <span data-ttu-id="3c009-181">指定新**定义**，并设置正确的路径。</span><span class="sxs-lookup"><span data-stu-id="3c009-181">Name the new **Definition**, and set the correct path.</span></span> 
13. <span data-ttu-id="3c009-182">保存定义后，选择**使新生成入队**。</span><span class="sxs-lookup"><span data-stu-id="3c009-182">Once the definition is saved, select **Queue the new build**.</span></span> <span data-ttu-id="3c009-183">然后，选择**队列代理**，并将注释添加到该提交。</span><span class="sxs-lookup"><span data-stu-id="3c009-183">Then, select the **Queue agent**, and add a comment to the commit.</span></span>
