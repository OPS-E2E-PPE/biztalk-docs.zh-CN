---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: true
ROBOTS: NOINDEX
title: 配置用于自动部署的 JSON 模板 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 0b7755a6-5a5a-4a6b-8f99-ac12a5fbf3d4
caps.latest.revision: 4
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d1587b7cf11b431e960035d4da4414a9a526c724
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356422"
---
# <a name="configure-the-json-template-for-automatic-deployment"></a>配置用于自动部署的 JSON 模板


生成使用 Visual Studio Team Services 在应用程序时，新的 BizTalk 项目文件创建 – (.btaproj)。 此新项目将包含使用 VSTS 生成的所有 BizTalk 应用程序。 

你的项目包括`BizTalkServerInventory.json`文件。 此文件中添加 BizTalk 程序集、 添加 BizTalk 应用程序，绑定文件和设置的部署序列。 

本主题演示如何更新的 json 文件。 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a>添加程序集、 绑定文件和部署序列

1. 打开`BizTalkServerInventory.json`文件中您**BizTalk Server 应用程序**项目 (.btaproj)。

2. 该模板包括以下各节： 

    | | |
    |---|---|
    |BizTalkAssemblies | 在应用程序中使用的程序集 |
    |BindingFiles | 所引用的绑定文件|
    | DeploymentSequence | 若要安装的元素序列|
    
    示例模板： 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > 具体取决于解决方案的复杂性，你想在生成中的元素必须引用此 JSON 模板文件中。

3. 在`BizTalkAssemblies`，添加 BizTalk 应用程序使用的程序集： 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. 在`BindingsFiles`，添加 BizTalk 应用程序的绑定文件： 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. 在中`DeploymentSequence`，用所需部署，并且在安装它们的顺序添加应用程序名称[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]: 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```
    
6. **保存**所做的更改。 

完成后，Visual Studio Team Service 部署任务将具有所需的文件和安装序列。 

## <a name="next-step"></a>下一步
[配置令牌和变量](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)绑定文件部署到多个相同的 BizTalk 应用程序中[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s。

 