---
title: 步骤 3-创建生成和发布定义 |Microsoft Docs
description: 在 VSTS 中，创建生成定义以生成您的 git 或 TFS 存储库中的项目，然后创建发布定义部署 BizTalk Server 应用程序
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
ms.openlocfilehash: fd25c92b7b9abea02bb7366c9c4cc83e68dff3aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345840"
---
# <a name="step-3-create-the-build-and-release-definition"></a><span data-ttu-id="cbcc2-103">步骤 3：创建生成和发布定义</span><span class="sxs-lookup"><span data-stu-id="cbcc2-103">Step 3: Create the build and release definition</span></span>

<span data-ttu-id="cbcc2-104">生成和发布定义 Visual Studio Team Services 任务，并且可能通过 VSTS 管理员。生成定义将生成在 git 存储库时，你的项目和发布定义将将其部署到 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-104">The build and release definitions are Visual Studio Team Services tasks, and should probably be done by a VSTS admin. The build definition builds your project within your git repository, and the release definitions deploys it to your BizTalk Server environment.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="cbcc2-105">开始之前</span><span class="sxs-lookup"><span data-stu-id="cbcc2-105">Before you begin</span></span>
<span data-ttu-id="cbcc2-106">完整[步骤 2-创建 VSTS 令牌和安装代理](feature-pack-create-vsts-token.md)。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-106">Complete [Step 2 - Create VSTS token and install agent](feature-pack-create-vsts-token.md).</span></span>

## <a name="add-the-build-tasks"></a><span data-ttu-id="cbcc2-107">添加生成任务</span><span class="sxs-lookup"><span data-stu-id="cbcc2-107">Add the Build tasks</span></span>
1. <span data-ttu-id="cbcc2-108">在项目中，选择**生成和发布**。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-108">In your project, select **Build and release**.</span></span> <span data-ttu-id="cbcc2-109">生成选项卡将打开。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-109">The Builds tab opens.</span></span> <span data-ttu-id="cbcc2-110">创建**新建**定义：</span><span class="sxs-lookup"><span data-stu-id="cbcc2-110">Create a **New** definition:</span></span>

    ![新的生成定义](../core/media/vsts-new-definition.png)

2. <span data-ttu-id="cbcc2-112">选择**空**模板，然后选择**应用**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-112">Select the **Empty** template, and select **Apply**:</span></span>  

    ![选择空模板](../core/media/vsts-emtpy-template.png)
 
3. <span data-ttu-id="cbcc2-114">设置**代理队列**为默认值：</span><span class="sxs-lookup"><span data-stu-id="cbcc2-114">Set the **Agent Queue** to Default:</span></span> 

    ![选择默认队列](../core/media/vsts-select-agent-queue.png)

4. <span data-ttu-id="cbcc2-116">在**第 1 阶段**，添加一个任务中，选择**Visual Studio 生成**，然后选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-116">In **Phase 1**, add a task, select **Visual Studio Build**, and select **Add**:</span></span>

    ![添加 VS 生成任务](../core/media/vsts-add-visual-studio-task.png)

5. <span data-ttu-id="cbcc2-118">单击 Visual Studio 生成的任务，只需添加，并设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cbcc2-118">Click the Visual Studio Build task you just added, and set the following properties:</span></span>  

    | <span data-ttu-id="cbcc2-119">属性</span><span class="sxs-lookup"><span data-stu-id="cbcc2-119">Property</span></span> | <span data-ttu-id="cbcc2-120">设置为</span><span class="sxs-lookup"><span data-stu-id="cbcc2-120">Set to</span></span> |
    | --- | --- | 
    | <span data-ttu-id="cbcc2-121">Display name</span><span class="sxs-lookup"><span data-stu-id="cbcc2-121">Display name</span></span> | <span data-ttu-id="cbcc2-122">*YourProjectName*构建的解决方案 \* \*\*.sln</span><span class="sxs-lookup"><span data-stu-id="cbcc2-122">*YourProjectName* Build solution \*\*\*.sln</span></span> | 
    | <span data-ttu-id="cbcc2-123">Visual Studio 版本</span><span class="sxs-lookup"><span data-stu-id="cbcc2-123">Visual Studio version</span></span> | <span data-ttu-id="cbcc2-124">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="cbcc2-124">Visual Studio 2015</span></span> | 
    | <span data-ttu-id="cbcc2-125">MSBuild 体系结构</span><span class="sxs-lookup"><span data-stu-id="cbcc2-125">MSBuild Architecture</span></span> | <span data-ttu-id="cbcc2-126">MSBuild x86</span><span class="sxs-lookup"><span data-stu-id="cbcc2-126">MSBuild x86</span></span> | 

