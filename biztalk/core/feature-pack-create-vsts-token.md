---
title: "步骤 2-创建 VSTS 令牌并安装代理 |Microsoft 文档"
description: "到 Visual Studio 中，创建 VSTS 安全访问令牌，克隆 VSTS 项目并安装用于自动执行部署你的 BizTalk Server 项目的生成代理"
ms.custom: 
ms.date: 11/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46047f0bb6a536642d503d68bb4f9161ecdf7fc5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="step-2-create-the-token--install-the-agent"></a>第 2 步： 创建令牌与安装代理

在 Visual Studio Team Services 中创建个人访问令牌 (PAT)。 此标记是你的密码，并且 VSTS 生成代理使用进行身份验证。 创建它时，才显示该令牌。 之后，它未显示不再。 因此一旦你创建它，将其保存到可记住的位置中的另一个文件。 

详细信息在 PAT [VSTS 和 TFS 的身份验证使用个人访问令牌访问](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)。 

创建令牌后，你安装的生成代理，并将其配置为使用此令牌。 

## <a name="sign-into-vsts-and-create-the-token"></a>登录到 VSTS，并创建令牌
1. 转到[https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)，和使用工作或学校帐户登录。 登录后，被列出你的 VSTS 帐户。 在下面的示例中，该帐户是**mandiaprojects.visualstudio.com**。  

    ![VSTS 帐户](../core/media/team-services-accounts.png)

    如果你没有帐户，选择**创建新帐户**，然后输入一个名称。 若要管理你的代码，请选择个人偏好之间**Git 或 Team Foundation 版本控制**。 完成后，创建新帐户，和类似于站点*https://YourAccountName.visualstudio.com/MyFirstProject*打开：  

    ![Git 或 TFS](../core/media/git-or-team-foundation.png)

2. 打开你的 VSTS 帐户 (https://*YourAccountName*。 visualstudio.com)。 在右侧的顶部，选择你图标并选择**安全**: 

    ![打开你的帐户安全](../core/media/vsts-account-security.png)

3. **个人访问令牌**将自动打开。 如果你有现有代理，选中它，并确认**代理池 （读取、 管理）**选择：

    ![代理池的读取和管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > 你必须知道访问令牌。 如果不这样做，并且未注意它任意位置，不能检索。 在此情况下，创建一个新代理。 

    如果你没有现有代理，则选择**添加**、 输入的描述、 设置的过期日期，和选择你的帐户。 在**选择作用域**，选择**代理池 （读取、 管理）**: 

    ![创建新的代理-读取和管理](../core/media/vsts-new-build-agent.png)

    选择**创建令牌**。 **请注意标记的值;需要在将来的步骤。**

4. 选择**代码**，然后选择**Visual Studio 中的克隆**:  

    ![在项目中，选择代码](../core/media/vsts-project-code.png)  

    ![Visual Studio 中克隆](../core/media/vsts-clone-in-visual-studio.png)

5. Visual Studio 将打开。 Visual Studio 中，打开 BizTalk 解决方案。 

## <a name="install-the-build-agent"></a>安装生成代理

在 BizTalk 开发计算机上安装生成代理。 

1. 打开你的 VSTS 帐户和项目中，这一点喜欢*https://YourAccountName.visualstudio.com/MyFirstProject*。 选择设置图标，并选择**代理队列**:  

    ![设置 > 代理队列](../core/media/vsts-settings-agent-queues.png)

2. 选择**默认**代理，然后选择**下载代理**。 选择**下载**按钮，然后将文件保存到你**下载**文件夹。

3. 安装步骤自动打开。 遵循这些步骤的最新的详细信息。 下面是一些指南： 

    1. 以管理员身份打开 Windows PowerShell。

    2. 若要创建代理，请输入： 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        Vsts 代理文件版本更改。 因此按照特定的详细信息的 VSTS 安装步骤。 你命中后输入，这可能需要几分钟以便返回的提示。 

    3. 若要配置的代理，请输入： 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. 输入以下详细信息：  
        
        | 属性 | 值 |
        | --- | --- |
        | 服务器 URL| https://{your-account}.visualstudio.com |
        | 身份验证类型 | PAT |
        | 个人访问令牌 | 将你的 VSTS 标记粘贴 |
        | 代理池 | 输入默认值 |
        | 代理名称 | 输入默认值 |
        | 替换 | *如果你有现有代理仅显示* |
        | 工作文件夹 | 输入默认值 |
        | 作为服务运行代理 | 是 |
        | 用户帐户 | 这是取决于你，但你可能会遇到权限问题。 <br/><br/>考虑输入你当前登录的帐户，这是本地管理员。 |

    5. 完成后，如下所示 PowerShell 窗口：  
    
        ![代理安装](../core/media/vsts-agent-powershell-install.png)

4. 打开 services.msc 以查看新的服务。 应运行：  

    ![服务正在运行](../core/media/vsts-service.png)

    如果此服务无法启动，[删除和重新配置代理](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)使用具有多个双重权限的帐户。


## <a name="what-you-did"></a>您进行的操作

登录到你的 VSTS 帐户，并创建了一个安全令牌。 此安全令牌是像的密码，并允许你访问你的 VSTS 项目。 它只会显示一次，因此确保你保存它。 你还克隆到 Visual Studio 中，你的 VSTS 项目，并创建 BizTalk 开发计算机作为服务运行的代理。 此代理使用的安全令牌。 

## <a name="next-steps"></a>后续步骤
[步骤 3： 创建构建并发布定义](feature-pack-add-build-release-definitions.md)  
[配置环境的令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)