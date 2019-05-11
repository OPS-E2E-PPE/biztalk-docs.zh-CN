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
# <a name="step-3-create-the-build-and-release-definition"></a>步骤 3：创建生成和发布定义

生成和发布定义 Visual Studio Team Services 任务，并且可能通过 VSTS 管理员。生成定义将生成在 git 存储库时，你的项目和发布定义将将其部署到 BizTalk Server 环境。 

## <a name="before-you-begin"></a>开始之前
完整[步骤 2-创建 VSTS 令牌和安装代理](feature-pack-create-vsts-token.md)。

## <a name="add-the-build-tasks"></a>添加生成任务
1. 在项目中，选择**生成和发布**。 生成选项卡将打开。 创建**新建**定义：

    ![新的生成定义](../core/media/vsts-new-definition.png)

2. 选择**空**模板，然后选择**应用**:  

    ![选择空模板](../core/media/vsts-emtpy-template.png)
 
3. 设置**代理队列**为默认值： 

    ![选择默认队列](../core/media/vsts-select-agent-queue.png)

4. 在**第 1 阶段**，添加一个任务中，选择**Visual Studio 生成**，然后选择**添加**:

    ![添加 VS 生成任务](../core/media/vsts-add-visual-studio-task.png)

5. 单击 Visual Studio 生成的任务，只需添加，并设置以下属性：  

    | 属性 | 设置为 |
    | --- | --- | 
    | Display name | *YourProjectName*构建的解决方案 * *\*.sln | 
    | Visual Studio 版本 | Visual Studio 2015 | 
    | MSBuild 体系结构 | MSBuild x86 | 

6. 在**第 1 阶段**，添加一个任务中，选择**发布生成项目**，然后选择**添加**: 

    ![添加 VS 生成任务](../core/media/vsts-add-publish-build-task.png)

7. 选择**发布的项目**任务，并输入首选**显示名称**。 有关**发布路径**，选择 **...** 按钮，然后选择应用程序项目文件夹 (例如 appProjectHelloWorld)。 选择 **确定**。

8. **项目名称**可以是任何需要的内容。 选择“保存”。 

9. 转到**触发器**，并设置**触发状态**到**已启用**:  

    ![添加 VS 生成任务](../core/media/vsts-continuous-integration.png)

10. **保存并排队**来测试你的生成定义。 进行排队时，系统会提示输入代理队列和你的分支。 选择**默认**代理队列，然后选择你的分支。 选择**队列**。  

11. 将启动新的生成，并且可以选择它以检查成功或失败。 

## <a name="add-the-release-tasks"></a>添加发布任务

生成成功后，发布定义部署到 BizTalk Server 应用程序。 

1. 选择**版本**选项卡上，选择**新定义**。 

2. 选择**空**模板，然后选择**应用**:

    ![添加空的模板](../core/media/vsts-empty-release-template.png)

3. 更改**环境名称**到**开发人员**，或者任何你想要调用它。 

4. 选择**添加项目**，选择你的项目，生成定义中，然后选择**添加**: 

5. 转到**任务**选项卡上，添加新的任务： 

    ![添加发布任务](../core/media/vsts-new-release-tasks.png)

6. 从列表中，筛选结果，请选择**BizTalk Server 应用程序部署**任务，并选择**添加**:  

    ![添加 BizTalk 部署任务](../core/media/vsts-biztalk-application-deployment-task.png)

    如果**BizTalk Server 应用程序部署**ins't 列出，请将其安装在[部署 BizTalk 应用程序](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)。

7. 选择**部署**任务，并输入值： 

    **操作名称**:选项包括：   
        - **创建新的 BizTalk 应用程序**:部署新的应用程序。 如果应用程序已存在，它会卸载当前应用程序 （句号），并安装新的应用程序。 如果启用持续集成，则它会自动重新部署应用程序在更新存储库中时。   
        - **更新现有的 BizTalk 应用程序**:将更改，例如架构、 追加到已运行的应用程序。 它不需要完全重新部署应用程序。  
        - **安装 BizTalk Server 应用程序**:[安装的应用程序](../core/how-to-install-a-biztalk-application.md)，并输入 BizTalk 管理计算机名，以及部署包路径。  

     ![部署操作](../core/media/vsts-deploy-operations.png)

    **应用程序名称**:你输入的文本将是在 BizTalk 管理的应用程序名称。 不要**不**输入 BizTalk 应用程序 1。

    **部署包**:选择向应用程序项目，该 zip 文件，然后选择**确定**。 

8. 选择**代理阶段**任务。 选择**默认**代理队列。 **保存**所做的更改。

9. 选择**释放** > **创建发布**:  

    ![发行版中，创建发布](../core/media/vsts-create-release.png)

10. 选择**队列**。 单击发布链接以查看状态。 如果失败，显示错误。 如果成功，应用程序添加到 BizTalk 管理控制台。 

## <a name="what-you-did"></a>用户进行的操作

在 VSTS 中，您将创建生成 Git 或 Team Foundation 版本控制 （无论您选择） 中的应用程序的生成定义。 当源代码管理中进行更改时，所做的更改将自动检测，并将它们推送。 在生成完成后，您将创建将部署到 BizTalk Server 中，可以在 BizTalk Server 管理中看到应用程序的发布定义。 

## <a name="next-step"></a>下一步
在此步骤中，已完成。 如果您愿意，可以在 BizTalk XML 绑定文件中，创建环境令牌和创建匹配环境令牌的 VSTS 中的变量。 请参阅[配置环境令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)有关详细信息。 
