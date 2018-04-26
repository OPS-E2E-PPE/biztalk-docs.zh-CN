---
title: 步骤 1-添加应用程序项目和更新 json |Microsoft 文档
description: 将 BizTalk Server 应用程序项目添加在 Visual Studio 中，并使用的 Dll，绑定文件和应用程序的 Visual Studio Team Services 的部署序列更新 BizTalkServerInventory.json 文件
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
ms.openlocfilehash: da1c4bb3cb12cf67e84bab7aa7f38c1a893eca00
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a>步骤 1： 在 Visual Studio 中添加 BizTalk Server 应用程序项目

生成你的应用程序使用 Visual Studio Team Services 时，BizTalk 项目创建新的文件是 –.btaproj。 此新项目包含所有 BizTalk 应用程序生成和部署使用 VSTS 生成和发布功能。 

BizTalk 应用程序项目包含`BizTalkServerInventory.json`文件。 在此文件中，添加你的 BizTalk 程序集、 添加 BizTalk 应用程序时，绑定文件，然后设置的部署序列。 

## <a name="before-you-begin"></a>開始之前

* 这些步骤假定你的一个现有的 BizTalk 项目。 如果没有，则可以使用 HelloWorld SDK 示例 (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。 
* 到 XML 绑定文件到你的 BizTalk 项目准备具有路径。 
* 知道你的 VSTS 帐户、 你的集合和你团队项目的详细信息。
* 熟悉 git 概念，包括克隆和使用存储库。 
* 请确保[功能包 2](https://aka.ms/bts2016fp2)安装。

## <a name="add-the-application-project"></a>添加应用程序项目

1. 在 BizTalk Server 中，在 Visual Studio 中打开你的解决方案 (ProjectName.sln)。 不要选择 Visual Studio Blend。

2. 在解决方案资源管理器，右键单击你的项目，然后选择**生成**。 请确保你的生成成功。 右键单击你的项目，然后选择**部署**。 请确保你部署成功。

3. 右键单击你的解决方案，选择**添加**，然后选择**添加新项目**。

4. 选择**BizTalk 项目**选项卡上，选择 **.NET Framework 4.6.1**从该下拉列表中，并选择**BizTalk 服务器应用程序项目**。 输入名称 (例如 appProjectHelloWorld)，并选择**确定**:  

    ![添加应用程序项目](../core/media/add-application-project.png)

5. 在解决方案资源管理器，右键单击新添加的应用程序项目 (.btaproj) 中，选择**添加**，选择**引用**。 展开**项目**选项卡，然后选中你的 BizTalk 项目 （你部署使用 VSTS 是项目）。 选择“确定”。  
    添加后，展开**引用**你应用程序的项目 (例如 appProjectHelloWorld) 若要查看 BizTalk 项目下你刚添加。 

6. 在解决方案资源管理器，右键单击你的应用程序项目 (.btaproj) 中，选择**添加**，选择**现有项**，和**添加**你绑定的 XML 文件。

7. 打开 binding.xml 的属性并设置**复制到输出目录**到**始终复制**。 **保存**所做的更改：  

    ![绑定文件属性](../core/media/xml-binding-file-properties.png)

8. 選擇性。 右键单击新添加的应用程序项目中，然后选择**属性**。 自定义**应用程序名称**要显示在 BizTalk 管理中：  

    ![应用程序名称](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a>配置的 JSON 模板

1. 在 Visual Studio 中，在应用程序项目 (.btaproj) 打开`BizTalkServerInventory.json`文件。 

2. 该模板包括以下各节： 

    | | |
    |---|---|
    |BizTalkAssemblies | 在应用程序中使用的程序集 |
    |BindingFiles | 你正在引用绑定文件|
    |DeploymentSequence | 若要安装的元素序列|
    
    示例模板： 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > 根据你的解决方案的复杂性，必须在此 JSON 模板文件中引用您要在生成中的元素。

3. 在`BizTalkAssemblies`，添加你的 BizTalk 项目使用的程序集： 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. 在`BindingsFiles`，添加你的 BizTalk 项目的绑定文件： 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. 在`DeploymentSequence`，将应用程序名称添加你希望他们部署，并在上安装的顺序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]: 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. **保存** 所做的更改。 完成后，如下所示.json 文件： 

    ```
    {
      "$schema": "C:\\Program Files (x86)\\Microsoft BizTalk Server 2016\\Developer Tools\\BizTalkServerAppplicationSchema.json",
      "BizTalkAssemblies": [
        {
          "Name": "HelloWorld",
          "Path": "HelloWorld\\bin\\Release\\HelloWorld.dll"
        }
      ],
      "BindingsFiles": [
        {
          "Name": "HelloWorldBinding",
          "Path": "HelloWorld\\HelloWorldBinding.xml"
        }
      ],
      "DeploymentSequence": [
        "HelloWorld", "HelloWorldBinding"
      ]
    }
    ```

7. **可选**。 右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**属性**。 你可以将调试或发布版本设置为新值。 我们不在这些步骤中，但请注意你可以执行此操作。  

    ![设置调试或发布版本](../core/media/application-project-version.png)

8. 右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**生成**。 如果成功，在中创建的 zip 文件 ***yourApplicationProject * \bin\debug**文件夹：  

    ![生成的 zip 文件](../core/media/application-project-zip-file.png)

9. 选择你的解决方案，然后选择**团队资源管理器**选项卡。在 VSTS 下, 选择**连接**。  

    ![连接到 Team Services](../core/media/connect-team-services.png)

10. 选择你的 VSTS 帐户、 你的集合和你的团队项目。 选择“确定”。 如果你未尚未创建 VSTS 帐户，然后创建一个 ([步骤 2： 创建 VSTS 令牌](feature-pack-create-vsts-token.md)提供了一些指导)。 一旦创建，回到此步骤中，并连接。  

    ![选择你的集合和项目](../core/media/team-collections-projects.png)

11. 连接时，可能会收到克隆此存储库的提示。 选择**克隆此存储库**链接。  

    ![克隆存储库](../core/media/vsts-clone-repository.png)

12. 记下的 URL 和路径，然后选择**克隆**:  

    ![存储库路径](../core/media/clone-repo-paths.png)

完成后，Visual Studio 团队服务部署任务服从所需的文件和安装序列。 

> [!TIP]
> 如果之后在 git 中克隆到你的项目中进行了更改，则可以**阶段**所做的更改，然后**推送**，Visual Studio 中的所有。 

## <a name="what-you-did"></a>您进行的操作

在 BizTalk 项目中，添加了 BizTalk 应用程序项目 (.btaproj)。 此项目使用自动完成部署使用 VSTS 你 BizTalk Server 项目。 创建应用程序项目后，你将添加到你的 BizTalk 项目的引用。 然后，您将更新一个 JSON 文件，告知在自动的部署，若要部署，若要使用，哪些绑定文件哪些 Dll 和部署应用程序的顺序。 

## <a name="next-steps"></a>后续步骤
[步骤 2： 创建 VSTS 令牌](feature-pack-create-vsts-token.md)  
[步骤 3： 创建构建并发布定义](feature-pack-add-build-release-definitions.md)  
[配置环境的令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
