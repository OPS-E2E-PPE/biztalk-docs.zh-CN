---
title: 步骤 1-添加应用程序项目并更新 json |Microsoft Docs
description: 将 BizTalk Server 应用程序项目添加在 Visual Studio 中，并更新 BizTalkServerInventory.json 文件与 Dll、 绑定文件和应用程序的 Visual Studio Team Services 的部署序列
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
ms.openlocfilehash: e0230d0b280be412e3138ffbafd83d3810cf1163
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826357"
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a>步骤 1： 在 Visual Studio 中添加 BizTalk Server 应用程序项目

生成使用 Visual Studio Team Services 在应用程序时，新的 BizTalk 项目文件创建 –.btaproj。 此新项目将包含所有 BizTalk 应用程序生成和部署使用 VSTS 生成和发布功能。 

BizTalk 应用程序项目包含`BizTalkServerInventory.json`文件。 此文件中添加 BizTalk 程序集、 添加 BizTalk 应用程序，绑定文件，然后设置部署序列。 

## <a name="before-you-begin"></a>开始之前

* 这些步骤假定你有现有的 BizTalk 项目。 如果没有设置，可以使用 HelloWorld SDK 示例 (\Program 文件 (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。 
* 具有到向 BizTalk 项目准备就绪的 XML 绑定文件的路径。 
* 知道你的 VSTS 帐户、 你的集合，以及你团队项目的详细信息。
* 已经熟悉 git 概念，包括克隆和使用存储库。 
* 请务必[功能包 2](https://aka.ms/bts2016fp2)安装。

## <a name="add-the-application-project"></a>添加应用程序项目

1. 在 BizTalk 服务器上，在 Visual Studio 中打开解决方案 (ProjectName.sln)。 不要选择 Visual Studio Blend。

2. 在解决方案资源管理器，右键单击你的项目，然后选择**生成**。 请确保你的生成成功。 右键单击你的项目，然后选择**部署**。 请确保在部署成功。

3. 右键单击你的解决方案，选择**外**，然后选择**添加新项目**。

4. 选择**BizTalk 项目**选项卡上，选择 **.NET Framework 4.6.1**从该下拉列表中，然后选择**BizTalk Server 应用程序项目**。 输入名称 (例如 appProjectHelloWorld)，并选择**确定**:  

    ![添加应用程序项目](../core/media/add-application-project.png)

5. 在解决方案资源管理器中右键单击新添加的应用程序项目 (.btaproj) 中，选择**外**，选择**引用**。 展开**项目**选项卡，然后检查您的 BizTalk 项目 （在使用 VSTS 部署是项目）。 选择“确定”。  
    添加后，展开**引用**应用程序项目 (例如 appProjectHelloWorld) 若要查看 BizTalk 项目下你刚添加。 

6. 在解决方案资源管理器中右键单击你的应用程序项目 (.btaproj) 中，选择**外**，选择**现有项**，并**添加**绑定 XML 文件。

7. 打开 binding.xml 的属性，并设置**复制到输出目录**到**始终复制**。 **保存**所做的更改：  

    ![绑定文件属性](../core/media/xml-binding-file-properties.png)

8. 可选。 右键单击新添加的应用程序项目，然后选择**属性**。 自定义**应用程序名称**想要显示在 BizTalk 管理：  

    ![应用程序名称](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a>配置 JSON 模板

1. 在 Visual Studio 中，在应用程序项目 (.btaproj) 打开`BizTalkServerInventory.json`文件。 

2. 该模板包括以下各节： 

    | | |
    |---|---|
    |BizTalkAssemblies | 在应用程序中使用的程序集 |
    |BindingFiles | 所引用的绑定文件|
    |DeploymentSequence | 若要安装的元素序列|
    
    示例模板： 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > 具体取决于解决方案的复杂性，你想在生成中的元素必须引用此 JSON 模板文件中。

3. 在`BizTalkAssemblies`，添加您的 BizTalk 项目使用的程序集： 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. 在`BindingsFiles`，添加您的 BizTalk 项目的绑定文件： 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. 在中`DeploymentSequence`，用所需部署，并在安装它们的顺序添加应用程序名称[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]: 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. **保存**所做的更改。 完成后，你的.json 文件看起来如下所示： 

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

7. **可选**。 右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**属性**。 为新值，可以设置调试或发布版本。 我们不在这些步骤，但请注意你可以执行此操作。  

    ![设置调试或发布版本](../core/media/application-project-version.png)

8. 右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**生成**。 如果成功，在中创建的 zip 文件 **_yourApplicationProject_\bin\debug**文件夹：  

    ![生成的 zip 文件](../core/media/application-project-zip-file.png)

9. 选择你的解决方案，然后选择**团队资源管理器**选项卡。在 VSTS 中，选择**Connect**。  

    ![连接到 Team Services](../core/media/connect-team-services.png)

10. 选择你的 VSTS 帐户、 你的集合和你的团队项目。 选择“确定”。 如果未尚未创建 VSTS 帐户，然后创建一个 ([步骤 2： 创建 VSTS 令牌](feature-pack-create-vsts-token.md)提供一些指导)。 在创建后回到此步骤中，并连接。  

    ![选择集合和项目](../core/media/team-collections-projects.png)

11. 连接时，可能会收到提示克隆此存储库。 选择**克隆此存储库**链接。  

    ![克隆存储库](../core/media/vsts-clone-repository.png)

12. 记下的 URL 和路径，然后选择**克隆**:  

    ![存储库路径](../core/media/clone-repo-paths.png)

完成后，Visual Studio Team Service 部署任务将具有所需的文件和安装序列。 

> [!TIP]
> 如果之后在 git 中克隆到你的项目进行更改，则可以**阶段**所做的更改，然后**推送**，Visual Studio 内。 

## <a name="what-you-did"></a>用户进行的操作

在 BizTalk 项目中，您添加了一个 BizTalk 应用程序项目 (.btaproj)。 此项目用于自动执行部署的 BizTalk Server 项目使用 VSTS。 创建应用程序项目后，即添加到 BizTalk 项目的引用。 然后，您更新的 JSON 文件，告知自动的部署要部署，若要使用，哪些绑定文件的 Dll 和部署应用程序的顺序。 

## <a name="next-steps"></a>后续步骤
[步骤 2： 创建 VSTS 令牌](feature-pack-create-vsts-token.md)  
[步骤 3： 创建生成和发布定义](feature-pack-add-build-release-definitions.md)  
[配置环境令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
