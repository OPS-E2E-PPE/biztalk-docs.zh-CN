---
title: 步骤 2-创建 VSTS 令牌并安装代理 |Microsoft 文档
description: 到 Visual Studio 中，创建 VSTS 安全访问令牌，克隆 VSTS 项目并安装用于自动执行部署你的 BizTalk Server 项目的生成代理
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
ms.openlocfilehash: 77296d9f2325bebaba4f4fa1ce7c55034ef1ead6
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497686"
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="36125-103">第 2 步： 创建令牌与安装代理</span><span class="sxs-lookup"><span data-stu-id="36125-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="36125-104">在 Visual Studio Team Services 中创建个人访问令牌 (PAT)。</span><span class="sxs-lookup"><span data-stu-id="36125-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="36125-105">此标记是你的密码，并且 VSTS 生成代理使用进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="36125-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="36125-106">创建它时，才显示该令牌。</span><span class="sxs-lookup"><span data-stu-id="36125-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="36125-107">之后，它未显示不再。</span><span class="sxs-lookup"><span data-stu-id="36125-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="36125-108">因此一旦你创建它，将其保存到可记住的位置中的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="36125-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="36125-109">详细信息在 PAT [VSTS 和 TFS 的身份验证使用个人访问令牌访问](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)。</span><span class="sxs-lookup"><span data-stu-id="36125-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="36125-110">创建令牌后，你安装的生成代理，并将其配置为使用此令牌。</span><span class="sxs-lookup"><span data-stu-id="36125-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="36125-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="36125-111">Before you begin</span></span>
<span data-ttu-id="36125-112">完成[步骤 1-添加应用程序项目，并更新 json](feature-pack-add-application-project.md)。</span><span class="sxs-lookup"><span data-stu-id="36125-112">Complete [Step 1 - Add Application project and update json](feature-pack-add-application-project.md).</span></span>

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="36125-113">登录到 VSTS，并创建令牌</span><span class="sxs-lookup"><span data-stu-id="36125-113">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="36125-114">转到[https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)，和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="36125-114">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="36125-115">登录后，被列出你的 VSTS 帐户。</span><span class="sxs-lookup"><span data-stu-id="36125-115">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="36125-116">在下面的示例中，该帐户是**mandiaprojects.visualstudio.com**。</span><span class="sxs-lookup"><span data-stu-id="36125-116">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![VSTS 帐户](../core/media/team-services-accounts.png)

    <span data-ttu-id="36125-118">如果你没有帐户，选择**创建新帐户**，然后输入一个名称。</span><span class="sxs-lookup"><span data-stu-id="36125-118">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="36125-119">若要管理你的代码，请选择个人偏好之间**Git 或 Team Foundation 版本控制**。</span><span class="sxs-lookup"><span data-stu-id="36125-119">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="36125-120">完成后，创建新帐户，和类似于站点*https://YourAccountName.visualstudio.com/MyFirstProject*打开：</span><span class="sxs-lookup"><span data-stu-id="36125-120">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![Git 或 TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="36125-122">打开你的 VSTS 帐户 (https://*YourAccountName*。 visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="36125-122">Open your VSTS account (https://*YourAccountName*.visualstudio.com).</span></span> <span data-ttu-id="36125-123">在右侧的顶部，选择你图标并选择**安全**:</span><span class="sxs-lookup"><span data-stu-id="36125-123">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![打开你的帐户安全](../core/media/vsts-account-security.png)

