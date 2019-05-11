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
# <a name="configure-the-json-template-for-automatic-deployment"></a><span data-ttu-id="f5625-102">配置用于自动部署的 JSON 模板</span><span class="sxs-lookup"><span data-stu-id="f5625-102">Configure the JSON template for automatic deployment</span></span>


<span data-ttu-id="f5625-103">生成使用 Visual Studio Team Services 在应用程序时，新的 BizTalk 项目文件创建 – (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="f5625-103">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – (.btaproj).</span></span> <span data-ttu-id="f5625-104">此新项目将包含使用 VSTS 生成的所有 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f5625-104">This new project holds all the BizTalk applications that you build using VSTS.</span></span> 

<span data-ttu-id="f5625-105">你的项目包括`BizTalkServerInventory.json`文件。</span><span class="sxs-lookup"><span data-stu-id="f5625-105">Your project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="f5625-106">此文件中添加 BizTalk 程序集、 添加 BizTalk 应用程序，绑定文件和设置的部署序列。</span><span class="sxs-lookup"><span data-stu-id="f5625-106">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and set a deployment sequence.</span></span> 

<span data-ttu-id="f5625-107">本主题演示如何更新的 json 文件。</span><span class="sxs-lookup"><span data-stu-id="f5625-107">This topic shows you how to update the json file.</span></span> 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a><span data-ttu-id="f5625-108">添加程序集、 绑定文件和部署序列</span><span class="sxs-lookup"><span data-stu-id="f5625-108">Add assemblies, binding files, and deployment sequence</span></span>

1. <span data-ttu-id="f5625-109">打开`BizTalkServerInventory.json`文件中您**BizTalk Server 应用程序**项目 (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="f5625-109">Open the `BizTalkServerInventory.json` file in your **BizTalk Server Application** project (.btaproj).</span></span>

2. <span data-ttu-id="f5625-110">该模板包括以下各节：</span><span class="sxs-lookup"><span data-stu-id="f5625-110">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="f5625-111">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="f5625-111">BizTalkAssemblies</span></span> | <span data-ttu-id="f5625-112">在应用程序中使用的程序集</span><span class="sxs-lookup"><span data-stu-id="f5625-112">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="f5625-113">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="f5625-113">BindingFiles</span></span> | <span data-ttu-id="f5625-114">所引用的绑定文件</span><span class="sxs-lookup"><span data-stu-id="f5625-114">The binding files you are referencing</span></span>|
    | <span data-ttu-id="f5625-115">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="f5625-115">DeploymentSequence</span></span> | <span data-ttu-id="f5625-116">若要安装的元素序列</span><span class="sxs-lookup"><span data-stu-id="f5625-116">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="f5625-117">示例模板：</span><span class="sxs-lookup"><span data-stu-id="f5625-117">Sample template:</span></span> 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="f5625-119">具体取决于解决方案的复杂性，你想在生成中的元素必须引用此 JSON 模板文件中。</span><span class="sxs-lookup"><span data-stu-id="f5625-119">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="f5625-120">在`BizTalkAssemblies`，添加 BizTalk 应用程序使用的程序集：</span><span class="sxs-lookup"><span data-stu-id="f5625-120">In `BizTalkAssemblies`, add the assemblies used by your BizTalk applications:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="f5625-121">在`BindingsFiles`，添加 BizTalk 应用程序的绑定文件：</span><span class="sxs-lookup"><span data-stu-id="f5625-121">In `BindingsFiles`, add the binding files for your BizTalk applications:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="f5625-122">在中`DeploymentSequence`，用所需部署，并且在安装它们的顺序添加应用程序名称[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f5625-122">In `DeploymentSequence`, add the application names in the order you want them deployed and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```
    
6. <span data-ttu-id="f5625-123">**保存**所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f5625-123">**Save** your changes.</span></span> 

<span data-ttu-id="f5625-124">完成后，Visual Studio Team Service 部署任务将具有所需的文件和安装序列。</span><span class="sxs-lookup"><span data-stu-id="f5625-124">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

## <a name="next-step"></a><span data-ttu-id="f5625-125">下一步</span><span class="sxs-lookup"><span data-stu-id="f5625-125">Next step</span></span>
<span data-ttu-id="f5625-126">[配置令牌和变量](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)绑定文件部署到多个相同的 BizTalk 应用程序中[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s。</span><span class="sxs-lookup"><span data-stu-id="f5625-126">[Configure tokens and variables](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md) in your binding file to deploy the same BizTalk application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s.</span></span>

 