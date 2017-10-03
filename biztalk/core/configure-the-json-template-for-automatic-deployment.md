---
title: "配置自动部署的 JSON 模板 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 0b7755a6-5a5a-4a6b-8f99-ac12a5fbf3d4
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: dba2870a2a7f9aeaaa627dba00afca85f3ca71c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-json-template-for-automatic-deployment"></a>配置自动部署的 JSON 模板


生成你的应用程序使用 Visual Studio Team Services 时，BizTalk 项目创建新的文件是 – (.btaproj)。 此新项目包含所有的 BizTalk 应用程序使用 VSTS 生成。 

你的项目包括`BizTalkServerInventory.json`文件。 在此文件中，添加你的 BizTalk 程序集、 添加 BizTalk 应用程序时，绑定文件和设置的部署序列。 

本主题演示如何更新 json 文件。 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a>添加程序集、 绑定文件和部署序列

1. 打开`BizTalkServerInventory.json`文件在你**BizTalk Server 应用程序**项目 (.btaproj)。

2. 该模板包括以下各节： 

    | | |
    |---|---|
    |BizTalkAssemblies | 在应用程序中使用的程序集 |
    |BindingFiles | 你正在引用绑定文件|
    | DeploymentSequence | 若要安装的元素序列|
    
    示例模板： 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > 根据你的解决方案的复杂性，必须在此 JSON 模板文件中引用您要在生成中的元素。

3. 在`BizTalkAssemblies`，添加你的 BizTalk 应用程序使用的程序集： 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. 在`BindingsFiles`，添加你的 BizTalk 应用程序的绑定文件： 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. 在`DeploymentSequence`，将应用程序名称添加你希望这些部署，并且在安装顺序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]: 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```
    
6. **保存**所做的更改。 

完成后，Visual Studio 团队服务部署任务服从所需的文件和安装序列。 

## <a name="next-step"></a>下一步
[配置令牌和变量](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)绑定文件部署到多个相同的 BizTalk 应用程序中[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s。

 