3. <span data-ttu-id="36125-125">**个人访问令牌**将自动打开。</span><span class="sxs-lookup"><span data-stu-id="36125-125">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="36125-126">如果你有现有代理，选中它，并确认**代理池 （读取、 管理）** 选择：</span><span class="sxs-lookup"><span data-stu-id="36125-126">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![代理池的读取和管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="36125-128">你必须知道访问令牌。</span><span class="sxs-lookup"><span data-stu-id="36125-128">You must know the access token.</span></span> <span data-ttu-id="36125-129">如果不这样做，并且未注意它任意位置，不能检索。</span><span class="sxs-lookup"><span data-stu-id="36125-129">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="36125-130">在此情况下，创建一个新代理。</span><span class="sxs-lookup"><span data-stu-id="36125-130">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="36125-131">如果你没有现有代理，则选择**添加**、 输入的描述、 设置的过期日期，和选择你的帐户。</span><span class="sxs-lookup"><span data-stu-id="36125-131">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="36125-132">在**选择作用域**，选择**代理池 （读取、 管理）**:</span><span class="sxs-lookup"><span data-stu-id="36125-132">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![创建新的代理-读取和管理](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="36125-134">选择**创建令牌**。</span><span class="sxs-lookup"><span data-stu-id="36125-134">Select **Create Token**.</span></span> <span data-ttu-id="36125-135">**请注意标记的值;需要在将来的步骤。**</span><span class="sxs-lookup"><span data-stu-id="36125-135">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="36125-136">选择**代码**，然后选择**Visual Studio 中的克隆**:</span><span class="sxs-lookup"><span data-stu-id="36125-136">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![在项目中，选择代码](../core/media/vsts-project-code.png)  

    ![Visual Studio 中克隆](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="36125-139">Visual Studio 将打开。</span><span class="sxs-lookup"><span data-stu-id="36125-139">Visual Studio opens.</span></span> <span data-ttu-id="36125-140">Visual Studio 中，打开 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="36125-140">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="36125-141">安装生成代理</span><span class="sxs-lookup"><span data-stu-id="36125-141">Install the Build Agent</span></span>

<span data-ttu-id="36125-142">在 BizTalk 开发计算机上安装生成代理。</span><span class="sxs-lookup"><span data-stu-id="36125-142">The build agent is installed on the BizTalk development computer.</span></span> <span data-ttu-id="36125-143">如果使用部署组，是你想要部署到的所有 BizTalk 服务器上安装的生成代理。</span><span class="sxs-lookup"><span data-stu-id="36125-143">If using deployment groups, the build agent is installed on all the BizTalk servers you want to deploy to.</span></span> <span data-ttu-id="36125-144">以下步骤显示如何在一台计算机上安装的生成代理。</span><span class="sxs-lookup"><span data-stu-id="36125-144">The following steps show you how to install the build agent on a single computer.</span></span> <span data-ttu-id="36125-145">有关使用部署组的详细信息，请参阅[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)。</span><span class="sxs-lookup"><span data-stu-id="36125-145">For details on using deployment groups, see [Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span></span>

1. <span data-ttu-id="36125-146">打开你的 VSTS 帐户和项目中，这一点喜欢*https://YourAccountName.visualstudio.com/MyFirstProject*。</span><span class="sxs-lookup"><span data-stu-id="36125-146">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="36125-147">选择设置图标，并选择**代理队列**:</span><span class="sxs-lookup"><span data-stu-id="36125-147">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![设置 > 代理队列](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="36125-149">选择**默认**代理，然后选择**下载代理**。</span><span class="sxs-lookup"><span data-stu-id="36125-149">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="36125-150">选择**下载**按钮，然后将文件保存到你**下载**文件夹。</span><span class="sxs-lookup"><span data-stu-id="36125-150">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="36125-151">安装步骤自动打开。</span><span class="sxs-lookup"><span data-stu-id="36125-151">The install steps automatically open.</span></span> <span data-ttu-id="36125-152">遵循这些步骤的最新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="36125-152">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="36125-153">下面是一些指南：</span><span class="sxs-lookup"><span data-stu-id="36125-153">Here is some guidance:</span></span> 

    1. <span data-ttu-id="36125-154">以管理员身份打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="36125-154">Open Windows PowerShell as Administrator.</span></span>

    2. <span data-ttu-id="36125-155">若要创建代理，请输入：</span><span class="sxs-lookup"><span data-stu-id="36125-155">To create the agent, enter:</span></span> 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        <span data-ttu-id="36125-156">Vsts 代理文件版本更改。</span><span class="sxs-lookup"><span data-stu-id="36125-156">The vsts-agent file version changes.</span></span> <span data-ttu-id="36125-157">因此按照特定的详细信息的 VSTS 安装步骤。</span><span class="sxs-lookup"><span data-stu-id="36125-157">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="36125-158">你命中后输入，这可能需要几分钟以便返回的提示。</span><span class="sxs-lookup"><span data-stu-id="36125-158">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

    3. <span data-ttu-id="36125-159">若要配置的代理，请输入：</span><span class="sxs-lookup"><span data-stu-id="36125-159">To configure the agent, enter:</span></span> 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. <span data-ttu-id="36125-160">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="36125-160">Enter the following details:</span></span>  
        
        | <span data-ttu-id="36125-161">属性</span><span class="sxs-lookup"><span data-stu-id="36125-161">Property</span></span> | <span data-ttu-id="36125-162">值</span><span class="sxs-lookup"><span data-stu-id="36125-162">Value</span></span> |
        | --- | --- |
        | <span data-ttu-id="36125-163">服务器 URL</span><span class="sxs-lookup"><span data-stu-id="36125-163">Server URL</span></span>| <span data-ttu-id="36125-164">https://{your-account}.visualstudio.com</span><span class="sxs-lookup"><span data-stu-id="36125-164">https://{your-account}.visualstudio.com</span></span> |
        | <span data-ttu-id="36125-165">身份验证类型</span><span class="sxs-lookup"><span data-stu-id="36125-165">Authentication Type</span></span> | <span data-ttu-id="36125-166">PAT</span><span class="sxs-lookup"><span data-stu-id="36125-166">PAT</span></span> |
        | <span data-ttu-id="36125-167">个人访问令牌</span><span class="sxs-lookup"><span data-stu-id="36125-167">Personal access token</span></span> | <span data-ttu-id="36125-168">将你的 VSTS 标记粘贴</span><span class="sxs-lookup"><span data-stu-id="36125-168">Paste your VSTS token</span></span> |
        | <span data-ttu-id="36125-169">代理池</span><span class="sxs-lookup"><span data-stu-id="36125-169">Agent pool</span></span> | <span data-ttu-id="36125-170">输入默认值</span><span class="sxs-lookup"><span data-stu-id="36125-170">Enter for the default</span></span> |
        | <span data-ttu-id="36125-171">代理名称</span><span class="sxs-lookup"><span data-stu-id="36125-171">Agent name</span></span> | <span data-ttu-id="36125-172">输入默认值</span><span class="sxs-lookup"><span data-stu-id="36125-172">Enter for the default</span></span> |
        | <span data-ttu-id="36125-173">替换</span><span class="sxs-lookup"><span data-stu-id="36125-173">Replace</span></span> | <span data-ttu-id="36125-174">*如果你有现有代理仅显示*</span><span class="sxs-lookup"><span data-stu-id="36125-174">*Only displays if you have an existing agent*</span></span> |
        | <span data-ttu-id="36125-175">工作文件夹</span><span class="sxs-lookup"><span data-stu-id="36125-175">Work folder</span></span> | <span data-ttu-id="36125-176">输入默认值</span><span class="sxs-lookup"><span data-stu-id="36125-176">Enter for the default</span></span> |
        | <span data-ttu-id="36125-177">作为服务运行代理</span><span class="sxs-lookup"><span data-stu-id="36125-177">Run agent as a service</span></span> | <span data-ttu-id="36125-178">是</span><span class="sxs-lookup"><span data-stu-id="36125-178">Y</span></span> |
        | <span data-ttu-id="36125-179">用户帐户</span><span class="sxs-lookup"><span data-stu-id="36125-179">User account</span></span> | <span data-ttu-id="36125-180">这是取决于你，但你可能会遇到权限问题。</span><span class="sxs-lookup"><span data-stu-id="36125-180">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="36125-181">考虑输入你当前登录的帐户，这是本地管理员。</span><span class="sxs-lookup"><span data-stu-id="36125-181">Consider entering your current logged-on account, which is a local Admin.</span></span> |

    5. <span data-ttu-id="36125-182">完成后，如下所示 PowerShell 窗口：</span><span class="sxs-lookup"><span data-stu-id="36125-182">When finished, your PowerShell window looks like the following:</span></span>  
    
        ![代理安装](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="36125-184">打开 services.msc 以查看新的服务。</span><span class="sxs-lookup"><span data-stu-id="36125-184">Open services.msc to see the new service.</span></span> <span data-ttu-id="36125-185">应运行：</span><span class="sxs-lookup"><span data-stu-id="36125-185">It should be running:</span></span>  

    ![服务正在运行](../core/media/vsts-service.png)

    <span data-ttu-id="36125-187">如果此服务无法启动，[删除和重新配置代理](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)使用具有多个双重权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="36125-187">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="36125-188">您进行的操作</span><span class="sxs-lookup"><span data-stu-id="36125-188">What you did</span></span>

<span data-ttu-id="36125-189">登录到你的 VSTS 帐户，并创建了一个安全令牌。</span><span class="sxs-lookup"><span data-stu-id="36125-189">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="36125-190">此安全令牌是像的密码，并允许你访问你的 VSTS 项目。</span><span class="sxs-lookup"><span data-stu-id="36125-190">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="36125-191">它只会显示一次，因此确保你保存它。</span><span class="sxs-lookup"><span data-stu-id="36125-191">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="36125-192">你还克隆到 Visual Studio 中，你的 VSTS 项目，并创建 BizTalk 开发计算机作为服务运行的代理。</span><span class="sxs-lookup"><span data-stu-id="36125-192">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="36125-193">此代理使用的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="36125-193">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="36125-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="36125-194">Next steps</span></span>
[<span data-ttu-id="36125-195">步骤 3： 创建构建并发布定义</span><span class="sxs-lookup"><span data-stu-id="36125-195">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="36125-196">配置环境的令牌和变量</span><span class="sxs-lookup"><span data-stu-id="36125-196">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)