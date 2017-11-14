---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: True
ROBOTS: NOINDEX
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
ms.openlocfilehash: 10d85b625d759af675ecc1a38d540da8a304ba43
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="configure-the-json-template-for-automatic-deployment"></a><span data-ttu-id="ee626-102">配置自动部署的 JSON 模板</span><span class="sxs-lookup"><span data-stu-id="ee626-102">Configure the JSON template for automatic deployment</span></span>


<span data-ttu-id="ee626-103">生成你的应用程序使用 Visual Studio Team Services 时，BizTalk 项目创建新的文件是 – (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="ee626-103">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – (.btaproj).</span></span> <span data-ttu-id="ee626-104">此新项目包含所有的 BizTalk 应用程序使用 VSTS 生成。</span><span class="sxs-lookup"><span data-stu-id="ee626-104">This new project holds all the BizTalk applications that you build using VSTS.</span></span> 

<span data-ttu-id="ee626-105">你的项目包括`BizTalkServerInventory.json`文件。</span><span class="sxs-lookup"><span data-stu-id="ee626-105">Your project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="ee626-106">在此文件中，添加你的 BizTalk 程序集、 添加 BizTalk 应用程序时，绑定文件和设置的部署序列。</span><span class="sxs-lookup"><span data-stu-id="ee626-106">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and set a deployment sequence.</span></span> 

<span data-ttu-id="ee626-107">本主题演示如何更新 json 文件。</span><span class="sxs-lookup"><span data-stu-id="ee626-107">This topic shows you how to update the json file.</span></span> 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a><span data-ttu-id="ee626-108">添加程序集、 绑定文件和部署序列</span><span class="sxs-lookup"><span data-stu-id="ee626-108">Add assemblies, binding files, and deployment sequence</span></span>

1. <span data-ttu-id="ee626-109">打开`BizTalkServerInventory.json`文件在你**BizTalk Server 应用程序**项目 (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="ee626-109">Open the `BizTalkServerInventory.json` file in your **BizTalk Server Application** project (.btaproj).</span></span>

2. <span data-ttu-id="ee626-110">该模板包括以下各节：</span><span class="sxs-lookup"><span data-stu-id="ee626-110">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="ee626-111">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="ee626-111">BizTalkAssemblies</span></span> | <span data-ttu-id="ee626-112">在应用程序中使用的程序集</span><span class="sxs-lookup"><span data-stu-id="ee626-112">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="ee626-113">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="ee626-113">BindingFiles</span></span> | <span data-ttu-id="ee626-114">你正在引用绑定文件</span><span class="sxs-lookup"><span data-stu-id="ee626-114">The binding files you are referencing</span></span>|
    | <span data-ttu-id="ee626-115">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="ee626-115">DeploymentSequence</span></span> | <span data-ttu-id="ee626-116">若要安装的元素序列</span><span class="sxs-lookup"><span data-stu-id="ee626-116">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="ee626-117">示例模板：</span><span class="sxs-lookup"><span data-stu-id="ee626-117">Sample template:</span></span> 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="ee626-119">根据你的解决方案的复杂性，必须在此 JSON 模板文件中引用您要在生成中的元素。</span><span class="sxs-lookup"><span data-stu-id="ee626-119">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="ee626-120">在`BizTalkAssemblies`，添加你的 BizTalk 应用程序使用的程序集：</span><span class="sxs-lookup"><span data-stu-id="ee626-120">In `BizTalkAssemblies`, add the assemblies used by your BizTalk applications:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="ee626-121">在`BindingsFiles`，添加你的 BizTalk 应用程序的绑定文件：</span><span class="sxs-lookup"><span data-stu-id="ee626-121">In `BindingsFiles`, add the binding files for your BizTalk applications:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="ee626-122">在`DeploymentSequence`，将应用程序名称添加你希望这些部署，并且在安装顺序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ee626-122">In `DeploymentSequence`, add the application names in the order you want them deployed and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```
    
6. <span data-ttu-id="ee626-123">**保存**所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ee626-123">**Save** your changes.</span></span> 

<span data-ttu-id="ee626-124">完成后，Visual Studio 团队服务部署任务服从所需的文件和安装序列。</span><span class="sxs-lookup"><span data-stu-id="ee626-124">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

## <a name="next-step"></a><span data-ttu-id="ee626-125">下一步</span><span class="sxs-lookup"><span data-stu-id="ee626-125">Next step</span></span>
<span data-ttu-id="ee626-126">[配置令牌和变量](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)绑定文件部署到多个相同的 BizTalk 应用程序中[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s。</span><span class="sxs-lookup"><span data-stu-id="ee626-126">[Configure tokens and variables](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md) in your binding file to deploy the same BizTalk application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s.</span></span>

 