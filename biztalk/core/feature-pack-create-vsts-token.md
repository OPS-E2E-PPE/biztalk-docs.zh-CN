---
title: 步骤 2-创建 VSTS 令牌和安装代理 |Microsoft Docs
description: 到 Visual Studio 中，在 VSTS 项目创建 VSTS 安全访问令牌，克隆并安装生成代理以自动执行部署的 BizTalk Server 项目
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
ms.openlocfilehash: 1d26a218b6de83b1ab2e5a2dd46be215dcbb0f49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979342"
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="d7879-103">步骤 2： 创建令牌和安装代理</span><span class="sxs-lookup"><span data-stu-id="d7879-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="d7879-104">Visual Studio Team Services 中创建个人访问令牌 (PAT)。</span><span class="sxs-lookup"><span data-stu-id="d7879-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="d7879-105">此令牌为你的密码，并由 VSTS 生成代理进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d7879-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="d7879-106">在创建时，仅显示标记。</span><span class="sxs-lookup"><span data-stu-id="d7879-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="d7879-107">然后，它不是再显示。</span><span class="sxs-lookup"><span data-stu-id="d7879-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="d7879-108">因此一旦你创建它，请将其保存到可记住的位置中的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="d7879-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="d7879-109">在 PAT 的详细信息[使用个人访问令牌访问用于 VSTS 和 TFS 进行身份验证](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)。</span><span class="sxs-lookup"><span data-stu-id="d7879-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="d7879-110">创建令牌后，你安装的生成代理，并将其配置为使用此令牌。</span><span class="sxs-lookup"><span data-stu-id="d7879-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="d7879-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="d7879-111">Before you begin</span></span>
<span data-ttu-id="d7879-112">完整[步骤 1-添加应用程序项目，然后更新 json](feature-pack-add-application-project.md)。</span><span class="sxs-lookup"><span data-stu-id="d7879-112">Complete [Step 1 - Add Application project and update json](feature-pack-add-application-project.md).</span></span>

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="d7879-113">登录到 VSTS，并创建令牌</span><span class="sxs-lookup"><span data-stu-id="d7879-113">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="d7879-114">转到[ https://app.vsaex.visualstudio.com/go/profile ](https://app.vsaex.visualstudio.com/go/profile)，并使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d7879-114">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="d7879-115">登录后，列出你的 VSTS 帐户。</span><span class="sxs-lookup"><span data-stu-id="d7879-115">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="d7879-116">在以下示例中，该帐户是**mandiaprojects.visualstudio.com**。</span><span class="sxs-lookup"><span data-stu-id="d7879-116">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![VSTS 帐户](../core/media/team-services-accounts.png)

    <span data-ttu-id="d7879-118">如果还没有帐户，请选择**创建新帐户**，并输入一个名称。</span><span class="sxs-lookup"><span data-stu-id="d7879-118">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="d7879-119">若要管理你的代码，选择你的个人喜好之间**Git 或 Team Foundation 版本控制**。</span><span class="sxs-lookup"><span data-stu-id="d7879-119">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="d7879-120">完成后，创建新帐户，和类似于站点*https://YourAccountName.visualstudio.com/MyFirstProject*打开：</span><span class="sxs-lookup"><span data-stu-id="d7879-120">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![Git 或 TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="d7879-122">打开你的 VSTS 帐户 (https://<em>YourAccountName</em>。 visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="d7879-122">Open your VSTS account (https://<em>YourAccountName</em>.visualstudio.com).</span></span> <span data-ttu-id="d7879-123">在右侧角，选择您的图标，然后选择**安全**:</span><span class="sxs-lookup"><span data-stu-id="d7879-123">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![打开你的帐户安全](../core/media/vsts-account-security.png)

3. <span data-ttu-id="d7879-125">**个人访问令牌**会自动打开。</span><span class="sxs-lookup"><span data-stu-id="d7879-125">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="d7879-126">如果现有代理，选择它，并确认**代理池 （读取、 管理）** 处于选中状态：</span><span class="sxs-lookup"><span data-stu-id="d7879-126">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![代理池的读取和管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="d7879-128">您必须知道的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="d7879-128">You must know the access token.</span></span> <span data-ttu-id="d7879-129">如果不这样做，并且未记下任何位置，不能检索。</span><span class="sxs-lookup"><span data-stu-id="d7879-129">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="d7879-130">在此情况下，创建新的代理。</span><span class="sxs-lookup"><span data-stu-id="d7879-130">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="d7879-131">如果没有现有代理，请选择**添加**，输入描述、 设置过期日期，并选择你的帐户。</span><span class="sxs-lookup"><span data-stu-id="d7879-131">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="d7879-132">在中**所选作用域**，选择**代理池 （读取、 管理）**:</span><span class="sxs-lookup"><span data-stu-id="d7879-132">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![创建新的代理-读取和管理](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="d7879-134">选择**创建令牌**。</span><span class="sxs-lookup"><span data-stu-id="d7879-134">Select **Create Token**.</span></span> <span data-ttu-id="d7879-135">**请注意标记的值;需要在将来的步骤。**</span><span class="sxs-lookup"><span data-stu-id="d7879-135">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="d7879-136">选择**代码**，然后选择**在 Visual Studio 中的克隆**:</span><span class="sxs-lookup"><span data-stu-id="d7879-136">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![在项目中，选择代码](../core/media/vsts-project-code.png)  

    ![在 Visual Studio 中克隆](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="d7879-139">Visual Studio 会打开。</span><span class="sxs-lookup"><span data-stu-id="d7879-139">Visual Studio opens.</span></span> <span data-ttu-id="d7879-140">Visual Studio 中，打开您的 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="d7879-140">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="d7879-141">安装生成代理</span><span class="sxs-lookup"><span data-stu-id="d7879-141">Install the Build Agent</span></span>

<span data-ttu-id="d7879-142">BizTalk 开发计算机上安装生成代理。</span><span class="sxs-lookup"><span data-stu-id="d7879-142">The build agent is installed on the BizTalk development computer.</span></span> <span data-ttu-id="d7879-143">如果使用部署组，你想要将部署到的所有 BizTalk 服务器上安装生成代理。</span><span class="sxs-lookup"><span data-stu-id="d7879-143">If using deployment groups, the build agent is installed on all the BizTalk servers you want to deploy to.</span></span> <span data-ttu-id="d7879-144">以下步骤显示如何在一台计算机上安装生成代理。</span><span class="sxs-lookup"><span data-stu-id="d7879-144">The following steps show you how to install the build agent on a single computer.</span></span> <span data-ttu-id="d7879-145">使用部署组的详细信息，请参阅[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)。</span><span class="sxs-lookup"><span data-stu-id="d7879-145">For details on using deployment groups, see [Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span></span>

1. <span data-ttu-id="d7879-146">打开你的 VSTS 帐户和项目，它是喜欢*https://YourAccountName.visualstudio.com/MyFirstProject*。</span><span class="sxs-lookup"><span data-stu-id="d7879-146">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="d7879-147">选择设置图标，然后选择**代理队列**:</span><span class="sxs-lookup"><span data-stu-id="d7879-147">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![设置 > 代理队列](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="d7879-149">选择**默认**代理，然后选择**下载代理**。</span><span class="sxs-lookup"><span data-stu-id="d7879-149">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="d7879-150">选择**下载**按钮，然后将文件保存到您**下载**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d7879-150">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="d7879-151">安装步骤会自动打开。</span><span class="sxs-lookup"><span data-stu-id="d7879-151">The install steps automatically open.</span></span> <span data-ttu-id="d7879-152">按照这些步骤的最新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d7879-152">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="d7879-153">下面是一些指导：</span><span class="sxs-lookup"><span data-stu-id="d7879-153">Here is some guidance:</span></span> 

   1. <span data-ttu-id="d7879-154">以管理员身份打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d7879-154">Open Windows PowerShell as Administrator.</span></span>

   2. <span data-ttu-id="d7879-155">若要创建代理，请输入：</span><span class="sxs-lookup"><span data-stu-id="d7879-155">To create the agent, enter:</span></span> 

       ```powershell
       PS C:\> mkdir agent ; cd agent  

       PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
       ```

       <span data-ttu-id="d7879-156">Vsts 代理文件版本更改。</span><span class="sxs-lookup"><span data-stu-id="d7879-156">The vsts-agent file version changes.</span></span> <span data-ttu-id="d7879-157">因此，请按照 VSTS 安装步骤的具体详细信息。</span><span class="sxs-lookup"><span data-stu-id="d7879-157">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="d7879-158">按后输入，这可能需要几分钟以便提示符返回。</span><span class="sxs-lookup"><span data-stu-id="d7879-158">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

   3. <span data-ttu-id="d7879-159">若要配置的代理，请输入：</span><span class="sxs-lookup"><span data-stu-id="d7879-159">To configure the agent, enter:</span></span> 

       ```powershell
       PS C:\agent> .\config.cmd
       ```

   4. <span data-ttu-id="d7879-160">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="d7879-160">Enter the following details:</span></span>  


      |        <span data-ttu-id="d7879-161">“属性”</span><span class="sxs-lookup"><span data-stu-id="d7879-161">Property</span></span>        |                                                                      <span data-ttu-id="d7879-162">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d7879-162">Value</span></span>                                                                       |
      |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
      |       <span data-ttu-id="d7879-163">服务器 URL</span><span class="sxs-lookup"><span data-stu-id="d7879-163">Server URL</span></span>       |                                                     <span data-ttu-id="d7879-164">https://{your-account}.visualstudio.com</span><span class="sxs-lookup"><span data-stu-id="d7879-164">https://{your-account}.visualstudio.com</span></span>                                                      |
      |  <span data-ttu-id="d7879-165">身份验证类型</span><span class="sxs-lookup"><span data-stu-id="d7879-165">Authentication Type</span></span>   |                                                                       <span data-ttu-id="d7879-166">PAT</span><span class="sxs-lookup"><span data-stu-id="d7879-166">PAT</span></span>                                                                        |
      | <span data-ttu-id="d7879-167">个人访问令牌</span><span class="sxs-lookup"><span data-stu-id="d7879-167">Personal access token</span></span>  |                                                              <span data-ttu-id="d7879-168">粘贴 VSTS 令牌</span><span class="sxs-lookup"><span data-stu-id="d7879-168">Paste your VSTS token</span></span>                                                               |
      |       <span data-ttu-id="d7879-169">代理池</span><span class="sxs-lookup"><span data-stu-id="d7879-169">Agent pool</span></span>       |                                                              <span data-ttu-id="d7879-170">输入的默认值</span><span class="sxs-lookup"><span data-stu-id="d7879-170">Enter for the default</span></span>                                                               |
      |       <span data-ttu-id="d7879-171">代理名称</span><span class="sxs-lookup"><span data-stu-id="d7879-171">Agent name</span></span>       |                                                              <span data-ttu-id="d7879-172">输入的默认值</span><span class="sxs-lookup"><span data-stu-id="d7879-172">Enter for the default</span></span>                                                               |
      |        <span data-ttu-id="d7879-173">替换</span><span class="sxs-lookup"><span data-stu-id="d7879-173">Replace</span></span>         |                                                  <span data-ttu-id="d7879-174">*如果在具有现有代理仅显示*</span><span class="sxs-lookup"><span data-stu-id="d7879-174">*Only displays if you have an existing agent*</span></span>                                                   |
      |      <span data-ttu-id="d7879-175">工作文件夹</span><span class="sxs-lookup"><span data-stu-id="d7879-175">Work folder</span></span>       |                                                              <span data-ttu-id="d7879-176">输入的默认值</span><span class="sxs-lookup"><span data-stu-id="d7879-176">Enter for the default</span></span>                                                               |
      | <span data-ttu-id="d7879-177">代理作为服务运行</span><span class="sxs-lookup"><span data-stu-id="d7879-177">Run agent as a service</span></span> |                                                                        <span data-ttu-id="d7879-178">是</span><span class="sxs-lookup"><span data-stu-id="d7879-178">Y</span></span>                                                                         |
      |      <span data-ttu-id="d7879-179">用户帐户</span><span class="sxs-lookup"><span data-stu-id="d7879-179">User account</span></span>      | <span data-ttu-id="d7879-180">这取决于您，但可能会遇到权限问题。</span><span class="sxs-lookup"><span data-stu-id="d7879-180">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="d7879-181">请考虑输入你当前登录的帐户，这是本地管理员。</span><span class="sxs-lookup"><span data-stu-id="d7879-181">Consider entering your current logged-on account, which is a local Admin.</span></span> |


   5. <span data-ttu-id="d7879-182">完成后，在 PowerShell 窗口看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7879-182">When finished, your PowerShell window looks like the following:</span></span>  

       ![代理安装](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="d7879-184">打开 services.msc，请参阅新的服务。</span><span class="sxs-lookup"><span data-stu-id="d7879-184">Open services.msc to see the new service.</span></span> <span data-ttu-id="d7879-185">它应运行：</span><span class="sxs-lookup"><span data-stu-id="d7879-185">It should be running:</span></span>  

    ![服务正在运行](../core/media/vsts-service.png)

    <span data-ttu-id="d7879-187">如果服务无法启动，请[删除并重新配置代理](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)使用具有多个权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="d7879-187">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="d7879-188">用户进行的操作</span><span class="sxs-lookup"><span data-stu-id="d7879-188">What you did</span></span>

<span data-ttu-id="d7879-189">登录到 VSTS 帐户，并创建了一个安全令牌。</span><span class="sxs-lookup"><span data-stu-id="d7879-189">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="d7879-190">此安全令牌是类似于密码，并使您可以访问到 VSTS 项目。</span><span class="sxs-lookup"><span data-stu-id="d7879-190">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="d7879-191">仅显示一次，因此确保您保存它。</span><span class="sxs-lookup"><span data-stu-id="d7879-191">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="d7879-192">您还在 VSTS 项目克隆到 Visual Studio 中，并创建作为服务运行在 BizTalk 开发计算机的代理。</span><span class="sxs-lookup"><span data-stu-id="d7879-192">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="d7879-193">此代理使用的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="d7879-193">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="d7879-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d7879-194">Next steps</span></span>
[<span data-ttu-id="d7879-195">步骤 3： 创建生成和发布定义</span><span class="sxs-lookup"><span data-stu-id="d7879-195">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="d7879-196">配置环境令牌和变量</span><span class="sxs-lookup"><span data-stu-id="d7879-196">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)