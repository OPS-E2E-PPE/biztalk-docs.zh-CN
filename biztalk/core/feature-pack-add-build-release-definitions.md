---
title: 第 3 步-创建的生成和发布定义 |Microsoft 文档
description: 在 VSTS，创建要生成你的 git 或 TFS 存储库中的项目，然后创建要部署 BizTalk Server 应用程序的版本定义的生成定义
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2df2cb82508a12e8e8d279204130d2deedd744f4
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="step-3-create-the-build-and-release-definition"></a><span data-ttu-id="e5d5f-103">步骤 3： 创建构建并发布定义</span><span class="sxs-lookup"><span data-stu-id="e5d5f-103">Step 3: Create the build and release definition</span></span>

<span data-ttu-id="e5d5f-104">生成和发布定义 Visual Studio Team Services 任务，并且可能通过 VSTS 管理员联系。生成定义将生成在 git 存储库时，项目和版本定义将将其部署到您的 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-104">The build and release definitions are Visual Studio Team Services tasks, and should probably be done by a VSTS admin. The build definition builds your project within your git repository, and the release definitions deploys it to your BizTalk Server environment.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="e5d5f-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="e5d5f-105">Before you begin</span></span>
<span data-ttu-id="e5d5f-106">完成[步骤 2-创建 VSTS 令牌并安装代理](feature-pack-create-vsts-token.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-106">Complete [Step 2 - Create VSTS token and install agent](feature-pack-create-vsts-token.md).</span></span>

## <a name="add-the-build-tasks"></a><span data-ttu-id="e5d5f-107">添加生成任务</span><span class="sxs-lookup"><span data-stu-id="e5d5f-107">Add the Build tasks</span></span>
1. <span data-ttu-id="e5d5f-108">在项目中，选择**生成和发布**。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-108">In your project, select **Build and release**.</span></span> <span data-ttu-id="e5d5f-109">生成选项卡将打开。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-109">The Builds tab opens.</span></span> <span data-ttu-id="e5d5f-110">创建**新建**定义：</span><span class="sxs-lookup"><span data-stu-id="e5d5f-110">Create a **New** definition:</span></span>

    ![新的生成定义](../core/media/vsts-new-definition.png)

2. <span data-ttu-id="e5d5f-112">选择**空**模板，然后选择**应用**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-112">Select the **Empty** template, and select **Apply**:</span></span>  

    ![选择空模板](../core/media/vsts-emtpy-template.png)
 
3. <span data-ttu-id="e5d5f-114">设置**代理队列**为默认值：</span><span class="sxs-lookup"><span data-stu-id="e5d5f-114">Set the **Agent Queue** to Default:</span></span> 

    ![选择默认的队列](../core/media/vsts-select-agent-queue.png)

4. <span data-ttu-id="e5d5f-116">在**第 1 阶段**，添加任务，选择**Visual Studio 生成**，然后选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-116">In **Phase 1**, add a task, select **Visual Studio Build**, and select **Add**:</span></span>

    ![添加 VS 生成任务](../core/media/vsts-add-visual-studio-task.png)

5. <span data-ttu-id="e5d5f-118">单击 Visual Studio 生成的任务，只需添加，并设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="e5d5f-118">Click the Visual Studio Build task you just added, and set the following properties:</span></span>  

    | <span data-ttu-id="e5d5f-119">属性</span><span class="sxs-lookup"><span data-stu-id="e5d5f-119">Property</span></span> | <span data-ttu-id="e5d5f-120">设置为</span><span class="sxs-lookup"><span data-stu-id="e5d5f-120">Set to</span></span> |
    | --- | --- | 
    | <span data-ttu-id="e5d5f-121">显示名称</span><span class="sxs-lookup"><span data-stu-id="e5d5f-121">Display name</span></span> | <span data-ttu-id="e5d5f-122">*YourProjectName*生成解决方案 \* \*\*.sln</span><span class="sxs-lookup"><span data-stu-id="e5d5f-122">*YourProjectName* Build solution \*\*\*.sln</span></span> | 
    | <span data-ttu-id="e5d5f-123">Visual Studio 版本</span><span class="sxs-lookup"><span data-stu-id="e5d5f-123">Visual Studio version</span></span> | <span data-ttu-id="e5d5f-124">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="e5d5f-124">Visual Studio 2015</span></span> | 
    | <span data-ttu-id="e5d5f-125">MSBuild 体系结构</span><span class="sxs-lookup"><span data-stu-id="e5d5f-125">MSBuild Architecture</span></span> | <span data-ttu-id="e5d5f-126">MSBuild x86</span><span class="sxs-lookup"><span data-stu-id="e5d5f-126">MSBuild x86</span></span> | 

6. <span data-ttu-id="e5d5f-127">在**第 1 阶段**，添加任务，选择**发布生成项目**，然后选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-127">In **Phase 1**, add a task, select **Publish Build Artifacts**, and select **Add**:</span></span> 

    ![添加 VS 生成任务](../core/media/vsts-add-publish-build-task.png)

7. <span data-ttu-id="e5d5f-129">选择**发布项目**任务，并输入你首选**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-129">Select the **Publish Artifact** task, and enter your preferred **Display name**.</span></span> <span data-ttu-id="e5d5f-130">有关**路径发布**，选择 **...** 按钮，然后选择应用程序项目文件夹 (例如 appProjectHelloWorld)。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-130">For **Path to publish**, select the **...**  button, and choose the application project folder (e.g. appProjectHelloWorld).</span></span> <span data-ttu-id="e5d5f-131">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-131">Select **OK**.</span></span>

8. <span data-ttu-id="e5d5f-132">**项目名称**可以是任何需要的内容。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-132">The **Artifact Name** can be anything you want.</span></span> <span data-ttu-id="e5d5f-133">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-133">Select **Save**.</span></span> 

9. <span data-ttu-id="e5d5f-134">转到**触发器**，并设置**触发状态**到**已启用**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-134">Go to **Triggers**, and set the **Trigger status** to **Enabled**:</span></span>  

    ![添加 VS 生成任务](../core/media/vsts-continuous-integration.png)

10. <span data-ttu-id="e5d5f-136">**保存并队列**若要测试你的生成定义。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-136">**Save & Queue** to test your build definition.</span></span> <span data-ttu-id="e5d5f-137">当您进行排队，提示你输入代理队列和你的分支。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-137">When you queue, you are prompted for the agent queue and your branch.</span></span> <span data-ttu-id="e5d5f-138">选择**默认**代理排队，并选择你的分支。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-138">Select the **Default** agent queue, and choose your branch.</span></span> <span data-ttu-id="e5d5f-139">选择**队列**。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-139">Select **Queue**.</span></span>  

11. <span data-ttu-id="e5d5f-140">将启动新的生成，并且你可以选择它以检查成功或失败。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-140">A new build is started, and you can select it to check for a success or failure.</span></span> 

## <a name="add-the-release-tasks"></a><span data-ttu-id="e5d5f-141">添加释放任务</span><span class="sxs-lookup"><span data-stu-id="e5d5f-141">Add the release tasks</span></span>

<span data-ttu-id="e5d5f-142">时生成成功，版本定义将部署到你的 BizTalk 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-142">When the build succeeds, the release definition deploys your application to your BizTalk Server.</span></span> 

1. <span data-ttu-id="e5d5f-143">选择**版本**选项卡上，选择**新定义**。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-143">Select the **Releases** tab, select **New definition**.</span></span> 

2. <span data-ttu-id="e5d5f-144">选择**空**模板，然后选择**应用**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-144">Select the **Empty** template, and select **Apply**:</span></span>

    ![添加空模板](../core/media/vsts-empty-release-template.png)

3. <span data-ttu-id="e5d5f-146">更改**环境名称**到**开发人员**，或者你想要调用它的任何内容。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-146">Change the **Environment name** to **Dev**, or whatever you want to call it.</span></span> 

4. <span data-ttu-id="e5d5f-147">选择**添加项目**，选择你的项目，生成定义中，并选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-147">Select **Add artifact**, select your project, your build definition, and select **Add**:</span></span> 

5. <span data-ttu-id="e5d5f-148">转到**任务**选项卡上，添加新任务：</span><span class="sxs-lookup"><span data-stu-id="e5d5f-148">Go to the **Tasks** tab, add a new task:</span></span> 

    ![添加版本任务](../core/media/vsts-new-release-tasks.png)

6. <span data-ttu-id="e5d5f-150">从列表中，筛选结果，请选择**BizTalk Server 应用程序部署**任务，并选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-150">From the list, filter the results, select the **BizTalk Server Application Deployment** task, and select **Add**:</span></span>  

    ![添加 BizTalk 部署任务](../core/media/vsts-biztalk-application-deployment-task.png)

    <span data-ttu-id="e5d5f-152">如果**BizTalk Server 应用程序部署**ins't 列出，然后将其在安装[部署 BizTalk 应用程序](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-152">If **BizTalk Server Application Deployment** ins't listed, then install it at [Deploy BizTalk Application](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).</span></span>

7. <span data-ttu-id="e5d5f-153">选择**部署**任务，并输入值：</span><span class="sxs-lookup"><span data-stu-id="e5d5f-153">Select the **Deploy** task, and enter the values:</span></span> 

    <span data-ttu-id="e5d5f-154">**操作名称**： 你的选项: \***创建新的 BizTalk 应用程序**： 部署一个新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-154">**Operation Name**: Your options: \* **Create new BizTalk Application**: Deploys a new application.</span></span> <span data-ttu-id="e5d5f-155">如果应用程序已存在，它会卸载当前的应用程序 （句号），并安装新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-155">If the application already exists, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="e5d5f-156">如果启用持续集成，则它会自动将重新部署应用程序更新存储库中时。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-156">If continuous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span> 
        <span data-ttu-id="e5d5f-157">\* **更新现有的 BizTalk 应用程序**： 将更改，如架构，追加到已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-157">\* **Update an existing BizTalk Application**: Appends changes, such as schemas, to an already running application.</span></span> <span data-ttu-id="e5d5f-158">它不需要应用程序完全重新部署。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-158">It does not require a full redeploy of the application.</span></span>
        <span data-ttu-id="e5d5f-159">\* **安装 BizTalk Server 应用程序**:[安装应用程序](../core/how-to-install-a-biztalk-application.md)，然后输入的 BizTalk 管理计算机的名称和部署包路径。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-159">\* **Install BizTalk Server Application**: [Install the applications](../core/how-to-install-a-biztalk-application.md), and you enter the BizTalk management computer name, and the deployment package path.</span></span>

     ![部署操作](../core/media/vsts-deploy-operations.png)

    <span data-ttu-id="e5d5f-161">**应用程序名称**： 您输入的文本将是在 BizTalk 管理的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-161">**Application Name**: The text you enter will be the application name in BizTalk Administration.</span></span> <span data-ttu-id="e5d5f-162">执行**不**输入 BizTalk 应用程序 1。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-162">Do **not** enter BizTalk Application 1.</span></span>

    <span data-ttu-id="e5d5f-163">**部署包**： 选择您的应用程序项目，该 zip 文件，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-163">**Deployment package**: Select the zip file to your application project, and select **OK**.</span></span> 

8. <span data-ttu-id="e5d5f-164">选择**代理阶段**任务。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-164">Select the **Agent phase** task.</span></span> <span data-ttu-id="e5d5f-165">选择**默认**代理队列。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-165">Select the **Default** Agent queue.</span></span> <span data-ttu-id="e5d5f-166">**保存** 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-166">**Save** your changes.</span></span>

9. <span data-ttu-id="e5d5f-167">选择**释放** > **创建版本**:</span><span class="sxs-lookup"><span data-stu-id="e5d5f-167">Select **Release** > **Create release**:</span></span>  

    ![发行版中，创建版本](../core/media/vsts-create-release.png)

10. <span data-ttu-id="e5d5f-169">选择**队列**。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-169">Select **Queue**.</span></span> <span data-ttu-id="e5d5f-170">通过单击版本链接检查的状态。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-170">Check the status by clicking the release link.</span></span> <span data-ttu-id="e5d5f-171">如果失败，错误显示。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-171">If it fails, the error displays.</span></span> <span data-ttu-id="e5d5f-172">如果成功，则会将应用程序添加到 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-172">If it succeeds, the application is added to the BizTalk Administration console.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="e5d5f-173">您进行的操作</span><span class="sxs-lookup"><span data-stu-id="e5d5f-173">What you did</span></span>

<span data-ttu-id="e5d5f-174">在 VSTS，你将创建一个生成定义构建你的应用程序内 Git 或 Team Foundation 版本控制 （无论你选择）。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-174">In VSTS, you created a build definition that builds your application within Git or Team Foundation Version Control (whatever you chose).</span></span> <span data-ttu-id="e5d5f-175">当源控件中进行更改时，所做的更改会自动检测，并可以将它们推送。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-175">When changes are made within the source control, the changes are automatically detected, and you can push them.</span></span> <span data-ttu-id="e5d5f-176">在生成完成后，你将创建部署到 BizTalk Server 中，你可以在 BizTalk Server 管理中看到应用程序的版本定义。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-176">After the build completes, you created a release definition that deploys the application to BizTalk Server, which you can see in BizTalk Server Administration.</span></span> 

## <a name="next-step"></a><span data-ttu-id="e5d5f-177">下一步</span><span class="sxs-lookup"><span data-stu-id="e5d5f-177">Next step</span></span>
<span data-ttu-id="e5d5f-178">在此步骤中，你已完成。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-178">At this step, you're done.</span></span> <span data-ttu-id="e5d5f-179">如果你愿意，可以在 BizTalk XML 绑定文件中，创建环境的令牌，并创建与环境的令牌匹配的 VSTS 中的变量。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-179">If you prefer, you can create environmental tokens within your BizTalk XML binding file, and create variables within VSTS that match the environmental tokens.</span></span> <span data-ttu-id="e5d5f-180">请参阅[配置环境的令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5d5f-180">See [Configure environmental tokens and variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) for the details.</span></span> 
