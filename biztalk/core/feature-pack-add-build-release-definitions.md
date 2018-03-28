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
ms.openlocfilehash: 5ce84071fbc105fd9faddd794792273aae2e76b9
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="step-3-create-the-build-and-release-definition"></a>步骤 3： 创建构建并发布定义

生成和发布定义 Visual Studio Team Services 任务，并且可能通过 VSTS 管理员联系。生成定义将生成在 git 存储库时，项目和版本定义将将其部署到您的 BizTalk Server 环境。 

## <a name="before-you-begin"></a>開始之前
完成[步骤 2-创建 VSTS 令牌并安装代理](feature-pack-create-vsts-token.md)。

## <a name="add-the-build-tasks"></a>添加生成任务
1. 在项目中，选择**生成和发布**。 生成选项卡将打开。 创建**新建**定义：

    ![新的生成定义](../core/media/vsts-new-definition.png)

2. 选择**空**模板，然后选择**应用**:  

    ![选择空模板](../core/media/vsts-emtpy-template.png)
 
3. 设置**代理队列**为默认值： 

    ![选择默认的队列](../core/media/vsts-select-agent-queue.png)

4. 在**第 1 阶段**，添加任务，选择**Visual Studio 生成**，然后选择**添加**:

    ![添加 VS 生成任务](../core/media/vsts-add-visual-studio-task.png)

5. 单击 Visual Studio 生成的任务，只需添加，并设置以下属性：  

    | 属性 | 设置为 |
    | --- | --- | 
    | 显示名称 | *YourProjectName*生成解决方案 * *\*.sln | 
    | Visual Studio 版本 | Visual Studio 2015 | 
    | MSBuild 体系结构 | MSBuild x86 | 

6. 在**第 1 阶段**，添加任务，选择**发布生成项目**，然后选择**添加**: 

    ![添加 VS 生成任务](../core/media/vsts-add-publish-build-task.png)

7. 选择**发布项目**任务，并输入你首选**显示名称**。 有关**路径发布**，选择**...**按钮，然后选择应用程序项目文件夹 (例如 appProjectHelloWorld)。 选择“确定”。

8. **项目名称**可以是任何需要的内容。 选择**保存**。 

9. 转到**触发器**，并设置**触发状态**到**已启用**:  

    ![添加 VS 生成任务](../core/media/vsts-continuous-integration.png)

10. **保存并队列**若要测试你的生成定义。 当您进行排队，提示你输入代理队列和你的分支。 选择**默认**代理排队，并选择你的分支。 选择**队列**。  

11. 将启动新的生成，并且你可以选择它以检查成功或失败。 

## <a name="add-the-release-tasks"></a>添加释放任务

时生成成功，版本定义将部署到你的 BizTalk 服务器应用程序。 

1. 选择**版本**选项卡上，选择**新定义**。 

2. 选择**空**模板，然后选择**应用**:

    ![添加空模板](../core/media/vsts-empty-release-template.png)

3. 更改**环境名称**到**开发人员**，或者你想要调用它的任何内容。 

4. 选择**添加项目**，选择你的项目，生成定义中，并选择**添加**: 

5. 转到**任务**选项卡上，添加新任务： 

    ![添加版本任务](../core/media/vsts-new-release-tasks.png)

6. 从列表中，筛选结果，请选择**BizTalk Server 应用程序部署**任务，并选择**添加**:  

    ![添加 BizTalk 部署任务](../core/media/vsts-biztalk-application-deployment-task.png)

    如果**BizTalk Server 应用程序部署**ins't 列出，然后将其在安装[部署 BizTalk 应用程序](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)。

7. 选择**部署**任务，并输入值： 

    **操作名称**： 你的选项: ***创建新的 BizTalk 应用程序**： 部署一个新的应用程序。 如果应用程序已存在，它会卸载当前的应用程序 （句号），并安装新的应用程序。 如果启用持续集成，则它会自动将重新部署应用程序更新存储库中时。 
        * **更新现有的 BizTalk 应用程序**： 将更改，如架构，追加到已运行的应用程序。 它不需要应用程序完全重新部署。
        * **安装 BizTalk Server 应用程序**:[安装应用程序](../core/how-to-install-a-biztalk-application.md)，然后输入的 BizTalk 管理计算机的名称和部署包路径。

        ![Deploy operations](../core/media/vsts-deploy-operations.png)

    **应用程序名称**： 您输入的文本将是在 BizTalk 管理的应用程序名称。 执行**不**输入 BizTalk 应用程序 1。

    **部署包**： 选择您的应用程序项目，该 zip 文件，然后选择**确定**。 

8. 选择**代理阶段**任务。 选择**默认**代理队列。 **保存** 所做的更改。

9. 选择**释放** > **创建版本**:  

    ![发行版中，创建版本](../core/media/vsts-create-release.png)

10. 选择**队列**。 通过单击版本链接检查的状态。 如果失败，错误显示。 如果成功，则会将应用程序添加到 BizTalk 管理控制台。 

## <a name="what-you-did"></a>您进行的操作

在 VSTS，你将创建一个生成定义构建你的应用程序内 Git 或 Team Foundation 版本控制 （无论你选择）。 当源控件中进行更改时，所做的更改会自动检测，并可以将它们推送。 在生成完成后，你将创建部署到 BizTalk Server 中，你可以在 BizTalk Server 管理中看到应用程序的版本定义。 

## <a name="next-step"></a>下一步
在此步骤中，你已完成。 如果你愿意，可以在 BizTalk XML 绑定文件中，创建环境的令牌，并创建与环境的令牌匹配的 VSTS 中的变量。 请参阅[配置环境的令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)有关详细信息。 