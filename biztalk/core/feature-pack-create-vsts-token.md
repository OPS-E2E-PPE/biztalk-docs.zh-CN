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
# <a name="step-2-create-the-token--install-the-agent"></a>步骤 2： 创建令牌和安装代理

Visual Studio Team Services 中创建个人访问令牌 (PAT)。 此令牌为你的密码，并由 VSTS 生成代理进行身份验证。 在创建时，仅显示标记。 然后，它不是再显示。 因此一旦你创建它，请将其保存到可记住的位置中的另一个文件。 

在 PAT 的详细信息[使用个人访问令牌访问用于 VSTS 和 TFS 进行身份验证](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)。 

创建令牌后，你安装的生成代理，并将其配置为使用此令牌。 

## <a name="before-you-begin"></a>开始之前
完整[步骤 1-添加应用程序项目，然后更新 json](feature-pack-add-application-project.md)。

## <a name="sign-into-vsts-and-create-the-token"></a>登录到 VSTS，并创建令牌
1. 转到[ https://app.vsaex.visualstudio.com/go/profile ](https://app.vsaex.visualstudio.com/go/profile)，并使用工作或学校帐户登录。 登录后，列出你的 VSTS 帐户。 在以下示例中，该帐户是**mandiaprojects.visualstudio.com**。  

    ![VSTS 帐户](../core/media/team-services-accounts.png)

    如果还没有帐户，请选择**创建新帐户**，并输入一个名称。 若要管理你的代码，选择你的个人喜好之间**Git 或 Team Foundation 版本控制**。 完成后，创建新帐户，和类似于站点*https://YourAccountName.visualstudio.com/MyFirstProject*打开：  

    ![Git 或 TFS](../core/media/git-or-team-foundation.png)

2. 打开你的 VSTS 帐户 (https://<em>YourAccountName</em>。 visualstudio.com)。 在右侧角，选择您的图标，然后选择**安全**: 

    ![打开你的帐户安全](../core/media/vsts-account-security.png)

3. **个人访问令牌**会自动打开。 如果现有代理，选择它，并确认**代理池 （读取、 管理）** 处于选中状态：

    ![代理池的读取和管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > 您必须知道的访问令牌。 如果不这样做，并且未记下任何位置，不能检索。 在此情况下，创建新的代理。 

    如果没有现有代理，请选择**添加**，输入描述、 设置过期日期，并选择你的帐户。 在中**所选作用域**，选择**代理池 （读取、 管理）**: 

    ![创建新的代理-读取和管理](../core/media/vsts-new-build-agent.png)

    选择**创建令牌**。 **请注意标记的值;需要在将来的步骤。**

4. 选择**代码**，然后选择**在 Visual Studio 中的克隆**:  

    ![在项目中，选择代码](../core/media/vsts-project-code.png)  

    ![在 Visual Studio 中克隆](../core/media/vsts-clone-in-visual-studio.png)

5. Visual Studio 会打开。 Visual Studio 中，打开您的 BizTalk 解决方案。 

## <a name="install-the-build-agent"></a>安装生成代理

BizTalk 开发计算机上安装生成代理。 如果使用部署组，你想要将部署到的所有 BizTalk 服务器上安装生成代理。 以下步骤显示如何在一台计算机上安装生成代理。 使用部署组的详细信息，请参阅[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)。

1. 打开你的 VSTS 帐户和项目，它是喜欢*https://YourAccountName.visualstudio.com/MyFirstProject*。 选择设置图标，然后选择**代理队列**:  

    ![设置 > 代理队列](../core/media/vsts-settings-agent-queues.png)

2. 选择**默认**代理，然后选择**下载代理**。 选择**下载**按钮，然后将文件保存到您**下载**文件夹。

3. 安装步骤会自动打开。 按照这些步骤的最新的详细信息。 下面是一些指导： 

   1. 以管理员身份打开 Windows PowerShell。

   2. 若要创建代理，请输入： 

       ```powershell
       PS C:\> mkdir agent ; cd agent  

       PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
       ```

       Vsts 代理文件版本更改。 因此，请按照 VSTS 安装步骤的具体详细信息。 按后输入，这可能需要几分钟以便提示符返回。 

   3. 若要配置的代理，请输入： 

       ```powershell
       PS C:\agent> .\config.cmd
       ```

   4. 输入以下详细信息：  


      |        “属性”        |                                                                      ReplTest1                                                                       |
      |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
      |       服务器 URL       |                                                     https://{your-account}.visualstudio.com                                                      |
      |  身份验证类型   |                                                                       PAT                                                                        |
      | 个人访问令牌  |                                                              粘贴 VSTS 令牌                                                               |
      |       代理池       |                                                              输入的默认值                                                               |
      |       代理名称       |                                                              输入的默认值                                                               |
      |        替换         |                                                  *如果在具有现有代理仅显示*                                                   |
      |      工作文件夹       |                                                              输入的默认值                                                               |
      | 代理作为服务运行 |                                                                        是                                                                         |
      |      用户帐户      | 这取决于您，但可能会遇到权限问题。 <br/><br/>请考虑输入你当前登录的帐户，这是本地管理员。 |


   5. 完成后，在 PowerShell 窗口看起来如下所示：  

       ![代理安装](../core/media/vsts-agent-powershell-install.png)

4. 打开 services.msc，请参阅新的服务。 它应运行：  

    ![服务正在运行](../core/media/vsts-service.png)

    如果服务无法启动，请[删除并重新配置代理](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)使用具有多个权限的帐户。


## <a name="what-you-did"></a>用户进行的操作

登录到 VSTS 帐户，并创建了一个安全令牌。 此安全令牌是类似于密码，并使您可以访问到 VSTS 项目。 仅显示一次，因此确保您保存它。 您还在 VSTS 项目克隆到 Visual Studio 中，并创建作为服务运行在 BizTalk 开发计算机的代理。 此代理使用的安全令牌。 

## <a name="next-steps"></a>后续步骤
[步骤 3： 创建生成和发布定义](feature-pack-add-build-release-definitions.md)  
[配置环境令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)