6. <span data-ttu-id="cbcc2-127">在**第 1 阶段**，添加一个任务中，选择**发布生成项目**，然后选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-127">In **Phase 1**, add a task, select **Publish Build Artifacts**, and select **Add**:</span></span> 

    ![添加 VS 生成任务](../core/media/vsts-add-publish-build-task.png)

7. <span data-ttu-id="cbcc2-129">选择**发布的项目**任务，并输入首选**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-129">Select the **Publish Artifact** task, and enter your preferred **Display name**.</span></span> <span data-ttu-id="cbcc2-130">有关**发布路径**，选择 **...** 按钮，然后选择应用程序项目文件夹 (例如 appProjectHelloWorld)。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-130">For **Path to publish**, select the **...**  button, and choose the application project folder (e.g. appProjectHelloWorld).</span></span> <span data-ttu-id="cbcc2-131">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-131">Select **OK**.</span></span>

8. <span data-ttu-id="cbcc2-132">**项目名称**可以是任何需要的内容。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-132">The **Artifact Name** can be anything you want.</span></span> <span data-ttu-id="cbcc2-133">选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-133">Select **Save**.</span></span> 

9. <span data-ttu-id="cbcc2-134">转到**触发器**，并设置**触发状态**到**已启用**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-134">Go to **Triggers**, and set the **Trigger status** to **Enabled**:</span></span>  

    ![添加 VS 生成任务](../core/media/vsts-continuous-integration.png)

10. <span data-ttu-id="cbcc2-136">**保存并排队**来测试你的生成定义。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-136">**Save & Queue** to test your build definition.</span></span> <span data-ttu-id="cbcc2-137">进行排队时，系统会提示输入代理队列和你的分支。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-137">When you queue, you are prompted for the agent queue and your branch.</span></span> <span data-ttu-id="cbcc2-138">选择**默认**代理队列，然后选择你的分支。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-138">Select the **Default** agent queue, and choose your branch.</span></span> <span data-ttu-id="cbcc2-139">选择**队列**。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-139">Select **Queue**.</span></span>  

11. <span data-ttu-id="cbcc2-140">将启动新的生成，并且可以选择它以检查成功或失败。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-140">A new build is started, and you can select it to check for a success or failure.</span></span> 

## <a name="add-the-release-tasks"></a><span data-ttu-id="cbcc2-141">添加发布任务</span><span class="sxs-lookup"><span data-stu-id="cbcc2-141">Add the release tasks</span></span>

<span data-ttu-id="cbcc2-142">生成成功后，发布定义部署到 BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-142">When the build succeeds, the release definition deploys your application to your BizTalk Server.</span></span> 

1. <span data-ttu-id="cbcc2-143">选择**版本**选项卡上，选择**新定义**。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-143">Select the **Releases** tab, select **New definition**.</span></span> 

2. <span data-ttu-id="cbcc2-144">选择**空**模板，然后选择**应用**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-144">Select the **Empty** template, and select **Apply**:</span></span>

    ![添加空的模板](../core/media/vsts-empty-release-template.png)

3. <span data-ttu-id="cbcc2-146">更改**环境名称**到**开发人员**，或者任何你想要调用它。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-146">Change the **Environment name** to **Dev**, or whatever you want to call it.</span></span> 

4. <span data-ttu-id="cbcc2-147">选择**添加项目**，选择你的项目，生成定义中，然后选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-147">Select **Add artifact**, select your project, your build definition, and select **Add**:</span></span> 

5. <span data-ttu-id="cbcc2-148">转到**任务**选项卡上，添加新的任务：</span><span class="sxs-lookup"><span data-stu-id="cbcc2-148">Go to the **Tasks** tab, add a new task:</span></span> 

    ![添加发布任务](../core/media/vsts-new-release-tasks.png)

6. <span data-ttu-id="cbcc2-150">从列表中，筛选结果，请选择**BizTalk Server 应用程序部署**任务，并选择**添加**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-150">From the list, filter the results, select the **BizTalk Server Application Deployment** task, and select **Add**:</span></span>  

    ![添加 BizTalk 部署任务](../core/media/vsts-biztalk-application-deployment-task.png)

    <span data-ttu-id="cbcc2-152">如果**BizTalk Server 应用程序部署**ins't 列出，请将其安装在[部署 BizTalk 应用程序](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-152">If **BizTalk Server Application Deployment** ins't listed, then install it at [Deploy BizTalk Application](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).</span></span>

7. <span data-ttu-id="cbcc2-153">选择**部署**任务，并输入值：</span><span class="sxs-lookup"><span data-stu-id="cbcc2-153">Select the **Deploy** task, and enter the values:</span></span> 

    <span data-ttu-id="cbcc2-154">**操作名称**:选项包括：</span><span class="sxs-lookup"><span data-stu-id="cbcc2-154">**Operation Name**: Your options:</span></span>   
        <span data-ttu-id="cbcc2-155">- **创建新的 BizTalk 应用程序**:部署新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-155">- **Create new BizTalk Application**: Deploys a new application.</span></span> <span data-ttu-id="cbcc2-156">如果应用程序已存在，它会卸载当前应用程序 （句号），并安装新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-156">If the application already exists, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="cbcc2-157">如果启用持续集成，则它会自动重新部署应用程序在更新存储库中时。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-157">If continuous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span>   
        <span data-ttu-id="cbcc2-158">- **更新现有的 BizTalk 应用程序**:将更改，例如架构、 追加到已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-158">- **Update an existing BizTalk Application**: Appends changes, such as schemas, to an already running application.</span></span> <span data-ttu-id="cbcc2-159">它不需要完全重新部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-159">It does not require a full redeploy of the application.</span></span>  
        <span data-ttu-id="cbcc2-160">- **安装 BizTalk Server 应用程序**:[安装的应用程序](../core/how-to-install-a-biztalk-application.md)，并输入 BizTalk 管理计算机名，以及部署包路径。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-160">- **Install BizTalk Server Application**: [Install the applications](../core/how-to-install-a-biztalk-application.md), and you enter the BizTalk management computer name, and the deployment package path.</span></span>  

     ![部署操作](../core/media/vsts-deploy-operations.png)

    <span data-ttu-id="cbcc2-162">**应用程序名称**:你输入的文本将是在 BizTalk 管理的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-162">**Application Name**: The text you enter will be the application name in BizTalk Administration.</span></span> <span data-ttu-id="cbcc2-163">不要**不**输入 BizTalk 应用程序 1。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-163">Do **not** enter BizTalk Application 1.</span></span>

    <span data-ttu-id="cbcc2-164">**部署包**:选择向应用程序项目，该 zip 文件，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-164">**Deployment package**: Select the zip file to your application project, and select **OK**.</span></span> 

8. <span data-ttu-id="cbcc2-165">选择**代理阶段**任务。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-165">Select the **Agent phase** task.</span></span> <span data-ttu-id="cbcc2-166">选择**默认**代理队列。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-166">Select the **Default** Agent queue.</span></span> <span data-ttu-id="cbcc2-167">**保存**所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-167">**Save** your changes.</span></span>

9. <span data-ttu-id="cbcc2-168">选择**释放** > **创建发布**:</span><span class="sxs-lookup"><span data-stu-id="cbcc2-168">Select **Release** > **Create release**:</span></span>  

    ![发行版中，创建发布](../core/media/vsts-create-release.png)

10. <span data-ttu-id="cbcc2-170">选择**队列**。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-170">Select **Queue**.</span></span> <span data-ttu-id="cbcc2-171">单击发布链接以查看状态。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-171">Check the status by clicking the release link.</span></span> <span data-ttu-id="cbcc2-172">如果失败，显示错误。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-172">If it fails, the error displays.</span></span> <span data-ttu-id="cbcc2-173">如果成功，应用程序添加到 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-173">If it succeeds, the application is added to the BizTalk Administration console.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="cbcc2-174">用户进行的操作</span><span class="sxs-lookup"><span data-stu-id="cbcc2-174">What you did</span></span>

<span data-ttu-id="cbcc2-175">在 VSTS 中，您将创建生成 Git 或 Team Foundation 版本控制 （无论您选择） 中的应用程序的生成定义。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-175">In VSTS, you created a build definition that builds your application within Git or Team Foundation Version Control (whatever you chose).</span></span> <span data-ttu-id="cbcc2-176">当源代码管理中进行更改时，所做的更改将自动检测，并将它们推送。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-176">When changes are made within the source control, the changes are automatically detected, and you can push them.</span></span> <span data-ttu-id="cbcc2-177">在生成完成后，您将创建将部署到 BizTalk Server 中，可以在 BizTalk Server 管理中看到应用程序的发布定义。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-177">After the build completes, you created a release definition that deploys the application to BizTalk Server, which you can see in BizTalk Server Administration.</span></span> 

## <a name="next-step"></a><span data-ttu-id="cbcc2-178">下一步</span><span class="sxs-lookup"><span data-stu-id="cbcc2-178">Next step</span></span>
<span data-ttu-id="cbcc2-179">在此步骤中，已完成。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-179">At this step, you're done.</span></span> <span data-ttu-id="cbcc2-180">如果您愿意，可以在 BizTalk XML 绑定文件中，创建环境令牌和创建匹配环境令牌的 VSTS 中的变量。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-180">If you prefer, you can create environmental tokens within your BizTalk XML binding file, and create variables within VSTS that match the environmental tokens.</span></span> <span data-ttu-id="cbcc2-181">请参阅[配置环境令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="cbcc2-181">See [Configure environmental tokens and variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) for the details.</span></span> 
